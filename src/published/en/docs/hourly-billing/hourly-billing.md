---
image: /assets/images/docs/en/hourly-billing/og-image.png
title: Hourly billing
description: "How prepaid hourly VPS instances accrue charges, renew, suspend and get destroyed, and what hourly instances cannot do."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: hourly-billing
locale: en
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## What hourly billing is

Hourly instances are prepaid but metered: instead of choosing a fixed plan and cycle, you
configure processors, memory and storage and pay for the time the instance runs. The deploy
form shows an **Hourly Rate** and an approximate monthly value, plus a **Monthly Cap** in
the order summary.

Hourly billing is useful for short-lived workloads, testing and projects that are idle for
long periods and can be stopped.

## How charges accrue

- The rate is based on the resources you selected at deploy time.
- Charges are drawn from your Credit balance for the time the instance runs.
- Deleting an instance ends it; there is no dormant hourly instance left behind.
- The **Monthly Cap** in the order summary shows the ceiling for an hourly configuration.

Resources cannot be resized on an hourly instance after deployment. To change processors,
memory or storage, deploy a new instance with the desired configuration.

## Renewal and extending

The instance **Overview** tab shows **Next Renewal** with an **Extend Instance** action and
the **Auto-Renew** toggle.

- Keep **Auto-Renew** enabled if the instance must keep running; the panel then charges the
  next period from your balance.
- Use **Extend Instance** to pay for additional time. On an hourly instance it becomes
  available once the instance is suspended; it buys **one more hour** at the current hourly
  rate and brings the instance back.
- If the balance cannot cover a renewal and auto-renew is on, the instance is suspended.

## Zero balance, suspension and deletion

- When the balance cannot cover the next hour, the instance expires and is suspended. A
  warning email is sent about **30 minutes** before an hourly expiry, unless the instance will
  auto-renew from the balance.
- A suspended instance does not serve traffic. Top up and restore it, or destroy it if you
  no longer need it.
- If it is not renewed, the instance is **permanently deleted with its data after 7 days**
  from expiry.
- **Destroy Instance** is in **Danger Zone** and requires typing the instance name. It is
  permanent.

Destroying an hourly instance is the normal way to stop paying for it. Take a backup or
export your data first: hourly instances cannot use the backup add-on, so the data is gone
with the instance.

## Limits of hourly instances

| Feature | Hourly |
|---|---|
| Add-ons (backups, extra IPs, private network) | Not available |
| Private networking | Not available |
| Automatic Backups | Not available |
| Promo codes | Not available |
| Resizing resources | Not possible after deploy |
| Self-service destroy | Available, with typed confirmation |

Deploy a monthly instance when you need private networking, backups or add-ons. Monthly plans
are paid per cycle and support discounts; hourly plans are metered per hour.

## Switching between Monthly and Hourly

On a **monthly** instance the **Overview** tab has a **Billing Scheme** action. It changes the
prepaid billing cycle (longer periods at a discount), is free, and takes effect at the next
renewal. Billing Scheme is not available on hourly instances; to change billing model, contact
support.
