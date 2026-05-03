---
categories: []
consumed_apis:
- spinnaker
description: Workflow capability for managing continuous delivery pipelines and deployments using the Spinnaker Gate API. Enables DevOps engineers and platform teams to manage application deployment lifecycles, trigger and control pipeline executions, monitor cluster state, and orchestrate multi-cloud deployments from a single interface.
layout: capability
name: Spinnaker Continuous Delivery
operations:
- description: List all Spinnaker applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Get application configuration and cluster summary
  method: GET
  name: get-application
  path: /v1/applications/{application}
- description: List recent pipeline executions
  method: GET
  name: list-pipeline-executions
  path: /v1/applications/{application}/pipelines
- description: Trigger a pipeline by name
  method: POST
  name: invoke-pipeline
  path: /v1/applications/{application}/pipelines
- description: Get pipeline execution status and stage details
  method: GET
  name: get-pipeline-execution
  path: /v1/pipelines/{id}
- description: Cancel a running pipeline
  method: PUT
  name: cancel-pipeline
  path: /v1/pipelines/{id}/cancel
- description: Pause a running pipeline
  method: PUT
  name: pause-pipeline
  path: /v1/pipelines/{id}/pause
- description: Resume a paused pipeline
  method: PUT
  name: resume-pipeline
  path: /v1/pipelines/{id}/resume
- description: List clusters for an application
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: List load balancers for an application
  method: GET
  name: list-load-balancers
  path: /v1/load-balancers
- description: Search Spinnaker resources
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: Spinnaker
provider_slug: spinnaker
search_terms:
- search resources
- invoke pipeline
- pipeline execution control
- list pipeline executions
- pause a running pipeline
- cluster management
- cancel a pipeline execution
- list applications
- pipelines
- list all pipeline configurations for a spinnaker application
- list all clusters for a spinnaker application across cloud accounts
- resource search
- list pipeline configs
- get application configuration and cluster summary
- continuous delivery
- resume a pipeline execution
- pipeline execution history
- pause a running pipeline execution — it can be resumed later
- deployments
- pause a pipeline execution
- pause pipeline
- list load balancers
- get configuration and cluster summary for a spinnaker application
- list recent pipeline executions
- load balancer management
- get full status, stage details, and outputs of a specific pipeline execution
- application management
- search
- get pipeline execution
- get application
- list all spinnaker applications
- get pipeline execution status and stage details
- cancel a running pipeline
- resume a paused pipeline
- trigger a spinnaker pipeline execution by application and pipeline name
- search across all spinnaker-managed resources by keyword and optional type
- cancel pipeline
- cloud infrastructure
- multi-cloud
- list load balancers associated with a spinnaker application
- resume pipeline
- list load balancers for an application
- search spinnaker resources
- resume a paused pipeline execution
- containers
- cancel a running pipeline execution
- application details
- list clusters for an application
- spinnaker
- list recent pipeline execution history with status for an application
- list clusters
- trigger a pipeline by name
- devops
slug: continuous-delivery
source_filename: continuous-delivery.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Spinnaker Continuous Delivery\"\n  description: >-\n    Workflow capability for managing continuous delivery pipelines and deployments\n    using the Spinnaker Gate API. Enables DevOps engineers and platform teams to\n    manage application deployment lifecycles, trigger and control pipeline executions,\n    monitor cluster state, and orchestrate multi-cloud deployments from a single interface.\n  tags:\n    - Spinnaker\n    - Continuous Delivery\n    - Pipelines\n    - Deployments\n    - Cloud Infrastructure\n    - DevOps\n    - Multi-Cloud\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPINNAKER_OAUTH_TOKEN: SPINNAKER_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: spinnaker\n      location: ./shared/gate.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spinnaker-cd-api\n      description: \"Unified REST API for Spinnaker continuous delivery\
  \ workflows.\"\n      resources:\n        - path: /v1/applications\n          name: applications\n          description: \"Application management\"\n          operations:\n            - method: GET\n              name: list-applications\n              description: \"List all Spinnaker applications\"\n              call: \"spinnaker.list-applications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{application}\n          name: application\n          description: \"Application details\"\n          operations:\n            - method: GET\n              name: get-application\n              description: \"Get application configuration and cluster summary\"\n              call: \"spinnaker.get-application\"\n              with:\n                application: \"rest.application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/applications/{application}/pipelines\n\
  \          name: pipeline-executions\n          description: \"Pipeline execution history\"\n          operations:\n            - method: GET\n              name: list-pipeline-executions\n              description: \"List recent pipeline executions\"\n              call: \"spinnaker.list-pipeline-executions\"\n              with:\n                application: \"rest.application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invoke-pipeline\n              description: \"Trigger a pipeline by name\"\n              call: \"spinnaker.invoke-pipeline\"\n              with:\n                application: \"rest.application\"\n                pipelineName: \"rest.pipelineName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipelines/{id}\n          name: pipeline\n          description: \"Pipeline execution control\"\
  \n          operations:\n            - method: GET\n              name: get-pipeline-execution\n              description: \"Get pipeline execution status and stage details\"\n              call: \"spinnaker.get-pipeline-execution\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipelines/{id}/cancel\n          name: pipeline-cancel\n          description: \"Cancel a pipeline execution\"\n          operations:\n            - method: PUT\n              name: cancel-pipeline\n              description: \"Cancel a running pipeline\"\n              call: \"spinnaker.cancel-pipeline\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipelines/{id}/pause\n          name: pipeline-pause\n          description: \"Pause a pipeline execution\"\n\
  \          operations:\n            - method: PUT\n              name: pause-pipeline\n              description: \"Pause a running pipeline\"\n              call: \"spinnaker.pause-pipeline\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipelines/{id}/resume\n          name: pipeline-resume\n          description: \"Resume a pipeline execution\"\n          operations:\n            - method: PUT\n              name: resume-pipeline\n              description: \"Resume a paused pipeline\"\n              call: \"spinnaker.resume-pipeline\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/clusters\n          name: clusters\n          description: \"Cluster management\"\n          operations:\n            - method: GET\n              name:\
  \ list-clusters\n              description: \"List clusters for an application\"\n              call: \"spinnaker.list-clusters\"\n              with:\n                application: \"rest.application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/load-balancers\n          name: load-balancers\n          description: \"Load balancer management\"\n          operations:\n            - method: GET\n              name: list-load-balancers\n              description: \"List load balancers for an application\"\n              call: \"spinnaker.list-load-balancers\"\n              with:\n                application: \"rest.application\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search\n          name: search\n          description: \"Resource search\"\n          operations:\n            - method: GET\n              name: search\n            \
  \  description: \"Search Spinnaker resources\"\n              call: \"spinnaker.search\"\n              with:\n                q: \"rest.q\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: spinnaker-cd-mcp\n      transport: http\n      description: \"MCP server for AI-assisted continuous delivery and deployment management.\"\n      tools:\n        - name: list-applications\n          description: \"List all Spinnaker applications\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.list-applications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-application\n          description: \"Get configuration and cluster summary for a Spinnaker application\"\n          hints:\n            readOnly: true\n          call: \"spinnaker.get-application\"\n          with:\n      \
  \      application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipeline-configs\n          description: \"List all pipeline configurations for a Spinnaker application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.list-pipeline-configs\"\n          with:\n            application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipeline-executions\n          description: \"List recent pipeline execution history with status for an application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.list-pipeline-executions\"\n          with:\n            application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-pipeline-execution\n\
  \          description: \"Get full status, stage details, and outputs of a specific pipeline execution\"\n          hints:\n            readOnly: true\n          call: \"spinnaker.get-pipeline-execution\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: invoke-pipeline\n          description: \"Trigger a Spinnaker pipeline execution by application and pipeline name\"\n          hints:\n            readOnly: false\n          call: \"spinnaker.invoke-pipeline\"\n          with:\n            application: \"tools.application\"\n            pipelineName: \"tools.pipeline_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-pipeline\n          description: \"Cancel a running pipeline execution\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"spinnaker.cancel-pipeline\"\
  \n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: pause-pipeline\n          description: \"Pause a running pipeline execution — it can be resumed later\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spinnaker.pause-pipeline\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: resume-pipeline\n          description: \"Resume a paused pipeline execution\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"spinnaker.resume-pipeline\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-clusters\n          description: \"List all clusters for a Spinnaker application across cloud accounts\"\n \
  \         hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.list-clusters\"\n          with:\n            application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-load-balancers\n          description: \"List load balancers associated with a Spinnaker application\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.list-load-balancers\"\n          with:\n            application: \"tools.application\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-resources\n          description: \"Search across all Spinnaker-managed resources by keyword and optional type\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"spinnaker.search\"\n          with:\n            q: \"tools.q\"\n            type: \"tools.type\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spinnaker/refs/heads/main/capabilities/continuous-delivery.yaml
tags:
- Spinnaker
- Continuous Delivery
- Pipelines
- Deployments
- Cloud Infrastructure
- DevOps
- Multi-Cloud
tools:
- description: List all Spinnaker applications
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get configuration and cluster summary for a Spinnaker application
  hints:
    readOnly: true
  name: get-application
- description: List all pipeline configurations for a Spinnaker application
  hints:
    openWorld: true
    readOnly: true
  name: list-pipeline-configs
- description: List recent pipeline execution history with status for an application
  hints:
    openWorld: true
    readOnly: true
  name: list-pipeline-executions
- description: Get full status, stage details, and outputs of a specific pipeline execution
  hints:
    readOnly: true
  name: get-pipeline-execution
- description: Trigger a Spinnaker pipeline execution by application and pipeline name
  hints:
    readOnly: false
  name: invoke-pipeline
- description: Cancel a running pipeline execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-pipeline
- description: Pause a running pipeline execution — it can be resumed later
  hints:
    idempotent: true
    readOnly: false
  name: pause-pipeline
- description: Resume a paused pipeline execution
  hints:
    idempotent: true
    readOnly: false
  name: resume-pipeline
- description: List all clusters for a Spinnaker application across cloud accounts
  hints:
    openWorld: true
    readOnly: true
  name: list-clusters
- description: List load balancers associated with a Spinnaker application
  hints:
    openWorld: true
    readOnly: true
  name: list-load-balancers
- description: Search across all Spinnaker-managed resources by keyword and optional type
  hints:
    openWorld: true
    readOnly: true
  name: search-resources
---
