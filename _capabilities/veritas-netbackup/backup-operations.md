---
categories: []
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
- backup
- get job try logs
- get try logs for a backup job.
- get job
- cancel job
- resume a suspended backup job.
- data protection
- list backup images in the catalog.
- storage
- individual job operations.
- create policy
- get details for a specific backup job.
- get image contents
- recovery
- list policies
- list all backup jobs with optional filters.
- list all clients.
- update a backup policy.
- get details for a specific backup image.
- backup image catalog.
- list jobs
- create a new backup policy.
- update policy
- list all backup policies.
- resume job
- get file list for a backup job.
- delete policy
- list all netbackup clients.
- get client
- suspend a running backup job.
- disaster recovery
- get image
- list images
- list backup images.
- expire a backup image.
- list all backup jobs.
- netbackup client management.
- suspend job
- get policy
- delete a backup policy.
- get file contents of a backup image.
- veritas
- get job details.
- get details for a specific client.
- backup policy management.
- login
- get a specific backup policy.
- expire image
- authenticate to netbackup and obtain a jwt token.
- backup job management.
- get job file list
- enterprise
- cancel a running backup job.
- restart job
- restart a failed backup job.
- list clients
slug: backup-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Veritas NetBackup Backup Operations\"\n  description: \"Backup operations workflow for backup administrators to manage jobs, policies, clients, and catalog images across NetBackup environments.\"\n  tags:\n    - Veritas\n    - Backup\n    - Data Protection\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      NETBACKUP_HOST: NETBACKUP_HOST\n      NETBACKUP_USERNAME: NETBACKUP_USERNAME\n      NETBACKUP_PASSWORD: NETBACKUP_PASSWORD\n\ncapability:\n  consumes:\n    - import: netbackup\n      location: ./shared/netbackup.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: backup-operations-api\n      description: \"Unified REST API for NetBackup backup operations.\"\n      resources:\n        - path: /v1/jobs\n          name: jobs\n          description: \"Backup job management.\"\n          operations:\n            - method: GET\n              name: list-jobs\n\
  \              description: \"List all backup jobs.\"\n              call: \"netbackup.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs/{jobId}\n          name: job\n          description: \"Individual job operations.\"\n          operations:\n            - method: GET\n              name: get-job\n              description: \"Get job details.\"\n              call: \"netbackup.get-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/policies\n          name: policies\n          description: \"Backup policy management.\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List all backup policies.\"\n              call: \"netbackup.list-policies\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-policy\n              description: \"Create a new backup policy.\"\n              call: \"netbackup.create-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clients\n          name: clients\n          description: \"NetBackup client management.\"\n          operations:\n            - method: GET\n              name: list-clients\n              description: \"List all clients.\"\n              call: \"netbackup.list-clients\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images\n          name: images\n          description: \"Backup image catalog.\"\n          operations:\n            - method: GET\n              name: list-images\n              description: \"List backup images.\"\n              call: \"netbackup.list-images\"\n     \
  \         outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: backup-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted NetBackup backup operations.\"\n      tools:\n        - name: login\n          description: \"Authenticate to NetBackup and obtain a JWT token.\"\n          hints:\n            readOnly: false\n          call: \"netbackup.login\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: \"List all backup jobs with optional filters.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job\n          description: \"Get details for a specific backup job.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-job\"\
  \n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-job\n          description: \"Cancel a running backup job.\"\n          hints:\n            destructive: true\n          call: \"netbackup.cancel-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: suspend-job\n          description: \"Suspend a running backup job.\"\n          hints:\n            readOnly: false\n          call: \"netbackup.suspend-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resume-job\n          description: \"Resume a suspended backup job.\"\n          hints:\n            readOnly: false\n          call: \"netbackup.resume-job\"\n          with:\n            jobId: \"tools.jobId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restart-job\n          description: \"Restart a failed backup job.\"\n          hints:\n            readOnly: false\n          call: \"netbackup.restart-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-file-list\n          description: \"Get file list for a backup job.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-job-file-list\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-job-try-logs\n          description: \"Get try logs for a backup job.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-job-try-logs\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: list-policies\n          description: \"List all backup policies.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-policy\n          description: \"Get a specific backup policy.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-policy\"\n          with:\n            policyName: \"tools.policyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-policy\n          description: \"Create a new backup policy.\"\n          hints:\n            readOnly: false\n          call: \"netbackup.create-policy\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-policy\n          description: \"Update a backup policy.\"\n\
  \          hints:\n            readOnly: false\n            idempotent: true\n          call: \"netbackup.update-policy\"\n          with:\n            policyName: \"tools.policyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-policy\n          description: \"Delete a backup policy.\"\n          hints:\n            destructive: true\n          call: \"netbackup.delete-policy\"\n          with:\n            policyName: \"tools.policyName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clients\n          description: \"List all NetBackup clients.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.list-clients\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-client\n          description: \"Get details for a specific client.\"\n          hints:\n            readOnly: true\n\
  \          call: \"netbackup.get-client\"\n          with:\n            hostId: \"tools.hostId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-images\n          description: \"List backup images in the catalog.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.list-images\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-image\n          description: \"Get details for a specific backup image.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-image\"\n          with:\n            backupId: \"tools.backupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: expire-image\n          description: \"Expire a backup image.\"\n          hints:\n            destructive: true\n          call: \"netbackup.expire-image\"\n          with:\n            backupId: \"\
  tools.backupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-image-contents\n          description: \"Get file contents of a backup image.\"\n          hints:\n            readOnly: true\n          call: \"netbackup.get-image-contents\"\n          with:\n            backupId: \"tools.backupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/veritas-netbackup/refs/heads/main/capabilities/backup-operations.yaml
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
