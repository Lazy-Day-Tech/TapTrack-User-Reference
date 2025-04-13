# Getting Started with TapTrack

## Table of Contents
- [What is TapTrack](#what-is-taptrack)
- [Getting Access](#getting-access)
- [Downloading & Installing TapTrack](#downloading--installing-taptrack)
    - [Android](#android)
    - [iOS](#ios)
- [Using TapTrack](#using-taptrack)
    - [Check-In/Check-Out Module](#check-incheckout-module)
    - [Repair Module](#repair-module)
    - [Reporting Module](#reporting-module)
    - [Shuttle Management Module](#shuttle-management-module)
- [Customer Acknowledgement](#customer-acknowledgement)
- [Giving Feedback](#giving-feedback)
- [Additional Reading](#additional-reading)

## What is TapTrack?

TapTrack simplifies the management of raft bookings and inventory. It streamlines tasks like check-in/check-out, raft repairs, reporting, and shuttle management.  It's designed to improve efficiency and accuracy in day to day operations.

## Getting Access

To access TapTrack, you will need:

1. **Valid Google email address:** Used for authentication within the application.
2. **Apple associated email address (Optional):** Required if installing on a personal Apple device.  Provide this when requesting iOS beta access.

## Downloading & Installing TapTrack

Currently, due to complications with getting internal applications approved on the open app stores, the application is only available for download from a beta stream that may take additional steps to get access to.

### Android

*To Be Determined.* We are working on providing an Android download option and will update this section when available.

### iOS

The iOS installation process requires two steps: joining the Lazy Day Apple Organization and accepting a TestFlight invitation.

1. **Join the Lazy Day Apple Organization:**
    - An email invitation will be sent to your provided Apple ID email address.  Accept this invitation.
2. **Accept TapTrack Tester Invitation:**
    - After joining the organization, you'll receive a second invitation to join the TapTrack tester group via TestFlight. Accept this invitation.

**Installing via TestFlight:**

1. Install **[TestFlight](https://apps.apple.com/ca/app/testflight/id899247664)** from the App Store if you haven't already.  [TestFlight](https://testflight.apple.com/) is Apple’s official beta app management platform.
2. Open TestFlight and TapTrack should appear as an available application. If it doesn't, ensure you are signed in with the correct Apple ID.

## Authentication 
TapTrack currently relies on Google Authentication. This means that a valid google account is required to access the application. Before first time authentication, your associated email must first be added to the ACL list.  

## Using TapTrack 
TapTrack is composed of 4 main modules:
1. Check-In/Check-Out (a.k.a Base) module
2. Repair Module
3. Reporting Module
4. Shuttle Management Module

### Check-In/Check-Out Module

This module manages customer booking states.  Booking records include:

*   Name on file
*   Phone Number on file
*   Booking Status
*   Booking Date and Time
*   List of rentals associated with the booking
*   Waivers
*   Booking Notes
*   Start Time (actual check-in time)
*   End Time
*   Float Time (duration between check-in and check-out)
*   Flags
*   Check-In UUIDs (NFC tag IDs scanned during check-in)
*   Check-Out UUIDs (NFC tag IDs scanned during check-out)
*   List of Raft Numbers associated with the booking (resolved from Check-In UUIDs or Manual Input)

**Key Features:**

*   **NFC Scanning:** Automates booking lookup during check-out by scanning NFC tags attached to rafts.
*   **Manual Search:**  Search for bookings using Name, Phone Number, Booking Status, Date (Today, Yesterday), and Rental Type if NFC is unavailable. *Custom Date search is planned for a future release.*
*   **QR Lookup:** Scan FareHarbor QR codes during check-in to retrieve booking records.
*   **Manual Booking Update** A manual redundant method of checking rafts in/out using raft numbers

### Repair Module

This module manages raft inventory status and repair history.  Repair records are created for rafts needing service before returning to inventory, with a complete log maintained for each raft.

**Repair Record Details:**

*   Raft Type (e.g., "6 Person Raft")
*   Raft Number
*   Record Creation Date
*   Record Resolution Date
*   User who created the record
*   User who resolved the record
*   User assigned to the record
*   Repair Notes
*   Repair Status

**Modes:**

*   **Add Record:** Create a new repair record.
*   **Search:** Manually search for a raft's repair history by raft number.
*   **NFC:** Search for repair history using the raft’s NFC tag.
*   **In-Repair:** List of all currently active repair records.
*   **History:**  List of all repair records, sorted by date.
*   **Assigned:** List of repair records assigned to your account.

### Reporting Module

This module displays statistics for today's bookings.

**Pages:**

1.  **Status and Rental:**
    *   Counters of rafts by rental type and status.
    *   Total number of combined rentals booked for the current day.
    *   Total availability of each rental type (rafts - in repair).
    *   Total bookings in each state.
    *   Average float time (Today, Yesterday, Percentage Difference).
    *   Search/access booking records based on these filters.

2.  **Hourly Report:**
    *   Displays the number of each rental type scheduled for departure each hour.
    *   Search/access booking records based on these filters.

### Shuttle Management Module

This module quickly locates essential information for managing the shuttle.

**Pages:**

1.  **Scan:** Lookup records using FareHarbor QR codes.
2.  **Manual:** Search for bookings with active shuttle seats associated for the current day.
3.  **Shuttle Report:** Displays bookings with shuttle seats, showing:
    *   Last Name
    *   Number of Shuttle Seats Associated
    *   Number of Shuttle Seats Booked per Hour
    *   Name on file
    *   Booking time
    *   Number of shuttle seats associated with booking

## Customer Acknowledgement

If a booking includes a BowYak, customers must accept an agreement explaining potential water exposure before check-in.  Future development will include storm warnings within this feature.

## Giving Feedback

We value your feedback! Please share your ideas for improving TapTrack through the bug report/feedback form.

*   [Submit Bug Report or Feedback](https://forms.gle/1c7rD3p2KsoXTtsU7)
*   Email: [TBD]
*   Contact: [TBD]

## Additional Reading
Additional guides:
  - [Check-In/Check-Out Operations](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/CheckInCheckOut)
  - [Repair Management](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/RepairManagement)
  - [Shuttle Management](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/ShuttleManagement)
  - [Reporting](https://lazy-day-tech.github.io/TapTrack-User-Reference/Guides/Reporting)