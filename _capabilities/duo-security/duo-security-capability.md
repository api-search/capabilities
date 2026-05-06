---
categories: []
consumed_apis: []
description: The Duo Admin API provides programmatic access to the administrative functionality of Duo Security for managing users, groups, phones, hardware tokens, WebAuthn credentials, integrations, and bypass codes. Requests are authenticated using HMAC-SHA1 signed HTTP Basic credentials derived from your integration key and secret key.
layout: capability
name: Duo Admin API
operations:
- description: List users
  method: GET
  name: listusers
  path: /admin/v1/users
- description: Create user
  method: POST
  name: createuser
  path: /admin/v1/users
- description: Bulk create users
  method: POST
  name: bulkcreateusers
  path: /admin/v1/users/bulk_create
- description: Bulk restore users
  method: POST
  name: bulkrestoreusers
  path: /admin/v1/users/bulk_restore
- description: Bulk send users to Trash
  method: POST
  name: bulksenduserstotrash
  path: /admin/v1/users/bulk_send_to_trash
- description: Get user
  method: GET
  name: getuser
  path: /admin/v1/users/{user_id}
- description: Update user
  method: POST
  name: updateuser
  path: /admin/v1/users/{user_id}
- description: Delete user
  method: DELETE
  name: deleteuser
  path: /admin/v1/users/{user_id}
- description: Enroll user
  method: POST
  name: enrolluser
  path: /admin/v1/users/enroll
- description: List user bypass codes
  method: GET
  name: listuserbypasscodes
  path: /admin/v1/users/{user_id}/bypass_codes
- description: Generate bypass codes
  method: POST
  name: createuserbypasscodes
  path: /admin/v1/users/{user_id}/bypass_codes
- description: List user groups
  method: GET
  name: listusergroups
  path: /admin/v1/users/{user_id}/groups
- description: Associate group with user
  method: POST
  name: associateusergroup
  path: /admin/v1/users/{user_id}/groups
- description: Disassociate group from user
  method: DELETE
  name: disassociateusergroup
  path: /admin/v1/users/{user_id}/groups/{group_id}
- description: List user phones
  method: GET
  name: listuserphones
  path: /admin/v1/users/{user_id}/phones
- description: Associate phone with user
  method: POST
  name: associateuserphone
  path: /admin/v1/users/{user_id}/phones
- description: Disassociate phone from user
  method: DELETE
  name: disassociateuserphone
  path: /admin/v1/users/{user_id}/phones/{phone_id}
- description: List user hardware tokens
  method: GET
  name: listusertokens
  path: /admin/v1/users/{user_id}/tokens
- description: Associate hardware token with user
  method: POST
  name: associateusertoken
  path: /admin/v1/users/{user_id}/tokens
- description: Disassociate hardware token from user
  method: DELETE
  name: disassociateusertoken
  path: /admin/v1/users/{user_id}/tokens/{token_id}
- description: List WebAuthn credentials for user
  method: GET
  name: listuserwebauthncredentials
  path: /admin/v1/users/{user_id}/webauthncredentials
- description: List desktop authenticators for user
  method: GET
  name: listuserdesktopauthenticators
  path: /admin/v1/users/{user_id}/desktopauthenticators
- description: List user directory syncs
  method: GET
  name: listuserdirectorysyncs
  path: /admin/v1/users/directorysync
- description: Sync directory user
  method: POST
  name: syncdirectoryuser
  path: /admin/v1/users/directorysync/{directory_key}/syncuser
- description: Send verification Duo Push
  method: POST
  name: sendverificationpush
  path: /admin/v1/users/{user_id}/send_verification_push
- description: Retrieve verification push result
  method: GET
  name: getverificationpushresponse
  path: /admin/v1/users/{user_id}/verification_push_response
- description: List groups
  method: GET
  name: listgroups
  path: /admin/v1/groups
- description: Create group
  method: POST
  name: creategroup
  path: /admin/v1/groups
- description: Update group
  method: POST
  name: updategroup
  path: /admin/v1/groups/{group_id}
- description: Get group (v2)
  method: GET
  name: getgroupv2
  path: /admin/v2/groups/{group_id}
- description: List group users (v2)
  method: GET
  name: listgroupusersv2
  path: /admin/v2/groups/{group_id}/users
- description: Bulk operations
  method: POST
  name: bulkoperations
  path: /admin/v1/bulk
personas: []
provider_name: Duo Security
provider_slug: duo-security
search_terms:
- enrolluser
- associate phone with user
- creategroup
- get group (v2)
- createuser
- sendverificationpush
- disassociateuserphone
- generate bypass codes
- associateusergroup
- identity
- list group users (v2)
- syncdirectoryuser
- send verification duo push
- disassociate phone from user
- associateuserphone
- bulkoperations
- disassociateusertoken
- listuserdesktopauthenticators
- create user
- sync directory user
- getgroupv2
- mfa
- bulk create users
- security
- list user hardware tokens
- listusergroups
- bulk send users to trash
- list user directory syncs
- create group
- list user bypass codes
- update group
- delete user
- bulksenduserstotrash
- listgroups
- associate group with user
- list user groups
- disassociateusergroup
- api
- bulkrestoreusers
- createuserbypasscodes
- disassociate hardware token from user
- bulkcreateusers
- disassociate group from user
- associate hardware token with user
- listuserbypasscodes
- duo
- list webauthn credentials for user
- list desktop authenticators for user
- retrieve verification push result
- listgroupusersv2
- update user
- listuserwebauthncredentials
- authentication
- get user
- listuserphones
- associateusertoken
- getuser
- bulk operations
- list users
- listuserdirectorysyncs
- listusertokens
- getverificationpushresponse
- list groups
- listusers
- zero trust
- updateuser
- bulk restore users
- enroll user
- list user phones
- updategroup
- deleteuser
slug: duo-security-capability
source_filename: duo-security-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Duo Admin API\n  description: The Duo Admin API provides programmatic access to the administrative functionality of Duo Security for managing\n    users, groups, phones, hardware tokens, WebAuthn credentials, integrations, and bypass codes. Requests are authenticated\n    using HMAC-SHA1 signed HTTP Basic credentials derived from your integration key and secret key.\n  tags:\n  - Duo\n  - Security\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: duo-security\n    baseUri: https://api-XXXXXXXX.duosecurity.com\n    description: Duo Admin API HTTP API.\n    authentication:\n      type: basic\n      username: '{{DUO_SECURITY_USERNAME}}'\n      password: '{{DUO_SECURITY_PASSWORD}}'\n    resources:\n    - name: admin-v1-users\n      path: /admin/v1/users\n      operations:\n      - name: listusers\n        method: GET\n        description: List users\n        inputParameters:\n\
  \        - name: username\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        - name: offset\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuser\n        method: POST\n        description: Create user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-bulk-create\n      path: /admin/v1/users/bulk_create\n      operations:\n      - name: bulkcreateusers\n        method: POST\n        description: Bulk create users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-bulk-restore\n      path: /admin/v1/users/bulk_restore\n      operations:\n      - name: bulkrestoreusers\n\
  \        method: POST\n        description: Bulk restore users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-bulk-send-to-trash\n      path: /admin/v1/users/bulk_send_to_trash\n      operations:\n      - name: bulksenduserstotrash\n        method: POST\n        description: Bulk send users to Trash\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id\n      path: /admin/v1/users/{user_id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: POST\n        description: Update user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-enroll\n      path: /admin/v1/users/enroll\n      operations:\n      - name: enrolluser\n        method: POST\n        description: Enroll user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-bypass-codes\n      path: /admin/v1/users/{user_id}/bypass_codes\n      operations:\n      - name: listuserbypasscodes\n        method: GET\n        description: List user bypass codes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createuserbypasscodes\n        method: POST\n        description: Generate bypass codes\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-groups\n      path: /admin/v1/users/{user_id}/groups\n      operations:\n      - name: listusergroups\n        method: GET\n        description: List user groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: associateusergroup\n        method: POST\n        description: Associate group with user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-groups-group-id\n      path: /admin/v1/users/{user_id}/groups/{group_id}\n      operations:\n      - name: disassociateusergroup\n        method: DELETE\n        description: Disassociate group from user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: admin-v1-users-user-id-phones\n      path: /admin/v1/users/{user_id}/phones\n      operations:\n      - name: listuserphones\n        method: GET\n        description: List user phones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: associateuserphone\n        method: POST\n        description: Associate phone with user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-phones-phone-id\n      path: /admin/v1/users/{user_id}/phones/{phone_id}\n      operations:\n      - name: disassociateuserphone\n        method: DELETE\n        description: Disassociate phone from user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-tokens\n\
  \      path: /admin/v1/users/{user_id}/tokens\n      operations:\n      - name: listusertokens\n        method: GET\n        description: List user hardware tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: associateusertoken\n        method: POST\n        description: Associate hardware token with user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-tokens-token-id\n      path: /admin/v1/users/{user_id}/tokens/{token_id}\n      operations:\n      - name: disassociateusertoken\n        method: DELETE\n        description: Disassociate hardware token from user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-webauthncredentials\n      path: /admin/v1/users/{user_id}/webauthncredentials\n\
  \      operations:\n      - name: listuserwebauthncredentials\n        method: GET\n        description: List WebAuthn credentials for user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-desktopauthenticators\n      path: /admin/v1/users/{user_id}/desktopauthenticators\n      operations:\n      - name: listuserdesktopauthenticators\n        method: GET\n        description: List desktop authenticators for user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-directorysync\n      path: /admin/v1/users/directorysync\n      operations:\n      - name: listuserdirectorysyncs\n        method: GET\n        description: List user directory syncs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: admin-v1-users-directorysync-directory-key-syncu\n      path: /admin/v1/users/directorysync/{directory_key}/syncuser\n      operations:\n      - name: syncdirectoryuser\n        method: POST\n        description: Sync directory user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-send-verification-push\n      path: /admin/v1/users/{user_id}/send_verification_push\n      operations:\n      - name: sendverificationpush\n        method: POST\n        description: Send verification Duo Push\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-users-user-id-verification-push-respons\n      path: /admin/v1/users/{user_id}/verification_push_response\n      operations:\n      - name: getverificationpushresponse\n        method: GET\n        description: Retrieve verification push\
  \ result\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-groups\n      path: /admin/v1/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: List groups\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: Create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-groups-group-id\n      path: /admin/v1/groups/{group_id}\n      operations:\n      - name: updategroup\n        method: POST\n        description: Update group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v2-groups-group-id\n      path: /admin/v2/groups/{group_id}\n\
  \      operations:\n      - name: getgroupv2\n        method: GET\n        description: Get group (v2)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v2-groups-group-id-users\n      path: /admin/v2/groups/{group_id}/users\n      operations:\n      - name: listgroupusersv2\n        method: GET\n        description: List group users (v2)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-v1-bulk\n      path: /admin/v1/bulk\n      operations:\n      - name: bulkoperations\n        method: POST\n        description: Bulk operations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: duo-security-rest\n    description: REST adapter for Duo Admin API.\n    resources:\n\
  \    - path: /admin/v1/users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: List users\n        call: duo-security.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users\n      name: createuser\n      operations:\n      - method: POST\n        name: createuser\n        description: Create user\n        call: duo-security.createuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/bulk_create\n      name: bulkcreateusers\n      operations:\n      - method: POST\n        name: bulkcreateusers\n        description: Bulk create users\n        call: duo-security.bulkcreateusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/bulk_restore\n      name: bulkrestoreusers\n      operations:\n      - method: POST\n        name: bulkrestoreusers\n        description: Bulk\
  \ restore users\n        call: duo-security.bulkrestoreusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/bulk_send_to_trash\n      name: bulksenduserstotrash\n      operations:\n      - method: POST\n        name: bulksenduserstotrash\n        description: Bulk send users to Trash\n        call: duo-security.bulksenduserstotrash\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get user\n        call: duo-security.getuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}\n      name: updateuser\n      operations:\n      - method: POST\n        name: updateuser\n        description: Update user\n        call: duo-security.updateuser\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /admin/v1/users/{user_id}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete user\n        call: duo-security.deleteuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/enroll\n      name: enrolluser\n      operations:\n      - method: POST\n        name: enrolluser\n        description: Enroll user\n        call: duo-security.enrolluser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/bypass_codes\n      name: listuserbypasscodes\n      operations:\n      - method: GET\n        name: listuserbypasscodes\n        description: List user bypass codes\n        call: duo-security.listuserbypasscodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/bypass_codes\n      name: createuserbypasscodes\n      operations:\n      -\
  \ method: POST\n        name: createuserbypasscodes\n        description: Generate bypass codes\n        call: duo-security.createuserbypasscodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/groups\n      name: listusergroups\n      operations:\n      - method: GET\n        name: listusergroups\n        description: List user groups\n        call: duo-security.listusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/groups\n      name: associateusergroup\n      operations:\n      - method: POST\n        name: associateusergroup\n        description: Associate group with user\n        call: duo-security.associateusergroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/groups/{group_id}\n      name: disassociateusergroup\n      operations:\n      - method: DELETE\n        name: disassociateusergroup\n\
  \        description: Disassociate group from user\n        call: duo-security.disassociateusergroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/phones\n      name: listuserphones\n      operations:\n      - method: GET\n        name: listuserphones\n        description: List user phones\n        call: duo-security.listuserphones\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/phones\n      name: associateuserphone\n      operations:\n      - method: POST\n        name: associateuserphone\n        description: Associate phone with user\n        call: duo-security.associateuserphone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/phones/{phone_id}\n      name: disassociateuserphone\n      operations:\n      - method: DELETE\n        name: disassociateuserphone\n        description: Disassociate\
  \ phone from user\n        call: duo-security.disassociateuserphone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/tokens\n      name: listusertokens\n      operations:\n      - method: GET\n        name: listusertokens\n        description: List user hardware tokens\n        call: duo-security.listusertokens\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/tokens\n      name: associateusertoken\n      operations:\n      - method: POST\n        name: associateusertoken\n        description: Associate hardware token with user\n        call: duo-security.associateusertoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/tokens/{token_id}\n      name: disassociateusertoken\n      operations:\n      - method: DELETE\n        name: disassociateusertoken\n        description: Disassociate hardware token\
  \ from user\n        call: duo-security.disassociateusertoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/webauthncredentials\n      name: listuserwebauthncredentials\n      operations:\n      - method: GET\n        name: listuserwebauthncredentials\n        description: List WebAuthn credentials for user\n        call: duo-security.listuserwebauthncredentials\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/desktopauthenticators\n      name: listuserdesktopauthenticators\n      operations:\n      - method: GET\n        name: listuserdesktopauthenticators\n        description: List desktop authenticators for user\n        call: duo-security.listuserdesktopauthenticators\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/directorysync\n      name: listuserdirectorysyncs\n      operations:\n      - method:\
  \ GET\n        name: listuserdirectorysyncs\n        description: List user directory syncs\n        call: duo-security.listuserdirectorysyncs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/directorysync/{directory_key}/syncuser\n      name: syncdirectoryuser\n      operations:\n      - method: POST\n        name: syncdirectoryuser\n        description: Sync directory user\n        call: duo-security.syncdirectoryuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/send_verification_push\n      name: sendverificationpush\n      operations:\n      - method: POST\n        name: sendverificationpush\n        description: Send verification Duo Push\n        call: duo-security.sendverificationpush\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/users/{user_id}/verification_push_response\n      name: getverificationpushresponse\n\
  \      operations:\n      - method: GET\n        name: getverificationpushresponse\n        description: Retrieve verification push result\n        call: duo-security.getverificationpushresponse\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/groups\n      name: listgroups\n      operations:\n      - method: GET\n        name: listgroups\n        description: List groups\n        call: duo-security.listgroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/groups\n      name: creategroup\n      operations:\n      - method: POST\n        name: creategroup\n        description: Create group\n        call: duo-security.creategroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/groups/{group_id}\n      name: updategroup\n      operations:\n      - method: POST\n        name: updategroup\n        description: Update group\n        call: duo-security.updategroup\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v2/groups/{group_id}\n      name: getgroupv2\n      operations:\n      - method: GET\n        name: getgroupv2\n        description: Get group (v2)\n        call: duo-security.getgroupv2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v2/groups/{group_id}/users\n      name: listgroupusersv2\n      operations:\n      - method: GET\n        name: listgroupusersv2\n        description: List group users (v2)\n        call: duo-security.listgroupusersv2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/v1/bulk\n      name: bulkoperations\n      operations:\n      - method: POST\n        name: bulkoperations\n        description: Bulk operations\n        call: duo-security.bulkoperations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: duo-security-mcp\n\
  \    transport: http\n    description: MCP adapter for Duo Admin API for AI agent use.\n    tools:\n    - name: listusers\n      description: List users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listusers\n      with:\n        username: tools.username\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: username\n        type: string\n        description: username\n      - name: limit\n        type: integer\n        description: limit\n      - name: offset\n        type: integer\n        description: offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuser\n      description: Create user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.createuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulkcreateusers\n      description:\
  \ Bulk create users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.bulkcreateusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulkrestoreusers\n      description: Bulk restore users\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.bulkrestoreusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulksenduserstotrash\n      description: Bulk send users to Trash\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.bulksenduserstotrash\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.getuser\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: updateuser\n      description: Update user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.updateuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: duo-security.deleteuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: enrolluser\n      description: Enroll user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.enrolluser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserbypasscodes\n      description: List user bypass codes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listuserbypasscodes\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createuserbypasscodes\n      description: Generate bypass codes\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.createuserbypasscodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusergroups\n      description: List user groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listusergroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associateusergroup\n      description: Associate group with user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.associateusergroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociateusergroup\n      description: Disassociate group from user\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: duo-security.disassociateusergroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserphones\n      description: List user phones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listuserphones\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associateuserphone\n      description: Associate phone with user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.associateuserphone\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociateuserphone\n      description: Disassociate phone from user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: duo-security.disassociateuserphone\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: listusertokens\n      description: List user hardware tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listusertokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: associateusertoken\n      description: Associate hardware token with user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.associateusertoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: disassociateusertoken\n      description: Disassociate hardware token from user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: duo-security.disassociateusertoken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserwebauthncredentials\n      description: List WebAuthn credentials for\
  \ user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listuserwebauthncredentials\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserdesktopauthenticators\n      description: List desktop authenticators for user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listuserdesktopauthenticators\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listuserdirectorysyncs\n      description: List user directory syncs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listuserdirectorysyncs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: syncdirectoryuser\n      description: Sync directory user\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n     \
  \ call: duo-security.syncdirectoryuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: sendverificationpush\n      description: Send verification Duo Push\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.sendverificationpush\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getverificationpushresponse\n      description: Retrieve verification push result\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.getverificationpushresponse\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroups\n      description: List groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listgroups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategroup\n      description:\
  \ Create group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.creategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategroup\n      description: Update group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.updategroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgroupv2\n      description: Get group (v2)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.getgroupv2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listgroupusersv2\n      description: List group users (v2)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: duo-security.listgroupusersv2\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: bulkoperations\n      description: Bulk operations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: duo-security.bulkoperations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DUO_SECURITY_USERNAME: DUO_SECURITY_USERNAME\n    DUO_SECURITY_PASSWORD: DUO_SECURITY_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/duo-security/refs/heads/main/capabilities/duo-security-capability.yaml
tags:
- Duo
- Security
- API
tools:
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Create user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuser
- description: Bulk create users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkcreateusers
- description: Bulk restore users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkrestoreusers
- description: Bulk send users to Trash
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulksenduserstotrash
- description: Get user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateuser
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Enroll user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: enrolluser
- description: List user bypass codes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserbypasscodes
- description: Generate bypass codes
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createuserbypasscodes
- description: List user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: Associate group with user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associateusergroup
- description: Disassociate group from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disassociateusergroup
- description: List user phones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserphones
- description: Associate phone with user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associateuserphone
- description: Disassociate phone from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disassociateuserphone
- description: List user hardware tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusertokens
- description: Associate hardware token with user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: associateusertoken
- description: Disassociate hardware token from user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: disassociateusertoken
- description: List WebAuthn credentials for user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserwebauthncredentials
- description: List desktop authenticators for user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserdesktopauthenticators
- description: List user directory syncs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuserdirectorysyncs
- description: Sync directory user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: syncdirectoryuser
- description: Send verification Duo Push
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendverificationpush
- description: Retrieve verification push result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getverificationpushresponse
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: Update group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategroup
- description: Get group (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroupv2
- description: List group users (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroupusersv2
- description: Bulk operations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: bulkoperations
---
