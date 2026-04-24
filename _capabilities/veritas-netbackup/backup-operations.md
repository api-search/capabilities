---
consumed_apis:
- netbackup
description: Backup operations workflow for backup administrators to manage jobs, policies, clients, and catalog images across NetBackup environments.
layout: capability
name: Veritas NetBackup Backup Operations
operations:
- description: List all backup jobs.
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Get job details.
  method: GET
  name: get-job
  path: /v1/jobs/{jobId}
- description: List all backup policies.
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a new backup policy.
  method: POST
  name: create-policy
  path: /v1/policies
- description: List all clients.
  method: GET
  name: list-clients
  path: /v1/clients
- description: List backup images.
  method: GET
  name: list-images
  path: /v1/images
personas: []
provider_name: Veritas NetBackup
provider_slug: veritas-netbackup
search_terms:
- login
- individual job operations.
- storage
- expire a backup image.
- authenticate to netbackup and obtain a jwt token.
- list all backup jobs with optional filters.
- backup policy management.
- get job file list
- get policy
- resume a suspended backup job.
- recovery
- expire image
- list all clients.
- get job try logs
- disaster recovery
- get file list for a backup job.
- veritas
- get a specific backup policy.
- delete policy
- suspend job
- get job
- update policy
- create policy
- get details for a specific backup job.
- backup image catalog.
- update a backup policy.
- get client
- backup job management.
- resume job
- list jobs
- list all backup policies.
- list clients
- list backup images.
- data protection
- list policies
- restart job
- restart a failed backup job.
- get try logs for a backup job.
- create a new backup policy.
- get file contents of a backup image.
- get image contents
- cancel a running backup job.
- delete a backup policy.
- get details for a specific backup image.
- list all backup jobs.
- get image
- list images
- cancel job
- suspend a running backup job.
- get job details.
- get details for a specific client.
- list all netbackup clients.
- list backup images in the catalog.
- netbackup client management.
- backup
- enterprise
slug: backup-operations
tags:
- Veritas
- Backup
- Data Protection
tools:
- description: Authenticate to NetBackup and obtain a JWT token.
  hints:
    readOnly: false
  name: login
- description: List all backup jobs with optional filters.
  hints:
    readOnly: true
  name: list-jobs
- description: Get details for a specific backup job.
  hints:
    readOnly: true
  name: get-job
- description: Cancel a running backup job.
  hints:
    destructive: true
  name: cancel-job
- description: Suspend a running backup job.
  hints:
    readOnly: false
  name: suspend-job
- description: Resume a suspended backup job.
  hints:
    readOnly: false
  name: resume-job
- description: Restart a failed backup job.
  hints:
    readOnly: false
  name: restart-job
- description: Get file list for a backup job.
  hints:
    readOnly: true
  name: get-job-file-list
- description: Get try logs for a backup job.
  hints:
    readOnly: true
  name: get-job-try-logs
- description: List all backup policies.
  hints:
    readOnly: true
  name: list-policies
- description: Get a specific backup policy.
  hints:
    readOnly: true
  name: get-policy
- description: Create a new backup policy.
  hints:
    readOnly: false
  name: create-policy
- description: Update a backup policy.
  hints:
    idempotent: true
    readOnly: false
  name: update-policy
- description: Delete a backup policy.
  hints:
    destructive: true
  name: delete-policy
- description: List all NetBackup clients.
  hints:
    readOnly: true
  name: list-clients
- description: Get details for a specific client.
  hints:
    readOnly: true
  name: get-client
- description: List backup images in the catalog.
  hints:
    readOnly: true
  name: list-images
- description: Get details for a specific backup image.
  hints:
    readOnly: true
  name: get-image
- description: Expire a backup image.
  hints:
    destructive: true
  name: expire-image
- description: Get file contents of a backup image.
  hints:
    readOnly: true
  name: get-image-contents
---
