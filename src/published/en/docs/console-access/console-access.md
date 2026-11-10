---
image: /assets/images/docs/en/console-access/og-image.png
title: "Console, SSH & RDP"
description: "Connect to your VPS through the VNC console, SSH or Remote Desktop, and find the credentials you set at deploy."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: console-access
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Before you connect

- The instance must be `running`.
- You need the root password you set at deployment, or an SSH key you install yourself.
- For SSH you need a terminal: Terminal on macOS/Linux, PuTTY or Windows Terminal on
  Windows. **SSH** is a text-only way to control the server from your own computer.

## VNC console

VNC is a remote screen in your browser: it shows the server's display and sends your
keyboard input, like remote-controlling its monitor.

The **Console** tab gives you a screen and keyboard even when the network or SSH is
unavailable.

1. Open the instance and select **Console**.
2. Select **Connect to Console**. The button shows **Connecting...** while the session starts.
3. Work inside the VNC session; use the fullscreen button for a larger view and the paste
   control to send text such as a long root password.

The console only connects while the instance is `running`. If it is stopped, start it
first. The console is the recovery path for a broken firewall rule or a failed SSH
configuration: it does not depend on the server's network stack being reachable.

## Instance credentials

The Console tab also shows **Instance Credentials**: the default user and the password set
during deployment. Use the reveal and copy controls to avoid transcription errors.

If you changed the root password inside the OS, the panel copy is out of date. Store your
own credentials in a password manager.

## SSH access

Linux templates are reachable over SSH with the public IPv4 address:

```bash
ssh root@<public-ip>
```

The **Access Methods** panel in the Console tab shows the exact command and a copy button for
it. Authenticate with the root password from deployment, or with a key you install yourself.

Recommended practices:

- Create a non-root sudo user and disable password logins once keys work.
- Keep the root login available through the console until key access is confirmed.
- Allow port 22 only from the addresses you use; see
  [Firewall rules](/docs/security/firewall-rules/).
- For key setup, follow [How to Secure SSH on Ubuntu & Debian](/guides/secure-ssh-ubuntu-debian/)
  or [How to Secure SSH on CentOS & RHEL](/guides/secure-ssh-centos-rhel/).

## RDP access

Windows templates are reached with Remote Desktop using the administrator credentials from
deployment. Confirm the Windows firewall allows RDP and restrict the
source addresses in the instance firewall.

## Troubleshooting access

| Symptom | Check |
|---|---|
| Console sticks on **Connecting...** | Confirm the instance is `running`; close and reopen the tab; try another browser; if it persists, use SSH or open a ticket |
| SSH connection refused | Instance running, public IP assigned, port 22 allowed by the firewall |
| SSH authentication failed | Use the deployment root password, or verify your SSH key is installed |
| Console connects but the OS does not boot | Reinstall the OS from Danger Zone, or restore a backup |
| Locked out after a firewall change | Use the console, or fix the rule from the Firewall tab |

If none of these restore access, open a support ticket with the instance name, public IP,
the exact error and the time it started.
