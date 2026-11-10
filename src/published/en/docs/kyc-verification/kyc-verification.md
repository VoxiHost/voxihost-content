---
image: /assets/images/docs/en/kyc-verification/og-image.png
title: "Identity verification (KYC)"
description: "Verify your identity with DiDit, understand what is stored and deleted, and see which features require verification."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: kyc-verification
locale: en
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Why verification is required

Identity verification (KYC) is required for features that carry legal or abuse risk:

- Lifting the SMTP port 25 block.
- Recovering welcome Credits when the automatic profile-completion grant did not happen. The
  normal route is completing your profile; KYC is the stronger alternative.
- Any other step the panel marks as requiring verification.

Verification also locks your name and date of birth, which prevents account takeover from
changing the identity behind it. Browsing and deploying standard services do not require
it.

## Start verification with DiDit

1. Open **Account → Verification**.
2. Select **Start Verification**.
3. Follow the DiDit flow: capture your identity document and complete the liveness steps
   the provider asks for.
4. Return to the panel. While DiDit reviews your submission the Verification tab shows
   **Verification Required**; after the review it becomes **Verification Pending** or
   **Identity Verified**.

Verification is handled by DiDit, not by VoxiHost support. The panel only receives the
verification result.

## What is stored and what is deleted

DiDit processes your identity document and the liveness check. VoxiHost receives the
verification result and, on approval, stores your first name, last name and date of birth
(encrypted) and locks those fields in the profile.

Identity documents, selfies and liveness media are not stored by VoxiHost. DiDit may keep
verification data for up to one month, and VoxiHost requests deletion after approval.
Account-data retention follows the Privacy Policy.

Do not send identity documents to support by email. Use the Verification tab.

## Verification status and locked fields

The Verification tab shows one of these statuses:

| Status | Meaning | What you can do |
|---|---|---|
| **Verification Required** | No verification yet, or DiDit is still reviewing your submission | Start or continue verification |
| **Verification Pending** | DiDit's review is still in progress | Wait; contact support if it stays pending unusually long |
| **Identity Verified** | Approved | Use gated features; name and date of birth are locked |

Both in-progress labels mean wait: **Verification Required** appears before or during
DiDit's review, and **Verification Pending** once the review record has arrived. Only
**Identity Verified** unlocks features.

Once verified, first and last name in the profile cannot be edited. If they are wrong,
contact support instead of creating a second account.

## Features that require KYC

- **SMTP port 25**: the outbound mail block can only be lifted for verified accounts. See
  [Firewall rules](/docs/security/firewall-rules/).
- **Welcome Credits**: KYC can release the bonus when the automatic profile-completion grant
  did not happen; completing the profile is the normal route.
- Any action that shows a verification notice in the panel.

## Troubleshooting

| Problem | What to do |
|---|---|
| Verification stays pending | Wait; DiDit may need more time. If it exceeds a day, open a ticket |
| Verification failed | Retry the DiDit flow with a clear, well-lit document photo |
| Name locked and wrong | Contact support with the correct details and proof |
| Port 25 still blocked after approval | Turn off the SMTP Mail Block toggle in the instance's Outbound Control; it becomes available once KYC is verified |
| Welcome Credits not released | Confirm the Verification tab shows **Identity Verified**, then reload the dashboard |
