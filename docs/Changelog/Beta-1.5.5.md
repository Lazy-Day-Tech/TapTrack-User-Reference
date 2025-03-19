# Beta-1.5.5
This release focuses on the new feature set of manual individual raft check-in/check-out as an additional redundant option

## What's New:
- Added the ability to check rafts in/out using manual raft number input
    - Will resolve raft numbers to associated `NFC UUID`
    - Allows for bypass of raft resolution, allowing users to enter raft numbers if there is a problem with the `RaftMap` table
    - Automatically requests user verification for discrepancies with raft numbers
    - Accounts for unresolvable raft records in Check-In/Check-Out counters
    - Reworked counter logic in BookingRecordView to support both modes
    - Updated BookingRecordView UI
    