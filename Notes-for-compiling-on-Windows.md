## These are initial rough notes for compiling on Windows

Managed to get it working, and am writing up the process (with detailed screenshots) here:

&nbsp; &nbsp; https://github.com/justinclift/sqlitebrowser/wiki/Setting-up-a-Win64-development-environment-for-DB4S

That's very rough.  When it's in good shape, I'll transfer the contents here. :smile:

The pieces below are my initial (older) notes while figuring out a working process.  They can be deleted when the above process documentation is ready.

### Software being used

* Win 8.1 x64
* MS Visual Studio Community 2013 Edition Update 5 - https://www.visualstudio.com/downloads/download-visual-studio-vs.
 * "Visual Studio 2013" option 1/2 way down the left side → "Community 2013"
* Qt Creator 3.6.1 - https://www.qt.io/download-open-source/
* SQLite 3.12.2 - https://www.sqlite.org/download.html
* OpenSSL - https://wiki.openssl.org/index.php/Binaries
 * From the first link (Shining Light Productions) → Win64 OpenSSL v1.0.2g
* CMake 3.5.2 - https://cmake.org/download/
* The INSTALL target on windows needs Visual C++ Redistributable Packages for Visual Studio 2013 (x64) - https://www.microsoft.com/en-us/download/details.aspx?id=40784

### ✔ Compiling SQLite

Initially followed the official SQLite instructions here, underneath the "Building A Windows DLL" heading:

&nbsp; &nbsp; https://sqlite.org/howtocompile.html

The command line given needs to be launched through the "VS2013 x64 Native Tools Command Prompt".  That's accessed through the "Visual Studio Tools" launcher found in the Win 8.1 menu structure.

Although the command generates the .dll (as per the heading)... it turns out MSVC needs a .lib file generated as well to do any useful compiling/development with it.  (That REALLY should be mentioned on the SQLite compiling page :frowning:)

The correct command to run instead, which created both the .dll file and other supporting files (such as the .lib), is this:

    cl sqlite3.c -DSQLITE_API=__declspec(dllexport) -link -dll -out:sqlite3.dll

That's copied from [here](http://protyposis.net/blog/compiling-sqlite-as-dll-with-msvc/).

### ✔ Trying with CMake now instead

1. Installed the above SQLite + OpenSSL to a directory off C:\
2. Change the paths in the CMakeLists.txt file to match the correct locations
 * QT5_PATH
 * SQLITE3_PATH
 * OPENSSL_PATH
3. Run "cmake" (the command line version, not the gui) from the main sqlitebrowser git repo directory

...

Managed to [get it working](https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-215229614), with the assistance of [@drescherjm](https://github.com/drescherjm) (seriously, thanks! :smile:).

Tomorrow I'll go back through it, get it working from scratch, and document the process so everyone else with an interest can make it happen too.

### Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468

### Other notes

* Conan looks like it might be useful for dependency management - https://www.conan.io.  [It's Open Source](https://github.com/conan-io/conan).