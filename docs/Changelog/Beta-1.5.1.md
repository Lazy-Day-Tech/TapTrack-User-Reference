# Beta-1.5.1
This release mainly focuses on significant logic enhancements/improvements as well as some bug fixes. Many minor graphical issues are known in this release and are intended to be focused in future releases. 

## What's New: 
- ModeSelectionPage will now wait until user permissions are fully synced before allowing the user to attempt to navigate to prevent confusion
- You can now search by phone number in ManualInput
- Shuttle Management
    - Shuttle management module now uses a common ViewModel, allowing for significant cost optimization and performance increases
    - New shuttle based report menu within the Shuttle Management module
    - New `shuttle.reports` permission
- Today's bookings can now be sent directly from Airtable, greatly increasing cost and performance optimization at scale
- New `Avalibility` counter in Reports by item type
- Added color coding to report bookings within `ReportLookup` if `Total` chip selected. Booking organizer names will display as different colors to reflect the following states:
    - `Not Checked-In` -> `LDOrange`
    - `Checked-In` -> `LDBlue`
    - `Returned` -> `LDGreen`
    - Otherwise if in other filter mode, `LDGray`
- Reports will no longer show any records with only shuttle seats registered to the booking
- Raft Availability in the Report page will store availablity in viewmodel (cost and performance optimization)
- Renamed columns in Reporting Module
    - `Total` -> `Booked`
    - `Not Checked-In` -> `Inflated`
    - `Checked-In` -> `Launched`
- Greatly improved QR scan result efficiency with backend
- Improve ManualInput to scale by receiving only records that it needs

## Bug Fixes:
- Fixed issue where permissions failed to finish initializing if already initialized in ModeSelectionPage
- Fixed shuttle seats from being displayed as rental items within BookingRecordView
- Added exception to handle missing phone numbers in `ReportLookup` page


## New Dependancies:
- **[compose-table](https://github.com/windedge/compose-table)**
    - Used to display shuttle report infromation using multiplatform material 3 style tables