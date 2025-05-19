# Firebase Authentication with React, Node.js, Express, and Scalekit

This repository contains a sample implementation of Firebase Authentication with React, Node.js, Express, and Scalekit.

This is a simple example of how to implement Single Sign-On (SSO) authentication using Scalekit with Firebase.

The implementation can be done in either of the two ways.

Option 1: You can directly configure Scalekit as an OpenID Connect provider with Firebase and let the authentication process be handled by Firebase. This documentation clearly articulates how to configure Scalekit as an OpenID provider with Firebase. <https://docs.scalekit.com/integrations/firebase>

Option 2: You can directly implement SSO with Scalekit in your backend and use Firebase's custom auth capability to create a custom token to authenticate with Firebase. In this approach, you don't need to upgrade to Google Identity Platform but you may have to write a little bit of custom code to handle the authentication process. You can find the documentation for how to create custom tokens here: <https://firebase.google.com/docs/auth/admin/create-custom-tokens>

## Structure of the sample app

The sample app is structured as follows:

- backend: This is the backend server that handles the authentication process. It uses the Scalekit SDK to authenticate the user and then creates a custom token to authenticate with Firebase.
- frontend: This is the frontend React app that shows the simple login page where the user can authenticate via either Google or either of the Login with SSO Options.

## Running the React App

```bash
npm install
```

## Usage

```bash
npm run start
```

## Running the Backend Server

Go to the appropriate backend directory and run the following commands.

1. Make sure to replace the environment variables in the .env file with your own values that you can copy from Scalekit Dashboard.
2. Also copy your Service Account details from your Firebase console and update them in the ServiceAccount.json file.
3. By default, backend server is configured to run on port 5100.

```bash
npm install
```

```bash
npm run dev
```

## License

MIT License
