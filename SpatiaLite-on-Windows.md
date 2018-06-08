It's possible to use SpatiaLite on Windows by downloading the official `mod_spatialite` binaries. You can download the binaries at the bottom of the page [here](http://www.gaia-gis.it/gaia-sins/).

Direct download links:

* [32bit Download](http://www.gaia-gis.it/gaia-sins/windows-bin-x86/mod_spatialite-4.3.0a-win-x86.7z)
* [64bit Download](http://www.gaia-gis.it/gaia-sins/windows-bin-amd64/mod_spatialite-4.3.0a-win-amd64.7z)

Because the `mod_spatialite` library was built as multiple DLLs, you have to make sure Windows can find all of them. DB4S will load an absolute path to the `mod_spatialite.dll`, and `mod_spatialite.dll` in turn loads the rest of the shared libraries like `libgeos_c-1.dll`, `libproj-9.dll` and others. In order to find these dependent .dll's, they must be located in a directory Windows will search.

There are 2 different ways to get it to work:

1. Add the directory containing the .dll files to your `%PATH%`. Windows searches `%PATH%` for dll files so it will be able to locate all of them. This has the side-effect of any program being able to use them.
2. Copy the .dll files to the same directory containing `DB Browser for SQLite.exe`. e.g. `C:\Program Files\DB Browser for SQLite` or `C:\Program Files (x86)\DB Browser for SQLite` whichever version you have installed (32bit or 64bit).

You will also want to make sure you use the correct x86 or x64 dll files that correspond to the version of DB4S you have.

### Alternative instructions, with screenshots

* [Working with Geospatial Data](http://www.fulcrumapp.com/blog/working-with-geodata/#tools-for-working-with-sqlite) - This guide by @bmcbride has a set of step-by-step instructions + screenshots showing how to install SpatiaLite.

### Workaround for Windows 10 failure

If you're using Windows 10 and the SpatiaLite extention fails to load, there is a workaround:

![Win10 fail](https://user-images.githubusercontent.com/12534211/41079043-148758fe-6a31-11e8-8def-5d6b462a789a.jpg)

As [@karim](https://github.com/karim) [points out](https://github.com/sqlitebrowser/sqlitebrowser/issues/267#issuecomment-395773272), Spatialite includes an older version of `libstdc++-6.dll`, which works fine in Windows 7 but not Windows 10.

This file comes from MinGW, the compiler they use to build the extension.  Replacing it with a newer version works.

1. Delete `libstdc++_64-6.dll` from DB4S folder
2. Go to https://sourceforge.net/projects/mingw-w64/files/ and download one of **x86_64-win32-seh** files
    - Or use this direct link [here](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win64/Personal%20Builds/mingw-builds/8.1.0/threads-win32/seh/x86_64-8.1.0-release-win32-seh-rt_v6-rev0.7z)
3. Extract it somewhere and look into the `bin` folder
4. Copy both `libstdc++-6.dll` and `libgcc_s_seh-1.dll` to DB4S folder
5. Rename `libstdc++-6.dll` to `libstdc++_64-6.dll`
6. Try to load the module again.  This time it should work.

Credit goes to http://blog.jrg.com.br/2016/04/25/Fixing-spatialite-loading-problem/