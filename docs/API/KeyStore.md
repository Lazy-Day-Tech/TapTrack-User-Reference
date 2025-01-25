# Native Secure Keystore

The `Config` object provides methods to get and set various configuration values such as API keys, user tokens, and user display names. This object is expected to be implemented for different platforms.

## Properties

### `getEncrypedAPIKey`
- **Type:** `String`
- **Description:** Retrieves the encrypted API key.

### `setEncryptedAPIKey`
- **Type:** `String`
- **Description:** Sets the encrypted API key.

### `getUserToken`
- **Type:** `String`
- **Description:** Retrieves the user token.

### `setUserToken(token: String)`
- **Type:** `Unit`
- **Description:** Sets the user token.
- **Parameters:**
  - `token`: The user token to be set.

### `getUserDisplayName`
- **Type:** `String`
- **Description:** Retrieves the user display name.

### `setUserDisplayName(displayName: String)`
- **Type:** `Unit`
- **Description:** Sets the user display name.
- **Parameters:**
  - `displayName`: The user display name to be set.