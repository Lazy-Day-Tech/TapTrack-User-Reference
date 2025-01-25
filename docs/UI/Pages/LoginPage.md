### LoginPage Documentation

#### Overview
`LoginPage` is a composable function that handles the user login process. It checks for existing user tokens, initializes Google authentication, and navigates the user to the appropriate page based on the authentication status.

#### Parameters
- `navController`: An optional `NavController` instance used for navigation between different pages.

#### State Variables
- `authReady`: A boolean state indicating if the authentication process is ready to start.
- `userRecords`: A list of `UserRecord` objects representing the user records fetched from the backend.
- `loginFailMessage`: A mutable state holding the message to be displayed in case of login failure.
- `showLoginFailDialog`: A boolean state indicating if the login failure dialog should be shown.
- `loading`: A boolean state indicating if the login process is currently loading.

#### Effects
- `LaunchedEffect`: This effect is triggered when the `LoginPage` composable is first launched. It fetches user records, checks for existing user tokens, and initializes Google authentication if necessary.

#### UI Components
- **Surface**: The main container for the login page, styled with a background color.
- **Column**: A vertical layout container that holds the various UI elements.
- **Spacer**: Used to add vertical spacing between UI elements.
- **Image**: Displays the application logo.
- **Divider**: A horizontal line used to separate sections of the UI.
- **Text**: Displays various text messages, including the welcome message and instructions.
- **Box**: A container for the Google sign-in button.
- **GoogleButtonUiContainer**: A custom container for the Google sign-in button, handling the sign-in result.
- **GoogleSignInButton**: The actual button that triggers the Google sign-in process.

#### Dialogs
- **ErrorDialogue**: A custom dialog displayed when the login process fails, showing the `loginFailMessage`.

#### Authentication Flow
1. **Fetch User Records**: Retrieves the list of valid user records from the backend.
2. **Check User Token**: Checks if a locally stored user token exists and is valid.
3. **Navigate to ModeSelectionPage**: If the token is valid, navigates the user to the `ModeSelectionPage`.
4. **Initialize Google Auth**: If no valid token is found, initializes the Google authentication process.
5. **Handle Google Sign-In Result**: Processes the result of the Google sign-in, checking if the user is authorized and updating the user record if necessary. Also encrypts and stores user token and display name to native secure keystore
6. **Show Login Failure Dialog**: If the login fails, displays an error dialog with the appropriate message.