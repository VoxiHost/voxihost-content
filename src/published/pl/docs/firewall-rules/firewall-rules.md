---
image: /assets/images/docs/pl/firewall-rules/og-image.png
title: Reguły firewalla
description: "Steruj ruchem przychodzącym, wychodzącym i globalnym na instancji, z limitami, filtrami GeoIP i analizatorem blokad."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: firewall-rules
locale: pl
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Zanim zaczniesz

Wiedz, które porty są potrzebne Twojej aplikacji; reszta może pozostać zamknięta. Zdjęcie
blokady portu 25 wymaga weryfikacji tożsamości.

## Otwórz zakładkę Firewall

Otwórz instancję i wybierz **Firewall**. Zakładka steruje firewallem instancji przez usługę
firewalla. Selektor **Target IP** na górze wybiera publiczny adres, którego dotyczą reguły.
Instancja z dodatkowymi adresami IPv4 ma osobny zestaw reguł dla każdego adresu.

Podzakładki:

- **Overview**: wskazówki startowe i wyjaśnienie dwóch warstw.
- **Inbound Rules**: co instancja przyjmuje.
- **Outbound Control**: co instancja może wysyłać.
- **Blocked IPs**: analizator i audyt polityki.
- **Global Inbound**: polityka domyślna, GeoIP, ASN, Threat Shield i limit pakietów.

## Firewall chwilowo niedostępny

Jeśli usługa firewalla jest nieosiągalna, zakładka pokazuje **VoxiShield Connection Failure**.
Zapisane reguły pozostają aktywne, ale nie są wyświetlane ani edytowalne do czasu przywrócenia
usługi. To stan przejściowy; reguły nie zostały utracone.

Poczekaj i odśwież. Jeśli stan się utrzymuje, otwórz zgłoszenie z nazwą instancji i czasem
pierwszego wystąpienia. Nie reinstaluj systemu; stan jest przejściowy.

## Reguły przychodzące

Reguły są oceniane w kolejności wyświetlania. Każdy wiersz ma przełącznik włączania,
akcje edycji i usunięcia oraz informacje o trafieniach.

Aby dodać regułę:

1. Wybierz **Add Rule**.
2. Podaj **Rule Name** i opcjonalny **Description**.
3. Zbuduj **Match Expression**: opis poniżej.
4. Wybierz akcję: **Allow** lub **Drop**.
5. Zapisz. Panel potwierdza wysłanie reguły do VoxiShield.

### Wyrażenie dopasowania

Reguła to jedna lub więcej warunków połączonych **IF / AND / OR**. Dostępne pola to adres
źródłowy, protokół, port TCP/UDP, flagi TCP i rozmiar pakietu. Inspekcja zawartości pakietów
nie jest dostępna. Możesz dodać do **10 warunków** w regule.

Zacznij od konkretnego ruchu, którego potrzebujesz (`protokół` + `port` + `źródło`), i go
dozwól, a potem ustaw domyślną blokadę reszty. Reguły „dowolne źródło” na wrażliwych portach
to najczęstsza przyczyna zgłoszeń o nadużycia.

### Limity

Sekcja **Rate Limiting Regulations** dodaje limity per port:

- **Add Limit** tworzy regułę dla wskazanych portów.
- Ustaw próg i czas bana.
- Lista pokazuje, ile adresów jest obecnie zbanowanych przez dany limit.

Limity chronią przed brute force i zalewami żądań. Ustawiaj progi powyżej normalnych skoków,
zbyt niski limit banuje legalnych użytkowników.

Każde pole, akcja i wartość domyślna są opisane w
[Dokumentacji reguł](/pl/docs/security/firewall-rules/rule-reference/).

## Kontrola wychodząca

Reguły wychodzące dotyczą ruchu opuszczającego instancję:

- **SMTP Mail Block (Port 25)**: port 25 jest domyślnie blokowany, aby zapobiegać spamowi.
  Usunięcie blokady wymaga weryfikacji tożsamości; panel informuje, że odblokowanie wymaga
  **KYC identity verification**. Zobacz [Weryfikacja (KYC)](/pl/docs/account/verification/).
- **Restrict All Outgoing**: blokuje cały ruch wychodzący.
- **Outbound Custom Rules**: po zablokowaniu całego ruchu wychodzącego **Add Rule** pozwala
  dopuścić konkretne cele i porty.

Jeśli aplikacja nie wysyła poczty, najpierw sprawdź port 25. Relay na portach przesyłania
(587/465) nie jest objęty tą blokadą.

## Blocked IPs

Podzakładka **Blocked IPs** zawiera dwa narzędzia:

- **Firewall Block Analyzer**: wpisz adres IPv4 i wybierz **Analyze IP State**, aby zobaczyć, dlaczego
  jest blokowany i przez jaki mechanizm.
- **Security Policy Audit**: dla jednego adresu IP pokazuje, która z czterech warstw filtrów
  (limit, GeoIP, ASN, Threat Shield) go zablokowała lub przepuściła.

Użyj analizatora, zanim napiszesz do supportu o zablokowanym kliencie lub partnerze.

## Global Inbound

Ustawienia globalne dotyczą całego adresu:

- **Default Packet Policy**: co dzieje się z ruchem bez dopasowanej reguły. Do utwardzonej
  konfiguracji ustaw blokowanie.
- **GeoIP Country Filter**: zezwalanie lub blokowanie według kraju.
- **ASN Network Filter**: zezwalanie lub blokowanie gości według sieci, do której należy ich
  adres (ich dostawca internetu lub firma hostingowa).
- **Threat Shield**: filtrowanie reputacyjne znanych złośliwych źródeł.
- **Packet Rate Limiting**: globalny limit pakietów na sekundę dla adresu.

Filtry kraju i ASN są skuteczne, ale mało precyzyjne: blokada kraju odcina legalnych
użytkowników i roboty z tego kraju. Włączaj je świadomie i przeglądaj listę Blocked IPs.
