**DB Browser for SQLite** has a command line interface.

Usage: sqlitebrowser [options] [db or [[project file|Project Files]]]

Possible command line arguments:

Short option | Long option | Argument | Description
-- | -- | -- | --
  -h| --help	|	|Show command line options
  -q| --quit	|	|Exit application after running scripts
  -s| --sql	| [file]	|Execute this SQL file after opening the DB
  -t| --table	| [table]	|Browse this table after opening the DB
  -R| --read-only	|	|Open database in read-only mode
  -o| --option	|[group/setting=value]	|Run application with this setting temporarily set to value
  -v| --version	|	|Display the current version
&nbsp;|  	| [file] |Open this SQLite database or project file


## Examples
Open a project file using the font DejaVu for the data browser:

` sqlitebrowser -o databrowser/font=DejaVu sample.sqbpro`

Open the Library DB read-only and browse the table loans:

`sqlitebrowser -R -t loans Library.db`

Open the Aquariums DB, execute the Aquariums_preload.sql file and quit:

`sqlitebrowser -s Aquariums_preload.sql -q Aquariums.db`

## Settings option

The possible values for the argument of the `--option` option can be found in the source file [Settings.cpp](https://github.com/sqlitebrowser/sqlitebrowser/blob/master/src/Settings.cpp). The provided values are applied only to the current session, but you can enter Preferences for saving them for future sessions.

These are sample values for the 3.11 version using the format:
```ini
[group]
setting=value
```
Note: all the color settings can be specified using hexadecimal notation or by their common names (when recognized).

```ini
[%General]
DBFileExtensions=SQLite database files (*.db *.sqlite *.sqlite3 *.db3)
language=es_ES
toolbarStyle=2

[checkversion]
enabled=true

[databrowser]
bin_bg_colour=@Variant(\0\0\0\x43\x1\xff\xff\xfc\xfc\xfc\xfc\xfc\xfc\0\0)
bin_fg_colour=@Variant(\0\0\0\x43\x1\xff\xff\xc0\xc0\xc0\xc0\xc0\xc0\0\0)
blob_text=BLOB
complete_threshold=1000
filter_delay=200
filter_escape=\\
font=DejaVu Sans
fontsize=10
null_bg_colour=@Variant(\0\0\0\x43\x1\xff\xff\xfc\xfc\xfc\xfc\xfc\xfc\0\0)
null_fg_colour=@Variant(\0\0\0\x43\x1\xff\xff\xc0\xc0\xc0\xc0\xc0\xc0\0\0)
null_text=NULL
reg_bg_colour=@Variant(\0\0\0\x43\x1\xff\xff\xfc\xfc\xfc\xfc\xfc\xfc\0\0)
reg_fg_colour=@Variant(\0\0\0\x43\x1\xff\xff!!!!!!\0\0)
symbol_limit=5000

[db]
defaultencoding=UTF-8
defaultfieldtype=0
defaultlocation=/home/mgr
defaultsqltext=
foreignkeys=true
hideschemalinebreaks=true
prefetchsize=50000
savedefaultlocation=2

[editor]
auto_completion=true
error_indicators=true
font=DejaVu Sans Mono
fontsize=9
horizontal_tiling=false
identifier_quotes=0
tabsize=4
upper_keywords=true
wrap_lines=0

[extensions]
disableregex=false
enable_load_extension=false
list=@Invalid()

[log]
fontsize=9

[remote]
active=true
client_certificates=@Invalid()
clonedirectory=/home/mgr/.local/share/sqlitebrowser/DB Browser for SQLite

[syntaxhighlighter]
background_bold=false
background_colour=#fcfcfc
background_italic=false
background_underline=false
comment_bold=false
comment_colour=#008000
comment_italic=false
comment_underline=false
currentline_bold=false
currentline_colour=#ececf5
currentline_italic=false
currentline_underline=false
foreground_bold=false
foreground_colour=#212121
foreground_italic=false
foreground_underline=false
function_bold=true
function_colour=#0000ff
function_italic=false
function_underline=false
identifier_bold=false
identifier_colour=#800080
identifier_italic=false
identifier_underline=false
keyword_bold=true
keyword_colour=#000080
keyword_italic=false
keyword_underline=false
string_bold=false
string_colour=#ff0000
string_italic=false
string_underline=false
table_bold=true
table_colour=#008080
table_italic=false
table_underline=false
```