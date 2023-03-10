* This feature allows you to configure conditional formats in the Browse Data tab. With this, you can set colours, font, font size, text alignment, and more depending on the values of the cell. It works very similarly to what you might know from your spreadsheet application.

* Conditional formats are set per column and multiple formats can be configured for each column. Conditional formats can select for anything that can be [[filtered|Using the Filters]] for, e.g. equals, does not equal, less than, more than, LIKE, etc.

* To set a conditional format you can right-click a cell or right-click a filter bar, then click 'Edit Conditional Formats...' to open the dialog. If you are currently filtering the view, you can also right-click the filter bar and click 'Use for Conditional Format' to quickly add a conditional format for the current filter condition.
![condformat](https://user-images.githubusercontent.com/3153504/76456084-c35ca000-63d6-11ea-8d28-7cef9374b9cc.png)

* Your configured conditional formats are saved to your [[project files|Project Files]] as well.

* Additionally there is a new format toolbar which allows you to set formats arbitrarily without giving any condition. This allows you to format the table contents just like a table in your favourite spreadsheet application, e.g. for presentations or printing. The formatting toolbar is shown when pressing this button: ![image](https://user-images.githubusercontent.com/13812910/89307009-e121ee80-d670-11ea-8c9b-4ed776915f2b.png)
![formatting](https://user-images.githubusercontent.com/3153504/76461572-6ebe2280-63e0-11ea-9f84-af37f97a89a2.png)

- When using the toolbar, three types of formats can be applied, depending on the selection made before pressing one of the buttons:
  * If the selection covers individual cells (even entire rows) the format is applied only to those cells.
  * If the selection covers entire columns:
    - If the filter is empty, the format applies to all current and future values of the column (a conditional format with an empty condition is added).
    - If the filter is applied, the format applies conditionally to the current and future values passing the filter (a conditional format is added using the filter).

Notes: Conditional formats are only available from version 3.12 onwards. See pull request [#1503](https://github.com/sqlitebrowser/sqlitebrowser/pull/1503) and issues [#1815](https://github.com/sqlitebrowser/sqlitebrowser/issues/1815) and [#1976](https://github.com/sqlitebrowser/sqlitebrowser/issues/1976) for background information about this feature.