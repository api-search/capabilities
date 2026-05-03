---
categories: []
consumed_apis:
- amplify-platform
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
- auth deviceauthCreate
- axway delete session
- axway validates a new sessions device authorization
- team userFind
- auth deviceauthConfirm
- axway revoke oauth service
- axway find sessions
- security
- auth mfaSend
- auth mfaVerify
- auth sessionSwitchOrg
- user findOne
- auth onboarding
- axway unlock account
- user operations
- auth deviceauthRemove
- auth operations
- auth deviceauthValidate
- axway get organizations
- axway get roles matching query
- axway get role
- auth activationConfirm
- axway activate a signup user
- axway sign-out
- axway retrieve authorized devices
- user update
- auth activationResend
- team operations
- axway checks if the user is signed in
- user findOrgs
- axway switch signed-in organization
- axway find team
- axway send an authorization code
- axway reset user password
- axway add member
- team find
- axway find missing domain users
- authentication
- team update
- axway accept terms & conditions
- axway unimpersonate user
- axway confirm authenticator app
- auth activationFind
- auth acceptTerms
- auth signup
- axway update team
- auth forgot
- axway remove authorized device
- auth sessionCheck
- session find
- user updateCredentials
- axway retrieves the current session
- axway find a mapped attribute for a user
- team findOne
- axway remove member
- team userAdd
- axway get effective password policy
- axway get a user
- axway onboarding capture
- axway
- session query
- role findOne
- user updatePref
- team create
- session remove
- team remove
- auth deviceauthFind
- identity
- axway sets the team member role
- auth deviceauthResend
- auth logout
- axway set credentials for tooling
- auth findPasswordPolicy
- team userRemove
- auth login
- user findDomain
- session operations
- axway update a single user preference
- axway update user profile
- axway get session
- axway create a team
- role find
- auth validatePassword
- auth unimpersonate
- axway get accessible teams for the query
- axway resend activation link
- axway get team members
- auth activationSignup
- axway remove user
- user remove
- api management
- axway remove team
- auth activationForgot
- integration
- axway activate a user
- axway find activation
- auth revokeOauth
- axway sign-in
- axway sign up
- team userUpdateRole
- auth activationUnlock
- enterprise
- axway resends device authorization
- access management
- axway validates a user password
- axway initiate authenticator app setup
- auth deviceauthRemoveApp
- role operations
- axway remove authenticator app
- axway verify an authorization code
- axway send forgot password link
- user findAttribute
- auth sessionFind
slug: identity-and-access
source_filename: identity-and-access.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Axway Identity and Access Management\n  description: Manage users, teams, roles, sessions, and authentication across the Axway Amplify platform.\n  tags:\n  - Axway\n  - Identity\n  - Access Management\n  - Authentication\n  created: '2026-04-21'\n  modified: '2026-04-21'\nbinds:\n- namespace: env\n  keys:\n    AXWAY_BEARER_TOKEN: AXWAY_BEARER_TOKEN\ncapability:\n  consumes:\n  - import: amplify-platform\n    location: ./shared/amplify-platform.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: identity-and-access-api\n    description: Unified REST API for manage users, teams, roles, sessions, and authentication across the axway amplify platform.\n    resources:\n    - path: /v1/auth\n      name: auth\n      description: Auth operations\n      operations:\n      - method: POST\n        name: auth-validatePassword\n        description: Axway Validates a User Password\n        call: amplify-platform.auth-validatePassword\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: auth-acceptTerms\n        description: Axway Accept Terms & Conditions\n        call: amplify-platform.auth-acceptTerms\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-sessionSwitchOrg\n        description: Axway Switch Signed-in Organization\n        call: amplify-platform.auth-sessionSwitchOrg\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-signup\n        description: Axway Sign Up\n        call: amplify-platform.auth-signup\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-findPasswordPolicy\n        description: Axway Get Effective Password Policy\n        call: amplify-platform.auth-findPasswordPolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: PUT\n        name: auth-onboarding\n        description: Axway Onboarding Capture\n        call: amplify-platform.auth-onboarding\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-mfaVerify\n        description: Axway Verify an Authorization Code\n        call: amplify-platform.auth-mfaVerify\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-mfaSend\n        description: Axway Send an Authorization Code\n        call: amplify-platform.auth-mfaSend\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-logout\n        description: Axway Sign-out\n        call: amplify-platform.auth-logout\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-login\n        description: Axway Sign-in\n        call: amplify-platform.auth-login\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: auth-unimpersonate\n        description: Axway Unimpersonate User\n        call: amplify-platform.auth-unimpersonate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-forgot\n        description: Axway Send Forgot Password Link\n        call: amplify-platform.auth-forgot\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-sessionFind\n        description: Axway Retrieves the Current Session\n        call: amplify-platform.auth-sessionFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-deviceauthResend\n        description: Axway Resends Device Authorization\n        call: amplify-platform.auth-deviceauthResend\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: POST\n        name: auth-deviceauthValidate\n        description: Axway Validates a New Sessions Device Authorization\n        call: amplify-platform.auth-deviceauthValidate\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-sessionCheck\n        description: Axway Checks if the User is Signed in\n        call: amplify-platform.auth-sessionCheck\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-deviceauthConfirm\n        description: Axway Confirm Authenticator App\n        call: amplify-platform.auth-deviceauthConfirm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-deviceauthCreate\n        description: Axway Initiate Authenticator App Setup\n        call: amplify-platform.auth-deviceauthCreate\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \      - method: DELETE\n        name: auth-deviceauthRemoveApp\n        description: Axway Remove Authenticator App\n        call: amplify-platform.auth-deviceauthRemoveApp\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-activationSignup\n        description: Axway Activate a Signup User\n        call: amplify-platform.auth-activationSignup\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-activationResend\n        description: Axway Resend Activation Link\n        call: amplify-platform.auth-activationResend\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-activationForgot\n        description: Axway Reset User Password\n        call: amplify-platform.auth-activationForgot\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: auth-activationConfirm\n\
  \        description: Axway Activate a User\n        call: amplify-platform.auth-activationConfirm\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: auth-activationUnlock\n        description: Axway Unlock Account\n        call: amplify-platform.auth-activationUnlock\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: auth-revokeOauth\n        description: Axway Revoke OAuth Service\n        call: amplify-platform.auth-revokeOauth\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-deviceauthFind\n        description: Axway Retrieve Authorized Devices\n        call: amplify-platform.auth-deviceauthFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: auth-deviceauthRemove\n        description: Axway Remove Authorized Device\n        call: amplify-platform.auth-deviceauthRemove\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: auth-activationFind\n        description: Axway Find Activation\n        call: amplify-platform.auth-activationFind\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user\n      name: user\n      description: User operations\n      operations:\n      - method: PUT\n        name: user-updatePref\n        description: Axway Update a Single User Preference\n        call: amplify-platform.user-updatePref\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: user-findOrgs\n        description: Axway Get Organizations\n        call: amplify-platform.user-findOrgs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: user-updateCredentials\n        description: Axway Set Credentials for Tooling\n        call: amplify-platform.user-updateCredentials\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: user-update\n        description: Axway Update User Profile\n        call: amplify-platform.user-update\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: user-findDomain\n        description: Axway Find Missing Domain Users\n        call: amplify-platform.user-findDomain\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: user-findAttribute\n        description: Axway Find a Mapped Attribute for a User\n        call: amplify-platform.user-findAttribute\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: user-findOne\n        description: Axway Get a User\n        call: amplify-platform.user-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name:\
  \ user-remove\n        description: Axway Remove User\n        call: amplify-platform.user-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/team\n      name: team\n      description: Team operations\n      operations:\n      - method: POST\n        name: team-create\n        description: Axway Create a Team\n        call: amplify-platform.team-create\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: team-find\n        description: Axway Get Accessible Teams for the Query\n        call: amplify-platform.team-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: team-userAdd\n        description: Axway Add Member\n        call: amplify-platform.team-userAdd\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: team-userRemove\n        description: Axway Remove Member\n\
  \        call: amplify-platform.team-userRemove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: team-userUpdateRole\n        description: Axway Sets the Team Member Role\n        call: amplify-platform.team-userUpdateRole\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: team-userFind\n        description: Axway Get Team Members\n        call: amplify-platform.team-userFind\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: team-findOne\n        description: Axway Find Team\n        call: amplify-platform.team-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: team-remove\n        description: Axway Remove Team\n        call: amplify-platform.team-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ PUT\n        name: team-update\n        description: Axway Update Team\n        call: amplify-platform.team-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/role\n      name: role\n      description: Role operations\n      operations:\n      - method: GET\n        name: role-find\n        description: Axway Get Roles Matching Query\n        call: amplify-platform.role-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: role-findOne\n        description: Axway Get Role\n        call: amplify-platform.role-findOne\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/session\n      name: session\n      description: Session operations\n      operations:\n      - method: POST\n        name: session-query\n        description: Axway Find Sessions\n        call: amplify-platform.session-query\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: GET\n        name: session-find\n        description: Axway Get Session\n        call: amplify-platform.session-find\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: session-remove\n        description: Axway Delete Session\n        call: amplify-platform.session-remove\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: identity-and-access-mcp\n    transport: http\n    description: MCP server for AI-assisted manage users, teams, roles, sessions, and authentication across the axway amplify platform.\n    tools:\n    - name: auth-validatePassword\n      description: Axway Validates a User Password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-validatePassword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ auth-acceptTerms\n      description: Axway Accept Terms & Conditions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-acceptTerms\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-sessionSwitchOrg\n      description: Axway Switch Signed-in Organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-sessionSwitchOrg\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-signup\n      description: Axway Sign Up\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-signup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-findPasswordPolicy\n      description: Axway Get Effective Password Policy\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: amplify-platform.auth-findPasswordPolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-onboarding\n      description: Axway Onboarding Capture\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-onboarding\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-mfaVerify\n      description: Axway Verify an Authorization Code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-mfaVerify\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-mfaSend\n      description: Axway Send an Authorization Code\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-mfaSend\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: auth-logout\n      description: Axway Sign-out\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-logout\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-login\n      description: Axway Sign-in\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-login\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-unimpersonate\n      description: Axway Unimpersonate User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.auth-unimpersonate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-forgot\n      description: Axway Send Forgot Password Link\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-forgot\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-sessionFind\n      description: Axway Retrieves the Current Session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-sessionFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthResend\n      description: Axway Resends Device Authorization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-deviceauthResend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthValidate\n      description: Axway Validates a New Sessions Device Authorization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-deviceauthValidate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ auth-sessionCheck\n      description: Axway Checks if the User is Signed in\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-sessionCheck\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthConfirm\n      description: Axway Confirm Authenticator App\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-deviceauthConfirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthCreate\n      description: Axway Initiate Authenticator App Setup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-deviceauthCreate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthRemoveApp\n      description: Axway Remove Authenticator App\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.auth-deviceauthRemoveApp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationSignup\n      description: Axway Activate a Signup User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-activationSignup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationResend\n      description: Axway Resend Activation Link\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-activationResend\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationForgot\n      description: Axway Reset User Password\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-activationForgot\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationConfirm\n      description: Axway Activate a User\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.auth-activationConfirm\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationUnlock\n      description: Axway Unlock Account\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-activationUnlock\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-revokeOauth\n      description: Axway Revoke OAuth Service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.auth-revokeOauth\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthFind\n      description: Axway Retrieve\
  \ Authorized Devices\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-deviceauthFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-deviceauthRemove\n      description: Axway Remove Authorized Device\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.auth-deviceauthRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: auth-activationFind\n      description: Axway Find Activation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.auth-activationFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-updatePref\n      description: Axway Update a Single User Preference\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n    \
  \  call: amplify-platform.user-updatePref\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-findOrgs\n      description: Axway Get Organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-findOrgs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-updateCredentials\n      description: Axway Set Credentials for Tooling\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-updateCredentials\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-update\n      description: Axway Update User Profile\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-findDomain\n      description:\
  \ Axway Find Missing Domain Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-findDomain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-findAttribute\n      description: Axway Find a Mapped Attribute for a User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-findAttribute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-findOne\n      description: Axway Get a User\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.user-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: user-remove\n      description: Axway Remove User\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.user-remove\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-create\n      description: Axway Create a Team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.team-create\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-find\n      description: Axway Get Accessible Teams for the Query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.team-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-userAdd\n      description: Axway Add Member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.team-userAdd\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-userRemove\n      description: Axway Remove Member\n      hints:\n        readOnly: false\n \
  \       destructive: true\n        idempotent: true\n      call: amplify-platform.team-userRemove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-userUpdateRole\n      description: Axway Sets the Team Member Role\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.team-userUpdateRole\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-userFind\n      description: Axway Get Team Members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.team-userFind\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-findOne\n      description: Axway Find Team\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.team-findOne\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: team-remove\n      description: Axway Remove Team\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.team-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: team-update\n      description: Axway Update Team\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: amplify-platform.team-update\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: role-find\n      description: Axway Get Roles Matching Query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.role-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: role-findOne\n      description: Axway Get Role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.role-findOne\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: session-query\n      description: Axway Find Sessions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amplify-platform.session-query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: session-find\n      description: Axway Get Session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: amplify-platform.session-find\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: session-remove\n      description: Axway Delete Session\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: amplify-platform.session-remove\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
