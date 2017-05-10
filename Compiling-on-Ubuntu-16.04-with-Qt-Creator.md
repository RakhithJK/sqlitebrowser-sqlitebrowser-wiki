## How to compile DB Browser for SQLite on Ubuntu 16.04

Ubuntu 16.04.x comes with an old version of Qt (5.5), causing some bad issues for DB Browser for SQLite (DB4S):

* https://github.com/sqlitebrowser/sqlitebrowser/issues/920
* https://github.com/sqlitebrowser/sqlitebrowser/issues/1001

Not everyone's database experience will have these problems, but if it happens to you there is a solution.

If you compile DB4S yourself using the steps shown below, you'll have a working DB4S without the above known issues.

### Install the Ubuntu software needed for compiling DB4S

    $ sudo apt install build-essential git cmake libsqlite3-dev qt5-default \
           qttools5-dev-tools


### Get the latest DB4S source code

Clone the sqlitebrowser/sqlitebrowser git repo:

    $ git clone https://github.com/sqlitebrowser/sqlitebrowser


### Download and install Qt 5.7 or above

Grab the Qt installer then run it:

```
$ wget http://www.mirrorservice.org/sites/download.qt-project.org/archive/online_installers/2.0/qt-unified-linux-x64-2.0.5-2-online.run
$ chmod 755 qt-unified-linux-x64-2.0.5-2-online.run
$ ./qt-unified-linux-x64-2.0.5-2-online.run
```

The Qt installer will appear:

![Qt Installer introduction screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/00_qt_installer_intro_screen.png)

If you have an (optional) Qt account, you can fill in the details.  Otherwise just click the "Skip" button:

![Qt Installer account screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/01_qt_installer_account_screen.png)

The Qt installer "welcome" screen will appear now.  Click next through the next few screens, until it asks where you want to install:

![Qt Installer welcome screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/02_qt_installer_welcome_screen.png)
![Qt Installer metadata retrieval](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/03_qt_installer_metadata_retrieval.png)

By default, Qt will install into a "Qt" directory in your home folder.  That seems to work well, but if you need to change it for some reason then this screen is where you do it.  Click "Next" once you're happy with the chosen location:

![Qt Installer choose installation directory](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/04_qt_installer_choose_install_dir.png)

This screen will have several component selected by default.  You don't need anything other than `Desktop gcc 64-bit` (or 32-bit if compiling on 32-bit Ubuntu), and Qt Creator (down the bottom).  The rest you can safely de-select before clicking "Next" to continue:

![Qt Installer choose components to install](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/05_qt_installer_choose_components.png)

Agree to the Qt license conditions (if you're ok with them), then click Next:

![Qt Installer license agreement screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/06_qt_installer_license_agreement.png)

Click "Install" to begin the actual installation process:

![Qt Installer ready to install](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/07_qt_installer_ready.png)
![Qt Installer installing](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/08_qt_installer_installing.png)

Qt is now installed.  Leave the "Launch Qt Creator" option enabled so it gets launched automatically when you click "Finish":

![Qt Installer finished](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/09_qt_installer_finished.png)


### Build DB Browser for SQLite

The welcome screen for Qt Creator appears.  Click the "Open Project" button near the middle top, browse into the "sqlitebrowser" folder, then select the `sqlitebrowser.pro` file, and open it:

![Qt Creator welcome screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/10_qt_creator_welcome_screen.png)
![Qt Creator browse to sqlitebrowser folder](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/11_qt_creator_open_sqlitebrowser_dir.png)
![Qt Creator open sqlitebrowser.pro file](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/12_qt_creator_open_sqlitebrowser_project_file.png)

A screen called "Configure Project" will appear.  There are three main checkboxes in it → `Debug`, `Release`, and `Profile`.  Unselect the `Debug` and `Profile` ones, so only `Release` is left enabled.  Then click the `Configure Project` button:

![Qt Creator only enable the release build](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/13_qt_creator_select_release_build.png)

This drops you into the "Edit" layout, with no documents open.  Click the "Projects" button in the left side to switch to the projects menu so we can made further changes:

![Qt Creator back on edit layout](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/14_qt_creator_edit_layout.png)

You're now in the Project layout, showing the "Build Settings".  By default, "Shadow build" is enabled.  We don't want that, so disable it:

![Qt Creator shadow build enabled](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/15_qt_creator_shadow_build_enabled.png)

This screenshot shows "Shadow build" disabled, which is what we want:

![Qt Creator shadow build disabled](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/16_qt_creator_shadow_build_disabled.png)

Now from the Qt Creator menu in the top bar, choose ***Build*** → ***Run qmake***:

![Qt Creator run qmake](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/17_qt_creator_run_qmake.png)

Wait a few seconds for it to finish, then choose ***Build*** → ***Build All***, also from the Qt Creator menu in the top bar:

![Qt Creator run build all](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/18_qt_creator_run_build_all.png)

DB Browser for SQLite is now being built.  It can take a few minutes, so be patient until it completes:

![Qt Creator building](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/19_qt_creator_building.png)

If all goes well, the build should finish without errors, looking somewhat like this:

![Qt Creator build finished](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/20_qt_creator_build_complete.png)

If the build process finishes with an error though, sometimes running ***Build*** → ***Build All*** again (as per the previous step) fixes the problem, and is worth trying.

### Install DB Browser for SQLite

*Still needs writing*