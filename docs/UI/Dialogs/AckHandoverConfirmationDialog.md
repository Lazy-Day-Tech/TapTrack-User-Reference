# AckHandoverConfirmationDialog

`AckHandoverConfirmationDialog` is designed to display a confirmation dialog that requires user acknowledgment before proceeding with an action. This document provides guidance on how this component works and can be utilized.

## Overview

This dialog is used when a specific customer action or acknowledgment is necessary before continuing with a process. It presents users with a message and a visual icon, alongside a "Confirm" button to finalize their acknowledgment.

### Key Features

- **Customizable Message**: The dialog displays an informative message that can be customized based on the context of its usage.
  
- **Icon Display**: Alongside the message, a customizable icon is shown for additional visual information or emphasis.

- **User Interaction**:
  - Users are required to click "Confirm" in order to acknowledge and proceed with their decision.
  - The dialog automatically dismisses if the user taps outside of it or presses the back button, providing flexibility in how users can cancel the action.

### Design Elements

- **Visual Styling**: 
  - The dialog is styled with rounded corners and a border to make it visually distinct.
  - It utilizes colors from `ColorScheme` for consistency throughout the application's UI. 

- **Components**:
  - **Text Fields**: Used to convey the main message and title of the acknowledgment requirement.
  - **Divider**: Serves as a visual separation between different sections within the dialog.
  - **Icon**: A vector image is displayed next to the text for additional context or emphasis.

## How to Use

1. **Configure the Dialog**:
   - Customize the `message` parameter with the specific information you want to present to the user.
   - Set the `Icon` resource to provide a visual cue related to the message.

2. **Handle User Actions**:
   - Define what should happen when users click "Confirm" by providing an action to the `onConfirm` parameter.
   - Provide an action for the dialog dismissal through the `onDismiss` parameter if specific cleanup or additional steps are needed.

3. **Display the Dialog**: Invoke this composable function in your UI code where you need to prompt user acknowledgment, passing all required parameters (message, icon, and callbacks).

