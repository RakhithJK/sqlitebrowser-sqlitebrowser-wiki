## These are initial rough notes for compiling on Windows

Haven't yet managed to figure get it working, but am making progress.  So, keeping notes here in the meantime. :smile:

### Software being used

* Win 8.1 x64
* MS Visual Studio Community 2013 Edition Update 5
* Qt Creator 3.6.1

### Compiling SQLite

Initially followed the official SQLite instructions here, underneath the "Building A Windows DLL" heading:

&nbsp; &nbsp; https://sqlite.org/howtocompile.html

The command line given needs to be launched through the "VS2013 x64 Native Tools Command Prompt".  That's accessed through the "Visual Studio Tools" launcher found in the Win 8.1 menu structure.

Although the command generates the .dll (as per the heading)... it turns out MSVC needs a .lib file generated as well to do any useful compiling/development with it.  (That REALLY should be mentioned on the SQLite compiling page :frowning:)

The correct command to run instead, which created both the .dll file and other supporting files (such as the .lib), is this:

    cl sqlite3.c -DSQLITE_API=__declspec(dllexport) -link -dll -out:sqlite3.dll

That's copied from [here](http://protyposis.net/blog/compiling-sqlite-as-dll-with-msvc/).

### Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468