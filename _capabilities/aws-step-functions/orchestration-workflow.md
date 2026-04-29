---
categories:
- container-orchestration
consumed_apis:
- step-functions
description: Workflow capability for managing state machines and executions with AWS Step Functions.
layout: capability
name: AWS Step Functions Orchestration Workflow
operations: []
personas: []
provider_name: AWS Step Functions
provider_slug: aws-step-functions
search_terms:
- stop_execution
- list_state_machines
- ipaas
- orchestration
- stop a running state machine execution
- create a new step functions state machine
- serverless
- describe_execution
- state machine
- start_execution
- list executions for a state machine
- aws
- workflows
- delete_state_machine
- list all step functions state machines
- create_state_machine
- start an execution of a state machine
- list_executions
- delete a step functions state machine
- get details about a state machine execution
slug: orchestration-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: AWS Step Functions Orchestration Workflow\n  description: Workflow capability for managing state machines and executions with AWS Step Functions.\n  tags:\n    - Orchestration\n    - Serverless\n    - Workflows\n    - State Machine\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n    - import: step-functions\n      location: ./shared/step-functions.yaml\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workflow-api\n      resources:\n        - label: Create State Machine\n          method: POST\n          path: /state-machines\n        - label: List State Machines\n          method: GET\n          path: /state-machines\n        - label: Delete State Machine\n          method: DELETE\n          path: /state-machines/{arn}\n\
  \        - label: Start Execution\n          method: POST\n          path: /executions\n        - label: Stop Execution\n          method: DELETE\n          path: /executions/{arn}\n        - label: Describe Execution\n          method: GET\n          path: /executions/{arn}\n        - label: List Executions\n          method: GET\n          path: /executions\n    - type: mcp\n      port: 9090\n      namespace: workflow-mcp\n      transport: http\n      tools:\n        - name: create_state_machine\n          description: Create a new Step Functions state machine\n        - name: list_state_machines\n          description: List all Step Functions state machines\n        - name: delete_state_machine\n          description: Delete a Step Functions state machine\n        - name: start_execution\n          description: Start an execution of a state machine\n        - name: stop_execution\n          description: Stop a running state machine execution\n        - name: describe_execution\n   \
  \       description: Get details about a state machine execution\n        - name: list_executions\n          description: List executions for a state machine\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-step-functions/refs/heads/main/capabilities/orchestration-workflow.yaml
tags:
- Orchestration
- Serverless
- Workflows
- State Machine
tools:
- description: Create a new Step Functions state machine
  hints: {}
  name: create_state_machine
- description: List all Step Functions state machines
  hints: {}
  name: list_state_machines
- description: Delete a Step Functions state machine
  hints: {}
  name: delete_state_machine
- description: Start an execution of a state machine
  hints: {}
  name: start_execution
- description: Stop a running state machine execution
  hints: {}
  name: stop_execution
- description: Get details about a state machine execution
  hints: {}
  name: describe_execution
- description: List executions for a state machine
  hints: {}
  name: list_executions
---
