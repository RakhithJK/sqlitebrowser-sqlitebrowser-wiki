### Abstract

This Wiki page aims at providing a step by step tutorial for non-programmers on how to provide basic debug information on DB4S on Windows. This is particularly relevant for crashes of the application. Sometimes a crash cannot be reproduced on a developer's system and then any extra bits of information are going to be a great help.

### Initial situation

Let's assume you're using either any DB4S release or any DB4S nightly build. Let's further assume that upon some action the application crashes on your system. Whenever that happens, please open an issue. Usually we'll be able to reproduce the error and fix it. But sometimes this doesn't work. Now any bits of information help in finding the source of the issue. However, in case of a crash newer versions of Windows don't provide much information at all. You'll usually get a dialog saying "DB Browser for SQLite has stopped working and needs to close" (or similar).

### Installing WinDbg

There's a free application by Microsoft called WinDbg. If you use Windows 10 you can download it from [this link](https://developer.microsoft.com/en-us/windows/hardware/download-windbg), if you use an older Windows version you can download it from [here](https://developer.microsoft.com/en-us/windows/hardware/windows-driver-kit).

Download and execute the file. The installer will download the actual program files during the installation, so you'll need an Internet connection for that. Just proceed through the installation, clicking 'Next' and 'Accept' where needed. When you get to the dialog that let's you select the programs to install, you can deselect all items except for the "Debugging Tools for Windows" (or similar).

As soon as the installation has finished you should have a new item in your Start Menu to start WinDbg.

### Debugging DB4S

If you want to debug DB4S you'll need to start it through WinDbg. In order to do this, start WinDbg by clicking the new Start menu item. Now open the ```File``` menu and click ```Open executable```. In the dialog navigate to the DB4S application directory and open the ```DB Browser for SQLite.exe``` file.

A couple of messages should appear in the window. As soon as it has stopped the application has been loaded and is ready for debugging. If this is the case open the ```Debug``` menu and click ```Go```. Now DB4S should start and run.

Use the DB4S instance as normal and try to reproduce the crash. This should work as before. As soon as DB4S crashes, WinDbg should print some messages.

From this point you cannot use DB4S anymore because it's in a state right before the actual crash. But you can use WinDbg to examine this state and extract debug information.

### Useful debug information

There's plenty of information WinDbg provides now. What is especially useful depends on the issue we're dealing with. But usually these information provide a good starting point:

* All the messages in the ```Command``` log window.
* The call stack. This can be shown by opening the ```View``` menu and clicking ```Call stack``` [More information](https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/calls-window).