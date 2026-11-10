---
image: /assets/images/docs/pl/ip-addressing/og-image.png
title: Adresy IP
description: "IPv4 i IPv6 w VoxiHost: limity dodatkowych adresów, opłaty, ustawianie adresu głównego i kiedy kontaktować się z supportem."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: ip-addressing
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## IPv4 i IPv6 w VoxiHost

Każda instancja otrzymuje publiczny adres IPv4. Adresy IPv6 są dostępne jako dodatek i są
przydatne dla usług, które nie powinny współdzielić adresu IPv4. Adresy prywatne to osobna
funkcja: zobacz [Sieć](/pl/docs/platform/networking/).

Adresy są przypisane do instancji, a nie do konta.

## Dodatkowe adresy IPv4

- Zamawiane przy wdrożeniu: **1-5** dodatkowych adresów na instancję.
- Każdy dodatkowy adres jest płatny i pojawia się w **Order Summary**.
- Po wdrożeniu adresy ponad limit formularza wymagają zgłoszenia do supportu.

## Dodatkowe adresy IPv6

- Zamawiane przy wdrożeniu: **1-5** adresów.
- Pierwszy adres IPv6 jest bezpłatny; kolejne są płatne.
- Powyżej limitu formularza obowiązuje ta sama droga przez support.

## Przed dodaniem adresów

VoxiHost konfiguruje główny IPv4 (oraz IPv6, gdy jest przydzielony) przy wdrożeniu; dodatkowe
adresy trzeba skonfigurować w systemie, a zmiana głównego adresu może przerwać łączność.
Podczas edycji ustawień sieci trzymaj otwartą konsolę.

## Ustawienie adresu głównego

Zakładka **Network** oznacza główny adres gwiazdką. Przy dodatkowym adresie wybierz
**Make primary**.

Główny adres jest domyślnym adresem źródłowym ruchu wychodzącego. Zmieniaj go ostrożnie:

- Zaktualizuj rekordy DNS wskazujące stary adres.
- Zaktualizuj listy dozwolonych na zdalnych usługach.
- Sprawdź konfigurację poczty, jeśli instancja wysyła e-maile.

## Przypisanie adresów w systemie

Panel przypisuje adresy do instancji; system operacyjny musi jeszcze obsłużyć dodatkowe
adresy. Zwykle oznacza to dodanie ich do interfejsu sieciowego lub konfiguracji usługi.
Jeśli nie masz pewności, zacznij od dokumentacji sieci dystrybucji i trzymaj otwartą konsolę
na wypadek utraty połączenia.

## Opłaty i limity

| Element | Limit | Opłata |
|---|---|---|
| Główny IPv4 | 1 na instancję | W cenie |
| Dodatkowe IPv4 | 1-5 przy wdrożeniu | Za adres |
| IPv6 | 1-5 przy wdrożeniu | Pierwszy bezpłatny, kolejne płatne |
| Adres sieci prywatnej | 1 na instancję | Dodatek bezpłatny; poziom Speed płatny |

Ceny są widoczne przed potwierdzeniem zamówienia; wiążący jest formularz wdrożenia.

## Kiedy kontaktować się z supportem

- Potrzebujesz więcej adresów, niż pozwala formularz.
- Adres zniknął lub utknął na `Pending IP...`, gdy instancja już działa.
- Uważasz, że adres znajduje się na liście blokad: podaj adres, usługę zgłaszającą i dokładny komunikat.
- Potrzebujesz przenieść adres między instancjami: robi to support, nie panel.
