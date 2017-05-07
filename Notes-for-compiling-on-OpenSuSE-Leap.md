### Notes for compiling on OpenSuSE Leap 42.2

```
$ sudo zypper install git patterns-openSUSE-devel_qt5 sqlite3-devel
$ git clone https://github.com/sqlitebrowser/sqlitebrowser
$ cd sqlitebrowser
$ cmake -DFORCE_INTERNAL_ANTLR=ON -DFORCE_INTERNAL_QSCINTILLA=ON
```