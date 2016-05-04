0 Note for folder structure:    
      /dev/SQLite    
     /git_repos/sqlitebrowser/    
     /git_repos/sqlitebrowser/src   
     /git_repos/sqlitebrowser/libs    
     .....   
1 Download the source package with git client or by "download zip"   
2 Download and install SQLite as https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-%E2%80%94-Step-8-%E2%80%94-Install-SQLite    
3 Open the src/src.pro file first, run lupdate, then lrelease    
4 After doing the above, close the src/src.pro file, then open the sqlitebrowser.pro one   
Choose the msvc 2013 64-bit kit for the project (it will ask when you open the .pro file)   
Compile/debug as per normal