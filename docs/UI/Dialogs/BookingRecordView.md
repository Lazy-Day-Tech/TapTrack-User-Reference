# BookingRecordView

## Overview

BookingRecordView is a @Composable function designed to display detailed information about a booking record and allow the user to perform actions such as checking in or checking out the booking. It includes several UI components that display booking details, rental information, waivers, and booking notes. The view also incorporates NFC scanning functionality for checking in bookings, with the status of the booking being updated accordingly.
### Key Features:
- **Booking Details Display:** Shows organizer's name, formatted phone number, booking date and time, associated rentals, signed waivers, and editable booking notes.
- **Check-In and Check-Out Functionality:**
    - **Check-In Mode:** Allows users to scan an NFC tag to check in the booking, updating the status to "Checked-In" and recording the start time.
    - **Check-Out Mode:** Enables users to confirm the check-out, updating the status to "Returned" and recording the end time.
- **Dynamic Button States**: The availability of check-in and check-out buttons adjusts based on the current booking status to prevent redundant actions.
- **NFC Integration:** Initiates NFC scanning upon user action in check-in mode, associating the scanned tag ID with the booking and updating its status accordingly.
- **Manual Check-In:** Allows users to manually enter raft numbers to get its according assigned NFC UUID in the raftMap if NFC scan fails
- **Override:** Allows users to skip Check-In/Check-Out counters and customer acknowledgement in order to perform action
## Parameters

```kotlin
BookingRecordView(
    initialBooking: Record,           // The initial booking record to display.
    isCheckInMode: Boolean,           // Determines if the dialog is in check-in mode.
    isCheckOutMode: Boolean,          // Determines if the dialog is in check-out mode.
    onConfirm: () -> Unit,            // Callback invoked when the user confirms the action.
    onDismiss: () -> Unit,            // Callback invoked when the dialog is dismissed.
    nfcManager: NfcManager            // The NFC manager for managing NFC tag scans.
    navController: NavController      // The Navigation manager
)
```

### Parameters Explained:
- `initialBooking`: The initial booking record that is displayed in the dialog. It contains all the details about the booking including the organizer's name, phone number, booking date/time, rentals, waivers, and booking notes.
- `isCheckInMode`: A boolean flag that determines if the dialog is in "Check-In" mode. When true, the user can check-in the booking.
- `isCheckOutMode`: A boolean flag that determines if the dialog is in "Check-Out" mode. When true, the user can check-out the booking.
- `onConfirm`: A lambda function that is executed when the user confirms the action, either checking in or checking out the booking.
- `onDismiss`: A lambda function that is executed when the dialog is dismissed by the user.
- `nfcManager`: The NFC manager responsible for initiating and managing NFC scans for check-in actions.
- `navController`: The Navigation manager responsible for navigation routing 

## Functionality
### Booking Details

The dialog shows various details about the booking, such as:
- Name of the organizer
- Phone Number of the organizer, formatted properly
- Booking Date and Time
- Rentals associated with the booking
- Waivers signed for the booking
- Booking Notes 
- Customer Flags (Discrete flags)

### Check-In and Check-Out
- If isCheckInMode is true, the user can scan an NFC tag to check in the booking. The booking status will be updated to "Checked-In" once the number of scannable rentals associated with the booking have been met. The start time and Google Display name of the user that checked the booking in will be recorded.
- If isCheckOutMode is true, the user can confirm the check-out of the booking. The booking status will be updated to "Returned," and the end time and Google Display name of the user that checked the booking in will be recorded.

### Enabling/Disabling Buttons
- The Check-In and Check-Out buttons are conditionally enabled or disabled based on the current status of the booking. For example:
    - If the booking is already checked-in or returned, the check-in button will be disabled.
    - If the booking is not checked-in yet, the check-out button will be disabled.

### Modify Booking Notes
Allows note modification via a dialog. Changes are stored until confirmation, with immediate backend updates for already processed bookings.

### NFC Scanning

The NFC scanning process plays a critical role in managing check-ins within the `BookingRecordView`. Here's how it works:

1. **Initiation**: 
   - The NFC scan is initiated when the user clicks on the Check-In/Check-Out button while in check-in or check-out mode.

2. **Tag Scanning**:
   - Once an NFC tag is successfully scanned, its UUID (Universal Unique Identifier) is captured and stored in `nfcPayload`.
   - All scanned tags are accumulated in `nfcPayloads`, ensuring all required items for a booking are checked in.

3. **Booking Update**:
   - The booking record is updated with the scanned NFC tag IDs.
   - If all necessary items have been scanned, the booking status changes to "Checked-In" or "Returned" respectively.

4. **Check-Out Considerations**:
   - In check-out mode, the system ensures that each scanned tag corresponds to items already checked in.
   - If a tag is not found in the list of checked-in items or has been scanned more than once (indicating it's already checked out), appropriate error messages are displayed.


### Confirmation

1. **Confirm Button**:
   - **Functionality**: 
     - When clicked, this button updates the booking status to either "Checked-In" or "Returned," depending on whether the user is in check-in or check-out mode.
   
   - **Check-In Mode**:
     - If all required NFC tags are scanned and validated, the booking status transitions to "Checked-In."
     - Before confirming BowYak rentals or during storm warnings, users must acknowledge any associated risks. This ensures customer awareness and consent.

   - **Check-Out Mode**:
     - The button checks that all items listed for check-out have corresponding scanned tags.
     - If all conditions are met, the booking status is updated to "Returned."

2. **Dismiss Button**:
   - **Functionality**: 
     - Allows users to cancel the current action without making any changes to the booking record.
     - Closes the dialog, returning control to the user and preserving existing data states.


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
- **BasicSnackbar**: Custom UI component used to warn user if both NFC scan and ManualInput fails

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
