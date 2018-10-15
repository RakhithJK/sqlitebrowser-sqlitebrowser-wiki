# Introduction

A view is a virtual table based on the result-set of an SQL query.  A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.  You can add SQL functions, WHERE, and JOIN statements to a view and present the data as if the data were coming from one single table.

## Example VIEW Statement

    CREATE VIEW view_name AS
    SELECT column1, column2, ...
    FROM table_name
    WHERE condition; 

The primary advantage of a view is that it always shows live data.  When you query a view, it recreates the necessary data, pulling in the data as required.  The main use of a view is incorporating data from numerous tables and viewing it as one table.  This aids debugging data enormously.

# Creating A View

You can create a view from the 'Execute SQL' tab, either by entering a 'CREATE VIEW' SQL statement as above, or by entering the necessary 'SELECT' statements, and clicking the 'Save as View' button in the toolbar.

![Save as View](https://snag.gy/gYAC5O.jpg)

This doesn't save the actual results, but the SQL entered to obtain those results.  If you add additional records this will be shown in the view when it is re-queried.

![Save View](https://snag.gy/mU6u90.jpg)

You will be asked to provide a name for the view.  This can be any descriptive name, but cannot be the same name as an existing view, table or index.

![Database Structure](https://snag.gy/ujEcMl.jpg)

When saved, the view appears in the 'Database Structure' tab in the 'Views' section of the tree.

# Querying A View

![Select View](https://snag.gy/Y7QnqE.jpg)

In the 'Browse Data' tab, select the required view.  The resultant data will be live, pulled from the necessary tables.

# Amending Views

![Copy Create Statement](https://snag.gy/JA97WY.jpg)

There is no GUI currently to amend a view.  However, you can copy the create statement by right-clicking on the view in the 'Database Structure' tab, copying that to the 'Execute SQL' tab, amending as required, and re-saving as a new view.

# Editing Data In A View

Traditionally, the data in a view is 'read only', as the data can potentially be pulled from multiple tables.  As you can use one or more fields from one or more tables, when you edit a record, DB4S has no way of knowing which field in which table you are editing.  However, its possible to edit one particular table if the view contains a unique field in that table (usually the record number) to identify that record.

![Unlocking View](https://snag.gy/3fHiN6.jpg)

From the 'Browse Data' tab, and when browsing a view, right click on the column headings and select 'Unlock view editing'.

![Provide NAme](https://snag.gy/NPXWeG.jpg)

You will be prompted to enter a unique column in the view to identify each row.  Depending on the table in which the field derives from, this may change if you plan to edit multiple fields in the view.

