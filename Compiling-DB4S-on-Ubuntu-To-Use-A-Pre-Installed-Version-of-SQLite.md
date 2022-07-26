DB4S is kept as up-to-date as possible with the latest version of SQLite, but if you have a newer version installed, you can compile DB4S to use this specific version instead.
The following instructions are for Ubuntu. Please also read [these build instructions](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/BUILDING.md#ubuntu-linux).

To use a different version of SQLite, add `-DCMAKE_SYSTEM_PREFIX_PATH=<prefix>` (where `<prefix>` is the SQLite installed directory) to the CMake invocation.

(If you use the default installation directory, which is usually `/usr/local`, this isn't required)

```
mkdir build && cd build
cmake -DCMAKE_SYSTEM_PREFIX_PATH=<prefix> ..
make
```

Credit to [longnguyen2004](https://github.com/longnguyen2004) for the detailed instructions.