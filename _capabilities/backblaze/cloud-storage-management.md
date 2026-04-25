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
- get notification rules for a bucket
- list unfinished large files
- get bucket notification rules
- delete key
- hide a file so it cannot be found by name (soft delete for versioned buckets)
- authorize account
- backup
- initiate a multi-part upload for files larger than 5gb
- complete a large file upload
- delete an empty bucket
- get a url to upload a file to a bucket
- large file part management
- object storage for application data, media, and backups
- list the parts uploaded so far for an in-progress large file upload
- get a time-limited token for downloading private files
- start a multi-part large file upload
- single key management
- cancel a large file upload
- list all application keys
- authorize account and obtain api token
- file listing and management within a bucket
- set or replace all event notification webhook rules for a bucket
- storage management
- list all application keys for the account
- list file versions
- cancel a large file upload and remove all parts
- copy file
- DevOps Engineer
- application key management for scoped, least-privilege api access
- update bucket
- finish large file
- list file names in a bucket
- webhook-based event notifications for real-time storage event processing
- hide a file from name-based downloads
- multi-part large file upload management
- delete a specific file version
- update bucket settings including type, cors rules, and lifecycle rules
- bucket event notification rules
- create a new scoped application key
- permanently delete a specific version of a file
- list file names
- get metadata about a specific file version including size, checksums, and custom info
- set event notification rules for a bucket
- start large file
- integration specialist connecting third-party tools (backup, cdn, media) to b2
- single bucket operations
- list in-progress large file uploads
- list current file names in a bucket with optional prefix filtering and pagination
- generate a time-limited authorization token for downloading private files
- list all versions of all files in a bucket
- set bucket notification rules
- bucket management
- object storage
- cancel large file
- get a url and token for uploading a file to a specific bucket
- delete bucket
- hide file
- file copy operations
- cloud storage
- get download authorization
- get upload part url
- unified workflow for bucket administration, file lifecycle, large file uploads, key management, and event notifications
- application key management
- list all b2 buckets in the account
- operations engineer managing b2 buckets, lifecycle rules, and application keys as infrastructure
- delete file version
- download authorization token generation
- create a new b2 bucket with specified privacy type
- assemble all uploaded parts into a complete large file
- create bucket
- storage
- get the event notification rules configured for a bucket
- list parts
- list buckets
- permanently delete an application key
- create key
- cancel a large file upload and permanently delete all uploaded parts
- delete an application key
- list keys
- list all b2 buckets associated with the account
- get file metadata
- file version listing
- single file operations
- create a new b2 bucket
- list large file uploads that have been started but not yet completed or cancelled
- log in to the backblaze b2 api and obtain an authorization token for subsequent calls
- update bucket type, cors, or lifecycle settings
- copy a file to a new name or bucket
- Application Integrator
- copy a file to create a new version with a different name or in another bucket
- delete an empty b2 bucket permanently
- get upload url
- file hiding operations
- application developer building on b2 for file storage and delivery
- account authorization
- assemble parts into a complete file
- get a url for uploading one part of an in-progress large file upload
- backblaze
- list uploaded parts for a large file
- create a new application key with specific capabilities and optional bucket/prefix restrictions
- file upload url generation
- Developer
- get file info
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
