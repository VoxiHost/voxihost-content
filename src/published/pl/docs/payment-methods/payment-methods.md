---
image: /assets/images/docs/pl/payment-methods/og-image.png
title: Doładowywanie kredytów
description: "Płać przez Stripe lub kryptowaluty, sprawdź dostępne metody i monety, wybierz paragon lub fakturę i poznaj zasady zwrotów."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: payment-methods
locale: pl
status: published
section: docs
group: billing
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Płatności Stripe

Stripe to domyślny operator płatności kartowych i lokalnych. Na ekranie płatności widnieje jako
**Cards, BLIK & Local**.

Dostępne metody zależą od waluty pakietu:

| Waluta | Metody |
|---|---|
| **PLN** | Karty, BLIK, Przelewy24, Klarna, Link, Revolut Pay, PayPal |
| **EUR** | Karty, Klarna, Link, Revolut Pay, EPS, Bancontact, MobilePay, MB WAY, TWINT, Przelewy24, PayPal, iDEAL, Bizum |
| **USD** | Karty, Link, PayPal |

Portfele kart **Apple Pay** i **Google Pay** są dostępne przez Stripe Checkout. Gdy urządzenie,
przeglądarka i karta je obsługują, pojawiają się jako przyciski portfela obok formularza karty;
tak samo działa **Link** dla zapisanych danych płatności Stripe.

1. W **Add Credits** wybierz pakiet.
2. Wybierz operatora Stripe.
3. Wybierz podmiot rozliczeniowy i zaakceptuj warunki.
4. Wybierz **Pay** i dokończ płatność w kasie Stripe.
5. Wróć do Billing: baner **Payment Successful** potwierdza zaksięgowanie.

Anulowanie kasy pokazuje **Payment Cancelled** i nie dodaje kredytów. Jeśli operator odrzuci
płatność, wracasz bez kredytów; spróbuj ponownie lub wybierz inną metodę. Danymi karty zarządza
Stripe; VoxiHost nie przechowuje numeru karty.

## Płatności kryptowalutowe

Kryptowaluty obsługuje **NOWPayments** i obowiązuje kwota minimalna:

| Waluta preferowana | Minimum |
|---|---|
| PLN | 40,00 |
| EUR | 10,00 |
| USD | 11,00 |

1. Wybierz operatora krypto i potwierdź kwotę.
2. Na fakturze NOWPayments wybierz monetę i sieć płatności. Widoczne są waluty włączone na
   koncie operatora: najczęściej Bitcoin (BTC), Ethereum (ETH), Litecoin (LTC), TRON (TRX),
   Tether (USDT), TrueUSD na TRON (TUSD), Dogecoin (DOGE), Monero (XMR) i Solana (SOL).
   USDT można wysłać sieciami m.in. TRON, Ethereum, BNB Smart Chain, Avalanche C-Chain,
   Polygon, Optimism, Arbitrum, Celo, TON, Solana i opBNB.
3. Zapłać dokładną kwotę i zachowaj link do transakcji do czasu potwierdzenia.

Transakcja pozostaje oczekująca w tabeli do potwierdzenia w sieci. Użyj **Continue**, aby
wrócić do płatności. Operator wraca z banerem sukcesu po akceptacji płatności; kredyty są
dodawane po potwierdzeniu w sieci.

## Paragon prywatny a faktura firmowa

Podmiot rozliczeniowy decyduje o dokumencie:

| Podmiot | Dokument | Wymagania |
|---|---|---|
| Profil prywatny | Paragon | Imię, nazwisko i adres rozliczeniowy w profilu |
| Profil firmowy | Faktura | Aktywny profil B2B z nazwą firmy, NIP i adresem |

Wybieraj podmiot firmowy przy płatności dopiero po aktywowaniu profilu firmy. Dokumenty są
dostępne w tabeli transakcji i do pobrania jako PDF. Zobacz
[Płatności i portfel](/pl/docs/billing/payments/).

## Waluta i przeliczenia

- Kredyty są denominowane w PLN: **1 kredyt = 1,00 PLN**.
- Waluta preferowana (PLN, EUR lub USD) określa wyświetlane ceny, dostępne metody płatności
  i walutę obciążenia przy doładowaniach; nie zmienia wartości kredytu w PLN.
- Dokładna kwota do zapłaty jest zawsze widoczna przed potwierdzeniem.

## Zrzeczenie się prawa odstąpienia i zwroty

Przed płatnością trzeba zaakceptować regulamin i zrzeczenie się prawa odstąpienia, ponieważ
kredyty są dostarczane natychmiast, a 14-dniowy termin odstąpienia jest wyłączony.

Kredyty są **bezzwrotne** po dostarczeniu doładowania, a potwierdzone płatności kryptowalutowe
są nieodwracalne. Jeśli płatność się powiodła, ale usługa nie została dostarczona, lub uważasz,
że obciążenie jest błędne, złóż reklamację przez support z datą transakcji, kwotą i numerem
dokumentu. Uznana reklamacja może skutkować zwrotem kredytów, przedłużeniem usługi lub innym
uzgodnionym rozwiązaniem: kredyty nie są wypłacane w gotówce.
