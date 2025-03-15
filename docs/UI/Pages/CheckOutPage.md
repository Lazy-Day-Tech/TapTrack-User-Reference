# CheckOutPage
## Overview

CheckOutPage is a composable function that handles the checkout process, allowing users to scan an NFC tag or use a manual input option. It fetches booking information based on the scanned NFC tag and handles various scenarios such as a valid booking match, an invalid or uninitialized NFC tag, or when no booking is found. The page includes dialogs for feedback and user actions, such as booking confirmation or retrying the scan.

## Key Features
- **NFC Tag Scanning**: Users can scan an NFC tag to perform checkout.
- **Manual Search Option**: A manual input option is available for users to search for a booking directly.
- **Booking Retrieval**: Upon scanning a valid NFC tag, the app fetches the corresponding booking record.
- **Error Handling**: Includes error dialogs for uninitialized or invalid NFC tags and when no matching booking is found.
- **Checkout Confirmation**: A dialog confirms successful checkout if the booking is found and matches the tag.
- **Floating Action Button**: A floating action button (FAB) for initiating the NFC scan.

## UI Elements
1. Back Button
    - **Description**: A back button (styled with an arrow icon) is placed at the top left corner of the screen. Clicking this button navigates the user back to the "ModeSelectionPage".
    - **Icon**: ArrowBack (from Icons.AutoMirrored.Filled).
    - **Action**: Navigates to the "ModeSelectionPage".

2. Page Title
    - **Text**: Displays "Check-Out Mode" in a gray color (ColorScheme.LDGrey).
    - **Font Style**: Medium font size (14sp), aligning with the back button on the same row.

3. Manual Search Button
    - **Description**: Positioned at the top-right corner, this button allows users to manually search for a booking by navigating to the "ManualInput/CheckOutPage".
    - **Icon**: A search icon (Res.drawable.search) is displayed on the button.

4. Floating Action Button (FAB)
    - **Description**: A FAB at the bottom center of the screen triggers the NFC scan when clicked.
    - **Icon**: A custom NFC icon (Res.drawable.nfc) is displayed on the FAB.
    - **Action**: Initiates the NFC scan when clicked.

5. Booking Checkout Dialog
    - **Description**: If a valid NFC tag is scanned and a matching booking is found, the app shows a checkout confirmation dialog using the BookingRecordView component.
    - **On Confirm**: Closes the dialog and marks the checkout as complete.

6. Error Handling Dialogs
    - **Invalid Tag**: If the NFC tag is invalid (i.e., not matching the expected format or length), an error dialog (InvalidTagDialog) is shown.
    - **Uninitialized Tag**: If no NFC tag is scanned, a warning dialog (ErrorDialogue) is displayed, indicating that the tag might be uninitialized.
    - **Booking Not Found**: If no booking matches the scanned NFC tag, a "Booking Not Found" dialog (RecordNotFound) is shown, prompting the user to retry.

## Behavior:
- **NFC Scan**: When the user taps the FAB, an NFC scan is initiated.
- **Booking Matching**: If a valid NFC tag is scanned and matches a booking, the checkout success dialog is shown.
- **Error Handling**: Invalid or uninitialized tags trigger corresponding error dialogs.
- **Manual Input**: The user can manually search for a booking by navigating to the manual input screen.