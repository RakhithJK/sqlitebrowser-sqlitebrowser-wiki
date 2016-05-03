### Previous page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-11-—-Generate-MSVC-solution-file).

## 12. Compile DB4S using MSVC

Start "Visual Studio 2013" from the Windows menu:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/084.png)

Choose whatever settings and theme appeals to you:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/007.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/008.png)

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/009.png)

Once it's started, choose "FILE" → "Open" → "Project/Solution" from the top menu:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/085.png)

Select the `sqlitebrowser.sln` file in `C:\git_repos\sqlitebrowser`:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/086.png)

Select "ALL_BUILD" in the solution explorer pane to the right, then choose "Build" →
"Build ALL_BUILD" from the top menu: 

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/087.png)

This will take a while to compile DB4S (could be a few minutes), and should finish with a message
like "Build: 7 succeeded, 0 failed, [etc]" in the output pane to the bottom:

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/12-compile_db4s/088.png)

## Next page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-13-—-Install-DB4S-locally).