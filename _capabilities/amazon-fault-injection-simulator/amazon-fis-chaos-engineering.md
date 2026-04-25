---
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
- update safety lever state
- manage specific experiment
- resilience testing
- full chaos engineering lifecycle
- deliberate fault injection to test system resilience
- monitor the status and progress of a fault injection experiment
- get template
- sres using fis to validate service resilience targets
- discover all available fault injection action types
- Resilience Engineer
- validating application behavior under failure conditions
- get experiment template
- modify targets, actions, or stop conditions of an experiment template
- DevOps Engineer
- manage experiment templates
- start experiment
- devops
- get the configuration of an experiment template
- monitoring system behavior during controlled experiments
- get action
- engage or disengage a safety lever to allow or block experiments
- list all experiments and their current status
- list templates
- list all fault injection experiment templates
- resilience
- aws fis
- get experiment
- check the status of a safety lever for experiment control
- create template
- create experiment template
- list experiments
- sre
- fault injection
- get details and parameters for a specific fis action
- execute a fault injection experiment from a template
- update experiment template
- safety lever control
- remove an experiment template
- delete template
- list experiment templates
- get safety lever
- manage specific template
- engineers integrating fis into ci/cd for automated resilience testing
- chaos engineering
- list actions
- design a new fault injection scenario with targets, actions, and stop conditions
- stop experiment
- manage experiments
- aws
- SRE
- update template
- engineers designing and running chaos experiments to improve system reliability
- abort a running fault injection experiment
- delete experiment template
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
