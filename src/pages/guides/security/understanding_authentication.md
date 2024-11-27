---
keywords:
  - Adobe I/O
  - Extensibility
  - API Documentation
  - Developer Tooling
title: Understanding Authentication
---

# Understanding Authentication

If you plan to work with Adobe APIs in your custom application, please follow this chapter to understand Adobe Authentication and the libraries that you can leverage. 

Adobe services like Creative SDK, Photoshop, Adobe Analytics, etc. use the OAuth 2.0 protocol for authentication and authorization. Using Adobe OAuth 2.0, you can generate an access token which is used to make API calls from your web server or browser-based apps. You can learn more about it at [OAuth 2.0 Authentication and Authorization](/developer-console/docs/guides/authentication/OAuth/).

API services tied to entitled Adobe products (e.g. Campaign, Target, etc.) require a JSON Web Token (JWT) in order to retrieve access tokens for usage against authenticated endpoints. [This document](/developer-console/docs/guides/authentication/JWT/) serves as a quickstart guide for first-time users.

Certain products, like Adobe Analytics 2.0, allow both types of integrations. You can choose to use an OAuth client if you are creating an application that requires an end user to authenticate before calling the Adobe Analytics APIs; JWT client if creating an application that needs to programmatically authenticate calls to the Adobe Analytics APIs.

To simplify your interaction with Adobe authentication, we have created a library.

You can configure it and try it out directly at 
- [Adobe I/O IMS SDK Library](https://github.com/adobe/aio-lib-ims)

**Note:** The Service Account (JWT) credentials have been deprecated in favor of the OAuth Server-to-Server credentials. Your applications using the Service Account (JWT) credentials will stop working after Jan 27, 2025. You must migrate to the new credential by **Jan 27, 2025**, to ensure your application continues functioning.

To migrate your old Service Account (JWT) credentials to the new OAuth Server-to-Server credentials, follow the steps mentioned in the [migration guide](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration).

Once you update your application code to use the new credential to generate access tokens, you can deploy your updated application to test, staging, and production environments.
Even for already published applications, you can deploy these code changes without any downtime or re-publishing the application. To do this using the AIO CLI, run the command `aio app deploy --force-deploy --no-publish` 


