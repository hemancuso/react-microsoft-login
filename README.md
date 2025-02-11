# react-microsoft-login [![npm version](http://img.shields.io/npm/v/react-microsoft-login.svg)](https://npmjs.org/package/react-microsoft-login) ![npm bundle size](https://img.shields.io/bundlephobia/minzip/react-microsoft-login) ![Libraries.io dependency status for GitHub repo](https://img.shields.io/librariesio/github/alexandrtovmach/react-microsoft-login)


React component for a simple login with Microsoft services, based on [Official Microsoft Authentication Library for JavaScript](https://github.com/AzureAD/microsoft-authentication-library-for-js).

<p align="center">
  <img src="https://user-images.githubusercontent.com/28801003/65941169-0cc1c000-e433-11e9-909d-bd97be8100b2.jpg" alt="buttons">
</p>

**[DEMO HERE](https://alexandrtovmach.github.io/react-microsoft-login/)**

## 🚀 Get started

1. Install package:
   ```sh
   yarn add react-microsoft-login
   ```
2. Import and configure component:

   ```jsx
   import React from "react";
   import MicrosoftLogin from "react-microsoft-login";

   export default props => {
     const authHandler = (err, data) => {
       console.log(err, data);
     };

     return (
       <MicrosoftLogin clientId={YOUR_CLIENT_ID} authCallback={authHandler} />
     );
   };
   ```

3. `YOUR_CLIENT_ID` is the key which you need to generate for your Microsoft app. [How to create Microsoft app?](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-v2-register-an-app) When finished, on the app Overview page, note down the Application (client) ID value.

##  API

| Parameter             | Type           | Default                | Description                                                                                                                                                                                                                                         |
| --------------------- | -------------- | ---------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| clientId              | string         | required               | Application (client) ID                                                                                                                                                                                                                             |
| authCallback          | function       | required               | Callback function which takes two arguments `(error, authData)`                                                                                                                                                                                     |
| graphScopes           | array          | `["user.read"]`        | Array of Graph API permission names. [More about Graph API permissions](https://developer.microsoft.com/en-us/graph/docs/concepts/permissions_reference).                                                                                           |
| tenantUrl             | string         | `""`                   | A URL indicating a directory that MSAL can request tokens from. [More about MSAL tenant auth](https://github.com/AzureAD/microsoft-authentication-library-for-js/wiki/MSAL-basics).                                                                 |
| redirectUri           | string         | `window.location.href` | The redirect URI of the application, this should be same as the value in the application registration portal.                                                                                                                                       |
| buttonTheme           | string         | `"light"`              | Name of theme for button style. Themes: `"light"` `"light_short"` `"dark"` `"dark_short"`. Styles come from [Official Microsoft brand design](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-add-branding-in-azure-ad-apps). |
| withUserData          | boolean        | `false`                | Boolean flag to make an additional request to GraphAPI to get user data.                                                                                                                                                                            |
| forceRedirectStrategy | boolean        | `false`                | Boolean flag to force redirect login strategy for all browsers. This strategy used by default just for IE browsers to avoid issues.                                                                                                                 |
| debug                 | boolean        | `false`                | Boolean flag to enable detailed logs of authorization process.                                                                                                                                                                                      |
| className             | string         | `""`                   | Additional class name string.                                                                                                                                                                                                                       |
| children              | ReactComponent | `null`                 | Alternative way to provide custom button element as a children prop instead of [Official Microsoft brand design](https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-add-branding-in-azure-ad-apps)                               |

## License

[MIT](https://github.com/nishanths/license/blob/master/LICENSE)
