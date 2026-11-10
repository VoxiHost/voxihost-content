---
image: /assets/images/docs/pl/deploy-vps/og-image.png
title: Wdrażanie VPS
description: "Wszystkie opcje wdrożenia VPS - region i strefa, plan, cykl rozliczeniowy, system operacyjny, dodatki i błędy."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: deploy-vps
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Zanim wdrożysz

Potrzebujesz salda kredytów pokrywającego **Total Due**, menedżera haseł na hasło roota oraz
opcjonalnego klienta SSH; konsola w przeglądarce działa bez instalacji.

Formularz wdrożenia pobiera pierwszy okres z salda kredytów od razu. Upewnij się, że
saldo pokrywa **Total Due** z podsumowania zamówienia; jeśli nie, formularz pokaże
**Top up balance** zamiast wdrożenia.

Trzy rzeczy mogą zatrzymać wdrożenie, zanim sprawdzona zostanie pojemność strefy:

- Za niskie saldo.
- Osiągnięty limit konta lub zasobów (jeśli potrzebujesz więcej instancji, napisz do
  supportu).
- Nieprawidłowy system operacyjny, hostname lub hasło.

Instancje **Monthly** są opłacane za cykl rozliczeniowy i mogą korzystać z dodatków,
kodów promocyjnych oraz sieci prywatnej. Instancje **Hourly** są przedpłacane w miarę
działania, konfiguruje się je suwakami zasobów zamiast kart planów i nie obsługują
dodatków. Porównanie modeli: [Rozliczenie godzinowe](/pl/docs/billing/hourly/).

## Region i strefa

Najpierw wybierz **Region**, potem **Zone** w jego obrębie. Strefa to miejsce fizycznego
uruchomienia instancji; panel używa jej również do sprawdzania wolnych miejsc.

- Strefy bez wolnych miejsc są wyszarzone wraz z wyjaśnieniem.
- Jeśli w wybranej strefie zabraknie miejsca dla wybranego poziomu (tier), formularz zgłosi
  brak pojemności i zaproponuje zgłoszenie do supportu.
- Regiony i strefy są dodawane z czasem. Wiążąca jest lista w formularzu: ta strona
  celowo nie zamraża nazw, które się zmieniają.

## Wybierz plan

Oba plany działają na tym samym sprzęcie AMD Ryzen 9 7950X3D i tej samej pamięci NVMe.
Różnica polega na tym, ile czasu CPU, pamięci i I/O dysku platforma gwarantuje instancji.

| | **Budget** | **Premium** |
|---|---|---|
| **Czas CPU** | Ograniczony do 50% przydzielonego vCPU, standardowy priorytet | Bez limitu czasu CPU, wysoki priorytet |
| **Pamięć** | 25% gwarantowane, burst do 100% | 95% gwarantowane, burst do 100% |
| **Sieć** | 100 Mbps na instancję | 1 Gbps na instancję |
| **I/O dysku** | Limity IOPS i przepustowości na instancję | Brak limitów na instancję |

Każda instancja ma własny limit przepustowości sieci. Premium rezerwuje więcej czasu CPU
i zapasu pamięci dla Twojego obciążenia.

Plan jest ustalany przy wdrożeniu. Planu nie można zmienić bez ponownego wdrożenia, więc wybierz go pod
oczekiwany czas życia obciążenia; zmiana oznacza wdrożenie nowej instancji.

Plan decyduje też o dostępnych kartach i strefach.

## Plan i cykl rozliczeniowy

Dla instancji **Monthly** karty planów pokazują RAM, vCPU, NVMe i sieć, a plany wyprzedane
są wyszarzone. Plakietka **Popular** wyróżnia najczęściej wybierany plan.

Krok **Billing Cycle** proponuje dłuższe, przedpłacone cykle z plakietką **Save X%** albo
**No discount** dla najkrótszego cyklu.

Dla instancji **Hourly** zamiast kart planów pojawiają się suwaki **Processors**,
**Memory** i **Storage**. Panel pokazuje **Hourly Rate**, przybliżony koszt miesięczny,
a gdy konfiguracja odpowiada standardowemu planowi: propozycję przejścia na tańszy
**Monthly Plan**.

Wiążące są aktualne ceny, nazwy planów i rabaty w panelu.

## System operacyjny

1. Wybierz rodzinę systemu, a następnie **Version**.
2. Jeśli szablon ma dopłatę licencyjną, pojawia się ona w podsumowaniu zamówienia. Szablony
   Windows są **180-dniowymi wersjami ewaluacyjnymi**: przedłużenie licencji odbywa się
   u Microsoftu, nie przez VoxiHost.
3. Jeśli brakuje szablonu, użyj linku do zgłoszenia i zaproponuj system lub wersję.

VPS jest niezarządzany (unmanaged): aktualizacje, użytkownicy i konfiguracja usług
w systemie należą do Ciebie. Reinstalacja i znaczenie „unmanaged”:
[Systemy operacyjne](/pl/docs/platform/operating-systems/).

## Hostname i hasło roota

- **Hostname**: co najmniej 3 znaki: litery, cyfry i myślniki. Staje się nazwą instancji
  w panelu i domyślnym hostname systemu. Możesz użyć generatora losowego.
- **Root Password**: wygeneruj hasło albo wpisz własne. Formularz pokazuje siłę hasła
  i pozwala je podejrzeć. Skopiuj je przed wdrożeniem; te same dane są później widoczne
  w karcie **Credentials** instancji.

Używaj menedżera haseł. Słabe hasło roota to najczęstsza droga do przejęcia
niezarządzanego serwera.

## Dodatki

Dodatki są oferowane wyłącznie dla instancji **Monthly**.

| Dodatek | Co daje | Uwagi |
|---|---|---|
| **Private Network** | Prywatny adres w sieci wewnętrznej strefy | Bezpłatny; wybierz adres i **Speed** |
| **Extra IPv4 Address** | Dodatkowe publiczne adresy IPv4 | 1-5 na wdrożenie, płatne |
| **IPv6 Addresses** | Dodatkowe adresy IPv6 | 1-5 na wdrożenie; pierwszy bezpłatny, kolejne płatne |
| **Automatic Backups** | Cotygodniowe automatyczne snapshoty | Płatne; dostępne później w zakładce Backups |

Adresy i sieć prywatną zmienisz po wdrożeniu w zakładce **Network**, ale adresy ponad
limity formularza wymagają kontaktu z supportem. Zobacz
[Adresy IP](/pl/docs/platform/networking/ip-addressing/) i
[Sieć](/pl/docs/platform/networking/).

## Podsumowanie zamówienia, kod promocyjny i oświadczenie

**Order Summary** po prawej stronie wymienia typ, region, strefę, plan lub zasoby, system,
dodatki, cenę cykliczną lub godzinową, rabaty i końcowe **Total Due**.

- **Promo Code**: wpisz kod i wybierz **Apply**. Nieprawidłowe lub wygasłe kody są
  odrzucane w miejscu.
- **Insufficient balance**: podsumowanie ostrzega i linkuje do **Top up balance**.
- **Oświadczenie prawne**: przed wdrożeniem musisz zaakceptować checkbox dotyczący
  natychmiastowego wykonania usługi i zrzeczenia się prawa odstąpienia.
- **Deploy Now**: wysyła zamówienie. Przycisk zmienia się w **Deploying…** w trakcie.

## Deploy Now i co dalej

Udane wdrożenie wraca do listy **VPS Instances**. Nowa instancja zaczyna jako `queue`,
przechodzi w `installing`, a kończy jako `running`; lista odświeża się automatycznie.
Instancję możesz otworzyć od razu: zakładka Overview pokazuje zasoby, gdy pojawią się dane o zasobach
je raportować.

Jeśli instancja długo pozostaje w `queue` albo kończy w `error`, otwórz zgłoszenie
z nazwą instancji, strefą i widocznym statusem.

## Błędy wdrożenia

| Komunikat lub stan | Znaczenie | Co zrobić |
|---|---|---|
| Insufficient balance | Kwota do zapłaty przekracza saldo | Doładuj kredyty i spróbuj ponownie |
| Duplicate hostname | Inna instancja na Twoim koncie używa tego hostname | Wybierz unikalny hostname |
| Active-instance limit | Konto osiągnęło limit instancji (domyślnie 10) | Usuń nieużywane instancje godzinowe, pozwól wygasnąć miesięcznym lub poproś support o wyższy limit |
| No capacity | Plan nie mieści się w wybranej strefie | Wybierz inną strefę lub region |
| Invalid hostname / password | Wartość nie spełnia reguł formularza | Popraw hostname; formularz pokazuje siłę hasła i odrzuca hasła poniżej najwyższej oceny |
| Invalid operating system | Szablon jest niedostępny | Wybierz inną wersję lub zaproponuj ją w zgłoszeniu |
