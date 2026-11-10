---
image: /assets/images/docs/en/operating-systems/og-image.png
title: Operating systems
description: "Available OS templates, paid licences, reinstalling an instance and what running an unmanaged VPS actually means."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: operating-systems
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Available templates

The deploy form lists operating systems by family and version. The active template list is
global and available in every zone.

The panel is the authoritative list: templates and versions are added and retired over
time, so this page deliberately does not freeze a version list. If a system or version you
need is missing, use the ticket link in the deploy form to suggest it.

## Windows templates and licences

Windows templates are provided with a **180-day evaluation licence**. VoxiHost does not
sell or renew Windows licences: after the evaluation period, activate or extend the licence
with Microsoft (or your reseller).

If you plan to run Windows long-term, budget for the licence separately. VoxiHost is an
infrastructure provider and does not verify customer licences; if a rights holder reports a
violation, the service may be suspended until the licence status is clarified.

## Reinstall the operating system

You need the instance stopped and, if you may need the current files, a backup. Reinstalling
is a destructive recovery action, not a repair:

1. Stop the instance first. Reinstall is refused while it is running.
2. Open the instance and select the **Danger Zone** tab.
3. Select **Reinstall**.
4. Choose the new OS family and version and set a new **Root Password**.
5. Confirm the data-loss warning.

The instance moves to `reinstalling`, briefly back to `queue`, then `installing`, then
`running`. Everything on the disk is replaced. Reinstall is the right tool when you want a
clean system or a different distribution; it is not a way to recover files. If you need the
current data, take a backup first: see
[Backups & snapshots](/docs/platform/client-panel/snapshots/).

## What "unmanaged" means

VoxiHost provides the instance and its network. Inside the operating system, you own:

- OS updates and upgrades.
- Users, SSH keys, sudo and authentication.
- Installed services, their configuration and their security.
- Backups of application data (in addition to instance backups).
- Firewall rules for the ports you expose.

We do not update or secure the software inside your server. That is your job. If a service
is compromised, the instance is yours to rebuild. The `/guides/` section covers many of these
tasks, for example
[How to Install Nginx on Ubuntu & Debian](/guides/install-nginx-ubuntu-debian/) and
[How to Secure SSH on Ubuntu & Debian](/guides/secure-ssh-ubuntu-debian/).

## Template compatibility

- Ubuntu and Debian have the widest guide coverage on this site; AlmaLinux, Rocky Linux and
  CentOS-compatible images provide Red Hat-compatible (RHEL-style) workflows.
- Long-term-support (LTS) and stable releases are offered alongside older versions for
  compatibility.
- Zones and plans that are full are greyed out in the form; the OS template list itself is
  global.

After the first boot, connect over the console or SSH. See
[Console, SSH & RDP](/docs/platform/console-access/).
