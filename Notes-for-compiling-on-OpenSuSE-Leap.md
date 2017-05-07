### Notes for compiling on OpenSuSE Leap 42.2

```
$ sudo zypper install antlr3c-devel git libqscintilla-devel patterns-openSUSE-devel_qt5 sqlite3-devel
$ git clone https://github.com/sqlitebrowser/sqlitebrowser
$ cd sqlitebrowser
$ cmake -Wno-dev .
$ make
$ sudo make install
...
Install the project...
-- Install configuration: "Release"
-- Installing: /usr/local/bin/sqlitebrowser
-- Up-to-date: /usr/local/share/icons/hicolor/256x256/apps/sqlitebrowser.png
-- Up-to-date: /usr/local/share/applications/sqlitebrowser.desktop
-- Up-to-date: /usr/local/share/appdata/sqlitebrowser.desktop.appdata.xml
```

The resulting executable is non-functional though.  It segfaults when run:

```
$ /usr/local/bin/sqlitebrowser
Segmentation fault (core dumped)
```

It's caused by the system provided QScintilla, as no core-dump happens when using the QScintilla we bundle.  Doing the compile like this leads to a working executable:

```
$ cmake -Wno-dev  -DFORCE_INTERNAL_ANTLR=OFF -DFORCE_INTERNAL_QSCINTILLA=ON
$ make
$ sudo make install
```

It's probably a good idea to investigate if the OpenSuSE provided "sqlitebrowser" works, and if so take a look at the build script used.