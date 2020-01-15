These are some rough notes, prior to making a full document.

## Qt

We removed support for Qt4 after our version 3.9.1 release.  We now require Qt5
instead.

An easy way to install it is through Homebrew:

    $ brew install qt5

This will work fine for most DB4S development.  The only downside is a lack of
debugging information on the Qt function calls themselves.

So, if you experience some kind of crash in DB4S, a stacktrace won't let you
productively double click (in Qt Creator) on any **Qt function calls**.  Doing
that will just open an assembler view on the output, which is generally not useful.

To compile Qt5 with debugging information included isn't difficult.  It's just a
bit more time consuming.  The official Qt instructions are here:

&nbsp; &nbsp; https://doc.qt.io/qt-5/osx-building.html

Or you can cheat, and copy the options from the Homebrew formula:

&nbsp; &nbsp; https://github.com/Homebrew/homebrew-core/blob/master/Formula/qt5.rb

If you copy the Homebrew formula options, make sure you replace the `-release` line
with `-debug-and-release` so debugging information gets kept.

It's also useful to use more than one thread when compiling.  Do that by adding a
`-j` option to the `make` command line.  eg `make -j6` to compile with 6 threads in
parallel.  This speeds up Qt compile time significantly.  6 threads are fine for a
quad core CPU, use more threads (or less) depending on how many cores you have in
your system.

## Build DB Browser for SQLite

Follow the [steps for Ubuntu](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Compiling-on-Ubuntu-16.04-with-Qt-Creator#build-db-browser-for-sqlite).

Then, uncheck the `Add build library search path to DYLD_LIBRARY_PATH and DYLD_FRAMEWORK_PATH` option from the `Run` section in the `Projects` tab:

![qtcreator](https://user-images.githubusercontent.com/5748627/40748162-2a8f4e50-6468-11e8-8de9-17a005557fe6.jpg)
