---
image: /assets/images/docs/en/ip-addressing/og-image.png
title: IP addresses
description: "IPv4 and IPv6 on VoxiHost: extra address limits, charges, making an address primary and when to contact support."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: ip-addressing
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## IPv4 and IPv6 on VoxiHost

Each instance receives a public IPv4 address. IPv6 addresses are available as an add-on and
are useful for services that should not share an IPv4 address. Private addresses are a
separate feature: see [Networking](/docs/platform/networking/).

Addresses are assigned to the instance, not to your account.

## Extra IPv4 addresses

- Ordered during deployment: **1-5** extra addresses per instance.
- Each extra address is charged and appears in the **Order Summary**.
- After deployment, additional addresses beyond the deploy limit require a support ticket.

## Extra IPv6 addresses

- Ordered during deployment: **1-5** addresses.
- The first IPv6 address is free; further addresses are charged.
- The same support route applies for more than the deploy limit.

## Before you add addresses

VoxiHost configures the primary IPv4 (and IPv6 when assigned) at deployment; extra addresses
must be configured in the OS, and changing the primary can interrupt connectivity. Keep the
console open while you edit network settings.

## Making an address primary

The **Network** tab marks the primary address with a star. On an additional address, select
**Make primary**.

The primary address is the default source address for outbound traffic. Change it with
care:

- Update DNS records pointing at the old address.
- Update allowlists on remote services.
- Re-check mail configuration if the instance sends email.

## Assigning addresses inside the OS

The panel assigns addresses to the instance; the operating system must still be
configured to use extra addresses. That usually means adding them to the network interface or
to the service configuration. If you are unsure, follow your distribution's networking
documentation and keep the console open in case a change cuts your connection.

## Charges and limits

| Item | Limit | Charged |
|---|---|---|
| Primary IPv4 | 1 per instance | Included |
| Extra IPv4 | 1-5 at deploy | Per address |
| IPv6 | 1-5 at deploy | First free, rest charged |
| Private network address | 1 per instance | Add-on free; speed tier charged |

Prices are shown before you confirm the order; the deploy form is authoritative.

## When to contact support

- You need more addresses than the deploy form allows.
- An address is missing or stuck on `Pending IP...` after the instance is running.
- You believe an address is blocklisted: include the address, the service that reports it
  and the exact message.
- You need an address moved between instances: this is handled by support, not by the panel.
