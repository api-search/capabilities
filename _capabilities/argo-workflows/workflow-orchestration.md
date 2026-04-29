---
categories:
- container-orchestration
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
- list scheduled cron workflows in a namespace
- list all workflow templates
- submit a new argo workflow to a kubernetes namespace
- list workflow templates
- list reusable workflow templates in a namespace
- cncf
- manages argo workflows platform, templates, and scheduling
- list historical archived workflow executions
- submit a new workflow
- argo workflows
- open source
- Data Engineer
- create workflow
- list workflows
- reusable workflow templates
- container-native workflow execution and lifecycle management
- parallel data transformation, ml training, and etl
- list archived workflows
- list all workflows in a namespace
- workflow execution history
- list all argo workflows in a kubernetes namespace with status
- list all cron workflows
- data processing
- runs ml training, data processing, and etl workflows on kubernetes
- container orchestration platform
- end-to-end container-native workflow orchestration combining lifecycle management, templates, scheduling, and history
- scheduled cron workflows
- list cron workflows
- machine learning
- kubernetes
- data engineering
- workflow engine
- workflow lifecycle management
- containers
- list archived workflow runs
- Platform Engineer
slug: workflow-orchestration
source_filename: workflow-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Argo Workflows Orchestration\"\n  description: \"Unified capability for container-native workflow orchestration on Kubernetes using Argo Workflows. Combines workflow lifecycle management, template reuse, cron scheduling, and workflow history for Data Engineers and Platform Engineers.\"\n  tags:\n    - Argo Workflows\n    - Kubernetes\n    - Workflow Engine\n    - CNCF\n    - Data Engineering\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      ARGO_TOKEN: ARGO_TOKEN\n      ARGO_SERVER: ARGO_SERVER\n\ncapability:\n  consumes:\n    - import: argoworkflows\n      location: ./shared/argo-workflows-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: workflow-orchestration-api\n      description: \"Unified REST API for Kubernetes workflow orchestration.\"\n      resources:\n        - path: /v1/workflows/{namespace}\n          name: workflows\n          description:\
  \ \"Workflow lifecycle management\"\n          operations:\n            - method: GET\n              name: list-workflows\n              description: \"List all workflows in a namespace\"\n              call: \"argoworkflows.list-workflows\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-workflow\n              description: \"Submit a new workflow\"\n              call: \"argoworkflows.create-workflow\"\n              with:\n                namespace: \"rest.namespace\"\n                workflow: \"rest.workflow\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workflow-templates/{namespace}\n          name: workflow-templates\n          description: \"Reusable workflow templates\"\n          operations:\n            - method: GET\n       \
  \       name: list-workflow-templates\n              description: \"List all workflow templates\"\n              call: \"argoworkflows.list-workflow-templates\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cron-workflows/{namespace}\n          name: cron-workflows\n          description: \"Scheduled cron workflows\"\n          operations:\n            - method: GET\n              name: list-cron-workflows\n              description: \"List all cron workflows\"\n              call: \"argoworkflows.list-cron-workflows\"\n              with:\n                namespace: \"rest.namespace\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/archived-workflows\n          name: archived-workflows\n          description: \"Workflow execution history\"\n          operations:\n        \
  \    - method: GET\n              name: list-archived-workflows\n              description: \"List archived workflow runs\"\n              call: \"argoworkflows.list-archived-workflows\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: workflow-orchestration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted workflow orchestration with Argo Workflows.\"\n      tools:\n        - name: list-workflows\n          description: \"List all Argo Workflows in a Kubernetes namespace with status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argoworkflows.list-workflows\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-workflow\n          description: \"Submit a new Argo Workflow to a Kubernetes namespace\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n          call: \"argoworkflows.create-workflow\"\n          with:\n            namespace: \"tools.namespace\"\n            workflow: \"tools.workflow\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workflow-templates\n          description: \"List reusable workflow templates in a namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argoworkflows.list-workflow-templates\"\n          with:\n            namespace: \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cron-workflows\n          description: \"List scheduled cron workflows in a namespace\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argoworkflows.list-cron-workflows\"\n          with:\n            namespace:\
  \ \"tools.namespace\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-archived-workflows\n          description: \"List historical archived workflow executions\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"argoworkflows.list-archived-workflows\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/argo-workflows/refs/heads/main/capabilities/workflow-orchestration.yaml
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
