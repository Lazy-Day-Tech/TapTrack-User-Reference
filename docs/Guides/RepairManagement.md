# Repair Management
This module allows users to manage the current and historical states of rafts.

## How Repair Records Work
Repair records include the following details:
1. Raft Number
2. Status
3. Record Creation Date & Time
4. Record Resolution Date & Time
5. Repair Notes
6. Type
7. Created By
8. Resolved By
9. Assigned To

## Locating a Repair Record
Repair records can be found using the following methods:
1. Manual Search
    - Search by Raft Number
2. NFC Scan
3. Lists
    1. In-Repair
        - Displays all repair records currently marked as in repair
    2. History
        - Displays all repair records sorted by date in descending order
    3. Assigned
        - Displays active repair records assigned to the logged-in user

### NFC
The NFC search tab activates the NFC scanner. When an NFC tag is scanned, the `RaftNumber` stored in the `RepairRecord` is mapped to its associated `NFC UUID` in the `RaftMap` table. If the raft is properly configured, its repair history will be displayed, allowing the user to select a specific record.

### Manual Search
In the Search tab, users can manually search for repair records by entering the Raft Number of the desired raft.

### In-Repair/History/Assigned
The In-Repair, History, and Assigned tabs provide quick access to repair records:
- **In-Repair**: Displays ongoing repairs.
- **History**: Shows the complete history of repair records.
- **Assigned**: Lists active repair records assigned to the logged-in user.

## Creating a Repair Record
Creating a repair record involves the following steps:

1. **Raft Number/NFC**  
    - Users can manually enter the raft number in a text field or scan the raft's NFC tag to retrieve the `RaftNumber` using its associated `NFC_UUID` from the `RaftMap` table.

2. **Type**  
    - The application attempts to auto-detect this information. If it cannot locate the raft's details in the `RaftMap` table, users must select the type from a dropdown list.

3. **Repair Notes**  
    - Users must provide a brief description of the issue (e.g., "Rip in floor").

4. **Confirmation**  
    - The application displays the entered details for user validation before submitting the record to the backend.

5. **Assign To** (Optional)  
    - If the user has the necessary permissions, they can assign the repair record to another user by selecting their display name from a dropdown list. This will make the record appear in the "Assigned" tab for the selected user.

> Once a repair record is created, the raft number and type cannot be modified.

![Flowchart](/docs/Assets/NewRepairRecordFlowchart.png)

## Managing a Repair Record
After a repair record is created, the following fields can be updated (if the user has the required permissions):
1. Repair Notes
2. Status
3. Assigned To
4. Delete

> Once a repair record is marked as resolved, it becomes unmodifiable. Any further changes require creating a new repair record.

> Once a change is made to an existing record. It will send the change to the backend and update the local viewmodel with the new change, removing the need to make additional API requests to sync data. 

### Assigning Repairs
After a user logs into the application for the first time, their display name becomes available for selection in the "Assign To" field of repair records. This assignment links the record to the user and makes it visible in their "Assigned" tab.

### Resolving Records
To resolve a repair record, change its status to "Repaired." This action adds a timestamp for the resolution date and time, and the record becomes unmodifiable. If additional changes are needed, a new repair record must be created.

### Record Aging
Repair records should be resolved within 48 hours of creation. Records older than 48 hours that remain unresolved will be displayed in red text to indicate priority. Additionally, users will see a notification within the repair record view highlighting its overdue status.