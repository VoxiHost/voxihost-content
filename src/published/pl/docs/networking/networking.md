---
image: /assets/images/docs/pl/networking/og-image.png
title: Sieć
description: "Sieć publiczna i prywatna VPS: główny adres IPv4, włączanie sieci prywatnej, zmiana prędkości i ograniczenia instancji godzinowych."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: networking
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Sieć publiczna

Każda instancja otrzymuje publiczny adres IPv4, widoczny w nagłówku instancji i w zakładce
**Network**. Zakładka podsumowuje **Public addresses**, status **Private network** oraz
**Reachable**, czyli liczbę innych instancji w sieci prywatnej, z którymi ta instancja ma
łączność.

- Adres skopiujesz bezpośrednio z jego kafelka.
- Główny adres jest oznaczony gwiazdką.
- Dodatkowe adresy mają akcję **Make primary**.

Zmiana głównego adresu wpływa na ruch wychodzący i wszystko, co zależy od źródłowego IP,
w tym rekordy DNS i zdalne listy dozwolonych. Po przełączeniu zaktualizuj te wpisy i sprawdź
konfigurację sieci w systemie.

## Dodatkowe adresy publiczne

Dodatkowe adresy IPv4 i IPv6 zamawiasz przy wdrożeniu: do pięciu każdego typu, z opłatami
w **Order Summary**. Po wdrożeniu zakładka Network odsyła do supportu:
**Potrzebujesz więcej adresów? Skontaktuj się z supportem, aby dodać IPv4 lub IPv6.**

Limity i opłaty: [Adresy IP](/pl/docs/platform/networking/ip-addressing/).

## Sieć prywatna

Sieć prywatna daje instancji adres w sieci wewnętrznej strefy, bez wystawiania go publicznie.
Sam dodatek Private Network jest bezpłatny; szybsze poziomy **Speed** są płatne i widoczne
przed potwierdzeniem.

Gdy sieć prywatna jest wyłączona:

1. Otwórz instancję i wybierz **Network**.
2. Wybierz **Enable private network**.
3. Wskaż adres prywatny i **Speed**, następnie potwierdź.

Gdy jest włączona, zakładka pokazuje adres prywatny z kopiowaniem, pozostałych członków sieci
oraz **Change address**, **Change speed** i **Disable private network**. Wybierz akcję,
potwierdź zmianę i zrestartuj instancję, jeśli panel pokaże takie ostrzeżenie.

## Instancje godzinowe a sieć prywatna

Instancje godzinowe nie obsługują sieci prywatnej. Jeśli jej potrzebujesz, wdróż instancję
miesięczną albo zapytaj support o dostępne opcje. Formularz wdrożenia ukrywa dodatek Private
Network dla rozliczenia godzinowego.

## Lokalizacje i testy sieci

Instancje działają w wybranym regionie i strefie; strefa to miejsce fizycznego sprzętu
i wspólnej sieci prywatnej. Aby zmierzyć opóźnienia ze swojej lokalizacji, użyj narzędzi
Looking Glass na stronie. VoxiHost obsługuje AS211011: przydatne przy diagnozowaniu tras
z ISP lub zdalną usługą.

## Gdy sieć wygląda źle

- **Brak publicznego IP**: świeżo wdrożona instancja może pokazywać `Pending IP...` do czasu
  przydzielenia adresu. Poczekaj na `running` i sprawdź ponownie.
- **Instancja nieosiągalna**: sprawdź, czy firewall dopuszcza port, potem użyj konsoli.
- **Sieć prywatna niewidoczna**: upewnij się, że obie instancje są w tej samej strefie
  i mają włączoną sieć prywatną.
- **Problemy z routingiem**: dołącz adresy źródłowy i docelowy, znaczniki czasu oraz wynik
  `traceroute` do zgłoszenia.
