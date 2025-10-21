---
layout: post
title: Thoughts on MTN Cloud.
subtitle: After several weeks of using MTN Nigeria's MTN Cloud, here's what I think. 
cover-img: /assets/img/mtncloudconsole.png
share-img: /assets/img/mtncloudconsole.png
tags: [software, cloud]
---

Weeks ago, I was granted early access to [MTN Cloud](https://cloud.mtn.ng/), and I’ve had a fun time tinkering around it. 

MTN Cloud is MTN Nigeria's ambitious effort to provide a localized alternative to major players like _AWS_, _Azure_, _Oracle_, and _Google Cloud_. It’s also worth noting that Nigeria already has a few local players in this space, including _Layer3_, _Galaxy Backbone_, and _Nobus_.

MTN Cloud runs a [customized OpenStack environment](https://www.openstack.org) managed through the [Morpheus Cloud Management Console](https://morpheusdata.com). It offers a variety of operating system images, including CentOS, Debian 12/13, Ubuntu 22/24, and Windows Server 2019/2022.

MTN Cloud also provides several pricing plans, ranging from the **GLD2x**, the highest tier available at the moment, with **96 cores**, **384 GB RAM**, and **100 GB storage**, to the **GS3 (General Small)** with **2 cores**, **8 GB RAM**, and **10 GB storage**. Resource capacity scales with the plan number, for example, **GM4** provides more resources than **GM3**.

After working with the console for a couple of weeks, here are my thoughts on what MTN should focus on if it wants to directly compete with the major cloud providers.
### Hardware Token Support

Please consider supporting hardware-based 2FA. Security-conscious users often enable two-factor authentication wherever possible. SMS OTPs are unreliable, leaving only app-based or hardware authentication as viable options.
While app-based OTPs have become the standard, they can be slow. It taks roughly 30 seconds to grab your phone, unlock it, open your authenticator app, and enter the code. Adding YubiKey or FIDO2/WebAuthn support would make authentication faster and more secure.
Major providers like Google, AWS, Oracle, and Microsoft already support hardware tokens. Here’s a good reference for implementation:
[WebAuthn Starter Kit – Yubico Developer Guide](https://developers.yubico.com/Developer_Program/WebAuthn_Starter_Kit/Front-End_System_Design.html)

### Infrastructure Access

Developers generally prefer automation over manual console operations, one reason HashiCorp reached a $6.4 billion valuation. Infrastructure as Code (IaC) is now a core part of modern cloud practice. The uniformity and reproducibility it offers are unmatched.
MTN Cloud should support Terraform or similar tools for provisioning and management. Even if only the API specifications are exposed, the community will quickly build and open-source the necessary providers and modules.

### Programmatic Access

Programmatic access is essential for interacting with infrastructure at scale. AWS provides Boto3 for Python, and most clouds expose SDKs or REST APIs. Currently, the API access button on MTN Cloud doesn’t seem functional. Enabling and documenting this feature would be a major step toward developer adoption.

### Security and Transparency

MTN Cloud should move away from the “security through obscurity” approach prevalent in telecom industry. Developers value visibility and openness. We want to know how the system works, why certain design choices were made, and what’s next.
Technical write-ups like [*Building and Operating a Pretty Big Storage System*](https://www.allthingsdistributed.com/2023/07/building-and-operating-a-pretty-big-storage-system.html) and [*How Azure.com Operates on Azure*](https://azure.microsoft.com/en-us/blog/how-azurecom-operates-on-azure-part-2-technology-and-architecture/) build credibility and trust. Publishing similar deep dives would promote transparency and long-term engagement.

### Technical Blog and Knowledge Sharing

A technical blog is crucial for demonstrating platform maturity, but currently, there isn’t one. Additionally, requiring users to create an account and provide a home/office address and a phone number just to view pricing plans is unusual and discouraging. 
Pricing transparency is a standard expectation among cloud providers. 
We should be able to evaluate plans and costs before committing to registration.
The proposed blog should highlight architecture frameworks, integration guides, and best practices, for example, how to connect with MTN Mobile Money(a selling point for MTN Cloud) or automate provisioning via Morpheus. This helps developers gain confidence and reduces friction during adoption.

### Knowledge Validation

As the platform grows, companies will want to confirm that vendors and partners understand MTN Cloud thoroughly. While full certification programs may not be necessary yet, structured learning paths and labs, focused on using the customized Morpheus environment, APIs, and integration workflows would be invaluable.
This approach would improve developer's confidence, andd help organizations onboard faster.

### Pricing
The price of the **GLD2x** is the cover image for this article. TThe currency icon should atleast be the Naira. [Here's what they were probably thinking.](https://youtu.be/IpwSXWq1wwU)

Above all, great work by the MTN Cloud team. I’ve enjoyed using it so far.

[Close out](https://youtu.be/IpwSXWq1wwU)
