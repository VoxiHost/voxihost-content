---
image: /assets/images/docs/en/voxishield/og-image.png
title: VoxiShield
description: "How VoxiShield's two-layer DDoS protection works, how it relates to your firewall rules, and what to do during an attack."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: voxishield
locale: en
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## What VoxiShield protects

VoxiShield is the network-level protection in front of your instances. It filters malicious
traffic before it reaches your server, so volumetric and protocol attacks do not consume the
instance's bandwidth or CPU.

It is always on. You do not enable it per instance, and nothing needs to be installed inside
your server.

## How the two layers work

VoxiShield is described in the panel as two layers:

- **Layer 1: PletX Edge.** Traffic is inspected and cleaned at the network edge, before
  it reaches your instance. This stops large floods that would otherwise saturate the link.
- **Layer 2: dashboard firewall.** The firewall you control from the instance's **Firewall**
  tab: inbound rules, outbound control, GeoIP/ASN filters and rate limits.

Layer 1 protects the network. Layer 2 decides which traffic the instance accepts. They
complement each other: edge scrubbing cannot know that only three ports should be open,
and port rules cannot absorb a very large flood.

## Protection on every plan

VoxiShield is included with every VPS plan: there is no separate DDoS protection tier to buy,
and Budget and Premium instances get the same two layers and the same firewall controls.
Traffic capacity and any optional upgrades are listed on the VoxiShield product page. If you
expect a very large attack, confirm the volume with support before deploying.

## VoxiShield and the instance firewall

VoxiShield does not replace firewall rules. Open ports are still your decision:

- Inbound rules decide which sources and ports reach the instance.
- Global inbound policy sets the default for everything not explicitly allowed.
- Outbound control limits what the instance can send: including the SMTP port 25 block
  that requires KYC verification to lift.

Start from a default-deny posture and allow only the ports you actually serve. See
[Firewall rules](/docs/security/firewall-rules/) and
[Rule reference](/docs/security/firewall-rules/rule-reference/).

## During an attack

1. Confirm the symptom: latency, packet loss or unreachability that affects the instance
   but not the panel.
2. Note the start time, the target IP and the traffic pattern if you can see it (for example
   from your own monitoring).
3. Open a support ticket with those details and the instance name.
4. Do not disable firewall rules in panic: if legitimate traffic is being dropped, the
   Blocked IPs view and the Firewall Block Analyzer explain why.

## False positives

If legitimate users are blocked:

- Check **Blocked IPs** in the firewall and use the **Firewall Block Analyzer** on the
  affected address.
- Review GeoIP and ASN filters: a country or network filter can be too broad.
- Review rate limits; a low threshold can ban normal bursts.
- If the block originates at the edge rather than from your rules, open a ticket with the
  source address and the time window.
