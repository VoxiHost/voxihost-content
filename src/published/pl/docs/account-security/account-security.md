---
image: /assets/images/docs/pl/account-security/og-image.png
title: "Logowanie i bezpieczeństwo"
description: "Zaloguj się hasłem lub przez OAuth, zresetuj hasło, włącz 2FA, przeglądaj sesje i zarządzaj wymaganymi regulaminami."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: account-security
locale: pl
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Logowanie

Strona logowania przyjmuje adres e-mail i hasło albo szybkie logowanie przez Google, GitHub,
Discord lub Fluxer. Użyj opcji pokaż/ukryj, jeśli wpisujesz hasło na współdzielonym
urządzeniu, i pozostaw **Keep me signed in** wyłączone, chyba że urządzenie jest Twoje.

Zalogowana sesja kończy się sama po godzinie bez aktywności, nawet z włączonym **Keep me
signed in**. Kolejne żądanie wraca na stronę logowania z komunikatem, a zapamiętane urządzenie
jest unieważniane razem z sesją, więc trzeba zalogować się ponownie. **Keep me signed in**
oszczędza hasło tylko przy *nowej* sesji; nie przedłuża bezczynnej.

Jeśli konto ma włączone uwierzytelnianie dwuskładnikowe, panel poprosi o kod po haśle. Wpisz
kod dla włączonej metody (aplikacja uwierzytelniająca albo e-mail) i wybierz **Verify & Login**.

## Założenie konta

1. Podaj e-mail i hasło, potwierdź hasło i zaakceptuj Terms & Conditions oraz Privacy Policy.
2. Wybierz **Create Account**.
3. Wpisz 6-cyfrowy kod wysłany na skrzynkę i wybierz **Verify & Enter Dashboard**.
4. Jeśli kod nie dotarł, użyj **Resend** po odczekaniu limitu. Przy złym adresie wybierz
   **Wrong email? Change address**.

Część kont musi przy pierwszym logowaniu zaakceptować wymagany regulamin. Strona wyjaśnia go
i oferuje **Confirm and Continue**; bez akceptacji możesz się wylogować.

## Reset hasła

1. Na stronie logowania otwórz link resetowania hasła.
2. Podaj adres e-mail i wybierz **Send Reset Link**.
3. Otwórz wiadomość i skorzystaj z linku.
4. Wpisz dwukrotnie nowe hasło i wyślij.

Linki resetowania wygasają. Nieprawidłowy lub wygasły link pokazuje **Link Expired or Invalid**
z akcją **Try Again**. Reset zmienia tylko hasło; logowanie OAuth i 2FA pozostają bez zmian.

Nowe hasło musi mieć co najmniej 12 znaków i łączyć wielkie i małe litery, cyfrę oraz znak
specjalny. Jest też sprawdzane w znanych wyciekach i odrzucane, jeśli już się w nich pojawiło.

## Uwierzytelnianie dwuskładnikowe

Włącz 2FA w **Account → Security**:

1. Znajdź **Two-Factor Authentication** i wybierz **Manage 2FA**.
2. Przejdź kroki konfiguracji aplikacji uwierzytelniającej.
3. Zachowaj dane odzyskiwania w bezpiecznym miejscu.

Po włączeniu każde nowe logowanie wymaga kodu. Jeśli stracisz dostęp do aplikacji, skontaktuj
się z supportem: odzyskanie wymaga potwierdzenia własności konta.

## Aktywne sesje

Zakładka Security wyświetla **Active Sessions**, w tym bieżącą.

- Każda sesja pokazuje urządzenie i przeglądarkę, adres IP oraz ostatnią aktywność.
- Wybierz **Revoke**, aby natychmiast zakończyć sesję; kolejne żądanie z tego urządzenia wymaga
  ponownego logowania.
- Jeśli widzisz nieznaną sesję, najpierw zmień hasło, potem ją unieważnij.

## Szybkie logowanie (OAuth)

Zakładka Security wyświetla też dostawców **Quick Login**: Discord, Google, GitHub i Fluxer.
Podłączaj i odłączaj ich tam. Odłączenie usuwa metodę logowania; upewnij się, że pozostaje
inne hasło lub metoda, zanim to zrobisz.

## Jeśli logowanie się nie udaje

| Objaw | Co zrobić |
|---|---|
| Błędne hasło | Użyj linku resetowania na stronie logowania |
| Link resetowania wygasł | Poproś o nowy link i użyj go od razu |
| Logowanie dostawcą odrzucone | E-mail należy już do konta: zaloguj się hasłem i podłącz dostawcę w **Account → Security** |
| Kod 2FA odrzucany | Sprawdź automatyczne ustawienie zegara, poproś o nowy kod lub użyj drugiej włączonej metody |

## Wiadomości marketingowe i wypisanie

Link wypisania w wiadomościach marketingowych zatrzymuje wyłącznie komunikację marketingową.
Wiadomości o koncie, bezpieczeństwie, płatnościach i usługach pozostają bez zmian. Kategorie
powiadomień ustawisz w preferencjach profilu: zobacz
[Profil i preferencje](/pl/docs/account/settings/).
