# Getting Started with TapTrack

## What is TapTrack
TapTrack is a tool that aims to simplify the process of managing bookings and inventory management of rafts. 

1. CheckIn/CheckOut Module
    -  This module is responsible for managing the states of customer bookings
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
        12. CheckIn UUIDS
            - List of NFC UUIDs that have been scanned for the check in process
        13. CheckOut UUIDs
            - List of matching NFC UUIDs that have been scanned in the check out process
    1. NFC
        1. Automates the process of booking lookup in CheckOut mode
        2. User scans a tag attached to raft with device to access booking information
    2. Manual Search
        1. If there is a problem with NFC, you can search for bookings manually by a combination of:
            1. Name
            2. Phone Number
            3. Booking Status
            4. Date
                1. Today
                2. Yesterday
                3. ~~Custom Date~~ (Not yet supported)
                4. Rental Type
    3. QR Lookup
        1. Within CheckIn mode, there is an option for a QR scan
        1. This will initiate a QR scanner that can lookup booking records in our system if the customer provides a FareHarbor QR code
2. Repair Module
    - This module is reponsible of managing the status of raft inventory
    - Repair records can be created for rafts that require service before they can be returned to inventory
    - A history of these records get logged for each raft
    - Repair Records can consist of:
        1. Raft Type 
            - i.e "6 Person Raft"
        2. Raft Number
        3. Record Creation Date
        4. Record Resolution Date
        5. User that created the repair record
        6. User that resolved the repair record
        7. User that the record is assigned to
        8. Repair Notes
        9. Repair Status
    - Within the Repair Mode, There is several tabs:
        1. Add Record
            - Create a new repair record
        2. Search 
            - Manually search for a rafts repair history by raft number
        3. NFC
            - Search for a specific rafts repair history by scanning the rafts NFC tag
        4. In-Repair
            - A list of all repair records currently in repair
        5. History
            - A list of repair records of all states sorted by date
        6. Assigned
            - A list of repair records assigned to the users account
3. Reporting Module
    - This mode is repsonsible for displaying statistics of today's bookings
    - The reporting module consists of 2 pages:
        1. Status and Rental
            - Displays counters of rafts by rental type and status
            - Displays total number of combined rentals booked for current day
            - Displays total availability of each rental type (Total rafts minus rafts in repair)
            - Total bookings in each state
            - Average float time
                - Today's average float time
                - Yesterdays average float time
                - Difference in percentage
            - Search/access booking records based on these filters
        2. Hourly Report
            - Displays number of each type to be sent out each hour
            - Search/access booking records based on these filters
4. Shuttle Management Module
    - This mode is responsible for quickly locating and gathering only essential information needed to manage the shuttle 
    - This mode consists of 3 pages:
        1. Scan
            - This allows for the quick lookup of records using the FareHarbor QR code if the customer provides it
        2. Manual
            - Allows for search lookup of records with active shuttle seats associated with the booking for the current day
        3. Shuttle Report
            - Displays bookings with shuttle seats associated with the booking for the current date
            - Only the following record information is shown:
                1. Last name 
                2. Number of shuttle seats assosiated 
                3. Number of shuttle seats booked for each hour
            - The following inforation is shown for each record:
                1. Name on file
                2. Booking time
                3. Number of shuttle seats associated with booking


## Getting Access
When a user is given access to the application, they need to either give or be provided with the following:
1. **Valid Google email address**: In order to authenticate directly within the application.
2. **Apple associated email address (Optional)**: If user wants to install the app on their personal Apple device. 


## Downloading TapTrack
Currently due to complications with getting internal applications to be approved on the open app stores, the application is only available for download from a beta stream that may take additional steps to get access to. 

### Android
*To Be determined.*

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
    1. [Testflight](https://testflight.apple.com/) is the official method of accessing and managing beta applications on Apple Devices
    2. It is essentially the official app store of beta applications
2. TapTrack should automatically appear as an option for instillation 
    1. If you do not see this, ensure that you are signed in


## Giving Feedback