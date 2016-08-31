When installing the Windows 64-bit version on top of a previous 32 bit version, file
associations may not work.
The registry key

'''
 HKEY_CLASSES_ROOT\Applications\sqlitebrowser3.exe\shell\open\command
'''

needs to be changed from "C:\Program Files (x86)..." to "C:\Program Files..."

You can then set up file associations as usual.

---

Manually created Windows file associations were broken again with the 3.9.0 release,
due to it being installed to a new path.  To fix this, either update the existing
file associations, or remove + recreate them.

@chrisjlocke made a screencast showing how.  Download it [here](http://chrisjlocke.co.uk/wp-content/uploads/2016/08/31_0750.mp4).  (It should play fine in any video player - eg VLC).

Issues referencing this:

* https://github.com/sqlitebrowser/sqlitebrowser/issues/279
* https://github.com/sqlitebrowser/sqlitebrowser/issues/745