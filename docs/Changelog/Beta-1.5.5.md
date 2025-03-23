# Beta-1.5.5
This release introduces a new feature for manual individual raft check-in/check-out as an additional redundancy option.

## What's New:
- Added manual raft number input for check-in/check-out
    - Resolves raft numbers to their associated `NFC UUID`
    - Allows users to bypass raft resolution by entering raft numbers directly if issues occur with the `RaftMap` table
    - Prompts user verification for raft number discrepancies
    - Handles unresolvable raft records in Check-In/Check-Out counters
    - Updated counter logic in BookingRecordView to support both manual and automatic modes
    - Enhanced BookingRecordView UI
- Fixed a bug preventing step back functionality in new repair record creation
- Greatly improved BookingRecordView support for small screen sizes
- Fixed overlapping flag-button row for large bookings
- Improved username fetching with backend data security
- Greatly improved Repair Module performance
    - Integrated with view model
- Major codebase cleanup
- Improved logging
- Improved source documentation 
