These are the steps I followed today (2022-10-23), to successfully Notarize our DB4S nightly releases

# Initial setup

Due to Apple's 2FA requirement for accounts, I needed to generate an "application specific password" for DB4S signing, then store that in a keychain for the nightly build script to use.

* https://support.apple.com/en-au/HT204397 <-- how to generate an application specific password

I created a new keychain to store the app specific password in, as the two default keychains aren't useful to us:

* the `Login` keychain is only available for interactive local logins (not ssh)
* the `System` keychain can't be unlocked over ssh, rendering it useless for our purposes


## Create our own keychain

```
$ security create-keychain
keychain to create: db4s.keychain
password for new keychain: <redacted>
retype password for new keychain: <redacted>
```


## Disable the timeout for the keychain

```
$ security set-keychain-settings db4s.keychain
```

Yep, the timeout is disabled by using *no* options to `set-keychain-settings`, as above.  Yep, this is a bizarre approach. :wink:


## Store our application specific password in our keychain

```
$ xcrun notarytool store-credentials --apple-id "${APPLE_ID}" --team-id "${TEAM_ID}" --keychain ~/Library/Keychains/db4s.keychain-db
```

When running the above command it asks for a profile name (text string), to store the password as.  This "profile name" is used in subsequent commands to retrieve the password from the keychain (`${PROFILE_NAME}` below).


# macOS notarization steps


1. Build and sign the app as per normal

2. Verify the signing worked properly

   Either mount the .dmg file manually:

   ```
   $ hdiutil attach <dmg file>
   $ codesign -vvv --deep --strict /Volumes/some_volume_name/"DB Browser for SQLite.app"
   ```

   Or verify the .dmg itself:

   ```
   $ codesign -vvv --deep --strict <dmg file>
   ```

I don't remember if verifying the .dmg actually checks the .app inside, and the steps I actually took were a much more complicated once-off. :wink:  So I'd recommend using hdiutil attach and manually checking the .app.


3. Notarize the app

   ```
   $ xcrun notarytool submit --apple-id "${APPLE_ID}" --team-id "${TEAM_ID}" --wait --keychain-profile "${PROFILE_NAME}" --keychain ~/Library/Keychains/db4s.keychain-db <dmg file>
   Conducting pre-submission checks for DB Browser for SQLite-arm64-3.12.2.dmg and initiating connection to the Apple notary service...
   Submission ID received
     id: 11111111-2222-3333-4444-555555555555
   Upload progress: 100.00% (23.3 MB of 23.3 MB)   
   Successfully uploaded file
     id: 11111111-2222-3333-4444-555555555555
     path: <full path to your local dmg file>
   Waiting for processing to complete.
   Current status: Accepted..........
   Processing complete
     id: 11111111-2222-3333-4444-555555555555
     status: Accepted
   ```

   In theory, the tool should do the submission then wait around for a result (`Accepted`, `Invalid`, etc).

   If the result is some kind of error, then you can display the log file of the submission (which shows the error(s)) using:

   ```
   $ xcrun notarytool log --keychain-profile "${PROFILE_NAME}" --keychain ~/Library/Keychains/db4s.keychain-db 11111111-2222-3333-4444-555555555555
   ```

   If the notarising was successful, then staple the dmg:

   ```
   xcrun stapler staple <dmg file>
   ```


8. Verify the stapling worked

   ```
   xcrun stapler validate <dmg file>
   ```

At this point, the file is ready to be uploaded for people to use