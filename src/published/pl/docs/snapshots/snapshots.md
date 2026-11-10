---
image: /assets/images/docs/pl/snapshots/og-image.png
title: "Kopie zapasowe i snapshoty"
description: "Twórz, weryfikuj, przywracaj i usuwaj kopie instancji oraz sprawdź, co obejmuje dodatek Automatic Backups."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: snapshots
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Jak działają kopie

Potrzebujesz dodatku **Automatic Backups** (kopie zaplanowane) albo wolnych miejsc na kopie
ręczne. Ręczne kopie są ograniczone do czterech na instancję.

Kopiami zarządzasz dla każdej instancji w zakładce **Backups**. Istnieją dwa rodzaje:

- **Kopie ręczne**: snapshoty tworzone na żądanie, maksymalnie cztery na instancję.
- **Kopie automatyczne**: cotygodniowe snapshoty w niedziele, gdy aktywny jest dodatek
  **Automatic Backups**.

Przywrócenie zawsze zatrzymuje instancję i nadpisuje jej bieżące dane snapshotem. Kopie
obejmują całą instancję, a nie pojedyncze pliki; nie zastępują eksportu danych z aplikacji.

Instancje godzinowe nie obsługują kopii: zakładka pokazuje **Backups Unavailable**.
VoxiHost nadal wykonuje systemowe kopie disaster recovery na potrzeby platformy, ale nie
możesz tworzyć ani przywracać własnych snapshotów. Jeśli ich potrzebujesz, przenieś obciążenie
na plan miesięczny.

## Utwórz ręczną kopię

1. Otwórz instancję i wybierz **Backups**.
2. Wybierz **Create Backup**. Przycisk zmienia się w **Creating...** na czas tworzenia snapshotu.
3. Nowy wpis pojawia się ze znacznikiem czasu i stanem weryfikacji.

Każda ręczna kopia zajmuje jedno z czterech miejsc. Usuń stary snapshot przed utworzeniem
piątego. Tworzenie kopii nie zatrzymuje instancji.

## Stany weryfikacji

- **Pending Verification**: snapshot istnieje, ale nie został jeszcze zweryfikowany.
- **Verified Snapshot**: snapshot przeszedł weryfikację i jest najbezpieczniejszym punktem
  przywracania.

Przywracaj zweryfikowane snapshoty. Jeśli kopia długo pozostaje w stanie pending, otwórz
zgłoszenie z nazwą instancji i znacznikiem czasu kopii.

## Przywróć kopię

1. Wybierz **Restore Backup** przy snapshocie **Verified Snapshot**. Snapshoty pending muszą
   najpierw przejść weryfikację; **Restore** i **Delete** pojawiają się tylko przy zweryfikowanych.
2. Potwierdź ostrzeżenie: instancja zostanie zatrzymana, a **wszystkie bieżące dane
   nadpisane**.
3. Instancja przechodzi w `restoring`. Po zakończeniu pozostaje w `stopped`; uruchom ją
   ponownie.

Przywracanie jest destrukcyjne. Jeśli potrzebujesz danych z bieżącego stanu, najpierw zrób
ręczną kopię, pamiętając o limicie czterech miejsc.

## Usuń kopię

Wybierz **Delete Backup** i potwierdź. Usunięcie jest trwałe i zwalnia miejsce na ręczną kopię.

## Dodatek Automatic Backups

Dodatek jest dostępny dla instancji miesięcznych. Gdy jest aktywny:

- Kopie wykonują się automatycznie w każdą niedzielę.
- Zakładka Backups pokazuje automatyczne snapshoty obok ręcznych.
- Wyłączenie dodatku zatrzymuje przyszłe automatyczne kopie; istniejące snapshoty pozostają
  do momentu ich usunięcia.

Jeśli dodatek nie jest aktywny, zakładka pokazuje **Backup Addon Required** z akcją
**Enable backups**. Włączenie uruchamia płatny dodatek na instancji.

Kopie chronią dysk instancji. Nie chronią konta VoxiHost: włącz 2FA i trzymaj osobne kopie
wszystkiego, czego nie da się odtworzyć.
