# Introduction

DB Browser for SQLite can be downloaded with SQLCipher support on Mac OSX, or, if you compile it yourself you can get support on Linux. Currently you cannot have SQLCipher support and hence encrypted databases on Windows.

You can get more information on SQLCipher from [https://www.zetetic.net/sqlcipher/](https://www.zetetic.net/sqlcipher/) or their GitHub repository at [https://github.com/sqlcipher/sqlcipher](https://github.com/sqlcipher/sqlcipher).

# Encrypting

You can only encrypt an existing database, so if you want a new encrypted database you first need to create a new database file and then encrypt it.

Providing you have a SQLCipher version of DB Browser for SQLite you simply need to select "Set Encryption" from the "File" menu and enter your chosen password.