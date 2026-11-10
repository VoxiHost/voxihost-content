---
image: /assets/images/docs/en/rule-reference/og-image.png
title: Firewall rule reference
description: "Every firewall field explained: match conditions, actions, rate limits, global policies, GeoIP/ASN filters and analyzer results."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: rule-reference
locale: en
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Rule anatomy

This page is a reference for firewall administrators. If you only want to open a port, start
with [Firewall rules](/docs/security/firewall-rules/).

Every inbound rule has the same parts:

| Part | Required | Purpose |
|---|---|---|
| **Rule Name** | Yes | Human-readable label in the rules table |
| **Description** | No | Why the rule exists; useful months later |
| **Match Expression** | Yes | Conditions that select traffic |
| **Action** | Yes | **Allow** or **Drop** |

Rules are evaluated in the order shown in the table. The first matching rule decides the
outcome; traffic that matches nothing falls to the global default packet policy. You can
enable or disable a rule without deleting it, which is safer than editing it during an
incident.

## Match conditions

A match expression joins up to **10 conditions** with **IF / AND / OR**.

| Field | What it matches | Typical use |
|---|---|---|
| **Source IP** | The remote address or network | Allow only your office or VPN range |
| **Protocol** | Transport protocol, such as TCP or UDP | Allow TCP for a web server, UDP for a game |
| **TCP/UDP Port** | A port or port range | Open 443, 22, or a game's port range |
| **TCP Flags** | TCP flag combinations | Advanced filtering (for example, SYN handling) |
| **Packet Size** | Packet length in bytes | Drop abnormally large or small packets |

Guidance:

- Prefer protocol + port + source. Broad "any source, any port" allows defeat the point.
- Combine conditions with **AND** to narrow; **OR** widens and is easy to get wrong.
- Deep packet inspection is not available: rules match addresses, protocols, ports, TCP flags
  and packet size, not payload contents.
- Keep rules small and named; ten conditions in one rule are hard to review.

The rule builder validates values as you enter them. If a value is rejected, the form
states the accepted format for that field.

## Inbound actions

| Action | Effect |
|---|---|
| **Allow** | Accept the matching traffic |
| **Drop** | Silently discard it |

Prefer **Drop** over an explicit deny banner: the sender learns nothing, which is the
correct default for exposed services.

## Rate limiting fields

Rate limits are defined per target port set:

| Field | Meaning |
|---|---|
| **Target ports** | Ports the limit applies to |
| **Threshold** | Requests or packets per interval that trigger the limit |
| **Ban duration** | How long an offending address stays banned |
| **Banned now** | Read-only count of addresses currently banned by the limit |

Set the threshold above normal bursts, including legitimate retries and health checks. A
ban that catches real users shows up as blocked legitimate traffic in the analyzer.

## Outbound control

| Control | Effect |
|---|---|
| **SMTP Mail Block (Port 25)** | Blocks outbound port 25 until identity verification is approved |
| **Restrict All Outgoing** | Blocks outbound traffic; custom rules then re-allow specific traffic |
| **Outbound Custom Rules** | Per-destination allow rules, available when all outgoing is restricted |

Outbound exceptions use a simpler form: choose the protocol (TCP, UDP, ICMP or all), the
target port and an optional destination. They are not built with the inbound condition editor.

## Global inbound fields

| Setting | Meaning | Safe starting point |
|---|---|---|
| **Default Packet Policy** | Outcome for traffic that matches no rule | **Default Drop** |
| **GeoIP Country Filter** | Allow or block whole countries | Off until you have a reason |
| **ASN Network Filter** | Allow or block networks by ASN | Off; use for known abusive hosting ranges |
| **Threat Shield** | Reputation-based blocking of known bad sources | On |
| **Packet Rate Limiting** | Blanket packet-per-second ceiling for the address | Above your normal peak, if you need it |

Enabling a country or ASN block affects every visitor from that network, including your
own monitoring or partners. Review the Blocked IPs list after any change.

## Precedence and defaults

1. Inbound rules are checked in table order; the first match wins.
2. If no rule matches, the **Default Packet Policy** decides.
3. Rate limits are evaluated independently and can ban an address even when a rule allows it.
4. Outbound control is separate from inbound rules.
5. GeoIP, ASN, Threat Shield and packet rate limiting are applied by the platform around
   your rules, so a packet can be dropped before reaching an allow rule.

## Firewall Block Analyzer

Enter an IPv4 address and select **Analyze IP State**. The analyzer reports which filter layer
affected the address:

| Output | Meaning |
|---|---|
| Rate limit name | A rate limiter banned the address |
| GeoIP | A country filter affected it |
| ASN | A network filter affected it |
| Threat Shield | Reputation filtering affected it |

Use it before opening a ticket. If none of these explains the block, open a ticket with the
address and the time you tested.

## Security Policy Audit

The audit is a per-IP breakdown: for one address it shows which of the four filter layers
(rate limiter, GeoIP, ASN, Threat Shield) blocked or permitted it. Use it to confirm why a
specific visitor is affected, not as a configuration scan.
