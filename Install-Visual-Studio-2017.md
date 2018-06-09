# Install Visual Studio 2017

Starting with Visual Studio 2017 Microsoft [no longer provides .iso images](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) for Visual Studio. Instead, they offer a web installer that can be used to install Visual Studio or create a [local cache](https://docs.microsoft.com/en-us/visualstudio/install/install-vs-inconsistent-quality-network) (called layout) of the installation for later use.

A full download of Visual Studio including recommended and optional downloads is a huge download (more than 100GB). That's probably why they stopped offering .iso images. Visual Studio now splits itself into dozens of *components* and some of these components are grouped into *workloads* to make installation easier (more on this later).

In this wiki we will show you how to download and install Visual Studio 2017 using the web installer. We will only download the required components (around 1GB) that are needed to successfully build **DB Browser for SQLite**.

First, go to https://www.visualstudio.com/downloads/ and click **Free download** under "Visual Studio Community 2017". This will download Visual Studio Installer (only 1.5MB) bootstrapper (`vs_Community.exe`).

[[images/vs2017-01.jpg]]

Run the bootstrapper (`vs_Community.exe`) to install **Visual Studio Installer**.

[[images/vs2017-02.jpg]]

This will download *the installer* (not Visual Studio) that will be used to install Visual Studio. So wait for it to finish downloading.

[[images/vs2017-03.jpg]]

The installer is now downloaded and ready to use.

[[images/vs2017-04.jpg]]

Click **Install** under Visual Studio Community 2017.

[[images/vs2017-05.jpg]]

Now we need to select the required components to install. By default, **Visual Studio core editor** is selected. This is the absolute minimum to install Visual Studio and it cannot be removed. It is basically just a code editor, nothing more.

[[images/vs2017-06.jpg]]

Select **Desktop development with C++** to install this workload. It will include some optional components as well.

[[images/vs2017-07.jpg]]

Keep **VC++ 2017 version 15.7 v14.14 latest v141 tools** only and uncheck the rest.

[[images/vs2017-08.jpg]]

Click **Install** and wait for it to finish installing.

[[images/vs2017-09.jpg]]

Congratulations! :tada:

[[images/vs2017-10.jpg]]

Visual Studio 2017 is now installed and ready to use. :smiley: 
