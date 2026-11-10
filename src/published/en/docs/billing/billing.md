---
image: /assets/images/docs/en/billing/og-image.png
title: "Billing & wallet"
description: "Credits, top-ups, transactions, invoices and receipts, and how the prepaid balance keeps your services running."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: billing
locale: en
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Wallet and Credits

VoxiHost is prepaid. Your wallet holds **Credits**; **1 Credit = 1.00 PLN**. The panel also shows an approximate value in your preferred currency, converted using NBP
rates (the Polish central bank's exchange rates).

- Deployments, renewals and add-ons are charged from the balance.
- If a renewal cannot be covered at expiry, the instance is suspended until you top up.

The wallet belongs to the **active workspace**, not to the account as a whole, so a company
and a private workspace keep separate balances. Switching workspaces changes the balance shown,
and a renewal is always charged to the workspace that owns the service. See
[Workspaces](/docs/account/workspaces/).

Open **Billing** to see the current balance, the **Add Credits** action, transactions and
the billing KPIs.

## Add Credits

1. On **Billing**, select **Add Credits**.
2. Choose a package.
3. Choose the payment provider: **Stripe** for cards, BLIK and local methods, or **Crypto**.
4. Choose the billing entity. A personal profile produces a receipt; a company profile
   produces an invoice and requires B2B details.
5. Accept the terms and the withdrawal waiver, then select **Pay**.

When you return from the provider, the banner reports the outcome: **Payment Successful**,
**Confirming Your Payment** for card payments awaiting bank verification, or **Payment
Cancelled**. Crypto payments return with the success banner once the provider accepts them and
stay pending until the network confirms them.

Payment details and document rules: [Adding credits](/docs/billing/payments/payment-methods/).

## Transactions

The transactions table lists every wallet movement.

- Filter with **Last 30 days**, **Last 90 days** or **All time**.
- Columns: transaction, date, method, amount and documents.
- Pending crypto payments show **Continue** so you can reopen the payment.
- Select the document icon to open the invoice or receipt.
- Select a row to open **Transaction Details**.

## Documents and invoices

Each payment produces a document:

- **Receipt**: for a personal profile.
- **Invoice**: for a company profile with B2B details (including the tax ID/NIP).

Open a document from the transactions table to view it and use **Download PDF**. Documents
show the seller, buyer, payment method and line items. Refunded documents are marked
**Refunded**. If buyer details are wrong, fix the company or billing address first, then
ask support about reissuing historical documents.

## Billing KPIs and preferred currency

The Billing page also shows:

- **Monthly Cost** with a days-left bar for the current period.
- **Deposits This Month** and **Expenses This Month**.

The preferred currency (PLN, EUR or USD) is set in the profile preferences and determines the
prices shown, the available payment methods and the currency charged for top-ups; Credits remain
denominated in PLN.

## Prepaid rules and suspension

- The balance must cover a deployment before it starts.
- Renewals are charged from the balance. If the balance is insufficient when auto-renew runs,
  auto-renew is disabled and you are notified.
- An instance that reaches its expiry is suspended and stops serving traffic.
- Warning emails are sent **7 days, 3 days, 1 day and 1 hour** before a monthly expiry.
- A suspended instance is **permanently deleted with its data 7 days after expiry** unless it
  is renewed. You can still extend it during that grace period.
- Hourly instances follow the same 7-day grace, with a 30-minute warning before expiry: see
  [Hourly billing](/docs/billing/hourly/).

## If something looks wrong

- **Top-up paid but Credits are missing**: check the transactions table. Crypto stays
  pending until the network confirms it; use **Continue** to reopen the payment. If it shows
  completed and the balance is unchanged, open a ticket with the transaction date, amount and
  document number.
- **Instance still suspended after topping up**: open the instance and check whether
  **Auto-Renew** is off or the instance has already expired. Extend it during the grace
  period; if that is not possible, open a ticket with the instance name.

## Billing FAQ

**How is the currency converted?**
Prices and top-up charges use your preferred currency (PLN, EUR or USD). The panel shows
approximate values using NBP rates and records the PLN equivalent for accounting.

**Why was my service suspended?**
The balance did not cover a renewal. Top up the wallet; if the service stays suspended,
open a support ticket.

**Do you support business invoices?**
Yes: activate the company profile with your tax ID and choose the company entity at
checkout.

**Which processor handles payments?**
Stripe, plus crypto payments where offered. See
[Adding credits](/docs/billing/payments/payment-methods/).

**Can I get a refund?**
Credits are non-refundable once delivered, and confirmed crypto payments are irreversible.
Billing complaints go through support; a recognized complaint may return Credits, extend the
service or apply another agreed remedy. Unused Credits are not paid out in cash: on account
termination they may be issued as a non-expiring promo code under the Terms.
