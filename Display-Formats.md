This feature allows the user to change the data in the Browse Data
tab on a per column basis before displaying it. This means even though
the data is stored in format _X_ in the database it can be shown in format
_Y_ in the browser. This should be useful in cases where the original
format _X_ is hard to read or just not useful in a particular case.

For activating the display format you have to right-click on the header
of a column.

[[images/Display-formats-step-1.png]]

Select "Edit display format" to open a dialog which
offers a (limited) list of pre-defined formats.

[[images/Display-formats-step-2.png]]

Select the desired display format from the list.

[[images/Display-formats-step-3.png]]

Click OK and the selected format is then applied to the display of the column.

[[images/Display-formats-step-4.png]]

Some considerations have to be taken into account when using display formats:
* Data is not editable (or only via the Edit Dialog) because it isn't
  transformed back yet.
* Display format customization is supported starting version 3.12.0 (issue [#573](https://github.com/sqlitebrowser/sqlitebrowser/issues/573)).
* There is no indication in the UI for which columns a format has been set.
