# RepairRecordView
## Overview

RepairRecordViewV2 is a composable function used to display and manage repair records in a dialog format. It allows users to view the details of a repair record, modify it (if not already marked as "Repaired"), and take actions such as confirming changes, deleting the record, or marking it as repaired. It also integrates with NFC functionality to scan and capture NFC tag data during the process.
### Key Features
- **Editable Repair Record Fields**: Allows modification of repair notes and status, depending on whether the record is already marked as "Repaired".
- **NFC Integration**: Scans NFC tags and captures the data associated with a repair record.
- **Record Update and Deletion**: Supports updating the repair record’s status and notes, or deleting the record.
- **Confirmation Dialogs**: Provides confirmation dialogs before deleting or marking a record as repaired.
- **Coroutines and Background Operations**: Uses Kotlin coroutines for asynchronous operations like updating and deleting records, ensuring smooth user interactions.

## UI Elements
1. Title Bar with Repair Type and Raft Number
    - Displays the repair type and raft number.
    Includes an edit button (if the record is not marked as "Repaired"), which opens the editing mode.

2. Repair Notes
    - A TextField where users can enter or modify the repair notes. The field is enabled only if the record is editable.

3. Creation and Resolution Dates
    - Displays the creation and resolution dates of the repair record. The resolution date is only shown if it is available.

4. Status Dropdown
    - A DropdownTextField for selecting the repair status from a list of options ("Broken", "In-Repair", "Repaired"). The status can only be modified if the record is editable.

5. Confirm and Delete Buttons
    - The dialog includes a confirm button for saving the changes and a delete button for removing the record. If the record is already marked as "Repaired", the status cannot be edited.

6. Confirmation Dialogs
    - Delete Record Confirmation: When the user clicks "Delete", a confirmation dialog is shown to ensure the user wants to delete the record.
    - Confirm Repaired: If the user tries to mark a record as "Repaired", a confirmation dialog is displayed to ensure that they want to finalize the repair. Once confirmed, the record’s resolution date is updated.

## Logic
### NFC Tag Scanning

RepairRecordViewV2 listens for NFC tag scans through the nfcManager.tags flow. If an NFC tag is scanned, its payload is captured and stored in nfcPayload.
### Record Update

When the user clicks "Confirm" after modifying the repair record, the record is updated through the API call (updateRepairRecord). The status, repair notes, and dates are updated.
### Record Deletion

If the user clicks "Delete", the record is deleted after a confirmation prompt using the deleteRepairRecord API call.
### Mark as Repaired

If the user marks the record as "Repaired", the RepairModuleConfirmation dialog appears to confirm the action. If confirmed, the record’s resolution date is set to the current date and time, and the RecordResolvedBy is set to the users google display name. 
