---
image: /assets/images/docs/en/account-security/og-image.png
title: "Signing in & account security"
description: "Sign in with a password or OAuth, reset a password, enable 2FA, review active sessions and manage required policies."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: account-security
locale: en
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Sign in

The sign-in page accepts an email address and password, or a quick login with Google,
GitHub, Discord or Fluxer. Those quick logins use OAuth, which means signing in with an
account you already have at that provider. Use the show/hide control if you are typing on a shared device,
and leave **Keep me signed in** off unless the device is yours.

A signed-in session ends by itself after one hour without activity, even with **Keep me
signed in** on. The next request returns you to the sign-in page with a notice, and the
remembered device is revoked with it, so signing in again is required. **Keep me signed in**
only spares you the password on a *new* session; it does not extend an idle one.

If the account has two-factor authentication enabled, the panel asks for the code after the
password step. Enter the code for the method you enabled (authenticator app or email), then
select **Verify & Login**.

## Create an account

1. Enter an email address and password, confirm the password, and accept the Terms &
   Conditions and Privacy Policy.
2. Select **Create Account**.
3. Enter the 6-digit code sent to your inbox, then select **Verify & Enter Dashboard**.
4. If the code does not arrive, use **Resend** after the cooldown. If the address is wrong,
   select **Wrong email? Change address**.

Some accounts must accept a required policy on first sign-in. The page explains it and
offers **Confirm and Continue**; if you do not accept, you can log out.

## Reset your password

1. On the sign-in page, open the password reset link.
2. Enter your email address and select **Send Reset Link**.
3. Open the email and follow the link.
4. Enter the new password twice and submit.

Reset links expire. An invalid or expired link shows **Link Expired or Invalid** with a
**Try Again** action. Reset only affects the password; OAuth logins and 2FA settings stay
as they are.

A new password must be at least 12 characters and mix upper case, lower case, a digit and a
symbol. It is also checked against known data breaches and refused if it has appeared in one.

## Two-factor authentication

Enable 2FA in **Account → Security**:

1. Find **Two-Factor Authentication** and select **Manage 2FA**.
2. Follow the setup steps for your authenticator app.
3. Store the recovery information in a safe place.

Once enabled, every new sign-in asks for a code. If you lose access to the authenticator,
first try the recovery options shown during setup. If none work, contact support with your
account email and proof of ownership; recovery cannot be done from the panel.

## Active sessions

The Security tab lists **Active Sessions**, including the current one.

- Each session shows the device and browser, IP address and last activity.
- Select revoke to end a session immediately; the next request from that device requires a
  new sign-in.
- If you see an unfamiliar session, change your password first, then revoke it.

## Quick login (OAuth)

The Security tab also lists **Quick Login** providers: Discord, Google, GitHub and Fluxer.
Connect or disconnect each provider there. Disconnecting removes the login method; make sure
another method or a password remains available before you do.

## If sign-in fails

| Symptom | What to try |
|---|---|
| Wrong password | Use the reset link on the sign-in page |
| Reset link expired | Request a new link and use it promptly |
| Provider login refused | The email already belongs to an account: sign in with your password, then link the provider in **Account → Security** |
| 2FA code rejected | Check the device clock is automatic, then request a new code or use the other enabled method |

## Marketing email and unsubscribe

The unsubscribe link in promotional email stops marketing messages only. Account,
security, billing and service messages are not affected. Notification categories are
controlled in the profile preferences: see
[Profile & preferences](/docs/account/settings/).
