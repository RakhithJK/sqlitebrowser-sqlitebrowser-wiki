DB Browser for SQLite allows you to plot simple graphs based on table or query data.

The Plot Dock is the place to configure and plot the graphs. The first step is to browse the table that you want use for plotting or execute a query that will give you the data for plotting. If the Plot Dock is not visible use <kbd>Ctrl</kbd>+<kbd>D</kbd> or select the _View | Plot_ menu entry.

[[images/Plot-dock-1.png]]

## Configuring the plot
The upper table in the dock shows the list of columns of the currently browsed table or the just executed query. You can select the columns that you want to be used as X or Y axis for the plot pane below. The table shows detected axis type that will affect the resulting plot. For the Y axis you can only select numeric columns, but for the X axis you will be able to select:
- Date/Time: strings with format "yyyy-MM-dd hh:mm:ss" or "yyyy-MM-ddThh:mm:ss"
- Date: strings with format "yyyy-MM-dd"
- Time: strings with format "hh:mm:ss"
- Label: other string formats. Selecting this column as X axis will produce a Bars plot with the column values as labels for the bars
- Numeric: integer or real values
Double-clicking the Y cells you can change the used color for that graph.

[[images/Plot-dock-2.png]]

The lower pane of the dock will draw a plot when you select the X and Y values above. You can only select an X axis, but you can select as many Y axis as you want for the plot.

[[images/Plot-dock-3.png]]

You can select different line type and point shapes using the lists in the lowest line.

[[images/Plot-dock-4.png]]

## Interacting with the plot

You can use the following action to interact with the plot:

- Click on points to select them in the plot and in the table. Ctrl+Click for selecting a range of points.
[[images/Plot-dock-5.1.png]]

- Use mouse-wheel for zooming and mouse drag for changing the axis range.
[[images/Plot-dock-5.png]]

- Select the axes or axes labels to drag and zoom only in that orientation.
[[images/Plot-dock-6.png]]

- Use the button with arrows in the lowest part to reload all data and reset the plot to zoom 0.
[[images/Plot-dock-7.png]]

## Bar charts

If you select an X column of Label type you will get a bar chart using those values as labels for the bars.

[[images/Plot-dock-10.png]]

Using the context menu you can toggle between stacked and grouped bars and activate the legend.

[[images/Plot-dock-8.png]]

[[images/Plot-dock-9.png]]

[[images/Plot-dock-11.png]]

## Export options
You can export the plot in different image formats using the "Save current plot..." button ![Save current plot...](https://raw.githubusercontent.com/sqlitebrowser/sqlitebrowser/master/src/icons/picture_save.png).

Using the context menu you can:
- print the plot or export it to PDF, selecting the "Print..." option ![Print](https://raw.githubusercontent.com/sqlitebrowser/sqlitebrowser/master/src/icons/printer.png). 
- copy the plot as image to the system clipboard, selecting the "Copy" option ![Copy](https://raw.githubusercontent.com/sqlitebrowser/sqlitebrowser/master/src/icons/page_copy.png).

[[images/Plot-dock-12.png]]