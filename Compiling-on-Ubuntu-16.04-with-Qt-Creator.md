## How to compile DB4S on Ubuntu 16.04

Ubuntu 16.04.x comes with an old version of Qt (5.5), causing some bad issues for DB Browser for SQLite:

* https://github.com/sqlitebrowser/sqlitebrowser/issues/920
* https://github.com/sqlitebrowser/sqlitebrowser/issues/1001

Not everyone's database experience will have these problems, but if it happens to you there is a solution.

If you compile DB4S yourself using the steps shown below, you'll have a working DB4S without the above known issues.