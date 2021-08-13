# These are initial notes for compiling on Windows

* MS Visual Studio 2013 (as both compiler + IDE) works
 * Complete setup, build, and packaging [instructions are here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Setting-up-a-Win64-development-environment-for-DB4S).
* Qt Creator (as IDE) works, using MSVC 2013 as the compiler
 * Instructions for setting it up and building haven't yet been written up

## Windows XP compatibility

When compiling 32-bit builds, Windows XP compatibility can be enabled for them.

### CMake

[This post](http://cmake.3232098.n2.nabble.com/Windows-XP-CMake-VS2013-td7586295.html) mentions adding `-T vc120_xp` to the cmake command line as one way to make it happen.

### MSVC 2013

Using the MSVC 2013 IDE, it can be achieved like this:

![Right click the project file used to compile](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/winxp_compile_notes/winxp_compat01.png)
![Choose the WinXP compatibility option](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/winxp_compile_notes/winxp_compat02.png)

## Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468

## Other notes

* Conan looks like it might be useful for dependency management - https://www.conan.io.  [It's Open Source](https://github.com/conan-io/conan).