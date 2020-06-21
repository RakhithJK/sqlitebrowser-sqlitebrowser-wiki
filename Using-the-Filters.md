## Introduction
When browsing a table a filter row consisting of one input field per column is shown between the table header and the actual table data. These filters allow you to perform quick filters in the currently selected table. The filter is performed as soon as you start typing (you can configure the delay time in **Preferences**).

## Visual example
This section provides some examples for people not familiar with SQL.

Consider the following table:

[[images/filter1.png]]

Say, you want to filter for those records where Field2 contains 'b'. In this case all you need to do is type 'b' in the column's filter:

[[images/30_0935.jpg]]

To filter for 'b' exactly, type '=b'.

[[images/30_1024.jpg]]

Typing '%' can be used as a wild card. 'b%' filters for records starting with 'b', '%b' filters for records ending in 'b' and '%b%' filters for records containing a 'b' at any position (this is the default filter option). You are free to use as many '%' wild cards as you wish and in any combination. Here's an example:

[[images/filter3.png]]

By default, we perform a 'containing' filter for numbers and a 'containing' (non case sensitive) filter for text. You can change the case sensitivity in the Pragmas tab (release 3.11 or later). You can override the default 'containing' search by specifying a comparison operator. You can do so by adding one of the supported operators at the beginning of your query. Have a look at this example where we filter for those records with a value greater than one in Field3:

[[images/filter4.png]]

For a full list of supported operators see the table below. You can also combine multiple filters by just using two or more input fields. By doing so a record must meet all criteria to be still shown:

[[images/filter5.png]]

## Supported operators
There are no default comparison operators used.  When filtering for both numbers and text, wild cards ('%') are allowed. The supported operators are:

|Operator | Description         | Notes
|---------|---------------------|------
|>        | Greater than        | 
|<        | Less than           | 
|>=       | Equal to or greater | 
|<=       | Equal to or less    | 
|=        | Equal to            | Unlike the default behaviour this performs an 100% exact search, i.e. case-dependent and |'%' characters not treated as wild cards but as normal characters.
|<>       | Unequal             | This is the opposite of the '=' operator, that is no wild cards allowed and case-dependent search.

## Range Operators

**NOTE** - Range operators were added to DB4S on the 3.10 release.

When filtering for numbers, a range operator can be specified by using the ~ operator, for example, if filtering for 1 to 5, type '1~5':

[[images/30_1002.jpg]]

## "Use in Filter Expression" helper options
For quick selection of the 'equal to' filter, you can click on any cell with the secondary mouse button and select the "Use as Exact Filter" option in order to get all the rows whose value in that column is the same as the chosen cell. Then you can modify the filter as you want. In the same context menu, you can select all the available filters through the "Use in Filter Expression" submenu using the current cell as value for the operator.

**NOTE** - Release 3.11

## Regular-expression filter
You can filter the column using a [regular expression](https://en.wikipedia.org/wiki/Regular_expression). You only have to enclose the regular expression in '/' characters, like /regexp/. Examples:

|Example | Description         
|---------|---------------------
|`/[a-zA-Z]/` | Contains any letter   
|`/^[a-zA-Z]*$/` | Contains only letters or is empty
|`/Sat\|Sun/`        | Contains the word `Sat` or the word `Sun`
|`/^Sat/`        | Begins with `Sat`
|`/Sun$/`        | Ends with `Sun`

If you want to use a "Containing" filter which has to include `/something/`, just use `\/something\/` to escape the character / and avoid the regular-expression interpretation.

**NOTE** - Only available in our future release 3.12

### Filter in any column
Finally, there is a new field: 'Filter in any column'. Type any number of words here to limit the view to only those rows which contain all these words, no matter in which column. This is super useful when looking for a certain value in a table without knowing in which column it could be.

![find_in_table](https://user-images.githubusercontent.com/3153504/76461862-f99f1d00-63e0-11ea-860b-6cc7dd26e783.png)

**NOTE** - Only available in our future release 3.12

## A look behind the scenes
For those familiar with the SQL syntax the filters are very easy to understand. The filters are translated into the WHERE part of the SELECT statement, joined by AND operators. The default comparison operator is LIKE but can be overridden as described in the table above. We automatically detect a numeric search and omit the quote characters around the filter term in this case while adding them when filtering for text. Single quote characters are automatically escaped and can therefore safely be used in a filter query. In case of any doubt you might want to check the generated SQL statement using the SQL Log panel - just make sure it is set to showing SQL submitted by the 'Application'.
