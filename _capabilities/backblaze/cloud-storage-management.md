---
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
- get a url and token for uploading a file to a specific bucket
- application key management for scoped, least-privilege api access
- multi-part large file upload management
- create a new b2 bucket with specified privacy type
- copy a file to create a new version with a different name or in another bucket
- permanently delete an application key
- list keys
- list file names
- copy a file to a new name or bucket
- update bucket
- get a time-limited token for downloading private files
- operations engineer managing b2 buckets, lifecycle rules, and application keys as infrastructure
- set bucket notification rules
- list all b2 buckets associated with the account
- create a new application key with specific capabilities and optional bucket/prefix restrictions
- delete file version
- get file metadata
- list all application keys
- authorize account and obtain api token
- get upload part url
- assemble all uploaded parts into a complete large file
- application key management
- backup
- list all versions of all files in a bucket
- list buckets
- list the parts uploaded so far for an in-progress large file upload
- bucket management
- delete bucket
- object storage for application data, media, and backups
- file upload url generation
- delete an application key
- unified workflow for bucket administration, file lifecycle, large file uploads, key management, and event notifications
- get file info
- list current file names in a bucket with optional prefix filtering and pagination
- object storage
- account authorization
- list all application keys for the account
- list large file uploads that have been started but not yet completed or cancelled
- update bucket settings including type, cors rules, and lifecycle rules
- cloud storage
- get upload url
- single key management
- Developer
- DevOps Engineer
- file hiding operations
- hide file
- get bucket notification rules
- assemble parts into a complete file
- initiate a multi-part upload for files larger than 5gb
- application developer building on b2 for file storage and delivery
- cancel a large file upload and permanently delete all uploaded parts
- set event notification rules for a bucket
- generate a time-limited authorization token for downloading private files
- file copy operations
- start a multi-part large file upload
- list parts
- list unfinished large files
- single bucket operations
- large file part management
- get metadata about a specific file version including size, checksums, and custom info
- list file versions
- file version listing
- delete a specific file version
- get download authorization
- Application Integrator
- single file operations
- webhook-based event notifications for real-time storage event processing
- cancel a large file upload
- start large file
- set or replace all event notification webhook rules for a bucket
- storage management
- create bucket
- hide a file so it cannot be found by name (soft delete for versioned buckets)
- delete an empty bucket
- storage
- integration specialist connecting third-party tools (backup, cdn, media) to b2
- get a url for uploading one part of an in-progress large file upload
- complete a large file upload
- create key
- backblaze
- bucket event notification rules
- list in-progress large file uploads
- hide a file from name-based downloads
- get notification rules for a bucket
- cancel large file
- copy file
- get the event notification rules configured for a bucket
- log in to the backblaze b2 api and obtain an authorization token for subsequent calls
- create a new scoped application key
- list all b2 buckets in the account
- authorize account
- list file names in a bucket
- update bucket type, cors, or lifecycle settings
- create a new b2 bucket
- finish large file
- cancel a large file upload and remove all parts
- file listing and management within a bucket
- delete an empty b2 bucket permanently
- delete key
- list uploaded parts for a large file
- permanently delete a specific version of a file
- get a url to upload a file to a bucket
- download authorization token generation
slug: cloud-storage-management
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
