---
image: /assets/images/docs/en/workspaces/og-image.png
title: Workspaces
description: "Run services for yourself, a company or a school in separate workspaces, invite teammates and decide what each of them can do."
date: '2026-11-10'
updated: '2026-11-10'
translationKey: workspaces
locale: en
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## What a workspace is

A workspace holds services, a wallet and the people who may use them. Every
account starts with one **Personal** workspace, which is the default and cannot be
deleted. You can add a **Business** or an **Education** workspace when the services
belong to a company or a school rather than to you as a person.

Keeping them apart matters for three reasons:

- **Money**: each workspace has its own credit balance. A top-up in one does not
  fund the other.
- **Documents**: invoices and receipts carry the buyer details of the workspace
  that paid, so a company invoice does not end up under a private purchase.
- **Legal regime**: a business workspace accepts the Data Processing Agreement;
  a personal one does not.

The workspace you are working in is shown in the top bar, and at the top of the
sidebar on wide screens; on a phone, open the sidebar to reach it. Everything that
follows depends on it: the services list, the wallet, the invoices and the members.

## Switching workspaces

Select the workspace name, then choose another one from the list. The panel
reloads its data for that workspace. Your choice is remembered on this device, and
a membership the owner removes takes effect immediately.

## Creating a workspace

Open the workspace switcher and select **Manage workspaces**, then **New
workspace**. Pick the type, give it a name and confirm with **Create workspace**.
A new workspace starts with an empty wallet, no services and you as its owner.

A **Business** or **Education** workspace starts locked: company or student
verification has to be completed before the workspace opens, and the panel links
straight to it. An education workspace is always named **Education**, so a
workspace cannot pass itself off as a particular school; the institution is part of
the verification, not of the name.

## Members and roles

A business workspace you own can be shared. Open the workspace, go to **Members**
and select **Invite member**. The invitation needs an address that already has a
VoxiHost account, and the row appears immediately with an **Invited** pill until it
is accepted. Education workspaces are personal to one student and do not accept
invites.

Each member has a role and, on top of it, a set of **capabilities**. The role is a
starting point; the owner decides what the person can actually do.

| Role | Baseline |
|---|---|
| Viewer | View support tickets |
| Member | View, open and reply to tickets |
| Billing | Wallet and invoices, plus support |
| Admin | Services, billing, members and settings, but not deleting the workspace |
| Owner | Everything, including deleting the workspace |

Capabilities you can grant or withhold per member:

| Capability | What it allows |
|---|---|
| Create services | Deploy new services in this workspace |
| Power | Start, stop and restart services |
| Destroy | Permanently delete services |
| View billing | See the wallet, payments and invoices |
| Add funds | Top up the workspace wallet |
| Request invoices | Ask for a VAT invoice |
| Request refunds | Ask for a service refund |
| Manage members | Invite, change roles and remove members |
| Edit settings | Rename, legal details and notification email |
| Delete workspace | Permanently remove the workspace |
| View tickets | Read support tickets in this workspace |
| Open tickets | Start a new support request |
| Reply and close | Answer, close and reopen tickets |

The owner keeps every capability. A role never grants something the owner has
withheld, and withdrawing a capability takes effect for that person at once.

## The workspace wallet

Credits belong to the workspace, not to the person who added them. The
**Billing** page shows the balance of the active workspace; top-ups, bonus credits
and refunds land there. When you switch workspaces the balance changes with it.

Automatic renewals are charged to the wallet of the workspace that owns the
service, so a service never renews from another workspace's funds.

## Company details

A business workspace has a **Company** tab with the legal identity, the invoicing
address and the notification e-mail used for invoices and notices. The legal name,
the tax ID and the address are stored encrypted; workspace members who open the
tab see them, and our team sees them only as far as servicing your account
requires.

Keep them current: an invoice request copies the details stored at that moment,
and correcting them afterwards does not rewrite a document that was already
issued.

## Rewards

An education workspace has a **Rewards** tab with its bonus balance, the amount
earned this year, the monthly base and the date of the nearest expiry. Business
and personal workspaces have no Rewards tab; their bonus credits are listed in
**Billing** instead.

Bonus credits are separate from paid credits and can expire. When a charge is made
they are used before the paid ones, so a bonus does not sit unused until it lapses.

## Danger zone

The **Danger zone** tab removes the workspace. It refuses while the workspace
still has services (expired ones included), another member, an open invoice or
refund request, or a balance above zero. Deleting a workspace is permanent: its
members lose access, and its tickets and documents stay with the people who need
them for accounting and legal reasons.

The owner can also hand that permission to an admin. The Personal workspace never
appears in this tab.

## Limits

Every account holds one Personal workspace and up to five additional business or
education workspaces in total. Once you reach the limit, **New workspace** is no
longer offered and the panel tells you why.
