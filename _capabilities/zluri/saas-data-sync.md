---
categories: []
consumed_apis: []
description: A workflow capability for an IT Operations engineer pushing user, application, contract, and activity data from custom or on-premise systems into Zluri. Combines instance setup, sync session management, and paginated snapshot/fact data uploads to keep Zluri's system of record in sync.
layout: capability
name: Saas Data Sync
operations: []
personas: []
provider_name: Zluri
provider_slug: zluri
search_terms:
- push entity and activity data from custom systems into zluri.
- saas management
- owns saas visibility, governance, and cost control.
- operates the saas data pipeline into zluri.
- uses zluri for access governance, reviews, and compliance.
- access management
slug: saas-data-sync
source_filename: saas-data-sync.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko/v1\nkind: WorkflowCapability\nmetadata:\n  name: saas-data-sync\n  provider: zluri\ninfo:\n  title: SaaS Data Sync\n  description: >-\n    A workflow capability for an IT Operations engineer pushing user,\n    application, contract, and activity data from custom or on-premise systems\n    into Zluri. Combines instance setup, sync session management, and paginated\n    snapshot/fact data uploads to keep Zluri's system of record in sync.\n  persona: IT Operations Engineer\ncombines:\n  - api: zluri-api\n    capability: capabilities/shared/zluri-api.yaml\nmcp:\n  tools:\n    - name: list-instances\n      description: List all configured integration instances.\n      operationId: listInstances\n    - name: get-instance\n      description: Retrieve details of a specific instance.\n      operationId: getInstance\n    - name: create-sync\n      description: Create a new sync session for an instance.\n      operationId: createSync\n    - name: upload-snapshot\n\
  \      description: Upload a page of snapshot data.\n      operationId: uploadSnapshotData\n    - name: upload-fact\n      description: Upload a page of fact data.\n      operationId: uploadFactData\n    - name: finish-sync\n      description: Finish the active sync session.\n      operationId: finishSync\n    - name: get-sync-status\n      description: Check sync status.\n      operationId: getSyncStatus\n    - name: list-webhooks\n      description: List configured webhooks.\n      operationId: listWebhooks\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zluri/refs/heads/main/capabilities/saas-data-sync.yaml
tags: []
tools: []
---
