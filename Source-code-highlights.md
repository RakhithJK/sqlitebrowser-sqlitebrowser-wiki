This page is intended for high-level source code parts explanations.

### Project files saving/loading

All project related code is defined in `MainWindow`.

There is a data structure called `BrowseDataTableSettings` defined in the header file, which is used to store all sort of things. We have a map named `browseTableSettings` defined in the header file too, which maps one table to one of these structs; so there is an instance of this struct for each table.

This map is just stored as-is in the project files. The loading code takes place in the `loadProject` method and the saving code takes place in the `saveProject` method, and we use the `operator<<` and `operator>>` for these. These operators are overloaded in the header file as `friend` functions. So in short, as long as the information is stored in the `browseTableSettings` map, all you need to do update are the `operator<<` and `operator>>` functions and it will also be written to the project files.
