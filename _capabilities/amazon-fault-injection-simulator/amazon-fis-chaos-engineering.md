---
categories: []
consumed_apis:
- fis
description: Workflow capability for executing chaos engineering experiments using AWS FIS. Enables resilience engineers and SREs to design, execute, and monitor fault injection experiments across AWS infrastructure.
layout: capability
name: AWS FIS Chaos Engineering
operations:
- description: List templates
  method: GET
  name: list-experiment-templates
  path: /v1/experiment-templates
- description: Create template
  method: POST
  name: create-experiment-template
  path: /v1/experiment-templates
- description: Get template
  method: GET
  name: get-experiment-template
  path: /v1/experiment-templates/{id}
- description: Update template
  method: PATCH
  name: update-experiment-template
  path: /v1/experiment-templates/{id}
- description: Delete template
  method: DELETE
  name: delete-experiment-template
  path: /v1/experiment-templates/{id}
- description: List experiments
  method: GET
  name: list-experiments
  path: /v1/experiments
- description: Start experiment
  method: POST
  name: start-experiment
  path: /v1/experiments
- description: Get experiment
  method: GET
  name: get-experiment
  path: /v1/experiments/{id}
- description: Stop experiment
  method: DELETE
  name: stop-experiment
  path: /v1/experiments/{id}
- description: Get safety lever
  method: GET
  name: get-safety-lever
  path: /v1/safety-levers/{id}
- description: Update safety lever state
  method: PATCH
  name: update-safety-lever-state
  path: /v1/safety-levers/{id}
personas: []
provider_name: Amazon Fault Injection Simulator
provider_slug: amazon-fault-injection-simulator
search_terms:
- manage specific template
- list all experiments and their current status
- remove an experiment template
- full chaos engineering lifecycle
- discover all available fault injection action types
- get template
- update experiment template
- get the configuration of an experiment template
- monitor the status and progress of a fault injection experiment
- get safety lever
- SRE
- monitoring system behavior during controlled experiments
- resilience testing
- DevOps Engineer
- check the status of a safety lever for experiment control
- sre
- list experiments
- design a new fault injection scenario with targets, actions, and stop conditions
- list all fault injection experiment templates
- safety lever control
- Resilience Engineer
- engineers integrating fis into ci/cd for automated resilience testing
- create experiment template
- list templates
- aws
- validating application behavior under failure conditions
- devops
- list experiment templates
- manage specific experiment
- get action
- update template
- get experiment template
- start experiment
- engineers designing and running chaos experiments to improve system reliability
- modify targets, actions, or stop conditions of an experiment template
- sres using fis to validate service resilience targets
- get details and parameters for a specific fis action
- abort a running fault injection experiment
- deliberate fault injection to test system resilience
- fault injection
- execute a fault injection experiment from a template
- aws fis
- resilience
- engage or disengage a safety lever to allow or block experiments
- update safety lever state
- stop experiment
- delete experiment template
- delete template
- chaos engineering
- manage experiment templates
- get experiment
- list actions
- manage experiments
- create template
slug: amazon-fis-chaos-engineering
source_filename: amazon-fis-chaos-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: AWS FIS Chaos Engineering\n  description: Workflow capability for executing chaos engineering experiments using AWS FIS. Enables resilience engineers and SREs to design, execute, and monitor fault injection experiments across \n    AWS infrastructure.\n  tags:\n  - AWS FIS\n  - Chaos Engineering\n  - Resilience\n  - SRE\n  - DevOps\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: fis\n    location: ./shared/fis.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fis-chaos-api\n    description: Unified REST API for AWS FIS chaos engineering workflows.\n    resources:\n    - path: /v1/experiment-templates\n      name: experiment-templates\n      description: Manage experiment templates\n      operations:\n      - method: GET\n     \
  \   name: list-experiment-templates\n        description: List templates\n        call: fis.list-experiment-templates\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-experiment-template\n        description: Create template\n        call: fis.create-experiment-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiment-templates/{id}\n      name: experiment-template\n      description: Manage specific template\n      operations:\n      - method: GET\n        name: get-experiment-template\n        description: Get template\n        call: fis.get-experiment-template\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-experiment-template\n        description: Update template\n        call: fis.update-experiment-template\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method:\
  \ DELETE\n        name: delete-experiment-template\n        description: Delete template\n        call: fis.delete-experiment-template\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments\n      name: experiments\n      description: Manage experiments\n      operations:\n      - method: GET\n        name: list-experiments\n        description: List experiments\n        call: fis.list-experiments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-experiment\n        description: Start experiment\n        call: fis.start-experiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/experiments/{id}\n      name: experiment\n      description: Manage specific experiment\n      operations:\n      - method: GET\n        name: get-experiment\n        description: Get experiment\n        call: fis.get-experiment\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: DELETE\n        name: stop-experiment\n        description: Stop experiment\n        call: fis.stop-experiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/safety-levers/{id}\n      name: safety-lever\n      description: Safety lever control\n      operations:\n      - method: GET\n        name: get-safety-lever\n        description: Get safety lever\n        call: fis.get-safety-lever\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PATCH\n        name: update-safety-lever-state\n        description: Update safety lever state\n        call: fis.update-safety-lever-state\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fis-chaos-mcp\n    transport: http\n    description: MCP server for AI-assisted chaos engineering with AWS FIS.\n    tools:\n    - name: list-experiment-templates\n\
  \      description: List all fault injection experiment templates\n      hints:\n        readOnly: true\n        openWorld: true\n      call: fis.list-experiment-templates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-experiment-template\n      description: Design a new fault injection scenario with targets, actions, and stop conditions\n      hints:\n        readOnly: false\n      call: fis.create-experiment-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-experiment-template\n      description: Get the configuration of an experiment template\n      hints:\n        readOnly: true\n      call: fis.get-experiment-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-experiment-template\n      description: Modify targets, actions, or stop conditions of an experiment template\n      hints:\n        readOnly: false\n      call: fis.update-experiment-template\n \
  \     outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-experiment-template\n      description: Remove an experiment template\n      hints:\n        readOnly: false\n        destructive: true\n      call: fis.delete-experiment-template\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-experiment\n      description: Execute a fault injection experiment from a template\n      hints:\n        readOnly: false\n        destructive: true\n      call: fis.start-experiment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-experiment\n      description: Monitor the status and progress of a fault injection experiment\n      hints:\n        readOnly: true\n      call: fis.get-experiment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-experiments\n      description: List all experiments and their current status\n      hints:\n        readOnly: true\n      call:\
  \ fis.list-experiments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-experiment\n      description: Abort a running fault injection experiment\n      hints:\n        readOnly: false\n        destructive: true\n      call: fis.stop-experiment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-actions\n      description: Discover all available fault injection action types\n      hints:\n        readOnly: true\n      call: fis.list-actions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-action\n      description: Get details and parameters for a specific FIS action\n      hints:\n        readOnly: true\n      call: fis.get-action\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-safety-lever\n      description: Check the status of a safety lever for experiment control\n      hints:\n        readOnly: true\n      call: fis.get-safety-lever\n   \
  \   outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-safety-lever-state\n      description: Engage or disengage a safety lever to allow or block experiments\n      hints:\n        readOnly: false\n      call: fis.update-safety-lever-state\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-fault-injection-simulator/refs/heads/main/capabilities/amazon-fis-chaos-engineering.yaml
tags:
- AWS FIS
- Chaos Engineering
- Resilience
- SRE
- DevOps
tools:
- description: List all fault injection experiment templates
  hints:
    openWorld: true
    readOnly: true
  name: list-experiment-templates
- description: Design a new fault injection scenario with targets, actions, and stop conditions
  hints:
    readOnly: false
  name: create-experiment-template
- description: Get the configuration of an experiment template
  hints:
    readOnly: true
  name: get-experiment-template
- description: Modify targets, actions, or stop conditions of an experiment template
  hints:
    readOnly: false
  name: update-experiment-template
- description: Remove an experiment template
  hints:
    destructive: true
    readOnly: false
  name: delete-experiment-template
- description: Execute a fault injection experiment from a template
  hints:
    destructive: true
    readOnly: false
  name: start-experiment
- description: Monitor the status and progress of a fault injection experiment
  hints:
    readOnly: true
  name: get-experiment
- description: List all experiments and their current status
  hints:
    readOnly: true
  name: list-experiments
- description: Abort a running fault injection experiment
  hints:
    destructive: true
    readOnly: false
  name: stop-experiment
- description: Discover all available fault injection action types
  hints:
    readOnly: true
  name: list-actions
- description: Get details and parameters for a specific FIS action
  hints:
    readOnly: true
  name: get-action
- description: Check the status of a safety lever for experiment control
  hints:
    readOnly: true
  name: get-safety-lever
- description: Engage or disengage a safety lever to allow or block experiments
  hints:
    readOnly: false
  name: update-safety-lever-state
---
