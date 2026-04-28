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
- create key
- list large file uploads that have been started but not yet completed or cancelled
- list all b2 buckets in the account
- copy a file to create a new version with a different name or in another bucket
- permanently delete an application key
- cancel a large file upload
- Application Integrator
- generate a time-limited authorization token for downloading private files
- get upload url
- bucket event notification rules
- get file info
- application key management for scoped, least-privilege api access
- get file metadata
- backup
- list parts
- list all application keys
- list unfinished large files
- download authorization token generation
- copy file
- assemble all uploaded parts into a complete large file
- cancel large file
- authorize account
- webhook-based event notifications for real-time storage event processing
- set or replace all event notification webhook rules for a bucket
- storage
- single key management
- large file part management
- delete an empty bucket
- create a new scoped application key
- get download authorization
- object storage
- DevOps Engineer
- delete a specific file version
- update bucket
- backblaze
- single file operations
- start large file
- list current file names in a bucket with optional prefix filtering and pagination
- file hiding operations
- unified workflow for bucket administration, file lifecycle, large file uploads, key management, and event notifications
- file listing and management within a bucket
- object storage for application data, media, and backups
- complete a large file upload
- get notification rules for a bucket
- cancel a large file upload and permanently delete all uploaded parts
- list buckets
- get bucket notification rules
- initiate a multi-part upload for files larger than 5gb
- delete key
- cancel a large file upload and remove all parts
- list all versions of all files in a bucket
- hide file
- permanently delete a specific version of a file
- hide a file from name-based downloads
- log in to the backblaze b2 api and obtain an authorization token for subsequent calls
- list file names in a bucket
- set event notification rules for a bucket
- file version listing
- list keys
- operations engineer managing b2 buckets, lifecycle rules, and application keys as infrastructure
- list all b2 buckets associated with the account
- get upload part url
- list in-progress large file uploads
- finish large file
- get a url and token for uploading a file to a specific bucket
- set bucket notification rules
- file copy operations
- create a new b2 bucket
- Developer
- update bucket settings including type, cors rules, and lifecycle rules
- get a url for uploading one part of an in-progress large file upload
- multi-part large file upload management
- list file names
- list the parts uploaded so far for an in-progress large file upload
- get a url to upload a file to a bucket
- application key management
- storage management
- update bucket type, cors, or lifecycle settings
- integration specialist connecting third-party tools (backup, cdn, media) to b2
- delete bucket
- delete file version
- cloud storage
- delete an application key
- list all application keys for the account
- bucket management
- file upload url generation
- application developer building on b2 for file storage and delivery
- start a multi-part large file upload
- create a new b2 bucket with specified privacy type
- create a new application key with specific capabilities and optional bucket/prefix restrictions
- create bucket
- get metadata about a specific file version including size, checksums, and custom info
- account authorization
- list uploaded parts for a large file
- get a time-limited token for downloading private files
- delete an empty b2 bucket permanently
- assemble parts into a complete file
- get the event notification rules configured for a bucket
- copy a file to a new name or bucket
- single bucket operations
- authorize account and obtain api token
- hide a file so it cannot be found by name (soft delete for versioned buckets)
- list file versions
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
