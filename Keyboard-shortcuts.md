## Abstract
This Wiki page aims at listing the more 'hidden' keyboard shortcuts. By this I mean those shortcuts that aren't obviously visible in the menus (e.g. <kbd>Ctrl</kbd> + <kbd>N</kbd> for a new database), that aren't simply <kbd>Alt</kbd> accelerators (e.g. <kbd>Alt</kbd> + <kbd>E</kbd> for clicking the button with the underlined E), and that aren't typical for all GUI application (e.g. <kbd>Tab</kbd> for changing focus).

## Notes
Mac users have to press <kbd>⌘</kbd> instead of <kbd>Ctrl</kbd>

Note that for some key combinations where a symbol is used, you might need to add the <kbd>Shift</kbd> or the <kbd>AltGr</kbd> key to the combination if your keyboard layout requires it to enter the symbol.

For example, <kbd>Ctrl</kbd>+<kbd>"</kbd> is the shortcut for duplicating a row. However, some keyboard layouts need the <kbd>Shift</kbd> key pressed in order to trigger a <kbd>"</kbd>. For example in the Spanish (Spain) and British keyboard layouts, you'll need to actually press <kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>2</kbd>.

---
## Main window

* <kbd>Ctrl</kbd> + <kbd>N</kbd> creates a new database.
* <kbd>Ctrl</kbd> + <kbd>Tab</kbd> go to next tab.
* <kbd>Alt</kbd> + <kbd>0</kbd> restores the window layout used by the application by default (version 3.12).
* <kbd>Alt</kbd> + <kbd>1</kbd> switches to the Database Structure tab.
* <kbd>Alt</kbd> + <kbd>2</kbd> switches to the Browse Data tab.
* <kbd>Alt</kbd> + <kbd>3</kbd> switches to the Edit Pragmas tab.
* <kbd>Alt</kbd> + <kbd>4</kbd> switches to the Execute SQL tab.

* <kbd>Ctrl</kbd> + <kbd>1</kbd>, * <kbd>Ctrl</kbd> + <kbd>2</kbd>, etc. opens the recent file whose position in the list is the number entered in the shorcut.

#### Database Structure tab
* <kbd>Ctrl</kbd> + <kbd>R</kbd> and <kbd>F5</kbd> refresh the database structure.

#### Browse Data tab
* <kbd>Ctrl</kbd> + <kbd>R</kbd> and <kbd>F5</kbd> refresh the currently browsed table.
* <kbd>Ctrl</kbd> + <kbd>"</kbd> duplicates the currently selected record.
* <kbd>Ctrl</kbd> + <kbd>'</kbd> copies the data from the cell above the current (version 3.11).
* <kbd>Ctrl</kbd> + <kbd>PageUp</kbd> and <kbd>Ctrl</kbd> + <kbd>PageDown</kbd> switch the currently browsed table to the previous or the next table.
* <kbd>Delete</kbd> and <kbd>Backspace</kbd> delete the content of the current cell(s), setting it to an empty string.
* <kbd>Alt</kbd> + <kbd>Delete</kbd> and <kbd>Alt</kbd> + <kbd>Backspace</kbd> delete the content of the current cell(s), setting them to NULL.
* <kbd>Tab</kbd> moves to the next cell when the table browser is focused. When being on the last cell, a new row is inserted automatically.
* <kbd>F2</kbd> enters the cell editor mode.

#### Edit Pragmas tab
* <kbd>Ctrl</kbd> + <kbd>R</kbd> and <kbd>F5</kbd> refresh the pragma list.

#### Execute SQL tab
* <kbd>Ctrl</kbd> + <kbd>Return</kbd> executes the SQL commands.
* <kbd>Ctrl</kbd> + <kbd>R</kbd> and <kbd>F5</kbd> execute the SQL commands.
* <kbd>Shift</kbd> + <kbd>F5</kbd> executes the SQL commands on the current line only.

## Edit dialog and edit pane
* <kbd>Ctrl</kbd> + <kbd>Return</kbd> clicks the Apply button.
* <kbd>Insert</kbd> toggles overwrite mode in both text editor and hex editor.
* <kbd>Ctrl</kbd> + <kbd>F</kbd> Opens the Find dialog (version 3.12).
* <kbd>Ctrl</kbd> + <kbd>H</kbd> Opens the Find/Replace dialog (version 3.12).

## Edit Table dialog
* <kbd>Ctrl</kbd> + <kbd>Return</kbd> clicks the OK button.

## SQL, JSON and XML editors
Key | Command
----|----
<kbd>Down</kbd>	|	Move down one line
<kbd>Shift</kbd>+<kbd>Down</kbd>	|	Extend selection down one line
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Down</kbd>	|	Extend rectangular selection down one line
<kbd>Ctrl</kbd>+<kbd>Down</kbd>	|	Scroll view down one line
<kbd>Up</kbd>	|	Move up one line
<kbd>Shift</kbd>+<kbd>Up</kbd>	|	Extend selection up one line
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Up</kbd>	|	Extend rectangular selection up one line
<kbd>Ctrl</kbd>+<kbd>Up</kbd>	|	Scroll view up one line
<kbd>Ctrl</kbd>+<kbd>]</kbd>	|	Move down one paragraph
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>]</kbd>	|	Extend selection down one paragraph
<kbd>Ctrl</kbd>+<kbd>[</kbd>	|	Move up one paragraph
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>[</kbd>	|	Extend selection up one paragraph
<kbd>Left</kbd>	|	Move left one character
<kbd>Shift</kbd>+<kbd>Left</kbd>	|	Extend selection left one character
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Left</kbd>	|	Extend rectangular selection left one character
<kbd>Right</kbd>	|	Move right one character
<kbd>Shift</kbd>+<kbd>Right</kbd>	|	Extend selection right one character
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Right</kbd>	|	Extend rectangular selection right one character
<kbd>Ctrl</kbd>+<kbd>Left</kbd>	|	Move left one word
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Left</kbd>	|	Extend selection left one word
<kbd>Ctrl</kbd>+<kbd>Right</kbd>	|	Move right one word
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Right</kbd>	|	Extend selection right one word
<kbd>Ctrl</kbd>+<kbd>\\</kbd>		|	Move right one word part
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>\\</kbd>	|	Extend selection right one word part
<kbd>Alt</kbd>+<kbd>Home</kbd>	|	Move to start of display line
<kbd>Home</kbd>	|	Move to first visible character in document line
<kbd>Shift</kbd>+<kbd>Home</kbd>	|	Extend selection to first visible character in document line
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>Home</kbd>	|	Extend rectangular selection to first visible character in document line
<kbd>End</kbd>	|	Move to end of document line
<kbd>Shift</kbd>+<kbd>End</kbd>	|	Extend selection to end of document line
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>End</kbd>	|	Extend rectangular selection to end of document line
<kbd>Alt</kbd>+<kbd>End</kbd>	|	Move to end of display line
<kbd>Ctrl</kbd>+<kbd>Home</kbd>	|	Move to start of document
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Home</kbd>	|	Extend selection to start of document
<kbd>Ctrl</kbd>+<kbd>End</kbd>	|	Move to end of document
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>End</kbd>	|	Extend selection to end of document
<kbd>PgUp</kbd>	|	Move up one page
<kbd>Shift</kbd>+<kbd>PgUp</kbd>	|	Extend selection up one page
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>PgUp</kbd>	|	Extend rectangular selection up one page
<kbd>PgDown</kbd>	|	Move down one page
<kbd>Shift</kbd>+<kbd>PgDown</kbd>	|	Extend selection down one page
<kbd>Alt</kbd>+<kbd>Shift</kbd>+<kbd>PgDown</kbd>	|	Extend rectangular selection down one page
<kbd>Del</kbd>	|	Delete current character
<kbd>Backspace</kbd>	|	Delete previous character
<kbd>Ctrl</kbd>+<kbd>Backspace</kbd>	|	Delete word to left
<kbd>Ctrl</kbd>+<kbd>Del</kbd>	|	Delete word to right
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Backspace</kbd>	|	Delete line to left
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>Del</kbd>	|	Delete line to right
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>L</kbd>	|	Delete current line
<kbd>Ctrl</kbd>+<kbd>L</kbd>	|	Cut current line
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>T</kbd>	|	Copy current line
<kbd>Ctrl</kbd>+<kbd>T</kbd>	|	Transpose current and previous lines
<kbd>Ctrl</kbd>+<kbd>A</kbd>	|	Select all
<kbd>Ctrl</kbd>+<kbd>D</kbd>	|	Duplicate selection
<kbd>Ctrl</kbd>+<kbd>U</kbd>	|	Convert selection to lower case
<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>U</kbd>	|	Convert selection to upper case
<kbd>Ctrl</kbd>+<kbd>X</kbd>	|	Cut selection
<kbd>Ctrl</kbd>+<kbd>C</kbd>	|	Copy selection
<kbd>Ctrl</kbd>+<kbd>V</kbd>	|	Paste
<kbd>Ins</kbd>	|	Toggle insert/overtype
<kbd>Return</kbd>	|	Insert newline
<kbd>Tab</kbd>	|	Indent one level
<kbd>Shift</kbd>+<kbd>Tab</kbd>	|	De-indent one level
<kbd>Esc</kbd>	|	Cancel
<kbd>Ctrl</kbd>+<kbd>Z</kbd>	|	Undo last command
<kbd>Ctrl</kbd>+<kbd>Y</kbd>	|	Redo last command
<kbd>Ctrl</kbd>+<kbd>+</kbd>	|	Zoom in
<kbd>Ctrl</kbd>+<kbd>-</kbd>	|	Zoom out
<kbd>Ctrl</kbd> + <kbd>F</kbd>	|	Open the Find dialog (version 3.12) or the search bar in the Execute SQL editors
<kbd>Ctrl</kbd> + <kbd>H</kbd>	|	Open the Find/Replace dialog
