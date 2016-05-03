## These are initial notes for compiling on Windows

* MS Visual Studio 2013 (as both compiler + IDE) works
 * Complete setup, build, and packaging [instructions are here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Setting-up-a-Win64-development-environment-for-DB4S#1-gather-the-required-files).
* Qt Creator (as IDE) works, using MSVC 2013 as the compiler
 * Instructions for setting it up and building haven't yet been written up

### Notes for Qt Creator

* Open the src/src.pro file first, run lupdate, then lrelease
  * This avoids the error about missing translation files, that happens if you open and use the sqlitebrowser.pro file first (in a newly cloned repo)
* After doing the above, close the src/src.pro file, then open the sqlitebrowser.pro one
  * Choose the msvc 2013 64-bit kit for the project (it will ask when you open the .pro file)
  * Compile/debug as per normal

### Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468

### Other notes

* Conan looks like it might be useful for dependency management - https://www.conan.io.  [It's Open Source](https://github.com/conan-io/conan).