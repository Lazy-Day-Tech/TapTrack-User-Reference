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
- CheckIn and CheckOut user
- RaftNumbers for valid checked-in rafts
- Start Time
- Float Time

### Check-In and Check-Out
- If isCheckInMode is true, the user can scan an NFC tag to check in the booking. The booking status will be updated to "Checked-In" once the number of scannable rentals associated with the booking have been met. The start time and Google Display name of the user that checked the booking in will be recorded. NFC UUIDs will also be resolved to their RaftNumbers. 
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

