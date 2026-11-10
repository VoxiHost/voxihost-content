---
image: /assets/images/docs/pl/kyc-verification/og-image.png
title: "Weryfikacja tożsamości (KYC)"
description: "Zweryfikuj tożsamość przez DiDit, zrozum, co jest przechowywane i usuwane, oraz sprawdź, które funkcje wymagają weryfikacji."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: kyc-verification
locale: pl
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Dlaczego weryfikacja jest wymagana

Weryfikacja tożsamości (KYC) jest wymagana przy funkcjach związanych z ryzykiem prawnym lub
nadużyciami:

- Usunięcie blokady portu SMTP 25.
- Odzyskanie kredytów powitalnych, gdy automatyczne przyznanie po uzupełnieniu profilu nie
  nastąpiło. Standardową drogą jest uzupełnienie profilu; KYC to mocniejsza alternatywa.
- Inne kroki, które panel oznacza jako wymagające weryfikacji.

Weryfikacja blokuje też imię, nazwisko i datę urodzenia, co utrudnia przejęcie konta i zmianę
tożsamości. Przeglądanie i wdrażanie standardowych usług nie wymaga KYC.

## Rozpocznij weryfikację w DiDit

1. Otwórz **Account → Verification**.
2. Wybierz **Start Verification**.
3. Przejdź proces DiDit: zrób zdjęcie dokumentu tożsamości i wykonaj kroki weryfikacji żywotności wskazane
   przez operatora.
4. Wróć do panelu. Gdy DiDit analizuje zgłoszenie, zakładka Verification pokazuje
   **Verification Required**; po zakończeniu analizy zmienia się w **Verification Pending**
   lub **Identity Verified**.

Weryfikację prowadzi DiDit, nie support VoxiHost. Panel otrzymuje tylko wynik weryfikacji.

## Co jest przechowywane, a co usuwane

DiDit przetwarza dokument tożsamości i weryfikację żywotności. VoxiHost otrzymuje wynik weryfikacji,
a po akceptacji przechowuje imię, nazwisko i datę urodzenia (zaszyfrowane) i blokuje te pola
w profilu.

Dokumenty tożsamości, selfie i materiał weryfikacji żywotności nie są przechowywane przez
VoxiHost. DiDit
może przechowywać dane weryfikacyjne do miesiąca, a VoxiHost wnioskuje o ich usunięcie po
akceptacji. Retencja danych konta wynika z Polityki Prywatności.

Nie wysyłaj dokumentów tożsamości do supportu e-mailem. Używaj zakładki Verification.

## Status weryfikacji i blokowane pola

Zakładka Verification pokazuje jeden ze statusów:

| Status | Znaczenie | Co możesz zrobić |
|---|---|---|
| **Verification Required** | Brak weryfikacji lub DiDit wciąż analizuje zgłoszenie | Rozpocznij lub kontynuuj weryfikację |
| **Verification Pending** | Analiza DiDit wciąż trwa | Poczekaj; jeśli trwa nietypowo długo, napisz do supportu |
| **Identity Verified** | Zaakceptowano | Korzystaj z funkcji wymagających KYC; imię i data urodzenia są zablokowane |

Oba statusy w toku oznaczają oczekiwanie: **Verification Required** pojawia się przed
analizą DiDit lub w jej trakcie, a **Verification Pending** po otrzymaniu zapisu z analizy.
Dopiero **Identity Verified** odblokowuje funkcje.

Po weryfikacji imię i nazwisko w profilu nie podlegają edycji. Jeśli są błędne, skontaktuj się
z supportem, zamiast tworzyć drugie konto.

## Funkcje wymagające KYC

- **SMTP port 25**: blokadę wychodzącej poczty zdejmuje się tylko dla zweryfikowanych kont.
  Zobacz [Reguły firewalla](/pl/docs/security/firewall-rules/).
- **Kredyty powitalne**: KYC może uwolnić bonus, gdy automatyczne przyznanie po uzupełnieniu
  profilu nie nastąpiło; standardową drogą jest uzupełnienie profilu.
- Każda akcja z komunikatem o weryfikacji w panelu.

## Rozwiązywanie problemów

| Problem | Co zrobić |
|---|---|
| Weryfikacja długo oczekuje | Poczekaj; DiDit może potrzebować czasu. Po ponad dobie otwórz zgłoszenie |
| Weryfikacja nie powiodła się | Powtórz proces DiDit z wyraźnym, dobrze oświetlonym zdjęciem |
| Imię zablokowane i błędne | Napisz do supportu z poprawnymi danymi i dokumentem potwierdzającym |
| Port 25 nadal zablokowany po akceptacji | Wyłącz przełącznik SMTP Mail Block w Outbound Control instancji; staje się dostępny po weryfikacji KYC |
| Kredyty powitalne nieuwolnione | Sprawdź, czy zakładka Verification pokazuje **Identity Verified**, i odśwież pulpit |
