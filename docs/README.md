## Table of Contents
- [Directory](#directory)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Device Permissions](#device-permissions)
  - [Android](#android)
  - [iOS](#ios)

## Directory:
Access other pages of documentation from here
- API 
  - [Airtable](https://lazy-day-tech.github.io/TapTrackDocs/API/Airtable)
  - [Data](https://lazy-day-tech.github.io/TapTrackDocs/API/Data)
  - [OpenCalgary](https://lazy-day-tech.github.io/TapTrackDocs/API/OpenCalgary)
- Handlers
  - [DateTimeHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/DateTimeHandlers)
  - [RaftMapHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/RaftMap)
  - [DataHandler](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Data)
- Development (For dev docs)
  - [Logging](https://lazy-day-tech.github.io/TapTrackDocs/Development/Logging)
  - [CI/CD Workflow](https://lazy-day-tech.github.io/TapTrackDocs/Development/CICD)
- iOS (For iOS native implementations)
  - [NFC](https://lazy-day-tech.github.io/TapTrackDocs/iOS/NFC)
- Android (For Android Native implementations)
  - [NFC](https://lazy-day-tech.github.io/TapTrackDocs/Android/NFC)
- UI
  - Components
    - [ProgressIndicators](https://lazy-day-tech.github.io/TapTrackDocs/UI/Components/ProgressIndicators)
    - [ReportWidgets](https://lazy-day-tech.github.io/TapTrackDocs/UI/Components/ReportWidgets)
    - [DropdownTextField](https://lazy-day-tech.github.io/TapTrackDocs/UI/Components/DropdownTextField)
  - Dialogs
    - [BookingRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BookingRecordView)
    - [RepairRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/RepairRecordView)
    - [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecordConfirm)
    - [BasicDialog](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BasicDialog)
  - Pages
    - [ReportPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportPage)
    - [CheckInPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckInPage)
    - [CheckOutPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckOutPage)
    - [RepairMenu](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/RepairMenu)
    - [Navigation](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/Navigation)

## Roadmap
Keep up to date with the project [here](https://github.com/orgs/Lazy-Day-Tech/projects/2)

## Getting Started

To get started with TapTrack Development, follow these steps:

1. Clone the repository (private repo):
    ```sh
    git clone https://github.com/Lazy-Day-Tech/LDClient.git
    cd LDClient
    ```

2. Open the project in Android Studio:
    - Open Android Studio.
    - Select "Open an existing project".
    - Navigate to the `LDClient` directory and open it.

3. Sync the project with Gradle files.

## Dependencies

The project uses several dependencies, including:

- **Multiplatform-Compose** (for UI)
- **Ktor** (for networking)
- **Kermit** (for logging)
- **Kotlinx Serialization** (for JSON parsing)
- **Kotlinx DateTime** (for Multiplatform DateTime support)
- **CoreNFC** (for iOS native NFC implementation)
- **android.nfc** (for Android native NFC implementation)
- **[AAY-chart](https://github.com/TheChance101/AAY-chart)** (for reports visualization)
- **[QRKitComposeMultiplatform](https://github.com/Chaintech-Network/QRKitComposeMultiplatform)** (for multiplatform QR code support)

> For a full list of dependencies, refer to the commonMain `build.gradle.kts` file.


## Device Permissions
Requires internet access

### Android
```xml
    Used for NFC Check-In/Check-Out/Repair Management
    <uses-feature android:name="android.hardware.nfc" android:required="true" />
    <uses-permission android:name="android.permission.NFC" />
    <action android:name="android.nfc.action.TAG_DISCOVERED"/>

    Used for QR code Check-In process
    <uses-feature android:name="android.hardware.camera"/>
    <uses-feature android:name="android.hardware.camera.autofocus"/>
    <uses-permission android:name="android.permission.CAMERA"/>
    <uses-permission android:name="android.permission.FLASHLIGHT"/>
```
### iOS
```plist
  Used for NFC Check-In/Check-Out/Repair Management
  <key>NFCReaderUsageDescription</key>
	<string>Needed for raft interaction</string>
  
  Used for QR code Check-In process
	<key>NSCameraUsageDescription</key>
	<string>Used for QR Code Check-In process</string>
	<key>NSPhotoLibraryUsageDescription</key>
	<string>Used for QR code check in</string>
```