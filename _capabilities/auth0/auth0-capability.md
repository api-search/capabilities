---
categories: []
consumed_apis: []
description: Auth0 exposes the following APIs for developers to consume in their applications.
layout: capability
name: Auth0 API
operations:
- description: Auth0 Authenticate a user with a social provider, Database/AD/LDAP (Passive), SAML/Windows Azure AD (Passive), Authorization Code Flow, Authorization Code Grant (PKCE) Flow, or Implicit Flow
  method: GET
  name: authorize
  path: /authorize
- description: Auth0 Logout a user
  method: GET
  name: logout
  path: /v2/logout
- description: Auth0 Logout a user
  method: GET
  name: oidc-logout
  path: /oidc/logout
- description: Auth0 Logout a user
  method: POST
  name: saml-logout
  path: /samlp/{CLIENT_ID}/logout
- description: Auth0 Start Passwordless flow
  method: POST
  name: passwordless-start
  path: /passwordless/start
- description: Auth0 Verify with verification code
  method: POST
  name: passwordless-verify
  path: /passwordless/verify
- description: Auth0 Authenticates a user using a verification code, verifies multi-factor authentication (MFA) using a one-time password (OTP), out-of-band (OOB) challenge, or a recovery code, or exchanges an Authorization Code for a Token
  method: POST
  name: oauth-token
  path: /oauth/token
- description: Auth0 Signup with user's credentials
  method: POST
  name: dbconnections-signup
  path: /dbconnections/signup
- description: Auth0 Send a change password email
  method: POST
  name: dbconnections-change-password
  path: /dbconnections/change_password
- description: Auth0 Returns a user's profile
  method: GET
  name: userinfo
  path: /userinfo
- description: Auth0 Request a challenge for multi-factor authentication
  method: POST
  name: mfa-challenge
  path: /mfa/challenge
- description: Auth0 Associates or adds a new authenticator for multi-factor authentication (MFA).
  method: POST
  name: mfa-associate
  path: /mfa/associate
- description: Auth0 Returns a list of authenticators associated with your application.
  method: GET
  name: mfa-authenticators
  path: /mfa/authenticators
- description: Auth0 Deletes an associated authenticator using its ID.
  method: DELETE
  name: mfa-authenticators-delete
  path: /mfa/authenticators/{AUTHENTICATOR_ID}
- description: Auth0 Use this endpoint to accept a SAML request to initiate a login.
  method: GET
  name: samlp-login
  path: /samlp/{client_id}
- description: Auth0 This endpoint returns the SAML 2.0 metadata.
  method: GET
  name: samlp-metadata
  path: /samlp/metadata/{client_id}
- description: Auth0 This endpoint accepts an IdP-Initiated Sign On SAMLResponse from a SAML Identity Provider.
  method: POST
  name: login-callback
  path: /login/callback
- description: Auth0 This endpoint accepts a WS-Federation request to initiate a login.
  method: GET
  name: wsfed-login
  path: /wsfed/{client_id}
- description: Auth0 This endpoint returns the WS-Federation metadata.
  method: GET
  name: wsfed-metadata
  path: /wsfed/FederationMetadata/2007-06/FederationMetadata.xml
- description: With a name and the necessary callback URL, you can dynamically register a client with Auth0. No token is needed for this request.
  method: POST
  name: oidc-register
  path: /oidc/register
- description: Auth0 Get Device Code
  method: POST
  name: oauth-device-code
  path: /oauth/device/code
- description: Auth0 Revoke Refresh Token
  method: POST
  name: oauth-revoke
  path: /oauth/revoke
- description: Auth0 Login using a social provider's access token
  method: POST
  name: oauth-access-token
  path: /oauth/access_token
- description: Auth0 Given the user's credentials, this endpoint will authenticate the user with the provider and return a JSON object with the Access Token and an ID Token.
  method: POST
  name: oauth-ro
  path: /oauth/ro
- description: Auth0 [Deprecated] Return a user profile based on the user's JWT
  method: POST
  name: tokeninfo
  path: /tokeninfo
- description: Auth0 Obtain a delegation token (from a refresh_token)
  method: POST
  name: delegation
  path: /delegation
- description: Auth0 Unlink an account
  method: POST
  name: unlink
  path: /unlink
- description: Auth0 Obtain an impersonation URL
  method: POST
  name: impersonate
  path: /users/{user_id}/impersonate
personas: []
provider_name: Auth0
provider_slug: auth0
search_terms:
- auth0 authenticates a user using a verification code, verifies multi-factor authentication (mfa) using a one-time password (otp), out-of-band (oob) challenge, or a recovery code, or exchanges an authorization code for a token
- auth0 revoke refresh token
- dbconnections signup
- oidc register
- oauth revoke
- auth0 [deprecated] return a user profile based on the user's jwt
- passwordless start
- impersonate
- auth0 start passwordless flow
- auth0 this endpoint accepts an idp-initiated sign on samlresponse from a saml identity provider.
- auth0 authenticate a user with a social provider, database/ad/ldap (passive), saml/windows azure ad (passive), authorization code flow, authorization code grant (pkce) flow, or implicit flow
- saml logout
- auth0 use this endpoint to accept a saml request to initiate a login.
- login callback
- wsfed login
- auth0 login using a social provider's access token
- mfa associate
- tokeninfo
- saml
- api
- auth0 request a challenge for multi-factor authentication
- dbconnections change password
- auth0 obtain a delegation token (from a refresh_token)
- identity management
- oauth token
- auth0
- authentication
- auth0 logout a user
- auth0 returns a list of authenticators associated with your application.
- auth0 deletes an associated authenticator using its id.
- auth0 signup with user's credentials
- auth0 obtain an impersonation url
- mfa authenticators
- openid connect
- auth0 this endpoint returns the saml 2.0 metadata.
- auth0 unlink an account
- oauth device code
- samlp metadata
- auth0 this endpoint returns the ws-federation metadata.
- auth0 verify with verification code
- mfa authenticators delete
- auth0 returns a user's profile
- wsfed metadata
- auth0 get device code
- authorize
- oauth ro
- authorization
- auth0 this endpoint accepts a ws-federation request to initiate a login.
- auth0 given the user's credentials, this endpoint will authenticate the user with the provider and return a json object with the access token and an id token.
- logout
- userinfo
- auth0 associates or adds a new authenticator for multi-factor authentication (mfa).
- oauth access token
- okta
- delegation
- oidc logout
- samlp login
- mfa challenge
- with a name and the necessary callback url, you can dynamically register a client with auth0. no token is needed for this request.
- auth0 send a change password email
- oauth
- security
- passwordless verify
- unlink
slug: auth0-capability
source_filename: auth0-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Auth0 API\n  description: Auth0 exposes the following APIs for developers to consume in their applications.\n  tags:\n  - Auth0\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: auth0\n    baseUri: https://demo.us.auth0.com\n    description: Auth0 API HTTP API.\n    resources:\n    - name: authorize\n      path: /authorize\n      operations:\n      - name: authorize\n        method: GET\n        description: Auth0 Authenticate a user with a social provider, Database/AD/LDAP (Passive), SAML/Windows Azure AD (Passive),\n          Authorization Code Flow, Authorization Code Grant (PKCE) Flow, or Implicit Flow\n        inputParameters:\n        - name: audience\n          in: query\n          type: string\n          description: The unique identifier of the target API you want to access\n        - name: scope\n          in: query\n          type: string\n          description:\
  \ The scopes which you want to request authorization for. These must be separated by a space. You can\n            request any of the standard OpenID Connect (OIDC) scopes abo\n        - name: response_type\n          in: query\n          type: string\n          required: true\n          description: 'Indicates to Auth0 which OAuth 2.0 flow you want to perform. Use code for Authorization Code Grant\n            Flow, token for Implicit Flow, or id_token token for both an '\n        - name: client_id\n          in: query\n          type: string\n          required: true\n          description: Your application's ID.\n        - name: redirect_uri\n          in: query\n          type: string\n          description: The URL to which Auth0 will redirect the browser after authorization has been granted by the user.\n        - name: state\n          in: query\n          type: string\n          description: An opaque value the applications adds to the initial request that the authorization server\
  \ includes\n            when redirecting the back to the application. This value mus\n        - name: nonce\n          in: query\n          type: string\n          description: A string value which will be included in the ID Token response from Auth0, used to prevent token replay\n            attacks. It is required for response_type=id_token token\n        - name: code_challenge_method\n          in: query\n          type: string\n          description: Method used to generate the challenge. The PKCE spec defines two methods, S256 and plain, however,\n            Auth0 supports only S256 since the latter is discouraged.\n        - name: code_challenge\n          in: query\n          type: string\n          description: Generated challenge from the code_verifier.\n        - name: connection\n          in: query\n          type: string\n          description: The name of the connection configured to your application.\n        - name: prompt\n          in: query\n          type: string\n\
  \          description: To initiate a silent authentication request, use prompt=none.\n        - name: organization\n          in: query\n          type: string\n          description: 'ID of the organization to use when authenticating a user. When not provided, if your application is\n            configured to Display Organization Prompt, the user will be '\n        - name: invitation\n          in: query\n          type: string\n          description: Ticket ID of the organization invitation. When inviting a member to an Organization, your application\n            should handle invitation acceptance by forwarding the invi\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-logout\n      path: /v2/logout\n      operations:\n      - name: logout\n        method: GET\n        description: Auth0 Logout a user\n        inputParameters:\n        - name: returnTo\n          in: query\n          type:\
  \ string\n          description: URL to redirect the user after the logout.\n        - name: client_id\n          in: query\n          type: string\n          description: The client_id of your application.\n        - name: federated\n          in: query\n          type: string\n          description: Add this query string parameter to the logout URL, to log the user out of their identity provider,\n            as well.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oidc-logout\n      path: /oidc/logout\n      operations:\n      - name: oidc-logout\n        method: GET\n        description: Auth0 Logout a user\n        inputParameters:\n        - name: id_token_hint\n          in: query\n          type: string\n          description: Previously issued ID Token for the user. This is used to indicate which user to log out.\n        - name: logout_hint\n          in: query\n          type: string\n\
  \          description: Optional sid (session ID) value to indicate which user to log out. Should be provided when id_token_hint\n            is not available.\n        - name: post_logout_redirect_uri\n          in: query\n          type: string\n          description: URL to redirect the user after the logout.\n        - name: client_id\n          in: query\n          type: string\n          description: The client_id of your application.\n        - name: federated\n          in: query\n          type: string\n          description: Add this query string parameter to log the user out of their identity provider.\n        - name: state\n          in: query\n          type: string\n          description: An opaque value the applications adds to the initial request that the authorization server includes\n            when redirecting the back to the post_logout_redirect_uri.\n        - name: ui_locales\n          in: query\n          type: string\n          description: Space-delimited list\
  \ of locales used to constrain the language list for the request. The first locale\n            on the list must match the enabled locale in your tenant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: samlp-client-id-logout\n      path: /samlp/{CLIENT_ID}/logout\n      operations:\n      - name: saml-logout\n        method: POST\n        description: Auth0 Logout a user\n        inputParameters:\n        - name: CLIENT_ID\n          in: path\n          type: string\n          required: true\n          description: Client ID of your application configured with the SAML2 Web App addon.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: passwordless-start\n      path: /passwordless/start\n      operations:\n      - name: passwordless-start\n        method: POST\n        description: Auth0 Start Passwordless flow\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: passwordless-verify\n      path: /passwordless/verify\n      operations:\n      - name: passwordless-verify\n        method: POST\n        description: Auth0 Verify with verification code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-token\n      path: /oauth/token\n      operations:\n      - name: oauth-token\n        method: POST\n        description: Auth0 Authenticates a user using a verification code, verifies multi-factor authentication (MFA) using\n          a one-time password (OTP), out-of-band (OOB) challenge, or a recovery code, or exchanges an Authorization Code for\n          a Token\n        inputParameters:\n        - name: auth0-forwarded-for\n          in: header\n          type: string\n          description: End-user IP as a string\
  \ value. Set this if you want brute-force protection to work in server-side scenarios.\n            For more information on how and when to use this he\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbconnections-signup\n      path: /dbconnections/signup\n      operations:\n      - name: dbconnections-signup\n        method: POST\n        description: Auth0 Signup with user's credentials\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbconnections-change-password\n      path: /dbconnections/change_password\n      operations:\n      - name: dbconnections-change-password\n        method: POST\n        description: Auth0 Send a change password email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: userinfo\n      path:\
  \ /userinfo\n      operations:\n      - name: userinfo\n        method: GET\n        description: Auth0 Returns a user's profile\n        inputParameters:\n        - name: access_token\n          in: header\n          type: string\n          required: true\n          description: The Auth0 Access Token obtained during login.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mfa-challenge\n      path: /mfa/challenge\n      operations:\n      - name: mfa-challenge\n        method: POST\n        description: Auth0 Request a challenge for multi-factor authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mfa-associate\n      path: /mfa/associate\n      operations:\n      - name: mfa-associate\n        method: POST\n        description: Auth0 Associates or adds a new authenticator for multi-factor authentication\
  \ (MFA).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mfa-authenticators\n      path: /mfa/authenticators\n      operations:\n      - name: mfa-authenticators\n        method: GET\n        description: Auth0 Returns a list of authenticators associated with your application.\n        inputParameters:\n        - name: ACCESS_TOKEN\n          in: header\n          type: string\n          required: true\n          description: The Access Token obtained during login.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mfa-authenticators-authenticator-id\n      path: /mfa/authenticators/{AUTHENTICATOR_ID}\n      operations:\n      - name: mfa-authenticators-delete\n        method: DELETE\n        description: Auth0 Deletes an associated authenticator using its ID.\n        inputParameters:\n        - name: ACCESS_TOKEN\n\
  \          in: header\n          type: string\n          required: true\n          description: The Access Token obtained during login.\n        - name: AUTHENTICATOR_ID\n          in: path\n          type: string\n          required: true\n          description: The ID of the authenticator to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: samlp-client-id\n      path: /samlp/{client_id}\n      operations:\n      - name: samlp-login\n        method: GET\n        description: Auth0 Use this endpoint to accept a SAML request to initiate a login.\n        inputParameters:\n        - name: client_id\n          in: path\n          type: string\n          required: true\n          description: Client ID of your application.\n        - name: connection\n          in: query\n          type: string\n          description: Connection to use during login.\n        - name: organization\n          in:\
  \ query\n          type: string\n          description: Organization ID, if authenticating in the context of an organization.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: samlp-metadata-client-id\n      path: /samlp/metadata/{client_id}\n      operations:\n      - name: samlp-metadata\n        method: GET\n        description: Auth0 This endpoint returns the SAML 2.0 metadata.\n        inputParameters:\n        - name: client_id\n          in: path\n          type: string\n          required: true\n          description: The client_id of your application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: login-callback\n      path: /login/callback\n      operations:\n      - name: login-callback\n        method: POST\n        description: Auth0 This endpoint accepts an IdP-Initiated Sign On SAMLResponse\
  \ from a SAML Identity Provider.\n        inputParameters:\n        - name: connection\n          in: query\n          type: string\n          required: true\n          description: The name of an identity provider configured to your application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wsfed-client-id\n      path: /wsfed/{client_id}\n      operations:\n      - name: wsfed-login\n        method: GET\n        description: Auth0 This endpoint accepts a WS-Federation request to initiate a login.\n        inputParameters:\n        - name: client_id\n          in: path\n          type: string\n          required: true\n          description: The client-id of your application.\n        - name: wtrealm\n          in: query\n          type: string\n          description: Can be used in place of client-id.\n        - name: whr\n          in: query\n          type: string\n          description: The\
  \ name of the connection (used to skip the login page).\n        - name: wctx\n          in: query\n          type: string\n          description: Your application's state.\n        - name: wreply\n          in: query\n          type: string\n          description: The callback URL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: wsfed-federationmetadata-2007-06-federationmetad\n      path: /wsfed/FederationMetadata/2007-06/FederationMetadata.xml\n      operations:\n      - name: wsfed-metadata\n        method: GET\n        description: Auth0 This endpoint returns the WS-Federation metadata.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oidc-register\n      path: /oidc/register\n      operations:\n      - name: oidc-register\n        method: POST\n        description: With a name and the necessary callback\
  \ URL, you can dynamically register a client with Auth0. No token\n          is needed for this request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-device-code\n      path: /oauth/device/code\n      operations:\n      - name: oauth-device-code\n        method: POST\n        description: Auth0 Get Device Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-revoke\n      path: /oauth/revoke\n      operations:\n      - name: oauth-revoke\n        method: POST\n        description: Auth0 Revoke Refresh Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-access-token\n      path: /oauth/access_token\n      operations:\n      - name: oauth-access-token\n        method: POST\n        description:\
  \ Auth0 Login using a social provider's access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: oauth-ro\n      path: /oauth/ro\n      operations:\n      - name: oauth-ro\n        method: POST\n        description: Auth0 Given the user's credentials, this endpoint will authenticate the user with the provider and return\n          a JSON object with the Access Token and an ID Token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tokeninfo\n      path: /tokeninfo\n      operations:\n      - name: tokeninfo\n        method: POST\n        description: Auth0 [Deprecated] Return a user profile based on the user's JWT\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: delegation\n      path: /delegation\n      operations:\n\
  \      - name: delegation\n        method: POST\n        description: Auth0 Obtain a delegation token (from a refresh_token)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: unlink\n      path: /unlink\n      operations:\n      - name: unlink\n        method: POST\n        description: Auth0 Unlink an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user-id-impersonate\n      path: /users/{user_id}/impersonate\n      operations:\n      - name: impersonate\n        method: POST\n        description: Auth0 Obtain an impersonation URL\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the user to impersonate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: auth0-rest\n    description: REST adapter for Auth0 API.\n    resources:\n    - path: /authorize\n      name: authorize\n      operations:\n      - method: GET\n        name: authorize\n        description: Auth0 Authenticate a user with a social provider, Database/AD/LDAP (Passive), SAML/Windows Azure AD (Passive),\n          Authorization Code Flow, Authorization Code Grant (PKCE) Flow, or Implicit Flow\n        call: auth0.authorize\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v2/logout\n      name: logout\n      operations:\n      - method: GET\n        name: logout\n        description: Auth0 Logout a user\n        call: auth0.logout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oidc/logout\n      name: oidc-logout\n      operations:\n      - method: GET\n        name: oidc-logout\n        description:\
  \ Auth0 Logout a user\n        call: auth0.oidc-logout\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /samlp/{CLIENT_ID}/logout\n      name: saml-logout\n      operations:\n      - method: POST\n        name: saml-logout\n        description: Auth0 Logout a user\n        call: auth0.saml-logout\n        with:\n          CLIENT_ID: rest.CLIENT_ID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /passwordless/start\n      name: passwordless-start\n      operations:\n      - method: POST\n        name: passwordless-start\n        description: Auth0 Start Passwordless flow\n        call: auth0.passwordless-start\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /passwordless/verify\n      name: passwordless-verify\n      operations:\n      - method: POST\n        name: passwordless-verify\n        description: Auth0 Verify with verification code\n        call: auth0.passwordless-verify\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/token\n      name: oauth-token\n      operations:\n      - method: POST\n        name: oauth-token\n        description: Auth0 Authenticates a user using a verification code, verifies multi-factor authentication (MFA) using\n          a one-time password (OTP), out-of-band (OOB) challenge, or a recovery code, or exchanges an Authorization Code for\n          a Token\n        call: auth0.oauth-token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbconnections/signup\n      name: dbconnections-signup\n      operations:\n      - method: POST\n        name: dbconnections-signup\n        description: Auth0 Signup with user's credentials\n        call: auth0.dbconnections-signup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbconnections/change_password\n      name: dbconnections-change-password\n      operations:\n \
  \     - method: POST\n        name: dbconnections-change-password\n        description: Auth0 Send a change password email\n        call: auth0.dbconnections-change-password\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /userinfo\n      name: userinfo\n      operations:\n      - method: GET\n        name: userinfo\n        description: Auth0 Returns a user's profile\n        call: auth0.userinfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mfa/challenge\n      name: mfa-challenge\n      operations:\n      - method: POST\n        name: mfa-challenge\n        description: Auth0 Request a challenge for multi-factor authentication\n        call: auth0.mfa-challenge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mfa/associate\n      name: mfa-associate\n      operations:\n      - method: POST\n        name: mfa-associate\n        description: Auth0 Associates or adds\
  \ a new authenticator for multi-factor authentication (MFA).\n        call: auth0.mfa-associate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mfa/authenticators\n      name: mfa-authenticators\n      operations:\n      - method: GET\n        name: mfa-authenticators\n        description: Auth0 Returns a list of authenticators associated with your application.\n        call: auth0.mfa-authenticators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mfa/authenticators/{AUTHENTICATOR_ID}\n      name: mfa-authenticators-delete\n      operations:\n      - method: DELETE\n        name: mfa-authenticators-delete\n        description: Auth0 Deletes an associated authenticator using its ID.\n        call: auth0.mfa-authenticators-delete\n        with:\n          AUTHENTICATOR_ID: rest.AUTHENTICATOR_ID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /samlp/{client_id}\n      name:\
  \ samlp-login\n      operations:\n      - method: GET\n        name: samlp-login\n        description: Auth0 Use this endpoint to accept a SAML request to initiate a login.\n        call: auth0.samlp-login\n        with:\n          client_id: rest.client_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /samlp/metadata/{client_id}\n      name: samlp-metadata\n      operations:\n      - method: GET\n        name: samlp-metadata\n        description: Auth0 This endpoint returns the SAML 2.0 metadata.\n        call: auth0.samlp-metadata\n        with:\n          client_id: rest.client_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /login/callback\n      name: login-callback\n      operations:\n      - method: POST\n        name: login-callback\n        description: Auth0 This endpoint accepts an IdP-Initiated Sign On SAMLResponse from a SAML Identity Provider.\n        call: auth0.login-callback\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /wsfed/{client_id}\n      name: wsfed-login\n      operations:\n      - method: GET\n        name: wsfed-login\n        description: Auth0 This endpoint accepts a WS-Federation request to initiate a login.\n        call: auth0.wsfed-login\n        with:\n          client_id: rest.client_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /wsfed/FederationMetadata/2007-06/FederationMetadata.xml\n      name: wsfed-metadata\n      operations:\n      - method: GET\n        name: wsfed-metadata\n        description: Auth0 This endpoint returns the WS-Federation metadata.\n        call: auth0.wsfed-metadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oidc/register\n      name: oidc-register\n      operations:\n      - method: POST\n        name: oidc-register\n        description: With a name and the necessary callback URL, you can dynamically register\
  \ a client with Auth0. No token\n          is needed for this request.\n        call: auth0.oidc-register\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/device/code\n      name: oauth-device-code\n      operations:\n      - method: POST\n        name: oauth-device-code\n        description: Auth0 Get Device Code\n        call: auth0.oauth-device-code\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/revoke\n      name: oauth-revoke\n      operations:\n      - method: POST\n        name: oauth-revoke\n        description: Auth0 Revoke Refresh Token\n        call: auth0.oauth-revoke\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/access_token\n      name: oauth-access-token\n      operations:\n      - method: POST\n        name: oauth-access-token\n        description: Auth0 Login using a social provider's access token\n        call: auth0.oauth-access-token\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /oauth/ro\n      name: oauth-ro\n      operations:\n      - method: POST\n        name: oauth-ro\n        description: Auth0 Given the user's credentials, this endpoint will authenticate the user with the provider and return\n          a JSON object with the Access Token and an ID Token.\n        call: auth0.oauth-ro\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tokeninfo\n      name: tokeninfo\n      operations:\n      - method: POST\n        name: tokeninfo\n        description: Auth0 [Deprecated] Return a user profile based on the user's JWT\n        call: auth0.tokeninfo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /delegation\n      name: delegation\n      operations:\n      - method: POST\n        name: delegation\n        description: Auth0 Obtain a delegation token (from a refresh_token)\n        call: auth0.delegation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /unlink\n      name: unlink\n      operations:\n      - method: POST\n        name: unlink\n        description: Auth0 Unlink an account\n        call: auth0.unlink\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}/impersonate\n      name: impersonate\n      operations:\n      - method: POST\n        name: impersonate\n        description: Auth0 Obtain an impersonation URL\n        call: auth0.impersonate\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: auth0-mcp\n    transport: http\n    description: MCP adapter for Auth0 API for AI agent use.\n    tools:\n    - name: authorize\n      description: Auth0 Authenticate a user with a social provider, Database/AD/LDAP (Passive), SAML/Windows Azure AD (Passive),\n        Authorization\
  \ Code Flow, Authorization Code Grant (PKCE) Flow, or Implicit Flow\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: auth0.authorize\n      with:\n        audience: tools.audience\n        scope: tools.scope\n        response_type: tools.response_type\n        client_id: tools.client_id\n        redirect_uri: tools.redirect_uri\n        state: tools.state\n        nonce: tools.nonce\n        code_challenge_method: tools.code_challenge_method\n        code_challenge: tools.code_challenge\n        connection: tools.connection\n        prompt: tools.prompt\n        organization: tools.organization\n        invitation: tools.invitation\n      inputParameters:\n      - name: audience\n        type: string\n        description: The unique identifier of the target API you want to access\n      - name: scope\n        type: string\n        description: The scopes which you want to request authorization for. These must be separated by a space.\
  \ You can request\n          any of the standard OpenID Connect (OIDC) scopes abo\n      - name: response_type\n        type: string\n        description: 'Indicates to Auth0 which OAuth 2.0 flow you want to perform. Use code for Authorization Code Grant Flow,\n          token for Implicit Flow, or id_token token for both an '\n        required: true\n      - name: client_id\n        type: string\n        description: Your application's ID.\n        required: true\n      - name: redirect_uri\n        type: string\n        description: The URL to which Auth0 will redirect the browser after authorization has been granted by the user.\n      - name: state\n        type: string\n        description: An opaque value the applications adds to the initial request that the authorization server includes when\n          redirecting the back to the application. This value mus\n      - name: nonce\n        type: string\n        description: A string value which will be included in the ID Token response\
  \ from Auth0, used to prevent token replay\n          attacks. It is required for response_type=id_token token\n      - name: code_challenge_method\n        type: string\n        description: Method used to generate the challenge. The PKCE spec defines two methods, S256 and plain, however, Auth0\n          supports only S256 since the latter is discouraged.\n      - name: code_challenge\n        type: string\n        description: Generated challenge from the code_verifier.\n      - name: connection\n        type: string\n        description: The name of the connection configured to your application.\n      - name: prompt\n        type: string\n        description: To initiate a silent authentication request, use prompt=none.\n      - name: organization\n        type: string\n        description: 'ID of the organization to use when authenticating a user. When not provided, if your application is\n          configured to Display Organization Prompt, the user will be '\n      - name: invitation\n\
  \        type: string\n        description: Ticket ID of the organization invitation. When inviting a member to an Organization, your application\n          should handle invitation acceptance by forwarding the invi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: logout\n      description: Auth0 Logout a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: auth0.logout\n      with:\n        returnTo: tools.returnTo\n        client_id: tools.client_id\n        federated: tools.federated\n      inputParameters:\n      - name: returnTo\n        type: string\n        description: URL to redirect the user after the logout.\n      - name: client_id\n        type: string\n        description: The client_id of your application.\n      - name: federated\n        type: string\n        description: Add this query string parameter to the logout URL, to log the user out of their identity provider, as\n       \
  \   well.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: oidc-logout\n      description: Auth0 Logout a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: auth0.oidc-logout\n      with:\n        id_token_hint: tools.id_token_hint\n        logout_hint: tools.logout_hint\n        post_logout_redirect_uri: tools.post_logout_redirect_uri\n        client_id: tools.client_id\n        federated: tools.federated\n        state: tools.state\n        ui_locales: tools.ui_locales\n      inputParameters:\n      - name: id_token_hint\n        type: string\n        description: Previously issued ID Token for the user. This is used to indicate which user to log out.\n      - name: logout_hint\n        type: string\n        description: Optional sid (session ID) value to indicate which user to log out. Should be provided when id_token_hint\n          is not available.\n      - name: post_logout_redirect_uri\n\
  \        type: string\n        description: URL to redirect the user after the logout.\n      - name: client_id\n        type: string\n        description: The client_id of your application.\n      - name: federated\n        type: string\n        description: Add this query string parameter to log the user out of their identity provider.\n      - name: state\n        type: string\n        description: An opaque value the applications adds to the initial request that the authorization server includes when\n          redirecting the back to the post_logout_redirect_uri.\n      - name: ui_locales\n        type: string\n        description: Space-delimited list of locales use\n\n# --- truncated at 32 KB (41 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/auth0/refs/heads/main/capabilities/auth0-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/auth0/refs/heads/main/capabilities/auth0-capability.yaml
tags:
- Auth0
- API
tools:
- description: Auth0 Authenticate a user with a social provider, Database/AD/LDAP (Passive), SAML/Windows Azure AD (Passive), Authorization Code Flow, Authorization Code Grant (PKCE) Flow, or Implicit Flow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: authorize
- description: Auth0 Logout a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: logout
- description: Auth0 Logout a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: oidc-logout
- description: Auth0 Logout a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: saml-logout
- description: Auth0 Start Passwordless flow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: passwordless-start
- description: Auth0 Verify with verification code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: passwordless-verify
- description: Auth0 Authenticates a user using a verification code, verifies multi-factor authentication (MFA) using a one-time password (OTP), out-of-band (OOB) challenge, or a recovery code, or exchanges an Authorization Code for a Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth-token
- description: Auth0 Signup with user's credentials
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: dbconnections-signup
- description: Auth0 Send a change password email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: dbconnections-change-password
- description: Auth0 Returns a user's profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: userinfo
- description: Auth0 Request a challenge for multi-factor authentication
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mfa-challenge
- description: Auth0 Associates or adds a new authenticator for multi-factor authentication (MFA).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: mfa-associate
- description: Auth0 Returns a list of authenticators associated with your application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: mfa-authenticators
- description: Auth0 Deletes an associated authenticator using its ID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: mfa-authenticators-delete
- description: Auth0 Use this endpoint to accept a SAML request to initiate a login.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: samlp-login
- description: Auth0 This endpoint returns the SAML 2.0 metadata.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: samlp-metadata
- description: Auth0 This endpoint accepts an IdP-Initiated Sign On SAMLResponse from a SAML Identity Provider.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: login-callback
- description: Auth0 This endpoint accepts a WS-Federation request to initiate a login.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wsfed-login
- description: Auth0 This endpoint returns the WS-Federation metadata.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: wsfed-metadata
- description: With a name and the necessary callback URL, you can dynamically register a client with Auth0. No token is needed for this request.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oidc-register
- description: Auth0 Get Device Code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth-device-code
- description: Auth0 Revoke Refresh Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth-revoke
- description: Auth0 Login using a social provider's access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth-access-token
- description: Auth0 Given the user's credentials, this endpoint will authenticate the user with the provider and return a JSON object with the Access Token and an ID Token.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: oauth-ro
- description: Auth0 [Deprecated] Return a user profile based on the user's JWT
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: tokeninfo
- description: Auth0 Obtain a delegation token (from a refresh_token)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: delegation
- description: Auth0 Unlink an account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unlink
- description: Auth0 Obtain an impersonation URL
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: impersonate
---
