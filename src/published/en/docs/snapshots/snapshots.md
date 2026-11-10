---
image: /assets/images/docs/en/snapshots/og-image.png
title: "Backups & snapshots"
description: "Create, verify, restore and delete instance backups, and understand what the Automatic Backups add-on covers."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: snapshots
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## How backups work

You need either the **Automatic Backups** add-on (for scheduled copies) or free manual
slots. Manual backups are limited to four per instance.

Backups are managed per instance on the **Backups** tab. Two kinds exist:

- **Manual backups**: snapshots you create on demand, up to four per instance.
- **Automatic backups**: weekly snapshots taken on Sundays when the
  **Automatic Backups** add-on is active.

A restore always stops the instance and overwrites its current data with the snapshot.
Backups are for the whole instance, not individual files; they are not a substitute for
application-level exports.

Hourly instances do not support backups; the tab shows **Backups Unavailable**. VoxiHost
still performs system-wide disaster recovery backups for platform safety, but you cannot
create or restore your own snapshots. Move the workload to a monthly plan if you need them.

## Create a manual backup

1. Open the instance and select **Backups**.
2. Select **Create Backup**. The button changes to **Creating...** while the snapshot runs.
3. The new entry appears with a timestamp and a verification state.

Each manual backup consumes one of the four slots. Delete an old snapshot before creating
a fifth. Backup creation does not stop the instance.

## Verification states

- **Pending Verification**: the snapshot exists but has not been verified yet.
- **Verified Snapshot**: the snapshot passed verification and is the safest restore point.

Prefer restoring verified snapshots. If a backup stays pending for an unusually long time, or
a create/restore attempt fails, open a support ticket with the instance name and backup
timestamp.

## Restore a backup

1. Select **Restore Backup** next to a **Verified Snapshot**. Pending snapshots must finish
   verification first; Restore and Delete appear only on verified ones.
2. Confirm the warning: the instance is stopped and **all current data is overwritten**.
3. The instance moves to `restoring`. When the restore completes it ends in `stopped`; start
   it again.

Restoring is destructive. If you need data from the current state, take a manual backup
first.

## Delete a backup

Select **Delete Backup** and confirm. Deletion is permanent and frees a manual slot.

## Automatic Backups add-on

The add-on is available for monthly instances. When it is active:

- Backups run automatically every Sunday.
- The Backups tab shows the automatic snapshots alongside manual ones.
- Turning the add-on off stops future automatic backups; existing snapshots remain until
  you delete them.

If the add-on is not active, the tab shows **Backup Addon Required** with an
**Enable backups** action. Enabling it starts a paid add-on on the instance.

Backups protect the instance disk. They do not protect your VoxiHost account, so keep 2FA
enabled and keep separate copies of anything irreplaceable.
