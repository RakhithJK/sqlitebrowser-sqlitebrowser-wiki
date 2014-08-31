## Update application version numbers (and commit + push the changes)

1. In the master branch, update the "CFBundleShortVersionString" and "CFBundleVersion" version strings in src/app.plist.  The new version string needs to be the latest release number + .99 on the end.  eg if the new release is for version 3.4, then the master branch version of this string will be 3.4.99.
2. In the new git version branch, update the "CFBundleShortVersionString" and "CFBundleVersion" version strings in src/app.plist.  The new version string needs to be the latest release number + .0 on the end.  eg if the new release is for version 3.4, then the master branch version of this string will be 3.4.0.
3. In the new git version branch, CMakeLists.txt file, update the APP_VERSION, MAJOR_VERSION, MINOR_VERSION, PATCH_VERSION, CPACK_PACKAGE_VERSION_MAJOR, CPACK_PACKAGE_VERSION_MINOR, and CPACK_PACKAGE_VERSION_PATCH place holder strings with the new release number.  eg APP_VERSION with "3.4.0", MAJOR_VERSION with "3", MINOR_VERSION with "4", and PATCH_VERSION with "0".
4. In the new git version branch, update the version numbers in src/gen_version.h.

## Translation strings?

* Is there anything we need to do for the translated strings?

## Build the application

* Build the application package files, and add them to the draft Release
* We really need to investigate making our own PortableApp version, instead of loading the work onto John Haller

## Add a good changelog

1. Use the Milestone "closed issues" thing for the initial text
2. Then add links and make the text nicer sounding (where possible and not too difficult)

## Publish the release

1. Make sure we have both the Windows and OSX packages on there first
2. Add the files to SourceForge as well (1/2 our downloads still come from there)
3. Add the new release info to the README.md file in both the master and version branches.  Releases section

## Update website

* It's the gh-pages branch in git
1. Update the button links for the downloadable files
2. Add a line to the News piece (keep max of 3 lines?)
3. Add the new release to the Releases list

## Notify people

1. Update currentrelease file in master branch
2. Email John Haller to let him know
3. Send a tweet about it (retweet that from our personal accounts)
4. Email SQLite Users &lt;sqlite-users@sqlite.org&gt; mailing list about the new release
5. Update the MacOS X Homebrew formula, and the Homebrew Cask, for the new version
