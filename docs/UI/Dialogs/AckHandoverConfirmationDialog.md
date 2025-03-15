# AckHandoverConfirmationDialog

`AckHandoverConfirmationDialog` is designed to display a confirmation dialog that requires user acknowledgment before proceeding with an action. This document provides guidance on how this component works and can be utilized.

## Overview

This dialog is used when a specific customer action or acknowledgment is necessary before continuing with a process. It presents users with a message and a visual icon, alongside a "Confirm" button to finalize their acknowledgment.

## Triggers
1. If 1 or more bowyaks are associated with the booking
2. ~~If there is a potential storm incoming~~ (Not yet implemented)

## Functionlity
1. If triggered,
2. Display warining to employee that further confirmation is needed for the booking before it can be checked-in
3. After the employee dismisses the warning dialog, a new page will appear
4. Customer must type "I agree" In any required fields on the page. 
5. Once the user enters in all text boxes, a confirm button will enable at the bottom of the screen
6. Once confirmed, the confirmation will be logged to the remote booking information and the checkin process can continue 

See [CustomerAcknowlegement](https://lazy-day-tech.github.io/TapTrackDocs/Pages/CustomerAcknowledgement)