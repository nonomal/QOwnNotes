# Pojęcie

```mermaid
graph TB
    subgraph Your computer
        qon((QOwnNotes))-->md{{"Markdown files"}}
        sync("Nextcloud Sync")-->md
        qon-comp("Browser extension")-->qon
        qc("Command-line snippet manager")-->qon
    end
    subgraph Your Nextcloud server
        qon-api("QOwnNotesApi")-->ncs[("Nextcloud server")]
        nc-notes-app("Nextcloud Notes")-->ncs
    end

    nc-notes-mob("Nextcloud Notes mobile app")-->nc-notes-app
    qon-web-app("QOwnNotes web application")-->qon
    qon-->qon-api
    qon-->ncs
    sync-->ncs
    qon-.->qon-web-api("api.qownnotes.org")
    qon-web-api-->github("GitHub")

    style qon fill:#d0d0ff,stroke:#333,stroke-width:4px
    click qon "/getting-started/concept.html#qownnotes" "QOwnNotes Desktop Application for managing your notes on your desktop computer"
    click md "/getting-started/concept.html#markdown-note-files" "Markdown, media and attachment files in your note folder"
    click qon-comp "/getting-started/concept.html#qownnotes-browser-extension" "QOwnNotes browser extension for managing bookmarks in markdown files and as web clipper"
    click qc "/getting-started/concept.html#qownnotes-command-line-snippet-manager" "QOwnNotes command-line snippet manager"
    click sync "/getting-started/concept.html#nextcloud-desktop-sync-client" "Nextcloud desktop sync client to sync your notes to your server"
    click ncs "/getting-started/concept.html#nextcloud-server" "Nextcloud server to host your notes and other files"
    click qon-api "/getting-started/concept.html#qownnotesapi-nextcloud-app" "QOwnNotesAPI Nextcloud app to access your server-side trash and note versions"
    click nc-notes-app "/getting-started/concept.html#nextcloud-notes-server-app" "Nextcloud Notes server app to manage your notes in the web"
    click nc-notes-mob "/getting-started/concept.html#nextcloud-notes-mobile-app" "Nextcloud Notes mobile app to manage your notes on your mobile phone"
    click qon-web-app "/getting-started/concept.html#qownnotes-web-app" "QOwnNotes Web App to send photos from your mobile phone"
    click qon-web-api "/getting-started/concept.html#api-qownnotes-org"
```

## QOwnNotes

- QOwnNotes **przechowuje notatki** w Twoim **folderze notatek jako pliki znaczników**
- Może komunikować się z serwerem Nextcloud / ownCloud, **aby publicznie udostępniać notatki** innym osobom
- Możesz także **uzyskać dostęp do historii notatek i kosza** na serwerze Nextcloud / ownCloud za pośrednictwem aplikacji [QOwnNotesApi Nextcloud](#qownnotesapi-nextcloud-app)
- Listy rzeczy do zrobienia na serwerze Nextcloud / ownCloud są dostępne z poziomu QOwnNotes
- **QOwnNotes nie synchronizuje twoich notatek** i plików multimedialnych / załączników!
    - Synchronizacja plików to złożone przedsięwzięcie, istnieją już świetne rozwiązania do synchronizacji plików (patrz [Klient synchronizacji pulpitu Nextcloud](#nextcloud-desktop-sync-client))


## Pliki notatek Markdown

- **jesteś właścicielem** wszystkich swoich notatek i plików multimedialnych / załączników!
- Notatki są przechowywane na komputerze jako **pliki zwykłego tekstu Markdown**
- Możesz użyć dowolnego edytora tekstu oprócz QOwnNotes do przeglądania lub edycji plików notatek
- **Synchronizuj swoje notatki** z innymi urządzeniami (stacjonarnymi i mobilnymi) za pomocą klienta synchronizacji [Nextcloud](https://nextcloud.com/) lub [ownCloud](https://owncloud.org/) z serwerem


## Rozszerzenie przeglądarki QOwnNotes

Możesz zarządzać swoimi **zakładkami przeglądarki** za pomocą QOwnNotes lub używać go jako **narzędzia do usuwania stron internetowych**.

::: tip
Rozszerzenia przeglądarki działają **offline**, nie jest potrzebne połączenie internetowe. Aby uzyskać więcej informacji, odwiedź [rozszerzenie QOwnNotes Web Companion do przeglądarki](browser-extension.md).
:::

## QOwnNotes command-line snippet manager

Możesz zarządzać **fragmentami poleceń** za pomocą QOwnNotes i wykonywać je w wierszu poleceń.

::: tip
Odwiedź stronę [menedżera fragmentów wiersza polecenia QOwnNotes](command-line-snippet-manager.md), aby uzyskać więcej informacji.
:::

## Klient synchronizacji pulpitu Nextcloud

**Synchronizuj swoje notatki** z innymi urządzeniami (stacjonarnymi i mobilnymi) za pomocą klienta synchronizacji [Nextcloud](https://nextcloud.com/) lub [ownCloud](https://owncloud.org/) z serwerem.

::: tip
Oczywiście inne rozwiązania, takie jak **Dropbox**, **Syncthing**, **Seafile** lub BitTorrent Sync mogą być również używane do synchronizacji notatek i innych plików.

Możesz także użyć **git** do synchronizacji z narzędziami takimi jak [gitomatic](https://github.com/muesli/gitomatic/).
:::

## Serwer Nextcloud

Aby pracować z notatkami online, możesz użyć serwerów takich jak [Nextcloud](https://nextcloud.com/) lub [ownCloud](https://owncloud.org/).

Możesz hostować własny serwer lub skorzystać z rozwiązań hostowanych.

Istnieje [lista obsługiwanych przez społeczność dostawców Nextcloud](https://github.com/nextcloud/providers#providers), a także [lista urządzeń z Nextcloud](https://nextcloud.com/devices/).

[Portknox](https://portknox.net) zgłosił, że ma [QOwnNotesAPI zainstalowane](https://portknox.net/en/app_listing).

::: tip
Oczywiście inne rozwiązania, takie jak **Dropbox**, **Syncthing**, **Seafile** lub BitTorrent Sync mogą być również używane do hostowania notatek i innych plików.
:::

## QOwnNotesAPI Nextcloud app

[**QOwnNotesAPI**](https://github.com/pbek/qownnotesapi) umożliwia dostęp do **notatek w koszu** i **wersji notatek** po stronie serwera.

::: tip
Aby uzyskać więcej informacji, odwiedź [QOwnNotesAPI Nextcloud App](qownnotesapi.md).
:::

## Aplikacja serwerowa Nextcloud Notes

Użyj [**Nextcloud Notes**](https://github.com/nextcloud/notes), aby edytować swoje notatki w **sieci**.

::: warning
Należy pamiętać, że program Nextcloud Notes obsługuje obecnie tylko jeden poziom podfolderów.
:::

## Aplikacja mobilna Nextcloud Notes

Aby uzyskać dostęp do notatek Nextcloud / ownCloud z **urządzenia mobilnego**, możesz korzystać z różnych aplikacji.

### Android

- [Nextcloud Notes dla Androida](https://play.google.com/store/apps/details?id=it.niedermann.owncloud.notes) (inna firma)

::: tip
Możesz także użyć dowolnego narzędzia do synchronizacji, takiego jak *Synchronize Ultimate* lub *FolderSync*, aby zsynchronizować pliki notatek i użyć oprogramowania takiego jak *neutriNotes* do edycji swoich notatek.
:::

### iOS

- [CloudNotes na iOS](https://itunes.apple.com/de/app/cloudnotes-owncloud-notes/id813973264?mt=8) (inna firma)

::: tip
Możesz także użyć [Notatników](https://itunes.apple.com/us/app/notebooks-write-and-organize/id780438662) i zsynchronizuj swoje notatki przez WebDAV, jest dobry samouczek pod adresem [Robienie notatek z Nextcloud, QOwnNotes i Notatnikami](https://lifemeetscode.com/blog/taking-notes-with-nextcloud-qownnotes-and-notebooks)
:::

## api.qownnotes.org

Jest to usługa online świadczona przez QOwnNotes w celu sprawdzenia, czy jest dostępna nowa wersja aplikacji.

Rozmawia z GitHubem i sprawdza najnowsze wydanie, pobiera odpowiedni adres URL pobierania i kompiluje zmiany z dziennika zmian w porównaniu z wersją QOwnNotes, której obecnie używasz jako html, aby wyświetlić w oknie dialogowym aktualizacji.

Ponadto zapewnia również [kanał informacyjny RSS wydania](http://api.qownnotes.org/rss/app-releases) oraz implementację starszego interfejsu API sprawdzającego aktualizacje dla starszych wersji QOwnNotes.

::: tip
Możesz uzyskać dostęp do kodu źródłowego [api.qownnotes.org](https://api.qownnotes.org) w [GitHub](https://github.com/qownnotes/api).
:::

## QOwnNotes Web App

Możesz wstawić zdjęcia z telefonu komórkowego do bieżącej notatki w QOwnNotes na komputerze za pomocą **aplikacji internetowej** na [app.qownnotes.org](https://app.qownnotes.org/).

::: tip
Odwiedź [Aplikację internetową QOwnNotes](web-app.md), aby uzyskać więcej informacji.
:::
