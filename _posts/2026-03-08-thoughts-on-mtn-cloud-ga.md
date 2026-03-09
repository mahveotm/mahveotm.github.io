---
layout: post
title: Thoughts on MTN Cloud (GA); Sovereignty, Pricing, and Startups
subtitle: General Availability is live. Here is the business reality check.
tags: [software, cloud, mtn cloud]
---

It is finally here. The **General Availability (GA)** version of MTN Cloud is live, and I spent the weekend playing around. As always, I have some thoughts. You can check some of my previous coverage on MTN Cloud, like my [Thoughts on MTN Cloud](https://blog.mahveo.codes/2025-10-22-thoughts-on-mtn-cloud/) or the [compute comparison](https://blog.mahveo.codes/2025-12-12-compute-comparison/).

The first major improvement: you can now sign up directly at [cloud.mtn.ng](https://cloud.mtn.ng/) without contacting sales or waiting for someone to reach out. This is a significant step forward from the early access days. That said, onboarding comes with a ₦120,000 commitment fee before your account gets activated, which is a non-trivial barrier for developers who just want to experiment. The registration process also asks for a myriad of information that feels unnecessary for a cloud platform signup.

On the technical side, things are promising but still rough around the edges. There is [decent documentation](https://cloud.mtn.ng/documentation/) now, which is good to see. I also ran into quirks like security groups mysteriously detaching from resource pools, floating IPs refusing to provision, and routers spontaneously deleting themselves after creation. These are early days though, and some instability is expected. The important part is that it works, and you can actually build things on it.

Also, to MTN Cloud's credit, a lot of the asks from my earlier post have started landing: there is now programmatic access through Morpheus CLI, infrastructure access through Morpheus Terraform, better documentation, and recurring technical webinars for knowledge sharing.

One request I want to repeat clearly is hardware token support for 2FA. The platform logs you out after roughly 15 minutes of inactivity, which is understandable from a security perspective, but for developers who already use hardware keys, repeatedly reaching for a phone OTP is unnecessary friction. This is not a criticism of the security posture, it is a usability request.

But stepping back from the technical specifics, let us talk about the business reality of local cloud in Nigeria. Here is the truth: people only care about data sovereignty because regulators make them. Without regulatory compliance mandating local data residency, the conversation around local cloud providers becomes significantly different. So if compliance is the primary hook, how does MTN Cloud stack up on the business side?

### The Double-Edged Sword of Naira Pricing

Pricing in Naira is, on paper, a fantastic idea. It shields local businesses from the daily anxiety of FX fluctuations. But let us be brutally honest: a significant chunk of MTN's underlying infrastructure costs are in USD. Also, MTN Cloud still does not have a publicly accessible pricing page, which is frankly irresponsible at this stage. Local competitors like [Nobus](https://nobus.io/pricing) and [Layer3](https://layer3.cloud/pricing) already publish detailed pricing options openly.

While minor currency swings might not have an immediate impact, a massive devaluation event, like the 15% to 30% dips we typically see around election cycles, means somebody has to bite the bullet on those costs. And to be fair, this is not entirely bad news in isolation, USD-paying customers in Nigeria will still feel exchange-rate swings too. The key point is that local companies are not fully immune either; when rates move hard enough, the pressure eventually shows up somewhere on the invoice. Knowing MTN as a telco, they are highly unlikely to absorb those losses for long. Eventually, those costs will trickle down to the consumer.

### The Overhanging AWS Threat

AWS is no longer a distant what-if. With an AWS Local Zone in Nigeria and edge presence in Lagos, the old latency argument keeps shrinking. If that gap closes enough for most workloads, MTN Cloud will need to compete on reliability, support, and speed of execution, not just local identity.

This is where reputation becomes hard to ignore. Speaking personally, it is still a mixed bag. On one hand, I remain genuinely grateful for the MTN Foundation Scholarship and the impact it had on my education.

On the other hand, their corporate reputation for handling technical outages leaves a lot to be desired. I am both an MTN Fibre X and 5G customer, and the less said about their outage response, the better. Should we realistically expect something different with a cloud product under the same umbrella?

That is the real pressure point. If global players are now physically closer and MTN still carries trust baggage on reliability, being the "Nigerian option" will not be enough on its own.

To be fair, most of my points from the original Thoughts on MTN Cloud are now being addressed, and that progress deserves applause. The question now is whether execution speed and reliability can keep up if competition tightens.

### The Verdict: Operate Like a Startup

For MTN Cloud to survive and thrive against both local competitors and global threats, they cannot operate with the bureaucratic bloat of a legacy telco. They need to treat this cloud division like a true startup. Maybe give it a different name, detach it from corporate red tape, be nimble, and allow them to break things. Several things.

Because when a real startup with serious funding enters this space, or when a global giant finally pivots hard into Lagos, MTN Cloud will need more than just regulatory sovereignty to stay relevant.

[Close out](https://youtu.be/bf_Nq70kzD8)
