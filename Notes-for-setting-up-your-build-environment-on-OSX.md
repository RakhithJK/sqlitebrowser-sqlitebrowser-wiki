These are some rough notes, prior to making a full document.

## Qt

Because we maintain compatibility with both Qt4 and Qt5, DB4S developers generally
build against Qt4.  This ensures no Qt5-only code is added until we've decided to
move to Qt5 only.

An easy way to install Qt4 is through Homebrew:

    $ brew install qt

This will work perfectly fine for most DB4S development.  The only downside to it
is the lack of debugging information on the Qt function calls themselves.  So, if
you experience some kind of crash in DB4S, a stacktrace won't let you productively
double click (in Qt Creator) on any Qt function calls.  Doing that will just open
an assembler view on the output, which is generally not useful.

To compile Qt4 with debugging information included isn't difficult.  It's just a
bit more time consuming:

    $ brew install openssl
    $ git clone git://code.qt.io/qt/qt.git
    $ cd qt
    $ ./configure -prefix $HOME/Qt4 -debug-and-release -opensource -confirm-license -fast -system-zlib \
        -qt-libtiff -qt-libpng -qt-libjpeg -nomake demos -nomake examples -cocoa -openssl-linked \
        -I/usr/local/opt/openssl/include -L/usr/local/opt/openssl/lib -arch x86_64 -no-webkit
    $ make -j6
    $ make -j1 install

The above configures Qt4 appropriately (using options copied from the Homebrew build),
compiles it using 6 threads (the `-j6`), then installs it into a `Qt4` subdirectory
under your home directory.

The `-j1` on the `make install` line is important.  The Qt4 docs mention a race
condition in the install logic, making any use of a higher -j number there a bad
idea.