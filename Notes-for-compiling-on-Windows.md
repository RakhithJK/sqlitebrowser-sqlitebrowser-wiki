## These are initial rough notes for compiling on Windows

Haven't yet managed to figure get it working, but am making progress.  So, keeping notes here in the meantime. :smile:

### Software being used

* Win 8.1 x64
* MS Visual Studio Community 2013 Edition Update 5 - https://www.visualstudio.com/downloads/download-visual-studio-vs.
 * "Visual Studio 2013" option 1/2 way down the left side → "Community 2013"
* Qt Creator 3.6.1 - https://www.qt.io/download-open-source/
* SQLite 3.12.2 - https://www.sqlite.org/download.html
* OpenSSL - https://wiki.openssl.org/index.php/Binaries
 * From the first link (Shining Light Productions) → Win64 OpenSSL v1.0.2g

### ✔ Compiling SQLite

Initially followed the official SQLite instructions here, underneath the "Building A Windows DLL" heading:

&nbsp; &nbsp; https://sqlite.org/howtocompile.html

The command line given needs to be launched through the "VS2013 x64 Native Tools Command Prompt".  That's accessed through the "Visual Studio Tools" launcher found in the Win 8.1 menu structure.

Although the command generates the .dll (as per the heading)... it turns out MSVC needs a .lib file generated as well to do any useful compiling/development with it.  (That REALLY should be mentioned on the SQLite compiling page :frowning:)

The correct command to run instead, which created both the .dll file and other supporting files (such as the .lib), is this:

    cl sqlite3.c -DSQLITE_API=__declspec(dllexport) -link -dll -out:sqlite3.dll

That's copied from [here](http://protyposis.net/blog/compiling-sqlite-as-dll-with-msvc/).

### ✗ Current error using in-built Qt tools - linking

It's all compiling ok, but linking is failing:

    LINK : fatal error LNK1104: cannot open file 'sqlite3.lib'

To me, this is bizarre, as I've created the exact .lib file it needs (above), and also added the library definition for it to the project _[using the Qt wizard for doing exactly that](https://doc.qt.io/qtcreator/creator-project-qmake-libraries.html#example-of-adding-internal-libraries)_.

Yes, getting frustrated. :wink:

Ironically, I'm not the only one.  StackExchange shows another person hitting exactly the same problem... with *our project*. :frowning: 

&nbsp; &nbsp; https://stackoverflow.com/questions/36117817/qt-cannot-open-file-sqlite3-lib/36786563

The people there didn't help the previous person at all, so no joy here either.

### ✗ Trying with CMake now instead

1. Installed the above SQLite + OpenSSL to a directory off C:\
2. Change the paths in the CMakeLists.txt file to match the correct locations
 * QT5_PATH
 * SQLITE3_PATH
 * OPENSSL_PATH
3. Run "cmake" (the command line version, not the gui) from the main sqlitebrowser git repo directory

### ✗ Current error using CMake

Well, this is non-optimal:

```
-- Could NOT find Antlr2 (missing:  ANTLR2_LIBRARIES ANTLR2_INCLUDE_DIRS)
CMake Error at libs/qhexedit/CMakeLists.txt:6 (find_package):
  By not providing "FindQt5Widgets.cmake" in CMAKE_MODULE_PATH this project
  has asked CMake to find a package configuration file provided by
  "Qt5Widgets", but CMake did not find one.

  Could not find a package configuration file provided by "Qt5Widgets" with
  any of the following names:

    Qt5WidgetsConfig.cmake
    qt5widgets-config.cmake

  Add the installation prefix of "Qt5Widgets" to CMAKE_PREFIX_PATH or set
  "Qt5Widgets_DIR" to a directory containing one of the above files.  If
  "Qt5Widgets" provides a separate development package or SDK, be sure it has
  been installed.
```

It doesn't seem to be automatically picking up the cmake/FindAntlr2.cmake file for some reason. :frowning:

### Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468

### Other notes

* Conan looks like it might be useful for dependency management - https://www.conan.io.  [It's Open Source](https://github.com/conan-io/conan).