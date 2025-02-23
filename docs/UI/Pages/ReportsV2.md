# ReportsV2

This is the new and improved varient of the reporting module. 

## Overview

The `ReportsV2` page provides comprehensive reports on today's rentals/Bookings. This screen categorizes rental items such as rafts, bowyaks, and tubes by their type and status—Checked-In, Not Checked-In, and Returned—providing users with detailed insights into current booking activities.

## Key Components

### Imports and Dependencies
- **Jetpack Compose**: Utilized for creating responsive user interface elements.
- **Koin for Dependency Injection**: Manages ViewModel instances efficiently within the app.
- **Logger (co.touchlab.kermit)**: Provides logging capabilities to monitor application behavior and facilitate debugging.
- **Time Libraries from `kotlinx.datetime`**: Facilitates handling of current system date-time operations.

### State Initialization
The function initializes several mutable states that represent different categories of rental items, such as 4-person rafts or solo yaks. Each category has further subdivisions based on the status of the item (Checked-In, Not Checked-In, Returned). These states are stored in lists of `Record` objects and dynamically updated based on fetched booking data.

### ViewModel Setup
The function employs a Koin context to handle dependency injection, initializing a `BookingViewModel`. This setup is crucial for managing data fetching, state updates, and user interactions effectively and efficiently. The view model allows the application to move between pages without requiring re-fetching of data. This is a critical component of the reporting module's base functionality. 

### Data Fetching and Filtering
Upon initialization or when no records are present, the function fetches booking data. It filters this data based on today's date, categorizing each record according to its type (raft size, yaks, tubes) and status. This ensures that users are presented with an up-to-date summary of current bookings, and prevents additional wasteful API calls significantly.

### User Interface
Using Jetpack Compose, `ReportsV2` constructs a user interface comprising:
- **Navigation**: A back button allows users to navigate away from the report screen.
- **Data Display**: The UI displays metrics using components like `BasicReportWidget`, `BigDateDisplay`, and `ValueChipRow`. These elements show today's date and provide quick access to detailed data on each category of rental items.

### Error Handling and Progress Indicators
The function includes a loading indicator that appears while booking data is being fetched. This provides visual feedback to users, indicating that the application is processing their request in real-time.

## Logging
Throughout its execution, `ReportsV2` employs logging extensively. It records key actions and data points, such as the number of rentals checked-in or returned for each category. These logs are helpful for monitoring app performance and troubleshooting issues.

## Navigation and Interaction
The UI is interactive; users can click on different chips to navigate to more detailed views based on selected categories. This feature enhances user engagement by providing deeper insights into specific rental data.

--- 
## Additional Notes  
- Filtering by `type` will show data based on the total number of rentals across all bookings, rather than on a per-booking basis. If a booking includes multiple types, it will be counted once for each relevant type rather than as a single entry for the entire booking.  
- The `Total` counters work differently, as they are based on bookings rather than rentals to avoid duplicate counts.
- The `TotalRentalsToday` widget at the top of the page, however will display the count of all rental items registered for the current date