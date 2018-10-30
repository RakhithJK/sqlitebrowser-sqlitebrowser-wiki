Project files (*.sqbpro) contain settings and options that are 'outside' normal database files, for example, filter options for the 'Browse Data' tab, previously opened SQL tabs in the 'Execute SQL' tab and various PRAGMA settings.

Normally when you open a database (*.db, *.SQLite) file, DB4S shows you the first table in the 'Browse Data' tab, resets any filters (so shows you all the available records), resets any PRAGMAs, and closes any SQL tabs in the 'Execute SQL' tab.  This can be frustrating if you perform the same actions on the same database repeatedly.  Instead, you can use project files to store these settings.

## Saving A Project File

Open a database as normal, and set the required filters, and open SQL tabs to display/set necessary records as required.  From the 'File' menu select 'Save Project'.

![File | Save Project](https://snag.gy/FGx3gM.jpg)

You will be prompted to save a *.sqbpro file.  A default filename will be the database name.  (The extension '.sqbpro' will be automatically suffixed.)

![File | Save Project](https://snag.gy/ixfEwS.jpg)

## Loading A Project File

Loading a project file automatically loads the database it is linked to, so you do not need to open a database and then open the project file.  Simply click on 'File' and select 'Open Project'.

![File | Open Project](https://snag.gy/bn1WzU.jpg)

The database will be automatically opened, the last tab you were viewing will be selected, any filters used on the 'Browse Data' tab will be applied (and records refreshed to show these), SQL tabs will be reopened on the 'Execute SQL' tab, and any PRAGMA options will be set.

## Saved Settings and Format
The complete list of settings saved in a project file are the following (version 3.11):
* The main database file and any attached database file.
* PRAGMA values that are not saved in the database itself.
* Currently selected tab
* "Database Structure" tab: column widths and expanded items 
* "Browse Data" tab:
  * Currently browsed table
  * For each table, the following attributes: Show Row Id option, encoding, column for X axis in [[Plot Dock]], [[Unlock View Primary Key option|Views]]; and the following lists of column properties:
    * Sort columns and sort directions 
    * [[Column widths|Resizing Columns]]
    * Applied [[Filters|Using the Filters]]
    * [[Display Formats]]
    * Hidden columns
    * Selected columns for Y axis for [[Plot Dock]]
* "Execute SQL" tab: name and content of editor tabs and currently selected editor tab.

The project files are written in XML and you can write them yourself, provided that you follow the same format as written by DB4S. This is a formatted example for the version 3.11:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<sqlb_project>
  <db path="/home/mgr/sqlitebrowser/pitchfork.db" foreign_keys="1" case_sensitive_like="1" temp_store="0" wal_autocheckpoint="1000" synchronous="2"/>
  <attached/>
  <window>
    <current_tab id="1"/>
  </window>
  <tab_structure>
    <column_width id="0" width="300"/>
    <column_width id="1" width="0"/>
    <column_width id="2" width="100"/>
    <column_width id="3" width="1509"/>
    <column_width id="4" width="0"/>
    <expanded_item id="0" parent="1"/>
    <expanded_item id="1" parent="1"/>
    <expanded_item id="2" parent="1"/>
    <expanded_item id="3" parent="1"/>
  </tab_structure>
  <tab_browse>
    <current_table name="reviews"/>
    <default_encoding codec=""/>
    <browse_table_settings>
      <table schema="main" name="artists" show_row_id="0" encoding="" plot_x_axis="" unlock_view_pk="">
        <sort>
          <column index="2" mode="0"/>
        </sort>
        <column_widths>
          <column index="2" value="243"/>
        </column_widths>
        <filter_values/>
        <display_formats/>
        <hidden_columns/>
        <plot_y_axes/>
      </table>
      <table schema="main" name="content" show_row_id="0" encoding="" plot_x_axis="" unlock_view_pk="">
        <sort>
          <column index="0" mode="0"/>
        </sort>
        <column_widths>
          <column index="2" value="626"/>
        </column_widths>
        <filter_values/>
        <display_formats/>
        <hidden_columns/>
        <plot_y_axes/>
      </table>
      <table schema="main" name="genres" show_row_id="0" encoding="" plot_x_axis="" unlock_view_pk="">
        <sort>
          <column index="0" mode="0"/>
        </sort>
        <column_widths/>
        <filter_values>
          <column index="2" value="&lt;&gt;NULL"/>
        </filter_values>
        <display_formats/>
        <hidden_columns/>
        <plot_y_axes/>
      </table>
      <table schema="main" name="labels" show_row_id="0" encoding="" plot_x_axis="" unlock_view_pk="">
        <sort>
          <column index="0" mode="0"/>
        </sort>
        <column_widths/>
        <filter_values>
          <column index="2" value="=self-released"/>
        </filter_values>
        <display_formats/>
        <hidden_columns/>
        <plot_y_axes/>
      </table>
      <table schema="main" name="reviews" show_row_id="0" encoding="" plot_x_axis="pub_year" unlock_view_pk="">
        <sort>
          <column index="13" mode="0"/>
        </sort>
        <column_widths>
          <column index="1" value="75"/>
          <column index="2" value="190"/>
          <column index="3" value="137"/>
          <column index="4" value="137"/>
          <column index="5" value="68"/>
        </column_widths>
        <filter_values>
          <column index="7" value=""/>
          <column index="13" value=""/>
        </filter_values>
        <display_formats>
          <column index="2" value="upper(&quot;title&quot;)"/>
          <column index="3" value=""/>
        </display_formats>
        <hidden_columns/>
        <plot_y_axes>
          <y_axis name="score" line_style="0" point_shape="5" colour="#004586" active="1"/>
        </plot_y_axes>
      </table>
      <table schema="main" name="years" show_row_id="0" encoding="" plot_x_axis="" unlock_view_pk="">
        <sort>
          <column index="0" mode="0"/>
        </sort>
        <column_widths/>
        <filter_values/>
        <display_formats/>
        <hidden_columns/>
        <plot_y_axes/>
      </table>
    </browse_table_settings>
  </tab_browse>
  <tab_sql>
    <sql name="SQL 1">SELECT avg("score"), pub_year FROM reviews GROUP BY pub_year;</sql>
    <current_tab id="0"/>
  </tab_sql>
</sqlb_project>
```