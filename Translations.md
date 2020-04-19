# How-To

There is a tool included in the Qt framework for doing the translations: [Qt Linguist](http://doc.qt.io/qt-5/qtlinguist-index.html). The basic translation process is to add a new entry to the [TRANSLATIONS part in the src/src.pro file](https://github.com/sqlitebrowser/sqlitebrowser/blob/988f200e12bf56b1a008677d3da1570c9518c2d4/src/src.pro#L170), then re-build the project. Now, the build system will collect all the strings to translate in the entire application and put them in the file you just added. This newly created ts file can then be opened in Qt Linguist and using this program you can translate all the strings. After saving and rebuilding the translation should be in the application.

# Notes regarding languages

## German

### Default translations for the German language

This list is work-in-progress in will be changed if needed. It should be considered as a support document for German-language translators to achieve a consistent translation throughout the whole application.

| Source | Context | Translation | Notes |
|--------|---------|-------------|-------|
| bar | plots| Säulen | Säulendiagramme ordnen die Werte von oben nach unten, Balkendiagramme von rechts nach links |
| bar | Toolbar | Werkzeugleiste | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Check-Constraint || CHECK-Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| clause | SQL | Anweisung ||
| Collation || Sortierung ||
| commit || abschließen ||
| Constraint || Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| Log || Protokoll | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Message from database [engine]<br>DB says || DB meldet ||
| pattern | regular expression | Suchmuster ||
| Query || Abfrage ||
| Record || Datensatz ||
| Row || Zeile *oder* Datenbankzeile ||
| Statement || Anweisung ||
| stop || abbrechen ||
| Tab | windowelement | Tab|entgegen https://community.kde.org/KDE_Localization/de/StandardUebersetzungen, die vorschlagen: 'Karteikarte' sondern analog Mozilla Firefox Browser - 74.0.1. (64-Bit) - die zum Beispiel übersetzen: 'Strg+T: Neuen Tab öffnen'
| Toolbar || Werkzeugleiste | siehe https://community.kde.org/KDE_Localization/de/StandardUebersetzungen |
| Unique-Constraint || UNIQUE-Beschränkung | siehe https://github.com/sqlitebrowser/sqlitebrowser/pull/2193 |
| Vacuum || Komprimierung ||