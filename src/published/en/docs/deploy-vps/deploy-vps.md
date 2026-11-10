---
image: /assets/images/docs/en/deploy-vps/og-image.png
title: Deploying a VPS
description: "Every VPS deploy option explained - region and zone, tier, billing cycle, operating system, add-ons and errors."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: deploy-vps
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Before you deploy

You need a Credit balance covering the **Total Due**, a password manager for the root
password, and an optional SSH client; the browser console works without one.

The deploy form charges the first period from your Credit balance immediately. Make
sure the balance covers the **Total Due** shown in the Order Summary; if it does not, the
form offers **Top up balance** instead of deploying.

Three things can stop a deployment before capacity is even checked:

- An insufficient balance.
- An account or resource limit reached (contact support if you need more instances).
- An invalid operating system, hostname or password.

**Monthly** instances are paid per billing cycle and can use add-ons, promos and
private networking. **Hourly** instances are prepaid as they run, are configured with
resource steppers instead of plan cards, and do not support add-ons. The billing models
are compared in [Hourly billing](/docs/billing/hourly/).

## Region and Zone

Pick a **Region** first, then a **Zone** inside it. A zone is where the instance will
physically run; the panel also uses it for capacity.

- Zones with no capacity are greyed out with an explanation.
- If the selected zone runs out of room for the chosen tier, the form says there is no
  capacity left and offers a support ticket.
- Regions and zones are added over time. The form is the authoritative list: this page
  intentionally does not freeze names that change.

## Choose a tier

Both tiers run on the same AMD Ryzen 9 7950X3D hardware and the same NVMe storage. The
difference is how much CPU time, memory and disk I/O the platform guarantees to your instance.
**vCPU** is a virtual processor, **IOPS** is disk operations per second, and **NVMe** is the
storage type.

| | **Budget** | **Premium** |
|---|---|---|
| **CPU time** | Capped at 50% of the allocated vCPU time, standard scheduling priority | Uncapped CPU time, high-priority scheduling |
| **Memory** | 25% guaranteed, burst to 100% | 95% guaranteed, burst to 100% |
| **Network** | 100 Mbps per instance | 1 Gbps per instance |
| **Disk I/O** | Per-instance IOPS and throughput caps | No per-instance caps |

Each instance has its own network rate limit. Premium reserves more CPU time and memory
headroom for your workload.

The tier is fixed at deployment. There is no in-place upgrade or downgrade, so choose it for
the workload's expected lifetime; moving tiers means deploying a new instance.

The tier also sets which plans and zones are available.

## Plan and billing cycle

For a **Monthly** instance, the plan cards show the included RAM, vCPU, NVMe storage and
network, and mark sold-out plans as greyed out. A **Popular** badge highlights the plan
most customers choose.

The **Billing Cycle** step then offers longer prepaid cycles with a **Save X%** badge,
or **No discount** for the shortest cycle.

For an **Hourly** instance, replace the plan cards with the **Processors**, **Memory**
and **Storage** steppers. The panel shows the **Hourly Rate**, an approximate monthly
cost, and, when your configuration matches a standard plan, a prompt to switch to the
cheaper **Monthly Plan**.

The panel is authoritative for current prices, plan names and discounts.

## Operating system

1. Select an OS family, then a **Version**.
2. If a template carries a licence surcharge, it appears as an extra charge in the Order
   Summary. Windows templates are **180-day evaluations**: extending the licence is done
   with Microsoft, not through VoxiHost.
3. If a template is missing, use the ticket link to suggest it.

The panel is unmanaged: you own updates, users and service configuration inside the OS.
See [Operating systems](/docs/platform/operating-systems/) for reinstalling and what
"unmanaged" means.

## Hostname and root password

- **Hostname**: at least 3 characters, letters, numbers and hyphens. It becomes the
  instance name in the panel and the default system hostname. Use the random generator
  if you do not have a naming scheme.
- **Root Password**: generate one or type your own. The form shows password strength
  and can reveal the value. Copy it before deploying; the same credentials are stored in
  the instance's **Credentials** card afterwards.

Use a password manager. A weak root password is the most common way an unmanaged server
gets compromised.

## Add-ons

Add-ons are offered for **Monthly** instances only.

| Add-on | What you get | Notes |
|---|---|---|
| **Private Network** | A private address on the zone's internal network | Free; choose the address and the **Speed** tier |
| **Extra IPv4 Address** | Additional public IPv4 addresses | 1-5 per deployment, charged |
| **IPv6 Addresses** | Additional IPv6 addresses | 1-5 per deployment; the first is free, the rest are charged |
| **Automatic Backups** | Weekly automatic snapshots | Charged; available on the instance's Backups tab afterwards |

Addresses and private networking can be changed after deployment from the instance's
**Network** tab, but additional addresses beyond the deploy limits are handled by support.
See [IP addresses](/docs/platform/networking/ip-addressing/) and
[Networking](/docs/platform/networking/).

## Order summary, promo code and legal waiver

The **Order Summary** on the right lists the type, region, zone, plan or resources, OS,
add-ons, the recurring or hourly price, discounts and the final **Total Due**.

- **Promo Code**: enter it and select **Apply**. Invalid or expired codes are rejected
  in place.
- **Insufficient balance**: the summary warns and links to **Top up balance**.
- **Legal waiver**: you must accept the immediate-performance and withdrawal-waiver
  checkbox before deploying.
- **Deploy Now**: submits the order. The button changes to **Deploying…** while the
  request runs.

## Deploy Now and what happens next

Successful deployments return you to **VPS Instances**. The new instance starts as
`queue`, moves to `installing`, and finally to `running`; the list refreshes automatically.
You can open the instance immediately: the Overview tab shows resources as soon as resource
data becomes available.

If the instance stays in `queue` or ends in `error`, open a support ticket with the
instance name, zone and the status you see.

## Deploy errors

| Message or state | Meaning | What to do |
|---|---|---|
| Insufficient balance | The total due exceeds your Credits | Add Credits, then retry |
| Duplicate hostname | Another instance in your account already uses that hostname | Choose a unique hostname |
| Active-instance limit | Your account reached its instance limit (10 instances by default) | Destroy unused hourly instances, let unused monthly instances expire, or contact support for a higher limit |
| No capacity | The chosen tier cannot be placed in the selected zone | Choose another zone or region |
| Invalid hostname / password | The value does not meet the form rules | Fix the hostname; the form shows password strength and rejects anything below the top score |
| Invalid operating system | The template is unavailable | Pick another version or suggest it via ticket |
