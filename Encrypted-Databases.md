# Introduction

DB Browser for SQLite can be downloaded with SQLCipher support on Mac OSX and Windows, or if you compile it yourself you can get support on Linux. 

You can get more information on SQLCipher from [https://www.zetetic.net/sqlcipher/](https://www.zetetic.net/sqlcipher/) or their GitHub repository at [https://github.com/sqlcipher/sqlcipher](https://github.com/sqlcipher/sqlcipher).

# Encrypting

You can only encrypt an existing database, so if you want a new encrypted database you first need to create a new database file and then encrypt it.

Providing you have a SQLCipher version of DB Browser for SQLite you simply need to select "Set Encryption" from the "File" menu and enter your chosen password.

# Third Party Support

There are many third party components that will read/write SQLite databases, but there is no standard encryption method used, if they support encryption.  This means that a database encrypted with SQLCipher via DB Browser for SQLite may not be able to be opened in another application, and vice versa - SQLCipher only recognises 256-bit AES, so databases encrypted in other applications may not be able to be decrypted.  If this is the case, DB Browser for SQLite will display the message, "Invalid file format".

## Platform Support

SQLCipher has broad platform support for with C/C++, Obj-C, QT, Win32/.NET, Java, Python, Ruby, Linux, Mac OS X, iPhone/iOS, Android, Xamarin.iOS, and Xamarin.Android. 