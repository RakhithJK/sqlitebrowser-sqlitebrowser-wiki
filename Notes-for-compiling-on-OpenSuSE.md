## Notes for compiling on OpenSuSE

### Leap 42.2

These steps work for compiling the latest source code:

```
$ sudo zypper install antlr3c-devel git patterns-openSUSE-devel_qt5 sqlite3-devel
$ git clone https://github.com/sqlitebrowser/sqlitebrowser
$ cd sqlitebrowser
$ cmake -Wno-dev -DFORCE_INTERNAL_QSCINTILLA=ON
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

Note, we use `-DFORCE_INTERNAL_QSCINTILLA=ON` to ensure our bundled version of QScintilla is used.  Leap 42.2 does provide a version of QScintilla, but it's compiled using Qt4 which will screw things up for us if used.

The finished result is installed as `/usr/local/bin/sqlitebrowser`, with a menu entry shortcut added in the "Development" Category:

![OpenSuSE Leap 42.2 Xfce menu entry](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/opensuse_leap_42.2/xfce_menu_screenshot.png)


### Tumbleweed

The above instructions also work for OpenSuSE Tumbleweed, with one exception.

On Tumbleweed, the shortcut in the "Development" Category doesn't appear in the UI.  The program itself works fine though when launched manually from the command line.