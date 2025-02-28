# DateTimeHandlers

The DateTimeHandlers module provides a set of utility functions to handle and manipulate date and time in a user-friendly way. It includes functions to get the current date and time, convert time to a 12-hour format, and format a date-time string into a human-readable format.

## Functions

### getCurrentDateTime

```kotlin
fun getCurrentDateTime(): LocalDateTime
```

#### Description:
This function returns the current date and time in the local timezone, formatted as a LocalDateTime object.

#### Returns:
- A LocalDateTime object representing the current date and time in the system's default timezone.

#### Example Usage:

```kotlin
val currentDateTime = getCurrentDateTime()
```

### convertTo12Hour

```kotlin
fun convertTo12Hour(localDateTime: LocalDateTime): String
```

#### Description:
This function converts a given LocalDateTime object to a 12-hour format string with an AM/PM period. It displays the time as hh:mm AM/PM.

#### Parameters:
- `localDateTime`: A LocalDateTime object to be converted into a 12-hour format.

#### Returns:
- A String representing the time in the 12-hour format (e.g., "02:05 PM").

#### Example Usage:

```kotlin
val time12Hour = convertTo12Hour(localDateTime)
```

##### Example Output:
- `02:05 PM`

---

### formatDateTime

```kotlin
fun formatDateTime(datetimeString: String): String
```

#### Description:
This function converts an ISO 8601 formatted String representing a datetime (e.g., "2023-10-15T14:30:00Z") into a more user-friendly format. It outputs the date and time in the format hh:mm AM/PM Month Day, Year (e.g., "02:05 PM October 15, 2023").

#### Parameters:
- `datetimeString`: A string representing a datetime in ISO 8601 format.

#### Returns:
- A String representing the formatted date and time (e.g., "02:05 PM October 15, 2023").

#### Example Usage:

```kotlin
val formattedDateTime = formatDateTime("2023-10-15T14:30:00Z")
```

#### Example Output:
`"02:05 PM October 15, 2023"`

### getAverageFloatTime

```kotlin
fun getAverageFloatTime(bookings: List<Record>): String
```

#### Description:
This function calculates the average float time from a list of booking records. Float time is the time between the start and end of a booking. The function sums the duration of all valid bookings and calculates the average.

#### Parameters:
- `bookings`: A list of Record objects, each representing a booking with a start and end date-time.

#### Returns:
- A String representing the average float time in hours and minutes (e.g., "2 hours 30 minutes").
- If no valid float times are found, it returns "No valid float times found".

#### Logic:
1. The function maps over the provided list of bookings and extracts the startDateTime and endDateTime for each booking.
2. It calculates the duration (float time) between the start and end time for each valid booking.
3. It sums the durations of all valid float times.
4. It calculates the average duration and returns it in a readable format ("X hours Y minutes").

#### Throws:
- If the startDateTime or endDateTime of a booking is missing or invalid, that booking is ignored in the calculation.

#### Example Usage:

```kotlin
val averageFloatTime = getAverageFloatTime(bookings)
```

##### Example Output:

- `"2 hours 30 minutes"`

If no valid float times exist in the provided bookings:

- `"No valid float times found"`

### formatTime
```kotlin
fun formatTime(dateTimeString: String): String
```
#### Description:
- This function converts an ISO 8601 formatted String representing a datetime into a more user-friendly format. It outputs the date and time in the format hh:mm AM/PM Month Day, Year.

#### Parameters:
- `dateTimeString`: A string representing a datetime in ISO 8601 format.
#### Returns:
- A String representing the formatted date and time (e.g., "02:05 PM October 15, 2023").

### formatDateTimeShort
```kotlin
fun formatDateTimeShort(dateTimeString: String): String
```
#### Description:
- This function converts a given datetime string into a more user-friendly format. It outputs the date and time in the format hh:mm AM/PM Day Month, Year.

#### Parameters:
- `dateTimeString`: A string representing a datetime in ISO 8601 format.
#### Returns:
- A String representing the formatted date and time (e.g., "12:00 PM Fri Feb 28").

## Dependencies
- kotlinx.datetime: Provides APIs to handle and manipulate dates and times, particularly for working with Instant, LocalDateTime, and TimeZone objects.
- Record: Represents a booking record, containing startDateTime and endDateTime fields (of type String).
- Instant: Used to parse and handle date and time in UTC.
- TimeZone and toLocalDateTime: Used to convert the Instant to a local LocalDateTime for duration calculations.
- Duration: Used to handle and perform arithmetic on time durations.

