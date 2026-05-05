---
categories: []
consumed_apis:
- spacelift
description: Workflow capability for orchestrating infrastructure deployments through Spacelift. Enables platform engineers and DevOps teams to manage IaC stacks, trigger deployments, enforce governance policies, and monitor worker pool health programmatically.
layout: capability
name: Spacelift Infrastructure Orchestration
operations:
- description: List all infrastructure stacks with state and configuration
  method: GET
  name: list-stacks
  path: /v1/stacks
- description: Create a new infrastructure stack
  method: POST
  name: create-stack
  path: /v1/stacks
- description: Trigger a new deployment run on a stack
  method: POST
  name: create-run
  path: /v1/runs
- description: List all governance policies in the account
  method: GET
  name: list-policies
  path: /v1/policies
- description: List all shared contexts available for stack attachment
  method: GET
  name: list-contexts
  path: /v1/contexts
- description: List all worker pools and their current worker status
  method: GET
  name: list-worker-pools
  path: /v1/worker-pools
personas: []
provider_name: Spacelift
provider_slug: spacelift
search_terms:
- list stacks
- shared environment variable contexts
- finops
- infrastructure stacks managed by spacelift
- gitops
- terraform
- governance policies (opa/rego)
- trigger a new deployment run on a stack
- list all shared contexts containing environment variables and files for stacks
- list all worker pools and their worker health status
- list contexts
- create stack
- platform engineering
- list all worker pools and their current worker status
- list all governance policies in the account
- create run
- devops
- infrastructure deployment runs
- create a new infrastructure stack
- worker pools for running infrastructure jobs
- create a new infrastructure stack in spacelift connected to a source repository
- list all shared contexts available for stack attachment
- list worker pools
- list all spacelift infrastructure stacks with their current state, repository, and deployment configuration
- list all infrastructure stacks with state and configuration
- infrastructure as code
- list policies
- trigger a new infrastructure deployment run on a spacelift stack
- list all governance policies (opa/rego) enforcing infrastructure deployment rules
- trigger run
slug: infrastructure-orchestration
source_filename: infrastructure-orchestration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Spacelift Infrastructure Orchestration\n  description: >-\n    Workflow capability for orchestrating infrastructure deployments through Spacelift.\n    Enables platform engineers and DevOps teams to manage IaC stacks, trigger deployments,\n    enforce governance policies, and monitor worker pool health programmatically.\n  tags:\n    - Infrastructure as Code\n    - DevOps\n    - Platform Engineering\n    - Terraform\n    - GitOps\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SPACELIFT_API_KEY_ID: SPACELIFT_API_KEY_ID\n      SPACELIFT_API_KEY_SECRET: SPACELIFT_API_KEY_SECRET\n      SPACELIFT_ACCOUNT: SPACELIFT_ACCOUNT\n\ncapability:\n  consumes:\n    - import: spacelift\n      location: ./shared/spacelift.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: spacelift-orchestration-api\n      description: Unified REST API for infrastructure orchestration via\
  \ Spacelift.\n      resources:\n        - path: /v1/stacks\n          name: stacks\n          description: Infrastructure stacks managed by Spacelift\n          operations:\n            - method: GET\n              name: list-stacks\n              description: List all infrastructure stacks with state and configuration\n              call: \"spacelift.list-stacks\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.stacks\"\n            - method: POST\n              name: create-stack\n              description: Create a new infrastructure stack\n              call: \"spacelift.create-stack\"\n              with:\n                input: \"rest.body\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.stackCreate\"\n        - path: /v1/runs\n          name: runs\n          description: Infrastructure deployment runs\n          operations:\n            - method: POST\n              name:\
  \ create-run\n              description: Trigger a new deployment run on a stack\n              call: \"spacelift.create-run\"\n              with:\n                stack: \"rest.stack\"\n                message: \"rest.message\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.runCreate\"\n        - path: /v1/policies\n          name: policies\n          description: Governance policies (OPA/Rego)\n          operations:\n            - method: GET\n              name: list-policies\n              description: List all governance policies in the account\n              call: \"spacelift.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.policies\"\n        - path: /v1/contexts\n          name: contexts\n          description: Shared environment variable contexts\n          operations:\n            - method: GET\n              name: list-contexts\n              description:\
  \ List all shared contexts available for stack attachment\n              call: \"spacelift.list-contexts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.contexts\"\n        - path: /v1/worker-pools\n          name: worker-pools\n          description: Worker pools for running infrastructure jobs\n          operations:\n            - method: GET\n              name: list-worker-pools\n              description: List all worker pools and their current worker status\n              call: \"spacelift.list-worker-pools\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data.workerPools\"\n\n    - type: mcp\n      port: 9090\n      namespace: spacelift-orchestration-mcp\n      transport: http\n      description: MCP server for AI-assisted infrastructure orchestration via Spacelift.\n      tools:\n        - name: list-stacks\n          description: List all Spacelift infrastructure stacks with\
  \ their current state, repository, and deployment configuration\n          hints:\n            readOnly: true\n          call: \"spacelift.list-stacks\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data.stacks\"\n        - name: create-stack\n          description: Create a new infrastructure stack in Spacelift connected to a source repository\n          hints:\n            readOnly: false\n          call: \"spacelift.create-stack\"\n          with:\n            input: \"tools.input\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data.stackCreate\"\n        - name: trigger-run\n          description: Trigger a new infrastructure deployment run on a Spacelift stack\n          hints:\n            readOnly: false\n          call: \"spacelift.create-run\"\n          with:\n            stack: \"tools.stack\"\n            message: \"tools.message\"\n          outputParameters:\n            - type: object\n       \
  \       mapping: \"$.data.runCreate\"\n        - name: list-policies\n          description: List all governance policies (OPA/Rego) enforcing infrastructure deployment rules\n          hints:\n            readOnly: true\n          call: \"spacelift.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data.policies\"\n        - name: list-contexts\n          description: List all shared contexts containing environment variables and files for stacks\n          hints:\n            readOnly: true\n          call: \"spacelift.list-contexts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data.contexts\"\n        - name: list-worker-pools\n          description: List all worker pools and their worker health status\n          hints:\n            readOnly: true\n          call: \"spacelift.list-worker-pools\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data.workerPools\"\
  \n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/spacelift/refs/heads/main/capabilities/infrastructure-orchestration.yaml
tags:
- Infrastructure as Code
- DevOps
- Platform Engineering
- Terraform
- GitOps
tools:
- description: List all Spacelift infrastructure stacks with their current state, repository, and deployment configuration
  hints:
    readOnly: true
  name: list-stacks
- description: Create a new infrastructure stack in Spacelift connected to a source repository
  hints:
    readOnly: false
  name: create-stack
- description: Trigger a new infrastructure deployment run on a Spacelift stack
  hints:
    readOnly: false
  name: trigger-run
- description: List all governance policies (OPA/Rego) enforcing infrastructure deployment rules
  hints:
    readOnly: true
  name: list-policies
- description: List all shared contexts containing environment variables and files for stacks
  hints:
    readOnly: true
  name: list-contexts
- description: List all worker pools and their worker health status
  hints:
    readOnly: true
  name: list-worker-pools
---
