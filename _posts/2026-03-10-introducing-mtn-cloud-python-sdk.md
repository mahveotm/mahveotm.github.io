---
layout: post
title: Introducing the MTN Cloud Python SDK
subtitle: Programmatic access to MTN Cloud, the way it should be.
tags: [software, cloud, mtn cloud, python, open-source]
---

If you have been following my [MTN Cloud coverage](https://blog.mahveo.codes/2026-03-08-thoughts-on-mtn-cloud-ga/), you know I have spent a good amount of time in the GA environment lately. And while the console works fine for poking around, I quickly realized that clicking through nested menus is not how anybody wants to manage infrastructure long-term.

So I built something: the **[MTN Cloud Python SDK](https://pypi.org/project/mtn-cloud/)**.

### Why Not Just Use the Morpheus API?

MTN Cloud runs on Morpheus, and yes, Morpheus has [API documentation](https://apidocs.morpheusdata.com/reference). But Morpheus is designed to orchestrate infrastructure across AWS, Azure, GCP, VMware, and a dozen other platforms. The docs reflect that. You are staring at endpoints with dozens of parameters, most of which are irrelevant for MTN's OpenStack deployment. Error responses are inconsistent. Required fields are unclear. You spend more time figuring out what to ignore than what to use.

This SDK strips away all that noise and gives you a clean, MTN-specific interface.

### What It Offers

- **Built-in Reference Data:** Service plan IDs, layout IDs, instance types - all mapped and documented. No more guessing what `6775` means.
- **Typed Models:** Full Pydantic support. Your IDE tells you exactly what fields are required before you run anything.
- **MTN-Specific Defaults:** You are not deploying to AWS through Morpheus. You are deploying to MTN Cloud. The SDK reflects that.
- **Automatic Retries:** Built-in exponential backoff for those inevitable network hiccups.
- **Sensible Errors:** Specific exception classes (`AuthenticationError`, `NotFoundError`, `RateLimitError`) instead of cryptic API responses.

### Before You Start: Create a Resource Pool

In MTN Cloud, everything lives inside a Resource Pool. This is your isolated sandbox, and it has to be created manually via the console:

- **How:** Navigate to **Provisioning** → **Catalog**.
- **Action:** Select **Create Project**. Fill in your Group (e.g., `MTNNG_CLOUD_AZ_1`) and give it a name.
- **Wait:** It takes about 15 minutes for the pool to complete and become available.

Once that is done, grab your API token from **User Settings** → **API Access**, and you are ready to go.

### Getting Started

```bash
pip install mtn-cloud
```

```python
from mtn_cloud import MTNCloud

cloud = MTNCloud(token="your-api-token")

# Check connection
user = cloud.whoami()
print(f"Connected as: {user.username}")
```

### List Your Instances

```python
for instance in cloud.instances.list():
    print(f"{instance.name}: {instance.status} ({instance.primary_ip})")
```

### Spin Up a Server

```python
from mtn_cloud import MTNCloud
from mtn_cloud.models import InstanceVolume

cloud = MTNCloud(token="your-api-token")

instance = cloud.instances.create(
    name="prod-web-01",
    cloud="MTNNG_CLOUD_AZ_1",
    type="MTN-CS10",                # CentOS Stream 10
    layout=327,                
    plan=6775,                      # G2S2: 2 cores, 2GB RAM
    resource_pool_id="your-pool-id", 
    availability_zone="Lagos-AZ-1-fd1",
    security_group="default",
    os_external_network_id="public-network-01",
    volumes=[InstanceVolume(name="root", size=20, storage_type=11)],
)

# Wait for the instance to be running
instance = cloud.instances.wait_until_running(instance.id, timeout=300)
print(f"Ready! IP: {instance.primary_ip}")
```

### Instance Actions

```python
# Stop, start, restart
cloud.instances.stop(instance.id)
cloud.instances.start(instance.id)
cloud.instances.restart(instance.id)

# Resize
cloud.instances.resize(instance.id, plan_id=6776)  # Upgrade to G2S4

# Delete
cloud.instances.delete(instance.id)
```

### Browse Instance Types

```python
# List all available instance types
for it in cloud.instance_types.list():
    print(f"{it.code}: {it.name}")

# Get by code
centos = cloud.instance_types.get_by_code("MTN-CS10")
print(f"Layout ID: {centos.default_layout_id}")

# Filter by category
os_types = cloud.instance_types.list_os()
db_types = cloud.instance_types.list_databases()
```

---

If we want local cloud infrastructure in Nigeria to mature, we need better community tooling. This is my contribution.

The project is on [GitHub](https://github.com/mahveotm/mtn-cloud-python). If you find a bug or want to add a feature, the PR door is open.


---

**Disclaimer:** This is an unofficial community project. Not affiliated with MTN Nigeria.

[Close out](https://youtu.be/o9zwXQC5iiY)

