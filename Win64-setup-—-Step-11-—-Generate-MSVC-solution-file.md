### Previous page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-10-—-Clone-the-DB4S-Repository).

## 11. Generate MSVC solution file

Launch the VS2013 x64 Native Tool window again, change to the `C:\git_repos\sqlitebrowser` directory, then run:

    cmake -G "Visual Studio 12 2013 Win64" -Wno-dev

![xyz](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/11-run_cmake/082.png)

Microsoft Visual C++ 2013 will now be able to build the project.

## Next page [here](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-12-—-Compile-DB4S-using-MSVC).