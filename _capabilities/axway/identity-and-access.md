---
categories: []
consumed_apis: []
description: Manage users, teams, roles, sessions, and authentication across the Axway Amplify platform.
layout: capability
name: Axway Identity and Access Management
operations:
- description: Axway Validates a User Password
  method: POST
  name: auth-validatePassword
  path: /v1/auth
- description: Axway Accept Terms & Conditions
  method: PUT
  name: auth-acceptTerms
  path: /v1/auth
- description: Axway Switch Signed-in Organization
  method: POST
  name: auth-sessionSwitchOrg
  path: /v1/auth
- description: Axway Sign Up
  method: POST
  name: auth-signup
  path: /v1/auth
- description: Axway Get Effective Password Policy
  method: GET
  name: auth-findPasswordPolicy
  path: /v1/auth
- description: Axway Onboarding Capture
  method: PUT
  name: auth-onboarding
  path: /v1/auth
- description: Axway Verify an Authorization Code
  method: POST
  name: auth-mfaVerify
  path: /v1/auth
- description: Axway Send an Authorization Code
  method: POST
  name: auth-mfaSend
  path: /v1/auth
- description: Axway Sign-out
  method: GET
  name: auth-logout
  path: /v1/auth
- description: Axway Sign-in
  method: POST
  name: auth-login
  path: /v1/auth
- description: Axway Unimpersonate User
  method: DELETE
  name: auth-unimpersonate
  path: /v1/auth
- description: Axway Send Forgot Password Link
  method: POST
  name: auth-forgot
  path: /v1/auth
- description: Axway Retrieves the Current Session
  method: GET
  name: auth-sessionFind
  path: /v1/auth
- description: Axway Resends Device Authorization
  method: POST
  name: auth-deviceauthResend
  path: /v1/auth
- description: Axway Validates a New Sessions Device Authorization
  method: POST
  name: auth-deviceauthValidate
  path: /v1/auth
- description: Axway Checks if the User is Signed in
  method: GET
  name: auth-sessionCheck
  path: /v1/auth
- description: Axway Confirm Authenticator App
  method: POST
  name: auth-deviceauthConfirm
  path: /v1/auth
- description: Axway Initiate Authenticator App Setup
  method: GET
  name: auth-deviceauthCreate
  path: /v1/auth
- description: Axway Remove Authenticator App
  method: DELETE
  name: auth-deviceauthRemoveApp
  path: /v1/auth
- description: Axway Activate a Signup User
  method: POST
  name: auth-activationSignup
  path: /v1/auth
- description: Axway Resend Activation Link
  method: POST
  name: auth-activationResend
  path: /v1/auth
- description: Axway Reset User Password
  method: POST
  name: auth-activationForgot
  path: /v1/auth
- description: Axway Activate a User
  method: POST
  name: auth-activationConfirm
  path: /v1/auth
- description: Axway Unlock Account
  method: PUT
  name: auth-activationUnlock
  path: /v1/auth
- description: Axway Revoke OAuth Service
  method: DELETE
  name: auth-revokeOauth
  path: /v1/auth
- description: Axway Retrieve Authorized Devices
  method: GET
  name: auth-deviceauthFind
  path: /v1/auth
- description: Axway Remove Authorized Device
  method: DELETE
  name: auth-deviceauthRemove
  path: /v1/auth
- description: Axway Find Activation
  method: GET
  name: auth-activationFind
  path: /v1/auth
- description: Axway Update a Single User Preference
  method: PUT
  name: user-updatePref
  path: /v1/user
- description: Axway Get Organizations
  method: GET
  name: user-findOrgs
  path: /v1/user
- description: Axway Set Credentials for Tooling
  method: PUT
  name: user-updateCredentials
  path: /v1/user
- description: Axway Update User Profile
  method: PUT
  name: user-update
  path: /v1/user
- description: Axway Find Missing Domain Users
  method: GET
  name: user-findDomain
  path: /v1/user
- description: Axway Find a Mapped Attribute for a User
  method: GET
  name: user-findAttribute
  path: /v1/user
- description: Axway Get a User
  method: GET
  name: user-findOne
  path: /v1/user
- description: Axway Remove User
  method: DELETE
  name: user-remove
  path: /v1/user
- description: Axway Create a Team
  method: POST
  name: team-create
  path: /v1/team
- description: Axway Get Accessible Teams for the Query
  method: GET
  name: team-find
  path: /v1/team
- description: Axway Add Member
  method: POST
  name: team-userAdd
  path: /v1/team
- description: Axway Remove Member
  method: DELETE
  name: team-userRemove
  path: /v1/team
- description: Axway Sets the Team Member Role
  method: PUT
  name: team-userUpdateRole
  path: /v1/team
- description: Axway Get Team Members
  method: GET
  name: team-userFind
  path: /v1/team
- description: Axway Find Team
  method: GET
  name: team-findOne
  path: /v1/team
- description: Axway Remove Team
  method: DELETE
  name: team-remove
  path: /v1/team
- description: Axway Update Team
  method: PUT
  name: team-update
  path: /v1/team
- description: Axway Get Roles Matching Query
  method: GET
  name: role-find
  path: /v1/role
- description: Axway Get Role
  method: GET
  name: role-findOne
  path: /v1/role
- description: Axway Find Sessions
  method: POST
  name: session-query
  path: /v1/session
- description: Axway Get Session
  method: GET
  name: session-find
  path: /v1/session
- description: Axway Delete Session
  method: DELETE
  name: session-remove
  path: /v1/session
personas: []
provider_name: Axway
provider_slug: axway
search_terms:
- auth acceptTerms
- axway update user profile
- axway delete session
- axway update a single user preference
- integration
- axway initiate authenticator app setup
- axway activate a user
- user findOne
- user updateCredentials
- axway retrieves the current session
- axway remove authorized device
- auth deviceauthConfirm
- auth sessionCheck
- axway checks if the user is signed in
- axway confirm authenticator app
- team userRemove
- axway update team
- security
- user operations
- team remove
- axway sets the team member role
- axway sign-in
- auth logout
- axway get organizations
- axway remove team
- auth activationResend
- session remove
- auth mfaSend
- api management
- user updatePref
- auth forgot
- axway remove user
- axway unimpersonate user
- auth findPasswordPolicy
- axway get effective password policy
- auth login
- axway remove authenticator app
- auth activationConfirm
- auth operations
- axway
- identity
- team userFind
- team operations
- auth activationUnlock
- user update
- auth mfaVerify
- team update
- axway get accessible teams for the query
- axway accept terms & conditions
- axway reset user password
- axway retrieve authorized devices
- role find
- auth sessionFind
- authentication
- user findDomain
- access management
- axway add member
- axway switch signed-in organization
- axway resends device authorization
- user findAttribute
- auth activationForgot
- session find
- axway activate a signup user
- axway send forgot password link
- axway get session
- auth deviceauthRemove
- axway get a user
- axway find a mapped attribute for a user
- auth validatePassword
- axway get roles matching query
- auth sessionSwitchOrg
- axway resend activation link
- team userAdd
- axway get role
- user remove
- team create
- axway set credentials for tooling
- auth onboarding
- auth deviceauthValidate
- role operations
- session operations
- team userUpdateRole
- axway sign up
- axway find team
- auth revokeOauth
- auth unimpersonate
- user findOrgs
- session query
- axway validates a user password
- axway verify an authorization code
- auth activationSignup
- axway sign-out
- auth deviceauthResend
- axway onboarding capture
- axway send an authorization code
- auth activationFind
- axway find sessions
- team find
- role findOne
- auth signup
- team findOne
- axway find activation
- axway find missing domain users
- axway remove member
- enterprise
- auth deviceauthCreate
- axway revoke oauth service
- axway get team members
- axway validates a new sessions device authorization
- axway unlock account
- auth deviceauthFind
- auth deviceauthRemoveApp
- axway create a team
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Axway Identity and Access Management\n  description: Manage users, teams, roles, sessions, and authentication across the Axway Amplify platform.\n  tags:\n  - Axway\n  - Identity\n  - Access Management\n  - Authentication\n  created: '2026-04-21'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: amplify-platform\n    baseUri: https://platform.axway.com/api/v1\n    description: Axway Amplify Platform API v1\n    authentication:\n      type: bearer\n      token: '{{env.AXWAY_BEARER_TOKEN}}'\n    resources:\n    - name: aca\n      path: /aca\n      description: Aca management operations\n      operations:\n      - name: aca-setMetadata\n        method: PUT\n        description: Axway Set Metadata by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name parameter\n        body:\n          type: json\n          data: {}\n      - name: aca-findOne\n        method: GET\n        description: Axway Find Crash Record by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n   \
  \     - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: aca_id\n          in: path\n          type: string\n          required: true\n          description: aca_id parameter\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n    - name: activity\n      path: /activity\n      description: Activity management operations\n      operations:\n      - name: activity-findEvents\n        method: GET\n        description: Axway Get Activity Event Names\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n    \
  \      description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: authorization\n          in: header\n          type: string\n          required: false\n          description: authorization parameter\n      - name: activity-find\n        method: GET\n        description: Axway Get Activity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: contexts\n          in: query\n\
  \          type: array\n          required: false\n          description: contexts parameter\n        - name: data\n          in: query\n          type: boolean\n          required: false\n          description: data parameter\n        - name: enrich\n          in: query\n          type: boolean\n          required: false\n          description: enrich parameter\n        - name: exclude_contexts\n          in: query\n          type: array\n          required: false\n          description: exclude_contexts parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: redact\n          in: query\n          type: boolean\n          required: false\n          description: redact parameter\n        - name: sort\n          in: query\n          type: number\n  \
  \        required: false\n          description: sort parameter\n        - name: term\n          in: query\n          type: string\n          required: false\n          description: term parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: user_guid\n          in: query\n          type: string\n          required: false\n          description: user_guid parameter\n        - name: user_messages\n          in: query\n          type: boolean\n          required: false\n          description: user_messages parameter\n        - name: limit\n          in: query\n          type: number\n          required: false\n          description: limit parameter\n        - name: page\n          in: query\n          type: number\n          required: false\n          description: page parameter\n        - name: skip\n          in: query\n          type: number\n          required: false\n          description:\
  \ skip parameter\n    - name: analytics\n      path: /analytics\n      description: Analytics management operations\n      operations:\n      - name: analytics-query\n        method: GET\n        description: Axway Analytics Query Using Lexus\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: apim_tier\n          in: query\n          type: string\n          required: false\n          description: apim_tier parameter\n        - name: app_guid\n          in: query\n          type: string\n          required: false\n          description: app_guid parameter\n        - name: clients\n          in: query\n          type: array\n          required: false\n          description: clients parameter\n        - name: cross_org\n          in: query\n          type: boolean\n          required: false\n          description: cross_org parameter\n        - name: custom_query\n      \
  \    in: query\n          type: string\n          required: false\n          description: custom_query parameter\n        - name: debug\n          in: query\n          type: boolean\n          required: false\n          description: debug parameter\n        - name: endpoint\n          in: query\n          type: string\n          required: false\n          description: endpoint parameter\n        - name: events\n          in: query\n          type: string\n          required: false\n          description: events parameter\n        - name: field\n          in: query\n          type: string\n          required: false\n          description: field parameter\n        - name: from\n          in: query\n          type: number\n          required: false\n          description: from parameter\n        - name: granularity\n          in: query\n          type: string\n          required: false\n          description: granularity parameter\n        - name: group_by\n          in: query\n         \
  \ type: string\n          required: false\n          description: group_by parameter\n        - name: grquantity\n          in: query\n          type: number\n          required: false\n          description: grquantity parameter\n        - name: include_query\n          in: query\n          type: string\n          required: false\n          description: include_query parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n        - name: platform\n          in: query\n          type: string\n          required: false\n          description: platform parameter\n        - name: post_process\n          in: query\n          type: boolean\n          required: false\n          description: post_process parameter\n        - name: prefix\n          in: query\n          type: string\n          required: false\n          description: prefix parameter\n        - name: preprocessor\n          in: query\n \
  \         type: string\n          required: false\n          description: preprocessor parameter\n        - name: processor\n          in: query\n          type: string\n          required: false\n          description: processor parameter\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: query parameter\n        - name: region\n          in: query\n          type: string\n          required: false\n          description: region parameter\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: status parameter\n        - name: to\n          in: query\n          type: number\n          required: false\n          description: to parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: type parameter\n        - name: username\n          in: query\n          type: string\n          required:\
  \ false\n          description: username parameter\n      - name: analytics-error\n        method: POST\n        description: Axway Report an Error\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: analytics-customCreate\n        method: POST\n        description: Axway Create a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n       \
  \ body:\n          type: json\n          data: {}\n      - name: analytics-customFind\n        method: GET\n        description: Axway Find Custom Queries\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customRemove\n        method: DELETE\n        description: Axway Delete a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n         \
  \ in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: analytics-customUpdate\n        method: PUT\n        description: Axway Update a Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n         \
  \ description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n      - name: analytics-customFindOne\n        method: GET\n        description: Axway Get Custom Query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: query_id\n          in: path\n          type: string\n          required: true\n          description: query_id\
  \ parameter\n        - name: org_id\n          in: query\n          type: string\n          required: false\n          description: org_id parameter\n    - name: app\n      path: /app\n      description: App management operations\n      operations:\n      - name: app-create\n        method: POST\n        description: Axway Create App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: app-find\n        method: GET\n        description: Axway Find Apps\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        inputParameters:\n        - name: fields\n          in: query\n          type: array\n          required: false\n          description: A list of fields to include in the response.\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: subtype\n          in: query\n          type: string\n          required: false\n          description: subtype parameter\n        - name: type\n          in: query\n          type: string\n          required: false\n          description:\
  \ type parameter\n      - name: app-findOne\n        method: GET\n        description: Axway Find App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n      - name: app-remove\n        method: DELETE\n        description: Axway Remove App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required: true\n          description: app_id parameter\n      - name: app-update\n        method: PUT\n        description: Axway Update App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: app_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: app_id parameter\n        - name: org_id\n          in: query\n          type: integer\n          required: false\n          description: org_id parameter\n        body:\n          type: json\n          data: {}\n    - name: auth\n      path: /auth\n      description: Auth management operations\n      operations:\n      - name: auth-validatePassword\n        method: POST\n        description: Axway Validates a User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-acceptTerms\n        method: PUT\n        description: Axway Accept Terms & Conditions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n      - name: auth-sessionSwitchOrg\n        method: POST\n        description: Axway Switch Signed-in Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data:\
  \ {}\n      - name: auth-signup\n        method: POST\n        description: Axway Sign Up\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-findPasswordPolicy\n        method: GET\n        description: Axway Get Effective Password Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: provider_guid\n          in: query\n          type: string\n          required: false\n          description: provider_guid parameter\n        - name: user_guid\n          in: query\n\
  \          type: string\n          required: false\n          description: user_guid parameter\n      - name: auth-onboarding\n        method: PUT\n        description: Axway Onboarding Capture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaVerify\n        method: POST\n        description: Axway Verify an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-mfaSend\n        method: POST\n        description: Axway Send an Authorization Code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: auth-logout\n        method: GET\n      \
  \  description: Axway Sign-out\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: msg\n          in: query\n          type: string\n          required: false\n          description: msg parameter\n        - name: redirect\n          in: query\n          type: string\n          required: false\n          description: redirect parameter\n      - name: auth-login\n        method: POST\n        description: Axway Sign-in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n      \
  \    type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-unimpersonate\n        method: DELETE\n        description: Axway Unimpersonate User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-forgot\n        method: POST\n        description: Axway Send\
  \ Forgot Password Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionFind\n        method: GET\n        description: Axway Retrieves the Current Session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: from parameter\n      - name: auth-deviceauthResend\n        method: POST\n        description: Axway Resends Device Authorization\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthValidate\n        method: POST\n        description: Axway Validates a New Sessions Device Authorization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: grant\n          in: query\n          type: string\n\
  \          required: false\n          description: grant parameter\n        body:\n          type: json\n          data: {}\n      - name: auth-sessionCheck\n        method: GET\n        description: Axway Checks if the User is Signed in\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthConfirm\n        method: POST\n        description: Axway Confirm Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-deviceauthCreate\n        method:\
  \ GET\n        description: Axway Initiate Authenticator App Setup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n      - name: auth-deviceauthRemoveApp\n        method: DELETE\n        description: Axway Remove Authenticator App\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: x-auth-password\n          in: header\n          type: string\n          required: true\n          description: x-auth-password parameter\n      - name: auth-activationSignup\n        method: POST\n        description: Axway Activate a\
  \ Signup User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationResend\n        method: POST\n        description: Axway Resend Activation Link\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationForgot\n        method: POST\n        description: Axway Reset User Password\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationConfirm\n        method: POST\n        description: Axway Activate a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n        body:\n          type: json\n          data: {}\n      - name: auth-activationUnlock\n        method: PUT\n        description: Axway Unlock Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n      - name: auth-revokeOauth\n        method: DELETE\n        description: Axway Revoke OAuth Service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n      \
  \  - name: service\n          in: path\n          type: string\n          required: true\n          description: service parameter\n      - name: auth-deviceauthFind\n        method: GET\n        description: Axway Retrieve Authorized Devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: user_id parameter\n      - name: auth-deviceauthRemove\n        method: DELETE\n        description: Axway Remove Authorized Device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        inputParameters:\n        - name: device_id\n          in: path\n          type: string\n          required: true\n          description: device_id parameter\n      - name: auth-activationFind\n        method: GET\n        description: Axway Find Activation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: activation_id\n          in: path\n          type: string\n          required: true\n          description: activation_id parameter\n    - name: client\n      path: /client\n      description: Client management operations\n      operations:\n      - name: client-create\n   \
  \     method: POST\n        description: Axway Add Service Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        body:\n          type: json\n          data: {}\n      - name: client-find\n        method: GET\n        description: Axway Get Service Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        inputParameters:\n        - name: ''\n          in: query\n          type: string\n          required: false\n          description: ' parameter'\n        - name: ''\n          in: query\n          type: string\n          required:\
  \ false\n          description: \n\n# --- truncated at 32 KB (134 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/identity-and-access.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/axway/refs/heads/main/capabilities/identity-and-access.yaml
tags:
- Axway
- Identity
- Access Management
- Authentication
tools:
- description: Axway Validates a User Password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-validatePassword
- description: Axway Accept Terms & Conditions
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: auth-acceptTerms
- description: Axway Switch Signed-in Organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-sessionSwitchOrg
- description: Axway Sign Up
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-signup
- description: Axway Get Effective Password Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-findPasswordPolicy
- description: Axway Onboarding Capture
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: auth-onboarding
- description: Axway Verify an Authorization Code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-mfaVerify
- description: Axway Send an Authorization Code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-mfaSend
- description: Axway Sign-out
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-logout
- description: Axway Sign-in
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-login
- description: Axway Unimpersonate User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: auth-unimpersonate
- description: Axway Send Forgot Password Link
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-forgot
- description: Axway Retrieves the Current Session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-sessionFind
- description: Axway Resends Device Authorization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-deviceauthResend
- description: Axway Validates a New Sessions Device Authorization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-deviceauthValidate
- description: Axway Checks if the User is Signed in
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-sessionCheck
- description: Axway Confirm Authenticator App
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-deviceauthConfirm
- description: Axway Initiate Authenticator App Setup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-deviceauthCreate
- description: Axway Remove Authenticator App
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: auth-deviceauthRemoveApp
- description: Axway Activate a Signup User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-activationSignup
- description: Axway Resend Activation Link
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-activationResend
- description: Axway Reset User Password
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-activationForgot
- description: Axway Activate a User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: auth-activationConfirm
- description: Axway Unlock Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: auth-activationUnlock
- description: Axway Revoke OAuth Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: auth-revokeOauth
- description: Axway Retrieve Authorized Devices
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-deviceauthFind
- description: Axway Remove Authorized Device
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: auth-deviceauthRemove
- description: Axway Find Activation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: auth-activationFind
- description: Axway Update a Single User Preference
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: user-updatePref
- description: Axway Get Organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: user-findOrgs
- description: Axway Set Credentials for Tooling
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: user-updateCredentials
- description: Axway Update User Profile
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: user-update
- description: Axway Find Missing Domain Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: user-findDomain
- description: Axway Find a Mapped Attribute for a User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: user-findAttribute
- description: Axway Get a User
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: user-findOne
- description: Axway Remove User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: user-remove
- description: Axway Create a Team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: team-create
- description: Axway Get Accessible Teams for the Query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: team-find
- description: Axway Add Member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: team-userAdd
- description: Axway Remove Member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: team-userRemove
- description: Axway Sets the Team Member Role
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: team-userUpdateRole
- description: Axway Get Team Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: team-userFind
- description: Axway Find Team
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: team-findOne
- description: Axway Remove Team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: team-remove
- description: Axway Update Team
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: team-update
- description: Axway Get Roles Matching Query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: role-find
- description: Axway Get Role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: role-findOne
- description: Axway Find Sessions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: session-query
- description: Axway Get Session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: session-find
- description: Axway Delete Session
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: session-remove
---
