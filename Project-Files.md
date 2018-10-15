Project files (*.sqbpro) contain settings and options that are 'outside' normal database files, for example, filter options for the 'Browse Data' tab, previously opened SQL tabs in the 'Execute SQL' tab and various PRAGMA settings.

Normally when you open a database (*.db, *.SQLite) file, DB4S shows you the first table in the 'Browse Data' tab, resets any filters (so shows you all the available records), resets any PRAGMAs, and closes any SQL tabs in the 'Execute SQL' tab.  This can be frustrating if you perform the same actions on the same database repeatedly.  Instead, you can use project files to store these settings.

## Saving A Project File

Open a database as normal, and set the required filters, and open SQL tabs to display/set necessary records as required.  From the 'File' menu select 'Save Project'.

![File | Save Project](https://snag.gy/FGx3gM.jpg)

You will be prompted to save a *.sqbpro file.  A default filename will be the database name.  (The extension '.sqbpro' will be automatically suffixed.)

![File | Save Project](https://snag.gy/ixfEwS.jpg)

## Loading A Project File

Loading a project file automatically loads the database it is linked to, so you do not need to open a database and then open the project file.  Simply click on 'File' and select 'Open Project'.

![File | Open Project](https://snag.gy/bn1WzU.jpg)

The database will be automatically opened, the last tab you were viewing will be selected, any filters used on the 'Browse Data' tab will be applied (and records refreshed to show these), SQL tabs will be reopened on the 'Execute SQL' tab, and any PRAGMA options will be set.
