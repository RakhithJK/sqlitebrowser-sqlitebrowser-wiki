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

### Current error - linking

It's all compiling ok, but linking is failing:

    LINK : fatal error LNK1104: cannot open file 'sqlite3.lib'

To me, is bizarre, as I've created the exact .lib file it needs (above), and also added the library definition to the project _using the Qt wizard for doing exactly that_.

Yes, getting frustrated. :wink:

Ironically, I'm not the only one.  StackExchange shows another user hitting exactly the same problem... with *our project*. :frowning: 

    https://stackoverflow.com/questions/36117817/qt-cannot-open-file-sqlite3-lib/36786563

The people there didn't help the previous person at all, so no joy here either.

### Related Issue(s) in our repo

* https://github.com/sqlitebrowser/sqlitebrowser/issues/482#issuecomment-169941468