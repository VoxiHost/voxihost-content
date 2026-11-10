---
image: /assets/images/docs/en/client-panel/og-image.png
title: Managing your VPS
description: "Find your instances, read their statuses, use power controls and work with the Overview, Settings and Danger Zone tabs."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: client-panel
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Dashboard overview

The Overview page is the panel home. It answers three questions at a glance:

- **Monthly cost**: the monthly-equivalent cost of all your services, including hourly
  instances projected to a full month.
- **Running**: how many instances are running out of your total.
- **Next renewal**: the next date and amount due, or `Nothing due`, `Expired` or
  `auto-renew off` when a renewal is not scheduled.

The KPIs and the services list belong to the **active workspace**, whose name sits in the top
bar, and at the top of the sidebar on wide screens. A personal account starts with one Personal
workspace; a company or a school can add its own, each with a separate wallet and its own
members. The Recommendations card concerns your account rather than the workspace. See
[Workspaces](/docs/account/workspaces/) for switching, inviting people and what each role may
do.

Below the KPIs, the **Services** card lists your **VPS Instances**. Databases, Kubernetes,
Docker, Object Storage, Load Balancers and Domains are marked **Coming soon**. The
**Recommendations** card suggests next steps such as adding a sign-in provider, completing
your profile, enabling 2FA, and claiming welcome Credits (granted after completing your profile
and linking a sign-in provider, or after identity verification, subject to eligibility checks).

If a legal document version is waiting for your acceptance, the panel opens the confirmation
page instead of this one until you accept it. See
[Legal documents & acceptance](/docs/account/legal/).

## Your VPS list

Open **VPS Instances** in the sidebar. Two tabs separate the billing models:

- **Recurring Plans**: monthly instances.
- **Hourly Billing**: hourly instances.

Each card shows the status, the instance name, CPU/RAM/disk utilisation, public IPv4 (or
`Pending IP...` while it is being assigned) and the plan specifications. Select a card or
its name to open the instance. The list refreshes automatically, so status changes appear
without reloading.

The empty tile **Deploy a VPS Instance** opens the deploy form described in
[Deploying a VPS](/docs/platform/deploy-vps/).

## Instance status reference

| Status | Meaning |
|---|---|
| `queue` | The deploy request is accepted and waiting for a host |
| `installing` | The operating system is being installed |
| `running` | The instance is up and reachable |
| `stopped` | The instance is powered off |
| `reinstalling` | The OS is being reinstalled; all data is replaced |
| `restoring` | A backup is being restored; the instance is stopped and data is overwritten |
| `error` | The last operation failed; open the instance or contact support |
| `suspended` | Billing or policy action; contact support if unexpected |
| `deleted` | The instance is being removed |

Long-lived `queue`, `installing` or `error` states usually mean a capacity or host problem.
For `error`, open the instance and note the status text and zone. For `suspended`, check
[prepaid rules and suspension](/docs/billing/payments/) first. If the top-up is already
paid, open a ticket with the instance name and the time it stopped.

## Power controls

Start, restart and stop are available on the instance header and on the list cards.

- **Start** powers on a stopped instance.
- **Restart** reboots it. A confirmation is required because the instance loses uptime.
- **Stop** powers it off. A confirmation is required; running services stop immediately.

Power actions are unavailable while an operation such as `installing` or `restoring` is
in progress. Stopping an instance does not stop billing for monthly plans; hourly billing
follows the rules in [Hourly billing](/docs/billing/hourly/).

## Extend, auto-renew or change the billing cycle

The Overview tab is the instance home:

- **Resource Usage**: live CPU, RAM and disk rings.
- **Instance Details**: location, zone, specifications, network and creation date.
- **Billing & Subscription**: the current **Billing Scheme** (select it to change the
  billing cycle; free and applied at the next renewal), **Next Renewal** with an
  **Extend Instance** action, the renewal cost or hourly rate, and the **Auto-Renew** toggle.

Other tabs are covered separately: [Console, SSH & RDP](/docs/platform/console-access/),
[Metrics](/docs/platform/metrics/), [Networking](/docs/platform/networking/),
[Firewall rules](/docs/security/firewall-rules/), and
[Backups & snapshots](/docs/platform/client-panel/snapshots/).

## Settings

The **Settings** tab contains one setting: **Instance Name**, which also updates the
hostname shown in the panel. Select **Save** to apply it. Operating system changes are in
the Danger Zone, not here.

## Danger Zone

The Danger Zone contains irreversible actions:

- **Reinstall Operating System**: choose a new OS family and version and set a new root
  password. All data on the instance is erased. See
  [Operating systems](/docs/platform/operating-systems/).
- **Destroy Instance**: available for hourly instances. You must type the instance name
  to confirm. Destroys are permanent; take a backup first if you might need the data.

For monthly instances there is no self-service destroy. Turn off **Auto-Renew** on the
Overview tab and let the instance expire; an expired instance is suspended and permanently
deleted with its data after the 7-day grace period.
