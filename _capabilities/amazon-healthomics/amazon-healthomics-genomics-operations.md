---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Amazon Healthomics Genomics Operations
operations: []
personas: []
provider_name: Amazon HealthOmics
provider_slug: amazon-healthomics
search_terms:
- genomics
- aws
- cloud computing
- bioinformatics
- life sciences
- healthcare
slug: amazon-healthomics-genomics-operations
source_yaml: "name: Amazon HealthOmics Genomics Operations\nversion: 1.0.0-alpha1\ndescription: Workflow capability for managing omics data including annotation stores, variant stores, workflows, and analysis runs.\npersona:\n  - Bioinformatics Scientist\n  - Genomics Data Engineer\n  - Life Sciences Developer\napis:\n  - Amazon HealthOmics\ntools:\n  - name: create_annotation_store\n    description: Create a new annotation store for genomic annotations\n    operationId: CreateAnnotationStore\n    method: POST\n    path: /annotationStore\n  - name: list_annotation_stores\n    description: List all annotation stores in the account\n    operationId: ListAnnotationStores\n    method: POST\n    path: /annotationStores\n  - name: create_variant_store\n    description: Create a new variant store for genomic variants\n    operationId: CreateVariantStore\n    method: POST\n    path: /variantStore\n  - name: list_variant_stores\n    description: List all variant stores in the account\n    operationId:\
  \ ListVariantStores\n    method: POST\n    path: /variantStores\n  - name: create_workflow\n    description: Create a new bioinformatics workflow\n    operationId: CreateWorkflow\n    method: POST\n    path: /workflow\n  - name: get_workflow\n    description: Get details of a specific workflow\n    operationId: GetWorkflow\n    method: GET\n    path: /workflow/{id}\n  - name: list_workflows\n    description: List all workflows in the account\n    operationId: ListWorkflows\n    method: GET\n    path: /workflow\n  - name: start_run\n    description: Start a workflow run for omics data analysis\n    operationId: StartRun\n    method: POST\n    path: /run\n  - name: get_run\n    description: Get status and details of a workflow run\n    operationId: GetRun\n    method: GET\n    path: /run/{id}\n  - name: list_runs\n    description: List all workflow runs in the account\n    operationId: ListRuns\n    method: GET\n    path: /run\n  - name: cancel_run\n    description: Cancel a running workflow\
  \ run\n    operationId: CancelRun\n    method: POST\n    path: /run/{id}/cancel\n  - name: list_run_groups\n    description: List all run groups for organizing workflow runs\n    operationId: ListRunGroups\n    method: GET\n    path: /runGroup\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-healthomics/refs/heads/main/capabilities/amazon-healthomics-genomics-operations.yaml
tags: []
tools: []
---
