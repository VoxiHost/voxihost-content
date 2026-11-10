---
image: /assets/images/docs/en/payment-methods/og-image.png
title: Adding credits
description: "Pay with Stripe or crypto, see which methods and coins are available, choose a receipt or invoice, and understand refund rules."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: payment-methods
locale: en
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Stripe payments

Stripe is the default provider for cards and local payment methods. The checkout labels it
**Cards, BLIK & Local**.

Which methods appear depends on the currency of the package:

| Currency | Methods offered |
|---|---|
| **PLN** | Cards, BLIK, Przelewy24, Klarna, Link, Revolut Pay, PayPal |
| **EUR** | Cards, Klarna, Link, Revolut Pay, EPS, Bancontact, MobilePay, MB WAY, TWINT, Przelewy24, PayPal, iDEAL, Bizum |
| **USD** | Cards, Link, PayPal |

Card wallets **Apple Pay** and **Google Pay** are available through Stripe Checkout. When
your device, browser and card support them, they appear as wallet buttons alongside the card
form; the same applies to **Link** for saved Stripe payment details.

1. In **Add Credits**, choose a package.
2. Select the Stripe provider.
3. Choose the billing entity and accept the terms.
4. Select **Pay** and complete the payment in Stripe's checkout.
5. Return to Billing: the banner shows **Payment Successful** when the payment settles.

Cancelling the checkout shows **Payment Cancelled** and adds no Credits. If the provider
declines the payment, you return without Credits; retry or choose another method. Stripe
handles card data; VoxiHost never stores your card number.

## Crypto payments

Crypto is handled by **NOWPayments** and has a minimum amount:

| Preferred currency | Minimum |
|---|---|
| PLN | 40.00 |
| EUR | 10.00 |
| USD | 11.00 |

1. Choose the crypto provider and confirm the amount.
2. On the NOWPayments invoice, choose the coin and network you want to pay with. The
   currencies shown are the ones enabled on the provider's account: commonly Bitcoin (BTC),
   Ethereum (ETH), Litecoin (LTC), TRON (TRX), Tether (USDT), TrueUSD on TRON (TUSD),
   Dogecoin (DOGE), Monero (XMR) and Solana (SOL). USDT can be sent over networks including
   TRON, Ethereum, BNB Smart Chain, Avalanche C-Chain, Polygon, Optimism, Arbitrum, Celo, TON,
   Solana and opBNB.
3. Pay the exact amount shown and keep the transaction link while it confirms.

The transaction stays pending in the transactions table until the network confirms it. Use
**Continue** to reopen the payment. The provider returns you with the success banner once it
accepts the payment; Credits are added when the network confirms it.

## Personal receipts vs company invoices

The billing entity decides which document you receive:

| Entity | Document | Requirements |
|---|---|---|
| Personal profile | Receipt | Name and billing address in the profile |
| Company profile | Invoice | Activated B2B profile with company name, tax ID (NIP) and address |

Choose the company entity at checkout only after the company profile is active. Documents
are available from the transactions table and can be downloaded as PDF. See
[Billing & wallet](/docs/billing/payments/).

## Currency and conversion

- Credits are denominated in PLN: **1 Credit = 1.00 PLN**.
- The preferred currency (PLN, EUR or USD) determines the prices shown, the available payment
  methods and the currency charged for top-ups; it does not change the PLN value of a Credit.
- The exact amount due is always shown before you confirm the payment.

## Withdrawal waiver and refunds

Before paying, the checkout requires accepting the terms and a waiver of the right to
withdraw, because Credits are delivered immediately and the 14-day cooling-off period is
excluded.

Credits are **non-refundable** once the top-up is delivered, and confirmed crypto payments are
irreversible. If a payment succeeded but the service was not delivered, or you believe a
charge is wrong, file a complaint through support with the transaction date, amount and
document number. A recognized complaint can result in returned Credits, an extended service
or another agreed remedy: Credits are not paid out in cash.
