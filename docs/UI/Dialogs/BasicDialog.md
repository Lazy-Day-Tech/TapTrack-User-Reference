# Basic Dialog
## Overview

BasicDialog is a composable function that provides a customizable alert dialog. The dialog is typically used for showing messages that require user acknowledgment or dismissal. It features a title, a message, and two action buttons—one for confirming the action and another for dismissing the dialog. This dialog is commonly used for informational messages or alerts.
## Key Features
    - Customizable Title and Message: Allows you to set a title and a message for the dialog.
    - Two Buttons: Provides a "Confirm" button and a "Dismiss" button, each with customizable text.
    - Non-dismissible by Outside Click: The dialog can only be dismissed by clicking the "Dismiss" button or the back button (on Android), but not by clicking outside the dialog.
    - Custom Styling: The dialog buttons are styled with a rounded shape and custom colors.

## Parameters
- `onConfirm: () -> Unit`
    - **Type**: () -> Unit
    - The callback that is executed when the user clicks the "Confirm" button. It allows the dialog to perform an action before dismissing.
- `onDismiss: () -> Unit`
    - **Type**: () -> Unit
    - The callback that is executed when the user clicks the "Dismiss" button. It allows the dialog to be dismissed.
- `title: String`
    - **Type**: String
    - The title text that appears at the top of the dialog. This is typically used to describe the purpose of the dialog (e.g., "Error", "Warning").
- `message: String`
    - **Type**: String
    - The body text that provides further details or the message the user needs to acknowledge.
- `confirmText: String`
    - **Type**: String
    - The text to display on the "Confirm" button. This button is typically used to confirm the user's acknowledgment of the dialog.
- `dismissText: String`
    - **Type**: String
    - The text to display on the "Dismiss" button. This button is used to close the dialog without taking any further action.

## UI Elements
1. Title and Message
    - The dialog contains a title and message, both of which are displayed in a column. The title uses a bold font, while the message uses a normal font weight.
    - **Title**: Typically displays the purpose or context of the dialog (e.g., "Error", "Confirmation").
    - **Message**: Provides the content or details related to the dialog’s purpose (e.g., "Are you sure you want to delete this item?").

2. Confirm and Dismiss Buttons
    - Confirm Button:
        - **Text**: The confirmText parameter controls the text shown on the button.
        - **Action**: When clicked, it triggers the onConfirm callback.
        - **Style**: The button has a rounded shape, with a blue background color (ColorScheme.LDBlue), and white text.
    - Dismiss Button:
        - **Text**: The dismissText parameter controls the text shown on the button.
        - **Action**: When clicked, it triggers the onDismiss callback.
        - **Style**: The button has a transparent background with a border (ColorScheme.LDGrey) and grey text.

3. Dialog Properties
    - Dismissal Behavior:
        - `dismissOnClickOutside = false`: The dialog cannot be dismissed by clicking outside of it.
        - `dismissOnBackPress = true`: The dialog can be dismissed by pressing the back button (on Android).

4. Dialog Shape and Border
    - The dialog has a rounded corner shape with a corner radius of 22.dp and a border on the dismiss button with a width of 1.2.dp.

## Example Usage

```kotlin
BasicDialog(
    onConfirm = {
        // Handle the confirm action
    },
    onDismiss = {
        // Handle the dismiss action
    },
    title = "Delete Item",
    message = "Are you sure you want to delete this item? This action cannot be undone.",
    confirmText = "Yes, Delete",
    dismissText = "Cancel"
)
```

## Behavior:
- **Title**: "Delete Item"
- **Message**: "Are you sure you want to delete this item? This action cannot be undone."
- **Confirm Button**: Text will be "Yes, Delete" and will execute the onConfirm callback.
- **Dismiss Button**: Text will be "Cancel" and will execute the onDismiss callback.