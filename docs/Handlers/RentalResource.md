# Rental Resource Handler

This document provides a detailed overview of the `rentalResource` function in the `org.lazyday.ldclient.handlers` package. This function is used to determine the appropriate drawable resource for a given rental list based on specific priorities.

---

## Package

`package org.lazyday.ldclient.handlers`

This function resides in the `handlers` package of the `org.lazyday.ldclient` project.

---

## Function Behavior

### Input:
- **`rental`**: A list of strings representing rental items (e.g., `"12-person raft"`, `"bowyak"`).

### Processing:
1. **Trim and Sort:**
   - Trims each item in the list.
   - Sorts the items in descending order of priority using a predefined ranking.

2. **Priority Mapping:**
   - Assigns a numerical priority to each rental item:
     - `"12-person raft"`: Priority 8
     - `"10-person raft"`: Priority 7
     - `"8-person raft"`: Priority 6
     - `"6-person raft"`: Priority 5
     - `"4-person raft"`: Priority 4
     - `"Kayak (Dual)"`: Priority 3 
     - `"Kayak (Solo)"`: Priority 2 
     - `"bowyak"`: Priority 1
     - Default: Priority 0

3. **Resource Selection:**
   - Maps the highest-priority rental item to a drawable resource using `Res.drawable`.
   - Defaults to `Res.drawable.ld6man` if no valid item is found.

4. **Logging:**
   - Logs the selected drawable resource using Kermit.

### Output:
- Returns a `DrawableResource` corresponding to the highest-priority rental item.

---

## Usage Example

```kotlin
val rentalList = listOf("bowyak", "12-person raft", "6-person raft")
val selectedResource = rentalResource(rentalList)
println("Drawable Resource: ${selectedResource.toString()}")
```

### Expected Output:
- Logs: `Selected rentalResource: Res.drawable.ld12man`
- Returns: `Res.drawable.ld12man`

---

## Logging

The function uses Kermit's `Logger.i` to log the selected resource:

```kotlin
Logger.i("rentalResource") { "Selected rentalResource: ${rentalImage.toString()}" }
```

This ensures that any issues with resource selection can be traced in the logs.

---

## Notes

- The function assumes that all necessary drawable resources are properly defined in `Res.drawable`.
- The priority order is hardcoded and may need updates if new rental items are introduced.

---

