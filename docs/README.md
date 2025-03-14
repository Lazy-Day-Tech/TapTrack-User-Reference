## Table of Contents
- [Directory](#directory)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Device Permissions](#device-permissions)
  - [Android](#android)
  - [iOS](#ios)

## Directory:
Access other pages of documentation from here
- [Getting Starterd](https://lazy-day-tech.github.io/TapTrackDocs/GettingStarted)
- [Terms and Conditions](https://lazy-day-tech.github.io/TapTrackDocs/Legal/tos)
- [Privacy Policy](https://lazy-day-tech.github.io/TapTrackDocs/Legal/PrivacyPolicy)
- API 
  - [Data](https://lazy-day-tech.github.io/TapTrackDocs/API/Data)
  - [KeyStore](https://lazy-day-tech.github.io/TapTrackDocs/API/KeyStore)
  - [User Permissions](https://lazy-day-tech.github.io/TapTrackDocs/API/Permissions)
- Development (For development related docs)
  - [CI/CD Workflow](https://lazy-day-tech.github.io/TapTrackDocs/Development/CICD)
- UI
  - Dialogs
    - [BookingRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/BookingRecordView)
    - [RepairRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/RepairRecordView)
    - [NewRepairRecord](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecord)
    - [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/NewRepairRecordConfirm)
    - [ShuttleRecordView](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/ShuttleRecordView)
    - [AckHandoverConfirmationDialog](https://lazy-day-tech.github.io/TapTrackDocs/UI/Dialogs/AckHandoverConfirmationDialog)
  - Pages
    - [LoginPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/LoginPage)
    - ~~[ReportPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportPage)~~ (Deprecated)
    - [CheckInPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckInPage)
    - [CheckOutPage](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CheckOutPage)
    - [RepairMenu](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/RepairMenu)
    - [ManualInput](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ManualInput)
    - [ShuttleManagement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleManagement)
    - [ShuttleManualInput](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleManualInput)
    - [ShuttleReports](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ShuttleReportPage)
    - [CustomerAcknowledgement](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/CustomerAcknowledgement)
    - [ReportsV2](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportsV2)
    - [ReportLookup](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/ReportLookup)
    - [HourlyReport](https://lazy-day-tech.github.io/TapTrackDocs/UI/Pages/HourlyReport)
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
    - [Beta-1.5.2](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.5.2)
    - [Beta-1.5.3](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.5.3)
    - [Beta-1.5.4](https://lazy-day-tech.github.io/TapTrackDocs/Changelog/Beta-1.5.4)

---

![badge-android](http://img.shields.io/badge/platform-android-3DDC84.svg?style=flat)
![badge-ios](http://img.shields.io/badge/platform-ios-FF375F.svg?style=flat)

[![Kotlin](https://img.shields.io/badge/kotlin-v2.1.0-blue.svg?logo=kotlin)](http://kotlinlang.org)
[![Compose Multiplatform](https://img.shields.io/badge/Compose%20Multiplatform-v1.7.3-blue)](https://github.com/JetBrains/compose-multiplatform)

---

## Dependencies

The project uses several dependencies, including:

- **Multiplatform-Compose** (for UI)
- **Ktor** (for networking)
- **Kermit** (for logging)
- **Kotlinx Serialization** (for JSON parsing)
- **Kotlinx DateTime** (for Multiplatform DateTime support)
- **CoreNFC** (for iOS native NFC implementation)
- **android.nfc** (for Android native NFC implementation)
- **[QRKitComposeMultiplatform](https://github.com/Chaintech-Network/QRKitComposeMultiplatform)** (for multiplatform QR code support)
- **[KMPAuth](https://github.com/mirzemehdi/KMPAuth)** (For multiplatform authentication)
- **[GoogleSignIn-iOS](https://github.com/google/GoogleSignIn-iOS)** (GAuth support for iOS)
- **[Koin](https://github.com/InsertKoinIO/koin)** (Dependancy Injection)
- **[compose-table](https://github.com/windedge/compose-table)** (Shuttle Reports and Hourly Report UI)

> This is not a complete list of dependancies in use, only the main ones


## Device Permissions
Requires internet access and a valid user record with permissions/role.

### Android
1. NFC Reader
    1. `TAG_DISCOVERED`
2. Camera
    1. Autofocus
    2. Flashlight


### iOS
1. NFC Reader
2. Camera
