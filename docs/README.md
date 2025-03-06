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
  - [User Permissions](https://lazy-day-tech.github.io/TapTrackDocs/API/Permissions)
- Handlers
  - [DateTimeHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/DateTimeHandlers)
  - [RaftMapHandlers](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/RaftMap)
  - [DataHandler](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Data)
  - [RentalResource](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/RentalResource)
  - [Users](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Users)
  - [Lookup](https://lazy-day-tech.github.io/TapTrackDocs/Handlers/Lookup)
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
    - [Acknowledgement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Components/Acknowledgement)
  - Dialogs
    - [BookingRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BookingRecordView)
    - [RepairRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/RepairRecordView)
    - [NewRepairRecord](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecord)
    - [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecordConfirm)
    - [BasicDialog](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BasicDialog)
    - [ShuttleRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/ShuttleRecordView)
    - [AckHandoverConfirmationDialog](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/AckHandoverConfirmationDialog)
  - Pages
    - [LoginPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/LoginPage)
    - [ReportPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportPage)
    - [CheckInPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckInPage)
    - [CheckOutPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckOutPage)
    - [RepairMenu](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/RepairMenu)
    - [ManualInput](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ManualInput)
    - [Navigation](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/Navigation)
    - [ShuttleManagement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleManagement)
    - [ShuttleManualInput](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleManualInput)
    - [ShuttleReports](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleReportPage)
    - [CustomerAcknowledgement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CustomerAcknowledgement)
    - [ReportsV2](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportsV2)
    - [ReportLookup](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportLookup)
  - Releases
    - [Beta-1.2.0](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.2.0)
    - [Beta-1.2.1](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.2.1)
    - [Beta-1.2.2](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.2.2)
    - [Beta-1.2.3](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.2.3)
    - [Beta-1.3.0](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.0)
    - [Beta-1.3.1](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.1)
    - [Beta-1.3.2](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.2)
    - [Beta-1.3.3](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.3)
    - [Beta-1.3.4](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.4)
    - [Beta-1.3.5](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.3.5)
    - [Beta-1.4.0](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.4.0)
    - [Beta-1.4.1](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.4.1)
    - [Beta-1.4.2](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.4.2)
    - [Beta-1.5.0](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.5.0)
    - [Beta-1.5.1](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.5.1)

---

![badge-android](http://img.shields.io/badge/platform-android-3DDC84.svg?style=flat)
![badge-ios](http://img.shields.io/badge/platform-ios-FF375F.svg?style=flat)

[![Kotlin](https://img.shields.io/badge/kotlin-v2.1.0-blue.svg?logo=kotlin)](http://kotlinlang.org)
[![Compose Multiplatform](https://img.shields.io/badge/Compose%20Multiplatform-v1.7.3-blue)](https://github.com/JetBrains/compose-multiplatform)

---

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
- **[Koin](https://github.com/InsertKoinIO/koin)** (Dependancy Injection)
- **[compose-table](https://github.com/windedge/compose-table)** (Shuttle Reports)

> For a full list of dependencies, refer to the commonMain `build.gradle.kts` file.


## Device Permissions
Requires internet access and a valid user record with permissions.

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