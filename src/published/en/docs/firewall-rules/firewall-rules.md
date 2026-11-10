---
image: /assets/images/docs/en/firewall-rules/og-image.png
title: Firewall rules
description: "Control inbound, outbound and global firewall behaviour on an instance, with rate limits, GeoIP filters and the block analyzer."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: firewall-rules
locale: en
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Before you start

Know which ports your application needs. Everything else can stay closed. Lifting the port 25
mail block requires identity verification.

## Open the Firewall tab

Open the instance and select **Firewall**. The tab controls the instance firewall through the
firewall service. A **Target IP** selector at the top chooses which public address the
rules apply to: an instance with extra IPv4 addresses keeps a separate ruleset per address.

Sub-tabs:

- **Overview**: onboarding guidance and the two-layer explanation.
- **Inbound Rules**: what the instance accepts.
- **Outbound Control**: what the instance may send.
- **Blocked IPs**: analyzer and security audit.
- **Global Inbound**: default policy, GeoIP, ASN, Threat Shield and packet rate limiting.

## Firewall service unavailable

If the firewall service cannot be reached, the tab shows **VoxiShield Connection Failure**.
Saved rules stay active but are not displayed or editable until the service is back. This is
temporary and does not mean your rules were lost.

Wait and reload. If the state persists, open a support ticket with the instance name and
the time you first saw it. Do not reinstall the OS; the state is temporary.

## Inbound Rules

**Inbound** traffic comes to your server; **outbound** traffic leaves it. Rules are
evaluated in the order shown. Each row has an enable/disable toggle, edit and delete actions,
and shows live hit information.

To add a rule:

1. Select **Add Rule**.
2. Enter a **Rule Name** and an optional **Description**.
3. Build the **Match Expression**: see below.
4. Choose the action: **Allow** or **Drop**.
5. Save. The panel confirms the rule was pushed to VoxiShield.

### Match expression

A rule is one or more conditions joined by **IF / AND / OR**. Available fields are source IP,
protocol, TCP/UDP port, TCP flags and packet size. Deep packet inspection is not available.
You can add up to **10 conditions** per rule.

Start with the specific traffic you need (`protocol` + `port` + `source`) and allow it,
then make the default policy deny everything else. Rules that allow "any source" on
sensitive ports are the usual cause of abuse reports.

### Rate limiting

The **Rate Limiting Regulations** section adds per-port limits:

- **Add Limit** creates a rule for target ports.
- Set the threshold and the ban duration.
- The list shows how many addresses are currently banned by each limit.

Rate limits protect against brute force and request floods. Set thresholds above normal
bursts: a limit that is too low bans legitimate users.

Every field, action and default is described in
[Rule reference](/docs/security/firewall-rules/rule-reference/).

## Outbound Control

Outbound rules govern traffic leaving the instance:

- **SMTP Mail Block (Port 25)**: port 25 is blocked by default to prevent spam. Lifting
  the block requires identity verification; the panel reports that unblocking needs **KYC
  identity verification**. See [Verification (KYC)](/docs/account/verification/).
- **Restrict All Outgoing**: blocks all outbound traffic.
- **Outbound Custom Rules**: after restricting all outgoing traffic, **Add Rule** lets you
  permit specific destinations and ports.

If your application cannot send mail, check port 25 first. Relays on submission ports
(587/465) are unaffected by this block.

## Blocked IPs

The **Blocked IPs** sub-tab has two tools:

- **Firewall Block Analyzer**: enter an IPv4 address and select **Analyze IP State** to see why it
  is blocked and by which mechanism.
- **Security Policy Audit**: for one IP, breaks down which of the four filter layers (rate
  limiter, GeoIP, ASN, Threat Shield) blocked or permitted it.

Use the analyzer before contacting support about a blocked customer or partner.

## Global Inbound

Global settings apply to the whole address:

- **Default Packet Policy**: what happens to traffic that matches no rule. Use deny for
  a hardened posture.
- **GeoIP Country Filter**: allow or block by country.
- **ASN Network Filter**: allow or block visitors by the network that owns their address
  (their internet provider or hosting company).
- **Threat Shield**: reputation-based filtering for known malicious sources.
- **Packet Rate Limiting**: a blanket packet-rate ceiling for the address.

Country and ASN filters are powerful and blunt: blocking a country blocks legitimate users
and crawlers from it. Enable them only with a clear reason and review the Blocked IPs list
afterwards.
