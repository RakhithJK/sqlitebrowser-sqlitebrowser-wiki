# Introduction

DB Browser for SQLite can be downloaded with SQLCipher support on Mac OSX and Windows, or if you compile it yourself you can get support on Linux. 

You can get more information on SQLCipher from [https://www.zetetic.net/sqlcipher/](https://www.zetetic.net/sqlcipher/) or their GitHub repository at [https://github.com/sqlcipher/sqlcipher](https://github.com/sqlcipher/sqlcipher).

# Encrypting

You can only encrypt an existing database, so if you want a new encrypted database you first need to create a new database file and then encrypt it.

Providing you have a SQLCipher version of DB Browser for SQLite you simply need to select "Set Encryption" from the "Tools" menu and enter your chosen password.

# Third Party Support

There are many third party components that will read/write SQLite databases, but there is no standard encryption method used, if they support encryption.  This means that a database encrypted with SQLCipher via DB Browser for SQLite may not be able to be opened in another application, and vice versa - SQLCipher only recognises 256-bit AES, so databases encrypted in other applications may not be able to be decrypted.  If this is the case, DB Browser for SQLite will display the message, "Invalid file format".

## Platform Support

SQLCipher has broad platform support for with C/C++, Obj-C, QT, Win32/.NET, Java, Python, Ruby, Linux, Mac OS X, iPhone/iOS, Android, Xamarin.iOS, and Xamarin.Android.

# What are "Raw keys"?

As a rule of thumb, most users will probably use a normal passphrase.

    e.g. if they want to encrypt a database that keeps track of their weight,
         exercise times or whatever

Applications and libraries might prefer using raw keys for their data.

    e.g. the data files of a Unity game

The normal passphrase is a feature SQLCipher offers to allow easy-to-remember passwords.  As far as I (@MKleusberg) know these passwords then get translated into a raw key internally.

Now imagine you want to open a database from some application that encrypted it using the raw key method.

    i.e. skipping the SQLCipher passphrase feature

DB4S would ask you for the password to the database and, since there is no 'normal passphrase', you could only enter the raw key that you happen to know.

Without the `Raw key` option, SQLCipher would take your raw key, interpret it as a normal passphrase and translate it into some key that corresponds to this passphrase.

But of course this translation doesn't yield the encryption key for the database.

By setting the `raw key` mode this translation step is deactivated.

This means the key you enter is used as-is to decrypt the database, so SQLCipher won't interfere by making a key of your key, instead of using it directly.

# Bypass the password prompt using a dotenv file

You can make DB4S automatically open an encrypted database file by creating a file named `.env` right next to the database file, specifying the password and optional settings.

---

**Be aware that this means having the password in plaintext right next to the database! Use this optional feature at your own risk.**

---

The required format of the contents of the file is:

```
<database_file_name> = <password>
[<database_file_name>_<setting> = <value>]
```

where:
- `<database_file_name>` is the exact name of the database file, including the extension,
- `<password>` is the password of the database,
- `<setting>` is the name of the setting, which can be one of:
    + `keyFormat`:
        * `0` for passphrase
        * `1` for raw key
    + `pageSize`
    + `kdfIter`
    + `hmacAlgorithm`
    + `kdfAlgorithm`
    + `plaintextHeaderSize`
- `<value>` is the value of the respective setting and
- all the setting lines are optional.

So a file for an SQLCipher 4 encrypted database with default settings would look like:

```
myDatabase.sqlite = AStr0ngPa??w0rd
```

and for one with custom settings would look like:

```
anotherDatabase.sqlite = AStr0ng3rPa??w0rd
anotherDatabase.sqlite_pageSize = 2048
anotherDatabase.sqlite_kdfIter = 128000
```

For your convenience, here are the current defaults:
- SQLCipher 3:
    + `pageSize` = `1024`
    + `kdfIter` = `64000`
    + `hmacAlgorithm` = `SHA1`
    + `kdfAlgorithm` = `SHA1`
    + `plaintextHeaderSize` = `0`
- SQLCipher 4:
    + `pageSize` = `4096`
    + `kdfIter` = `256000`
    + `hmacAlgorithm` = `SHA512`
    + `kdfAlgorithm` = `SHA512`
    + `plaintextHeaderSize` = `0`
