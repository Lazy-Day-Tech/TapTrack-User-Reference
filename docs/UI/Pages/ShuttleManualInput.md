# Shuttle Manual Input

## Overview

The **Shuttle Manual Input** page is a feature that helps find shuttle bookings quickly and easily. You can search for specific bookings using the name of the booking organizer.

### Key Features

- **Search Functionality**: Easily look up shuttle records by typing keywords.
- **Filter Options**: Automatically filters today’s shuttle seats to show relevant options.
- **User-Friendly Interface**: Minimal information, only provides as much information as needed for the task.

## How It Works

### Getting Started

1. **Access Shuttle Search**: Navigate to the Shuttle Search Page from Shuttle Management page.
2. **Back Navigation**: Use the back button at the top if you need to return to the main shuttle management area.
3. **Refresh**: Update the list of bookings stored in the shared ViewModel

### Main Features

#### Search for Bookings

- **Search Bar**: Enter keywords related to the organizer name to find specific records.
  - The system filters results to show only today's relevant pre-float shuttle seats, helping you focus on current bookings.
  
#### View Booking Details

- Once you find a record that matches your search, click on it to view more details about the booking.

### Visual Elements

- **Search Bar**: Located at the top of the page for easy access. Type in your query and see results filtered in real-time.
- **List of Bookings**: Displays relevant shuttle bookings below the search bar, showing essential information like booking time and organizer name.

## Helpful Tips

- **Filtering**: The application only displays bookings for the current date that also contain at least 1 shuttle ticket in their list of rentals associated with a booking. If a record is not visable in manual input; it means that the booking is either not for todays date or the booking does not have any shuttle tickets. If you are unable to find a booking in the manual search, try scanning their QR code as the QR search will look through all bookings and disreguard the date for a matching booking 

## What You See

### Interface Details

- **Search Bar**: Where you type in your query. It updates as you type, showing results that match what you’ve entered.
- **List of Results**: Shows filtered shuttle records below the search bar. Each entry gives a quick overview of key booking details like the time and organizer's name.
  

## Other Links
- [ShuttleManagement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleManagement)
- [ShuttleRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/ShuttleRecordView)