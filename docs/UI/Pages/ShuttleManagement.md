# Shuttle Management

## What It Does

The **Shuttle Management** feature lets you manage shuttle bookings easily through your app. You can scan a QR code to quickly find booking details or enter information manually if needed.

### Features

- **QR Code Scanning**: Quickly scan a shuttle's QR code to view its booking details.
- **Manual Entry**: If scanning isn't possible, use the manual input option to enter shuttle information.
- **Easy Navigation**: Move between different sections of your app with simple navigation buttons.
- **Common ViewModel**: All pages within the Shuttle Management module share the same ViewModel, allowing for the application to function with minimal API requests while incresing performance

## How It Works

### Getting Started

1. **Open Shuttle Management**: Start by opening this feature in your app.
2. **Navigation Bar**: You'll see a back button at the top, allowing you to return to the main menu if needed.

### What Can You Do?

#### Scan QR Code

- **Scan Button**: Click this to start scanning a shuttle's QR code.
  - Follow the on-screen instructions to align your QR code within the frame for successful scanning.
  - The app will show details of the booking associated with that QR code once scanned successfully.

#### Enter Information Manually

- **Manual Input Button**: If you don't have a QR code handy, click this button to manually enter shuttle information.

### Helpful Tips

- **Loading Indicator**: When the app is processing your scan or input, a spinning circle will show up. This means it's working on getting your information.
  
- **Error Handling**: If something goes wrong during scanning (like an unclear QR code), you'll see a message alerting you to try again.

## What You See

### User Interface Elements

- **Scan and Manual Buttons**: These are at the bottom of the screen for quick access to either function.
- **Instructions**: When scanning, instructions will appear on how to align your QR code.
- **Dialogs for Booking Details**: After a successful scan or manual entry, you'll see detailed information about the shuttle booking.

## Important Notes

- Ensure your device's camera is working properly when using the scan feature.
- Make sure there’s good lighting if scanning a QR code to ensure it reads correctly.


## Other Links
- [ShuttleManualInput](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ShuttleManualInput)
- [ShuttleRecordView](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/ShuttleRecordView)