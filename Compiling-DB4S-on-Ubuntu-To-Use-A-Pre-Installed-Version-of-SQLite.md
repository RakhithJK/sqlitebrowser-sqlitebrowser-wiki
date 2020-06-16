DB4S is kept as up-to-date as possible with the latest version of SQLite, but if you have a newer version installed, you can compile DB4S to use this specific version instead.
The following instructions are for Ubuntu.  Please also read [these build instructions]( https://github.com/sqlitebrowser/sqlitebrowser/blob/master/BUILDING.md#ubuntu-linux).

Recompile DB4S and configure the build to search for the manually installed SQLite version. How exactly this works depends on how you've built SQLite, but the general idea is as follows.

Edit the src/src.pro file. Around line 256 you should find these lines:

```
INCLUDEPATH += $$PWD/../libs/qhexedit $$PWD/../libs/qcustomplot-source $$PWD/../libs/qscintilla/Qt4Qt5 $$PWD/..
LIBS += -L$$LIBPATH_QHEXEDIT -L$$LIBPATH_QCUSTOMPLOT -L$$LIBPATH_QSCINTILLA -lqhexedit -lqcustomplot -lqscintilla2
```
Change them to
```
INCLUDEPATH += /path/to/your/sqlite/lib/header/files $$PWD/../libs/qhexedit $$PWD/../libs/qcustomplot-source $$PWD/../libs/qscintilla/Qt4Qt5 $$PWD/..
LIBS += -L/path/to/your/sqlite/lib/a/file -L$$LIBPATH_QHEXEDIT -L$$LIBPATH_QCUSTOMPLOT -L$$LIBPATH_QSCINTILLA -lqhexedit -lqcustomplot -lqscintilla2
```
Where the first path points to the directory that contains the ```sqlite3.h``` file and the second path points to the directory that contains the ```libsqlite3.a``` file.

Then just run this from the root dir of the repository to build the application:
```
qmake
make
```

If you want to use cmake, you'll have to edit the ```CMakeLists.txt``` file and change line 252
```
find_library(LIBSQLITE ${LIBSQLITE_NAME})
```
to this
```
find_library(LIBSQLITE ${LIBSQLITE_NAME} HINTS /path/to/your/sqlite/lib/a/file)
set(ADDITIONAL_INCLUDE_PATHS /path/to/your/sqlite/lib/header/files)
```
And then run this from the root dir of the repository:
```
mkdir build
cd build
cmake ..
make
```


Credit to [MKleusberg](https://github.com/MKleusberg) for the detailed instructions.