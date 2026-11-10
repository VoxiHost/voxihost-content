---
image: /assets/images/docs/pl/voxishield/og-image.png
title: "VoxiShield: zapora sieciowa w panelu"
description: "Jak działa dwuwarstwowa ochrona DDoS VoxiShield, jak łączy się z regułami firewalla i co robić w trakcie ataku."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: voxishield
locale: pl
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Co chroni VoxiShield

VoxiShield to ochrona sieciowa działająca przed instancjami. Filtruje złośliwy ruch, zanim
dotrze do serwera, więc ataki wolumenowe i protokołowe nie zużywają pasma ani CPU instancji.

Działa zawsze. Nie włączasz jej per instancja i nic nie trzeba instalować w serwerze.

## Jak działają dwie warstwy

Panel opisuje VoxiShield jako dwie warstwy:

- **Warstwa 1: PletX Edge.** Ruch jest analizowany i czyszczony na brzegu sieci, zanim
  dotrze do instancji. To zatrzymuje duże zalewy, które w innym wypadku przeciążyłyby łącze.
- **Warstwa 2: firewall w panelu.** Firewall, którym sterujesz w zakładce **Firewall**:
  reguły przychodzące, kontrola wychodząca, filtry GeoIP/ASN i limity.

Warstwa 1 chroni sieć. Warstwa 2 decyduje, jaki ruch instancja przyjmuje. Uzupełniają się:
czyszczenie na brzegu nie wie, że powinny być otwarte trzy porty, a reguły portów nie
pochłoną bardzo dużego zalewu.

## Ochrona na każdym planie

VoxiShield jest częścią każdego planu VPS: nie ma osobnego planu ochrony DDoS do dokupienia,
a instancje Budget i Premium otrzymują te same dwie warstwy i te same mechanizmy firewalla.
Przepustowość i ewentualne rozszerzenia opisuje strona produktu VoxiShield. Jeśli spodziewasz
się bardzo dużego ataku, potwierdź wolumen z supportem przed wdrożeniem.

## VoxiShield a firewall instancji

VoxiShield nie zastępuje reguł firewalla. Otwarte porty nadal są Twoją decyzją:

- Reguły przychodzące decydują, które źródła i porty docierają do instancji.
- Globalna polityka przychodząca ustawia domyślne zachowanie dla ruchu bez dopasowanej reguły.
- Kontrola wychodząca ogranicza ruch z instancji: w tym blokadę portu SMTP 25, którą
  zdejmuje się po weryfikacji KYC.

Zacznij od domyślnego blokowania i otwieraj tylko rzeczywiście obsługiwane porty. Zobacz
[Reguły firewalla](/pl/docs/security/firewall-rules/) i
[Dokumentację reguł](/pl/docs/security/firewall-rules/rule-reference/).

## W trakcie ataku

1. Potwierdź objaw: opóźnienia, utrata pakietów lub niedostępność dotykająca instancję, ale
   nie panel.
2. Zanotuj czas rozpoczęcia, docelowy adres IP i wzorzec ruchu, jeśli widzisz go
   w monitoringu.
3. Otwórz zgłoszenie z tymi danymi i nazwą instancji.
4. Nie wyłączaj reguł firewalla w panice: jeśli legalny ruch jest odrzucany, widok Blocked
   IPs i Firewall Block Analyzer wyjaśniają przyczynę.

## Fałszywe alarmy

Jeśli legalni użytkownicy są blokowani:

- Sprawdź **Blocked IPs** w firewallu i użyj **Firewall Block Analyzer** na dotkniętym adresie.
- Przejrzyj filtry GeoIP i ASN: filtr kraju lub sieci może być zbyt szeroki.
- Przejrzyj limity; zbyt niski próg może banować normalne skoki ruchu.
- Jeśli blokada pochodzi z brzegu sieci, a nie z Twoich reguł, otwórz zgłoszenie z adresem
  źródłowym i oknem czasu.
