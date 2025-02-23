# Beta-1.4.0

## What's New:
- Customer Caution Acknowledgement
  - Require customer compliance in certain circumstances. 
  - Currently only supports BowYaks (Storm warning needs further planning for trigger/activation)
  - This is built to be highly scalable and additional warnings/cautions can easily be added in the future as needed
- Shuttle Seat Management
  - A new mode that allows for easy access to shuttle information 
- Remove Kayak's, BowYaks, Shuttle Seats from Check-In/Check-Out counters in `BookingRecordView`
  - Dont require NFC input for rental items that are not associated or scannable (still allows for checkin/checkout of bookings that do not have scannable/raft items associated to their booking)
- Add support for modifying booking notes after booking processing 
  - You can now modify booking notes for a booking that you have already checked-in or checked-out