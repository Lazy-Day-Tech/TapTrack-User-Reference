# CheckInPage
## Overview

CheckInPage is a composable function that represents a user interface (UI) for checking in. Users can either scan a QR code or manually input information. The page handles NFC interactions, QR code scanning, and displays error dialogs. It also provides navigation capabilities to different screens and includes confirmation dialogs for NFC tag writing.

## Key Features
- **QR Code Scanning**: Users can scan a QR code to perform the check-in.
- **Manual Check-In**: A manual check-in option is available, allowing users to navigate to a different page for manual input.
- **NFC Integration**: The page interacts with an NFC manager for handling NFC tags.
- **Error Handling**: QR code scanning errors trigger an error dialog.
- **Customizable UI**: The page features a segmented button interface for selecting the QR scan or manual check-in options.
- **Blurred Background**: When a dialog is active, the background is blurred for better user focus.

## UI Elements
1. **Back Button**
    - **Description**: A back button (styled with an arrow icon) is placed at the top left corner of the screen. Clicking this button navigates the user back to the "ModeSelectionPage".
    - **Icon**: ArrowBack (from Icons.AutoMirrored.Filled).
    - **Action**: Navigates the user to the previous page.

2. **Page Title**
    - **Text**: Displays "Check-In Mode" in a gray color (ColorScheme.LDGrey).
    - **Font Style**: Medium font size (14sp), aligning with the back button on the same row.

3. **Segmented Buttons**
    - **Description**: Two segmented buttons are used for selecting between "Scan QR" and "Manual" check-in modes. Each button displays an icon and label.
        - **Scan QR**: Initiates QR scanning when selected.
        - **Manual**: Navigates the user to the "ManualInput/CheckInPage".
    - **Icons**:
        - **QR Scan**: Uses a QR code icon (qr2 from resources).
        - **Manual**: Uses an edit icon (edit from resources).

4. **QR Code Scanner**
    - **Description**: When the "Scan QR" button is selected, the app initiates a QR code scanning session. A semi-transparent overlay is displayed to guide the user to align the QR code within the scanner frame.
    - **Instructions**: Displays "Align the QR code within the frame to scan" at the top of the screen.
    - **Failure Handling**: If the QR code scan fails, an error dialog is triggered.

5. **Confirmation Dialog for NFC Tag**
    - **Description**: If the NFC tag is written successfully, a confirmation dialog (tagWriteConfirmationDialog) is displayed, asking the user to confirm the tag writing action.
    - **Blur Effect**: When the dialog is active, the background is blurred to emphasize the dialog content.

6. **Error Dialog for QR Scanning**
    - **Description**: If the QR code scan fails, an error dialog (qrErrorDialog) is shown to the user, providing a message and an option to dismiss it.
    - **Message**: "QR Code Scanning Failed. Please try again. If the issue persists, please contact support."

7. **Exit Button**
    - **Description**: While QR scanning is active, an exit button is displayed at the top-right corner. This button allows users to cancel the scan and return to the previous screen.
