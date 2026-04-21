---
consumed_apis:
- google-apps-script
description: Workflow capability for managing Google Apps Script projects, deployments, versions, and script execution. Enables developers and IT admins to automate Google Workspace workflows, manage script lifecycle, and monitor execution health.
layout: capability
name: Google Workspace Automation
operations:
- description: Create a new script project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get a script project's metadata
  method: GET
  name: get-project
  path: /v1/projects/{scriptId}
- description: Get the code content of a script project
  method: GET
  name: get-project-content
  path: /v1/projects/{scriptId}/content
- description: Update the code content of a script project
  method: PUT
  name: update-project-content
  path: /v1/projects/{scriptId}/content
- description: Get execution metrics for a script project
  method: GET
  name: get-project-metrics
  path: /v1/projects/{scriptId}/metrics
- description: List deployments for a script project
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create a new deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: List versions of a script project
  method: GET
  name: list-versions
  path: /v1/versions
- description: Create a new immutable version
  method: POST
  name: create-version
  path: /v1/versions
- description: List execution processes
  method: GET
  name: list-processes
  path: /v1/processes
personas: []
provider_name: Google Apps Script
provider_slug: google-apps-script
search_terms:
- google workspace
- list deployments of an apps script project
- get the code content of a script project
- apps script
- create a new, empty script project
- list deployments for a script project
- get a specific version
- update a deployment
- delete a deployment
- get version
- get project content
- create project
- create version
- scripting
- create a new script project
- list deployments
- process monitoring
- create a new deployment
- script project management
- script project details and content
- deployment management
- script project content
- get a specific deployment
- script project metrics
- list processes
- get deployment
- deployments
- get project
- automation
- list a specific script's executed processes
- update the code content of a script project
- update project content
- get execution metrics for a script project
- list versions
- get project metrics
- create deployment
- version management
- list script processes
- update deployment
- google
- create a new immutable version
- get a script project's metadata
- run a function in an apps script project
- list versions of a script project
- create a deployment of an apps script project
- delete deployment
- list execution processes
- run script
slug: workspace-automation
tags:
- Google
- Apps Script
- Automation
- Google Workspace
tools:
- description: Create a new, empty script project
  hints:
    readOnly: false
  name: create-project
- description: Get a script project's metadata
  hints:
    openWorld: true
    readOnly: true
  name: get-project
- description: Get the code content of a script project
  hints:
    openWorld: true
    readOnly: true
  name: get-project-content
- description: Update the code content of a script project
  hints:
    idempotent: true
    readOnly: false
  name: update-project-content
- description: Get execution metrics for a script project
  hints:
    openWorld: true
    readOnly: true
  name: get-project-metrics
- description: List deployments of an Apps Script project
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Create a deployment of an Apps Script project
  hints:
    readOnly: false
  name: create-deployment
- description: Get a specific deployment
  hints:
    openWorld: true
    readOnly: true
  name: get-deployment
- description: Update a deployment
  hints:
    idempotent: true
    readOnly: false
  name: update-deployment
- description: Delete a deployment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-deployment
- description: List versions of a script project
  hints:
    openWorld: true
    readOnly: true
  name: list-versions
- description: Create a new immutable version
  hints:
    readOnly: false
  name: create-version
- description: Get a specific version
  hints:
    openWorld: true
    readOnly: true
  name: get-version
- description: Run a function in an Apps Script project
  hints:
    readOnly: false
  name: run-script
- description: List execution processes
  hints:
    openWorld: true
    readOnly: true
  name: list-processes
- description: List a specific script's executed processes
  hints:
    openWorld: true
    readOnly: true
  name: list-script-processes
---
