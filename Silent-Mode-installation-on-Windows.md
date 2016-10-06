DB Browser for SQLite can be installed in "silent mode" on Windows, for easier deployment to multiple PC's.

This is done by passing `/S` to the installer on the command line:

    DB.Browser.for.SQLite-3.9.1-win64.exe /S

DB Browser for SQLite will then install using default values.

---

### Implementation details

Our silent install capability comes from using [NSIS](nsis.sourceforge.net) to create our installers.

In theory, overriding the default values (eg which directory to install to) should be possible by providing further options on the command line.

This hasn't been tested (yet), but the NSIS documentation should provide enough details for people wanting to try it.

