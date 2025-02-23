# Customer Acknowledgement Component Guide

The `CustomerAcknowledgement` function is designed to inform customers about specific conditions related to their booking and obtain their agreement before proceeding.

## What It Does

This component serves as a notification and confirmation tool. When you book an activity, there may be special warnings or advisories you need to be aware of. This interface will display these warnings and require your acknowledgment.

### Key Features

- **Warnings Display**: Depending on the booking details, you might see one or more warning messages about conditions like using inflatable kayaks (BowYak) or potential stormy weather during a rafting trip.
  
- **Acknowledgment Requirement**: For each warning displayed, you need to type "I agree" to acknowledge that you understand and accept these conditions.

- **Navigation Options**:
  - **Decline**: If you decide not to proceed with the booking under these warnings, simply choose "Decline". This will take you back without making any changes.
  - **Agree**: Once you've acknowledged all necessary warnings by typing "I agree", you can confirm your agreement. This action updates your booking status and logs that you accepted the terms. This will also launch a new instance of BookingRecordView automatically, allowing the user to continue the checkin process where they left off

### How to Use

1. **View Warnings**: The system automatically shows relevant warnings based on your booking details. Read each warning carefully.

2. **Acknowledge**:
   - Enter "I agree" in the text field provided for each warning.
   - Your focus will be cleared once you type this, indicating that acknowledgment is complete.
   - A new instance of BookingRecordView will be launched. After the booking record view, the user will be moved back to their initial page

3. **Make a Decision**:
   - If you are comfortable with the conditions and have acknowledged them, click "Agree". This confirms your acceptance of the terms associated with your booking.
   - If you prefer not to proceed under these conditions, choose "Decline" to cancel this process.

### Important Notes

- Your confirmation ("I agree") is necessary for each warning presented. Make sure to acknowledge all that apply before proceeding.
- Once you agree, the booking details are updated to reflect your acceptance of the warnings, and the user may continue the check-in process as normal
