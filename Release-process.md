## Update application version numbers (and commit + push the changes)

Create a new branch in git, based upon the new release version:

    $ git checkout -b v3.9.x

The `x` on the end as the minor version number is correct, as for branches
all of the `3.9` series code will go into this same branch.  eg 3.9.0, 3.9.1, etc.

### In the new version branch

1. Update the "CFBundleShortVersionString", "CFBundleGetInfoString", and "CFBundleVersion" strings in `src/app.plist`.  Use the full version for these.  eg `3.9.0`
2. In `CMakeLists.txt`, update the CPACK_PACKAGE_VERSION_MAJOR, CPACK_PACKAGE_VERSION_MINOR, and CPACK_PACKAGE_VERSION_PATCH place holder strings with the new release numbers.
3. Update the version numbers in src/gen_version.h.


### In the master branch

1. Update the "CFBundleShortVersionString" and "CFBundleVersion" version strings in src/app.plist.  The new version string needs to be the latest release number + .99 on the end.  eg if the new release is for version 3.9, then the master branch version of this string will be `3.9.99`.
2. In `CMakeLists.txt`, update the CPACK_PACKAGE_VERSION_MAJOR, CPACK_PACKAGE_VERSION_MINOR, and CPACK_PACKAGE_VERSION_PATCH place holder strings with the new development version numbers. eg `3.9.99`
3. Update the version numbers in src/gen_version.h to reflect the new development version. eg `3.9.99`

## Translation strings?

* Is there anything we need to do for the translated strings?

## Build the application

* Build the application package files, and add them to the draft Release
* We really need to investigate making our own PortableApp version, instead of loading the work onto John Haller

## Verify the version of SQLite being bundled

* Install the new OSX .app from the .dmg, start it, and check the SQLite version in the About dialog.  If this isn't at least 3.8.6 then something has gone wrong and needs to be fixed.

## Add a good changelog

1. Use the Milestone "closed issues" thing for the initial text
2. Then add links and make the text nicer sounding (where possible and not too difficult)

## Publish the release

1. Make sure we have both the Windows and OSX packages on there first
2. Add the new release info to the README.md file in both the master and version branches.  Releases section

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