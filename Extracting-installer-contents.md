To extract the contents of the MSI installers on Windows use this command (from either PowerShell or the command line):

```
msiexec /a "path\to\installer.msi" /q TARGETDIR=D:\where\to\extract
```

It doesn't need admin rights, and will create a "DB Browser for SQLite" folder inside the folder name you specify.

DB4S will happily run when launched from that folder, as it doesn't really care where it's installed.

This lets you install DB4S into a folder of your choice.  Potentially useful when using a computer you don't have Admin rights on. :smile:

Note: If the application failed to start because it is missing some system files, move the .dll files inside "System64" folder to "DB Browser for SQLite".

Thanks to [@karim](https://github.com/karim) [for this handy tip](https://github.com/sqlitebrowser/dbhub.io/issues/116#issuecomment-425618621). :smile: