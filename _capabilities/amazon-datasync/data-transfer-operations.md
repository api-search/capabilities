---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Data Transfer Operations
operations: []
personas: []
provider_name: Amazon DataSync
provider_slug: amazon-datasync
search_terms:
- migration
- storage
- hybrid cloud
- automation
- data transfer
- aws
slug: data-transfer-operations
source_filename: data-transfer-operations.yaml
source_heading: Capability Spec
source_yaml: "id: https://api-evangelist.github.io/amazon-datasync/capabilities/data-transfer-operations.yaml\nname: Data Transfer Operations\ndescription: Workflow-oriented Naftiko capability for automated data transfer operations using Amazon DataSync, covering on-premises to cloud migration, cross-cloud transfer, and ongoing synchronization workflows.\nversion: 1.0.0-alpha1\nspecificationVersion: 1.0.0-alpha1\n\ntags:\n  - Data Transfer\n  - Migration\n  - Storage\n  - Automation\n  - Hybrid Cloud\n\nimports:\n  - url: capabilities/shared/datasync.yaml\n    as: datasync\n\npersonas:\n  - name: Storage Administrator\n    description: Administrator responsible for managing data movement between on-premises and cloud storage\n  - name: Cloud Migration Engineer\n    description: Engineer executing data migrations from on-premises systems to AWS cloud storage\n  - name: Data Platform Engineer\n    description: Engineer maintaining ongoing data synchronization between storage systems\n\nworkflows:\n\
  \  - name: Migrate Data to S3\n    description: Transfer data from an on-premises NFS/SMB share to Amazon S3\n    steps:\n      - step: createAgent\n        capability: datasync\n        description: Activate a DataSync agent on the on-premises network\n      - step: createLocationNfs\n        capability: datasync\n        description: Create the source NFS location pointing to on-premises data\n      - step: createLocationS3\n        capability: datasync\n        description: Create the destination S3 location\n      - step: createTask\n        capability: datasync\n        description: Create a transfer task linking source and destination\n      - step: startTaskExecution\n        capability: datasync\n        description: Start the data transfer\n      - step: describeTaskExecution\n        capability: datasync\n        description: Monitor transfer progress until completion\n    persona: Cloud Migration Engineer\n\n  - name: Monitor Ongoing Synchronization\n    description: Monitor\
  \ and manage scheduled data synchronization runs\n    steps:\n      - step: listTaskExecutions\n        capability: datasync\n        description: List recent task execution runs\n      - step: describeTaskExecution\n        capability: datasync\n        description: Check status and metrics for each execution\n    persona: Storage Administrator\n\n  - name: Set Up Recurring Transfer\n    description: Configure a task with a schedule for ongoing recurring data transfers\n    steps:\n      - step: createTask\n        capability: datasync\n        description: Create task with schedule configuration\n      - step: listTasks\n        capability: datasync\n        description: Verify task is scheduled and active\n    persona: Data Platform Engineer\n\nrest:\n  port: 8080\n  baseURL: https://datasync.amazonaws.com\n  auth:\n    type: aws-signature-v4\n    service: datasync\n\nmcp:\n  port: 9090\n  tools:\n    - name: migrate_data_to_s3\n      description: Full workflow to transfer data from\
  \ on-premises storage to Amazon S3\n      workflow: Migrate Data to S3\n    - name: monitor_synchronization\n      description: Monitor the status of ongoing data synchronization runs\n      workflow: Monitor Ongoing Synchronization\n    - name: setup_recurring_transfer\n      description: Configure a scheduled recurring data transfer task\n      workflow: Set Up Recurring Transfer\n    - name: list_tasks\n      description: List all configured DataSync tasks\n      operationId: listTasks\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-datasync/refs/heads/main/capabilities/data-transfer-operations.yaml
tags: []
tools: []
---
