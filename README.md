<p align="center">
  <a href="https://scalekit.com" target="_blank" rel="noopener noreferrer">
    <picture>
      <img src="https://cdn.scalekit.cloud/v1/scalekit-logo-dark.svg" height="64">
    </picture>
  </a>
</p>

<h1 align="center">
  Firebase + Scalekit SSO Integration
</h1>

<p align="center">
  <strong>Auth stack for AI apps ⚡ Enterprise SSO with Firebase</strong>
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/@scalekit-sdk/node"><img src="https://img.shields.io/npm/v/@scalekit-sdk/node.svg" alt="npm version"></a>
  <a href="https://github.com/scalekit-inc/scalekit-firebase-sso/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License: MIT"></a>
  <a href="https://docs.scalekit.com/integrations/firebase"><img src="https://img.shields.io/badge/docs-Firebase%20Integration-blue" alt="Firebase Integration Guide"></a>
</p>

<p align="center">
  Add enterprise SAML/OIDC SSO to your existing Firebase authentication in hours, not weeks
</p>

## 🚀 What This Integration Shows

- **Dual Authentication Strategy**: Keep existing Firebase auth while adding enterprise SSO
- **Multiple Integration Patterns**: OIDC provider setup and custom token approaches
- **Zero Migration Required**: Add enterprise SSO without changing existing users or flows
- **Production-Ready Implementation**: Error handling, security, and scalability patterns 

## Implementation Choices
Firebase and Scalekit can be integrated in multiple ways depending on what you prefer and how you choose to implement. 

### Option 1: Configure Scalekit as an OIDC Provider on Firebase
1. If you are already using Firebase Identity Platform, then this method will be the easiest to implement. All you need to do is configure Scalekit as an OIDC Provider in your Firebase Console and instruct Firebase to choose this provider whenever your customers want to login via SSO. 
2. This documentation clearly articulates how to configure Scalekit as an OpenID provider with Firebase. <https://docs.scalekit.com/integrations/firebase>
3. In the App.js file, you can follow - signInwithScalekit() to see how this works.

### Option 2: Direct SSO Implementation with Custom Tokens on Firebase
1. If you are using Firebase Authentication version and don't want to upgrade to Firebase Identity Platform - then this could be an ideal option for you.
2. In this method, you will integrate your backend directly with Scalekit and fetch the user details from Scalekit after the user successfully logs in via their enterprise identity provider.
3. Using the details fetched from Scalekit - you will create a custom Firebase token and complete the authentication process with Firebase.
4. In the backend/src/index.js - you will see the sample code for how to integrate with Scalekit, how to create custom auth token and complete the authentication flow with Firebase. You can also find the documentation for how to create custom tokens here: <https://firebase.google.com/docs/auth/admin/create-custom-tokens>

## Structure of the sample app
The sample app is structured in two parts
### React App: 
- This react application is meant to show how you can implement a sample login page and use different ways to integrate Login with SSO in your login page.
- If you choose Option 1 to integrate Scalekit direcly as an OIDC provider, running the React Application should be enough to test the end-end login with SSO workflow.

### Express Backend Server:
- This backend server handles the routes to integrate with Scalekit, fetch the user profile, create custom token with firebase and all the other backend functionalities. 
- If you choose Option 2 to integrate Scalekit directly with your backend application - you need to run both the React App and Backend Server 

## Running the React App

```bash
npm install
npm run start
```

## Running the Backend Server

Go to the appropriate backend directory and run the following commands.

1. Make sure to replace the environment variables in the .env file with your own values that you can copy from Scalekit Dashboard.
2. Also copy your Service Account details from your Firebase console and update them in the ServiceAccount.json file.
3. By default, backend server is configured to run on port 5100.

```bash
npm install
npm run dev
```

## Key Integration Benefits

- **Keep Existing Users**: No migration needed for current Firebase users
- **Dual Authentication**: Consumer and enterprise users in the same application
- **Enterprise Grade**: SAML/OIDC support for major identity providers  
- **Flexible Architecture**: Choose OIDC provider or custom token approach
- **Scalable Solution**: Handle thousands of enterprise organizations

## Additional Resources

- 📚 [Firebase Integration Guide](https://docs.scalekit.com/integrations/firebase)
- 🔧 [Scalekit API Reference](https://docs.scalekit.com/apis)
- 💬 [Community Support](https://github.com/scalekit-inc/scalekit-sdk-node-js/discussions)
- 🎯 [Get Started Guide](https://docs.scalekit.com/quick-start-guide)
- ⚡ [Firebase Documentation](https://firebase.google.com/docs)
- 🔥 [Firebase Identity Platform](https://firebase.google.com/docs/auth)

## License
MIT License

## Credits
We would like to thank Wanuja for creating the base React, Firebase repo that we used to build on top of: <https://github.com/Wanuja97/firebase-authentication-with-react-node-express-article>

---

<p align="center">
  Made with ❤️ by <a href="https://scalekit.com">Scalekit</a>
</p>
