## Introduction
When browsing a table a filter row consisting of one input field per column is shown between the table header and the actual table data. These filters allow you to perform quick filters in the currently selected table. The filter is performed as soon as you start typing.

## Visual example
This section provides some examples for people not familiar with SQL.

Consider the following table:

[[images/filter1.png]]

Say, you want to filter for those records where Field2 contains 'b'. In this case all you need to do is type 'b' in the column's filter:

![](http://www.chrisjlocke.co.uk/wp-content/uploads/2017/01/30_0935.jpg)

To filter for 'b' exactly, type '=b'.

![](http://www.chrisjlocke.co.uk/wp-content/uploads/2017/01/30_1024.jpg)

Typing '%' can be used as a wild card. 'b%' filters for records starting with 'b', '%b' filters for records ending in 'b' and '%b%' filters for records containing a 'b' at any position (this is the default filter option). You are free to use as many '%' wild cards as you wish and in any combination. Here's an example:

[[images/filter3.png]]

By default, we perform a 'containing' filter for numbers and a 'containing' (but non case sensitive) filter for text. You can override this behaviour by specifying a comparison operator. You can do so by adding one of the supported operators at the beginning of your query. Have a look at this example where we filter for those records with a value greater than one in Field3:

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

**NOTE** - Range operators were added to DB4S on the [27th Jan 2017](https://github.com/sqlitebrowser/sqlitebrowser/commit/a75f2dac1100c98b387ee5378bcd460b159a02c7), so aren't in the releases prior to that (for exampe not in 3.9.1).  You'll need to grab either a release or [nightly build](nightlies.sqlitebrowser.org/latest) after that.

When filtering for numbers, a range operator can be specified by using the ~ operator, for example, if filtering for 1 to 5, type '1~5':

![](http://www.chrisjlocke.co.uk/wp-content/uploads/2017/01/30_1002.jpg)

## A look behind the scenes
For those familiar with the SQL syntax the filters are very easy to understand. The filters are translated into the WHERE part of the SELECT statement, joined by AND operators. The default comparison operator is LIKE but can be overridden as described in the table above. We automatically detect a numeric search and omit the quote characters around the filter term in this case while adding them when filtering for text. Single quote characters are automatically escaped and can therefore safely be used in a filter query. In case of any doubt you might want to check the generated SQL statement using the SQL Log panel - just make sure it is set to showing SQL submitted by the 'Application'.
