## Update translation strings

**Try to do this step a few days before the release, so translators have time!**

* Update the .ts files under src/translations, then commit them to the master branch:

```
$ lupdate src/src.pro
$ git add src/translations/*.ts
$ git commit
```

* Notify the translators of the new strings + the tentative release date.


## Update application version numbers (and commit + push the changes)

Create a new branch in git, based upon the new release version:

    $ git checkout -b v3.9.x

The `x` on the end as the minor version number is correct, as for branches
all of the `3.9` series code will go into this same branch.  eg 3.9.0, 3.9.1, etc.

### In the new version branch

1. Update the "CFBundleShortVersionString", "CFBundleGetInfoString", and "CFBundleVersion" strings in `src/app.plist`.  Use the full version for these.  eg `3.9.0`
2. In `src/version.h`, update the version number components as appropriate.
3. In `installer/windows/variables.wxi`, update the version number components.

### In the master branch

1. Update the "CFBundleShortVersionString" and "CFBundleVersion" version strings in src/app.plist.  The new version string needs to be the latest release number + .99 on the end.  eg if the new release is for version 3.9, then the master branch version of this string will be `3.9.99`.
2. In `src/version.h`, update the version number components as appropriate.
3. In `installer/windows/variables.wxi`, update the version number components.

## Build the application

* The .dmg file should be automatically signed by our build script.  If that doesn't work for some reason, it can be done manually with:
    $ codesign --sign "${DEV_ID}" --verbose --deep --keychain "/Library/Keychains/System.keychain" DB*.dmg
* The windows binaries need to be manually signed with our certificate.  Martin does that, so upload the binaries to our nightly server and let him know:
  * https://nightlies.sqlitebrowser.org/win32-prerelease/
  * https://nightlies.sqlitebrowser.org/win64-prerelease/
* We really need to investigate making our own PortableApp version, instead of loading the work onto John Haller

## Verify the versions of SQLCipher being bundled

* Install the new OSX .app from the .dmg, start it, and check the SQLCipher version in the About dialog.  If this isn't at least 3.28.0 then something has gone wrong and needs to be fixed.

## (TODO?) Build an AppImage version of the release

* Verify it works with a new (minimal) install on (say) CentOS 7 x64

## Add a good changelog

1. Use the Milestone "closed issues" thing for the initial text
2. Then add links and make the text nicer sounding (where possible and not too difficult)

## Publish the release

1. Make sure we have both the Windows and OSX packages on there first
2. Add the new release info to the History section of the source repo README.md, and the about page of the website
3. Update the version numbers in the [issue reporting template](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/.github/ISSUE_TEMPLATE.md)

## Update website

* It's the [sqlitebrowser/website](https://github.com/sqlitebrowser/website/) repo.
  * Uses Hugo and blogdown
1. Update the download links
2. Add a blog entry
3. Add the new release to the releases section on the About page

## Notify packagers

Email, or ping via GitHub, our packagers to let them know about the new release:

* deepsidhu1313 (Ubuntu)
* @lbartoletti (FreeBSD)
* Arch?
* Gentoo?
* RHEL/Fedora?

## Updates stats counters

1. Create cronjob scripts to get the daily download count for the new release binaries

## Notify people

1. Update currentrelease file
   * In the [master branch of our GitHub repo](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/currentrelease)
   * On our [download server cluster](https://github.com/sqlitebrowser/db4s_cluster_downloader/blob/cef5ae7ffa65c1be448a55a619ff5df7a569c72f/main.go#L364)
2. Email John Haller to let him know
3. Send a tweet about it (retweet that from our personal accounts)
4. Email SQLite Users &lt;sqlite-users@mailinglists.sqlite.org&gt; mailing list about the new release
5. Update the MacOS X Homebrew formula, and the Homebrew Cask, for the new version
6. Add a mention of the new release on the [SQLCipher forums](https://discuss.zetetic.net/c/sqlcipher)
7. Do a "News" item release on our SourceForge page (but don't upload the files there)
8. Let the maintainers of the [Chocolatey package](https://chocolatey.org/packages/sqlitebrowser/ContactOwners) know