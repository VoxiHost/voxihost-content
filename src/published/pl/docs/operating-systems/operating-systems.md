---
image: /assets/images/docs/pl/operating-systems/og-image.png
title: Systemy operacyjne
description: "Dostępne szablony systemów, płatne licencje, reinstalacja instancji i co oznacza niezarządzany VPS."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: operating-systems
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Dostępne szablony

Formularz wdrożenia wyświetla systemy operacyjne według rodziny i wersji. Lista aktywnych
szablonów jest globalna i dostępna w każdej strefie.

Wiążąca jest lista w panelu: szablony i wersje są dodawane i wycofywane, dlatego ta strona
celowo nie zamraża listy wersji. Jeśli brakuje potrzebnego systemu lub wersji, użyj linku do
zgłoszenia w formularzu wdrożenia.

## Szablony Windows i licencje

Szablony Windows są udostępniane z **180-dniową licencją ewaluacyjną**. VoxiHost nie sprzedaje
ani nie odnawia licencji Windows: po okresie ewaluacji aktywuj lub przedłuż licencję
u Microsoftu (lub u swojego resellera).

Jeśli Windows ma działać długoterminowo, zaplanuj koszt licencji osobno. VoxiHost jest
dostawcą infrastruktury i nie weryfikuje licencji klientów; jeśli uprawniony podmiot zgłosi
naruszenie, usługa może zostać zawieszona do wyjaśnienia statusu licencji.

## Reinstalacja systemu operacyjnego

Potrzebujesz zatrzymanej instancji i, jeśli dane mogą być potrzebne, kopii zapasowej.
Reinstalacja to destrukcyjne działanie ratunkowe, a nie naprawa:

1. Najpierw zatrzymaj instancję. Reinstalacja jest odrzucana, gdy instancja działa.
2. Otwórz instancję i przejdź do zakładki **Danger Zone**.
3. Wybierz **Reinstall**.
4. Wskaż nową rodzinę i wersję systemu oraz ustaw nowe **Root Password**.
5. Potwierdź ostrzeżenie o utracie danych.

Instancja przechodzi w `reinstalling`, na chwilę wraca do `queue`, potem `installing`, a kończy
jako `running`. Cały dysk jest zastępowany. Reinstalacja to właściwe narzędzie, gdy chcesz
czysty system lub inną dystrybucję; nie służy do odzyskiwania plików. Jeśli dane są potrzebne,
najpierw zrób kopię, zobacz
[Kopie zapasowe i snapshoty](/pl/docs/platform/client-panel/snapshots/).

## Co oznacza „unmanaged”

VoxiHost dostarcza instancję i jej sieć. Wewnątrz systemu operacyjnego po Twojej stronie są:

- Aktualizacje zabezpieczeń i uaktualnienia wersji systemu.
- Użytkownicy, klucze SSH, sudo i uwierzytelnianie.
- Zainstalowane usługi, ich konfiguracja i bezpieczeństwo.
- Kopie danych aplikacji (oprócz kopii instancji).
- Reguły firewalla dla wystawionych portów.

Nie aktualizujemy ani nie zabezpieczamy oprogramowania w Twoim serwerze.
Jeśli usługa zostanie przejęta, instancję odbudowujesz samodzielnie. Wiele z tych zadań opisuje sekcja
`/pl/guides/`, na przykład
[Jak zainstalować Nginx na Ubuntu i Debian](/pl/guides/instalacja-nginx-ubuntu-debian/) oraz
[Jak zabezpieczyć SSH na Ubuntu i Debian](/pl/guides/jak-zabezpieczyc-ssh-ubuntu-debian/).

## Zgodność szablonów

- Ubuntu i Debian mają najszersze pokrycie poradnikami na tej stronie; AlmaLinux, Rocky Linux
  i obrazy zgodne z CentOS zapewniają środowiska zgodne z RHEL.
- Dostępne są wydania LTS (long-term support) i stabilne oraz starsze wersje dla zgodności.
- Strefy i plany bez wolnych miejsc są wyszarzone w formularzu; sama lista szablonów
  systemów jest globalna.

Po pierwszym uruchomieniu połącz się przez konsolę lub SSH. Zobacz
[Konsola, SSH i RDP](/pl/docs/platform/console-access/).
