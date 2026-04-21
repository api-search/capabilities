---
consumed_apis:
- argoworkflows
description: Unified capability for container-native workflow orchestration on Kubernetes using Argo Workflows. Combines workflow lifecycle management, template reuse, cron scheduling, and workflow history for Data Engineers and Platform Engineers.
layout: capability
name: Argo Workflows Orchestration
operations:
- description: List all workflows in a namespace
  method: GET
  name: list-workflows
  path: /v1/workflows/{namespace}
- description: Submit a new workflow
  method: POST
  name: create-workflow
  path: /v1/workflows/{namespace}
- description: List all workflow templates
  method: GET
  name: list-workflow-templates
  path: /v1/workflow-templates/{namespace}
- description: List all cron workflows
  method: GET
  name: list-cron-workflows
  path: /v1/cron-workflows/{namespace}
- description: List archived workflow runs
  method: GET
  name: list-archived-workflows
  path: /v1/archived-workflows
personas: []
provider_name: Argo Workflows
provider_slug: argo-workflows
search_terms:
- reusable workflow templates
- list all cron workflows
- submit a new argo workflow to a kubernetes namespace
- list all workflows in a namespace
- create workflow
- kubernetes
- list all argo workflows in a kubernetes namespace with status
- workflow execution history
- runs ml training, data processing, and etl workflows on kubernetes
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
- Platform Engineer
- list archived workflows
- list cron workflows
- list archived workflow runs
- list scheduled cron workflows in a namespace
- container-native workflow execution and lifecycle management
- scheduled cron workflows
- data processing
- list workflows
- cncf
- containers
- workflow lifecycle management
- workflow engine
- manages argo workflows platform, templates, and scheduling
- data engineering
- parallel data transformation, ml training, and etl
- list reusable workflow templates in a namespace
- Data Engineer
- list all workflow templates
- submit a new workflow
- list historical archived workflow executions
- container orchestration platform
- machine learning
- list workflow templates
- argo workflows
- open source
slug: workflow-orchestration
tags:
- Argo Workflows
- Kubernetes
- Workflow Engine
- CNCF
- Data Engineering
tools:
- description: List all Argo Workflows in a Kubernetes namespace with status
  hints:
    openWorld: true
    readOnly: true
  name: list-workflows
- description: Submit a new Argo Workflow to a Kubernetes namespace
  hints:
    destructive: false
    readOnly: false
  name: create-workflow
- description: List reusable workflow templates in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-workflow-templates
- description: List scheduled cron workflows in a namespace
  hints:
    openWorld: true
    readOnly: true
  name: list-cron-workflows
- description: List historical archived workflow executions
  hints:
    openWorld: true
    readOnly: true
  name: list-archived-workflows
---
