These instructions are for setting up a MS Visual Studio 2013 based development environment for DB4S on 64-bit Windows.

The steps and screenshots were all done in a freshly installed Windows 8.1 x64 system.

If you're using a different version of windows, then some things may look slightly different, but the general approach should be the same.  Hopefully. :D

## Requirements

* [CMake 3.6.1 or later](https://cmake.org/download)
  * Under the "Binary distributions" heading, choose the Windows Installer
  * Make sure you get version 3.6.1 or later.  Earlier versions can introduce security problems.
* [GitHub Desktop for Windows](https://desktop.github.com)
  * GitHub Desktop for Windows 7 or later
* [Microsoft Visual Studio Community 2013 Edition Update 5](https://www.visualstudio.com/downloads/download-visual-studio-vs)
  * Click the "Visual Studio 2013" option 1/2 way down the left side → "Community 2013" → ISO
* The latest [Microsoft Visual C++ Redistributable Packages for Visual Studio 2013 (x64)](https://support.microsoft.com/en-us/help/3138367/update-for-visual-c-2013-and-visual-c-redistributable-package)
  * Choose the "vcredist_x64.exe" option
* [Nullsoft Scriptable Install System](http://nsis.sourceforge.net/Download)
  * Version 3.0rc1 or later
* [OpenSSL](https://wiki.openssl.org/index.php/Binaries)
  * From the first link (Shining Light Productions) → Win64 OpenSSL (use latest version)
* [Qt](https://www.qt.io/download-open-source)
  * Choose the Qt Online Installer for Windows
* [SQLite](https://www.sqlite.org/download.html)
  * Under the "Source Code" heading, download the "sqlite-amalgamation" .zip file
  * Version 3.12.2 was used for this guide, but other versions will probably work without issue too

## Steps

**1.** Gather all the required files

As a first step, download all of the files listed in the Requirements section (above), and place them in a single directory.  This is purely for reference purposes, and you can skip this if you want to do it differently. ;)

![Gather the requirements](https://github.com/sqlitebrowser/db4s-screenshots/raw/master/wiki/win64_install/01-install_requirements/000-installation_requirements.png)

**2.** [Install Microsoft Visual Studio 2013](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-2-—-Install-MSVC2013)

**3.** [Create dev & git_repos directories](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-3-—-Create-dev-&-git_repos-directories)

**4.** [Install OpenSSL](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-4-—-Install-OpenSSL)

**5.** [Install CMake](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-5-—-Install-CMake)

**6.** [Install NSIS](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-6-—-Install-NSIS)

**7.** [Install Qt](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-7-—-Install-Qt)

**8.** [Install SQLite](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-8-—-Install-SQLite)

**9.** [Install GitHub Desktop](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-9-—-Install-GitHub-Desktop)

**10.** [Clone the DB4S repository](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-10-—-Clone-the-DB4S-Repository)

**11.** [Generate MSVC solution file](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-11-—-Generate-MSVC-solution-file)

**12.** [Compile DB4S using MSVC](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-12-—-Compile-DB4S-using-MSVC)

**13.** [Install DB4S locally](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-13-—-Install-DB4S-locally)

**14.** [Create a redistributable DB4S package](https://github.com/sqlitebrowser/sqlitebrowser/wiki/Win64-setup-—-Step-14-—-Create-DB4S-package)

When you've finished step 14, you'll have DB4S fully compiled, installed locally, and also a package for it you can distribute. :)