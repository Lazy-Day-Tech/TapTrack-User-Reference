# Native Secure Keystore

The `Config` object provides methods to get and set various configuration values such as API keys, user tokens, and user display names to the encrypted native keystore.

The keystore is intended to secure any sensitive information that needs to be stored locally on device. This includes:
1. **Token ID**: The token provided by Google Authentication on sign in. This token is used for automatic authentication once the user authenticates a first time. Only the active account is stored. 
2. **Display Name**: The display name of the user provided by Google Authentication on first time Google Auth sign in. Only the active account is stored locally.
> All values are also provided to the backend to be stored in remote user account information