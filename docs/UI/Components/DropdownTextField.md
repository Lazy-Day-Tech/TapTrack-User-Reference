# DropDownTextField
## Overview

The DropdownTextField is a custom composable component that combines a text field with a dropdown menu. It allows users to select an option from a list of predefined values, while the selected option is displayed inside the text field. The component is designed for use in Android applications that leverage Jetpack Compose.
## Features
- **Selectable options**: Display a list of options to the user in a dropdown menu.
- **Pre-selected option**: The dropdown shows the currently selected option in the text field.
- **Customizable appearance**: Supports custom label text, colors, and styles.
- **Enabled/Disabled states**: The component can be disabled to prevent interaction.
- **Focus behavior**: Opens the dropdown menu when the text field is focused.

## Parameters
- `options (List<String>)`:
    - A list of string values to display in the dropdown menu. Each item represents an option the user can select.

- `selectedOption (String)`:
    - The current selected option. This value is displayed in the text field.

- `onOptionSelected ((String) -> Unit)`:
    - A callback function that gets invoked when a new option is selected from the dropdown. The selected option is passed to this function.

- `label (String)`:
    - A label that appears inside the text field to indicate the purpose of the field.

- `enabled (Boolean, default: true)`:
    - Determines whether the dropdown and text field are interactive. 
    If false, the text field is disabled and no interactions are allowed.
- `Modifier`: allows you to customize the visual appearance of the DropdownTextField. You can pass a `Modifier` object to this parameter to apply additional styles or layout adjustments.
## Example

```kotlin
DropdownTextField(
    options = listOf("Option 1", "Option 2", "Option 3"),
    selectedOption = "Option 1",
    onOptionSelected = { selected -> 
        // Handle option selection
        println("Selected option: $selected")
    },
    label = "Choose an option"
)
```

## Behavior

- Dropdown Interaction
    - The user taps on the text field or icon to open the dropdown menu.
    - The options list is displayed in a dropdown below the text field, allowing the user to select an option.
- Text Field
    - The currently selected option is displayed inside the text field.
    - The text field is read-only; users cannot manually type in it.
- Dropdown Menu
    - The dropdown menu appears when the text field is focused or clicked, and is dismissed when the user selects an option or clicks outside.
- Focus Handling
    - If the text field gains focus (e.g., when clicked), the dropdown menu opens automatically if enabled.
- Icon
    - The dropdown icon (ArrowDropDown) is displayed next to the text field, indicating that the field has a dropdown associated with it.

## Styling

The appearance of the text field and dropdown is customizable through the following parameters:
- Borders and Shapes:
    - The text field and dropdown items are enclosed in a rounded border with a customizable shape.
- Text Colors:
    - The text color inside the text field and dropdown menu is black by default. You can change it by modifying the TextFieldDefaults.textFieldColors properties.
- Indicator Colors:
    - The focused and unfocused indicator colors are customized using ColorScheme.LDBlue for a consistent theme across the component.

## Key Considerations
- The dropdown menu will dismiss automatically when the user selects an option.
- The text field is read-only to prevent manual input and ensure that users can only select from the provided options.
- The dropdown is toggled by clicking either the text field or the arrow icon.

# DropdownImage

The DropdownImage composable displays an icon (either a right or down arrow) based on the state of a dropdown. This component is useful when toggling a dropdown menu, indicating whether the menu is currently expanded or collapsed. It utilizes a MutableState<Boolean> to determine the current state and update the icon accordingly.
## Features
- Dynamic Icon Change: The icon switches between a right arrow (arrow_right) and a down arrow (arrow_down) based on the dropdown's state.
- Styling: The icon is tinted using the LDGrey color from your color scheme and is padded to ensure proper spacing within its container.
- State-Driven: The icon's behavior is controlled by a mutable state, making it ideal for scenarios where the icon needs to update in response to user interaction.

## Usage
### Parameters
- isDropdownActive (MutableState<Boolean>):
- A MutableState representing whether the dropdown is active (expanded). If true, the down arrow is shown; if false, the right arrow is shown. This state is typically updated when the user clicks to toggle the dropdown.

## Behavior
- Arrow Icons
    - When the dropdown is collapsed (isDropdownActive.value == false), the component displays a right arrow (arrow_right).
    - When the dropdown is expanded (isDropdownActive.value == true), the component displays a down arrow (arrow_down).

- State Control
    - The component relies on the isDropdownActive state to determine which icon to display. This state is generally tied to the action of opening or closing a dropdown.

- Styling
    - The icon is given a consistent size using fillMaxSize() and padded by 2.dp for aesthetic spacing.
    - The icon's color is set using ColorScheme.LDGrey to maintain the visual theme of the application.

## Example Visual
- Collapsed Dropdown (Right Arrow)
    - Before the dropdown is opened, the right arrow is shown.
- Expanded Dropdown (Down Arrow)
    - Once the dropdown is open, the down arrow is shown.

## Key Considerations
- The icon changes dynamically based on the dropdown's state, which is passed in as a MutableState<Boolean>.
- You should ensure that the state (isDropdownActive) is properly updated elsewhere in the UI to reflect the correct dropdown state.
- The DropdownImage composable is ideal for use in UI components that toggle visibility or display additional options when clicked.
