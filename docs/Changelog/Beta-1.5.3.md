# Beta-1.5.3
This release focuses on improvements to the Reporting Module, resolving numerous graphical bugs across the application, improving error handling and the overall health of the codebase.

## What's New
- Reporting Module
    - New `Report By Hour` page
        - View hourly reports of today's bookings by rental type
        - Integrated with the shared `ReportLookupPage`, allowing users to find more information about selected bookings and perform actions on them
        - Requires new permission `reports.hourly.view`
    - Fixed alignment issues on the base `ReportsV2` page
    - Modified the base `ReportsV2` page to fit most device sizes without needing vertical scrolling
    - Improved color support in `ReportLookupPage` to support the `ReportByHour` total filter
    - Realigned the top row of `ReportsV2` and added a button to access `ReportByHour`
- ModeSelectionPage
    - Fixed the old graphical issue causing logo overlapping with the segmented button on small devices
- ManualInput Page
    - Shortened naming conventions of rental items displayed in ManualInput booking details (e.g "6-person raft" will now display as "6p")
        - New function `shortenRentalItemNames`

## Other Improvements
- Significantly improved the overall health of the codebase
    - Removed multiple deprecated classes
    - Removed unused assets
    - Added documentation (within source code) for each function used 
    - Added additional exception/error handling
    - Removed old unnecessary logs
    - Deprecated `RepairModuleConfirmation` dialog to replace with `BasicDialog`
    - Deprecated `RecordNotFound` dialog and replaced with BasicDialog
    - Deprecated `ModifyRental` dialog
    - Deprecated `CheckInBookingNoteDialog`
    - Cleaned `AndroidManifest`
- Added a null message if the phone number is of invalid length or missing
- Ensured the user record is updated on login before navigation begins
