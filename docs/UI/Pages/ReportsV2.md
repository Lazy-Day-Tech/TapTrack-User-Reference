# ReportsV2

This is the new and improved varient of the reporting module. 

## Overview

The `ReportsV2` page provides comprehensive reports on today's rentals/Bookings. This screen categorizes rental items such as rafts, bowyaks, and tubes by their type and status—Checked-In, Not Checked-In, and Returned—providing users with detailed insights into current booking activities.

## Key Components

### ViewModel Setup
The function employs a Koin context to handle dependency injection, initializing a `BookingViewModel`. This setup is crucial for managing data fetching, state updates, and user interactions effectively and efficiently. The view model allows the application to move between pages without requiring re-fetching of data. This is a critical component of the reporting module's base functionality. 

### Data Fetching and Filtering
Upon initialization or when no records are present, the function fetches booking data. Only fetches a list of **Today's** bookings, categorizing each record according to its type (raft size, yaks, tubes) and status. This ensures that users are presented with an up-to-date summary of current bookings, and prevents additional wasteful API calls significantly.

--- 
## Additional Notes  
- Filtering by `type` will show data based on the total number of rentals across all bookings, rather than on a per-booking basis. If a booking includes multiple types, it will be counted once for each relevant type rather than as a single entry for the entire booking.  
- The `Total` counters work differently, as they are based on bookings rather than rentals to avoid duplicate counts.
- The `TotalRentalsToday` widget at the top of the page, however will display the count of all rental items registered for the current date
- Bookings with only shuttle seats assigned to their booking will not be displayed

## Also See:
1. [ReportLookup](https://lazy-day-tech.github.io/TapTrackDocs/Pages/ReportLookup)
2. [HourlyReport](https://lazy-day-tech.github.io/TapTrackDocs/Pages/HourlyReport)