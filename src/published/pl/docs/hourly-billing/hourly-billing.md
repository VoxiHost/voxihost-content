---
image: /assets/images/docs/pl/hourly-billing/og-image.png
title: Rozliczenie godzinowe
description: "Jak przedpłacone instancje godzinowe naliczają opłaty, odnawiają się, zawieszają i są usuwane oraz czego nie obsługują."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: hourly-billing
locale: pl
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Czym jest rozliczenie godzinowe

Instancje godzinowe są przedpłacone, ale rozliczane za czas: zamiast stałego planu i cyklu
konfigurujesz procesory, pamięć i dysk i płacisz za czas działania. Formularz wdrożenia
pokazuje **Hourly Rate**, przybliżoną wartość miesięczną oraz **Monthly Cap** w podsumowaniu.

Rozliczenie godzinowe przydaje się do krótkich zadań, testów i projektów, które długo
pozostają bezczynne i można je zatrzymać.

## Jak naliczane są opłaty

- Stawka wynika z zasobów wybranych przy wdrożeniu.
- Opłaty są pobierane z salda kredytów za czas działania instancji.
- Usunięcie instancji kończy rozliczanie; nie pozostaje uśpiona instancja godzinowa.
- **Monthly Cap** w podsumowaniu pokazuje górny limit kosztu konfiguracji godzinowej.

Zasobów instancji godzinowej nie można zmienić po wdrożeniu. Aby zmienić procesory, pamięć
lub dysk, wdróż nową instancję z wybraną konfiguracją.

## Odnowienie i przedłużanie

Zakładka **Overview** instancji pokazuje **Next Renewal** z akcją **Extend Instance** oraz
przełącznik **Auto-Renew**.

- Pozostaw **Auto-Renew** włączone, jeśli instancja ma działać bez przerwy; panel pobierze
  kolejny okres z salda.
- Użyj **Extend Instance**, aby opłacić dodatkowy czas. Na instancji godzinowej staje się
  dostępne po zawieszeniu instancji; kupuje **jedną dodatkową godzinę** po bieżącej stawce
  i przywraca instancję.
- Jeśli saldo nie pokryje odnowienia przy włączonym auto-renew, instancja zostaje zawieszona.

## Zero salda, zawieszenie i usunięcie

- Gdy saldo nie pokrywa kolejnej godziny, instancja wygasa i zostaje zawieszona. Około
  **30 minut** przed wygaśnięciem instancji godzinowej wysyłany jest e-mail ostrzegawczy,
  chyba że instancja odnowi się automatycznie z salda.
- Zawieszona instancja nie obsługuje ruchu. Doładuj saldo i przywróć ją albo usuń, jeśli nie
  jest już potrzebna.
- Bez odnowienia instancja zostaje **trwale usunięta wraz z danymi po 7 dniach** od wygaśnięcia.
- **Destroy Instance** znajduje się w **Danger Zone** i wymaga wpisania nazwy instancji.
  Operacja jest trwała.

Usunięcie instancji godzinowej to normalny sposób zakończenia opłat. Najpierw zrób kopię lub
wyeksportuj dane: instancje godzinowe nie obsługują dodatku kopii zapasowych, więc dane
znikają razem z instancją.

## Ograniczenia instancji godzinowych

| Funkcja | Godzinowe |
|---|---|
| Dodatki (kopie, dodatkowe IP, sieć prywatna) | Niedostępne |
| Sieć prywatna | Niedostępna |
| Automatic Backups | Niedostępne |
| Kody promocyjne | Niedostępne |
| Zmiana zasobów | Niemożliwa po wdrożeniu |
| Samodzielne usunięcie | Dostępne, z potwierdzeniem nazwy |

Wdróż instancję miesięczną, jeśli potrzebujesz sieci prywatnej, kopii lub dodatków. Plany
miesięczne są opłacane za cykl i obsługują rabaty; plany godzinowe są rozliczane za godzinę.

## Przejście między Monthly i Hourly

Na instancji **miesięcznej** zakładka **Overview** zawiera akcję **Billing Scheme**. Zmienia
ona przedpłacony cykl rozliczeniowy (dłuższe okresy z rabatem), jest bezpłatna i obowiązuje od
następnego odnowienia. Billing Scheme nie jest dostępny dla instancji godzinowych; aby zmienić
model rozliczenia, skontaktuj się z supportem.
