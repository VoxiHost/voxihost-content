---
image: /assets/images/docs/pl/rule-reference/og-image.png
title: Dokumentacja reguł firewalla
description: "Wszystkie pola firewalla: warunki dopasowania, akcje, limity, polityki globalne, filtry GeoIP/ASN i wyniki analizatora."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: rule-reference
locale: pl
status: published
section: docs
group: security
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Anatomia reguły

Ta strona to dokumentacja dla administratorów firewalla. Jeśli chcesz tylko otworzyć port,
zacznij od [Reguł firewalla](/pl/docs/security/firewall-rules/).

Każda reguła przychodząca ma te same części:

| Część | Wymagane | Cel |
|---|---|---|
| **Rule Name** | Tak | Czytelna nazwa w tabeli reguł |
| **Description** | Nie | Dlaczego reguła istnieje; przydatne po miesiącach |
| **Match Expression** | Tak | Warunki wybierające ruch |
| **Action** | Tak | **Allow** lub **Drop** |

Reguły są oceniane w kolejności w tabeli. Pierwsza dopasowana reguła decyduje o wyniku;
ruch bez dopasowania trafia do globalnej polityki domyślnej. Regułę możesz wyłączyć bez
usuwania: to bezpieczniejsze niż edycja w trakcie incydentu.

## Warunki dopasowania

Wyrażenie łączy do **10 warunków** operatorami **IF / AND / OR**.

| Pole | Co dopasowuje | Typowe użycie |
|---|---|---|
| **Source IP** | Adres lub sieć zdalna | Dopuść tylko biuro lub VPN |
| **Protocol** | Protokół transportowy, np. TCP lub UDP | TCP dla serwera WWW, UDP dla gry |
| **TCP/UDP Port** | Port lub zakres portów | Otwórz 443, 22 lub zakres gry |
| **TCP Flags** | Kombinacje flag TCP | Zaawansowane filtrowanie (np. SYN) |
| **Packet Size** | Długość pakietu w bajtach | Odrzucanie nietypowo dużych lub małych pakietów |

Wskazówki:

- Preferuj protokół + port + źródło. Szerokie „dowolne źródło, dowolny port” niweczy sens.
- **AND** zawęża, **OR** rozszerza i łatwo się pomylić.
- Inspekcja zawartości pakietów nie jest dostępna: reguły dopasowują adresy, protokoły, porty,
  flagi TCP i rozmiar pakietu, a nie zawartość pakietu.
- Trzymaj reguły małe i nazwane; dziesięć warunków w jednej regule trudno zweryfikować.

Kreator waliduje wartości na bieżąco. Jeśli wartość jest odrzucana, formularz podaje
akceptowany format pola.

## Akcje przychodzące

| Akcja | Efekt |
|---|---|
| **Allow** | Przepuszcza pasujący ruch |
| **Drop** | Po cichu odrzuca ruch |

Preferuj **Drop** zamiast jawnego odrzucenia: nadawca niczego się nie dowiaduje, co jest
właściwym domyślnym zachowaniem dla wystawionych usług.

## Pola limitów

Limity definiuje się dla zestawu portów docelowych:

| Pole | Znaczenie |
|---|---|
| **Target ports** | Porty objęte limitem |
| **Threshold** | Liczba żądań lub pakietów w interwale uruchamiająca limit |
| **Ban duration** | Jak długo adres sprawcy pozostaje zablokowany |
| **Banned now** | Tylko do odczytu: liczba aktualnie zbanowanych adresów |

Ustaw próg powyżej normalnych skoków, w tym legalnych ponowień i testów kondycji. Ban łapiący
prawdziwych użytkowników widać potem jako zablokowany legalny ruch w analizatorze.

## Kontrola wychodząca

| Ustawienie | Efekt |
|---|---|
| **SMTP Mail Block (Port 25)** | Blokuje wychodzący port 25 do czasu zatwierdzenia weryfikacji |
| **Restrict All Outgoing** | Blokuje ruch wychodzący; własne reguły ponownie dopuszczają wybrane |
| **Outbound Custom Rules** | Reguły zezwoleń per cel, dostępne po zablokowaniu całego ruchu |

Wyjątki wychodzące mają prostszy formularz: wybierasz protokół (TCP, UDP, ICMP lub wszystkie),
port docelowy i opcjonalny cel. Nie używa się do nich edytora warunków przychodzących.

## Pola globalne

| Ustawienie | Znaczenie | Bezpieczny start |
|---|---|---|
| **Default Packet Policy** | Wynik dla ruchu bez dopasowanej reguły | **Default Drop** |
| **GeoIP Country Filter** | Zezwalanie lub blokowanie całych krajów | Wyłączone, dopóki nie ma powodu |
| **ASN Network Filter** | Zezwalanie lub blokowanie sieci według ASN | Wyłączone; dla znanych sieci nadużyć |
| **Threat Shield** | Blokowanie źródeł o złej reputacji | Włączone |
| **Packet Rate Limiting** | Globalny limit pakietów na sekundę dla adresu | Powyżej normalnego szczytu, jeśli potrzebny |

Blokada kraju lub ASN dotyczy każdego użytkownika z tej sieci, w tym własnego monitoringu
i partnerów. Po zmianie przejrzyj listę Blocked IPs.

## Kolejność i wartości domyślne

1. Reguły przychodzące są sprawdzane w kolejności tabeli; pierwsze dopasowanie wygrywa.
2. Jeśli nic nie pasuje, decyduje **Default Packet Policy**.
3. Limity są oceniane niezależnie i mogą zbanować adres nawet przy regule Allow.
4. Kontrola wychodząca jest niezależna od reguł przychodzących.
5. GeoIP, ASN, Threat Shield i limit pakietów działają poza Twoimi regułami, więc pakiet może
   zostać odrzucony, zanim dotrze do reguły Allow.

## Firewall Block Analyzer

Wpisz adres IPv4 i wybierz **Analyze IP State**. Analizator pokazuje, która warstwa filtrów
wpłynęła na adres:

| Wynik | Znaczenie |
|---|---|
| Nazwa limitu | Limit zbanował adres |
| GeoIP | Filtr kraju wpłynął na adres |
| ASN | Filtr sieci wpłynął na adres |
| Threat Shield | Filtrowanie reputacyjne wpłynęło na adres |

Użyj analizatora przed otwarciem zgłoszenia. Jeśli żadna z tych warstw nie wyjaśnia blokady,
otwórz zgłoszenie z adresem i czasem testu.

## Security Policy Audit

Audyt pokazuje dla jednego adresu IP, która z czterech warstw filtrów (limit, GeoIP, ASN,
Threat Shield) go zablokowała lub przepuściła. Służy do potwierdzenia przyczyny dla
konkretnego użytkownika, a nie do skanowania konfiguracji.
