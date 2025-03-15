# Beta-1.5.4

## What's New:
- Added Average Float Time information to the *Reporting Module*
    - New `reports.floattie.view` permission to access advanced floattime report
        - This permission is only needed to view yesterday's float time and the difference between. Today's float time is included within the base `reports.view` permission
    - View today's current average float time, yesterday's average float time, and the percentage of difference between the two. 
- Raft numbers of rafts checked in is now automated based on NFC UUID values and stored in booking data
    - Will also display values in BookingRecordView
- Improved small screen support for BookingRecordView
- Fixed support for "Tomorrow" filter chip in ManualInput 