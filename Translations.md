# How-To

There is a tool included in the Qt framework for doing the translations: [Qt Linguist](http://doc.qt.io/qt-5/qtlinguist-index.html). The basic translation process is to add a new entry to the [TRANSLATIONS part in the src/src.pro file](https://github.com/sqlitebrowser/sqlitebrowser/blob/988f200e12bf56b1a008677d3da1570c9518c2d4/src/src.pro#L170), then re-build the project. Now, the build system will collect all the strings to translate in the entire application and put them in the file you just added. This newly created ts file can then be opened in Qt Linguist and using this program you can translate all the strings. After saving and rebuilding the translation should be in the application.

## Don't translate key names in shortcuts

Keyboard shortcuts get automatically localized by Qt, and translating key names may indeed break them. They show up on the translation file only for the rare occasions that one has to redirect a shortcut to another one in a specific language. But even then, you should use the English key names to get this working. Theoretically, one could follow Qt conventions for translated key names, and they should work, but the risk to stumble upon Qt bugs or moving conventions is high, so it is better not to translate keys, only remap the shortcut. If you want to preserve the original key sequence (recommended), just leave the translation empty and finished.

## Troubleshooting
[[Translation merge conflicts|Translation conflicts]] - How to proceed with translation conflicts

# Notes regarding languages

## German

### Default translations for the German language

This list is work-in-progress and will be changed if needed. It should be considered as a support document for German-language translators to achieve a consistent translation throughout the whole application.

| Source | Context | Translation | Notes |
|--------|---------|-------------|-------|
| Bar | plots| Säulen | Säulendiagramme ordnen die Werte von oben nach unten, Balkendiagramme von rechts nach links |
| Bar | Toolbar | Werkzeugleiste | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Branch | dbhub.io | Branch | as there is no German translation on dbhub.io it's probably better not to translate branch |
| Certificate file || Zertifikatdatei ||
| Check-Constraint || CHECK-Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| Clause | SQL | Anweisung ||
| Collation || Sortierung ||
| Commit | dbhub.io | commit | as there is no German translation on dbhub.io it's probably better not to translate commit |
| Commit | SQL | abschließen ||
| Constraint || Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| DB Browser for SQLite || DB-Browser für SQLite ||
| Log || Protokoll | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Message from database [engine]<br>DB says || DB meldet ||
| Modifier || Modifizierer ||
| Pane | windowelement | Fensterbereich ||
| Panel | windowelement | Fenster ||
| Passphrase || Passphrase (feminin) | siehe https://www.welivesecurity.com/deutsch/2016/05/06/warum-die-passphrase-besser-als-das-passwort-ist |
| Pattern | regular expression | Suchmuster ||
| Push | dbhub.io | übertragen | It might be better, not to translate always, e.g. 'Push erzwingen'. But never use denglisch like: 'pushen'. |
| Query || Abfrage ||
| Record || Datensatz ||
| Remote | dbhub.io | Entfernt ||
| Row || Zeile *oder* Datenbankzeile ||
| Statement || Anweisung ||
| Stop || abbrechen ||
| String || Zeichenkette ||
| SQL |sql statement| SQL (feminin) | e.g. "Komplette SQL ausführen" instead of "Komplettes SQL ausführen" as it stands for "SQL-Anweisung".|
| Tab | windowelement | Tab| entgegen https://community.kde.org/KDE_Localization/de/StandardUebersetzungen, die vorschlagen: 'Karteikarte' sondern analog Mozilla Firefox Browser - 74.0.1. (64-Bit) - die zum Beispiel übersetzen: 'Strg+T: Neuen Tab öffnen'
| Timestring || Zeit-Zeichenkette||
| Toolbar || Werkzeugleiste | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Unique-Constraint || UNIQUE-Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| Vacuum || Komprimierung ||