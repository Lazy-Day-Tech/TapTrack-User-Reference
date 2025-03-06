# ReportLookupPage

## Overview

The `ReportLookupPage` provides a view of booking records depending on which filters were selected from `ReportsV2`. This page is also connected to `BookingRecordView` with automated mode selection based on booking status, allowing you to check-in/out bookings or modify flags or booking notes as needed. This screen is part of the reporting feature that helps users navigate through filtered booking data.

## Key Components

### Imports and Dependencies
- **Jetpack Compose**: Utilized for creating a dynamic user interface.
- **NFC Manager**: Manages interactions with NFC tags, allowing for scanning and processing of data.
- **Koin for Dependency Injection**: Used to manage instances of `BookingViewModel`.
- **Logger (co.touchlab.kermit)**: Facilitates logging activities within the application.

### State Management
The function initializes several mutable states:
- `displayName`: Tracks the name of the filter currently being applied.
- `selectedBooking`: Holds the booking record that a user selects for detailed viewing.
- `showRecord`: Toggles visibility for displaying an individual booking's details.
- `nfcPayload`: Stores data received from NFC tag scans.

If "Total" filter is active, the names of organizers will display in varous colors to reflect the state of the booking:
- `Not Checked-In` -> `LDOrange`
- `Checked-In` -> `LDBlue`
- `Returned` -> `LDGreen`
- Otherwise if in other filter mode, `LDGray`

### ViewModel Setup
The function uses Koin to inject an instance of `BookingViewModel`, which provides access to booking records and facilitates data operations provided from the base ReportsV2 page

### Booking Data Handling
- **Data Collection**: The function collects booking records from the ViewModel, displaying them based on the specified filter.
- **Logging**: Logs initial bookings count and NFC payload data for monitoring and debugging purposes.

### User Interface
Using Jetpack Compose, `ReportLookupPage` constructs a user interface that includes:
- **Navigation**: A back button allows users to return to the previous report screen.
- **Display Name**: Shows the name of the current filter being applied.
- **Total Bookings Count**: Displays the total number of bookings for the selected category using a chip component.
- **Booking List**: Utilizes a `LazyColumn` to efficiently list booking records, allowing users to click on individual entries to view more details.

### NFC Integration
The function includes logic to handle NFC tag scans:
- **NFC Payload Handling**: Collects and processes data from scanned NFC tags, logging the payload for further actions.
- **Interaction with Booking Records**: Users can scan NFC tags associated with bookings to quickly modify booking details.

### Error Handling and User Feedback
- Displays a message when no bookings are found for the selected filter.
- Shows detailed views of individual bookings upon user interaction, including options to confirm or dismiss changes.

## Navigation and Interaction
The UI is interactive:
- Users can navigate back to the main report screen using the back button.
- Booking records are clickable, allowing users to view details or make modifications.
- NFC tags can be scanned to check bookings in/out.
