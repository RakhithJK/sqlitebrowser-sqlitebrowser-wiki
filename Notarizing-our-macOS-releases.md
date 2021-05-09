These are the steps I followed today (2021-05-9), to successfully Notarize our DB4S 3.12.2 release

# macOS notarization steps


1. Build the app as per normal


2. Sign the app:

   ```
   codesign --sign "${DEV_ID}" --verbose --deep --force --keychain "/Library/Keychains/System.keychain" \
     --options runtime --timestamp DB\ Browser\ for\ SQLite.app
   ```


3. Verify the signing worked properly

   ```
   codesign -vvv --deep --strict "DB Browser for SQLite.app"
   ```


4. Zip the app

   *Use* the right-click Finder option for this, as both the command line "zip" utility and "ditto" seem to screw things up


5. Notarize the app

   ```
   xcrun altool --notarize-app --file DB\ Browser\ for\ SQLite.app.zip --primary-bundle-id "net.sourceforge.sqlitebrowser" \
     -u "Your Apple ID username goes here"
   ```


6. Check the status of all notarization requests

   ```
   xcrun --notarization-history 0 -u "Your Apple ID username goes here"
   ```


7. If the notarization request was successful, then staple the app

   ```
   xcrun stapler staple DB\ Browser\ for\ SQLite.app
   ```


8. Verify the stapling worked

   ```
   xcrun stapler validate DB\ Browser\ for\ SQLite.app
   ```


9. Create a .dmg of the app

   ```
   mv DB\ Browser\ for\ SQLite.app ~/appdmg/
   cd ~/appdmg
   appdmg --quiet 3.12.2.json DB\ Browser\ for\ SQLite.dmg
   ```


10. Notarize the dmg

   ```
    xcrun altool --notarize-app --file DB\ Browser\ for\ SQLite.dmg --primary-bundle-id "net.sourceforge.sqlitebrowser" \
      -u "Your Apple ID username goes here"
   ```


11. Check the status of all notarization requests

   ```
    xcrun --notarization-history 0 -u "Your Apple ID username goes here"
   ```


12. If the notarization request was successful, then staple the dmg

   ```
    xcrun stapler staple DB\ Browser\ for\ SQLite.dmg
   ```


13. Verify the stapling worked

   ```
    xcrun stapler validate DB\ Browser\ for\ SQLite.dmg
   ```