---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Backup Automation Operations
operations: []
personas: []
provider_name: Amazon Data Lifecycle Manager
provider_slug: amazon-data-lifecycle-manager
search_terms:
- lifecycle management
- compliance
- ebs snapshots
- automation
- aws
- storage
- backup
slug: backup-automation-operations
source_filename: backup-automation-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-data-lifecycle-manager/capabilities/backup-automation-operations.yaml\nname: Backup Automation Operations\ndescription: Workflow-oriented Naftiko capability for automating EBS backup and retention operations using Amazon Data Lifecycle Manager, covering policy creation, monitoring, and lifecycle management workflows.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Backup\n  - Automation\n  - EBS Snapshots\n  - Compliance\n  - Disaster Recovery\n\nimports:\n  - url: capabilities/shared/data-lifecycle-manager.yaml\n    as: dlm\n\npersonas:\n  - name: Cloud Operations Engineer\n    description: Engineer responsible for managing EBS backup and retention policies across AWS accounts\n  - name: Compliance Officer\n    description: Officer ensuring backup policies meet regulatory retention requirements\n  - name: Storage Administrator\n    description: Administrator managing EBS storage costs through lifecycle automation\n\
  \nworkflows:\n  - name: Create Backup Policy\n    description: Create and activate an automated EBS snapshot backup policy\n    steps:\n      - step: createLifecyclePolicy\n        capability: dlm\n        description: Create a lifecycle policy with schedule and retention rules\n      - step: getLifecyclePolicy\n        capability: dlm\n        description: Verify the policy was created and is in ENABLED state\n    persona: Cloud Operations Engineer\n\n  - name: Audit Backup Policies\n    description: Review all active backup policies and their configurations\n    steps:\n      - step: getLifecyclePolicies\n        capability: dlm\n        description: List all lifecycle policies with their states\n      - step: getLifecyclePolicy\n        capability: dlm\n        description: Inspect details of each policy for compliance review\n    persona: Compliance Officer\n\n  - name: Suspend Backup Policy\n    description: Temporarily disable a backup policy during maintenance windows\n    steps:\n\
  \      - step: updateLifecyclePolicy\n        capability: dlm\n        description: Set policy state to DISABLED\n      - step: getLifecyclePolicy\n        capability: dlm\n        description: Confirm policy is disabled\n    persona: Cloud Operations Engineer\n\n  - name: Decommission Backup Policy\n    description: Remove a backup policy when it is no longer needed\n    steps:\n      - step: getLifecyclePolicy\n        capability: dlm\n        description: Review policy before deletion\n      - step: deleteLifecyclePolicy\n        capability: dlm\n        description: Delete the lifecycle policy\n    persona: Storage Administrator\n\nrest:\n  port: 8080\n  baseURL: https://dlm.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: dlm\n\nmcp:\n  port: 9090\n  tools:\n    - name: create_backup_policy\n      description: Create an automated EBS snapshot backup policy with schedule and retention rules\n      workflow: Create Backup Policy\n    - name: audit_backup_policies\n \
  \     description: List and review all active backup policies for compliance\n      workflow: Audit Backup Policies\n    - name: suspend_backup_policy\n      description: Temporarily disable a backup policy during maintenance\n      workflow: Suspend Backup Policy\n    - name: decommission_backup_policy\n      description: Remove a backup policy that is no longer needed\n      workflow: Decommission Backup Policy\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-data-lifecycle-manager/refs/heads/main/capabilities/backup-automation-operations.yaml
tags: []
tools: []
---
