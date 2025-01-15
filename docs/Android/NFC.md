# AndroidNFCManager
## Overview
The AndroidNfcManager class is responsible for managing NFC (Near Field Communication) operations on Android devices. It provides the functionality to start and stop NFC scanning, handle detected NFC tags, and notify other parts of the application about the scanned data through a SharedFlow. The class integrates with Android's NfcAdapter to enable or disable NFC reader mode and handle tag reading operations.
## Key Features
- **NFC Tag Scanning**: Initiates NFC scanning to detect NFC tags and retrieve data from them.
- **SharedFlow Integration**: Uses a SharedFlow to emit the payload of scanned NFC tags, allowing other parts of the application to observe and react to NFC data.
- **NFC Error Handling**: Displays a dialog if the device does not support NFC.
- **Coroutines and Concurrency**: Leverages Kotlin coroutines to manage background tasks and update the UI on the main thread.

## Usage
The AndroidNfcManager class requires a Context (such as an Activity or Application) to interact with the NFC system and display dialogs.
### Properties
- `nfcAdapter`:
    - This is a lazy-loaded property that retrieves the NfcAdapter from the device. It is used to start and stop the NFC scan.

- `_tagData (MutableSharedFlow<String>)`:
    - This private property holds the flow of data from scanned NFC tags. It emits the payload of NFC tags as a String.

- `tags (SharedFlow<String>)`:
    - This public property exposes the _tagData shared flow to other components, allowing them to observe NFC tag payloads as they are scanned.

- `scope (CoroutineScope)`:
    - A coroutine scope for managing background tasks. This scope ensures that NFC tag handling and data emission occur on the main thread, while the background tasks (like reading the tag) are managed on a different thread.

## Methods
`startNfcScan()`

`override fun startNfcScan()`

Starts the NFC scan process. If the device does not support NFC, the method shows a dialog indicating this to the user and logs the event.

### Behavior:
- If NFC is supported, it enables the NFC reader mode with NfcAdapter.FLAG_READER_NFC_A and NfcAdapter.FLAG_READER_NFC_B flags to read NFC tags.

- Error Handling:
    - If the device does not have an NFC adapter, an AlertDialog is shown with a message indicating that NFC is not supported.

`stopNfcScan()`

`override fun stopNfcScan()`

Stops the NFC scan by disabling the NFC reader mode.
- Behavior:
   - It disables the NFC reader mode and logs the action.

`handleNfcTag(tag: Tag)`

`private fun handleNfcTag(tag: Tag)`

Handles the detected NFC tag, reads the NDEF message, and emits the payload of the tag.

### Parameters:
- tag — The detected Tag object, representing the scanned NFC tag.

- Behavior:
    - The method attempts to read the NDEF message from the NFC tag. If the message is valid, it extracts the payload (if available) and emits it via the _tagData flow.

`showNoNfcSupportDialog()`

`private fun showNoNfcSupportDialog()`

Displays an AlertDialog to the user, indicating that the device does not support NFC functionality.

#### Behavior:
This method is invoked when NFC is not available on the device, providing the user with information about the lack of NFC support.

#### Example Usage
```kotlin
val nfcManager = AndroidNfcManager(context)
nfcManager.startNfcScan()

// Observe NFC tags being scanned
nfcManager.tags.collect { tagData ->
    println("NFC Tag Data: $tagData")
}

// Stop NFC scan when no longer needed
nfcManager.stopNfcScan()
```

## Key Considerations
- **Permissions**: Ensure that the appropriate permissions (android.permission.NFC) are declared in the app's AndroidManifest.xml.
- **NFC Support**: This class checks whether the device supports NFC and handles the case where NFC is unavailable by showing a dialog to the user.
    - **UI Thread**: The class uses a coroutine scope to handle background - NFC reading operations, ensuring that updates to the UI or shared state (via SharedFlow) occur on the main thread.
