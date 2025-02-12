# RepairMenu Documentation

## Overview

The `RepairMenu` is a Composable function in the `org.lazyday.ldclient.ui` package. It provides a user interface for managing repair records, including viewing, adding, and searching for repair records. The menu includes navigation options for different functionalities such as history, in-repair items, search, and NFC scanning.

## Parameters
- `navController`: An optional NavController for navigating between screens within the app.
- `nfcManager`: An instance of NfcManager for handling NFC interactions.

## Components
### State Variables
- `scope`: A coroutine scope for launching coroutines.
- `isLoading`: A mutable state indicating whether data is loading.
- `isMakingChanges`: A mutable state indicating whether changes are being made.
- `nfcPayload`: A mutable state for storing NFC payload data.
- `selectedIndex`: A mutable state for tracking the selected index in the navigation rail.
- `repairItems`: A mutable state for storing a list of repair records.
- `isHistorySelected`, `isInRepairSelected`, `isSearchSelected`, `isNFCSelected`: Mutable states for tracking the selected navigation mode.
- `showRecordView`, `showAddRecordD1`, `showAddRecordD2`, `showAddRecordD3`, `showAddRecordD4`, `showNewRepairRecordConfirm`: Mutable states for managing the visibility of various dialogs.
- `matchingItems`: A mutable state for storing a list of matching repair records.
- `defaultStatus`: A string representing the default status of a new repair record.
- `newRaftNum`, repairNotes, rentalType, nfcValue: Mutable states for storing input values for new repair records.
- `safepadding`: A padding value calculated from safe drawing insets.
- `noRecordsFoundDialog`: A mutable state for managing the visibility of the "No Records Found" dialog.

## UI Components
- **MaterialTheme**: The theme for the UI components.
- **NavigationRail**: A vertical navigation rail for menu items.
- **LazyColumn**: A scrollable column for displaying lists of repair records.
- **FilterChip**: Chips for filtering search results.

## Dialogs
- `NewRepairRecordD1`, `NewRepairRecordD2`, `NewRepairRecordD3`, `NewRepairRecordD4`: Dialogs for adding a new repair record in multiple steps.
- `NewRepairRecordConfirm`: A dialog for confirming the creation of a new repair record.
- `RecordNotFound`: A dialog shown when no matching records are found.

## Functionality

### Fetching Repair Records

- Repair records are fetched and stored in the repairItems state when the RepairMenu composable is launched.
NFC Interaction

- The RepairMenu interacts with NFC tags using the nfcManager. When an NFC tag is detected, its payload is processed to find matching repair records.
Navigation

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

- Users can search for specific repair records by raft number or by NFC

### Viewing Repair Records

- The LazyColumn components display lists of repair records based on the selected view (History, In-Repair, Search, NFC).

---


