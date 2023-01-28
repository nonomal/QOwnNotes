# Zainstaluj na Arch Linux

## Arch Repozytorium użytkowników (AUR)

Alternatywnie istnieje również oficjalny pakiet dla QOwnNotes na AUR, nazywa się on `qownnotes`.

Znajdziesz go tutaj: [QOwnNotes na AUR](https://aur.archlinux.org/packages/qownnotes)

Zsynchronizuj bazę danych pakietów i zainstaluj pakiet z `yay`:

```bash
yay -S qownnotes
```

::: wskazówka Jeśli chcesz przyspieszyć czas budowania, możesz przeczytać [CCACHE i AUR](https://www.reddit.com/r/archlinux/comments/6vez44/a_small_tip_if_you_compile_from_aur/).
:::

## pacman

::: ostrzeżenie [OBS](https://build.opensuse.org/package/show/home:pbek:QOwnNotes/desktop) obecnie wydaje się, że ma problemy z kompilacją w Arch Linux. Najlepiej na razie użyj AUR lub [AppImage](./appimage.md).
:::

Dodaj następujące wiersze do pliku `/etc/pacman.conf` za pomocą `sudo nano /etc/pacman.conf`:

```ini
[home_pbek_QOwnNotes_Arch_Extra]
SigLevel = Optional TrustAll
Server = http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Arch_Extra/$arch
```

Uruchom następujące polecenia w wierszu poleceń, aby dodać repozytorium jako zaufane:

```bash
wget http://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Arch_Extra/x86_64/home_pbek_QOwnNotes_Arch_Extra.key -O - | sudo pacman-key --add -
sudo pacman-key --lsign-key F2205FB121DF142B31450865A3BA514562A835DB
```

Jeśli wykonanie polecenia `sudo pacman-key --lsign-key F2205FB121DF142B31450865A3BA514562A835DB` się nie powiodło i pojawił się komunikat: `ERROR: FFC43FC94539B8B0 nie można podpisać lokalnie.`, możesz najpierw sprawdzić rzeczywisty identyfikator klucza *keyid*, np. za pomocą polecenia (i danych wyjściowych):

```bash
gpg /path/to/downloaded/home_pbek_QOwnNotes_Arch_Extra.key
gpg: Ostrzeżenie: Brak polecenia.  Próbuję zgadnąć, co masz na myśli ...
pub   rsa2048 2019-07-31 [SC] [expires: 2021-10-10]
      F2205FB121DF142B31450865A3BA514562A835DB
uid           home:pbek OBS Project <home:pbek@build.opensuse.org>
```

Możesz teraz zsynchronizować swoją bazę pakietów i zainstalować pakiet z `pacman`:

```bash
sudo pacman -Syy qownnotes
```

[Bezpośrednie Pobieranie](https://download.opensuse.org/repositories/home:/pbek:/QOwnNotes/Arch_Extra)

::: Wskazówka
Oczywiście możesz również używać tego repozytorium z innymi dystrybucjami opartymi na Arch Linux, takimi jak Manjaro.
:::
