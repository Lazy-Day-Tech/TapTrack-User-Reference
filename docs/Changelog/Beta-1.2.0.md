# Beta 1.2.0

## New Features:
- Float Time Implementation 
  - Set startDateTime and endDateTime on checkin/checkout using device currentDateTime and timezone
  - Display time since startDateTime in BookingRecordView
  - If marked as returned, compare against endDateTime rather than currentDateTime
  - get average of all returned booking floattimes of the day and display in Reports page (Early implementation)
- Replaced CheckOutSuccess dialog with BookingRecordView for uniformity
- Pass BookingNote instead of updating directly in ModifyBookingNotes (Airtable API Ratelimit Optimization)
- Fix "Booking Note modifications no longer refresh to BookingRecordView after update" graphical bug
- Reenabled phone number formatting in BookingRecordView
- Upgraded Gradle to version 8.8.0 for better performance
- Removed sample objects from source as they are no longer needed in backend implementations