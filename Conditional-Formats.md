* This feature allows you to configure conditional formats in the Browse Data tab. With this, you can set colours, font, font size, text alignment, and more depending on the values of the cell. It works very similarly to what you might know from your spreadsheet application.

* Conditional formats are set per column and multiple formats can be configured for each column. Conditional formats can select for anything that can be filtered for, e.g. equals, does not equal, less than, more than, LIKE, etc.

* To set a conditional format you can right-click a cell or right-click a filter bar, then click 'Edit Conditional Formats...' to open the dialog. If you are currently filtering the view, you can also right-click the filter bar and click 'Use for Conditional Format' to quickly add a conditional format for the current filter condition.

* Your configured conditional formats are saved to your project files as well.
![condformat](https://user-images.githubusercontent.com/3153504/76456084-c35ca000-63d6-11ea-8d28-7cef9374b9cc.png)

* Additionally there is a new format toolbar which allows you to set formats arbitrarily without giving any condition. This allows you to format the table contents just like a table in your favourite spreadsheet application, e.g. for presentations or printing.
![formatting](https://user-images.githubusercontent.com/3153504/76461572-6ebe2280-63e0-11ea-9f84-af37f97a89a2.png)

Notes: Conditional formats are only available from version 3.12 onwards. See pull request [#1503](https://github.com/sqlitebrowser/sqlitebrowser/pull/1503) and issues [#1815](https://github.com/sqlitebrowser/sqlitebrowser/issues/1815) and [#1976](https://github.com/sqlitebrowser/sqlitebrowser/issues/1976) for background information about this feature.