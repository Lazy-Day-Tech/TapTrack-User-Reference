# Progress/Loading Indicators
A collection of graphical elements/animations to display loading states

---

### StandardCircularProgressIndicator

A circular progress indicator used to show ongoing operations that are indeterminate in nature, such as data loading or processing.

#### Parameters
- None

#### Returns
- A Box containing a circular progress indicator (CircularProgressIndicator) with a custom style:
        The outer box has a white background, a grey border, and rounded corners.
        The CircularProgressIndicator is centered within the box and uses a blue color (ColorScheme.LDBlue).

#### Usage Example

```kotlin
StandardCircularProgressIndicator()
```

> This will display a circular progress indicator that can be used as a loading spinner.

---

### StandardSearchProgressIndicator

A linear progress indicator used to display the progress of a task, like a search operation or any process that provides a progress value.
#### Parameters
- `progress (Float)`: A value between 0 and 1 representing the progress of the task (e.g., 0.5 for 50% completion).

#### Returns
- A LinearProgressIndicator that shows progress horizontally:
    - The progress is represented as a floating-point number.
    - The progress bar is blue (ColorScheme.LDBlue) with a grey background (ColorScheme.LDGrey).

#### Usage Example

```kotlin
StandardSearchProgressIndicator(progress = 0.5f)
```

> This will display a linear progress bar at 50% progress.

---

### StandardProgressDialog

A dialog that shows a message along with a circular progress indicator, typically used for operations requiring user attention, such as loading data or performing a background task such as updating backend information.
#### Parameters
- `message (String)`: The message to be displayed in the dialog, typically explaining the operation in progress.

#### Returns
- A Box containing a card that displays a message and a circular progress indicator.
    - The card has a white background, rounded corners, and a light grey border.
    - Inside the card, the message is displayed at the top, followed by a divider and the circular progress indicator.

#### Usage Example

```kotlin
StandardProgressDialog(message = "Loading data...")
```

> This will display a dialog with the text "Loading data..." and a circular progress indicator below it.
Example Usages
StandardCircularProgressIndicator

---