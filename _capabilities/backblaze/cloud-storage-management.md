---
categories:
- object-storage
consumed_apis: []
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
- list all versions of all files in a bucket
- create a new b2 bucket
- DevOps Engineer
- cancel a large file upload
- file listing and management within a bucket
- get a url to upload a file to a bucket
- copy a file to create a new version with a different name or in another bucket
- application key management for scoped, least-privilege api access
- get a time-limited token for downloading private files
- list file names
- webhook-based event notifications for real-time storage event processing
- authorize account and obtain api token
- integration specialist connecting third-party tools (backup, cdn, media) to b2
- copy a file to a new name or bucket
- create bucket
- application key management
- hide a file from name-based downloads
- hide file
- delete key
- permanently delete an application key
- get the event notification rules configured for a bucket
- start a multi-part large file upload
- delete an empty b2 bucket permanently
- large file part management
- bucket event notification rules
- cancel large file
- delete an empty bucket
- get notification rules for a bucket
- list uploaded parts for a large file
- file version listing
- update bucket settings including type, cors rules, and lifecycle rules
- cancel a large file upload and remove all parts
- get download authorization
- get file metadata
- cloud storage
- set bucket notification rules
- list parts
- operations engineer managing b2 buckets, lifecycle rules, and application keys as infrastructure
- backup
- single key management
- object storage
- assemble all uploaded parts into a complete large file
- create a new application key with specific capabilities and optional bucket/prefix restrictions
- Application Integrator
- single file operations
- get a url and token for uploading a file to a specific bucket
- storage
- start large file
- list all b2 buckets in the account
- delete an application key
- generate a time-limited authorization token for downloading private files
- create a new scoped application key
- permanently delete a specific version of a file
- file hiding operations
- multi-part large file upload management
- log in to the backblaze b2 api and obtain an authorization token for subsequent calls
- list the parts uploaded so far for an in-progress large file upload
- download authorization token generation
- update bucket
- list unfinished large files
- list in-progress large file uploads
- unified workflow for bucket administration, file lifecycle, large file uploads, key management, and event notifications
- update bucket type, cors, or lifecycle settings
- hide a file so it cannot be found by name (soft delete for versioned buckets)
- initiate a multi-part upload for files larger than 5gb
- get upload part url
- get a url for uploading one part of an in-progress large file upload
- delete bucket
- file copy operations
- create key
- set or replace all event notification webhook rules for a bucket
- single bucket operations
- cancel a large file upload and permanently delete all uploaded parts
- authorize account
- set event notification rules for a bucket
- bucket management
- list all application keys
- create a new b2 bucket with specified privacy type
- list buckets
- get bucket notification rules
- complete a large file upload
- delete file version
- assemble parts into a complete file
- account authorization
- get metadata about a specific file version including size, checksums, and custom info
- list large file uploads that have been started but not yet completed or cancelled
- list file names in a bucket
- delete a specific file version
- list current file names in a bucket with optional prefix filtering and pagination
- list file versions
- list all b2 buckets associated with the account
- file upload url generation
- list keys
- object storage for application data, media, and backups
- finish large file
- application developer building on b2 for file storage and delivery
- storage management
- copy file
- Developer
- get upload url
- backblaze
- list all application keys for the account
- get file info
slug: cloud-storage-management
source_filename: cloud-storage-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Backblaze B2 Cloud Storage Management\n  description: Unified cloud storage management workflow combining bucket administration, file lifecycle, large file upload,\n    application key management, and event notification configuration. Serves developers, DevOps engineers, and application\n    integrators building on Backblaze B2.\n  tags:\n  - Backblaze\n  - Cloud Storage\n  - Object Storage\n  - Storage Management\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    B2_APPLICATION_KEY_ID: B2_APPLICATION_KEY_ID\n    B2_APPLICATION_KEY: B2_APPLICATION_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: b2-native-api\n    baseUri: https://api.backblazeb2.com\n    description: Backblaze B2 Native API v4 for cloud object storage management\n    authentication:\n      type: basic\n      username: '{{B2_APPLICATION_KEY_ID}}'\n      password: '{{B2_APPLICATION_KEY}}'\n    resources:\n    - name:\
  \ authorization\n      path: /b2api/v4\n      description: Account authorization and download token generation\n      operations:\n      - name: authorize-account\n        method: GET\n        description: Log in to the B2 API and obtain an authorization token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-download-authorization\n        method: POST\n        description: Generate a time-limited token for downloading private files\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n            fileNamePrefix: '{{tools.file_name_prefix}}'\n            validDurationInSeconds: '{{tools.valid_duration_in_seconds}}'\n    - name: buckets\n      path: /b2api/v4\n      description: Bucket creation, listing, updating, and deletion\n\
  \      operations:\n      - name: create-bucket\n        method: POST\n        description: Create a new B2 bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n            bucketName: '{{tools.bucket_name}}'\n            bucketType: '{{tools.bucket_type}}'\n      - name: list-buckets\n        method: POST\n        description: List all buckets in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n      - name: update-bucket\n        method: POST\n        description: Update bucket settings, CORS rules, or lifecycle rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n            bucketId: '{{tools.bucket_id}}'\n      - name: delete-bucket\n        method: POST\n        description: Delete an empty bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n            bucketId: '{{tools.bucket_id}}'\n    - name: files\n      path: /b2api/v4\n      description: File upload, download, listing, deletion, and metadata operations\n      operations:\n      - name: get-upload-url\n        method: POST\n        description: Get a URL for uploading a file to a specific bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n\
  \            bucketId: '{{tools.bucket_id}}'\n      - name: get-file-info\n        method: POST\n        description: Get metadata and info about a specific file version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fileId: '{{tools.file_id}}'\n      - name: list-file-names\n        method: POST\n        description: List file names in a bucket with optional prefix filtering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n            maxFileCount: '{{tools.max_file_count}}'\n            prefix: '{{tools.prefix}}'\n      - name: list-file-versions\n        method: POST\n        description: List all versions of all files in a bucket\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n      - name: delete-file-version\n        method: POST\n        description: Delete a specific version of a file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fileName: '{{tools.file_name}}'\n            fileId: '{{tools.file_id}}'\n      - name: copy-file\n        method: POST\n        description: Copy a file to create a new version or rename\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sourceFileId: '{{tools.source_file_id}}'\n            fileName: '{{tools.file_name}}'\n      - name: hide-file\n \
  \       method: POST\n        description: Hide a file so it is not returned when listing by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n            fileName: '{{tools.file_name}}'\n    - name: large-files\n      path: /b2api/v4\n      description: Multi-part upload operations for large files\n      operations:\n      - name: start-large-file\n        method: POST\n        description: Prepare for uploading a large file in parts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n            fileName: '{{tools.file_name}}'\n            contentType: '{{tools.content_type}}'\n      - name: get-upload-part-url\n        method: POST\n\
  \        description: Get a URL for uploading one part of a large file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fileId: '{{tools.file_id}}'\n      - name: finish-large-file\n        method: POST\n        description: Assemble all uploaded parts into a complete file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fileId: '{{tools.file_id}}'\n            partSha1Array: '{{tools.part_sha1_array}}'\n      - name: cancel-large-file\n        method: POST\n        description: Cancel a large file upload and remove all uploaded parts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n   \
  \       data:\n            fileId: '{{tools.file_id}}'\n      - name: list-parts\n        method: POST\n        description: List parts uploaded for an in-progress large file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fileId: '{{tools.file_id}}'\n      - name: list-unfinished-large-files\n        method: POST\n        description: List large file uploads that have been started but not finished\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n    - name: application-keys\n      path: /b2api/v4\n      description: Application key creation, listing, and deletion\n      operations:\n      - name: create-key\n        method: POST\n        description: Create a new application\
  \ key with specified capabilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n            capabilities: '{{tools.capabilities}}'\n            keyName: '{{tools.key_name}}'\n      - name: list-keys\n        method: POST\n        description: List all application keys for the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            accountId: '{{tools.account_id}}'\n      - name: delete-key\n        method: POST\n        description: Delete an application key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            applicationKeyId:\
  \ '{{tools.application_key_id}}'\n    - name: notifications\n      path: /b2api/v4\n      description: Bucket event notification rule configuration\n      operations:\n      - name: get-bucket-notification-rules\n        method: POST\n        description: Get the event notification rules configured for a bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n      - name: set-bucket-notification-rules\n        method: POST\n        description: Set or replace all event notification rules for a bucket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            bucketId: '{{tools.bucket_id}}'\n            rules: '{{tools.rules}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ backblaze-storage-api\n    description: Unified REST API for Backblaze B2 Cloud Storage management.\n    resources:\n    - path: /v1/authorize\n      name: authorization\n      description: Account authorization\n      operations:\n      - method: GET\n        name: authorize-account\n        description: Authorize account and obtain API token\n        call: b2-native-api.authorize-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets\n      name: buckets\n      description: Bucket management\n      operations:\n      - method: GET\n        name: list-buckets\n        description: List all B2 buckets in the account\n        call: b2-native-api.list-buckets\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-bucket\n        description: Create a new B2 bucket\n        call: b2-native-api.create-bucket\n        with:\n\
  \          account_id: rest.account_id\n          bucket_name: rest.bucket_name\n          bucket_type: rest.bucket_type\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket_id}\n      name: bucket\n      description: Single bucket operations\n      operations:\n      - method: PUT\n        name: update-bucket\n        description: Update bucket type, CORS, or lifecycle settings\n        call: b2-native-api.update-bucket\n        with:\n          account_id: rest.account_id\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-bucket\n        description: Delete an empty bucket\n        call: b2-native-api.delete-bucket\n        with:\n          account_id: rest.account_id\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket_id}/files\n     \
  \ name: files\n      description: File listing and management within a bucket\n      operations:\n      - method: GET\n        name: list-file-names\n        description: List file names in a bucket\n        call: b2-native-api.list-file-names\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket_id}/file-versions\n      name: file-versions\n      description: File version listing\n      operations:\n      - method: GET\n        name: list-file-versions\n        description: List all versions of all files in a bucket\n        call: b2-native-api.list-file-versions\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/buckets/{bucket_id}/notifications\n      name: notifications\n      description: Bucket event notification rules\n      operations:\n      - method: GET\n        name: get-bucket-notification-rules\n\
  \        description: Get notification rules for a bucket\n        call: b2-native-api.get-bucket-notification-rules\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: set-bucket-notification-rules\n        description: Set event notification rules for a bucket\n        call: b2-native-api.set-bucket-notification-rules\n        with:\n          bucket_id: rest.bucket_id\n          rules: rest.rules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files/{file_id}\n      name: file\n      description: Single file operations\n      operations:\n      - method: GET\n        name: get-file-info\n        description: Get file metadata\n        call: b2-native-api.get-file-info\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-file-version\n\
  \        description: Delete a specific file version\n        call: b2-native-api.delete-file-version\n        with:\n          file_id: rest.file_id\n          file_name: rest.file_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files/upload-url\n      name: upload-url\n      description: File upload URL generation\n      operations:\n      - method: POST\n        name: get-upload-url\n        description: Get a URL to upload a file to a bucket\n        call: b2-native-api.get-upload-url\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files/copy\n      name: file-copy\n      description: File copy operations\n      operations:\n      - method: POST\n        name: copy-file\n        description: Copy a file to a new name or bucket\n        call: b2-native-api.copy-file\n        with:\n          source_file_id: rest.source_file_id\n          file_name:\
  \ rest.file_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/files/hide\n      name: file-hide\n      description: File hiding operations\n      operations:\n      - method: POST\n        name: hide-file\n        description: Hide a file from name-based downloads\n        call: b2-native-api.hide-file\n        with:\n          bucket_id: rest.bucket_id\n          file_name: rest.file_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/large-files\n      name: large-files\n      description: Multi-part large file upload management\n      operations:\n      - method: POST\n        name: start-large-file\n        description: Start a multi-part large file upload\n        call: b2-native-api.start-large-file\n        with:\n          bucket_id: rest.bucket_id\n          file_name: rest.file_name\n          content_type: rest.content_type\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n      - method: GET\n        name: list-unfinished-large-files\n        description: List in-progress large file uploads\n        call: b2-native-api.list-unfinished-large-files\n        with:\n          bucket_id: rest.bucket_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/large-files/{file_id}/parts\n      name: large-file-parts\n      description: Large file part management\n      operations:\n      - method: GET\n        name: list-parts\n        description: List uploaded parts for a large file\n        call: b2-native-api.list-parts\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/large-files/{file_id}/finish\n      name: large-file-finish\n      description: Complete a large file upload\n      operations:\n      - method: POST\n        name: finish-large-file\n        description: Assemble parts into a complete file\n        call: b2-native-api.finish-large-file\n\
  \        with:\n          file_id: rest.file_id\n          part_sha1_array: rest.part_sha1_array\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/large-files/{file_id}/cancel\n      name: large-file-cancel\n      description: Cancel a large file upload\n      operations:\n      - method: POST\n        name: cancel-large-file\n        description: Cancel a large file upload and remove all parts\n        call: b2-native-api.cancel-large-file\n        with:\n          file_id: rest.file_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys\n      name: application-keys\n      description: Application key management\n      operations:\n      - method: GET\n        name: list-keys\n        description: List all application keys\n        call: b2-native-api.list-keys\n        with:\n          account_id: rest.account_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ POST\n        name: create-key\n        description: Create a new scoped application key\n        call: b2-native-api.create-key\n        with:\n          account_id: rest.account_id\n          capabilities: rest.capabilities\n          key_name: rest.key_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/keys/{key_id}\n      name: application-key\n      description: Single key management\n      operations:\n      - method: DELETE\n        name: delete-key\n        description: Delete an application key\n        call: b2-native-api.delete-key\n        with:\n          application_key_id: rest.key_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/download-authorization\n      name: download-authorization\n      description: Download authorization token generation\n      operations:\n      - method: POST\n        name: get-download-authorization\n        description: Get a time-limited token for downloading\
  \ private files\n        call: b2-native-api.get-download-authorization\n        with:\n          bucket_id: rest.bucket_id\n          file_name_prefix: rest.file_name_prefix\n          valid_duration_in_seconds: rest.valid_duration_in_seconds\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: backblaze-storage-mcp\n    transport: http\n    description: MCP server for AI-assisted Backblaze B2 Cloud Storage management.\n    tools:\n    - name: authorize-account\n      description: Log in to the Backblaze B2 API and obtain an authorization token for subsequent calls\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.authorize-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-buckets\n      description: List all B2 buckets associated with the account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-buckets\n\
  \      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-bucket\n      description: Create a new B2 bucket with specified privacy type\n      hints:\n        readOnly: false\n        openWorld: false\n      call: b2-native-api.create-bucket\n      with:\n        account_id: tools.account_id\n        bucket_name: tools.bucket_name\n        bucket_type: tools.bucket_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-bucket\n      description: Update bucket settings including type, CORS rules, and lifecycle rules\n      hints:\n        readOnly: false\n        idempotent: true\n      call: b2-native-api.update-bucket\n      with:\n        account_id: tools.account_id\n        bucket_id: tools.bucket_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-bucket\n      description: Delete an empty B2 bucket permanently\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: b2-native-api.delete-bucket\n      with:\n        account_id: tools.account_id\n        bucket_id: tools.bucket_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-file-names\n      description: List current file names in a bucket with optional prefix filtering and pagination\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-file-names\n      with:\n        bucket_id: tools.bucket_id\n        max_file_count: tools.max_file_count\n        prefix: tools.prefix\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-file-versions\n      description: List all versions of all files in a bucket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-file-versions\n      with:\n        bucket_id: tools.bucket_id\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: get-file-info\n      description: Get metadata about a specific file version including size, checksums, and custom info\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.get-file-info\n      with:\n        file_id: tools.file_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upload-url\n      description: Get a URL and token for uploading a file to a specific bucket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.get-upload-url\n      with:\n        bucket_id: tools.bucket_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-file-version\n      description: Permanently delete a specific version of a file\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: b2-native-api.delete-file-version\n      with:\n        file_name: tools.file_name\n    \
  \    file_id: tools.file_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copy-file\n      description: Copy a file to create a new version with a different name or in another bucket\n      hints:\n        readOnly: false\n        openWorld: false\n      call: b2-native-api.copy-file\n      with:\n        source_file_id: tools.source_file_id\n        file_name: tools.file_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: hide-file\n      description: Hide a file so it cannot be found by name (soft delete for versioned buckets)\n      hints:\n        readOnly: false\n        destructive: false\n      call: b2-native-api.hide-file\n      with:\n        bucket_id: tools.bucket_id\n        file_name: tools.file_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-large-file\n      description: Initiate a multi-part upload for files larger than 5GB\n      hints:\n        readOnly: false\n\
  \        openWorld: false\n      call: b2-native-api.start-large-file\n      with:\n        bucket_id: tools.bucket_id\n        file_name: tools.file_name\n        content_type: tools.content_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upload-part-url\n      description: Get a URL for uploading one part of an in-progress large file upload\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.get-upload-part-url\n      with:\n        file_id: tools.file_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: finish-large-file\n      description: Assemble all uploaded parts into a complete large file\n      hints:\n        readOnly: false\n        openWorld: false\n      call: b2-native-api.finish-large-file\n      with:\n        file_id: tools.file_id\n        part_sha1_array: tools.part_sha1_array\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ cancel-large-file\n      description: Cancel a large file upload and permanently delete all uploaded parts\n      hints:\n        readOnly: false\n        destructive: true\n      call: b2-native-api.cancel-large-file\n      with:\n        file_id: tools.file_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-parts\n      description: List the parts uploaded so far for an in-progress large file upload\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-parts\n      with:\n        file_id: tools.file_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-unfinished-large-files\n      description: List large file uploads that have been started but not yet completed or cancelled\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-unfinished-large-files\n      with:\n        bucket_id: tools.bucket_id\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: create-key\n      description: Create a new application key with specific capabilities and optional bucket/prefix restrictions\n      hints:\n        readOnly: false\n        openWorld: false\n      call: b2-native-api.create-key\n      with:\n        account_id: tools.account_id\n        capabilities: tools.capabilities\n        key_name: tools.key_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-keys\n      description: List all application keys for the account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.list-keys\n      with:\n        account_id: tools.account_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-key\n      description: Permanently delete an application key\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: b2-native-api.delete-key\n  \
  \    with:\n        application_key_id: tools.application_key_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-download-authorization\n      description: Generate a time-limited authorization token for downloading private files\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.get-download-authorization\n      with:\n        bucket_id: tools.bucket_id\n        file_name_prefix: tools.file_name_prefix\n        valid_duration_in_seconds: tools.valid_duration_in_seconds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bucket-notification-rules\n      description: Get the event notification rules configured for a bucket\n      hints:\n        readOnly: true\n        openWorld: false\n      call: b2-native-api.get-bucket-notification-rules\n      with:\n        bucket_id: tools.bucket_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-bucket-notification-rules\n\
  \      description: Set or replace all event notification webhook rules for a bucket\n      hints:\n        readOnly: false\n        idempotent: true\n      call: b2-native-api.set-bucket-notification-rules\n      with:\n        bucket_id: tools.bucket_id\n        rules: tools.rules\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
