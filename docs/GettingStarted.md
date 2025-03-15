# Getting Started with TapTrack

## Table of Contents
- [What is TapTrack](#what-is-taptrack)
- [Getting Access](#getting-access)
- [Downloading TapTrack](#downloading-taptrack)
    - [Android](#android)
    - [iOS](#ios)
        - [Joining the Beta](#joining-the-beta)
        - [Installing TapTrack](#installing-taptrack)
- [Giving Feedback](#giving-feedback)

## What is TapTrack
TapTrack is a tool that aims to simplify the process of managing bookings and inventory management of rafts. It helps simplify tasks such as booking check-ins/outs, raft repairs, reporting, and shuttle management.

1. CheckIn/CheckOut Module
    - This module is responsible for managing the states of customer bookings.
    - Booking Records consist of:
        1. Name on file
        2. Phone Number on file
        3. Booking Status
        4. Booking Date and Time
        5. List of rentals associated with the booking
        6. Waivers
        7. Booking Notes
        8. Start Time
            - The time the booking was actually checked-in
        9. End Time
        10. Float Time
            - The duration of the booking between check-in and check-out
        11. Flags
        12. CheckIn UUIDs
            - List of NFC UUIDs that have been scanned for the check-in process
        13. CheckOut UUIDs
            - List of matching NFC UUIDs that have been scanned in the check-out process
        14. List of Raft Numbers associated with booking
            - Resolved from the list of CheckIn UUIDs
    - NFC
        1. Automates the process of booking lookup in CheckOut mode
        2. User scans a tag attached to the raft with a device to access booking information
    - Manual Search
        1. If there is a problem with NFC, you can search for bookings manually by a combination of:
            1. Name
            2. Phone Number
            3. Booking Status
            4. Date
                1. Today
                2. Yesterday
                3. ~~Custom Date~~ (Not yet supported)
            5. Rental Type
    - QR Lookup
        1. Within CheckIn mode, there is an option for a QR scan
        2. This will initiate a QR scanner that can look up booking records in our system if the customer provides a FareHarbor QR code
2. Repair Module
    - This module is responsible for managing the status of raft inventory.
    - Repair records can be created for rafts that require service before they can be returned to inventory.
    - A history of these records gets logged for each raft.
    - Repair Records can consist of:
        1. Raft Type 
            - i.e., "6 Person Raft"
        2. Raft Number
        3. Record Creation Date
        4. Record Resolution Date
        5. User that created the repair record
        6. User that resolved the repair record
        7. User that the record is assigned to
        8. Repair Notes
        9. Repair Status
    - Within the Repair Mode, there are several tabs:
        1. Add Record
            - Create a new repair record
        2. Search 
            - Manually search for a raft's repair history by raft number
        3. NFC
            - Search for a specific raft's repair history by scanning the raft's NFC tag
        4. In-Repair
            - A list of all repair records currently in repair
        5. History
            - A list of repair records of all states sorted by date
        6. Assigned
            - A list of repair records assigned to the user's account
3. Reporting Module
    - This mode is responsible for displaying statistics of today's bookings.
    - The reporting module consists of 2 pages:
        1. Status and Rental
            - Displays counters of rafts by rental type and status
            - Displays the total number of combined rentals booked for the current day
            - Displays total availability of each rental type (Total rafts minus rafts in repair)
            - Total bookings in each state
            - Average float time
                - Today's average float time
                - Yesterday's average float time
                - Difference in percentage
            - Search/access booking records based on these filters
        2. Hourly Report
            - Displays the number of each type to be sent out each hour
            - Search/access booking records based on these filters
4. Shuttle Management Module
    - This mode is responsible for quickly locating and gathering only essential information needed to manage the shuttle.
    - This mode consists of 3 pages:
        1. Scan
            - This allows for the quick lookup of records using the FareHarbor QR code if the customer provides it
        2. Manual
            - Allows for search lookup of records with active shuttle seats associated with the booking for the current day
        3. Shuttle Report
            - Displays bookings with shuttle seats associated with the booking for the current date
            - Only the following record information is shown:
                1. Last name 
                2. Number of shuttle seats associated 
                3. Number of shuttle seats booked for each hour
            - The following information is shown for each record:
                1. Name on file
                2. Booking time
                3. Number of shuttle seats associated with booking
5. Customer Acknowledgement 
    - If a booking has a BowYak associated with their booking, the customer will need to complete an additional step before they can be checked in. The user will need to accept an agreement on the device explaining how they are likely to get wet.
    - This feature also has planned warnings for storms, however, this is not yet implemented.

## Getting Access
When a user is given access to the application, they need to either give or be provided with the following:
1. **Valid Google email address**: In order to authenticate directly within the application.
2. **Apple associated email address (Optional)**: If the user wants to install the app on their personal Apple device.

## Downloading TapTrack
Currently, due to complications with getting internal applications approved on the open app stores, the application is only available for download from a beta stream that may take additional steps to get access to.

### Android
*To Be Determined.*

#### ~~Joining the beta~~

#### ~~Installing TapTrack~~

### iOS
This is the more complicated platform to get access to. Setup for this platform includes 2 steps to gain access to the application as well as one additional piece of user information.

#### Joining the beta
1. User must join the Apple Organization for Lazy Day
    1. This requires the email associated with a valid Apple account
    2. To do this, an email invitation will be sent to the provided email
2. User must then accept a second invitation to join the tester group for TapTrack

#### Installing TapTrack
1. Install **[TestFlight](https://apps.apple.com/ca/app/testflight/id899247664)** from the App Store
    1. [TestFlight](https://testflight.apple.com/) is the official method of accessing and managing beta applications on Apple Devices
    2. It is essentially the official app store of beta applications
2. TapTrack should automatically appear as an option for installation 
    1. If you do not see this, ensure that you are signed in

## Giving Feedback
We are open to feedback. Have an idea of a way we can improve the application? Here are some ways to get this information to us:
- Email: TBD
- Talk to: TBD
- Submit feedback in TestFlight