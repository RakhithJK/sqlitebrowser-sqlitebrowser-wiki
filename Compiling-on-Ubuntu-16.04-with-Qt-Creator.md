## How to compile DB4S on Ubuntu 16.04

Ubuntu 16.04.x comes with an old version of Qt (5.5), causing some bad issues for DB Browser for SQLite (DB4S):

* https://github.com/sqlitebrowser/sqlitebrowser/issues/920
* https://github.com/sqlitebrowser/sqlitebrowser/issues/1001

Not everyone's database experience will have these problems, but if it happens to you there is a solution.

If you compile DB4S yourself using the steps shown below, you'll have a working DB4S without the above known issues.

### Install the Ubuntu software needed for compiling DB4S

    $ sudo apt install build-essential git cmake libsqlite3-dev qt5-default qttools5-dev-tools


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

### Screenshots below are still a work in progress

* They need turning into a useful step-by-step instruction guide, with black borders, callouts and similar added as appropriate:

![Qt Installer introduction screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/00_qt_installer_intro_screen.png)
![Qt Installer account screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/01_qt_installer_account_screen.png)
![Qt Installer welcome screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/02_qt_installer_welcome_screen.png)
![Qt Installer metadata retrieval](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/03_qt_installer_metadata_retrieval.png)
![Qt Installer choose installation directory](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/04_qt_installer_choose_install_dir.png)
![Qt Installer choose components to install - Qt 5.7](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/05_qt_installer_choose_components-5.7.png)
![Qt Installer choose components to install - Qt 5.8](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/05_qt_installer_choose_components-5.8.png)
![Qt Installer license agreement screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/06_qt_installer_license_agreement.png)
![Qt Installer ready to install](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/07_qt_installer_ready.png)
![Qt Installer installing](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/08_qt_installer_installing.png)
![Qt Installer finished](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/09_qt_installer_finished.png)


### Build DB4S

![Qt Creator welcome screen](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/10_qt_creator_welcome_screen.png)
![Qt Creator browse to sqlitebrowser folder](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/11_qt_creator_open_sqlitebrowser_dir.png)
![Qt Creator open sqlitebrowser.pro file](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/12_qt_creator_open_sqlitebrowser_project_file.png)
![Qt Creator only enable the release build](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/13_qt_creator_select_release_build.png)
![Qt Creator back on edit layout](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/14_qt_creator_edit_layout.png)
![Qt Creator shadow build enabled](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/15_qt_creator_shadow_build_enabled.png)
![Qt Creator shadow build disabled](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/16_qt_creator_shadow_build_disabled.png)
![Qt Creator run qmake](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/17_qt_creator_run_qmake.png)
![Qt Creator run build all](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/18_qt_creator_run_build_all.png)
![Qt Creator building](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/19_qt_creator_building.png)
![Qt Creator build finished](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/ubuntu_16.04/20_qt_creator_build_complete.png)


### Install DB4S

