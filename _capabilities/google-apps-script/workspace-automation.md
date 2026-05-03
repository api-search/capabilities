---
categories:
- automation
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
- update project content
- create a new deployment
- get project metrics
- list versions
- create a new immutable version
- get the code content of a script project
- get project content
- create project
- get a specific version
- automation
- deployment management
- run script
- script project management
- update the code content of a script project
- create deployment
- version management
- process monitoring
- list deployments for a script project
- deployments
- list execution processes
- google
- get deployment
- script project metrics
- get version
- get a specific deployment
- list versions of a script project
- delete deployment
- script project details and content
- list processes
- scripting
- delete a deployment
- apps script
- create a new script project
- script project content
- get project
- get a script project's metadata
- run a function in an apps script project
- create a deployment of an apps script project
- list deployments of an apps script project
- google workspace
- list deployments
- list a specific script's executed processes
- create version
- update a deployment
- create a new, empty script project
- update deployment
- list script processes
- get execution metrics for a script project
slug: workspace-automation
source_filename: workspace-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Workspace Automation\"\n  description: \"Workflow capability for managing Google Apps Script projects, deployments, versions, and script execution. Enables developers and IT admins to automate Google Workspace workflows, manage script lifecycle, and monitor execution health.\"\n  tags:\n    - Google\n    - Apps Script\n    - Automation\n    - Google Workspace\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: google-apps-script\n      location: ./shared/apps-script.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: workspace-automation-api\n      description: \"Unified REST API for Google Workspace automation via Apps Script project management, deployment, and execution.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description:\
  \ \"Script project management\"\n          operations:\n            - method: POST\n              name: create-project\n              description: \"Create a new script project\"\n              call: \"google-apps-script.create-project\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{scriptId}\n          name: project-detail\n          description: \"Script project details and content\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get a script project's metadata\"\n              call: \"google-apps-script.get-project\"\n              with:\n                scriptId: \"rest.scriptId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{scriptId}/content\n          name: project-content\n          description: \"Script project content\"\n          operations:\n\
  \            - method: GET\n              name: get-project-content\n              description: \"Get the code content of a script project\"\n              call: \"google-apps-script.get-project-content\"\n              with:\n                scriptId: \"rest.scriptId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-project-content\n              description: \"Update the code content of a script project\"\n              call: \"google-apps-script.update-project-content\"\n              with:\n                scriptId: \"rest.scriptId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{scriptId}/metrics\n          name: project-metrics\n          description: \"Script project metrics\"\n          operations:\n            - method: GET\n              name: get-project-metrics\n              description:\
  \ \"Get execution metrics for a script project\"\n              call: \"google-apps-script.get-project-metrics\"\n              with:\n                scriptId: \"rest.scriptId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments\n          name: deployments\n          description: \"Deployment management\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List deployments for a script project\"\n              call: \"google-apps-script.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Create a new deployment\"\n              call: \"google-apps-script.create-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n   \
  \     - path: /v1/versions\n          name: versions\n          description: \"Version management\"\n          operations:\n            - method: GET\n              name: list-versions\n              description: \"List versions of a script project\"\n              call: \"google-apps-script.list-versions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-version\n              description: \"Create a new immutable version\"\n              call: \"google-apps-script.create-version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/processes\n          name: processes\n          description: \"Process monitoring\"\n          operations:\n            - method: GET\n              name: list-processes\n              description: \"List execution processes\"\n              call: \"google-apps-script.list-processes\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: workspace-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Workspace automation via Apps Script management and execution.\"\n      tools:\n        - name: create-project\n          description: \"Create a new, empty script project\"\n          hints:\n            readOnly: false\n          call: \"google-apps-script.create-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project\n          description: \"Get a script project's metadata\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.get-project\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project-content\n          description: \"Get the code\
  \ content of a script project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.get-project-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-project-content\n          description: \"Update the code content of a script project\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"google-apps-script.update-project-content\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project-metrics\n          description: \"Get execution metrics for a script project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.get-project-metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-deployments\n          description: \"List deployments\
  \ of an Apps Script project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.list-deployments\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-deployment\n          description: \"Create a deployment of an Apps Script project\"\n          hints:\n            readOnly: false\n          call: \"google-apps-script.create-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-deployment\n          description: \"Get a specific deployment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.get-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-deployment\n          description: \"Update a deployment\"\n          hints:\n            readOnly: false\n            idempotent:\
  \ true\n          call: \"google-apps-script.update-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-deployment\n          description: \"Delete a deployment\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"google-apps-script.delete-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-versions\n          description: \"List versions of a script project\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.list-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-version\n          description: \"Create a new immutable version\"\n          hints:\n            readOnly: false\n          call: \"google-apps-script.create-version\"\n     \
  \     outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-version\n          description: \"Get a specific version\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.get-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-script\n          description: \"Run a function in an Apps Script project\"\n          hints:\n            readOnly: false\n          call: \"google-apps-script.run-script\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-processes\n          description: \"List execution processes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.list-processes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-script-processes\n\
  \          description: \"List a specific script's executed processes\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"google-apps-script.list-script-processes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-apps-script/refs/heads/main/capabilities/workspace-automation.yaml
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
