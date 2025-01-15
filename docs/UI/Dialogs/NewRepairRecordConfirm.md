# NewRepairRecordConfirm
## Overview

NewRepairRecordConfirm is a composable function designed to display a confirmation dialog for creating a new repair record. It allows users to review the details of the repair record, including the repair notes, raft number, rental type, status, and current date. It also integrates NFC functionality to scan and register a unique NFC tag UUID associated with the repair record.
## Key Features
- Displays Repair Record Details: Shows the rental type, raft number, repair notes, creation date, and status of the repair record.
- NFC Integration: Supports NFC tag scanning, capturing and validating NFC UUIDs.
- Confirm and Cancel Actions: Provides options for confirming the creation of the repair record or going back to the previous screen.
- Warnings and Alerts: Shows warnings if an invalid or uninitialized NFC tag is detected and prompts the user before overwriting an existing NFC UUID.

## Parameters
- onCreate: (LocalDateTime) -> Unit
    - Type: (LocalDateTime) -> Unit
    - A callback to be executed when the user confirms the creation of the repair record. It takes the current date and time as a parameter.
- onDismiss: () -> Unit
    - Type: () -> Unit
    - A callback to dismiss the confirmation dialog, typically used when the user clicks the "Go Back" button.
- repairNotes: String
    - Type: String
    - The repair notes associated with the record.
- raftNum: String
    - Type: String
    - The raft number associated with the repair record.
- rentalType: String
    - Type: String
    - The type of rental associated with the repair record.
- defaultStatus: String
    - Type: String
    - The default status of the repair record (e.g., "Pending", "In-Repair").
- nfcUUID: String
    - Type: String
    - The NFC UUID associated with the repair record. If it's empty, it indicates that no NFC tag is registered.
- nfcManager: NfcManager
    - Type: NfcManager
    - The NFC manager object used to handle NFC tag scanning. It listens for NFC tag events and captures payload data.

## State Variables
- nfcActive: Tracks whether NFC is currently active (i.e., whether an NFC UUID is registered).
- nfcPayload: Holds the NFC tag data when a tag is scanned.
- showInvalidTag: Displays a warning if the scanned NFC tag is invalid.
- showUninitializedTagWarning: Displays a warning if no NFC tag is scanned.
- didScan: Tracks whether an NFC scan has been initiated.
- showActiveTagWarning: Displays a dialog asking the user if they want to overwrite the existing NFC tag UUID.

## UI Elements
1. Title and Repair Details
    - Displays the title "Confirm Repair Record" and details such as the rental type, raft number, repair notes, and creation date.

2. NFC Tag Status
    - Indicates whether NFC is active, based on the presence of an NFC UUID. It also provides the option to scan an NFC tag if no valid tag is currently registered.

3. Status Display
    - Displays the current status of the repair record (e.g., "Pending", "In-Repair").

4. Confirm and Cancel Buttons
    - Provides a "Create" button to confirm the repair record creation, and a "Go Back" button to cancel and dismiss the dialog.

5. Active NFC Tag Warning
    - If the NFC UUID is already registered, a dialog appears asking the user if they want to overwrite the existing tag UUID.

## Logic
### NFC Tag Scanning
The function listens for NFC tag scans using the nfcManager.tags flow. When an NFC tag is detected, it checks if the tag is valid:
- If the tag is empty, a warning is shown to indicate that no tag was scanned.
- If the tag is invalid (not a valid UUID), an invalid tag warning is shown.

### NFC Tag Overwriting Warning

If an NFC tag is already associated with the repair record (i.e., nfcUUID is not empty), the user is warned before overwriting the existing NFC tag. The dialog gives the option to either overwrite the existing tag or cancel the action.
Record Creation

When the user clicks "Create", the current date and time are passed to the onCreate callback, triggering the creation of the repair record.
Dismissing the Dialog

The "Go Back" button triggers the onDismiss callback, allowing the user to cancel the action and close the dialog.
### Example Usage

```kotlin
val nfcManager = NfcManager(context) // Initialize NfcManager

NewRepairRecordConfirm(
    onCreate1 = Unit, // Placeholder for future use
    onCreate = { currentDate -> 
        // Handle the creation of the new repair record
    },
    onDismiss = { 
        // Handle dialog dismissal
    },
    repairNotes = "Repair note details",
    raftNum = "12345",
    rentalType = "4-person raft",
    defaultStatus = "In-Repair",
    nfcUUID = "123e4567-e89b-12d3-a456-426614174000",
    nfcManager = nfcManager
)
```