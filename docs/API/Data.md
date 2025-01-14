# TapTrack API Data Serialization

This document provides an overview and usage instructions for the Kotlin data classes used in various API responses, including Booking, Repair, and RaftMap tables.

## Overview

The data classes in this project are annotated with `@Serializable` to enable seamless JSON serialization and deserialization using Kotlin Serialization. These classes represent structured data returned by APIs for booking management, repair records, and raft mapping.

---

## Booking Table

### Classes

#### `BookingResponse`

- Represents the response from the booking API.
- **Properties:**
  - `records`: List of `Record` objects.
  - `offset`: Pagination offset (optional).

#### `Record`

- Represents an individual booking record.
- **Properties:**
  - `id`: Unique identifier of the record.
  - `createdTime`: Creation time of the record.
  - `fields`: Associated booking fields as `Fields`.

#### `Fields`

- Represents the fields of a booking record.
- **Properties:**
  - `Rentals`: List of rentals (optional).
  - `Due_Balance`: Due balance for the booking (optional).
  - `Status`: Booking status (optional).
  - `Waivers`: List of waivers (optional).
  - `NFC_UUID`: NFC UUID associated with the booking (optional).
  - `Phone_Number`: Associated phone number (optional).
  - `BookingDateTime`: Date and time of the booking (optional).
  - `Organizer`: Booking organizer (optional).
  - `Booking_Notes`: Notes about the booking (optional).
  - `FHID`: FareHarbour Booking UUID (optional).
  - `startDateTime`: Start date and time (optional).
  - `endDateTime`: End date and time (optional).

---

## Repairs Table

### Classes

#### `RepairResponse`

- Represents the response from the repair API.
- **Properties:**
  - `records`: List of `RepairRecord` objects.
  - `offset`: Pagination offset (optional).

#### `RepairRecord`

- Represents an individual repair record.
- **Properties:**
  - `id`: Unique identifier of the record.
  - `createdTime`: Creation time of the record.
  - `fields`: Associated repair fields as `RepairFields`.

#### `RepairFields`

- Represents the fields of a repair record.
- **Properties:**
  - `RaftNumber`: Associated raft number (optional).
  - `Status`: Repair status.
  - `RecordCreationDateTime`: Creation date and time.
  - `RecordResolutionDateTime`: Resolution date and time (optional).
  - `Repair_Notes`: Notes about the repair (optional).
  - `Type`: Type of repair (optional).

---

## RaftMap Table

### Classes

#### `RaftMapResponse`

- Represents the response from the raft map API.
- **Properties:**
  - `records`: List of `RaftMapRecord` objects.
  - `offset`: Pagination offset (optional).

#### `RaftMapRecord`

- Represents an individual raft map record.
- **Properties:**
  - `id`: Unique identifier of the record.
  - `createdTime`: Creation time of the record.
  - `fields`: Associated raft map fields as `RaftMapFields`.

#### `RaftMapFields`

- Represents the fields of a raft map record.
- **Properties:**
  - `RaftNumber`: Associated raft number (optional).
  - `NFC_UUID`: NFC UUID (optional).
  - `Type`: Type of raft map (optional).

---

## River Data

### Class: `RiverData`

- Represents river data from the API.
- **Properties:**
  - `station_number`: Unique station identifier.
  - `station_name`: Station name.
  - `timestamp`: Timestamp of the data.
  - `level`: Water level.
  - `flow`: Flow rate (optional).
  - `id`: Unique data record identifier.

---

## Usage

These data classes can be used to deserialize JSON responses from APIs into Kotlin objects. Ensure that you have the Kotlin Serialization library set up in your project.

### Example

```kotlin
import kotlinx.serialization.json.Json

val jsonResponse = """{"records": [...], "offset": "abc123"}"""
val bookingResponse = Json.decodeFromString<BookingResponse>(jsonResponse)

println(bookingResponse.records.first().fields.Status)
```

This example demonstrates deserializing a JSON response into a `BookingResponse` object and accessing its properties.

---

## Conclusion

This documentation provides an overview of the data classes used for managing bookings, repairs, and raft maps. For further details, refer to the API specifications or project documentation.

