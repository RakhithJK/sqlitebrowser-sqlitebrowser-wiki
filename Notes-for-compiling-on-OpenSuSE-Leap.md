### Notes for compiling on OpenSuSE Leap 42.2

```
$ sudo zypper install antlr3c-devel git libqscintilla-devel patterns-openSUSE-devel_qt5 sqlite3-devel
$ git clone https://github.com/sqlitebrowser/sqlitebrowser
$ cd sqlitebrowser
$ cmake -Wno-dev .
$ sudo cmake install
...
Install the project...
-- Install configuration: "Release"
-- Installing: /usr/local/bin/sqlitebrowser
-- Up-to-date: /usr/local/share/icons/hicolor/256x256/apps/sqlitebrowser.png
-- Up-to-date: /usr/local/share/applications/sqlitebrowser.desktop
-- Up-to-date: /usr/local/share/appdata/sqlitebrowser.desktop.appdata.xml
```

The resulting binary is non-functional though.  It segfaults when run:

```
$ /usr/local/bin/sqlitebrowser
Segmentation fault (core dumped)
```

It's caused by one of the system provided ANTLR or QScintilla libs, as no core-dump happens when using the ones we provide.  More investigation needed.