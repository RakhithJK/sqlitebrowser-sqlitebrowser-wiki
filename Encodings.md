By default, DB Browser for SQLite displays text in UTF-8 encoding (which includes ASCII as subset). But your data could be stored in other encodings, like ISO-8859-1 or IBM851. In that case, the encoding has to be indicated to the data browser, otherwise the cell contents could be displayed as ''BLOB''. That can be done in this way:

* Click with left button in the column header and choose 'Set encoding' or 'Set encoding for all tables'.
* In the dialog window, choose the proper encoding for the data and click OK.
* Save the [[project|Project Files]] to remember this setting.
