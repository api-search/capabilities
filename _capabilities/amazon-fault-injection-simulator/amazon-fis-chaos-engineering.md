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
- list experiment templates
- list all experiments and their current status
- discover all available fault injection action types
- stop experiment
- engage or disengage a safety lever to allow or block experiments
- manage experiment templates
- update experiment template
- monitor the status and progress of a fault injection experiment
- modify targets, actions, or stop conditions of an experiment template
- manage specific template
- validating application behavior under failure conditions
- get the configuration of an experiment template
- design a new fault injection scenario with targets, actions, and stop conditions
- manage specific experiment
- monitoring system behavior during controlled experiments
- aws
- get action
- delete experiment template
- get template
- engineers integrating fis into ci/cd for automated resilience testing
- create experiment template
- chaos engineering
- list experiments
- fault injection
- engineers designing and running chaos experiments to improve system reliability
- get experiment
- sre
- resilience testing
- execute a fault injection experiment from a template
- list templates
- create template
- list actions
- deliberate fault injection to test system resilience
- get safety lever
- abort a running fault injection experiment
- SRE
- devops
- aws fis
- start experiment
- get details and parameters for a specific fis action
- update template
- manage experiments
- get experiment template
- safety lever control
- check the status of a safety lever for experiment control
- list all fault injection experiment templates
- delete template
- update safety lever state
- DevOps Engineer
- Resilience Engineer
- sres using fis to validate service resilience targets
- resilience
- remove an experiment template
- full chaos engineering lifecycle
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
