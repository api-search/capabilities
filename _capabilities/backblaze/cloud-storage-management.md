---
categories:
- object-storage
consumed_apis:
- b2-native-api
description: Unified cloud storage management workflow combining bucket administration, file lifecycle, large file upload, application key management, and event notification configuration. Serves developers, DevOps engineers, and application integrators building on Backblaze B2.
layout: capability
name: Backblaze B2 Cloud Storage Management
operations:
- description: Authorize account and obtain API token
  method: GET
  name: authorize-account
  path: /v1/authorize
- description: List all B2 buckets in the account
  method: GET
  name: list-buckets
  path: /v1/buckets
- description: Create a new B2 bucket
  method: POST
  name: create-bucket
  path: /v1/buckets
- description: Update bucket type, CORS, or lifecycle settings
  method: PUT
  name: update-bucket
  path: /v1/buckets/{bucket_id}
- description: Delete an empty bucket
  method: DELETE
  name: delete-bucket
  path: /v1/buckets/{bucket_id}
- description: List file names in a bucket
  method: GET
  name: list-file-names
  path: /v1/buckets/{bucket_id}/files
- description: List all versions of all files in a bucket
  method: GET
  name: list-file-versions
  path: /v1/buckets/{bucket_id}/file-versions
- description: Get notification rules for a bucket
  method: GET
  name: get-bucket-notification-rules
  path: /v1/buckets/{bucket_id}/notifications
- description: Set event notification rules for a bucket
  method: PUT
  name: set-bucket-notification-rules
  path: /v1/buckets/{bucket_id}/notifications
- description: Get file metadata
  method: GET
  name: get-file-info
  path: /v1/files/{file_id}
- description: Delete a specific file version
  method: DELETE
  name: delete-file-version
  path: /v1/files/{file_id}
- description: Get a URL to upload a file to a bucket
  method: POST
  name: get-upload-url
  path: /v1/files/upload-url
- description: Copy a file to a new name or bucket
  method: POST
  name: copy-file
  path: /v1/files/copy
- description: Hide a file from name-based downloads
  method: POST
  name: hide-file
  path: /v1/files/hide
- description: Start a multi-part large file upload
  method: POST
  name: start-large-file
  path: /v1/large-files
- description: List in-progress large file uploads
  method: GET
  name: list-unfinished-large-files
  path: /v1/large-files
- description: List uploaded parts for a large file
  method: GET
  name: list-parts
  path: /v1/large-files/{file_id}/parts
- description: Assemble parts into a complete file
  method: POST
  name: finish-large-file
  path: /v1/large-files/{file_id}/finish
- description: Cancel a large file upload and remove all parts
  method: POST
  name: cancel-large-file
  path: /v1/large-files/{file_id}/cancel
- description: List all application keys
  method: GET
  name: list-keys
  path: /v1/keys
- description: Create a new scoped application key
  method: POST
  name: create-key
  path: /v1/keys
- description: Delete an application key
  method: DELETE
  name: delete-key
  path: /v1/keys/{key_id}
- description: Get a time-limited token for downloading private files
  method: POST
  name: get-download-authorization
  path: /v1/download-authorization
personas: []
provider_name: Backblaze
provider_slug: backblaze
search_terms:
- webhook-based event notifications for real-time storage event processing
- delete an empty bucket
- create a new application key with specific capabilities and optional bucket/prefix restrictions
- storage management
- hide file
- create key
- file upload url generation
- create a new b2 bucket with specified privacy type
- copy a file to a new name or bucket
- get a time-limited token for downloading private files
- initiate a multi-part upload for files larger than 5gb
- list large file uploads that have been started but not yet completed or cancelled
- update bucket settings including type, cors rules, and lifecycle rules
- file version listing
- get file info
- create a new b2 bucket
- assemble parts into a complete file
- update bucket
- hide a file from name-based downloads
- bucket management
- complete a large file upload
- finish large file
- backup
- list all application keys
- DevOps Engineer
- delete key
- delete a specific file version
- set event notification rules for a bucket
- unified workflow for bucket administration, file lifecycle, large file uploads, key management, and event notifications
- get file metadata
- list all application keys for the account
- cancel large file
- cancel a large file upload
- application key management
- create a new scoped application key
- cancel a large file upload and permanently delete all uploaded parts
- download authorization token generation
- permanently delete an application key
- cloud storage
- list file names in a bucket
- assemble all uploaded parts into a complete large file
- file listing and management within a bucket
- list current file names in a bucket with optional prefix filtering and pagination
- list the parts uploaded so far for an in-progress large file upload
- list parts
- list keys
- copy file
- delete an empty b2 bucket permanently
- application developer building on b2 for file storage and delivery
- get a url for uploading one part of an in-progress large file upload
- file hiding operations
- authorize account and obtain api token
- get a url to upload a file to a bucket
- authorize account
- get download authorization
- list all b2 buckets associated with the account
- object storage
- large file part management
- get metadata about a specific file version including size, checksums, and custom info
- get the event notification rules configured for a bucket
- create bucket
- list all b2 buckets in the account
- set or replace all event notification webhook rules for a bucket
- integration specialist connecting third-party tools (backup, cdn, media) to b2
- list buckets
- delete bucket
- single key management
- get notification rules for a bucket
- account authorization
- Application Integrator
- set bucket notification rules
- list file names
- list unfinished large files
- Developer
- storage
- permanently delete a specific version of a file
- cancel a large file upload and remove all parts
- update bucket type, cors, or lifecycle settings
- single file operations
- copy a file to create a new version with a different name or in another bucket
- list file versions
- hide a file so it cannot be found by name (soft delete for versioned buckets)
- log in to the backblaze b2 api and obtain an authorization token for subsequent calls
- list all versions of all files in a bucket
- multi-part large file upload management
- operations engineer managing b2 buckets, lifecycle rules, and application keys as infrastructure
- start a multi-part large file upload
- get upload part url
- get a url and token for uploading a file to a specific bucket
- application key management for scoped, least-privilege api access
- delete an application key
- single bucket operations
- bucket event notification rules
- list in-progress large file uploads
- start large file
- get upload url
- file copy operations
- get bucket notification rules
- list uploaded parts for a large file
- generate a time-limited authorization token for downloading private files
- object storage for application data, media, and backups
- backblaze
- delete file version
slug: cloud-storage-management
source_filename: cloud-storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Backblaze B2 Cloud Storage Management\"\n  description: >-\n    Unified cloud storage management workflow combining bucket administration, file lifecycle,\n    large file upload, application key management, and event notification configuration.\n    Serves developers, DevOps engineers, and application integrators building on Backblaze B2.\n  tags:\n    - Backblaze\n    - Cloud Storage\n    - Object Storage\n    - Storage Management\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      B2_APPLICATION_KEY_ID: B2_APPLICATION_KEY_ID\n      B2_APPLICATION_KEY: B2_APPLICATION_KEY\n\ncapability:\n  consumes:\n    - import: b2-native-api\n      location: ./shared/b2-native-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: backblaze-storage-api\n      description: \"Unified REST API for Backblaze B2 Cloud Storage management.\"\n      resources:\n        - path:\
  \ /v1/authorize\n          name: authorization\n          description: Account authorization\n          operations:\n            - method: GET\n              name: authorize-account\n              description: Authorize account and obtain API token\n              call: \"b2-native-api.authorize-account\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buckets\n          name: buckets\n          description: Bucket management\n          operations:\n            - method: GET\n              name: list-buckets\n              description: List all B2 buckets in the account\n              call: \"b2-native-api.list-buckets\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-bucket\n              description: Create a new B2 bucket\n           \
  \   call: \"b2-native-api.create-bucket\"\n              with:\n                account_id: \"rest.account_id\"\n                bucket_name: \"rest.bucket_name\"\n                bucket_type: \"rest.bucket_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buckets/{bucket_id}\n          name: bucket\n          description: Single bucket operations\n          operations:\n            - method: PUT\n              name: update-bucket\n              description: Update bucket type, CORS, or lifecycle settings\n              call: \"b2-native-api.update-bucket\"\n              with:\n                account_id: \"rest.account_id\"\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-bucket\n              description: Delete an empty bucket\n              call: \"\
  b2-native-api.delete-bucket\"\n              with:\n                account_id: \"rest.account_id\"\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buckets/{bucket_id}/files\n          name: files\n          description: File listing and management within a bucket\n          operations:\n            - method: GET\n              name: list-file-names\n              description: List file names in a bucket\n              call: \"b2-native-api.list-file-names\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buckets/{bucket_id}/file-versions\n          name: file-versions\n          description: File version listing\n          operations:\n            - method: GET\n              name: list-file-versions\n              description:\
  \ List all versions of all files in a bucket\n              call: \"b2-native-api.list-file-versions\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/buckets/{bucket_id}/notifications\n          name: notifications\n          description: Bucket event notification rules\n          operations:\n            - method: GET\n              name: get-bucket-notification-rules\n              description: Get notification rules for a bucket\n              call: \"b2-native-api.get-bucket-notification-rules\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: set-bucket-notification-rules\n              description: Set event notification rules for a bucket\n              call: \"b2-native-api.set-bucket-notification-rules\"\
  \n              with:\n                bucket_id: \"rest.bucket_id\"\n                rules: \"rest.rules\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/{file_id}\n          name: file\n          description: Single file operations\n          operations:\n            - method: GET\n              name: get-file-info\n              description: Get file metadata\n              call: \"b2-native-api.get-file-info\"\n              with:\n                file_id: \"rest.file_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-file-version\n              description: Delete a specific file version\n              call: \"b2-native-api.delete-file-version\"\n              with:\n                file_id: \"rest.file_id\"\n                file_name: \"rest.file_name\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/upload-url\n          name: upload-url\n          description: File upload URL generation\n          operations:\n            - method: POST\n              name: get-upload-url\n              description: Get a URL to upload a file to a bucket\n              call: \"b2-native-api.get-upload-url\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/copy\n          name: file-copy\n          description: File copy operations\n          operations:\n            - method: POST\n              name: copy-file\n              description: Copy a file to a new name or bucket\n              call: \"b2-native-api.copy-file\"\n              with:\n                source_file_id: \"rest.source_file_id\"\n                file_name: \"rest.file_name\"\n           \
  \   outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/hide\n          name: file-hide\n          description: File hiding operations\n          operations:\n            - method: POST\n              name: hide-file\n              description: Hide a file from name-based downloads\n              call: \"b2-native-api.hide-file\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n                file_name: \"rest.file_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/large-files\n          name: large-files\n          description: Multi-part large file upload management\n          operations:\n            - method: POST\n              name: start-large-file\n              description: Start a multi-part large file upload\n              call: \"b2-native-api.start-large-file\"\n              with:\n                bucket_id: \"rest.bucket_id\"\
  \n                file_name: \"rest.file_name\"\n                content_type: \"rest.content_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: list-unfinished-large-files\n              description: List in-progress large file uploads\n              call: \"b2-native-api.list-unfinished-large-files\"\n              with:\n                bucket_id: \"rest.bucket_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/large-files/{file_id}/parts\n          name: large-file-parts\n          description: Large file part management\n          operations:\n            - method: GET\n              name: list-parts\n              description: List uploaded parts for a large file\n              call: \"b2-native-api.list-parts\"\n              with:\n                file_id: \"rest.file_id\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/large-files/{file_id}/finish\n          name: large-file-finish\n          description: Complete a large file upload\n          operations:\n            - method: POST\n              name: finish-large-file\n              description: Assemble parts into a complete file\n              call: \"b2-native-api.finish-large-file\"\n              with:\n                file_id: \"rest.file_id\"\n                part_sha1_array: \"rest.part_sha1_array\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/large-files/{file_id}/cancel\n          name: large-file-cancel\n          description: Cancel a large file upload\n          operations:\n            - method: POST\n              name: cancel-large-file\n              description: Cancel a large file upload and remove all parts\n              call: \"b2-native-api.cancel-large-file\"\
  \n              with:\n                file_id: \"rest.file_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys\n          name: application-keys\n          description: Application key management\n          operations:\n            - method: GET\n              name: list-keys\n              description: List all application keys\n              call: \"b2-native-api.list-keys\"\n              with:\n                account_id: \"rest.account_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-key\n              description: Create a new scoped application key\n              call: \"b2-native-api.create-key\"\n              with:\n                account_id: \"rest.account_id\"\n                capabilities: \"rest.capabilities\"\n                key_name: \"rest.key_name\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/keys/{key_id}\n          name: application-key\n          description: Single key management\n          operations:\n            - method: DELETE\n              name: delete-key\n              description: Delete an application key\n              call: \"b2-native-api.delete-key\"\n              with:\n                application_key_id: \"rest.key_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/download-authorization\n          name: download-authorization\n          description: Download authorization token generation\n          operations:\n            - method: POST\n              name: get-download-authorization\n              description: Get a time-limited token for downloading private files\n              call: \"b2-native-api.get-download-authorization\"\n              with:\n                bucket_id: \"rest.bucket_id\"\
  \n                file_name_prefix: \"rest.file_name_prefix\"\n                valid_duration_in_seconds: \"rest.valid_duration_in_seconds\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: backblaze-storage-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Backblaze B2 Cloud Storage management.\"\n      tools:\n        - name: authorize-account\n          description: Log in to the Backblaze B2 API and obtain an authorization token for subsequent calls\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.authorize-account\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-buckets\n          description: List all B2 buckets associated with the account\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"b2-native-api.list-buckets\"\n          with:\n            account_id: \"tools.account_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-bucket\n          description: Create a new B2 bucket with specified privacy type\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"b2-native-api.create-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_name: \"tools.bucket_name\"\n            bucket_type: \"tools.bucket_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-bucket\n          description: Update bucket settings including type, CORS rules, and lifecycle rules\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"b2-native-api.update-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_id:\
  \ \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-bucket\n          description: Delete an empty B2 bucket permanently\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"b2-native-api.delete-bucket\"\n          with:\n            account_id: \"tools.account_id\"\n            bucket_id: \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-file-names\n          description: List current file names in a bucket with optional prefix filtering and pagination\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.list-file-names\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            max_file_count: \"tools.max_file_count\"\n            prefix: \"tools.prefix\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: list-file-versions\n          description: List all versions of all files in a bucket\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.list-file-versions\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-file-info\n          description: Get metadata about a specific file version including size, checksums, and custom info\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.get-file-info\"\n          with:\n            file_id: \"tools.file_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-upload-url\n          description: Get a URL and token for uploading a file to a specific bucket\n          hints:\n    \
  \        readOnly: true\n            openWorld: false\n          call: \"b2-native-api.get-upload-url\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-file-version\n          description: Permanently delete a specific version of a file\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"b2-native-api.delete-file-version\"\n          with:\n            file_name: \"tools.file_name\"\n            file_id: \"tools.file_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: copy-file\n          description: Copy a file to create a new version with a different name or in another bucket\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"b2-native-api.copy-file\"\n          with:\n           \
  \ source_file_id: \"tools.source_file_id\"\n            file_name: \"tools.file_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: hide-file\n          description: Hide a file so it cannot be found by name (soft delete for versioned buckets)\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"b2-native-api.hide-file\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            file_name: \"tools.file_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-large-file\n          description: Initiate a multi-part upload for files larger than 5GB\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"b2-native-api.start-large-file\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            file_name: \"tools.file_name\"\n            content_type: \"\
  tools.content_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-upload-part-url\n          description: Get a URL for uploading one part of an in-progress large file upload\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.get-upload-part-url\"\n          with:\n            file_id: \"tools.file_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: finish-large-file\n          description: Assemble all uploaded parts into a complete large file\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"b2-native-api.finish-large-file\"\n          with:\n            file_id: \"tools.file_id\"\n            part_sha1_array: \"tools.part_sha1_array\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: cancel-large-file\n\
  \          description: Cancel a large file upload and permanently delete all uploaded parts\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"b2-native-api.cancel-large-file\"\n          with:\n            file_id: \"tools.file_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-parts\n          description: List the parts uploaded so far for an in-progress large file upload\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.list-parts\"\n          with:\n            file_id: \"tools.file_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-unfinished-large-files\n          description: List large file uploads that have been started but not yet completed or cancelled\n          hints:\n            readOnly: true\n            openWorld: false\n          call:\
  \ \"b2-native-api.list-unfinished-large-files\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-key\n          description: Create a new application key with specific capabilities and optional bucket/prefix restrictions\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"b2-native-api.create-key\"\n          with:\n            account_id: \"tools.account_id\"\n            capabilities: \"tools.capabilities\"\n            key_name: \"tools.key_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-keys\n          description: List all application keys for the account\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.list-keys\"\n          with:\n            account_id: \"tools.account_id\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-key\n          description: Permanently delete an application key\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"b2-native-api.delete-key\"\n          with:\n            application_key_id: \"tools.application_key_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-download-authorization\n          description: Generate a time-limited authorization token for downloading private files\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.get-download-authorization\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            file_name_prefix: \"tools.file_name_prefix\"\n            valid_duration_in_seconds: \"tools.valid_duration_in_seconds\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-bucket-notification-rules\n          description: Get the event notification rules configured for a bucket\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"b2-native-api.get-bucket-notification-rules\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: set-bucket-notification-rules\n          description: Set or replace all event notification webhook rules for a bucket\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"b2-native-api.set-bucket-notification-rules\"\n          with:\n            bucket_id: \"tools.bucket_id\"\n            rules: \"tools.rules\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/backblaze/refs/heads/main/capabilities/cloud-storage-management.yaml
tags:
- Backblaze
- Cloud Storage
- Object Storage
- Storage Management
tools:
- description: Log in to the Backblaze B2 API and obtain an authorization token for subsequent calls
  hints:
    openWorld: false
    readOnly: true
  name: authorize-account
- description: List all B2 buckets associated with the account
  hints:
    openWorld: false
    readOnly: true
  name: list-buckets
- description: Create a new B2 bucket with specified privacy type
  hints:
    openWorld: false
    readOnly: false
  name: create-bucket
- description: Update bucket settings including type, CORS rules, and lifecycle rules
  hints:
    idempotent: true
    readOnly: false
  name: update-bucket
- description: Delete an empty B2 bucket permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-bucket
- description: List current file names in a bucket with optional prefix filtering and pagination
  hints:
    openWorld: false
    readOnly: true
  name: list-file-names
- description: List all versions of all files in a bucket
  hints:
    openWorld: false
    readOnly: true
  name: list-file-versions
- description: Get metadata about a specific file version including size, checksums, and custom info
  hints:
    openWorld: false
    readOnly: true
  name: get-file-info
- description: Get a URL and token for uploading a file to a specific bucket
  hints:
    openWorld: false
    readOnly: true
  name: get-upload-url
- description: Permanently delete a specific version of a file
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-file-version
- description: Copy a file to create a new version with a different name or in another bucket
  hints:
    openWorld: false
    readOnly: false
  name: copy-file
- description: Hide a file so it cannot be found by name (soft delete for versioned buckets)
  hints:
    destructive: false
    readOnly: false
  name: hide-file
- description: Initiate a multi-part upload for files larger than 5GB
  hints:
    openWorld: false
    readOnly: false
  name: start-large-file
- description: Get a URL for uploading one part of an in-progress large file upload
  hints:
    openWorld: false
    readOnly: true
  name: get-upload-part-url
- description: Assemble all uploaded parts into a complete large file
  hints:
    openWorld: false
    readOnly: false
  name: finish-large-file
- description: Cancel a large file upload and permanently delete all uploaded parts
  hints:
    destructive: true
    readOnly: false
  name: cancel-large-file
- description: List the parts uploaded so far for an in-progress large file upload
  hints:
    openWorld: false
    readOnly: true
  name: list-parts
- description: List large file uploads that have been started but not yet completed or cancelled
  hints:
    openWorld: false
    readOnly: true
  name: list-unfinished-large-files
- description: Create a new application key with specific capabilities and optional bucket/prefix restrictions
  hints:
    openWorld: false
    readOnly: false
  name: create-key
- description: List all application keys for the account
  hints:
    openWorld: false
    readOnly: true
  name: list-keys
- description: Permanently delete an application key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-key
- description: Generate a time-limited authorization token for downloading private files
  hints:
    openWorld: false
    readOnly: true
  name: get-download-authorization
- description: Get the event notification rules configured for a bucket
  hints:
    openWorld: false
    readOnly: true
  name: get-bucket-notification-rules
- description: Set or replace all event notification webhook rules for a bucket
  hints:
    idempotent: true
    readOnly: false
  name: set-bucket-notification-rules
---
