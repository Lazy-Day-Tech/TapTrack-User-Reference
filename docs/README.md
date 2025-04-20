## Table of Contents
- [Directory](#directory)
- [Getting Started](#getting-started)
- [Dependencies](#dependencies)
- [Device Permissions](#device-permissions)
  - [Android](#android)
  - [iOS](#ios)

## Directory:
Access other pages of documentation from here
- Guides
  - [Getting Started](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/GettingStarted)
  - [Check-In/Check-Out Operations](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/CheckInCheckOut)
  - [Repair Management](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/RepairManagement)
  - [Shuttle Management](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/ShuttleManagement)
  - [Reporting](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/Reporting)
- [Terms and Conditions](https://lazy-day-tech.github.io/TapTrack-User-Reference/Legal/tos)
- [Privacy Policy](https://lazy-day-tech.github.io/TapTrack-User-Reference/Legal/PrivacyPolicy)
- API 
  - [Data](https://lazy-day-tech.github.io/TapTrack-User-Reference/API/Data)
  - [KeyStore](https://lazy-day-tech.github.io/TapTrack-User-Reference/API/KeyStore)
  - [User Permissions](https://lazy-day-tech.github.io/TapTrack-User-Reference/API/Permissions)
- Development (For development related docs)
  - [CI/CD Workflow](https://lazy-day-tech.github.io/TapTrack-User-Reference/Development/CICD)
- UI
  - Dialogs
    - [BookingRecordView](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/BookingRecordView)
    - [RepairRecordView](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/RepairRecordView)
    - [NewRepairRecord](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/NewRepairRecord)
    - [NewRepairRecordConfirm](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/NewRepairRecordConfirm)
    - [ShuttleRecordView](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/ShuttleRecordView)
    - [AckHandoverConfirmationDialog](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Dialogs/AckHandoverConfirmationDialog)
  - Pages
    - [LoginPage](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/LoginPage)
    - ~~[ReportPage](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ReportPage)~~ (Deprecated)
    - [CheckInPage](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/CheckInPage)
    - [CheckOutPage](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/CheckOutPage)
    - [RepairMenu](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/RepairMenu)
    - [ManualInput](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ManualInput)
    - [ShuttleManagement](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ShuttleManagement)
    - [ShuttleManualInput](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ShuttleManualInput)
    - [ShuttleReports](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ShuttleReportPage)
    - [CustomerAcknowledgement](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/CustomerAcknowledgement)
    - [ReportsV2](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ReportsV2)
    - [ReportLookup](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/ReportLookup)
    - [HourlyReport](https://lazy-day-tech.github.io/TapTrack-User-Reference/UI/Pages/HourlyReport)
  - Releases
    - [Beta-1.2.0](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.2.0)
    - [Beta-1.2.1](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.2.1)
    - [Beta-1.2.2](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.2.2)
    - [Beta-1.2.3](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.2.3)
    - [Beta-1.3.0](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.0)
    - [Beta-1.3.1](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.1)
    - [Beta-1.3.2](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.2)
    - [Beta-1.3.3](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.3)
    - [Beta-1.3.4](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.4)
    - [Beta-1.3.5](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.3.5)
    - [Beta-1.4.0](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.4.0)
    - [Beta-1.4.1](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.4.1)
    - [Beta-1.4.2](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.4.2)
    - [Beta-1.5.0](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.0)
    - [Beta-1.5.1](hhttps://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.1)
    - [Beta-1.5.2](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.2)
    - [Beta-1.5.3](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.3)
    - [Beta-1.5.4](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.4)
    - [Beta-1.5.5](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.5)
    - [Beta-1.5.6](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/Beta-1.5.6)
    - [1.5.7](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/1.5.7)
    - [1.5.8](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/1.5.8)
    - [1.5.9](https://lazy-day-tech.github.io/TapTrack-User-Reference/Changelog/1.5.9)

---

![badge-android](http://img.shields.io/badge/platform-android-3DDC84.svg?style=flat)
![badge-ios](http://img.shields.io/badge/platform-ios-FF375F.svg?style=flat)

[![Kotlin](https://img.shields.io/badge/kotlin-v2.1.20-blue.svg?logo=kotlin)](http://kotlinlang.org)
[![Compose Multiplatform](https://img.shields.io/badge/Compose%20Multiplatform-v1.7.3-blue)](https://github.com/JetBrains/compose-multiplatform)

---

## Device Support & Permissions
Requires internet access and a valid user record with permissions/role.

### Android
#### Compatability
Requires:
- Minimum SDK: `28` (`Android 9.0`)
- Features: `NFC Reader`

#### Permissions
1. NFC Reader
    - For Booking/Repair Lookup and Management
    1. `TAG_DISCOVERED`
2. Camera
    - For QR Code scanning
    1. Autofocus
    2. Flashlight


### iOS
#### Compatability
Requires iOS version **15.5** or later
#### Permissions
1. NFC Reader
    - For Booking/Repair Lookup and Management
2. Camera
    - For QR Code scanning
