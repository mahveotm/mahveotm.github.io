---
layout: post
title: Compute pricing comparism.
subtitle: How much is what?

tags: [software, cloud, mtn cloud]
---

## 📝 Preamble & Assumptions

To compare the four providers effectively, we are making the following consistent assumptions:

  * **Pricing Model:** Pay-As-You-Go (On-Demand). No long-term contracts or commitment savings.
  * **Timeframe:** Monthly costs calculated using **730 hours** of runtime.
  * **Tax/Currency:** AWS, Azure, and GCP costs include a **7.5% sales tax** and are converted at **$1 USD = $\text{N}1500$ NGN**. MTN Cloud prices are the provided Naira rates.
  * **Location:** AWS, Azure, and GCP prices are based on their popular US East regions. MTN Cloud is priced in Naira, and independent of the availaility zone.
  * **Core Equivalence:** For comparison purposes, we are making the decision to approximate **1 Core (MTN)** to **1 vCPU (AWS/Azure/GCP)**.

## 📊 4-Way Cloud Compute Cost Comparison (Monthly NGN)
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


## Some interesting data points. 

1.  **Low-End Price Disparity:** For the smallest, Entry-level instances (1-2 vCPU), **MTN Cloud is significantly more expensive** than the international hyperscalers. The MTN G1S1 (1/1) is nearly **6 times** the cost of the GCP `e2-micro` (2/1). This suggests the overhead of smaller, highly utilized local infrastructure is much higher than the global US-based clouds.

2.  **Mid-Range Competitiveness:** As the instances scale up to the **General Purpose (4 vCPU, 16 GB)** tier, MTN's price gap narrows considerably. The MTN G4S16 at $\text{N}270,389$ is much closer to the AWS/GCP prices ($\text{N}225,750 - \text{N}228,975$).

3.  **High-End Local Premium:** In the largest **Enterprise/Dedicated** tiers (96 Cores), **MTN Cloud becomes the most expensive option**. The MTN Ge96L384 is priced at $\text{N}6,431,371$, which is about $\text{N}1$ million more per month than the equivalent instance on AWS, and about $\text{N}442,000$ more than the equivalent instance on Azure.

4.  **Hyperscaler Consistency:** AWS and GCP maintain their tight competition, generally providing the lowest cost for General Purpose instances, while Azure maintains a small premium across most tiers.

**This comparison clearly shows a trade-off:** while the hyperscalers are vastly cheaper for small tasks (even after tax and exchange rate conversion), a local provider like MTN offers the benefit of **low-latency access** within Nigeria and eliminates the reliance on volatile USD-to-NGN exchange rates and foreign payment methods.

Next article I'll talk about data transfer costs(Egress).
