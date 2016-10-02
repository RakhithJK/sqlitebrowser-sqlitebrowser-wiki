## Update translation strings

**Try to do this step a few days before the release, so translators have time!**

* Update the .ts files under src/translations, then commit them to the release branch:

    $ lupdate src/src.pro
    $ git add src/translations/*.ts
    $ git commit

* Notify the translators of the new strings + the tentative release date.



## Update application version numbers (and commit + push the changes)

Create a new branch in git, based upon the new release version:

    $ git checkout -b v3.9.x

The `x` on the end as the minor version number is correct, as for branches
all of the `3.9` series code will go into this same branch.  eg 3.9.0, 3.9.1, etc.

### In the new version branch

1. Update the "CFBundleShortVersionString", "CFBundleGetInfoString", and "CFBundleVersion" strings in `src/app.plist`.  Use the full version for these.  eg `3.9.0`
2. In `CMakeLists.txt`, update the CPACK_PACKAGE_VERSION_MAJOR, CPACK_PACKAGE_VERSION_MINOR, and CPACK_PACKAGE_VERSION_PATCH place holder strings with the new release numbers.
3. In `src/version.h`, update the version number components as appropriate.


### In the master branch

1. Update the "CFBundleShortVersionString" and "CFBundleVersion" version strings in src/app.plist.  The new version string needs to be the latest release number + .99 on the end.  eg if the new release is for version 3.9, then the master branch version of this string will be `3.9.99`.
2. In `CMakeLists.txt`, update the CPACK_PACKAGE_VERSION_MAJOR, CPACK_PACKAGE_VERSION_MINOR, and CPACK_PACKAGE_VERSION_PATCH place holder strings with the new development version numbers. eg `3.9.99`
3. In `src/version.h`, update the version number components as appropriate.

## Build the application

* Remember to include FTS support on OSX with the `-with-fts` option to Homebrew's SQLCipher install
* Build the application package files, and add them to the draft Release
* Remember to sign them on both OSX and Windows
* We really need to investigate making our own PortableApp version, instead of loading the work onto John Haller

## Verify the version of SQLite being bundled

* Install the new OSX .app from the .dmg, start it, and check the SQLite version in the About dialog.  If this isn't at least 3.8.6 then something has gone wrong and needs to be fixed.

## Add a good changelog

1. Use the Milestone "closed issues" thing for the initial text
2. Then add links and make the text nicer sounding (where possible and not too difficult)

## Publish the release

1. Make sure we have both the Windows and OSX packages on there first
2. Add the new release info to the README.md file in both the master and version branches.  Releases section
3. Update the version numbers in the [issue reporting template](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/.github/ISSUE_TEMPLATE.md)

## Update website

* It's the gh-pages branch in git
1. Update the button links for the downloadable files
2. Add a line to the News piece (keep max of 3 lines?)
3. Add the new release to the Releases list

## Updates stats counters

1. Create cronjob scripts to get the daily download count for the new release binaries

## Notify people

1. Update currentrelease file in master branch
2. Email John Haller to let him know
3. Send a tweet about it (retweet that from our personal accounts)
4. Email SQLite Users &lt;sqlite-users@mailinglists.sqlite.org&gt; mailing list about the new release
5. Update the MacOS X Homebrew formula, and the Homebrew Cask, for the new version
6. Add a mention of the new release on the [SQLCipher forums](https://discuss.zetetic.net/c/sqlcipher)
7. Do a "News" item release on our SourceForge page (but don't upload the files there)