---
image: /assets/images/docs/en/networking/og-image.png
title: Networking
description: "Public and private networking on a VPS: primary IPv4, private network enablement, speed changes and hourly limits."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: networking
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Public networking

Every instance receives a public IPv4 address, shown in the instance header and on the
**Network** tab. The tab summarises **Public addresses**, **Private network** status, and
**Reachable**, which counts the other instances on your private network that this instance
can reach.

- Copy an address straight from its tile.
- The primary address is marked with a star.
- Additional addresses have a **Make primary** action.

Changing the primary address affects outbound traffic and anything that relies on the
source IP, including DNS records and remote allowlists. Update those records after the
switch, and check the instance's own network configuration.

## Getting more public addresses

Additional IPv4 and IPv6 addresses are ordered at deploy time: up to five of each, with
charges shown in the **Order Summary**. After deployment the Network tab points to support:
**Need more addresses? Contact support to add IPv4 or IPv6.**

See [IP addresses](/docs/platform/networking/ip-addressing/) for limits and charges.

## Private networking

A private network gives the instance an address on the zone's internal network, without
exposing it publicly. The Private Network add-on itself is free; faster **Speed** tiers are
charged and shown before you confirm.

If private networking is off:

1. Open the instance and select **Network**.
2. Select **Enable private network**.
3. Choose the private address and **Speed**, then confirm.

If it is on, the tab shows the private address with a copy control, the other members of
the network, and **Change address**, **Change speed** and **Disable private network**. Select
the action, confirm the change, and reboot if the panel shows a reboot notice. Private
networking is intended for traffic between your own instances in the same zone.

## Hourly instances and private networking

Hourly instances cannot use private networking. If you need it, deploy a monthly instance
or contact support about your options. The deploy form hides the Private Network add-on
for hourly billing.

## Locations and network tests

Instances run in a chosen region and zone; the zone is where the hardware sits and where
private networks are shared. To test latency from your location, use the Looking Glass tools
on the website. VoxiHost operates AS211011, its autonomous system number, the network
identity used when troubleshooting routing with your ISP or a remote service.

## When networking looks wrong

- **No public IP**: a newly deployed instance can show `Pending IP...` until assignment
  completes. Wait for `running`, then check again.
- **Instance unreachable**: verify the firewall allows the port, then use the console.
- **Private network not visible**: confirm both instances are in the same zone and that
  private networking is enabled on both.
- **Routing oddities**: include the source and destination addresses, timestamps and
  `traceroute` output in a support ticket.
