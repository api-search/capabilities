---
api_specs:
- filename: xiaomi-open-api-openapi.yml
  format: yaml
  label: xiaomi-open-api
  slug: xiaomi-open-api
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/xiaomi/refs/heads/main/openapi/xiaomi-open-api-openapi.yml
- filename: xiaomi-galaxy-fds-openapi.yml
  format: yaml
  label: xiaomi-galaxy-fds
  slug: xiaomi-galaxy-fds
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/xiaomi/refs/heads/main/openapi/xiaomi-galaxy-fds-openapi.yml
categories: []
consumed_apis:
- xiaomi-open-api
- xiaomi-galaxy-fds
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
- mobile
- delete an object from cloud storage.
- developer platform
- get the authenticated xiaomi user's profile information.
- get object
- get user phone and email
- object storage
- cloud storage
- download object
- get the authenticated xiaomi user's profile.
- authenticated user profile.
- get user phone number and email address.
- get object metadata
- upload object
- get metadata for an object in xiaomi galaxy fds without downloading.
- get user contact
- object storage operations.
- upload a file or object to xiaomi galaxy fds cloud storage.
- consumer electronics
- artificial intelligence
- download a file or object from xiaomi galaxy fds cloud storage.
- delete object
- get the xiaomi user's phone number and email address.
- smart home
- machine learning
- get user profile
- download an object from cloud storage.
- xiaomi
- user contact information.
- put object
- iot
- upload an object to cloud storage.
- identity
- delete an object from xiaomi galaxy fds cloud storage.
slug: cloud-storage
source_filename: cloud-storage.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Xiaomi Cloud Storage\"\n  description: \"Unified capability for Xiaomi cloud storage workflows combining Galaxy FDS object storage with account authentication. Enables developers to authenticate users and manage files in Xiaomi's cloud infrastructure.\"\n  tags:\n    - Xiaomi\n    - Cloud Storage\n    - Object Storage\n    - Identity\n    - Developer Platform\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      XIAOMI_ACCESS_TOKEN: XIAOMI_ACCESS_TOKEN\n      XIAOMI_CLIENT_ID: XIAOMI_CLIENT_ID\n      XIAOMI_FDS_ACCESS_KEY: XIAOMI_FDS_ACCESS_KEY\n      XIAOMI_FDS_SECRET_KEY: XIAOMI_FDS_SECRET_KEY\n\ncapability:\n  consumes:\n    - import: xiaomi-open-api\n      location: ./shared/xiaomi-open-api.yaml\n    - import: xiaomi-galaxy-fds\n      location: ./shared/xiaomi-galaxy-fds.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: xiaomi-cloud-storage-api\n      description:\
  \ \"Unified REST API for Xiaomi cloud storage operations with user authentication.\"\n      resources:\n        - path: /v1/user/profile\n          name: user-profile\n          description: \"Authenticated user profile.\"\n          operations:\n            - method: GET\n              name: get-user-profile\n              description: \"Get the authenticated Xiaomi user's profile.\"\n              call: \"xiaomi-open-api.get-user-profile\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/user/contact\n          name: user-contact\n          description: \"User contact information.\"\n          operations:\n            - method: GET\n              name: get-user-phone-and-email\n              description: \"Get user phone number and email address.\"\n              call: \"xiaomi-open-api.get-user-phone-and-email\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n        - path: /v1/storage/objects/{bucketName}/{objectName}\n          name: storage-objects\n          description: \"Object storage operations.\"\n          operations:\n            - method: PUT\n              name: put-object\n              description: \"Upload an object to cloud storage.\"\n              call: \"xiaomi-galaxy-fds.put-object\"\n              with:\n                bucketName: \"rest.bucketName\"\n                objectName: \"rest.objectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-object\n              description: \"Download an object from cloud storage.\"\n              call: \"xiaomi-galaxy-fds.get-object\"\n              with:\n                bucketName: \"rest.bucketName\"\n                objectName: \"rest.objectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method:\
  \ DELETE\n              name: delete-object\n              description: \"Delete an object from cloud storage.\"\n              call: \"xiaomi-galaxy-fds.delete-object\"\n              with:\n                bucketName: \"rest.bucketName\"\n                objectName: \"rest.objectName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: xiaomi-cloud-storage-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Xiaomi cloud storage management.\"\n      tools:\n        - name: get-user-profile\n          description: \"Get the authenticated Xiaomi user's profile information.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"xiaomi-open-api.get-user-profile\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-user-contact\n          description: \"Get the Xiaomi\
  \ user's phone number and email address.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"xiaomi-open-api.get-user-phone-and-email\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upload-object\n          description: \"Upload a file or object to Xiaomi Galaxy FDS cloud storage.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"xiaomi-galaxy-fds.put-object\"\n          with:\n            bucketName: \"tools.bucketName\"\n            objectName: \"tools.objectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-object\n          description: \"Download a file or object from Xiaomi Galaxy FDS cloud storage.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"xiaomi-galaxy-fds.get-object\"\n\
  \          with:\n            bucketName: \"tools.bucketName\"\n            objectName: \"tools.objectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-object-metadata\n          description: \"Get metadata for an object in Xiaomi Galaxy FDS without downloading.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"xiaomi-galaxy-fds.head-object\"\n          with:\n            bucketName: \"tools.bucketName\"\n            objectName: \"tools.objectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-object\n          description: \"Delete an object from Xiaomi Galaxy FDS cloud storage.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"xiaomi-galaxy-fds.delete-object\"\n          with:\n            bucketName: \"tools.bucketName\"\n \
  \           objectName: \"tools.objectName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
