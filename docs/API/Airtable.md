# Airtable API Implementation Documentation

User -> Developer -> API Key -> Internet -> Airtable API -> Airtable Database

Welcome to the documentation for the TapTrack API library, part of the `org.lazyday.ldclient.API` package. This library provides a set of utilities to interact with Airtable APIs and other data sources. It simplifies error handling, retry logic, and serialization for API requests and responses.

## Table of Contents

1. [Overview](#overview)
2. [Usage](#usage)
3. [Functions](#functions)
    - [safeApiCall](#safeapicall)
    - [fetchBookings](#fetchbookings)
    - [fetchBooking](#fetchbooking)
    - [updateBooking](#updatebooking)
    - [fetchRepairRecords](#fetchrepairrecords)
    - [fetchRepairRecord](#fetchrepairrecord)
    - [updateRepairRecord](#updaterepairrecord)
    - [createRepairRecord](#createrepairrecord)
    - [deleteRepairRecord](#deleterepairrecord)
    - [fetchRaftMaps](#fetchraftmaps)
    - [fetchRaftMap](#fetchraftmap)
    - [fetchStationData](#fetchstationdata)
4. [Error Handling](#error-handling)

---

## Overview

The TapTrack API library is designed for ease of use with Airtable and similar APIs. It includes:
- A shared `HttpClient` instance with built-in retry logic.
- Utilities for managing API responses and exceptions.
- Functions for CRUD operations on Airtable resources such as bookings, repairs, and raft maps.

---

## Usage

To use the library, ensure you have the following dependencies in your project:

```kotlin
implementation("io.ktor:ktor-client-core:<version>")
implementation("io.ktor:ktor-client-json:<version>")
implementation("org.jetbrains.kotlinx:kotlinx-serialization-json:<version>")
implementation("co.touchlab:kermit:<version>")
```

Replace `<version>` with the appropriate versions for your project.

---

## Functions

### safeApiCall

A helper function for executing API calls with robust error handling.

#### Parameters
- `call`: A suspend function representing the API call.

#### Returns
- The result of the API call.

#### Exceptions
- Throws `ApiException` for client, server, or unexpected errors.

---

### fetchBookings

Fetches all booking records from the Airtable API.

#### Returns
- `List<Record>`: A list of booking records.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchBooking

Fetches a single booking record by ID.

#### Parameters
- `bookingId`: The ID of the booking to fetch.

#### Returns
- `BookingResponse`: The booking response object.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### updateBooking

Updates a booking record with new fields.

#### Parameters
- `bookingId`: The ID of the booking to update.
- `updatedFields`: The new fields to apply to the booking.

#### Returns
- `Record`: The updated booking record.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchRepairRecords

Fetches all repair records from the Airtable API.

#### Returns
- `List<RepairRecord>`: A list of repair records.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchRepairRecord

Fetches a single repair record by ID.

#### Parameters
- `recordId`: The ID of the repair record to fetch.

#### Returns
- `RepairResponse`: The repair response object.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### updateRepairRecord

Updates a repair record with new fields.

#### Parameters
- `recordId`: The ID of the repair record to update.
- `updatedFields`: The new fields to apply to the repair record.

#### Returns
- `RepairRecord`: The updated repair record.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### createRepairRecord

Creates new repair records.

#### Parameters
- `newFields`: A list of new fields for the repair records.

#### Returns
- `List<RepairRecord>`: The list of created repair records.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### deleteRepairRecord

Deletes a repair record by ID.

#### Parameters
- `recordId`: The ID of the repair record to delete.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchRaftMaps

Fetches all raftmap records from the Airtable API.

#### Returns
- `List<RaftMapRecord>`: A list of raftmap records.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchRaftMap

Fetches a single raftmap record by ID.

#### Parameters
- `recordId`: The ID of the raftmap record to fetch.

#### Returns
- `RaftMapResponse`: The raftmap response object.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

### fetchStationData

Fetches the latest station data from the Calgary data API.

#### Parameters
- `stationNumber` (optional): The station number to fetch data for. Defaults to `05BH004`.

#### Returns
- `List<RiverData>`: A list of river data objects.

#### Exceptions
- Throws `ApiException` if the API call fails.

---

## Error Handling

### ApiException

Custom exception class for handling API-related errors.

#### Parameters
- `message`: A description of the error.
- `cause`: The underlying cause of the error (optional).

### Retry Logic

The shared `HttpClient` is configured with retry logic to handle transient failures.

- **Maximum Retries**: 3
- **Exponential Delay**: Starts at 1.0s with a maximum delay of 5000ms.

---

For more details, visit the [GitHub Repository](https://github.com/Lazy-Day-Tech/LDClient).

