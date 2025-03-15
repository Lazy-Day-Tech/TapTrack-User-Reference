# LoginPage 

## Overview
The login page is the first page ran when the applicaiton is launched. 

The application will first attempt to connect to Google's authentication servers before allowing the user to attempt to authenticate. If the user has not already signed into an account, they will need to press the *"Sign in with Google"* button in order to initialize the authentication process. Otherwise the application will attempt to automatically authenticate

## Basic Authentication Workflow
1. Check if user has encrypted credentials already stored
    1. Check if encrypted credentials are valid
2. If user credentials not stored, require google authentication to continue.
    1. If the google email is on the list of authorized users, allow the user to authenticate
    2. Store encrypted credentials locally in keystore
    3. Update user information in backend