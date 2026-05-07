---
categories: []
consumed_apis: []
description: Unified capability for Xiaomi cloud storage workflows combining Galaxy FDS object storage with account authentication. Enables developers to authenticate users and manage files in Xiaomi's cloud infrastructure.
layout: capability
name: Xiaomi Cloud Storage
operations:
- description: Get the authenticated Xiaomi user's profile.
  method: GET
  name: get-user-profile
  path: /v1/user/profile
- description: Get user phone number and email address.
  method: GET
  name: get-user-phone-and-email
  path: /v1/user/contact
- description: Upload an object to cloud storage.
  method: PUT
  name: put-object
  path: /v1/storage/objects/{bucketName}/{objectName}
- description: Download an object from cloud storage.
  method: GET
  name: get-object
  path: /v1/storage/objects/{bucketName}/{objectName}
- description: Delete an object from cloud storage.
  method: DELETE
  name: delete-object
  path: /v1/storage/objects/{bucketName}/{objectName}
personas: []
provider_name: Xiaomi
provider_slug: xiaomi
search_terms:
- authenticated user profile.
- get metadata for an object in xiaomi galaxy fds without downloading.
- delete object
- get the xiaomi user's phone number and email address.
- download an object from cloud storage.
- get object
- object storage operations.
- mobile
- cloud storage
- artificial intelligence
- get the authenticated xiaomi user's profile.
- get object metadata
- get user profile
- identity
- upload a file or object to xiaomi galaxy fds cloud storage.
- download a file or object from xiaomi galaxy fds cloud storage.
- machine learning
- get the authenticated xiaomi user's profile information.
- object storage
- iot
- smart home
- consumer electronics
- get user phone and email
- get user contact
- upload object
- user contact information.
- developer platform
- get user phone number and email address.
- put object
- upload an object to cloud storage.
- delete an object from cloud storage.
- download object
- xiaomi
- delete an object from xiaomi galaxy fds cloud storage.
slug: cloud-storage
source_filename: cloud-storage.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Xiaomi Cloud Storage\n  description: Unified capability for Xiaomi cloud storage workflows combining Galaxy FDS object storage with account authentication.\n    Enables developers to authenticate users and manage files in Xiaomi's cloud infrastructure.\n  tags:\n  - Xiaomi\n  - Cloud Storage\n  - Object Storage\n  - Identity\n  - Developer Platform\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    XIAOMI_ACCESS_TOKEN: XIAOMI_ACCESS_TOKEN\n    XIAOMI_CLIENT_ID: XIAOMI_CLIENT_ID\n    XIAOMI_FDS_ACCESS_KEY: XIAOMI_FDS_ACCESS_KEY\n    XIAOMI_FDS_SECRET_KEY: XIAOMI_FDS_SECRET_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: xiaomi-open-api\n    baseUri: https://open.account.xiaomi.com\n    description: Xiaomi OAuth 2.0 user account API.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{XIAOMI_ACCESS_TOKEN}}\n      placement: header\n    resources:\n\
  \    - name: user-profile\n      path: /user/profile\n      description: User profile information.\n      operations:\n      - name: get-user-profile\n        method: GET\n        description: Retrieves the authenticated user's profile including nickname, ID, and avatar.\n        inputParameters:\n        - name: clientId\n          in: query\n          type: integer\n          required: true\n          description: The allocated application client ID.\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: The OAuth 2.0 access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-openid\n      path: /user/openidV2\n      description: User unique OpenID.\n      operations:\n      - name: get-user-open-id\n        method: GET\n        description: Retrieves the authenticated user's unique OpenID.\n        inputParameters:\n     \
  \   - name: clientId\n          in: query\n          type: integer\n          required: true\n          description: Application client ID.\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: OAuth 2.0 access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-contact\n      path: /user/phoneAndEmail\n      description: User phone and email contact information.\n      operations:\n      - name: get-user-phone-and-email\n        method: GET\n        description: Retrieves the user's phone number and email address.\n        inputParameters:\n        - name: clientId\n          in: query\n          type: integer\n          required: true\n          description: Application client ID.\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: OAuth 2.0 access token.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-friends\n      path: /user/relation\n      description: User MiChat friend list.\n      operations:\n      - name: get-user-friend-list\n        method: GET\n        description: Retrieves the user's MiChat friend list.\n        inputParameters:\n        - name: clientId\n          in: query\n          type: integer\n          required: true\n          description: Application client ID.\n        - name: token\n          in: query\n          type: string\n          required: true\n          description: OAuth 2.0 access token.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: xiaomi-galaxy-fds\n    baseUri: https://cnbj0.fds.api.xiaomi.com\n    description: Xiaomi Galaxy FDS object storage REST API.\n    authentication:\n      type: apikey\n\
  \      key: Authorization\n      value: Galaxy {{XIAOMI_FDS_ACCESS_KEY}}:{{XIAOMI_FDS_SECRET_KEY}}\n      placement: header\n    resources:\n    - name: objects\n      path: /{bucketName}/{objectName}\n      description: Object operations.\n      operations:\n      - name: put-object\n        method: PUT\n        description: Uploads an object to the specified bucket.\n        inputParameters:\n        - name: bucketName\n          in: path\n          type: string\n          required: true\n          description: Target bucket name.\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Object key/name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-object\n        method: GET\n        description: Retrieves an object from the specified bucket.\n        inputParameters:\n        - name: bucketName\n          in: path\n   \
  \       type: string\n          required: true\n          description: Bucket name.\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Object key/name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: head-object\n        method: HEAD\n        description: Retrieves object metadata without the body.\n        inputParameters:\n        - name: bucketName\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Object key/name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-object\n        method: DELETE\n        description: Deletes the specified object from\
  \ the bucket.\n        inputParameters:\n        - name: bucketName\n          in: path\n          type: string\n          required: true\n          description: Bucket name.\n        - name: objectName\n          in: path\n          type: string\n          required: true\n          description: Object key/name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: xiaomi-cloud-storage-api\n    description: Unified REST API for Xiaomi cloud storage operations with user authentication.\n    resources:\n    - path: /v1/user/profile\n      name: user-profile\n      description: Authenticated user profile.\n      operations:\n      - method: GET\n        name: get-user-profile\n        description: Get the authenticated Xiaomi user's profile.\n        call: xiaomi-open-api.get-user-profile\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/user/contact\n      name: user-contact\n      description: User contact information.\n      operations:\n      - method: GET\n        name: get-user-phone-and-email\n        description: Get user phone number and email address.\n        call: xiaomi-open-api.get-user-phone-and-email\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/storage/objects/{bucketName}/{objectName}\n      name: storage-objects\n      description: Object storage operations.\n      operations:\n      - method: PUT\n        name: put-object\n        description: Upload an object to cloud storage.\n        call: xiaomi-galaxy-fds.put-object\n        with:\n          bucketName: rest.bucketName\n          objectName: rest.objectName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-object\n        description: Download an object from cloud storage.\n        call: xiaomi-galaxy-fds.get-object\n\
  \        with:\n          bucketName: rest.bucketName\n          objectName: rest.objectName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-object\n        description: Delete an object from cloud storage.\n        call: xiaomi-galaxy-fds.delete-object\n        with:\n          bucketName: rest.bucketName\n          objectName: rest.objectName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: xiaomi-cloud-storage-mcp\n    transport: http\n    description: MCP server for AI-assisted Xiaomi cloud storage management.\n    tools:\n    - name: get-user-profile\n      description: Get the authenticated Xiaomi user's profile information.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xiaomi-open-api.get-user-profile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-user-contact\n      description:\
  \ Get the Xiaomi user's phone number and email address.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xiaomi-open-api.get-user-phone-and-email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-object\n      description: Upload a file or object to Xiaomi Galaxy FDS cloud storage.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: xiaomi-galaxy-fds.put-object\n      with:\n        bucketName: tools.bucketName\n        objectName: tools.objectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: download-object\n      description: Download a file or object from Xiaomi Galaxy FDS cloud storage.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xiaomi-galaxy-fds.get-object\n      with:\n        bucketName: tools.bucketName\n        objectName: tools.objectName\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: get-object-metadata\n      description: Get metadata for an object in Xiaomi Galaxy FDS without downloading.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: xiaomi-galaxy-fds.head-object\n      with:\n        bucketName: tools.bucketName\n        objectName: tools.objectName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-object\n      description: Delete an object from Xiaomi Galaxy FDS cloud storage.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: xiaomi-galaxy-fds.delete-object\n      with:\n        bucketName: tools.bucketName\n        objectName: tools.objectName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/xiaomi/refs/heads/main/capabilities/cloud-storage.yaml
tags:
- Xiaomi
- Cloud Storage
- Object Storage
- Identity
- Developer Platform
tools:
- description: Get the authenticated Xiaomi user's profile information.
  hints:
    openWorld: false
    readOnly: true
  name: get-user-profile
- description: Get the Xiaomi user's phone number and email address.
  hints:
    openWorld: false
    readOnly: true
  name: get-user-contact
- description: Upload a file or object to Xiaomi Galaxy FDS cloud storage.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upload-object
- description: Download a file or object from Xiaomi Galaxy FDS cloud storage.
  hints:
    openWorld: false
    readOnly: true
  name: download-object
- description: Get metadata for an object in Xiaomi Galaxy FDS without downloading.
  hints:
    openWorld: false
    readOnly: true
  name: get-object-metadata
- description: Delete an object from Xiaomi Galaxy FDS cloud storage.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-object
---
