---
categories:
- ci-cd
consumed_apis:
- codepipeline
description: Unified workflow for DevOps and release engineering teams to create and manage delivery pipelines, trigger pipeline executions, monitor pipeline status, and manage pipeline artifacts using Amazon CodePipeline.
layout: capability
name: Amazon CodePipeline Release Pipeline Automation
operations: []
personas: []
provider_name: Amazon CodePipeline
provider_slug: amazon-codepipeline
search_terms:
- pipeline
- unified workflow for devops and release engineering teams to create and manage delivery pipelines, trigger pipeline executions, monitor pipeline statu
- stop pipeline execution
- get details about a pipeline execution
- release automation
- start pipeline execution
- update the structure of a pipeline
- list action executions for a pipeline
- get the structure and details of a pipeline
- list pipelines in the account
- create pipeline
- list pipeline webhooks
- get pipeline
- stop an in-progress pipeline execution
- delete pipeline
- list pipelines
- DevOps Engineer
- aws
- devops
- Release Manager
- get pipeline state
- devops engineer persona.
- list action executions
- continuous delivery
- release manager persona.
- put approval result
- delete a pipeline
- retry stage execution
- list pipeline executions
- get the current state of each stage in a pipeline
- update pipeline
- start a pipeline execution
- Platform Engineer
- retry all failed actions in a pipeline stage
- ci/cd
- platform engineer persona.
- unified workflow for devops and release engineering teams to create and manage delivery pipelines, t
- submit approval or rejection for a manual approval action
- amazon
- get pipeline execution
- create a new delivery pipeline
- list executions for a pipeline
- list webhooks
slug: amazon-codepipeline-release-pipeline
source_filename: amazon-codepipeline-release-pipeline.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon CodePipeline Release Pipeline Automation\n  description: Unified workflow for DevOps and release engineering teams to create and manage delivery pipelines, trigger pipeline executions, monitor pipeline status, and manage pipeline artifacts \n    using Amazon CodePipeline.\n  tags:\n  - Amazon\n  - AWS\n  - CI/CD\n  - Continuous Delivery\n  - DevOps\n  - Pipeline\n  - Release Automation\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: codepipeline\n    location: ./shared/codepipeline.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: codepipeline-release-pipeline-api\n    description: Unified REST API for Release Pipeline Automation.\n    resources:\n    - path: /v1/listPipelines\n      name: list-pipelines\n      description:\
  \ List pipelines in the account\n    - path: /v1/getPipeline\n      name: get-pipeline\n      description: Get the structure and details of a pipeline\n    - path: /v1/createPipeline\n      name: create-pipeline\n      description: Create a new delivery pipeline\n    - path: /v1/updatePipeline\n      name: update-pipeline\n      description: Update the structure of a pipeline\n  - type: mcp\n    port: 9090\n    namespace: codepipeline-release-pipeline-mcp\n    transport: http\n    description: MCP server for AI-assisted Release Pipeline Automation.\n    tools:\n    - name: list-pipelines\n      description: List pipelines in the account\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.listPipelines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline\n      description: Get the structure and details of a pipeline\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.getPipeline\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pipeline\n      description: Create a new delivery pipeline\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.createPipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-pipeline\n      description: Update the structure of a pipeline\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.updatePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-pipeline\n      description: Delete a pipeline\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.deletePipeline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-pipeline-execution\n      description: Start a pipeline execution\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.startPipelineExecution\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-pipeline-execution\n      description: Stop an in-progress pipeline execution\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.stopPipelineExecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline-execution\n      description: Get details about a pipeline execution\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.getPipelineExecution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipeline-executions\n      description: List executions for a pipeline\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.listPipelineExecutions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline-state\n      description: Get the current state of each stage in a pipeline\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: codepipeline.getPipelineState\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-action-executions\n      description: List action executions for a pipeline\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.listActionExecutions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: put-approval-result\n      description: Submit approval or rejection for a manual approval action\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.putApprovalResult\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retry-stage-execution\n      description: Retry all failed actions in a pipeline stage\n      hints:\n        readOnly: false\n        openWorld: true\n      call: codepipeline.retryStageExecution\n      outputParameters:\n      - type: object\n        mapping: $.\n \
  \   - name: list-webhooks\n      description: List pipeline webhooks\n      hints:\n        readOnly: true\n        openWorld: true\n      call: codepipeline.listWebhooks\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-codepipeline/refs/heads/main/capabilities/amazon-codepipeline-release-pipeline.yaml
tags:
- Amazon
- AWS
- CI/CD
- Continuous Delivery
- DevOps
- Pipeline
- Release Automation
tools:
- description: List pipelines in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: Get the structure and details of a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline
- description: Create a new delivery pipeline
  hints:
    openWorld: true
    readOnly: false
  name: create-pipeline
- description: Update the structure of a pipeline
  hints:
    openWorld: true
    readOnly: false
  name: update-pipeline
- description: Delete a pipeline
  hints:
    openWorld: true
    readOnly: false
  name: delete-pipeline
- description: Start a pipeline execution
  hints:
    openWorld: true
    readOnly: false
  name: start-pipeline-execution
- description: Stop an in-progress pipeline execution
  hints:
    openWorld: true
    readOnly: false
  name: stop-pipeline-execution
- description: Get details about a pipeline execution
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline-execution
- description: List executions for a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-pipeline-executions
- description: Get the current state of each stage in a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: get-pipeline-state
- description: List action executions for a pipeline
  hints:
    openWorld: true
    readOnly: true
  name: list-action-executions
- description: Submit approval or rejection for a manual approval action
  hints:
    openWorld: true
    readOnly: false
  name: put-approval-result
- description: Retry all failed actions in a pipeline stage
  hints:
    openWorld: true
    readOnly: false
  name: retry-stage-execution
- description: List pipeline webhooks
  hints:
    openWorld: true
    readOnly: true
  name: list-webhooks
---
