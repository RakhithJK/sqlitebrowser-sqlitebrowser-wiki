### Previous page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-12-—-Compile-DB4S-using-MSVC).

## 13. Install DB4S locally

To install DB4S locally from MSVC, you'll need to manually create the `C:\Program Files\sqlitebrowser` directory first, and change it's ownership permissions so that all users can write to it:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/090.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/091.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/092.png)

Switch to the Security tab of the Properties dialog

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/093.png)

Click the Edit button and you should see the following where you first select "Users" and then can set their permissions

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/094.png)

Create a 'C:\dev\dependencies' directory, and copy the MSVC 2013 redistributable file (vcredist_x64.exe) in there:

![xyz](http://i.imgur.com/1fW5VBd.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/097.png)

![xyz](http://i.imgur.com/xbDlRZ7.png)

![xyz](http://i.imgur.com/plJZ6Mt.png)

Select "INSTALL" in the solution explorer pane on the right:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/089.png)

Then choose "BUILD" → "Build INSTALL" from the top menu structure:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/112.png)

The "Build" process should finish, with the message "Build: 1 succeeded, 0 failed, [etc]" in the Output pane at the bottom:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/13-install_db4s/100.png)

DB4S should now be installed into C:\Program Files\sqlitebrowser.  Try launching it, to confirm everything is working as expected. :)

## Next page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-14-—-Create-DB4S-package).