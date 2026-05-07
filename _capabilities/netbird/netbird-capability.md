---
categories: []
consumed_apis: []
description: API to manipulate groups, rules, policies and retrieve information about peers and users
layout: capability
name: NetBird REST API
operations:
- description: Get Instance Status
  method: GET
  name: get-api-instance
  path: /api/instance
- description: Get Version Info
  method: GET
  name: get-api-instance-version
  path: /api/instance/version
- description: Setup Instance
  method: POST
  name: post-api-setup
  path: /api/setup
- description: List Jobs
  method: GET
  name: get-api-peers-peerid-jobs
  path: /api/peers/{peerId}/jobs
- description: Create Job
  method: POST
  name: post-api-peers-peerid-jobs
  path: /api/peers/{peerId}/jobs
- description: Get Job
  method: GET
  name: get-api-peers-peerid-jobs-jobid
  path: /api/peers/{peerId}/jobs/{jobId}
- description: List all Accounts
  method: GET
  name: get-api-accounts
  path: /api/accounts
- description: Delete an Account
  method: DELETE
  name: delete-api-accounts-accountid
  path: /api/accounts/{accountId}
- description: Update an Account
  method: PUT
  name: put-api-accounts-accountid
  path: /api/accounts/{accountId}
- description: List all Users
  method: GET
  name: get-api-users
  path: /api/users
- description: Create a User
  method: POST
  name: post-api-users
  path: /api/users
- description: Update a User
  method: PUT
  name: put-api-users-userid
  path: /api/users/{userId}
- description: Delete a User
  method: DELETE
  name: delete-api-users-userid
  path: /api/users/{userId}
- description: List all Tokens
  method: GET
  name: get-api-users-userid-tokens
  path: /api/users/{userId}/tokens
- description: Create a Token
  method: POST
  name: post-api-users-userid-tokens
  path: /api/users/{userId}/tokens
- description: Retrieve a Token
  method: GET
  name: get-api-users-userid-tokens-tokenid
  path: /api/users/{userId}/tokens/{tokenId}
- description: Delete a Token
  method: DELETE
  name: delete-api-users-userid-tokens-tokenid
  path: /api/users/{userId}/tokens/{tokenId}
- description: Resend user invitation
  method: POST
  name: post-api-users-userid-invite
  path: /api/users/{userId}/invite
- description: Approve user
  method: POST
  name: post-api-users-userid-approve
  path: /api/users/{userId}/approve
- description: Reject user
  method: DELETE
  name: delete-api-users-userid-reject
  path: /api/users/{userId}/reject
- description: Change user password
  method: PUT
  name: put-api-users-userid-password
  path: /api/users/{userId}/password
- description: Retrieve current user
  method: GET
  name: get-api-users-current
  path: /api/users/current
- description: List user invites
  method: GET
  name: get-api-users-invites
  path: /api/users/invites
- description: Create a user invite
  method: POST
  name: post-api-users-invites
  path: /api/users/invites
- description: Delete a user invite
  method: DELETE
  name: delete-api-users-invites-inviteid
  path: /api/users/invites/{inviteId}
- description: Regenerate a user invite
  method: POST
  name: post-api-users-invites-inviteid-regenerate
  path: /api/users/invites/{inviteId}/regenerate
- description: Get invite information
  method: GET
  name: get-api-users-invites-token
  path: /api/users/invites/{token}
- description: Accept an invite
  method: POST
  name: post-api-users-invites-token-accept
  path: /api/users/invites/{token}/accept
- description: List all Peers
  method: GET
  name: get-api-peers
  path: /api/peers
- description: Retrieve a Peer
  method: GET
  name: get-api-peers-peerid
  path: /api/peers/{peerId}
- description: Update a Peer
  method: PUT
  name: put-api-peers-peerid
  path: /api/peers/{peerId}
- description: Delete a Peer
  method: DELETE
  name: delete-api-peers-peerid
  path: /api/peers/{peerId}
- description: List accessible Peers
  method: GET
  name: get-api-peers-peerid-accessible-peers
  path: /api/peers/{peerId}/accessible-peers
- description: Create a Temporary Access Peer
  method: POST
  name: post-api-peers-peerid-temporary-access
  path: /api/peers/{peerId}/temporary-access
- description: List all Port Allocations
  method: GET
  name: get-api-peers-peerid-ingress-ports
  path: /api/peers/{peerId}/ingress/ports
- description: Create a Port Allocation
  method: POST
  name: post-api-peers-peerid-ingress-ports
  path: /api/peers/{peerId}/ingress/ports
- description: Retrieve a Port Allocation
  method: GET
  name: get-api-peers-peerid-ingress-ports-allocationid
  path: /api/peers/{peerId}/ingress/ports/{allocationId}
- description: Update a Port Allocation
  method: PUT
  name: put-api-peers-peerid-ingress-ports-allocationid
  path: /api/peers/{peerId}/ingress/ports/{allocationId}
- description: Delete a Port Allocation
  method: DELETE
  name: delete-api-peers-peerid-ingress-ports-allocation
  path: /api/peers/{peerId}/ingress/ports/{allocationId}
- description: List all Ingress Peers
  method: GET
  name: get-api-ingress-peers
  path: /api/ingress/peers
- description: Create a Ingress Peer
  method: POST
  name: post-api-ingress-peers
  path: /api/ingress/peers
- description: Retrieve a Ingress Peer
  method: GET
  name: get-api-ingress-peers-ingresspeerid
  path: /api/ingress/peers/{ingressPeerId}
- description: Update a Ingress Peer
  method: PUT
  name: put-api-ingress-peers-ingresspeerid
  path: /api/ingress/peers/{ingressPeerId}
- description: Delete a Ingress Peer
  method: DELETE
  name: delete-api-ingress-peers-ingresspeerid
  path: /api/ingress/peers/{ingressPeerId}
- description: List all Setup Keys
  method: GET
  name: get-api-setup-keys
  path: /api/setup-keys
- description: Create a Setup Key
  method: POST
  name: post-api-setup-keys
  path: /api/setup-keys
- description: Retrieve a Setup Key
  method: GET
  name: get-api-setup-keys-keyid
  path: /api/setup-keys/{keyId}
- description: Update a Setup Key
  method: PUT
  name: put-api-setup-keys-keyid
  path: /api/setup-keys/{keyId}
- description: Delete a Setup Key
  method: DELETE
  name: delete-api-setup-keys-keyid
  path: /api/setup-keys/{keyId}
- description: List all Groups
  method: GET
  name: get-api-groups
  path: /api/groups
- description: Create a Group
  method: POST
  name: post-api-groups
  path: /api/groups
- description: Retrieve a Group
  method: GET
  name: get-api-groups-groupid
  path: /api/groups/{groupId}
- description: Update a Group
  method: PUT
  name: put-api-groups-groupid
  path: /api/groups/{groupId}
- description: Delete a Group
  method: DELETE
  name: delete-api-groups-groupid
  path: /api/groups/{groupId}
- description: List all Policies
  method: GET
  name: get-api-policies
  path: /api/policies
- description: Create a Policy
  method: POST
  name: post-api-policies
  path: /api/policies
- description: Retrieve a Policy
  method: GET
  name: get-api-policies-policyid
  path: /api/policies/{policyId}
- description: Update a Policy
  method: PUT
  name: put-api-policies-policyid
  path: /api/policies/{policyId}
- description: Delete a Policy
  method: DELETE
  name: delete-api-policies-policyid
  path: /api/policies/{policyId}
- description: List all Routes
  method: GET
  name: get-api-routes
  path: /api/routes
personas: []
provider_name: NetBird
provider_slug: netbird
search_terms:
- delete a token
- list all port allocations
- list all setup keys
- put api groups groupid
- api
- put api peers peerid ingress ports allocationid
- delete a user
- list all tokens
- delete api setup keys keyid
- vpn
- list all users
- delete api groups groupid
- get api users userid tokens tokenid
- delete a ingress peer
- create a user invite
- delete api policies policyid
- get api users invites token
- post api setup keys
- create a group
- create a setup key
- create a policy
- list all peers
- retrieve a port allocation
- list all ingress peers
- put api users userid
- put api peers peerid
- delete api users userid reject
- approve user
- update a user
- post api peers peerid jobs
- put api policies policyid
- setup instance
- delete api peers peerid ingress ports allocation
- post api ingress peers
- create job
- get instance status
- accept an invite
- delete an account
- get job
- create a ingress peer
- wireguard
- get api peers peerid ingress ports allocationid
- post api users invites inviteid regenerate
- update a setup key
- resend user invitation
- regenerate a user invite
- delete api ingress peers ingresspeerid
- retrieve a ingress peer
- retrieve a peer
- list all policies
- reject user
- zero trust
- post api users invites
- get api peers peerid
- delete a policy
- put api ingress peers ingresspeerid
- security
- get api users userid tokens
- create a port allocation
- retrieve current user
- delete api users userid
- networking
- netbird
- delete api users userid tokens tokenid
- get api setup keys keyid
- create a temporary access peer
- list all groups
- post api users userid approve
- get api users invites
- delete a group
- put api accounts accountid
- get api peers peerid ingress ports
- post api users userid invite
- delete api accounts accountid
- delete api peers peerid
- create a token
- change user password
- update a group
- put api setup keys keyid
- get api policies policyid
- list all accounts
- get api users
- get api instance version
- get api groups groupid
- retrieve a setup key
- get api policies
- get api instance
- list user invites
- list jobs
- post api users userid tokens
- retrieve a policy
- create a user
- get api peers peerid accessible peers
- post api setup
- post api users invites token accept
- update a peer
- update a policy
- get version info
- retrieve a group
- get api peers peerid jobs jobid
- post api peers peerid ingress ports
- list all routes
- post api users
- delete a user invite
- list accessible peers
- get api accounts
- get api routes
- update a port allocation
- open source
- get api ingress peers
- put api users userid password
- post api groups
- get api peers
- get api users current
- get api setup keys
- post api policies
- update an account
- get api ingress peers ingresspeerid
- delete a port allocation
- get api groups
- delete api users invites inviteid
- get api peers peerid jobs
- retrieve a token
- get invite information
- delete a peer
- post api peers peerid temporary access
- update a ingress peer
- delete a setup key
slug: netbird-capability
source_filename: netbird-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NetBird REST API\n  description: API to manipulate groups, rules, policies and retrieve information about peers and users\n  tags:\n  - Netbird\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: netbird\n    baseUri: https://api.netbird.io\n    description: NetBird REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NETBIRD_TOKEN}}'\n    resources:\n    - name: api-instance\n      path: /api/instance\n      operations:\n      - name: get-api-instance\n        method: GET\n        description: Get Instance Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-instance-version\n      path: /api/instance/version\n      operations:\n      - name: get-api-instance-version\n        method: GET\n        description: Get Version Info\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-setup\n      path: /api/setup\n      operations:\n      - name: post-api-setup\n        method: POST\n        description: Setup Instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-jobs\n      path: /api/peers/{peerId}/jobs\n      operations:\n      - name: get-api-peers-peerid-jobs\n        method: GET\n        description: List Jobs\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-peers-peerid-jobs\n        method: POST\n        description: Create Job\n        inputParameters:\n \
  \       - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-jobs-jobid\n      path: /api/peers/{peerId}/jobs/{jobId}\n      operations:\n      - name: get-api-peers-peerid-jobs-jobid\n        method: GET\n        description: Get Job\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-accounts\n      path: /api/accounts\n      operations:\n\
  \      - name: get-api-accounts\n        method: GET\n        description: List all Accounts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-accounts-accountid\n      path: /api/accounts/{accountId}\n      operations:\n      - name: delete-api-accounts-accountid\n        method: DELETE\n        description: Delete an Account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-accounts-accountid\n        method: PUT\n        description: Update an Account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier\
  \ of an account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users\n      path: /api/users\n      operations:\n      - name: get-api-users\n        method: GET\n        description: List all Users\n        inputParameters:\n        - name: service_user\n          in: query\n          type: boolean\n          description: Filters users and returns either regular users or service users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-users\n        method: POST\n        description: Create a User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid\n      path: /api/users/{userId}\n      operations:\n      - name: put-api-users-userid\n        method: PUT\n        description: Update a User\n\
  \        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-users-userid\n        method: DELETE\n        description: Delete a User\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-tokens\n      path: /api/users/{userId}/tokens\n      operations:\n      - name: get-api-users-userid-tokens\n        method: GET\n        description: List all Tokens\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n \
  \         required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-users-userid-tokens\n        method: POST\n        description: Create a Token\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-tokens-tokenid\n      path: /api/users/{userId}/tokens/{tokenId}\n      operations:\n      - name: get-api-users-userid-tokens-tokenid\n        method: GET\n        description: Retrieve a Token\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier\
  \ of a user\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-users-userid-tokens-tokenid\n        method: DELETE\n        description: Delete a Token\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        - name: tokenId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-invite\n      path: /api/users/{userId}/invite\n      operations:\n      - name: post-api-users-userid-invite\n\
  \        method: POST\n        description: Resend user invitation\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-approve\n      path: /api/users/{userId}/approve\n      operations:\n      - name: post-api-users-userid-approve\n        method: POST\n        description: Approve user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-reject\n      path: /api/users/{userId}/reject\n      operations:\n      - name: delete-api-users-userid-reject\n\
  \        method: DELETE\n        description: Reject user\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-userid-password\n      path: /api/users/{userId}/password\n      operations:\n      - name: put-api-users-userid-password\n        method: PUT\n        description: Change user password\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-current\n      path: /api/users/current\n      operations:\n      - name: get-api-users-current\n      \
  \  method: GET\n        description: Retrieve current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-invites\n      path: /api/users/invites\n      operations:\n      - name: get-api-users-invites\n        method: GET\n        description: List user invites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-users-invites\n        method: POST\n        description: Create a user invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-invites-inviteid\n      path: /api/users/invites/{inviteId}\n      operations:\n      - name: delete-api-users-invites-inviteid\n        method: DELETE\n        description: Delete a user invite\n        inputParameters:\n        - name: inviteId\n     \
  \     in: path\n          type: string\n          required: true\n          description: The ID of the invite to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-invites-inviteid-regenerate\n      path: /api/users/invites/{inviteId}/regenerate\n      operations:\n      - name: post-api-users-invites-inviteid-regenerate\n        method: POST\n        description: Regenerate a user invite\n        inputParameters:\n        - name: inviteId\n          in: path\n          type: string\n          required: true\n          description: The ID of the invite to regenerate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-invites-token\n      path: /api/users/invites/{token}\n      operations:\n      - name: get-api-users-invites-token\n        method: GET\n        description: Get invite information\n\
  \        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: The invite token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-invites-token-accept\n      path: /api/users/invites/{token}/accept\n      operations:\n      - name: post-api-users-invites-token-accept\n        method: POST\n        description: Accept an invite\n        inputParameters:\n        - name: token\n          in: path\n          type: string\n          required: true\n          description: The invite token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers\n      path: /api/peers\n      operations:\n      - name: get-api-peers\n        method: GET\n        description: List all Peers\n        inputParameters:\n        - name: name\n \
  \         in: query\n          type: string\n          description: Filter peers by name\n        - name: ip\n          in: query\n          type: string\n          description: Filter peers by IP address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid\n      path: /api/peers/{peerId}\n      operations:\n      - name: get-api-peers-peerid\n        method: GET\n        description: Retrieve a Peer\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-peers-peerid\n        method: PUT\n        description: Update a Peer\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n\
  \          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-peers-peerid\n        method: DELETE\n        description: Delete a Peer\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-accessible-peers\n      path: /api/peers/{peerId}/accessible-peers\n      operations:\n      - name: get-api-peers-peerid-accessible-peers\n        method: GET\n        description: List accessible Peers\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique\
  \ identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-temporary-access\n      path: /api/peers/{peerId}/temporary-access\n      operations:\n      - name: post-api-peers-peerid-temporary-access\n        method: POST\n        description: Create a Temporary Access Peer\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-ingress-ports\n      path: /api/peers/{peerId}/ingress/ports\n      operations:\n      - name: get-api-peers-peerid-ingress-ports\n        method: GET\n        description: List all Port Allocations\n        inputParameters:\n        - name: peerId\n          in: path\n \
  \         type: string\n          required: true\n          description: The unique identifier of a peer\n        - name: name\n          in: query\n          type: string\n          description: Filters ingress port allocations by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-peers-peerid-ingress-ports\n        method: POST\n        description: Create a Port Allocation\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-peers-peerid-ingress-ports-allocationid\n      path: /api/peers/{peerId}/ingress/ports/{allocationId}\n      operations:\n      - name: get-api-peers-peerid-ingress-ports-allocationid\n        method:\
  \ GET\n        description: Retrieve a Port Allocation\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        - name: allocationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress port allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-peers-peerid-ingress-ports-allocationid\n        method: PUT\n        description: Update a Port Allocation\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        - name: allocationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress\
  \ port allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-peers-peerid-ingress-ports-allocation\n        method: DELETE\n        description: Delete a Port Allocation\n        inputParameters:\n        - name: peerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a peer\n        - name: allocationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress port allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-ingress-peers\n      path: /api/ingress/peers\n      operations:\n      - name: get-api-ingress-peers\n        method: GET\n        description: List all Ingress Peers\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: post-api-ingress-peers\n        method: POST\n        description: Create a Ingress Peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-ingress-peers-ingresspeerid\n      path: /api/ingress/peers/{ingressPeerId}\n      operations:\n      - name: get-api-ingress-peers-ingresspeerid\n        method: GET\n        description: Retrieve a Ingress Peer\n        inputParameters:\n        - name: ingressPeerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-ingress-peers-ingresspeerid\n        method: PUT\n        description: Update a Ingress Peer\n        inputParameters:\n       \
  \ - name: ingressPeerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-ingress-peers-ingresspeerid\n        method: DELETE\n        description: Delete a Ingress Peer\n        inputParameters:\n        - name: ingressPeerId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of an ingress peer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-setup-keys\n      path: /api/setup-keys\n      operations:\n      - name: get-api-setup-keys\n        method: GET\n        description: List all Setup Keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: post-api-setup-keys\n        method: POST\n        description: Create a Setup Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-setup-keys-keyid\n      path: /api/setup-keys/{keyId}\n      operations:\n      - name: get-api-setup-keys-keyid\n        method: GET\n        description: Retrieve a Setup Key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a setup key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-setup-keys-keyid\n        method: PUT\n        description: Update a Setup Key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n          description: The unique\
  \ identifier of a setup key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-setup-keys-keyid\n        method: DELETE\n        description: Delete a Setup Key\n        inputParameters:\n        - name: keyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a setup key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-groups\n      path: /api/groups\n      operations:\n      - name: get-api-groups\n        method: GET\n        description: List all Groups\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter groups by name (exact match)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: post-api-groups\n        method: POST\n        description: Create a Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-groups-groupid\n      path: /api/groups/{groupId}\n      operations:\n      - name: get-api-groups-groupid\n        method: GET\n        description: Retrieve a Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-groups-groupid\n        method: PUT\n        description: Update a Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a group\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-groups-groupid\n        method: DELETE\n        description: Delete a Group\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-policies\n      path: /api/policies\n      operations:\n      - name: get-api-policies\n        method: GET\n        description: List all Policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-api-policies\n        method: POST\n        description: Create a Policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-policies-policyid\n      path: /api/policies/{policyId}\n      operations:\n      - name: get-api-policies-policyid\n        method: GET\n        description: Retrieve a Policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-api-policies-policyid\n        method: PUT\n        description: Update a Policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-api-policies-policyid\n        method: DELETE\n \
  \       description: Delete a Policy\n        inputParameters:\n        - name: policyId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of a policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-routes\n      path: /api/routes\n      operations:\n      - name: get-api-routes\n        method: GET\n        description: List all Routes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: netbird-rest\n    description: REST adapter for NetBird REST API.\n    resources:\n    - path: /api/instance\n      name: get-api-instance\n      operations:\n      - method: GET\n        name: get-api-instance\n        description: Get Instance Status\n        call: netbird.get-api-instance\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/instance/version\n      name: get-api-instance-version\n      operations:\n      - method: GET\n        name: get-api-instance-version\n        description: Get Version Info\n        call: netbird.get-api-instance-version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/setup\n      name: post-api-setup\n      operations:\n      - method: POST\n        name: post-api-setup\n        description: Setup Instance\n        call: netbird.post-api-setup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/peers/{peerId}/jobs\n      name: get-api-peers-peerid-jobs\n      operations:\n      - method: GET\n        name: get-api-peers-peerid-jobs\n        description: List Jobs\n        call: netbird.get-api-peers-peerid-jobs\n        with:\n          peerId: rest.peerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /api/peers/{peerId}/jobs\n      name: post-api-peers-peerid-jobs\n      operations:\n      - method: POST\n        name: post-api-peers-peerid-jobs\n        description: Create Job\n        call: netbird.post-api-peers-peerid-jobs\n        with:\n          peerId: rest.peerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/peers/{peerId}/jobs/{jobId}\n      name: get-api-peers-peerid-jobs-jobid\n      operations:\n      - method: GET\n        name: get-api-peers-peerid-jobs-jobid\n        description: Get Job\n        call: netbird.get-api-peers-peerid-jobs-jobid\n        with:\n          peerId: rest.peerId\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/accounts\n      name: get-api-accounts\n      operations:\n      - method: GET\n        name: get-api-accounts\n        description: List all Accounts\n        call: netbird.get-api-accounts\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/accounts/{accountId}\n      name: delete-api-accounts-accountid\n      operations:\n      - method: DELETE\n        name: delete-api-accounts-accountid\n        description: Delete an Account\n        call: netbird.delete-api-accounts-accountid\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/accounts/{accountId}\n      name: put-api-accounts-accountid\n      operations:\n      - method: PUT\n        name: put-api-accounts-accountid\n        description: Update an Account\n        call: netbird.put-api-accounts-accountid\n        with:\n          accountId: rest.accountId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users\n      name: get-api-users\n      operations:\n      - method: GET\n        name: get-api-users\n        description: List all Users\n        call: netbird.get-api-users\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users\n      name: post-api-users\n      operations:\n      - method: POST\n        name: post-api-users\n        description: Create a User\n        call: netbird.post-api-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}\n      name: put-api-users-userid\n      operations:\n      - method: PUT\n        name: put-api-users-userid\n        description: Update a User\n        call: netbird.put-api-users-userid\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}\n      name: delete-api-users-userid\n      operations:\n      - method: DELETE\n        name: delete-api-users-userid\n        description: Delete a User\n        call: netbird.delete-api-users-userid\n        with:\n          userId: rest.userId\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /api/users/{userId}/tokens\n      name: get-api-users-userid-tokens\n      operations:\n      - method: GET\n        name: get-api-users-userid-tokens\n        description: List all Tokens\n        call: netbird.get-api-users-userid-tokens\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/tokens\n      name: post-api-users-userid-tokens\n      operations:\n      - method: POST\n        name: post-api-users-userid-tokens\n        description: Create a Token\n        call: netbird.post-api-users-userid-tokens\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/tokens/{tokenId}\n      name: get-api-users-userid-tokens-tokenid\n      operations:\n      - method: GET\n        name: get-api-users-userid-tokens-tokenid\n        description:\
  \ Retrieve a Token\n        call: netbird.get-api-users-userid-tokens-tokenid\n        with:\n          userId: rest.userId\n          tokenId: rest.tokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/tokens/{tokenId}\n      name: delete-api-users-userid-tokens-tokenid\n      operations:\n      - method: DELETE\n        name: delete-api-users-userid-tokens-tokenid\n        description: Delete a Token\n        call: netbird.delete-api-users-userid-tokens-tokenid\n        with:\n          userId: rest.userId\n          tokenId: rest.tokenId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/invite\n      name: post-api-users-userid-invite\n      operations:\n      - method: POST\n        name: post-api-users-userid-invite\n        description: Resend user invitation\n        call: netbird.post-api-users-userid-invite\n        with:\n          userId: rest.userId\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/approve\n      name: post-api-users-userid-approve\n      operations:\n      - method: POST\n        name: post-api-users-userid-approve\n        description: Approve user\n        call: netbird.post-api-users-userid-approve\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/reject\n      name: delete-api-users-userid-reject\n      operations:\n      - method: DELETE\n        name: delete-api-users-userid-reject\n        description: Reject user\n        call: netbird.delete-api-users-userid-reject\n        with:\n          userId: rest.userId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/users/{userId}/p\n\n# --- truncated at 32 KB (71 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/netbird/refs/heads/main/capabilities/netbird-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netbird/refs/heads/main/capabilities/netbird-capability.yaml
tags:
- Netbird
- API
tools:
- description: Get Instance Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-instance
- description: Get Version Info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-instance-version
- description: Setup Instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-setup
- description: List Jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid-jobs
- description: Create Job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-peers-peerid-jobs
- description: Get Job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid-jobs-jobid
- description: List all Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-accounts
- description: Delete an Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-accounts-accountid
- description: Update an Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-accounts-accountid
- description: List all Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users
- description: Create a User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users
- description: Update a User
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-users-userid
- description: Delete a User
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-users-userid
- description: List all Tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users-userid-tokens
- description: Create a Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-userid-tokens
- description: Retrieve a Token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users-userid-tokens-tokenid
- description: Delete a Token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-users-userid-tokens-tokenid
- description: Resend user invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-userid-invite
- description: Approve user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-userid-approve
- description: Reject user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-users-userid-reject
- description: Change user password
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-users-userid-password
- description: Retrieve current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users-current
- description: List user invites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users-invites
- description: Create a user invite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-invites
- description: Delete a user invite
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-users-invites-inviteid
- description: Regenerate a user invite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-invites-inviteid-regenerate
- description: Get invite information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-users-invites-token
- description: Accept an invite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-users-invites-token-accept
- description: List all Peers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers
- description: Retrieve a Peer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid
- description: Update a Peer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-peers-peerid
- description: Delete a Peer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-peers-peerid
- description: List accessible Peers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid-accessible-peers
- description: Create a Temporary Access Peer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-peers-peerid-temporary-access
- description: List all Port Allocations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid-ingress-ports
- description: Create a Port Allocation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-peers-peerid-ingress-ports
- description: Retrieve a Port Allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-peers-peerid-ingress-ports-allocationid
- description: Update a Port Allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-peers-peerid-ingress-ports-allocationid
- description: Delete a Port Allocation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-peers-peerid-ingress-ports-allocation
- description: List all Ingress Peers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-ingress-peers
- description: Create a Ingress Peer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-ingress-peers
- description: Retrieve a Ingress Peer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-ingress-peers-ingresspeerid
- description: Update a Ingress Peer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-ingress-peers-ingresspeerid
- description: Delete a Ingress Peer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-ingress-peers-ingresspeerid
- description: List all Setup Keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-setup-keys
- description: Create a Setup Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-setup-keys
- description: Retrieve a Setup Key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-setup-keys-keyid
- description: Update a Setup Key
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-setup-keys-keyid
- description: Delete a Setup Key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-setup-keys-keyid
- description: List all Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-groups
- description: Create a Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-groups
- description: Retrieve a Group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-groups-groupid
- description: Update a Group
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-groups-groupid
- description: Delete a Group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-groups-groupid
- description: List all Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-policies
- description: Create a Policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-api-policies
- description: Retrieve a Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-policies-policyid
- description: Update a Policy
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-api-policies-policyid
- description: Delete a Policy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-api-policies-policyid
- description: List all Routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-api-routes
---
