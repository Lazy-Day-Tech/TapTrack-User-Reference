# Data Handlers


### DuplicateRentalHandler
This function processes a list of rental identifiers and identifies duplicate rentals.

#### Parameters
- `rentals (List<String>)`: A list of rental identifiers (e.g., rental IDs or raft IDs).

#### Returns
- _List<String>:_ A list of rental identifiers, with duplicates labeled in the format "rental xN", where N is the number of times that rental appears in the list. Non-duplicate rentals are returned as-is.

#### Example

```kotlin
val rentals = listOf("Raft1", "Raft2", "Raft1", "Raft3", "Raft2")
val result = duplicateRentalHandler(rentals)
// Result: ["Raft1 x2", "Raft2 x2", "Raft3"]
```

---

### countRentalsByTypeAndStatus

Counts the rentals based on raft type, rental status, and the date they were rented (default is today).
#### Parameters
- `rentals (List<List<Any>>)`: A list of rental records, where each record is a list of different types of data (e.g., rental ID, raft type, status, date, etc.).
- `raftType (String)`: The raft type to filter by (optional). If empty, all raft types are considered.
- `rentalStatus (String?, optional)`: The rental status to filter by (optional). If null, no filtering by status is done.

#### Returns
- `Int`: The count of rentals that match the given criteria.

#### Example

```kotlin
val rentals = listOf(
    listOf("Raft1", "Large", "Not Checked-In", LocalDateTime(2023, 10, 14, 10, 0), "Customer1", "Not Checked-In"),
    listOf("Raft2", "Medium", "Launched", LocalDateTime(2023, 10, 14, 9, 0), "Customer2", "Launched")
)
val count = countRentalsByTypeAndStatus(rentals, "Large", "Not Checked-In")
// Result: 1
```

--- 

### getTotalRentalsToday

Returns the total number of rentals today, regardless of raft type or status.
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.

#### Returns
- `Int`: The total number of rentals today.

#### Example

```kotlin
val totalRentals = getTotalRentalsToday(rentals)
// Result: 2
```

---

### getCurrentlyCheckedIn

Returns the number of rentals checked in today with the status "Launched".
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.

#### Returns
- `Int`: The number of rentals with the status "Launched" today.

#### Example

```kotlin
val checkedIn = getCurrentlyCheckedIn(rentals)
// Result: 1
```

---

### getCurrentlyNotCheckedIn

Returns the number of rentals that are not checked in today with the status "Not Checked-In".
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.

#### Returns
- `Int`: The number of rentals with the status "Not Checked-In" today.

#### Example

```kotlin
val notCheckedIn = getCurrentlyNotCheckedIn(rentals)
// Result: 1
```

---

### getCurrentlyReturned

Returns the number of rentals that have been returned today with the status "Returned".
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.

#### Returns
- `Int`: The number of rentals with the status "Returned" today.

#### Example

```kotlin
val returned = getCurrentlyReturned(rentals)
// Result: 0
```

---

### getTotalRaftsToday

Returns the total number of rentals today for a specific raft type.
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.
- `raftType (String)`: The raft type to filter by.

#### Returns
- `Int`: The total number of rentals of the specified raft type today.

#### Example

```kotlin
val totalRafts = getTotalRaftsToday(rentals, "Large")
// Result: 1
```

---

### getRaftsCheckedInToday

Returns the number of rentals that are checked in today for a specific raft type.
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.
- `raftType (String)`: The raft type to filter by.

#### Returns
- `Int`: The number of checked-in rentals of the specified raft type today.

#### Example

```kotlin
val raftsCheckedIn = getRaftsCheckedInToday(rentals, "Large")
// Result: 0
```

---

### getRaftsNotCheckedInToday

Returns the number of rentals that are not checked in today for a specific raft type.
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.
- `raftType (String)`: The raft type to filter by.

#### Returns
- `Int`: The number of not checked-in rentals of the specified raft type today.

#### Example

```kotlin
val raftsNotCheckedIn = getRaftsNotCheckedInToday(rentals, "Large")
// Result: 1
```

---

### getRaftsReturnedToday

Returns the number of rentals that have been returned today for a specific raft type.
#### Parameters
- `rentals (List<List<Any>>)`: The list of rental records.
- `raftType (String)`: The raft type to filter by.

#### Returns
- `Int`: The number of returned rentals of the specified raft type today.

#### Example

```kotlin
val raftsReturned = getRaftsReturnedToday(rentals, "Large")
// Result: 0
```

---

### FormatPhoneNumber()

This function formats a 10-digit phone number into the format (xxx) xxx-xxxx.
#### Parameters
- `phoneNumber (String)`: The phone number to be formatted. It must contain exactly 10 digits.

#### Returns
- `String`: The formatted phone number in the format (xxx) xxx-xxxx.

#### Throws
- `IllegalArgumentException`: If the phone number does not contain exactly 10 digits.

#### Example

```kotlin
val formattedPhone = formatPhoneNumber("1234567890")
// Result: "(123) 456-7890"
```

---
### findMatchingQRCode()
This function provides lookup functionality for finding qr codes associated with a booking

#### Parameters
- `qrCode (String)`: The QR code to lookup (Pass from qr scanner)

#### Returns
- **BookingRecord**

#### Throws
- `IllegalArgumentException`: If no matching booking for QR code value.

---