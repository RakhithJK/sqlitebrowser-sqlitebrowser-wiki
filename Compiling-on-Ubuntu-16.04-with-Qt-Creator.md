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

Screenshots here need renaming, and turned into a useful step-by-step instruction guide:

&nbsp; &nbsp; https://github.com/sqlitebrowser/db4s-screenshots/tree/master/wiki/ubuntu_16.04

### Build DB4S


### Install DB4S

