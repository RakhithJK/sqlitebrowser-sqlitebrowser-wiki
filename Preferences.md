## Introduction

DB4S has a number of options to change how the program operates, split across a number of different tabs.
The preferences dialog is opened by clicking 'Edit' on the main menu bar, and selecting 'Preferences'.

![How to access preferences dialog](https://i.imgur.com/0QwbUVR.png)

## General

![General page](https://i.imgur.com/5GVebhK.png)

**Default Location** | When you open a database, DB4S will either remember the last location you opened a database from, or use a default location regardless of where you last opened a database.  

**Language** | This lets you select one of eighteen possible languages - English, Arabic, Chinese, Czech, Dutch, French, German, Italian, Japanese, Korean, Polish, Portuguese, Russian, Spanish, Turkish or Ukranian.  
This wouldn't be possible without the fantastic help of our volunteer translators, so a heartfelt thanks to them.  🥰

**Font size** | This affects the general font size within the application (menus, button text, general labels, etc).

![Example of large fonts](https://i.imgur.com/zjW2FCo.png)

**Toolbar style** | Each tab (database structure, browse data, etc) has a toolbar, and it can be set to be shown in one of four ways.

"Only display the icon"
![only display icon](https://i.imgur.com/GMJLyi2.png)

"Only display the text"
![only display text](https://i.imgur.com/QwuGPbT.png)

"The text appears beside the icon"
![text beside icon](https://i.imgur.com/TafFmdE.png)

"The text appears under the icon"
![text under icon](https://i.imgur.com/kc4GCJm.png)

Each tab can have a different setting.

**Show remote options** |  This hides both the remote panel and the 'Remote' option from the 'View' menu.

**Automatic updates**  | This checks at the start of the application loading whether there is an updated version of DB4S available.  

**DB file extensions**  | Click 'Manage' to amend what file extensions are used in the 'Open database' and 'Save database' dialogs.

![database file extensions](https://i.imgur.com/ePVwcAz.png)

## Database

![Database preferences](https://i.imgur.com/yJ0e5n8.png)

**Database encoding** | This sets the encoding for the database.  
You can test the encoding with this pragma:

`PRAGMA encoding; `

You cannot change the encoding for an existing database. To create a new database with a specific encoding, open an SQLite connection to a blank file, run this pragma:

`PRAGMA encoding = "UTF-8"; `

And then create your database.

**Foreign keys** | This enables internal checks on foreign keys.

** Remove line breaks in schema view ** | This either shows the schema in the 'Database structure' tab on one line or multiple.

![schema on one line](https://i.imgur.com/l1G4K79.png)

compared to

![schema on multiple lines](https://i.imgur.com/lKnWSFh.png)

**Prefetch block size** | This is the number of records returned when viewing a table in the 'Browse data' tab.  If for example a table contains 500 records and this value is set to 100, DB4S will download 100 records.  When the user scrolls down and further records are required, another 'batch' of 100 records is read.  
Setting this to a smaller value makes the initial viewing of tables more responsive, but does require more reads to the database if the grid is heavily scrolled.

**Default field type** | This is the default field type used when creating a new field in a table.

**Database structure font size** | This is the font size used on the 'Database structure' treeview.

**SQL to execute after opening a database** | This SQL will get executed after opening a database, for example, setting a PRAGMA value.


---
(other pages to follow)