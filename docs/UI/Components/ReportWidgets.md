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


### PhoneChip (Alpha)
#### Parameters
- `iconColor (Color)`: The color of the phone icon. Defaults to `ColorScheme.LDBlue`.
- `phoneTextColor (Color)`: The color of the phone number text. Defaults to `ColorScheme.LDGrey`.
- `phoneNumber (String)`: The phone number to display.
- `fontFamily (FontFamily)`: The font family for the text. Defaults to `FontFamily.Default`.

#### Returns
A Row styled as a chip that displays a phone icon and a phone number. The chip has a border and padding, and the text is styled with the specified font family and colors.

---

### ValueChip (Alpha)
#### Parameters
- `displayNumber (String)`: The number to display on the chip.
- `chipColor (Color)`: The background color of the chip. Defaults to `ColorScheme.LDGreen`.
- `textColor (Color)`: The color of the text. Defaults to `Color.White`.
- `onClick (()->Unit)`: The callback function to be invoked when the chip is clicked.

#### Returns
A Row styled as a chip that displays a number. The chip has a border, background color, and padding. It is clickable and invokes the provided callback function when clicked.

---

### ValueChipRow (Alpha)
#### Parameters
- `displayNumbers (List<String>)`: A list of numbers to display on the chips.
- `onChipClick ((Int)->Unit)`: The callback function to be invoked when a chip is clicked, with the index of the clicked chip.
- `displayText (List<String>, optional)`: A list of text labels to display above the chips. Defaults to an empty list.
- `modifier (Modifier)`: An optional modifier to customize the layout of the ValueChipRow. If not provided, the widget uses default styling.

#### Returns
A Column containing a row of chips that display numbers. If `displayText` is provided, it displays the text labels above the chips. Each chip is clickable and invokes the provided callback function with the index of the clicked chip.

---

### backButton (Alpha)
#### Parameters
- `onClick (()->Unit)`: The callback function to be invoked when the button is clicked.
- `color (Color)`: The color of the icon and text. Defaults to `ColorScheme.LDGrey`.
- `fontFamily (FontFamily)`: The font family for the text. Defaults to `FontFamily.Default`.

#### Returns
A Row styled as a back button that displays a back icon and the text "Back". The button is clickable and invokes the provided callback function when clicked.

---

### BigDateDisplay (Alpha)
#### Parameters
- `dateTime (LocalDateTime)`: The date and time to display.
- `fontSize (TextUnit)`: The font size of the text. Defaults to `20.sp`.
- `fontWeight (FontWeight)`: The font weight of the text. Defaults to `FontWeight.Bold`.
- `color (Color)`: The color of the text. Defaults to `ColorScheme.LDBlue`.
- `fontFamily (FontFamily)`: The font family for the text. Defaults to `FontFamily.Default`.

#### Returns
A Box containing a Column that displays the date in a formatted string. The text is styled with the specified font size, weight, color, and family.

---