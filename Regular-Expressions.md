Regular expression support in the where clause of a query is a powerful feature of SQLite.

It is a reserved word as part of the language syntax but it is not quite "out of the box", as it requires a function to be hooked at run-time.

DB Browser for SQLite (DB4S) provides this hooked function using a standard regular expression engine from Qt, the GUI framework on which DB4S is built.

Assuming you have a table of products then the following query will return every product where the description ends with "Kg" or "kg".

    select * from Products where Description regexp '(kg|Kg)$'

You can extend this to more complex possibilities, this is just a simple example. If you get the message "no such function: regexp" this means you are either using a version of DB4S prior to 3.6, due for release in April 2015 or you have checked "Disable Regular Expression extension" on the Extensions tab of the Preferences dialog.

It should be noted that the regular expression implementation used is the standard Qt regular expression engine, which is a "rich Perl-like pattern matching syntax".

Useful references:

* <https://www.sqlite.org/lang_expr.html#regexp> - Official SQLite documentation
* <http://en.wikipedia.org/wiki/Regular_expression> - Handy reference and introduction