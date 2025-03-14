# Hourly Report

This page serves to display rental information based on the hour. A list of **today's** `BookingDateTime`'s are compiled and filtered from the `BookingViewModel` to display a list of rental items by the hour.

## Columns
The application will display times for 10 AM to 4PM on the hour

1. Hour
    - e.g. "10 AM"
2. Type
    - e.g. "4-person raft"
3. Count
    - e.g. "3"

## Total
Each hour has a summary of the collective number of rentals to be sent out for each hour

## Managing/Viewing records
Each row of data can be filtered to display the containing records within `ReportLookup`, including totals. This allows for the ability to manage customer booking information directly from the reporting module.

## Also See:
1. [ReportLookup](https://lazy-day-tech.github.io/TapTrackDocs/Pages/ReportLookup)
2. [ReportsV2](https://lazy-day-tech.github.io/TapTrackDocs/Pages/ReportsV2)