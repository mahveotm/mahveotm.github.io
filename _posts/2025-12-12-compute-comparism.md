---
layout: post
title: MTN Cloud compute pricing comparism(cloud this, cloud that).
subtitle: How much is what, where?

tags: [software, cloud, mtn cloud, aws, azure, gcp]
---

Hello, this is **Marv** here again, diving into something I think is important: **MTN Cloud** compute pricing.

MTN Cloud does not offer a publicly accessible pricing plan or a simple cost calculator - yet. As I [strongly opined in this post](https://blog.mahveo.codes/2025-10-22-thoughts-on-mtn-cloud/), users should be able to evaluate potential costs and plans *before* even committing to registration or provisioning an instance. 

To fill this crucial information gap, I have meticulously calculated and compared compute costs across MTN and the three other major global cloud providers: Amazon Web Services (AWS), Microsoft Azure, and Google Cloud Platform (GCP).

#### **The Comparison: Pay-As-You-Go in Naira**

I will be comparing the monthly prices of several common instance sizes, all presented as if you were paying the final amount in **Nigerian Naira (₦)**.

To ensure this is a fair, apples-to-apples comparison of the four providers, we will be grounding our analysis in the following consistent assumptions:

| Assumption | Detail | Rationale |
| :--- | :--- | :--- |
| **Pricing Model** | **Pay-As-You-Go (On-Demand)**. No long-term contracts (Reserved Instances, etc.) are applied. | Represents the most common starting point for new users and ensures a fair comparism across board. |
| **Timeframe** | **Monthly Cost (730 Hours)**. MTN’s quoted cost per instance is assumed to be the final monthly rate. | Standard industry metric for monthly uptime. |
| **Currency Conversion** | **$1 USD = ₦1500**. AWS, Azure, and GCP costs include a **7.5% VAT/Sales Tax** and are converted at this rate. | Reflects a real-world, current-market exchange rate and includes essential tax for a final comparison. |
| **Location Factor** | **AWS/Azure/GCP** prices are sourced from their popular **US East** regions. MTN’s price is currently consistent across its available zone(s). | Acknowledge the physical location that dictates global cloud pricing. |
| **Compute Equivalence** | **1 Core (MTN)** is approximated to **1 vCPU (AWS/Azure/GCP)**. | Necessary simplification to compare architectural differences in standard compute offerings. |

#### Cloud Compute Cost Comparison (Monthly NGN)

<div style="overflow-x:auto; max-width:100%; border:1px solid #ddd;">
<table>

  <tr>
    <th style="background:#F2F2F2;">Size</th>
    <th style="background:#F2F2F2;">vCPU</th>
    <th style="background:#F2F2F2;">RAM (GB)</th>
    <th style="background:#FFEB99;">
      <img src="https://upload.wikimedia.org/wikipedia/commons/2/2a/MTN_2022_logo.svg" width="40" />
      MTN Instance Type
    </th>
    <th style="background:#FFEB99;">MTN Cost (NGN)</th>
    <th style="background:#FFE5CC;">
      <img src="https://upload.wikimedia.org/wikipedia/commons/9/93/Amazon_Web_Services_Logo.svg" width="60" />
      AWS Instance Type
    </th>
    <th style="background:#FFE5CC;">AWS Cost (NGN)</th>
    <th style="background:#CFE6FF;">
      <img src="https://upload.wikimedia.org/wikipedia/commons/4/44/Microsoft_logo.svg" width="40" />
      Azure Instance Type
    </th>
    <th style="background:#CFE6FF;">Azure Cost (NGN)</th>
    <th style="background:#E3ECFF;">
      <img src="https://upload.wikimedia.org/wikipedia/commons/c/c1/Google_%22G%22_logo.svg" width="35" />
      GCP Instance Type
    </th>
    <th style="background:#E3ECFF;">GCP Cost (NGN)</th>
  </tr>

  <tr>
    <td>Entry (Burstable)</td><td>1</td><td>1</td>
    <td style="background:#FFF8CC;">G1S1</td><td style="background:#FFF8CC;">59,119</td>
    <td style="background:#FFF2E0;">t2.micro</td><td style="background:#FFF2E0;">13,658</td>
    <td style="background:#E9F3FF;">B1s</td><td style="background:#E9F3FF;">15,303</td>
    <td style="background:#F4F8FF;">e2-micro</td><td style="background:#F4F8FF;">9,868</td>
  </tr>

  <tr>
    <td>Entry (Burstable)</td><td>2</td><td>4</td>
    <td style="background:#FFF8CC;">G2S4</td><td style="background:#FFF8CC;">122,630</td>
    <td style="background:#FFF2E0;">t3.medium</td><td style="background:#FFF2E0;">48,972</td>
    <td style="background:#E9F3FF;">B2s</td><td style="background:#E9F3FF;">48,972</td>
    <td style="background:#F4F8FF;">e2-medium</td><td style="background:#F4F8FF;">39,442</td>
  </tr>

  <tr>
    <td>General Purpose</td><td>4</td><td>16</td>
    <td style="background:#FFF8CC;">G4S16</td><td style="background:#FFF8CC;">270,389</td>
    <td style="background:#FFF2E0;">m6i.xlarge</td><td style="background:#FFF2E0;">225,750</td>
    <td style="background:#E9F3FF;">D4s_v5</td><td style="background:#E9F3FF;">243,487</td>
    <td style="background:#F4F8FF;">n2-standard-4</td><td style="background:#F4F8FF;">228,975</td>
  </tr>

  <tr>
    <td>General Purpose</td><td>8</td><td>32</td>
    <td style="background:#FFF8CC;">G8S32</td><td style="background:#FFF8CC;">538,258</td>
    <td style="background:#FFF2E0;">m6i.2xlarge</td><td style="background:#FFF2E0;">451,500</td>
    <td style="background:#E9F3FF;">D8s_v5</td><td style="background:#E9F3FF;">486,975</td>
    <td style="background:#F4F8FF;">n2-standard-8</td><td style="background:#F4F8FF;">457,950</td>
  </tr>

  <tr>
    <td>General Purpose</td><td>16</td><td>64</td>
    <td style="background:#FFF8CC;">Ge16S64</td><td style="background:#FFF8CC;">1,073,995</td>
    <td style="background:#FFF2E0;">m6i.4xlarge</td><td style="background:#FFF2E0;">904,612</td>
    <td style="background:#E9F3FF;">D16s_v5</td><td style="background:#E9F3FF;">973,950</td>
    <td style="background:#F4F8FF;">n2-standard-16</td><td style="background:#F4F8FF;">914,288</td>
  </tr>

  <tr>
    <td>Enterprise Scale</td><td>32</td><td>128</td>
    <td style="background:#FFF8CC;">Ge32M128</td><td style="background:#FFF8CC;">2,145,470</td>
    <td style="background:#FFF2E0;">m6i.8xlarge</td><td style="background:#FFF2E0;">1,807,612</td>
    <td style="background:#E9F3FF;">D32s_v5</td><td style="background:#E9F3FF;">1,949,512</td>
    <td style="background:#F4F8FF;">n2-standard-32</td><td style="background:#F4F8FF;">1,828,575</td>
  </tr>

  <tr>
    <td>Enterprise Scale</td><td>64</td><td>256</td>
    <td style="background:#FFF8CC;">Ge64L256</td><td style="background:#FFF8CC;">4,288,421</td>
    <td style="background:#FFF2E0;">m6i.16xlarge</td><td style="background:#FFF2E0;">3,616,838</td>
    <td style="background:#E9F3FF;">D64s_v5</td><td style="background:#E9F3FF;">3,899,025</td>
    <td style="background:#F4F8FF;">n2-standard-64</td><td style="background:#F4F8FF;">3,658,762</td>
  </tr>

  <tr>
    <td>Maximum (Dedicated)</td><td>96</td><td>384</td>
    <td style="background:#FFF8CC;">Ge96L384</td><td style="background:#FFF8CC;">6,431,371</td>
    <td style="background:#FFF2E0;">m6i.24xlarge</td><td style="background:#FFF2E0;">5,424,450</td>
    <td style="background:#E9F3FF;">D96s_v5</td><td style="background:#E9F3FF;">5,988,825</td>
    <td style="background:#F4F8FF;">n2-standard-96</td><td style="background:#F4F8FF;">5,487,338</td>
  </tr>

</table>
</div>

#### Key Takeaways from the Compute Price Showdown

This final addition gives a personal, appreciative touch and sets up the next article perfectly.

Here is the completed, final version of your conclusion:

***

## **Key Takeaways from the Compute Price Showdown**

The comparison across all four cloud providers reveals some fascinating, and critical, data points regarding cloud infrastructure in Nigeria.

The initial shock comes at the **low-end**: For the smallest, entry-level instances (1-2 vCPU), MTN Cloud is *s**ignificantly* more expensive than the international hyperscalers. To put a number on it, the MTN G1S1 (1 core, 1 GB) is nearly **six times** the cost of the GCP `e2-micro` (2 vCPU, 1 GB). I'm not an economist, but this might suggests the overhead of smaller, highly utilized local infrastructure is simply much higher than what the massive global US-based clouds can absorb.

However, as we scale up, the picture changes. In the **mid-range** General Purpose tier (4 vCPU, 16 GB), MTN’s price gap narrows considerably. The MTN G4S16 is priced at ₦270,389, putting it much closer to the tight price range of AWS and GCP (₦225,750 – ₦228,975). Interestingly, the tight competition between **AWS and GCP** holds true across all sizes, generally providing the lowest costs for General Purpose instances, with Azure maintaining a slight premium across most tiers.

The trend culminates in the **high-end Enterprise/Dedicated** tiers (96 Cores), where **MTN Cloud becomes the most expensive option**. The MTN Ge96L384, at ₦6,431,371, is about ₦1 million more per month than the equivalent instance on AWS, and approximately ₦442,000 more than Azure.

**The trade-off is seems clear:** While the hyperscalers are vastly cheaper for small tasks—even after accounting for VAT and the volatile exchange rate conversion—a local provider like MTN offers the undeniable benefits of **low-latency access** within Nigeria. Crucially, MTN eliminates the reliance on volatile USD-to-NGN exchange rates and foreign payment methods, offering billing predictability that others simply cannot match.

It is worth noting that **MTN has generously allowed me to play across all classes of compute for free** to conduct this research, which is an extremely kind gesture that I sincerely appreciate.

***

*Prices for AWS, Azure, and GCP were meticulously sourced and calculated using their official tools: the [AWS EC2 On-Demand Pricing page](https://aws.amazon.com/ec2/pricing/on-demand/), the [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/), and the [Google Cloud Pricing Calculator](https://cloud.google.com/products/calculator).*

In the next article, we will pivot away from raw compute cost and look at the areas where MTN might truly have the edge: **data transfer costs (Egress)**, and a head-to-head comparison of **latency** for a simple web application hosted on MTN Cloud versus the AWS US-East-1 region.

[CLose out](https://youtu.be/xIk0_uFV-rU)
