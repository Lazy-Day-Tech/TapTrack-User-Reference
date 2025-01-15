# RepairMenu Documentation

## Overview

The `RepairMenu` is a Composable function in the `org.lazyday.ldclient.ui` package. It provides a user interface for managing repair records, including viewing, adding, and searching for repair records. The menu includes navigation options for different functionalities such as history, in-repair items, search, and NFC scanning.

## Components

### Navigation Rail

The navigation rail provides quick access to different sections of the repair menu:
- **Back**: Navigates back to the main mode selection page.
- **New Record**: Opens a dialog to add a new repair record.
- **Search**: Opens the search interface to find repair records by raft number.
- **NFC**: Initiates NFC scanning to find matching repair records.
- **In-Repair**: Displays a list of items currently in repair.
- **History**: Displays the repair history.

### Dialogs

The `RepairMenu` includes several dialogs for different steps in the repair record management process:
- **NewRepairRecordD1**: Initial step for adding a new repair record, with options for NFC scanning or manual entry.
- **NewRepairRecordD2**: Step for entering the raft number manually.
- **NewRepairRecordD3**: Step for entering the rental type.
- **NewRepairRecordD4**: Step for entering repair notes.
- **NewRepairRecordConfirm**: Final confirmation step for creating a new repair record.

### Dependencies
The RepairMenu relies on several dependencies:  
- androidx.compose.*: For Compose UI components.
- co.touchlab.kermit.Logger: For logging.
- kotlinx.coroutines.*: For coroutine support.
- kotlinx.datetime.*: For date and time handling.
- org.lazyday.ldclient.*: For project-specific components and API handlers.