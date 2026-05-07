---
categories: []
consumed_apis: []
description: Allows customers to easily access the Okta API
layout: capability
name: Okta API
operations:
- description: Okta List Applications
  method: GET
  name: listapplications
  path: /api/v1/apps
- description: Okta Add Application
  method: POST
  name: createapplication
  path: /api/v1/apps
- description: Okta Get Application
  method: GET
  name: getapplication
  path: /api/v1/apps/{appId}
- description: Okta Update Application
  method: PUT
  name: updateapplication
  path: /api/v1/apps/{appId}
- description: Okta Delete Application
  method: DELETE
  name: deleteapplication
  path: /api/v1/apps/{appId}
- description: Okta Fetches the default Provisioning Connection for an application.
  method: GET
  name: getdefaultprovisioningconnectionforapplication
  path: /api/v1/apps/{appId}/connections/default
- description: Okta Sets the default Provisioning Connection for an application.
  method: POST
  name: setdefaultprovisioningconnectionforapplication
  path: /api/v1/apps/{appId}/connections/default
- description: Okta Activate default Provisioning Connection for application
  method: POST
  name: activatedefaultprovisioningconnectionforapplicat
  path: /api/v1/apps/{appId}/connections/default/lifecycle/activate
- description: Okta Deactivate default Provisioning Connection for application
  method: POST
  name: deactivatedefaultprovisioningconnectionforapplic
  path: /api/v1/apps/{appId}/connections/default/lifecycle/deactivate
- description: Okta List Certificate Signing Requests for Application
  method: GET
  name: listcsrsforapplication
  path: /api/v1/apps/{appId}/credentials/csrs
- description: Okta Generate Certificate Signing Request for Application
  method: POST
  name: generatecsrforapplication
  path: /api/v1/apps/{appId}/credentials/csrs
- description: GET /api/v1/apps/{appId}/credentials/csrs/{csrId}
  method: GET
  name: getcsrforapplication
  path: /api/v1/apps/{appId}/credentials/csrs/{csrId}
- description: DELETE /api/v1/apps/{appId}/credentials/csrs/{csrId}
  method: DELETE
  name: revokecsrfromapplication
  path: /api/v1/apps/{appId}/credentials/csrs/{csrId}
- description: POST /api/v1/apps/{appId}/credentials/csrs/{csrId}/lifecycle/publish
  method: POST
  name: post-api-v1-apps-appid-credentials-csrs-csrid-li
  path: /api/v1/apps/{appId}/credentials/csrs/{csrId}/lifecycle/publish
- description: Okta List Key Credentials for Application
  method: GET
  name: listapplicationkeys
  path: /api/v1/apps/{appId}/credentials/keys
- description: Generates a new X.509 certificate for an application key credential
  method: POST
  name: generateapplicationkey
  path: /api/v1/apps/{appId}/credentials/keys/generate
- description: Okta Get Key Credential for Application
  method: GET
  name: getapplicationkey
  path: /api/v1/apps/{appId}/credentials/keys/{keyId}
- description: Okta Clone Application Key Credential
  method: POST
  name: cloneapplicationkey
  path: /api/v1/apps/{appId}/credentials/keys/{keyId}/clone
- description: Okta List client secrets
  method: GET
  name: listclientsecretsforapplication
  path: /api/v1/apps/{appId}/credentials/secrets
- description: Okta Add new client secret
  method: POST
  name: createnewclientsecretforapplication
  path: /api/v1/apps/{appId}/credentials/secrets
- description: Okta Get client secret
  method: GET
  name: getclientsecretforapplication
  path: /api/v1/apps/{appId}/credentials/secrets/{secretId}
- description: Removes a secret from the client's collection of secrets.
  method: DELETE
  name: deleteclientsecretforapplication
  path: /api/v1/apps/{appId}/credentials/secrets/{secretId}
- description: Okta Activate a client secret
  method: POST
  name: activateclientsecretforapplication
  path: /api/v1/apps/{appId}/credentials/secrets/{secretId}/lifecycle/activate
- description: Okta Deactivate a client secret
  method: POST
  name: deactivateclientsecretforapplication
  path: /api/v1/apps/{appId}/credentials/secrets/{secretId}/lifecycle/deactivate
- description: Okta Fetches the Feature objects for an application.
  method: GET
  name: listfeaturesforapplication
  path: /api/v1/apps/{appId}/features
- description: Okta Fetches a Feature object for an application.
  method: GET
  name: getfeatureforapplication
  path: /api/v1/apps/{appId}/features/{name}
- description: Okta Updates a Feature object for an application.
  method: PUT
  name: updatefeatureforapplication
  path: /api/v1/apps/{appId}/features/{name}
- description: Lists all scope consent grants for the application
  method: GET
  name: listscopeconsentgrants
  path: /api/v1/apps/{appId}/grants
- description: Grants consent for the application to request an OAuth 2.0 Okta scope
  method: POST
  name: grantconsenttoscope
  path: /api/v1/apps/{appId}/grants
- description: Fetches a single scope consent grant for the application
  method: GET
  name: getscopeconsentgrant
  path: /api/v1/apps/{appId}/grants/{grantId}
- description: Revokes permission for the application to request the given scope
  method: DELETE
  name: revokescopeconsentgrant
  path: /api/v1/apps/{appId}/grants/{grantId}
- description: Okta List Groups Assigned to Application
  method: GET
  name: listapplicationgroupassignments
  path: /api/v1/apps/{appId}/groups
- description: Okta Get Assigned Group for Application
  method: GET
  name: getapplicationgroupassignment
  path: /api/v1/apps/{appId}/groups/{groupId}
- description: Okta Assign Group to Application
  method: PUT
  name: createapplicationgroupassignment
  path: /api/v1/apps/{appId}/groups/{groupId}
- description: Okta Remove Group from Application
  method: DELETE
  name: deleteapplicationgroupassignment
  path: /api/v1/apps/{appId}/groups/{groupId}
- description: Okta Activate Application
  method: POST
  name: activateapplication
  path: /api/v1/apps/{appId}/lifecycle/activate
- description: Okta Deactivate Application
  method: POST
  name: deactivateapplication
  path: /api/v1/apps/{appId}/lifecycle/deactivate
- description: Okta The file must be in PNG, JPG, or GIF format, and less than 1 MB in size. For best results use landscape orientation, a transparent background, and a minimum size of 420px by 120px to prevent upscaling.
  method: POST
  name: uploadapplicationlogo
  path: /api/v1/apps/{appId}/logo
- description: Okta Update application policy
  method: PUT
  name: updateapplicationpolicy
  path: /api/v1/apps/{appId}/policies/{policyId}
- description: Previews SAML metadata based on a specific key credential for an application
  method: GET
  name: previewsamlappmetadata
  path: /api/v1/apps/{appId}/sso/saml/metadata
- description: Lists all tokens for the application
  method: GET
  name: listoauth2tokensforapplication
  path: /api/v1/apps/{appId}/tokens
- description: Revokes all tokens for the specified application
  method: DELETE
  name: revokeoauth2tokensforapplication
  path: /api/v1/apps/{appId}/tokens
- description: Gets a token for the specified application
  method: GET
  name: getoauth2tokenforapplication
  path: /api/v1/apps/{appId}/tokens/{tokenId}
- description: Revokes the specified token for the specified application
  method: DELETE
  name: revokeoauth2tokenforapplication
  path: /api/v1/apps/{appId}/tokens/{tokenId}
- description: Okta List Users Assigned to Application
  method: GET
  name: listapplicationusers
  path: /api/v1/apps/{appId}/users
- description: Okta Assign User to Application for SSO & Provisioning
  method: POST
  name: assignusertoapplication
  path: /api/v1/apps/{appId}/users
- description: Okta Get Assigned User for Application
  method: GET
  name: getapplicationuser
  path: /api/v1/apps/{appId}/users/{userId}
- description: Okta Update Application Profile for Assigned User
  method: POST
  name: updateapplicationuser
  path: /api/v1/apps/{appId}/users/{userId}
- description: Okta Remove User from Application
  method: DELETE
  name: deleteapplicationuser
  path: /api/v1/apps/{appId}/users/{userId}
- description: Okta Lists all available Authenticators
  method: GET
  name: listauthenticators
  path: /api/v1/authenticators
- description: Okta Create an Authenticator
  method: POST
  name: createauthenticator
  path: /api/v1/authenticators
- description: Success
  method: GET
  name: getauthenticator
  path: /api/v1/authenticators/{authenticatorId}
- description: Okta Update Authenticator
  method: PUT
  name: updateauthenticator
  path: /api/v1/authenticators/{authenticatorId}
- description: Success
  method: POST
  name: activateauthenticator
  path: /api/v1/authenticators/{authenticatorId}/lifecycle/activate
- description: Success
  method: POST
  name: deactivateauthenticator
  path: /api/v1/authenticators/{authenticatorId}/lifecycle/deactivate
- description: Success
  method: GET
  name: listauthorizationservers
  path: /api/v1/authorizationServers
- description: Success
  method: POST
  name: createauthorizationserver
  path: /api/v1/authorizationServers
- description: Success
  method: GET
  name: getauthorizationserver
  path: /api/v1/authorizationServers/{authServerId}
- description: Success
  method: PUT
  name: updateauthorizationserver
  path: /api/v1/authorizationServers/{authServerId}
- description: Success
  method: DELETE
  name: deleteauthorizationserver
  path: /api/v1/authorizationServers/{authServerId}
personas: []
provider_name: Okta
provider_slug: okta
search_terms:
- delete /api/v1/apps/{appid}/credentials/csrs/{csrid}
- revokes all tokens for the specified application
- gets a token for the specified application
- api
- okta clone application key credential
- post api v1 apps appid credentials csrs csrid li
- listclientsecretsforapplication
- deactivatedefaultprovisioningconnectionforapplic
- getfeatureforapplication
- listapplicationkeys
- okta fetches a feature object for an application.
- okta assign user to application for sso & provisioning
- getapplicationkey
- fetches a single scope consent grant for the application
- authorization
- previews saml metadata based on a specific key credential for an application
- okta update application profile for assigned user
- listapplicationusers
- previewsamlappmetadata
- okta
- createauthorizationserver
- okta update authenticator
- okta updates a feature object for an application.
- okta get key credential for application
- deleteapplicationuser
- activateclientsecretforapplication
- okta get assigned user for application
- revokeoauth2tokensforapplication
- deleteapplicationgroupassignment
- getclientsecretforapplication
- listscopeconsentgrants
- generates a new x.509 certificate for an application key credential
- createnewclientsecretforapplication
- okta fetches the feature objects for an application.
- activatedefaultprovisioningconnectionforapplicat
- authentication
- revokes the specified token for the specified application
- okta list applications
- listfeaturesforapplication
- grantconsenttoscope
- revokescopeconsentgrant
- okta sets the default provisioning connection for an application.
- okta update application
- revokecsrfromapplication
- okta list client secrets
- okta create an authenticator
- getapplication
- createauthenticator
- grants consent for the application to request an oauth 2.0 okta scope
- lists all scope consent grants for the application
- okta lists all available authenticators
- okta remove user from application
- okta deactivate a client secret
- listauthorizationservers
- okta assign group to application
- lists all tokens for the application
- updateapplicationuser
- removes a secret from the client's collection of secrets.
- updatefeatureforapplication
- listapplicationgroupassignments
- single sign-on
- okta update application policy
- revokeoauth2tokenforapplication
- activateauthenticator
- updateauthenticator
- platform
- okta deactivate application
- assignusertoapplication
- okta list key credentials for application
- okta remove group from application
- deleteapplication
- getapplicationgroupassignment
- getauthenticator
- identity
- listcsrsforapplication
- okta generate certificate signing request for application
- generateapplicationkey
- revokes permission for the application to request the given scope
- okta deactivate default provisioning connection for application
- updateauthorizationserver
- listoauth2tokensforapplication
- okta add application
- okta list certificate signing requests for application
- get /api/v1/apps/{appid}/credentials/csrs/{csrid}
- createapplicationgroupassignment
- listauthenticators
- post /api/v1/apps/{appid}/credentials/csrs/{csrid}/lifecycle/publish
- getoauth2tokenforapplication
- uploadapplicationlogo
- getscopeconsentgrant
- deleteclientsecretforapplication
- getauthorizationserver
- deactivateauthenticator
- okta delete application
- generatecsrforapplication
- deactivateclientsecretforapplication
- okta add new client secret
- updateapplicationpolicy
- success
- getdefaultprovisioningconnectionforapplication
- deleteauthorizationserver
- okta fetches the default provisioning connection for an application.
- setdefaultprovisioningconnectionforapplication
- okta get client secret
- createapplication
- okta activate application
- getcsrforapplication
- activateapplication
- cloneapplicationkey
- deactivateapplication
- okta activate a client secret
- getapplicationuser
- okta list users assigned to application
- okta the file must be in png, jpg, or gif format, and less than 1 mb in size. for best results use landscape orientation, a transparent background, and a minimum size of 420px by 120px to prevent upscaling.
- okta activate default provisioning connection for application
- okta get application
- listapplications
- okta get assigned group for application
- updateapplication
- okta list groups assigned to application
slug: okta-capability
source_filename: okta-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Okta API\n  description: Allows customers to easily access the Okta API\n  tags:\n  - Okta\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: okta\n    baseUri: https://your-subdomain.okta.com\n    description: Okta API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{OKTA_TOKEN}}'\n    resources:\n    - name: api-v1-apps\n      path: /api/v1/apps\n      operations:\n      - name: listapplications\n        method: GET\n        description: Okta List Applications\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n          description: Specifies the pagination cursor for the next page of apps\n        - name: limit\n          in: query\n          type: integer\n          description: Specifies the number\
  \ of results for a page\n        - name: filter\n          in: query\n          type: string\n          description: Filters apps by status, user.id, group.id or credentials.signing.kid expression\n        - name: expand\n          in: query\n          type: string\n          description: Traverses users link relationship and optionally embeds Application User resource\n        - name: includeNonDeleted\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplication\n        method: POST\n        description: Okta Add Application\n        inputParameters:\n        - name: activate\n          in: query\n          type: boolean\n          description: Executes activation lifecycle operation when creating the app\n        - name: OktaAccessGateway-Agent\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid\n      path: /api/v1/apps/{appId}\n      operations:\n      - name: getapplication\n        method: GET\n        description: Okta Get Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplication\n        method: PUT\n        description: Okta Update Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplication\n        method: DELETE\n        description: Okta Delete Application\n\
  \        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-connections-default\n      path: /api/v1/apps/{appId}/connections/default\n      operations:\n      - name: getdefaultprovisioningconnectionforapplication\n        method: GET\n        description: Okta Fetches the default Provisioning Connection for an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setdefaultprovisioningconnectionforapplication\n        method: POST\n        description: Okta Sets the default Provisioning Connection for an application.\n        inputParameters:\n        - name:\
  \ appId\n          in: path\n          type: string\n          required: true\n        - name: activate\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-connections-default-lifecycle-\n      path: /api/v1/apps/{appId}/connections/default/lifecycle/activate\n      operations:\n      - name: activatedefaultprovisioningconnectionforapplicat\n        method: POST\n        description: Okta Activate default Provisioning Connection for application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-connections-default-lifecycle-\n      path: /api/v1/apps/{appId}/connections/default/lifecycle/deactivate\n      operations:\n\
  \      - name: deactivatedefaultprovisioningconnectionforapplic\n        method: POST\n        description: Okta Deactivate default Provisioning Connection for application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-csrs\n      path: /api/v1/apps/{appId}/credentials/csrs\n      operations:\n      - name: listcsrsforapplication\n        method: GET\n        description: Okta List Certificate Signing Requests for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generatecsrforapplication\n        method: POST\n        description:\
  \ Okta Generate Certificate Signing Request for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-csrs-csrid\n      path: /api/v1/apps/{appId}/credentials/csrs/{csrId}\n      operations:\n      - name: getcsrforapplication\n        method: GET\n        description: GET /api/v1/apps/{appId}/credentials/csrs/{csrId}\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: csrId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokecsrfromapplication\n        method: DELETE\n        description: DELETE /api/v1/apps/{appId}/credentials/csrs/{csrId}\n\
  \        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: csrId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-csrs-csrid-lifecyc\n      path: /api/v1/apps/{appId}/credentials/csrs/{csrId}/lifecycle/publish\n      operations:\n      - name: post-api-v1-apps-appid-credentials-csrs-csrid-li\n        method: POST\n        description: POST /api/v1/apps/{appId}/credentials/csrs/{csrId}/lifecycle/publish\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: csrId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: api-v1-apps-appid-credentials-keys\n      path: /api/v1/apps/{appId}/credentials/keys\n      operations:\n      - name: listapplicationkeys\n        method: GET\n        description: Okta List Key Credentials for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-keys-generate\n      path: /api/v1/apps/{appId}/credentials/keys/generate\n      operations:\n      - name: generateapplicationkey\n        method: POST\n        description: Generates a new X.509 certificate for an application key credential\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: validityYears\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-keys-keyid\n      path: /api/v1/apps/{appId}/credentials/keys/{keyId}\n      operations:\n      - name: getapplicationkey\n        method: GET\n        description: Okta Get Key Credential for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: keyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-keys-keyid-clone\n      path: /api/v1/apps/{appId}/credentials/keys/{keyId}/clone\n      operations:\n      - name: cloneapplicationkey\n        method: POST\n        description: Okta Clone Application Key Credential\n        inputParameters:\n        - name: appId\n\
  \          in: path\n          type: string\n          required: true\n        - name: keyId\n          in: path\n          type: string\n          required: true\n        - name: targetAid\n          in: query\n          type: string\n          required: true\n          description: Unique key of the target Application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-secrets\n      path: /api/v1/apps/{appId}/credentials/secrets\n      operations:\n      - name: listclientsecretsforapplication\n        method: GET\n        description: Okta List client secrets\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnewclientsecretforapplication\n        method:\
  \ POST\n        description: Okta Add new client secret\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-secrets-secretid\n      path: /api/v1/apps/{appId}/credentials/secrets/{secretId}\n      operations:\n      - name: getclientsecretforapplication\n        method: GET\n        description: Okta Get client secret\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteclientsecretforapplication\n        method: DELETE\n        description: Removes\
  \ a secret from the client's collection of secrets.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-credentials-secrets-secretid-l\n      path: /api/v1/apps/{appId}/credentials/secrets/{secretId}/lifecycle/activate\n      operations:\n      - name: activateclientsecretforapplication\n        method: POST\n        description: Okta Activate a client secret\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-v1-apps-appid-credentials-secrets-secretid-l\n      path: /api/v1/apps/{appId}/credentials/secrets/{secretId}/lifecycle/deactivate\n      operations:\n      - name: deactivateclientsecretforapplication\n        method: POST\n        description: Okta Deactivate a client secret\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: secretId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-features\n      path: /api/v1/apps/{appId}/features\n      operations:\n      - name: listfeaturesforapplication\n        method: GET\n        description: Okta Fetches the Feature objects for an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n       \
  \   required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-features-name\n      path: /api/v1/apps/{appId}/features/{name}\n      operations:\n      - name: getfeatureforapplication\n        method: GET\n        description: Okta Fetches a Feature object for an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefeatureforapplication\n        method: PUT\n        description: Okta Updates a Feature object for an application.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name:\
  \ name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-grants\n      path: /api/v1/apps/{appId}/grants\n      operations:\n      - name: listscopeconsentgrants\n        method: GET\n        description: Lists all scope consent grants for the application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: grantconsenttoscope\n        method: POST\n        description: Grants consent for the application to request an OAuth 2.0 Okta scope\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n       \
  \   required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-grants-grantid\n      path: /api/v1/apps/{appId}/grants/{grantId}\n      operations:\n      - name: getscopeconsentgrant\n        method: GET\n        description: Fetches a single scope consent grant for the application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: grantId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokescopeconsentgrant\n        method: DELETE\n        description: Revokes permission for the application to request the given scope\n        inputParameters:\n        - name:\
  \ appId\n          in: path\n          type: string\n          required: true\n        - name: grantId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-groups\n      path: /api/v1/apps/{appId}/groups\n      operations:\n      - name: listapplicationgroupassignments\n        method: GET\n        description: Okta List Groups Assigned to Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: q\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n          description: Specifies the pagination cursor for the next page of assignments\n        - name: limit\n          in: query\n          type: integer\n          description: Specifies the number of results for a\
  \ page\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-groups-groupid\n      path: /api/v1/apps/{appId}/groups/{groupId}\n      operations:\n      - name: getapplicationgroupassignment\n        method: GET\n        description: Okta Get Assigned Group for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapplicationgroupassignment\n        method: PUT\n        description: Okta Assign Group to Application\n        inputParameters:\n\
  \        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplicationgroupassignment\n        method: DELETE\n        description: Okta Remove Group from Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-lifecycle-activate\n      path: /api/v1/apps/{appId}/lifecycle/activate\n      operations:\n      - name: activateapplication\n        method: POST\n        description: Okta Activate\
  \ Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-lifecycle-deactivate\n      path: /api/v1/apps/{appId}/lifecycle/deactivate\n      operations:\n      - name: deactivateapplication\n        method: POST\n        description: Okta Deactivate Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-logo\n      path: /api/v1/apps/{appId}/logo\n      operations:\n      - name: uploadapplicationlogo\n        method: POST\n        description: Okta The file must be in PNG, JPG, or GIF format, and less than 1 MB in size. For best\
  \ results use landscape\n          orientation, a transparent background, and a minimum size of 420px by 120px to prevent upscaling.\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-policies-policyid\n      path: /api/v1/apps/{appId}/policies/{policyId}\n      operations:\n      - name: updateapplicationpolicy\n        method: PUT\n        description: Okta Update application policy\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: policyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-sso-saml-metadata\n\
  \      path: /api/v1/apps/{appId}/sso/saml/metadata\n      operations:\n      - name: previewsamlappmetadata\n        method: GET\n        description: Previews SAML metadata based on a specific key credential for an application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: kid\n          in: query\n          type: string\n          required: true\n          description: unique key identifier of an Application Key Credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-tokens\n      path: /api/v1/apps/{appId}/tokens\n      operations:\n      - name: listoauth2tokensforapplication\n        method: GET\n        description: Lists all tokens for the application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        -\
  \ name: expand\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokeoauth2tokensforapplication\n        method: DELETE\n        description: Revokes all tokens for the specified application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-tokens-tokenid\n      path: /api/v1/apps/{appId}/tokens/{tokenId}\n      operations:\n      - name: getoauth2tokenforapplication\n        method: GET\n        description: Gets a token for the specified application\n        inputParameters:\n        - name:\
  \ appId\n          in: path\n          type: string\n          required: true\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: revokeoauth2tokenforapplication\n        method: DELETE\n        description: Revokes the specified token for the specified application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-users\n      path: /api/v1/apps/{appId}/users\n      operations:\n      - name: listapplicationusers\n     \
  \   method: GET\n        description: Okta List Users Assigned to Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: q\n          in: query\n          type: string\n        - name: query_scope\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n          description: specifies the pagination cursor for the next page of assignments\n        - name: limit\n          in: query\n          type: integer\n          description: specifies the number of results for a page\n        - name: filter\n          in: query\n          type: string\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: assignusertoapplication\n        method: POST\n        description: Okta Assign User to Application\
  \ for SSO & Provisioning\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-apps-appid-users-userid\n      path: /api/v1/apps/{appId}/users/{userId}\n      operations:\n      - name: getapplicationuser\n        method: GET\n        description: Okta Get Assigned User for Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: expand\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapplicationuser\n        method: POST\n        description: Okta Update\
  \ Application Profile for Assigned User\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapplicationuser\n        method: DELETE\n        description: Okta Remove User from Application\n        inputParameters:\n        - name: appId\n          in: path\n          type: string\n          required: true\n        - name: userId\n          in: path\n          type: string\n          required: true\n        - name: sendEmail\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authenticators\n      path: /api/v1/authenticators\n      operations:\n\
  \      - name: listauthenticators\n        method: GET\n        description: Okta Lists all available Authenticators\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createauthenticator\n        method: POST\n        description: Okta Create an Authenticator\n        inputParameters:\n        - name: activate\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authenticators-authenticatorid\n      path: /api/v1/authenticators/{authenticatorId}\n      operations:\n      - name: getauthenticator\n        method: GET\n        description: Success\n        inputParameters:\n        - name: authenticatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n      - name: updateauthenticator\n        method: PUT\n        description: Okta Update Authenticator\n        inputParameters:\n        - name: authenticatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authenticators-authenticatorid-lifecycle-\n      path: /api/v1/authenticators/{authenticatorId}/lifecycle/activate\n      operations:\n      - name: activateauthenticator\n        method: POST\n        description: Success\n        inputParameters:\n        - name: authenticatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authenticators-authenticatorid-lifecycle-\n      path: /api/v1/authenticators/{authenticatorId}/lifecycle/deactivate\n\
  \      operations:\n      - name: deactivateauthenticator\n        method: POST\n        description: Success\n        inputParameters:\n        - name: authenticatorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authorizationservers\n      path: /api/v1/authorizationServers\n      operations:\n      - name: listauthorizationservers\n        method: GET\n        description: Success\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createauthorizationserver\n        method: POST\n        description: Success\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-authorizationservers-authserverid\n      path: /api/v1/authorizationServers/{authServerId}\n      operations:\n      - name: getauthorizationserver\n        method: GET\n        description: Success\n        inputParameters:\n        - name: authServerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateauthorizationserver\n        method: PUT\n        description: Success\n        inputParameters:\n        - name: authServerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteauthorizationserver\n        method:\
  \ DELETE\n        description: Success\n        inputParameters:\n        - name: authServerId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: okta-rest\n    description: REST adapter for Okta API.\n    resources:\n    - path: /api/v1/apps\n      name: listapplications\n      operations:\n      - method: GET\n        name: listapplications\n        description: Okta List Applications\n        call: okta.listapplications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/apps\n      name: createapplication\n      operations:\n      - method: POST\n        name: createapplication\n        description: Okta Add Application\n        call: okta.createapplication\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /api/v1/apps/{appId}\n      name: getapplication\n      operations:\n      - method: GET\n        name: getapplication\n        description: Okta Get Application\n        call: okta.getapplication\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/apps/{appId}\n      name: updateapplication\n      operations:\n      - method: PUT\n        name: updateapplication\n        description: Okta Update Application\n        call: okta.updateapplication\n        with:\n          appId: rest.appId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/apps/{appId}\n      name: deleteapplication\n      operations:\n      - method: DELETE\n        name: deleteapplication\n   \n\n# --- truncated at 32 KB (86 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/okta/refs/heads/main/capabilities/okta-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/okta/refs/heads/main/capabilities/okta-capability.yaml
tags:
- Okta
- API
tools:
- description: Okta List Applications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplications
- description: Okta Add Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapplication
- description: Okta Get Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplication
- description: Okta Update Application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapplication
- description: Okta Delete Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplication
- description: Okta Fetches the default Provisioning Connection for an application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdefaultprovisioningconnectionforapplication
- description: Okta Sets the default Provisioning Connection for an application.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setdefaultprovisioningconnectionforapplication
- description: Okta Activate default Provisioning Connection for application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activatedefaultprovisioningconnectionforapplicat
- description: Okta Deactivate default Provisioning Connection for application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivatedefaultprovisioningconnectionforapplic
- description: Okta List Certificate Signing Requests for Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcsrsforapplication
- description: Okta Generate Certificate Signing Request for Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generatecsrforapplication
- description: GET /api/v1/apps/{appId}/credentials/csrs/{csrId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcsrforapplication
- description: DELETE /api/v1/apps/{appId}/credentials/csrs/{csrId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokecsrfromapplication
- description: POST /api/v1/apps/{appId}/credentials/csrs/{csrId}/lifecycle/publish
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-v1-apps-appid-credentials-csrs-csrid-li
- description: Okta List Key Credentials for Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationkeys
- description: Generates a new X.509 certificate for an application key credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateapplicationkey
- description: Okta Get Key Credential for Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationkey
- description: Okta Clone Application Key Credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cloneapplicationkey
- description: Okta List client secrets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclientsecretsforapplication
- description: Okta Add new client secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnewclientsecretforapplication
- description: Okta Get client secret
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclientsecretforapplication
- description: Removes a secret from the client's collection of secrets.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclientsecretforapplication
- description: Okta Activate a client secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activateclientsecretforapplication
- description: Okta Deactivate a client secret
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateclientsecretforapplication
- description: Okta Fetches the Feature objects for an application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfeaturesforapplication
- description: Okta Fetches a Feature object for an application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfeatureforapplication
- description: Okta Updates a Feature object for an application.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefeatureforapplication
- description: Lists all scope consent grants for the application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscopeconsentgrants
- description: Grants consent for the application to request an OAuth 2.0 Okta scope
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: grantconsenttoscope
- description: Fetches a single scope consent grant for the application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscopeconsentgrant
- description: Revokes permission for the application to request the given scope
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokescopeconsentgrant
- description: Okta List Groups Assigned to Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationgroupassignments
- description: Okta Get Assigned Group for Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationgroupassignment
- description: Okta Assign Group to Application
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createapplicationgroupassignment
- description: Okta Remove Group from Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationgroupassignment
- description: Okta Activate Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activateapplication
- description: Okta Deactivate Application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateapplication
- description: Okta The file must be in PNG, JPG, or GIF format, and less than 1 MB in size. For best results use landscape orientation, a transparent background, and a minimum size of 420px by 120px to prevent upscaling.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadapplicationlogo
- description: Okta Update application policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapplicationpolicy
- description: Previews SAML metadata based on a specific key credential for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: previewsamlappmetadata
- description: Lists all tokens for the application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoauth2tokensforapplication
- description: Revokes all tokens for the specified application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeoauth2tokensforapplication
- description: Gets a token for the specified application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoauth2tokenforapplication
- description: Revokes the specified token for the specified application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: revokeoauth2tokenforapplication
- description: Okta List Users Assigned to Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapplicationusers
- description: Okta Assign User to Application for SSO & Provisioning
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assignusertoapplication
- description: Okta Get Assigned User for Application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationuser
- description: Okta Update Application Profile for Assigned User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapplicationuser
- description: Okta Remove User from Application
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapplicationuser
- description: Okta Lists all available Authenticators
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthenticators
- description: Okta Create an Authenticator
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthenticator
- description: Success
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthenticator
- description: Okta Update Authenticator
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateauthenticator
- description: Success
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activateauthenticator
- description: Success
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateauthenticator
- description: Success
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listauthorizationservers
- description: Success
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthorizationserver
- description: Success
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthorizationserver
- description: Success
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateauthorizationserver
- description: Success
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthorizationserver
---
