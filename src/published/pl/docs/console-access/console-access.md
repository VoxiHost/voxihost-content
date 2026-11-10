---
image: /assets/images/docs/pl/console-access/og-image.png
title: "Konsola, SSH i RDP"
description: "Połącz się z VPS przez konsolę VNC, SSH lub Remote Desktop i znajdź dane dostępowe ustawione przy wdrożeniu."
date: '2026-10-27'
updated: '2026-10-27'
translationKey: console-access
locale: pl
status: published
section: docs
group: platform
author:
  name: VoxiHost Team
  link: https://voxihost.pl/
---


## Przed połączeniem

- Instancja musi mieć status `running`.
- Potrzebujesz hasła roota ustawionego przy wdrożeniu albo klucza SSH, który sam zainstalujesz.
- Do SSH potrzebujesz terminala: Terminal w macOS/Linux, PuTTY lub Windows Terminal
  w Windows. **SSH** to tekstowy sposób sterowania serwerem z Twojego komputera.

## Konsola VNC

VNC to zdalny ekran w przeglądarce: pokazuje pulpit serwera i przekazuje Twoje klawisze, jak
zdalne sterowanie monitorem.

Zakładka **Console** daje ekran i klawiaturę nawet wtedy, gdy sieć lub SSH nie działają.

1. Otwórz instancję i wybierz **Console**.
2. Wybierz **Connect to Console**. Przycisk pokazuje **Connecting...** podczas łączenia.
3. Pracuj w sesji VNC; użyj trybu pełnoekranowego dla większego widoku i wklejania tekstu,
   np. długiego hasła roota.

Konsola łączy się tylko wtedy, gdy instancja ma status `running`. Jeśli jest zatrzymana,
najpierw ją uruchom. Konsola to droga ratunkowa przy błędnej regule firewalla lub zepsutej
konfiguracji SSH: nie zależy od osiągalności sieci wewnątrz systemu.

## Dane dostępowe instancji

Zakładka Console pokazuje też **Instance Credentials**: domyślnego użytkownika i hasło
ustawione przy wdrożeniu. Użyj opcji podejrzenia i kopiowania, aby uniknąć błędów przepisywania.

Jeśli zmienisz hasło roota w systemie, kopia w panelu będzie nieaktualna. Przechowuj własne
dane dostępowe w menedżerze haseł.

## Dostęp SSH

Szablony linuksowe są dostępne przez SSH z publicznym adresem IPv4:

```bash
ssh root@<public-ip>
```

Panel **Access Methods** w zakładce Console pokazuje dokładne polecenie i przycisk kopiowania
go. Uwierzytelniaj się hasłem roota z wdrożenia albo kluczem, który sam zainstalujesz.

Zalecane praktyki:

- Utwórz użytkownika sudo innego niż root i wyłącz logowanie hasłem, gdy klucze zadziałają.
- Do potwierdzenia dostępu kluczem pozostaw logowanie roota przez konsolę.
- Otwórz port 22 tylko dla używanych adresów; zobacz
  [Reguły firewalla](/pl/docs/security/firewall-rules/).
- Skorzystaj z [Jak zabezpieczyć SSH na Ubuntu i Debian](/pl/guides/jak-zabezpieczyc-ssh-ubuntu-debian/)
  lub [Jak zabezpieczyć SSH na CentOS i RHEL](/pl/guides/jak-zabezpieczyc-ssh-centos-rhel/).

## Dostęp RDP

Szablony Windows są dostępne przez Remote Desktop z danymi administratora z wdrożenia.
Upewnij się, że firewall Windows dopuszcza RDP, i ogranicz źródła w firewallu instancji.

## Rozwiązywanie problemów z dostępem

| Objaw | Co sprawdzić |
|---|---|
| Konsola utyka na **Connecting...** | Upewnij się, że instancja ma status `running`; zamknij i otwórz kartę ponownie; spróbuj innej przeglądarki; jeśli problem trwa, użyj SSH lub otwórz zgłoszenie |
| SSH odrzuca połączenie | Instancja działa, publiczny adres IP jest przypisany, port 22 dopuszczony w firewallu |
| SSH: błąd uwierzytelniania | Użyj hasła roota z wdrożenia lub sprawdź, czy klucz SSH jest zainstalowany |
| Konsola łączy, ale system nie startuje | Reinstaluj system w Danger Zone albo przywróć kopię |
| Brak dostępu po zmianie firewalla | Użyj konsoli albo popraw regułę w zakładce Firewall |

Jeśli żadna z tych czynności nie przywróci dostępu, otwórz zgłoszenie z nazwą instancji,
publicznym IP, dokładnym błędem i czasem wystąpienia.
