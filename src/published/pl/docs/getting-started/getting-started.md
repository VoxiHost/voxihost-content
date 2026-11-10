---
image: /assets/images/docs/pl/getting-started/og-image.png
title: Pierwsze kroki
description: Załóż konto w VoxiHost, doładuj kredyty, wdróż pierwszy VPS i połącz się przez SSH lub konsolę.
date: '2026-10-27'
updated: '2026-10-27'
translationKey: getting-started
locale: pl
status: published
section: docs
group: start
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Zanim zaczniesz

VoxiHost działa w modelu przedpłaconym. Doładowujesz kredyty na portfel, a usługi są
opłacane z tego salda. **1 kredyt = 1,00 PLN**; panel pokazuje przybliżoną wartość
w wybranej walucie. Wdrożenie i odnowienia są pobierane z góry, a instancja zostaje
zawieszona, gdy wygaśnie, a saldo nie pokryje odnowienia.

Potrzebujesz:

- Adresu e-mail, do którego masz dostęp: trafi tam kod rejestracyjny i powiadomienia.
- Metody płatności obsługiwanej przez Stripe albo portfela kryptowalutowego.
- Dodatniego salda kredytów przed wdrożeniem.
- Menedżera haseł na hasło roota oraz, jeśli chcesz łączyć się z własnego komputera, klienta
  SSH. **SSH** to tekstowy sposób sterowania serwerem; konsola w przeglądarce działa bez
  instalacji.

## Załóż konto

1. Otwórz stronę rejestracji i podaj adres e-mail oraz silne hasło.
2. Przeczytaj Terms & Conditions i Privacy Policy, a następnie wybierz **Create Account**.
3. Panel przejdzie do widoku **Check your inbox** i wyśle 6-cyfrowy kod. Wpisz go
   i wybierz **Verify & Enter Dashboard**.
4. Jeśli kod nie dotarł, użyj **Resend** po odczekaniu limitu. Jeśli podałeś zły adres,
   wybierz **Wrong email? Change address** i zacznij od nowa.
5. Część kont musi przy pierwszym logowaniu zaakceptować wymagany regulamin. Strona
   potwierdzenia opisuje politykę: wybierz **Confirm and Continue**, aby wejść do panelu.

Konto możesz też założyć przez Google, GitHub, Discord lub Fluxer na stronie logowania.
Kolejne metody logowania podłączysz później w **Account → Security**.

## Doładuj portfel

1. Zaloguj się i otwórz **Billing**.
2. Wybierz **Add Credits**.
3. Wybierz pakiet kredytów.
4. Wybierz operatora płatności: **Stripe** (karty, BLIK i metody lokalne) albo **Crypto**.
   Płatności kryptowalutowe mają kwotę minimalną.
5. Wybierz podmiot rozliczeniowy: profil prywatny daje paragon, profil firmowy fakturę.
   Faktura firmowa wymaga danych B2B w profilu.
6. Zaakceptuj regulamin i zrzeczenie się prawa odstąpienia, a następnie wybierz **Pay**.

Po powrocie z operatora baner w Billing informuje o wyniku: **Payment Successful**,
**Confirming Your Payment** dla płatności kartą oczekujących na weryfikację banku albo
**Payment Cancelled**. Kryptowaluty wracają z banerem sukcesu i pozostają oczekujące
w tabeli transakcji z akcją **Continue** do potwierdzenia.

Więcej: [Płatności i portfel](/pl/docs/billing/payments/).

## Wdróż pierwszy VPS

1. Wybierz **Deploy New** w menu bocznym albo **+** na górnym pasku.
2. Wskaż **Region**, a następnie **Zone**. Strefy bez wolnych miejsc są wyszarzone.
3. Wybierz plan: **Budget** (współdzielony priorytet) lub **Premium** (wysoki priorytet CPU
   i znacznie wyższa gwarancja pamięci).
4. Wybierz rozliczenie **Monthly** albo **Hourly**, a następnie plan; dla instancji
   godzinowej wybierz procesory, pamięć i dysk.
5. Wybierz rodzinę i wersję systemu operacyjnego. Szablony z płatną licencją pokazują
   dodatkową opłatę miesięczną.
6. Podaj **Hostname** i **Root Password** albo wygeneruj je w formularzu. Hasło jest
   widoczne tutaj i później w danych dostępowych instancji.
7. Opcjonalnie dodaj **Private Network**, dodatkowe adresy IPv4/IPv6 i Automatic Backups.
   Dodatki są dostępne dla instancji miesięcznych.
8. Sprawdź **Order Summary**, wpisz kod promocyjny, zaakceptuj oświadczenie i wybierz
   **Deploy Now**.

Nowa instancja pojawia się w **VPS Instances** ze statusem `queue`, potem `installing`,
a na końcu `running`. Instalacja zwykle kończy się w kilka minut. Pełny opis opcji
i komunikatów błędów: [Wdrażanie VPS](/pl/docs/platform/deploy-vps/).

## Połącz się z serwerem

- **Console**: otwórz instancję, przejdź do **Console** i wybierz **Connect to Console**,
  aby dostać sesję VNC. Przydaje się, gdy SSH jeszcze nie działa.
- **SSH**: szablony linuksowe przyjmują `ssh root@<public-ip>` z hasłem roota ustawionym
  przy wdrożeniu. Dokładne polecenie jest widoczne w zakładce Console razem z adresem IP.
- **RDP**: szablony Windows obsługuje Remote Desktop z danymi administratora z tej samej
  zakładki.

## Zabezpiecz serwer

- Włącz uwierzytelnianie dwuskładnikowe w **Account → Security**.
- Dodaj reguły przychodzące w zakładce **Firewall** instancji. VoxiShield chroni sieć, ale
  o tym, jakie porty są wystawione, decydujesz Ty.
- Włącz Automatic Backups albo zrób ręczny snapshot przed większymi zmianami.
- Utwardź system operacyjny: poradniki SSH i firewalla znajdziesz na
  [/pl/guides/](/pl/guides/), na przykład
  [Jak zabezpieczyć SSH na Ubuntu i Debian](/pl/guides/jak-zabezpieczyc-ssh-ubuntu-debian/).
