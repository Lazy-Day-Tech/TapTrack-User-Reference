# BookingRecordView

## Overview

BookingRecordView is a @Composable function designed to display detailed information about a booking record and allow the user to perform actions such as checking in or checking out the booking. It includes several UI components that display booking details, rental information, waivers, and booking notes. The view also incorporates NFC scanning functionality for checking in bookings, with the status of the booking being updated accordingly.
### Key Features:
- Displays booking details such as name, phone number, booking time, rentals, waivers, and notes.
- Supports the ability to check in and check out bookings.
- Utilizes NFC scanning to register check-ins.
- Allows users to modify booking notes.
- Dynamically enables/disables check-in and check-out buttons based on booking status.
- Displays an informative dialog with actionable buttons.

## Parameters

```kotlin
BookingRecordView(
    initialBooking: Record,           // The initial booking record to display.
    isCheckInMode: Boolean,           // Determines if the dialog is in check-in mode.
    isCheckOutMode: Boolean,          // Determines if the dialog is in check-out mode.
    onConfirm: () -> Unit,            // Callback invoked when the user confirms the action.
    onDismiss: () -> Unit,            // Callback invoked when the dialog is dismissed.
    nfcManager: NfcManager            // The NFC manager for managing NFC tag scans.
)
```

### Parameters Explained:
- `initialBooking`: The initial booking record that is displayed in the dialog. It contains all the details about the booking including the organizer's name, phone number, booking date/time, rentals, waivers, and booking notes.
- `isCheckInMode`: A boolean flag that determines if the dialog is in "Check-In" mode. When true, the user can check-in the booking.
- `isCheckOutMode`: A boolean flag that determines if the dialog is in "Check-Out" mode. When true, the user can check-out the booking.
- `onConfirm`: A lambda function that is executed when the user confirms the action, either checking in or checking out the booking.
- `onDismiss`: A lambda function that is executed when the dialog is dismissed by the user.
- `nfcManager`: The NFC manager responsible for initiating and managing NFC scans for check-in actions.

## Functionality
### Booking Details

The dialog shows various details about the booking, such as:
- Name of the organizer
- Phone Number of the organizer, formatted properly
- Booking Date and Time
- Rentals associated with the booking
- Waivers signed for the booking
- Booking Notes which the user can modify

### Check-In and Check-Out
- If isCheckInMode is true, the user can scan an NFC tag to check in the booking. The booking status will be updated to "Checked-In," and the start time will be recorded.
- If isCheckOutMode is true, the user can confirm the check-out of the booking. The booking status will be updated to "Returned," and the end time will be recorded.

### Enabling/Disabling Buttons
- The Check-In and Check-Out buttons are conditionally enabled or disabled based on the current status of the booking. For example:
    - If the booking is already checked-in or returned, the check-in button will be disabled.
    - If the booking is not checked-in yet, the check-out button will be disabled.

### Modify Booking Notes
The dialog allows the user to modify the booking notes. Upon clicking the edit button, the user can modify the notes in a new dialog.

### NFC Scanning
NFC scanning is initiated when the user clicks on the Check-In button in check-in mode. Once an NFC tag is scanned, the booking is updated with the tag ID, and the booking status is changed to "Checked-In."

### Confirmation
The Confirm button updates the booking status to either "Checked-In" or "Returned," depending on the mode (check-in or check-out).
    The Dismiss button allows the user to cancel the action and close the dialog.

## UI Components

The following UI components are used to create the booking record view:
- **AlertDialog**: A modal dialog that displays booking details and allows the user to confirm or dismiss actions.
- **Text**: Used to display text fields such as booking name, phone number, status, and other information.
- **Image**: Displays an image related to the rental.
- **Button**: Provides buttons for confirming check-in/check-out and editing booking notes.
- **OutlinedButton**: Used for the "Go Back" button.
- **Spacer**: Adds spacing between UI elements.
- **Icon**: Displays an icon (e.g., for the edit button).
- **Row and Column**: Layout components to arrange UI elements in a horizontal or vertical manner.

## Helper Functions Used:
- `formatPhoneNumber`: Formats the phone number into a human-readable format.
- `convertTo12Hour`: Converts a 24-hour time format into a 12-hour format with AM/PM.
- `formatDateTime`: Formats the start and end date-time in a user-friendly way.
- `compareTime`: Compares two date-times and provides information about the difference between them.
- `duplicateRentalHandler`: Handles rental data and avoids duplicate rentals.
- `updateBooking`: A function used to update booking details on the server.
- `StandardProgressDialog`: A loading dialog displayed while the booking is being updated.

### Example Usage

```kotlin
BookingRecordView(
    initialBooking = bookingRecord,
    isCheckInMode = true,
    isCheckOutMode = false,
    onConfirm = { 
        // Handle the confirmation action
    },
    onDismiss = { 
        // Handle the dismissal action
    },
    nfcManager = nfcManager
)
```
