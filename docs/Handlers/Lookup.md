# Lookup Handlers


## findMatchingQRCode

#### Overview

Finds a matching booking record by QR code.

#### Parameters

* `qrCode`: The QR code to match against booking records.
* `list` (Optional): a list of booking records to compare the QR code against. If none provided, it will automatically fetch **today's** bookings from the backend

#### Returns

The matching booking record, or null if no match is found or an error occurs.

#### Behavior

This function fetches booking records and filters them to find a record that matches the provided QR code. It logs the result and returns the matching 
record if found, or null if no match is found or an error occurs.

#### Example Usage
```kotlin
val qrCode = "your-qr-code-here"
val matchingRecord = await(findMatchingQRCode(qrCode))
```

## parseRentals

#### Overview

Parses a string of rental information into a list of individual rentals.

#### Parameters

* `rentals`: A string containing rental information, separated by commas.

#### Returns

A list of individual rentals, or an empty list if the input is null or empty.

#### Behavior

This function splits the input string into individual rentals and trims any leading or trailing whitespace from each rental. It returns an empty list 
if the input is null or empty.

#### Example Usage
```kotlin
val rentals = "rental1,rental2,rental3"
val parsedRentals = parseRentals(rentals)
println(parsedRentals) // prints [rental1, rental2, rental3]
```

Note: The `await` function is not shown here as it's a part of the coroutine context and not directly related to the handler functions.

## fetchItemAvailabilityCount

#### Overview:
Takes a list of `raftMapRecords` and `repairRecords`, then compares them against the provided `type` or `null` to determine the number of available rafts for each type or all.

#### Returns:

`Int` of item available