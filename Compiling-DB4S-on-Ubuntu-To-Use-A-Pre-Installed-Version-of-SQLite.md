DB4S is kept as up-to-date as possible with the latest version of SQLite, but if you have a newer version installed, you can compile DB4S to use this specific version instead.
The following instructions are for Ubuntu.  Please also read [these build instructions]( https://github.com/sqlitebrowser/sqlitebrowser/blob/master/BUILDING.md#ubuntu-linux).

Recompile DB4S and configure the build to search for the manually installed SQLite version. How exactly this works depends on how you've built SQLite, but the general idea is as follows.

Edit the ```CMakeLists.txt``` file and change line 397
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