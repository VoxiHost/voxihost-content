---
image: /assets/images/docs/pl/metrics/og-image.png
title: "Metryki i monitorowanie"
description: "Odczytuj wykresy CPU, pamięci, dysku, sieci i uptime instancji dla wszystkich zakresów czasu dostępnych w panelu."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: metrics
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Zakresy czasu

Zakładka **Metrics** pokazuje te same dane w pięciu zakresach:

| Zakres | Do czego służy |
|---|---|
| **Live (1H)** | Obserwacja efektu zmiany w tej chwili |
| **24 Hours** | Dzienne wzorce i ostatnie incydenty |
| **48 Hours** | Porównanie dnia dzisiejszego z wczorajszym |
| **7 Days** | Tygodniowe wzorce obciążenia |
| **30 Days** | Planowanie pojemności i trendy długoterminowe |

Live jest aktualizowany na bieżąco. Dłuższe zakresy są agregowane, więc krótkie skoki mogą
zostać spłaszczone: najwyższą rozdzielczość (odświeżanie co 10 sekund) daje widok live.

## Grupy metryk

- **Uptime**: czy instancja była osiągalna, oraz luki w zbieraniu danych.
- **CPU Usage**: obciążenie procesora; trwale wysokie wartości oznaczają, że plan jest za mały.
- **Memory usage**: RAM zużywany przez system; stały wzrost bez spadków zwykle oznacza wyciek.
- **Disk space**: zajętość dysku; zaplanuj zapas, zanim osiągnie 100%.
- **Disk I/O**: odczyt i zapis; wysokie wartości przy wolnej aplikacji wskazują na dysk.
- **Network (public i private)**: przepustowość każdego interfejsu.
- **Network packets (public i private)**: liczba pakietów, przydatna do wykrywania zalewów.

## Ograniczenia metryk panelu

- Metryki zbiera platforma VoxiHost; nic nie trzeba instalować wewnątrz instancji.
- Zatrzymana instancja zachowuje historię (dostępność pokazuje 0), ale wykresy live przestają
  się aktualizować. Instancja, która dopiero się tworzy, nie ma jeszcze danych.
- Panel mierzy instancję, nie aplikację. Nie pokaże zużycia per proces, opóźnień żądań,
  czasów zapytań ani metryk biznesowych.
- Nie ma alertów. Jeśli potrzebujesz powiadomień, uruchom monitoring na instancji lub poza nią;
  `/pl/guides/` opisuje m.in. Netdata i Uptime Kuma.
- Historia jest przechowywana przez **30 dni**; starsze dane zapisz samodzielnie. Panel nie ma
  eksportu metryk.

Zdarzenia sieciowe i firewall sprawdzisz w zakładce Firewall oraz w
[Regułach firewalla](/pl/docs/security/firewall-rules/). Przy incydencie hosta otwórz
zgłoszenie z oknem czasu i zakresem wykresu, który analizowałeś.
