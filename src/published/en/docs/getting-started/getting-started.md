---
image: /assets/images/docs/en/getting-started/og-image.png
title: Getting started
description: Create your VoxiHost account, add Credits, deploy your first VPS and connect to it over SSH or the console.
date: '2026-10-27'
updated: '2026-10-27'
translationKey: getting-started
locale: en
status: published
section: docs
group: start
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Before you start

VoxiHost is prepaid. You add Credits to your wallet and services are paid from that
balance. **1 Credit = 1.00 PLN**; the panel shows an approximate value in your preferred
currency. Deployment and renewals are charged before they run, and an instance is suspended
when it expires and the balance cannot cover the renewal.

You need:

- An email address you can access: it receives your sign-up code and account notices.
- A payment method supported by Stripe, or a crypto wallet if you prefer crypto top-ups.
- A positive Credit balance before you deploy.
- A password manager for the root password, and an SSH client if you want to connect from
  your own computer. **SSH** is a text-only way to control the server; the browser console
  works without installing anything.

## Create your account

1. Open the sign-up page and enter your email address and a strong password.
2. Read the Terms & Conditions and Privacy Policy, then select **Create Account**.
3. The panel switches to **Check your inbox** and emails you a 6-digit code. Enter it and
   select **Verify & Enter Dashboard**.
4. If the code does not arrive, use **Resend** after the cooldown. If you typed the wrong
   address, select **Wrong email? Change address** and start again.
5. Some accounts must accept a required policy on first sign-in. The confirmation page
   explains the policy; select **Confirm and Continue** to reach the panel.

You can also create an account with Google, GitHub, Discord or Fluxer from the sign-in
page. You can link more sign-in methods later in **Account → Security**.

## Add Credits to your wallet

1. Sign in and open **Billing**.
2. Select **Add Credits**.
3. Choose a Credits package.
4. Choose a payment provider: **Stripe** (cards, BLIK and local methods) or **Crypto**.
   Crypto has a minimum amount.
5. Choose the billing entity: a personal profile produces a receipt, a company profile
   produces an invoice. Company invoicing requires B2B details in your profile.
6. Accept the terms and the withdrawal waiver, then select **Pay**.

After the payment provider returns you to Billing, the banner tells you what happened:
**Payment Successful**, **Confirming Your Payment** for card payments awaiting bank
verification, or **Payment Cancelled**. Crypto returns with the success banner and stays
pending until confirmed. Pending crypto top-ups stay in
the transactions table with a **Continue** action.

More detail: [Billing & wallet](/docs/billing/payments/).

## Deploy your first VPS

1. Select **Deploy New** in the sidebar, or the **+** button in the top bar.
2. Pick a **Region** and then a **Zone**. Sold-out zones are greyed out.
3. Choose a tier: **Budget** for shared-priority plans or **Premium** for high-priority CPU
   time and a much higher memory guarantee.
4. Choose **Monthly** or **Hourly** billing, then select a plan or configure processors,
   memory and storage for an hourly instance.
5. Choose an operating system family and version. Paid licence templates show an extra
   monthly charge.
6. Enter a **Hostname** and a **Root Password**, or generate them in the form. The
   password is shown to you here and stored in the instance credentials afterwards.
7. Optionally add **Private Network**, extra IPv4 or IPv6 addresses, and Automatic
   Backups. Add-ons are available for monthly instances.
8. Review the **Order Summary**, apply a promo code if you have one, accept the legal
   waiver, and select **Deploy Now**.

The new instance appears in **VPS Instances** with the status `queue`, then `installing`,
then `running`. Installation usually completes within a few minutes. Full option-by-option
detail and error messages: [Deploying a VPS](/docs/platform/deploy-vps/).

## Connect to your server

- **Console**: open the instance, switch to **Console** and select **Connect to Console**
  for a VNC session. Use it when SSH is not available yet.
- **SSH**: Linux templates accept `ssh root@<public-ip>` with the root password you set
  at deployment. The exact command is shown in the Console tab together with the public IP.
- **RDP**: Windows templates are reached over Remote Desktop with the administrator
  credentials from the same tab.

## Secure it next

- Enable two-factor authentication in **Account → Security**.
- Add inbound firewall rules in the instance's **Firewall** tab. VoxiShield protects the
  network, but the ports you expose are your decision.
- Enable Automatic Backups or take a manual snapshot before making large changes.
- Harden the operating system itself: see the SSH and firewall guides on
  [/guides/](/guides/), for example
  [How to Secure SSH on Ubuntu & Debian](/guides/secure-ssh-ubuntu-debian/).
