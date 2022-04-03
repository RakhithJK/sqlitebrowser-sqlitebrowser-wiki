In https://nightlies.sqlitebrowser.org/latest you can find the automatic nightly builds for DB Browser for SQLite, made
from our latest `master` branch source code on GitHub. This means that these builds include the latest developments and bug fixes, not yet released. Nightly builds are usually stable, but from time to time new bugs might appear, which aren't in the stable versions.

Windows
=======

We've moved to providing MSI based installers, instead of the previous
.exe ones.  These new installers include both SQLite and SQLCipher (for
optional encryption):

  * [DB.Browser.for.SQLite-win32.msi](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-win32.msi)
  * [DB.Browser.for.SQLite-win64.msi](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-win64.msi)

Additionally, there's now a .zip version of each. That's useful for
people needing to run DB Browser for SQLite without installing it first.

  * [DB.Browser.for.SQLite-win32.zip](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-win32.zip)
  * [DB.Browser.for.SQLite-win64.zip](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-win64.zip)

If you're not sure which one to get, try the .msi version first. :smile:


macOS
=====

Each build comes in two flavours:

  * One using standard SQLite
  * One using SQLCipher, which provides optional encryption

If you're wanting encryption, make sure you grab a build that has
"SQLCipher" in the file name. :smile:

  * [DB.Browser.for.SQLite.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite.dmg)    
  * [DB.Browser.for.SQLite-sqlcipher.dmg](https://nightlies.sqlitebrowser.org/latest/DB.Browser.for.SQLite-sqlcipher.dmg) (this supports encryption)


Linux
=====

Depending on your distribution, you have a few options. :smile:

* We build an AppImage for every change in the `master` branch:
  * https://github.com/sqlitebrowser/sqlitebrowser/releases/tag/continuous

* Ubuntu and its derivatives have nightly builds available:

  * https://github.com/sqlitebrowser/sqlitebrowser/#nightly-builds-1

* If you're into Snap packages, there are nightly Snap packages too:

  * https://github.com/sqlitebrowser/sqlitebrowser/#snap-packages

If neither of those work for you, then you can build DB4S yourself:

  * https://github.com/sqlitebrowser/sqlitebrowser/blob/master/BUILDING.md#generic-linux-and-freebsd
