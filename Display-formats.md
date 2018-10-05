This feature allows the user to change the data in the Browse Data
tab on a per column basis before displaying it. This means even though
the data is stored in format X in the database it can be shown in format
Y in the browser. This should be useful in cases where the original
format X is hard to read or just not useful in a particular case.

For activating the display format you have to right-click on the header
of a column to open a new dialog for setting the display format which
offers a (limited) list of pre-defined formats.

The selected format is then applied to the display of the column.

Some considerations have to be taken into account when using display formats:
* Data not editable (or only via the Edit Dialog) because it isn't
  transformed back yet.
* You cannot currently customize the list of display formats (issue #573).
* There is no indication in the UI for which columns a format has been set.
* Could _maybe_ be integrated into the import/export etc. for optional
  use.