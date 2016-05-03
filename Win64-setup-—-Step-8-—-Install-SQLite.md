### Previous page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-7-—-Install-Qt).

## 8. Install SQLite

In this step, we create a directory structure to hold the SQLite source code and libraries.

Create `C:\dev\SQLite`:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/050.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/051.png)

Next, copy the contents of the sqlite-amalgamation .zip file (from the SQLite website) into it:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/049.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/054.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/108.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/055.png)

We need to compile the SQLite source code now.  To do that, launch the "VS2013 x64 Native Tools Command Prompt".

That's accessed through the "Visual Studio Tools" item in the Win 8.1 menu structure.

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/056.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/057.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/058.png)

First, change directory to `C:\dev\SQLite`.

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/109.png)

Then run [this command](http://protyposis.net/blog/compiling-sqlite-as-dll-with-msvc/) to compile SQLite:

    cl sqlite3.c -DSQLITE_API=__declspec(dllexport) -link -dll -out:sqlite3.dll

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/059.png)

Four new files will be created in the folder:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/08-install_sqlite/110.png)

SQLite is now compiled for MSVC to use.

You can close the DOS command window now,  as it's not needed any more.

## Next page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-9-—-Install-GitHub-Desktop).