---
image: /assets/images/docs/pl/workspaces/og-image.png
title: Przestrzenie robocze
description: "Prowadź usługi dla siebie, firmy lub szkoły w osobnych przestrzeniach, zapraszaj współpracowników i decyduj, co każdy z nich może robić."
date: '2026-11-10'
updated: '2026-11-10'
translationKey: workspaces
locale: pl
status: published
section: docs
group: account
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---

## Czym jest przestrzeń robocza

Przestrzeń robocza (workspace) przechowuje usługi, portfel oraz osoby, które mogą
z nich korzystać. Każde konto zaczyna od jednej przestrzeni **Personal**, która jest
domyślna i nie da się jej usunąć. Gdy usługi należą do firmy lub szkoły, a nie do
Ciebie jako osoby, dodaj przestrzeń **Business** albo **Education**.

Rozdzielenie ich ma znaczenie z trzech powodów:

- **Pieniądze**: każda przestrzeń ma własne saldo kredytów. Doładowanie w jednej
  nie zasila drugiej.
- **Dokumenty**: faktury i paragony zawierają dane nabywcy tej przestrzeni, która
  zapłaciła, więc faktura firmowa nie trafi pod zakup prywatny.
- **Reżim prawny**: przestrzeń firmowa przyjmuje Umowę powierzenia przetwarzania
  danych (DPA), a prywatna nie.

Przestrzeń, w której pracujesz, jest widoczna na górnym pasku, a na szerokich
ekranach na górze paska bocznego; na telefonie otwórz pasek boczny. Od niej zależy
wszystko dalej: lista usług, portfel, faktury i członkowie.

## Przełączanie przestrzeni

Wybierz nazwę przestrzeni i wskaż inną z listy. Panel ponownie wczyta dane dla tej
przestrzeni. Wybór jest pamiętany na tym urządzeniu, a odebrane członkostwo
przestaje działać natychmiast.

## Tworzenie przestrzeni

Otwórz przełącznik przestrzeni, wybierz **Manage workspaces**, a następnie **New
workspace**. Wskaż typ, nadaj nazwę i potwierdź przyciskiem **Create workspace**.
Nowa przestrzeń zaczyna z pustym portfelem, bez usług, z Tobą jako właścicielem.

Przestrzeń **Business** i **Education** powstaje zablokowana: przed jej otwarciem
trzeba ukończyć weryfikację firmy lub ucznia, a panel prowadzi do niej wprost.
Przestrzeń edukacyjna zawsze nosi nazwę **Education**, żeby nie mogła podszyć się
pod konkretną szkołę; instytucja jest częścią weryfikacji, nie nazwy.

## Członkowie i role

Przestrzenią firmową, której jesteś właścicielem, możesz się dzielić. Otwórz ją,
przejdź do **Members** i wybierz **Invite member**. Zaproszenie wymaga adresu,
który ma już konto VoxiHost, a wiersz pojawia się od razu z etykietą **Invited**
do momentu przyjęcia. Przestrzenie edukacyjne są przypisane do jednego ucznia i nie
przyjmują zaproszeń.

Każdy członek ma rolę, a dodatkowo zestaw **uprawnień**. Rola to punkt wyjścia;
właściciel decyduje, co dana osoba naprawdę może robić.

| Rola | Podstawa |
|---|---|
| Viewer | Podgląd zgłoszeń |
| Member | Podgląd, otwieranie i odpowiadanie na zgłoszenia |
| Billing | Portfel i faktury oraz zgłoszenia |
| Admin | Usługi, rozliczenia, członkowie i ustawienia, bez usuwania przestrzeni |
| Owner | Wszystko, łącznie z usunięciem przestrzeni |

Uprawnienia, które możesz przyznać lub odebrać każdemu członkowi:

| Uprawnienie | Co pozwala |
|---|---|
| Create services | Wdrażanie nowych usług w tej przestrzeni |
| Power | Uruchamianie, zatrzymywanie i restart usług |
| Destroy | Trwałe usuwanie usług |
| View billing | Wgląd w portfel, płatności i faktury |
| Add funds | Zasilenie portfela przestrzeni |
| Request invoices | Prośba o fakturę VAT |
| Request refunds | Prośba o zwrot za usługę |
| Manage members | Zapraszanie, zmiana ról i usuwanie członków |
| Edit settings | Nazwa, dane prawne i adres do powiadomień |
| Delete workspace | Trwałe usunięcie przestrzeni |
| View tickets | Czytanie zgłoszeń w tej przestrzeni |
| Open tickets | Zakładanie nowego zgłoszenia |
| Reply and close | Odpowiadanie, zamykanie i ponowne otwieranie zgłoszeń |

Właściciel zachowuje wszystkie uprawnienia. Rola nigdy nie daje czegoś, czego
właściciel odebrał, a odebranie uprawnienia działa od razu dla tej osoby.

## Portfel przestrzeni

Kredyty należą do przestrzeni, nie do osoby, która je dodała. Strona **Billing**
pokazuje saldo aktywnej przestrzeni; tam trafiają doładowania, kredyty bonusowe i
zwroty. Po przełączeniu przestrzeni saldo zmienia się razem z nią.

Automatyczne odnowienia są pobierane z portfela przestrzeni, do której należy
usługa, więc usługa nigdy nie odnowi się ze środków innej przestrzeni.

## Dane firmy

Przestrzeń firmowa ma zakładkę **Company** z danymi prawnymi, adresem do faktur i
adresem e-mail do powiadomień. Nazwa prawna, NIP i adres są zapisywane zaszyfrowane;
widzą je członkowie przestrzeni, którzy otworzą zakładkę, a nasz zespół tylko w
zakresie potrzebnym do obsługi konta.

Utrzymuj je aktualne: prośba o fakturę kopiuje dane zapisane w tej chwili, a
późniejsza poprawka nie przepisuje już wystawionego dokumentu.

## Nagrody

Przestrzeń edukacyjna ma zakładkę **Rewards** z saldem bonusowym, kwotą zdobytą w
tym roku, podstawą miesięczną i datą najbliższego wygaśnięcia. Przestrzenie
firmowe i prywatne nie mają tej zakładki; ich kredyty bonusowe są widoczne w
**Billing**.

Kredyty bonusowe są oddzielone od płatnych i mogą wygasać. Przy obciążeniu są
zużywane przed płatnymi, więc bonus nie czeka niewykorzystany do wygaśnięcia.

## Strefa niebezpieczna

Zakładka **Danger zone** usuwa przestrzeń. Odmawia, dopóki przestrzeń ma usługi
(także wygasłe), innego członka, otwartą prośbę o fakturę lub zwrot albo saldo
większe od zera. Usunięcie jest trwałe: członkowie tracą dostęp, a zgłoszenia i
dokumenty pozostają u osób, które potrzebują ich dla księgowości i celów prawnych.

Właściciel może też przekazać to uprawnienie administratorowi. Przestrzeń Personal
nigdy nie pojawia się w tej zakładce.

## Limity

Każde konto ma jedną przestrzeń Personal i do pięciu dodatkowych przestrzeni
firmowych lub edukacyjnych łącznie. Po osiągnięciu limitu akcja **New workspace**
nie jest już proponowana, a panel wyjaśnia dlaczego.
