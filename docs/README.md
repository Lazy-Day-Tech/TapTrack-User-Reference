## Table of Contents
- [Directory](#directory)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Device Permissions](#device-permissions)
  - [Android](#android)
  - [iOS](#ios)

## Directory:
Access other pages of documentation from here
- [Terms and Conditions](https://lazy-day-tech.github.io/TapTrackDocs/Legal/tos)
- [Privacy Policy](https://lazy-day-tech.github.io/TapTrackDocs/Legal/PrivacyPolicy)
- API 
  - [Airtable](https://lazy-day-tech.github.io/TapTrackDocs/API/Airtable)
  - [Data](https://lazy-day-tech.github.io/TapTrackDocs/API/Data)
  - [KeyStore](https://lazy-day-tech.github.io/TapTrackDocs/API/KeyStore)
  - [OpenCalgary](https://lazy-day-tech.github.io/TapTrackDocs/API/OpenCalgary)
- Handlers
  - [DateTimeHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/DateTimeHandlers)
  - [RaftMapHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/RaftMap)
  - [DataHandler](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Data)
  - [RentalResource](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/RentalResource)
  - [Users](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Users)
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
    - [NewRepairRecord](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecord)
    - [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecordConfirm)
    - [BasicDialog](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BasicDialog)
  - Pages
    - [LoginPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/LoginPage)
    - [ReportPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportPage)
    - [CheckInPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckInPage)
    - [CheckOutPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckOutPage)
    - [RepairMenu](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/RepairMenu)
    - [ManualInput](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ManualInput)
    - [Navigation](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/Navigation)


## Getting Started

To get started with TapTrack Development, follow these steps:

1. Clone the repository (private repo):
    ```sh
    git clone https://github.com/Lazy-Day-Tech/LDClient.git
    cd LDClient
    ```

2. iOS/MacOS setup
    - Install [Cocoapods](https://cocoapods.org/)
      - Install dependancies and open workspace:
      - `cd /LDClient/iosApp`
      - `pod install`
      - `open iosApp.xcworkspace`

3. Open the project in Android Studio:
    - Open Android Studio.
    - Select "Open an existing project".
    - Navigate to the `LDClient` directory and open it.

4. Sync the project with Gradle files.

## Dependencies

The project uses several dependencies, including:

- **Multiplatform-Compose** (for UI)
- **Ktor** (for networking)
- **Kermit** (for logging)
- **Kotlinx Serialization** (for JSON parsing)
- **Kotlinx DateTime** (for Multiplatform DateTime support)
- **CoreNFC** (for iOS native NFC implementation)
- **android.nfc** (for Android native NFC implementation)
- **[AAY-chart](https://github.com/TheChance101/AAY-chart)** (for data visualization)
- **[QRKitComposeMultiplatform](https://github.com/Chaintech-Network/QRKitComposeMultiplatform)** (for multiplatform QR code support)
- **[KMPAuth](https://github.com/mirzemehdi/KMPAuth)** (For multiplatform authentication)
- **[GoogleSignIn-iOS](https://github.com/google/GoogleSignIn-iOS)** (GAuth support for iOS)

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