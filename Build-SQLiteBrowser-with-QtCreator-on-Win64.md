## Tools

* Windows 8.1/10 64bit
* Visual C++ Build Tools 2015
* Qt 5.6 with Qt Creator

### 0. Note for folder structure

```
/dev/SQLite    
/git_repos/sqlitebrowser/    
/git_repos/sqlitebrowser/src   
/git_repos/sqlitebrowser/libs    
...
```
   
### 1. Download the source package

Use either a git client or by "download zip" on the GitHub project page

### 2. Download and install SQLite

As per https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-8-—-Install-SQLite

### 3. Update the translations

Open the src/src.pro file first, run lupdate, then lrelease    

### 4. Open the project file

After doing the above, close the src/src.pro file, then open the sqlitebrowser.pro one   
Choose the msvc 2013 64-bit kit for the project (it will ask when you open the .pro file)   
Compile/debug as per normal

## Debugging

Qt on Windows doesn't provide its own debugger, so you'll need to install one yourself.

One option is to install the "Windows SDK" for your version of windows, and ensure the ***Debugging Tools for Windows*** option is enabled when you're installing it.

For Windows 8.1, this is the correct download URL:

&nbsp; &nbsp; https://developer.microsoft.com/en-us/windows/downloads/windows-8-1-sdk