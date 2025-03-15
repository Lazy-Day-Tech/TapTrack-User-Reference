# RepairMenu Documentation

## Overview

The `RepairMenu` is a Composable function in the `org.lazyday.ldclient.ui` package. It provides a user interface for managing repair records, including viewing, adding, and searching for repair records. The menu includes navigation options for different functionalities such as history, in-repair items, search, and NFC scanning.

## Dialogs
- `NewRepairRecordD1`, `NewRepairRecordD2`, `NewRepairRecordD3`, `NewRepairRecordD4`: Dialogs for adding a new repair record in multiple steps.
- `NewRepairRecordConfirm`: A dialog for confirming the creation of a new repair record.
- `RecordNotFound`: A dialog shown when no matching records are found.

## Functionality

### Fetching Repair Records

- Repair records are fetched and stored in the repairItems state when the RepairMenu composable is launched.
NFC Interaction

- The RepairMenu interacts with NFC tags using the nfcManager. When an NFC tag is detected, its payload is processed to find matching repair records.

## Assigning Repair Records
Repair records can be assigned to any authorized user that has already authenticated with the application for the first time. Once a user is authorized, their user display name will display as an option to select from within the "Assign To" dropdown menu. Once confirmed, the user will be listed as the assigned user for the record. The assigned user will then be able to see the record assigned to them within the "Assigned" tab in the Repair Menu

### Navigation
The NavigationRail provides options for navigating between different views:
- Main mode selection page
- Adding a new record
- Searching for a record
- Viewing in-repair items
- Viewing repair history 
- Viewing records assigned to you

### Adding a New Repair Record

The process of adding a new repair record involves multiple steps, each managed by a different dialog:
- `NewRepairRecordD1`: Initiates the process and optionally starts an NFC scan.
- `NewRepairRecordD2`: Collects the raft number if manual option selected.
- `NewRepairRecordD3`: Collects the rental type if raftnumber not found in RaftMap.
- `NewRepairRecordD4`: Collects the repair notes.
- `NewRepairRecordConfirm`: Confirms the creation of the new repair record.

### Searching for Repair Records

- Users can search for specific repair records by raft number, NFC, or assigned values

### Viewing Repair Records

- The LazyColumn components display lists of repair records based on the selected view (History, In-Repair, Search, NFC, Assigned to you).

---

Also See:
- [ReportRecordView](https://lazy-day-tech.github.io/TapTrack-User-Reference/Dialogs/RepairRecordView)
- [NewRepairRecord](https://lazy-day-tech.github.io/TapTrack-User-Reference/Dialogs/NewRepairRecord)
- [NewRepairRecordConfirmation](https://lazy-day-tech.github.io/TapTrack-User-Reference/Dialogs/NewRepairRecordConfirm)


