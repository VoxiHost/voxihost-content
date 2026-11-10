---
image: /assets/images/docs/en/metrics/og-image.png
title: "Metrics & monitoring"
description: "Read CPU, memory, disk, network and uptime charts for an instance across every time range the panel offers."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: metrics
locale: en
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Time ranges

The **Metrics** tab shows the same data across five ranges:

| Range | Use it for |
|---|---|
| **Live (1H)** | Watching the effect of a change right now |
| **24 Hours** | Daily patterns and recent incidents |
| **48 Hours** | Comparing today with yesterday |
| **7 Days** | Weekly load patterns |
| **30 Days** | Capacity planning and long-term trends |

Live is near-real-time and refreshes as it runs. Longer ranges are aggregated, so short
spikes can be flattened: use the live view when you need the highest resolution (refreshed
every 10 seconds).

## Metric groups

- **Uptime**: whether the instance was reachable, and gaps in collection.
- **CPU Usage**: processor load over time; sustained high values mean the plan is too
  small for the workload.
- **Memory usage**: RAM used by your server; watch for steady growth that never drops,
  which usually means a leak.
- **Disk space**: used capacity; plan for headroom before it reaches 100%.
- **Disk I/O**: read and write activity; large values alongside slow applications point
  at the disk rather than the CPU.
- **Network (public and private)**: throughput on each interface.
- **Network packets (public and private)**: packet rates, useful for spotting floods or
  unusual traffic patterns.

## Limits of panel metrics

- VoxiHost collects metrics at the platform level; nothing needs to be installed inside your
  instance.
- A stopped instance keeps its history (availability shows 0), but live charts stop updating.
  An instance that is still being created has no data yet.
- The panel measures the instance, not your application. It cannot show per-process usage,
  request latency, query times or business metrics.
- There is no alerting. If you need notifications, run a monitoring service on the instance
  or outside it; [/guides/](/guides/) covers options such as Netdata and Uptime Kuma.
- History is kept for **30 days**; save anything older yourself. The panel has no metrics
  export.

For firewall and network-level events, use the Firewall tab and the
[Firewall rules](/docs/security/firewall-rules/) documentation. For host-level incidents,
open a support ticket with the time window and the chart range you were looking at.
