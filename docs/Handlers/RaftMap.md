# RaftMap Handlers
The RaftMap Handlers module provides functions that assist in the process of fetching and filtering RaftMapRecord items based on specific identifiers like NFC UUID and raft number. These handlers are used to retrieve the relevant RaftMapRecord associated with a specific raft or NFC tag.

## Functions

### NFCUuidToRaft

```kotlin
suspend fun NFCUuidToRaft(nfcUUID: String): RaftMapRecord
```

#### Description:
This function fetches a RaftMapRecord by filtering the raft map items based on the provided NFC UUID. It is primarily used for matching a specific NFC tag to a raft map record.

#### Parameters:
- `nfcUUID`: A String representing the NFC UUID used to filter the raft map items.

#### Returns:
- A RaftMapRecord object that matches the provided NFC UUID. This is the first record that matches the given NFC UUID.

#### Logs:
- Logs the RaftMap ID for the found record.

#### Throws:
- If no matching RaftMapRecord is found, this function will throw an exception.

#### Example Usage:

```kotlin
val raftRecord = NFCUuidToRaft("12345678-1234-1234-1234-1234567890ab")
```

##### Example Output:

- `Found Raft Record: raft1234`

---

### RaftNumberToRaft

```kotlin
suspend fun RaftNumberToRaft(raftNumber: String): RaftMapRecord
```

#### Description:
This function fetches a RaftMapRecord by filtering the raft map items based on the provided raft number. It is used to retrieve a raft map record associated with a specific raft number.

#### Parameters:
- `raftNumber`: A String representing the raft number used to filter the raft map items.

#### Returns:
- A RaftMapRecord object that matches the provided raft number. This is the first record that matches the given raft number.

#### Logs:
- Logs the RaftMap ID for the found record.

#### Throws:
- If no matching RaftMapRecord is found, this function will throw an exception.

#### Example Usage:
```kotlin
val raftRecord = RaftNumberToRaft("raft101")
```

#### Example Output:

- `Found Raft Record: raft5678`

## Dependencies
- fetchRaftMaps: A function that fetches a list of RaftMapRecord items from the data source.
- RaftMapRecord: A data model representing a raft map record.
- Logger: A logging tool used to record events and outputs, providing insights into the function’s execution.
