---
image: /assets/images/docs/pl/client-panel/og-image.png
title: Zarządzanie VPS
description: "Znajdź swoje instancje, odczytaj statusy, używaj sterowania zasilaniem i pracuj z zakładkami Overview, Settings i Danger Zone."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: client-panel
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Przegląd panelu

Strona Overview to strona główna panelu. Odpowiada na trzy pytania:

- **Monthly cost**: miesięczny odpowiednik kosztu wszystkich usług, w tym instancji
  godzinowych przeliczonych na pełny miesiąc.
- **Running**: ile instancji działa spośród wszystkich.
- **Next renewal**: najbliższa data i kwota odnowienia albo `Nothing due`, `Expired`
  lub `auto-renew off`, gdy odnowienie nie jest zaplanowane.

Karty KPI i lista usług należą do **aktywnej przestrzeni**, której nazwa jest na górnym pasku,
a na szerokich ekranach na górze paska bocznego. Konto prywatne zaczyna od jednej przestrzeni
Personal; firma lub szkoła może dodać własną, każda z osobnym portfelem i własnymi członkami.
Karta Recommendations dotyczy całego konta. Przełączanie, zapraszanie osób i zakres uprawnień
opisuje strona [Przestrzenie robocze](/pl/docs/account/workspaces/).

Poniżej kart KPI karta **Services** wyświetla **VPS Instances**. Databases, Kubernetes, Docker,
Object Storage, Load Balancers i Domains są oznaczone jako **Coming soon**. Karta
**Recommendations** podpowiada kolejne kroki: dodanie metody logowania, uzupełnienie
profilu, włączenie 2FA i odebranie kredytów powitalnych (przyznawanych po uzupełnieniu profilu
i podłączeniu metody logowania albo po weryfikacji tożsamości, zależnie od warunków).

Jeśli czeka nowa wersja dokumentu prawnego, panel otwiera stronę potwierdzenia zamiast tej,
dopóki jej nie zaakceptujesz. Opisuje to strona
[Dokumenty prawne i akceptacja](/pl/docs/account/legal/).

## Lista VPS

Otwórz **VPS Instances** w menu bocznym. Dwie zakładki rozdzielają modele rozliczenia:

- **Recurring Plans**: instancje miesięczne.
- **Hourly Billing**: instancje godzinowe.

Każda karta pokazuje status, nazwę instancji, zużycie CPU/RAM/dysku, publiczny IPv4 (lub
`Pending IP...`, gdy adres jest przydzielany) oraz parametry planu. Kliknij kartę lub nazwę,
aby otworzyć instancję. Lista odświeża się automatycznie, więc zmiany statusu widać bez
przeładowania strony.

Kafelek **Deploy a VPS Instance** otwiera formularz wdrożenia opisany w
[Wdrażanie VPS](/pl/docs/platform/deploy-vps/).

## Statusy instancji

| Status | Znaczenie |
|---|---|
| `queue` | Wdrożenie przyjęte, oczekuje na hosta |
| `installing` | Trwa instalacja systemu operacyjnego |
| `running` | Instancja działa i jest osiągalna |
| `stopped` | Instancja jest wyłączona |
| `reinstalling` | Trwa reinstalacja systemu; wszystkie dane są zastępowane |
| `restoring` | Trwa przywracanie kopii; instancja jest zatrzymana, dane nadpisywane |
| `error` | Ostatnia operacja nie powiodła się; otwórz instancję lub zgłoś problem |
| `suspended` | Zawieszenie rozliczeniowe lub regulaminowe; przy niespodziewanym stanie napisz do supportu |
| `deleted` | Instancja jest usuwana |

Długotrwałe stany `queue`, `installing` lub `error` zwykle oznaczają problem z pojemnością
albo hostem. Przy `error` otwórz instancję i zanotuj treść statusu oraz strefę. Przy
`suspended` sprawdź najpierw
[zasady przedpłaty i zawieszenia](/pl/docs/billing/payments/); jeśli doładowanie zostało już
opłacone, otwórz zgłoszenie z nazwą instancji i czasem zatrzymania.

## Sterowanie zasilaniem

**Start**, **Restart** i **Stop** są dostępne w nagłówku instancji oraz na kartach listy.

- **Start** uruchamia zatrzymaną instancję.
- **Restart** restartuje system. Wymaga potwierdzenia, bo instancja zostanie na chwilę wyłączona.
- **Stop** wyłącza instancję. Wymaga potwierdzenia; działające usługi zatrzymują się od razu.

Akcje zasilania są niedostępne, gdy trwa operacja, np. `installing` lub `restoring`.
Zatrzymanie instancji nie wstrzymuje rozliczenia planów miesięcznych; instancje godzinowe
rozliczają się zgodnie z zasadami opisanymi w [Rozliczeniu godzinowym](/pl/docs/billing/hourly/).

## Przedłużenie, auto-renew i cykl rozliczeniowy

Zakładka Overview to strona domowa instancji:

- **Resource Usage**: bieżące wskaźniki CPU, RAM i dysku.
- **Instance Details**: lokalizacja, strefa, parametry, sieć i data utworzenia.
- **Billing & Subscription**: bieżący **Billing Scheme** (po wybraniu zmienia cykl
  rozliczeniowy; bezpłatnie, obowiązuje od następnego odnowienia), **Next Renewal** z akcją
  **Extend Instance**, koszt odnowienia lub stawka godzinowa oraz przełącznik **Auto-Renew**.

Pozostałe zakładki opisują osobne strony:
[Konsola, SSH i RDP](/pl/docs/platform/console-access/),
[Metryki](/pl/docs/platform/metrics/), [Sieć](/pl/docs/platform/networking/),
[Reguły firewalla](/pl/docs/security/firewall-rules/) i
[Kopie zapasowe](/pl/docs/platform/client-panel/snapshots/).

## Ustawienia

Zakładka **Settings** zawiera jedno ustawienie: **Instance Name**, które aktualizuje też
hostname widoczny w panelu. Wybierz **Save**, aby zapisać. Zmiana systemu operacyjnego jest
w strefie ryzyka, nie tutaj.

## Strefa ryzyka

**Danger Zone** zawiera nieodwracalne akcje:

- **Reinstall Operating System**: wybierz nową rodzinę i wersję systemu oraz nowe hasło
  roota. Wszystkie dane na instancji zostaną usunięte. Zobacz
  [Systemy operacyjne](/pl/docs/platform/operating-systems/).
- **Destroy Instance**: dostępne dla instancji godzinowych. Musisz wpisać nazwę instancji,
  aby potwierdzić. Usunięcie jest trwałe; jeśli dane mogą być potrzebne, najpierw zrób kopię.

Dla instancji miesięcznych nie ma samodzielnego usuwania. Wyłącz **Auto-Renew** w zakładce
Overview i pozwól instancji wygasnąć; wygasła instancja zostaje zawieszona, a po 7-dniowym
okresie łaski trwale usunięta wraz z danymi.
