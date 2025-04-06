# Beta-1.5.7

This release focuses on adding Android Support as well as the new Dynamic Shuttle Report, and some additional bug fixes and minor improvements.

## What's New

- **New**:
  - Google Play/Android support
        - Added google's signing licence to Google Cloud OAuth API so that authentication works on playstore signed builds
        - Removed feature requirements give additional device support as NFC is no longer a requirement to operate the applicaiton
        - Google play closed testing
  - Added Version Management to LoginPage and ModeSelectionPage to make it easier manage which version is installed
  - Icons in RepairMenu are now dynamically sized for better device support
  - Improved styling in ModeSelectionPage
  - Improved efficiency of filter logic across Shuttle Management Module and BookingRecordView
  - Added pagination support to `fetchUserRoles()` allowing over 100 roles to exist
  - Improved filtering logic in `ReportLookupPage` and `ManualInputV2`
  - Added "Unknown" rental when no registered rental items are known for rentals, but rentals are associated in `BookingRecordView` and `ManualInputV2`
- **Fixes**:
  - Fixed Shuttle Report datetime varying timezone support
    - New ShuttleReportV2
      - No longer uses static times and is now fully dynamic based on earliest and latest booking of each day
        - Only displays non-empty hours
    - Fixed a bug causing base Shuttle Management page button row to overlap with system bar
    - Fixed Icon-Label overlap in RepairMenu navigation bar on some devices
    - Improved sizing of waiver display text in BookingRecordView to be more consistent
    - Added padding to ManualInput to prevent overlap with system bar on Android devices
    - `RaftNumbersToRaftList` can now retuen a nullable list for not found raft numbers
    - Fixed warnings and removed temporary suppresions
    - Fixed some grammar of function/variables
- Determined minimum Android device requirements
  - SDK 28 (Android 9.0)
- Upgraded Several Dependancies
- Improved source documention
- Additional Unit Tests
