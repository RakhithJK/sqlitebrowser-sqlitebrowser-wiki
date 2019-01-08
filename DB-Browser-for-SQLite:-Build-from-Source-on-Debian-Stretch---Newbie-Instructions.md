Instructions for a build newbie for building DB Browser for SQLite on Debian Stretch  (Debian v.9, the current stable version).

Tested on Jan 8, 2019.

## Prerequisites

Check that the following packages are installed. All are available in the normal Debian Stretch repositories.

- ``libsqlite3-0``, ``libsqlite3-dev`` and  ``sqlite3``
- ``git``
- either ``qt5-qmake`` or ``cmake``
- ``make``
- the following pieces of the so-called GNU Compilation Collection (GCC): ``g++``, ``g++-6``, ``gcc`` and ``gcc-6`` (installing ``g++`` should bring the others as dependencies)
- ``qt5-default`` and ``qttools5-dev`` with their dependencies (both version 5.7)

For **building with encryption support**, the following packages are needed instead of the sqlite3 packages:

-  ``libsqlcipher0``, ``libsqlcipher-dev`` and  ``sqlcipher``

**Note 1:** The command line interface (``sqlite3`` or ``sqlcipher``) is not absolutely required for the build process itself, but is useful for e.g. testing how to encrypt a database. 


**Note 2:** If you need the latest version of SQLite3 (or SQLCipher) or SQLite3 with some other options than included in the standard Debian packages, you will need to compile SQLite3 (or SQLCipher) yourself.

**Note 3:** If you later on want to remove your own ``DB Browser for SQLite`` build, or if you want to easily remove and reinstall different build versions, install also the ``checkinstall`` package. See [this StackOverflow question](https://stackoverflow.com/questions/1439950/whats-the-opposite-of-make-install-i-e-how-do-you-uninstall-a-library-in-li).

### Installing from command line:

Update the repository information:
```
    $ sudo apt-get update
```
Install a package or packages (examples):
```
    $ sudo apt-get install g++
    $ sudo apt-get install qt5-default qttools5-dev
```

Alternatively, use e.g. ``Synaptic Package Manager`` (but it seemed to have some problems with bringing in correctly the required dependencies for the ``GCC`` packages).


## Steps

### Step 1: Clone (=copy) the Github repository to your computer

Open a terminal session and navigate to the directory to which you want to copy the source files. For instance, your home directory. Or a temp directory created under the home directory.

Then run

```
    $ git clone https://github.com/sqlitebrowser/sqlitebrowser
```

This creates a directory ``sqlitebrowser``, fetches the files from Github and saves them to the directory and its subdirectories.

### Step 2: Run cmake or qmake

In this step you can use either ``cmake`` or ``qmake``. Using ``cmake`` produces a nicer-looking log showing percentage completion in the next ``make`` step. Using ``qmake`` produces a very long messy-looking log that does not tell much at least to an uninitiated. Anyway, both will generate the desired end result.


#### Step 2a: If using cmake

Create a directory ``build`` under ``sqlitebrowser`` and navigate to it:

```
    $ cd sqlitebrowser
    $ mkdir build
    $ cd build
```

Then run ``cmake`` in the ``build`` directory. Note the two dots at the end.
```
    $ cmake  ..
```
If building with SQLCipher support:
```
    $ cmake -Dsqlcipher=1 ..
```

This step is quick. It will create a file named ``Makefile`` and various other files needed in the actual build step in the ``build`` directory.

#### Step 2b: If using qmake

Run ``qmake`` in the ``sqlitebrowser`` directory:
```
    $ qmake
```
In addition to the ``Makefile`` file, ``qmake`` also creates a file named ``.qmake.stash`` in the ``sqlitebrowser`` directory. It lists the file locations where ``qmake`` searches for programmes and libraries.

### Step 3: Run make

#### Step 3a: If using cmake

If you used ``cmake`` in the previous step, run ``make`` in the ``build`` directory:
```
    $ make
```
This takes a few minutes. The log shows progress as percentage completion and gives somewhat understandable information òn what is being done.

If everything goes well, the log ends with the following lines:

```
    [100%] Linking CXX executable sqlitebrowser
    [100%] Built target sqlitebrowser
```

The appr. 6 MB (7 MB if compiled with SQLCipher support) ``sqlitebrowser`` binary file now appears in the ``build`` directory together with some other files generated during build.

#### Step 3b: If using qmake

If you used ``qmake`` in the previous step, run ``make`` in the ``sqlitebrowser`` directory:
```
    $ make
```
This takes a few minutes. A loooooooooong undecipherable log runs on the screen.

If everything goes well, the log ends with the following lines:

```
    make[2]: Leaving directory '/home/myusername/sqlitebrowser/src'
    make[1]: Leaving directory '/home/myusername/sqlitebrowser/src'
```

The ``sqlitebrowser`` binary file appears in the ``src`` directory amidst the various source files.


### Step 4: Install your newly built DB Browser for SQLite

#### Step 4a: Normal ``make install``

If using ``cmake``, run the following command in the ``build`` directory. If using ``qmake``, run the following command in the ``src`` directory:
```
    $ sudo make install
```
The following files will be installed:
```
    /usr/local/bin/sqlitebrowser
    /usr/local/share/icons/hicolor/256x256/apps/sqlitebrowser.png
    /usr/local/share/applications/sqlitebrowser.desktop
    /usr/local/share/appdata/sqlitebrowser.desktop.appdata.xml
```

#### Step 4b: Install with ``checkinstall``

Instead of the ``sudo make install`` command, run:

```
    $ sudo checkinstall
```

It will first ask to enter a description for the package. The first line of the description will be shown in Synaptic Package Manager's listing, so you could e.g. enter something like this:
```
    >>DB Browser for SQLite, v3.11.99 (SQLCipher v4.0.1), build date 2019-01-08
```
You can enter several lines of commentary which will show as description in Synaptic - a good way to document the parametres of your build. Press ``return`` twice to end the description.

Then, ``checkinstall`` shows a number of other fields you can change. You should at least change the name, because ``checkinstall`` proposes the name of the directory (=``build``) as the name of the package. You can also update version (also shown in Synaptic) and licence.

Once you accept, ``checkinstall`` will create a ``*.deb`` package in the ``build`` directory and install the files as above. You can then later remove installation with Synaptic or command line as follows, if needed (assuming that you gave ``sqlitebrowser`` as the name of the package):
```
    $ sudo dpkg -r sqlitebrowser
```


### Step 5: Clean up

Now you can delete the ``sqlitebrowser`` directory. It is not needed any more unless you want to repeat the build process with exactly the same source files.

If you created a ``*.deb`` package with ``checkinstall``, move it first somewhere else so you can reinstall exactly the same build later, if needed:
```
    $ sudo dpkg -i /path/to/the/deb/package/name_of_sqlitebrowser_deb_package.deb
```

However, if you did not create a ``*.deb`` package, move the ``install_manifest.txt`` file somewhere else before deleting the ``sqlitebrowser`` directory. It can be used to remove the installation as per instructions in the [StackOverflow question](https://stackoverflow.com/questions/1439950/whats-the-opposite-of-make-install-i-e-how-do-you-uninstall-a-library-in-li).
