It's possible to use SpatiaLite on Windows by downloading the official `mod_spatialite` binaries. You can download the binaries at the bottom of the page [here](http://www.gaia-gis.it/gaia-sins/).

Direct download links:

* [32bit Download](http://www.gaia-gis.it/gaia-sins/windows-bin-x86/mod_spatialite-4.3.0a-win-x86.7z)
* [64bit Download](http://www.gaia-gis.it/gaia-sins/windows-bin-amd64/mod_spatialite-4.3.0a-win-amd64.7z)

Because the `mod_spatialite` library was built as multiple DLLs, you have to make sure Windows can find all of them. DB4S will load an absolute path to the `mod_spatialite.dll`, and `mod_spatialite.dll` in turn loads the rest of the shared libraries like `libgeos_c-1.dll`, `libproj-9.dll` and others. In order to find these dependent .dll's, they must be located in a directory Windows will search.

There are 2 different ways to get it to work:

1.) Add the directory containing the .dll files to your %PATH%. Windows searches %PATH% for dll files so it will be able to locate all of them. This has the side-effect of any program being able to use them.
2.) Copy the .dll files to the same directory containing `DB Browser for SQLite.exe`. e.g. `C:\Program Files\DB Browser for SQLite` or `C:\Program Files (x86)\DB Browser for SQLite` whichever version you have installed (32bit or 64bit).

You will also want to make sure you use the correct x86 or x64 dll files that correspond to the version of DB4S you have.