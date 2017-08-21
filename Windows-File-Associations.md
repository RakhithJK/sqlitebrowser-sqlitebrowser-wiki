The Windows file association can be a bit fiddly - sometimes, if you install several copies of DB Browser for SQLite (various nightlies, betas, etc) Windows isn't sure which version you want to use ... and doesn't help by displaying several similar names:
![](https://snag.gy/7eaM8F.jpg)

Sometimes, even telling Windows which 'app' you want to use, it doesn't save it properly, so ignores you.

It is therefore recommended to download and install **NirSoft File Types Manager** (http://www.nirsoft.net/utils/file_types_manager.html).  This is a free utility which easily edits associations.  It works on all versions of Windows, right back to Windows 98.  DB4S doesn't run on Windows 98.... 

After downloading the 91 KB .ZIP file, run the filetypesman.exe - it can be run directly from the .ZIP file.
![](https://snag.gy/6Skrl5.jpg)

Search for either '.db' or '.sqlite' (or whichever file extension you use for SQLite databases)

![](https://snag.gy/6bBmzX.jpg)

Notice how .db and .db3 are associated with different types - sqliteDatabase and SQLite3 database.  File extensions can either have their own explicit associations, or be assigned to a 'group'.  This is where the general confusion and mess comes in.  It is easier to assign to a group, so we'll cover that method first.  

## Creating A New File Type
File Type Man can't edit the file type itself (ironically...) it can just assign extensions TO file types.  Creating a file type is relatively easy though.  Copy this code into a text file called 'sql.reg':
    
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\SQLiteDatabase\shell\open\command]
    @="\"C:\\Program Files\\DB Browser for SQLite\\DB Browser for SQLite.exe\" \"%1\""

Notice how the \ character is an 'escape character' used in conjunction with quotes and backslashes.  So each quote and backslash should be prefixed with an **\**.
Edit the path as required.
Save the file, and double click on it.  Windows will ask if you want to import it.
![](https://snag.gy/TteUYQ.jpg)

Click 'Yes' and on 'OK' on the next confirmation message.

Back to File Type Man, and with the extension you want to edit, remove any actions from the file extensions, by right clicking the action and selecting 'delete' (or selecting it and pressing the [DELETE] button on the keyboard):
![](https://snag.gy/AsDpUn.jpg)

![](https://snag.gy/FJIYy9.jpg)

(note how .sqlite files have yet another file type and explicit associations)

Set the required extensions to have the 'SQLiteDatabase' file type.  Double click the extension and ensure 'UserChoice' is empty:
![](https://snag.gy/UybRHz.jpg)

Right click the extension and select 'Replace File Type for Selected Extension'
![](https://snag.gy/MLuBy3.jpg)

From the 'Select another file type' dialog, select 'SQLiteDatabase'
![](https://snag.gy/AMBGXo.jpg)

Note (as in my example) the file type might be at the top, rather than in alphabetical order.  Just because... (I did say Windows was weird...)

Phew.  Almost there.  Click OK.  
FileTypesMan now shows .db extensions associated with SQLiteDatabases, which has an 'action' pointing to the correct .exe file:
![](https://snag.gy/AJK5zc.jpg)

Repeat this for .sqlite or .db3 - depending on what other file extensions you use.
Double click a .db file to ensure it opens correctly.
![](https://snag.gy/cUHJ2d.jpg)

In future, if you need to change where SQLiteDatabase types open, all you need to do is edit the sql.reg file, double click it, and the changes will take effect immediately.

## Adding Additional Actions
When you double click a '.db' file, it will open the program associated with the 'Open' action.  Its useful (if you've downloaded a beta or nightly version) to have the option of opening a database in that version.  Simply create a new action.
Select the required extension which belongs to a file type (like '.db' in the above example).  Right click in the action area and select 'New Action'.
![](https://snag.gy/YqHbl9.jpg)

![](https://snag.gy/KinOj6.jpg)

Ensure the destination is enclosed in quotes.  This time you don't need the \ escape character.  Don't forget to suffix the .exe file with "%1" - this is a placeholder for the database filename when Windows runs DB4S.
![](https://snag.gy/gvUDCd.jpg)

This now gives you an extra option when right clicking .db or .sqlite files (any extension belonging to the same file type as the one you edited)
![](https://snag.gy/s9Aokq.jpg) 
