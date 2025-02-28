# Users

This contains various utility functions for handling user records, including checking user activity, retrieving user records, and managing user tokens.

#### Functions

1. **`isActiveUser`**
    - **Description**: Checks if the given email belongs to an active user.
    - **Parameters**:
        - `users`: List of `UserRecord` objects.
        - `email`: Email address to check.
    - **Returns**: `Boolean` indicating if the email is an active user.

2. **`doesTokenExist`**
    - **Description**: Checks if the given token exists in the user records.
    - **Parameters**:
        - `users`: List of `UserRecord` objects.
        - `userTokenId`: Token ID to check.
    - **Returns**: `Boolean` indicating if the token exists.

3. **`getUserRecord`**
    - **Description**: Retrieves the user record associated with the given email.
    - **Parameters**:
        - `users`: List of `UserRecord` objects.
        - `email`: Email address to search for.
    - **Returns**: `UserRecord` object if found, `null` otherwise.

4. **`getUserRecordByToken`**
    - **Description**: Retrieves the user record associated with the given token ID.
    - **Parameters**:
        - `users`: List of `UserRecord` objects.
        - `userTokenId`: Token ID to search for.
    - **Returns**: `UserRecord` object if found, `null` otherwise.

5. **`clearRemoteUserToken`**
    - **Description**: Clears the token for the given user record on the remote server.
    - **Parameters**:
        - `userRecord`: `UserRecord` object whose token needs to be cleared.
    - **Returns**: `Unit`

6. **`clearLocalUserData`**
    - **Description**: Clears the local encrypted user data (token and display name).
    - **Parameters**: None
    - **Returns**: `Unit`

7. **`setLocalUserData`**
    - **Description**: Sets the local encrypted user data (token and display name).
    - **Parameters**:
        - `userToken`: User token to set.
        - `userDisplayName`: User display name to set.
    - **Returns**: `Unit`
8. **`getUserNames`**
    - **Description**: Retrieves the display names of all users.
    - **Parameters**: None
    - **Returns**: List of user display names.
9. **`getUserPermission`**
    - **Description**: Fetches a list of all permissions assigned to the currently authenticated user
    - **Parameters**: None
    - **Returns**: `List<String>`

### Note:
The function `getUserNames()` is a suspending function that can be used in asynchronous code, it uses `fetchUserRecords()` to retrieve the list of users and then extracts 
the display names from each user record.

