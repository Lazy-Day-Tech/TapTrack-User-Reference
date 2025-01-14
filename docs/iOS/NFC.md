# IOSNfcManager

IOSNfcManager is the main class for managing the NFC functionality on iOS devices. It uses the NfcDelegate class to handle NFC session events and communicates with the user via logs and shared data flows.

## Key Functions:
- startNfcScan: Starts a new NFC scan session.
    - Configures a NFCNDEFReaderSession and begins scanning for NDEF messages.
    - The session shows an alert message prompting the user to bring the device close to an NFC tag.
- stopNfcScan: Stops the current NFC scan session.


## NfcDelegate

The NfcDelegate class implements NFCNDEFReaderSessionDelegateProtocol, handling NFC session events such as detecting NDEF messages and session invalidation.
### Key Functions:
- `readerSession(didInvalidateWithError)`: Called when the NFC session is invalidated (e.g., error or user cancellation).
- `readerSession(didDetectNDEFs)`: Called when NDEF messages are detected in the session.
- `readerSessionDidBecomeActive`: Called when the NFC session becomes active and is ready to read NDEF messages.

## Helper Functions
- `NSData.toByteArray()`: An extension function that converts NSData to a ByteArray, which can then be decoded into a string or used for further processing.

