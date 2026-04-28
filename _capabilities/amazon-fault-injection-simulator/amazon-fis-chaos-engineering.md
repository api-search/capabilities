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
- list actions
- delete experiment template
- Resilience Engineer
- modify targets, actions, or stop conditions of an experiment template
- update template
- engineers designing and running chaos experiments to improve system reliability
- discover all available fault injection action types
- stop experiment
- monitoring system behavior during controlled experiments
- full chaos engineering lifecycle
- resilience
- SRE
- abort a running fault injection experiment
- check the status of a safety lever for experiment control
- get template
- get details and parameters for a specific fis action
- manage specific experiment
- update safety lever state
- resilience testing
- monitor the status and progress of a fault injection experiment
- get the configuration of an experiment template
- engage or disengage a safety lever to allow or block experiments
- DevOps Engineer
- remove an experiment template
- delete template
- list all experiments and their current status
- get action
- create template
- list all fault injection experiment templates
- chaos engineering
- sre
- execute a fault injection experiment from a template
- devops
- list templates
- engineers integrating fis into ci/cd for automated resilience testing
- get experiment
- aws fis
- update experiment template
- get experiment template
- get safety lever
- sres using fis to validate service resilience targets
- design a new fault injection scenario with targets, actions, and stop conditions
- manage experiments
- aws
- start experiment
- list experiment templates
- validating application behavior under failure conditions
- create experiment template
- fault injection
- deliberate fault injection to test system resilience
- safety lever control
- list experiments
- manage experiment templates
slug: amazon-fis-chaos-engineering
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
