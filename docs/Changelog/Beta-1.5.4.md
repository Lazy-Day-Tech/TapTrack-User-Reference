# Beta-1.5.4

## What's New:
- Added Average Float Time information to the *Reporting Module*
    - New `reports.floattie.view` permission to access advanced floattime report
        - This permission is only needed to view yesterday's float time and the difference between. Today's float time is included within the base `reports.view` permission
    - View todays current average float time, yesterdays average float time, and the percentage of difference between the two. 