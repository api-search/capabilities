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
- list all workflow templates
- Platform Engineer
- create workflow
- workflow engine
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
- list all cron workflows
- containers
- list all workflows in a namespace
- list archived workflow runs
- kubernetes
- workflow lifecycle management
- list scheduled cron workflows in a namespace
- list reusable workflow templates in a namespace
- machine learning
- reusable workflow templates
- manages argo workflows platform, templates, and scheduling
- list workflow templates
- container orchestration platform
- workflow execution history
- submit a new argo workflow to a kubernetes namespace
- list workflows
- list cron workflows
- parallel data transformation, ml training, and etl
- argo workflows
- data processing
- cncf
- Data Engineer
- list historical archived workflow executions
- submit a new workflow
- scheduled cron workflows
- list archived workflows
- container-native workflow execution and lifecycle management
- data engineering
- open source
- runs ml training, data processing, and etl workflows on kubernetes
- list all argo workflows in a kubernetes namespace with status
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
