## Quiet installation on Windows

DB Browser for SQLite can be installed in "quiet mode" on Windows, for easier deployment to multiple PCs.

This is done by passing `/quiet` to the installer on the command line:

    msiexec /i c:\full_path\to\setup_file\DB.Browser.for.SQLite-3.9.1-win64.exe /quiet

DB Browser for SQLite will then install using default values.

---

### Implementation details

Our silent install capability comes from using the standard MSI (Windows Installer) to create our installers.

You can also override the default values (eg which directory to install to) by providing further options on the command line.
