### Notes for compiling on OpenSuSE Leap 42.2

```
$ sudo zypper install antlr3c-devel git libqscintilla-devel patterns-openSUSE-devel_qt5 sqlite3-devel
$ git clone https://github.com/sqlitebrowser/sqlitebrowser
$ cd sqlitebrowser
$ cmake -Wno-dev .
```