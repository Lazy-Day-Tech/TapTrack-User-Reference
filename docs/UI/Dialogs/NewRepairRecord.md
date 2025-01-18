# New Repair Record D1-4
A collection of dialogs used in the Repair Record Creation process.


## NewRepairRecordD1
- Description: This component provides a dialog with options to create a new repair record either by scanning an NFC tag or entering details manually.
    - Details:
        - The dialog features a title that guides the user to create a new record.
        - It includes two main options: "Scan Tag" for scanning raft NFC tags and "Manual" for manually entering the details.
        - The dialog is styled with a rounded corner shape and dismisses when clicked outside or when the back button is pressed.

## NewRepairRecordD2
- Description: This component provides a dialog for entering a raft number to continue creating a repair record.
    - Details:
        - The dialog prompts the user to enter a raft number with validation to ensure the input is not blank and less than 4 characters.
        - It includes a "Continue" button that activates when the input is valid and a "Go Back" button to dismiss the dialog.
        - The dialog is styled with a rounded corner shape and dismisses when clicked outside or when the back button is pressed.

## NewRepairRecordD3
- Description: This component provides a dialog for entering rental type information for a repair record.
    - Details:
        - The dialog features a dropdown menu with predefined rental options such as "4 Person Raft", "6 Person Raft", and others.
        - It validates that the selected option is not blank and enables the "Continue" button accordingly.
        - Users can go back by clicking the "Go Back" button.
        - The dialog is styled with a rounded corner shape and dismisses when clicked outside or when the back button is pressed.

## NewRepairRecordD4
- Description: This component provides a dialog for entering repair notes for a repair record.
    - Details:
        - The dialog prompts the user to enter repair notes with validation to ensure the input is not blank.
        - It includes a "Continue" button that activates when the input is valid and a "Go Back" button to dismiss the dialog.
        - The dialog is styled with a rounded corner shape and dismisses when clicked outside or when the back button is pressed.

---
Also see [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecordConfirm) for more details on record creation.