---
image: /assets/images/docs/pl/billing/og-image.png
title: "Płatności i portfel"
description: "Kredyty, doładowania, transakcje, faktury i paragony oraz to, jak przedpłacone saldo utrzymuje usługi w działaniu."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: billing
locale: pl
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Portfel i kredyty

VoxiHost działa w modelu przedpłaconym. Portfel przechowuje **Credits**; **1 kredyt =
1,00 PLN**. Panel pokazuje też przybliżoną wartość w wybranej walucie, przeliczoną kursami NBP
(kursy walutowe Narodowego Banku Polskiego).

- Wdrożenia, odnowienia i dodatki są pobierane z salda.
- Gdy odnowienie nie może zostać pokryte w dacie wygaśnięcia, instancja zostaje zawieszona do czasu doładowania.

Portfel należy do **aktywnej przestrzeni**, a nie do całego konta, więc firma i przestrzeń
prywatna mają osobne salda. Przełączenie przestrzeni zmienia pokazywane saldo, a odnowienie
zawsze obciąża portfel tej przestrzeni, do której należy usługa. Opisuje to strona
[Przestrzenie robocze](/pl/docs/account/workspaces/).

Otwórz **Billing**, aby zobaczyć saldo, akcję **Add Credits**, transakcje i wskaźniki
rozliczeniowe.

## Doładuj kredyty

1. W **Billing** wybierz **Add Credits**.
2. Wybierz pakiet.
3. Wybierz operatora: **Stripe** (karty, BLIK i metody lokalne) albo **Crypto**.
4. Wybierz podmiot rozliczeniowy. Profil prywatny daje paragon, firmowy fakturę i wymaga
   danych B2B.
5. Zaakceptuj regulamin i zrzeczenie się prawa odstąpienia, następnie wybierz **Pay**.

Po powrocie od operatora baner informuje o wyniku: **Payment Successful**, **Confirming Your
Payment** dla płatności kartą oczekujących na weryfikację banku lub **Payment Cancelled**.
Płatności kryptowalutowe wracają z banerem sukcesu po akceptacji operatora i pozostają
oczekujące do potwierdzenia w sieci.

Szczegóły płatności i dokumentów:
[Doładowywanie kredytów](/pl/docs/billing/payments/payment-methods/).

## Transakcje

Tabela transakcji wyświetla wszystkie operacje w portfelu.

- Filtry: **Last 30 days**, **Last 90 days** i **All time**.
- Kolumny: transakcja, data, metoda, kwota i dokumenty.
- Oczekujące płatności kryptowalutowe pokazują **Continue**, aby wrócić do płatności.
- Ikona dokumentu otwiera fakturę lub paragon.
- Kliknięcie wiersza otwiera **Transaction Details**.

## Dokumenty i faktury

Każda płatność tworzy dokument:

- **Paragon**: dla profilu prywatnego.
- **Faktura**: dla profilu firmowego z danymi B2B (w tym NIP).

Otwórz dokument z tabeli transakcji i użyj **Download PDF**. Dokumenty pokazują sprzedawcę,
nabywcę, metodę płatności i pozycje. Zwrócone dokumenty są oznaczone **Refunded**. Jeśli dane
nabywcy są błędne, popraw najpierw firmę lub adres rozliczeniowy, a następnie zapytaj support
o ponowne wystawienie dokumentów historycznych.

## Wskaźniki i waluta

Strona Billing pokazuje też:

- **Monthly Cost** z paskiem pozostałych dni bieżącego okresu.
- **Deposits This Month** i **Expenses This Month**.

Walutę preferowaną (PLN, EUR lub USD) ustawia się w preferencjach profilu; określa ona
wyświetlane ceny, dostępne metody płatności i walutę obciążenia przy doładowaniach. Kredyty
pozostają denominowane w PLN.

## Zasady przedpłaty i zawieszenie

- Saldo musi pokrywać wdrożenie, zanim się rozpocznie.
- Odnowienia są pobierane z salda. Gdy saldo nie wystarcza w momencie automatycznego
  odnowienia, auto-renew zostaje wyłączony, a Ty otrzymujesz powiadomienie.
- Instancja, która osiągnie datę wygaśnięcia, zostaje zawieszona i przestaje obsługiwać ruch.
- E-maile ostrzegawcze są wysyłane **7 dni, 3 dni, 1 dzień i 1 godzinę** przed wygaśnięciem
  miesięcznym.
- Zawieszona instancja zostaje **trwale usunięta wraz z danymi 7 dni po wygaśnięciu**, jeśli
  nie zostanie odnowiona. W okresie łaski nadal możesz ją przedłużyć.
- Instancje godzinowe mają ten sam 7-dniowy okres łaski, z ostrzeżeniem 30 minut przed
  wygaśnięciem: zobacz [Rozliczenie godzinowe](/pl/docs/billing/hourly/).

## Gdy coś wygląda źle

- **Doładowanie opłacone, ale brak kredytów**: sprawdź tabelę transakcji. Kryptowaluty
  pozostają oczekujące do potwierdzenia w sieci; użyj **Continue**, aby wrócić do płatności.
  Jeśli transakcja jest zakończona, a saldo się nie zmieniło, otwórz zgłoszenie z datą,
  kwotą i numerem dokumentu.
- **Instancja nadal zawieszona po doładowaniu**: otwórz instancję i sprawdź, czy
  **Auto-Renew** jest wyłączone albo czy instancja już wygasła. Przedłuż ją w okresie łaski;
  jeśli to niemożliwe, otwórz zgłoszenie z nazwą instancji.

## FAQ rozliczeń

**Jak przeliczana jest waluta?**
Ceny i doładowania używają wybranej waluty (PLN, EUR lub USD). Panel pokazuje przybliżone
wartości według kursów NBP i zapisuje odpowiednik w PLN do rozliczeń.

**Dlaczego usługa została zawieszona?**
Saldo nie pokryło odnowienia. Doładuj portfel; jeśli usługa nadal jest zawieszona, otwórz
zgłoszenie.

**Czy wystawiacie faktury firmowe?**
Tak: aktywuj profil firmowy z NIP i wybierz podmiot firmowy przy płatności.

**Jaki operator obsługuje płatności?**
Stripe oraz płatności kryptowalutowe, jeśli są oferowane. Zobacz
[Doładowywanie kredytów](/pl/docs/billing/payments/payment-methods/).

**Czy mogę otrzymać zwrot?**
Kredyty są bezzwrotne po dostarczeniu, a potwierdzone płatności kryptowalutowe są
nieodwracalne. Reklamacje rozliczeniowe składasz przez support; uznana reklamacja może
skutkować zwrotem kredytów, przedłużeniem usługi lub innym uzgodnionym rozwiązaniem. Kredyty
nie są wypłacane w gotówce: przy zakończeniu konta mogą zostać wydane jako bezterminowy kod
promocyjny zgodnie z regulaminem.
