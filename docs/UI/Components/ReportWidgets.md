# Report Widgets
A collection of widgets intended for use in the `ReportPage`

---

### BasicReportWidget
#### Parameters:
- `title (String)`: The title text that will be displayed at the top of the widget.
- `metric (String)`: The metric or data value that will be shown prominently in the widget.

#### Returns:
A Card containing a simple layout with the title at the top, separated by a divider, and the metric value displayed prominently below. The widget is styled with a rounded corner shape and a border.


---

### BigReportWidget
#### Parameters
- `title (String)`: The title of the widget, displayed at the top.
- `metric (String)`: The metric or value to be displayed in a large, bold format at the center.
- `modifier (Modifier?, optional)`: An optional modifier to customize the widget’s layout and appearance. If not provided, the widget uses default styling.

#### Returns
A Card containing a Column with the title at the top, a Divider separating the title from the metric, and the metric displayed in a large font size at the center of the widget. The widget also has a customizable size through the modifier parameter.


---

### StatusList
#### Parameters
- `label (String)`: The label for the row, typically a description of the data being presented.
- `CheckedIn (Int)`: The count of items that are "Checked In".
- `NotCheckedIn (Int)`: The count of items that are "Not Checked In".
- `Returned (Int)`: The count of items that have been "Returned".
- `Total (Int)`: The total number of items.
- `modifier (Modifier?, optional)`: An optional modifier to customize the layout of the StatusList. If not provided, the widget uses default styling.

#### Returns
A Row widget that displays the label, followed by the values for CheckedIn, NotCheckedIn, Returned, and Total. These values are divided by vertical dividers for visual separation. Each value is presented in its own column with equal width. The row layout is designed to fit horizontally across the screen and ensures that each value is easy to read and compare.


---