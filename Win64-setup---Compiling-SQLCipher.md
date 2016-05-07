## How to compile SQLCipher on Win64

### Requirements

* [Microsoft Visual Studio Community 2013 Edition Update 5](https://www.visualstudio.com/downloads/download-visual-studio-vs)
 * Click the "Visual Studio 2013" option 1/2 way down the left side → "Community 2013" → ISO
* [ActiveState ActiveTcl 8.5 Community Edition](https://www.activestate.com/activetcl/downloads)
 * Windows (64-bit, x64)

### Instructions

**1.** [Install Visual Studio 2013](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-2-—-Install-MSVC2013)

Only follow the instructions for that one page, not the rest of the guide it is part of.

**2.** [Install ActiveTcl 8.5](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Install-ActiveTcl-8.5)

**3.** [Install OpenSSL](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-4-—-Install-OpenSSL)

Only follow the instructions for that one page, not the rest of the guide it is part of.

**4.** Clone the SQLCipher repo

[screenshots to be added here]

**5.** Edit Makefile.msc

* `-DSQLITE_TEMP_STORE` needs to be changed from 1 to 2
* `-DSQLITE_HAS_CODEC` needs to be added to the `TCC` and `RCC` variables
* `-IC:\dev\OpenSSL-Win64\include` needs to be added to the `TCC` and `RCC` variables
* `/LIBPATH:C:\dev\OpenSSL-Win64\lib /LIBPATH:C:\dev\OpenSSL-Win64\lib\VC` needs to be added to the `LTLIBPATHS` variable
* `4758cca.lib aep.lib atalla.lib capi.lib chil.lib cswift.lib gmp.lib gost.lib libeay32.lib nuron.lib padlock.lib ssleay32.lib sureware.lib ubsec.lib` needs to be added to the `LTLIBS` variable
* `SQLITE3DLL` should be changed to `sqlcipher.dll`
* `SQLITE3LIB` should be changed to `sqlcipher.lib`
* `SQLITE3EXE` should be changed to `sqlcipher.exe`
* `SQLITE3EXEPDB` should be changed to `/pdb:sqlciphersh.pdb`
* Do a case sensitive search-n-replace, changing `sqlite3.def` to `sqlcipher.def`

**6.** Compile SQLCipher

Launch the "VS2013 x64 Native Tools Command Prompt".

It's accessed through the "Visual Studio Tools" item in the Win 8.1 menu structure.

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/08-install_sqlite/056.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/08-install_sqlite/057.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/08-install_sqlite/058.png)

Change to the `C:\git_repos\sqlcipher` directory, then run this command to compile SQLCipher:

    nmake /f Makefile.msc

It should run for about a minute or so, and you'll see various other commands running in the command prompt window.  It should finish without error, looking something like this:

If so, the process is now complete, with SQLCipher successfully compiled. 😋
