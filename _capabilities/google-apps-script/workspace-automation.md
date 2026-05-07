---
categories:
- automation
consumed_apis: []
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
- delete deployment
- get deployment
- run script
- get execution metrics for a script project
- create a new immutable version
- automation
- apps script
- list a specific script's executed processes
- get project metrics
- script project details and content
- list versions of a script project
- list execution processes
- create a new script project
- update a deployment
- create a deployment of an apps script project
- delete a deployment
- get the code content of a script project
- update deployment
- google
- update project content
- script project management
- list deployments for a script project
- list versions
- process monitoring
- create version
- scripting
- deployment management
- create project
- list deployments of an apps script project
- deployments
- list script processes
- run a function in an apps script project
- script project metrics
- create a new deployment
- version management
- get version
- create deployment
- get project
- create a new, empty script project
- get project content
- google workspace
- script project content
- get a specific deployment
- list processes
- update the code content of a script project
- get a specific version
- get a script project's metadata
- list deployments
slug: workspace-automation
source_filename: workspace-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Workspace Automation\n  description: Workflow capability for managing Google Apps Script projects, deployments, versions, and script execution.\n    Enables developers and IT admins to automate Google Workspace workflows, manage script lifecycle, and monitor execution\n    health.\n  tags:\n  - Google\n  - Apps Script\n  - Automation\n  - Google Workspace\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: google-apps-script\n    baseUri: https://script.googleapis.com\n    description: Google Apps Script API for project management, deployments, versioning, and script execution.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_OAUTH_TOKEN}}'\n    resources:\n    - name: projects\n      path: /v1/projects\n      description: Script project management\n      operations:\n      - name:\
  \ create-project\n        method: POST\n        description: Creates a new, empty script project with no script files.\n        body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            parentId: '{{tools.parentId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: GET\n        path: /{scriptId}\n        description: Gets a script project's metadata.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project-content\n        method: GET\n        path: /{scriptId}/content\n        description: Gets the content of the script project including code source and metadata.\n  \
  \      inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: versionNumber\n          in: query\n          type: integer\n          required: false\n          description: Version number to retrieve\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-project-content\n        method: PUT\n        path: /{scriptId}/content\n        description: Updates the content of the specified script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        body:\n          type: json\n          data:\n            files: '{{tools.files}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: get-project-metrics\n        method: GET\n        path: /{scriptId}/metrics\n        description: Get metrics data for scripts such as number of executions and active users.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: metricsGranularity\n          in: query\n          type: string\n          required: false\n          description: Granularity of metrics (WEEKLY, DAILY)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployments\n      path: /v1/projects/{scriptId}/deployments\n      description: Deployment management\n      operations:\n      - name: list-deployments\n        method: GET\n        description: Lists the deployments of an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n       \
  \   type: string\n          required: true\n          description: The script project ID\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of deployments per page\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Page token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Creates a deployment of an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        body:\n          type: json\n          data:\n            versionNumber: '{{tools.versionNumber}}'\n            manifestFileName: '{{tools.manifestFileName}}'\n          \
  \  description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-deployment\n        method: GET\n        path: /{deploymentId}\n        description: Gets a deployment of an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deployment\n        method: PUT\n        path: /{deploymentId}\n        description: Updates a deployment of an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n\
  \          required: true\n          description: The script project ID\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The deployment ID\n        body:\n          type: json\n          data:\n            deploymentConfig: '{{tools.deploymentConfig}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-deployment\n        method: DELETE\n        path: /{deploymentId}\n        description: Deletes a deployment of an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The deployment ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: versions\n      path: /v1/projects/{scriptId}/versions\n      description: Version management\n      operations:\n      - name: list-versions\n        method: GET\n        description: List the versions of a script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of versions per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-version\n        method: POST\n        description: Creates a new immutable version using the current code.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description:\
  \ The script project ID\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-version\n        method: GET\n        path: /{versionNumber}\n        description: Gets a version of a script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        - name: versionNumber\n          in: path\n          type: integer\n          required: true\n          description: The version number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scripts\n      path: /v1/scripts\n      description: Script execution\n      operations:\n      - name: run-script\n        method: POST\n        path: /{scriptId}:run\n\
  \        description: Runs a function in an Apps Script project.\n        inputParameters:\n        - name: scriptId\n          in: path\n          type: string\n          required: true\n          description: The script project ID\n        body:\n          type: json\n          data:\n            function: '{{tools.function}}'\n            parameters: '{{tools.parameters}}'\n            devMode: '{{tools.devMode}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: processes\n      path: /v1/processes\n      description: Process monitoring\n      operations:\n      - name: list-processes\n        method: GET\n        description: List information about processes made by or on behalf of a user.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of processes per page\n        - name: pageToken\n\
  \          in: query\n          type: string\n          required: false\n          description: Page token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-script-processes\n        method: GET\n        path: :listScriptProcesses\n        description: List information about a script's executed processes.\n        inputParameters:\n        - name: scriptId\n          in: query\n          type: string\n          required: true\n          description: The script project ID\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of processes per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workspace-automation-api\n    description: Unified REST API for Google\
  \ Workspace automation via Apps Script project management, deployment, and execution.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Script project management\n      operations:\n      - method: POST\n        name: create-project\n        description: Create a new script project\n        call: google-apps-script.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{scriptId}\n      name: project-detail\n      description: Script project details and content\n      operations:\n      - method: GET\n        name: get-project\n        description: Get a script project's metadata\n        call: google-apps-script.get-project\n        with:\n          scriptId: rest.scriptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{scriptId}/content\n      name: project-content\n      description: Script project content\n      operations:\n      - method:\
  \ GET\n        name: get-project-content\n        description: Get the code content of a script project\n        call: google-apps-script.get-project-content\n        with:\n          scriptId: rest.scriptId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-project-content\n        description: Update the code content of a script project\n        call: google-apps-script.update-project-content\n        with:\n          scriptId: rest.scriptId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{scriptId}/metrics\n      name: project-metrics\n      description: Script project metrics\n      operations:\n      - method: GET\n        name: get-project-metrics\n        description: Get execution metrics for a script project\n        call: google-apps-script.get-project-metrics\n        with:\n          scriptId: rest.scriptId\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/deployments\n      name: deployments\n      description: Deployment management\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List deployments for a script project\n        call: google-apps-script.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n        description: Create a new deployment\n        call: google-apps-script.create-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/versions\n      name: versions\n      description: Version management\n      operations:\n      - method: GET\n        name: list-versions\n        description: List versions of a script project\n        call: google-apps-script.list-versions\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-version\n        description:\
  \ Create a new immutable version\n        call: google-apps-script.create-version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/processes\n      name: processes\n      description: Process monitoring\n      operations:\n      - method: GET\n        name: list-processes\n        description: List execution processes\n        call: google-apps-script.list-processes\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workspace-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Workspace automation via Apps Script management and execution.\n    tools:\n    - name: create-project\n      description: Create a new, empty script project\n      hints:\n        readOnly: false\n      call: google-apps-script.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get a script\
  \ project's metadata\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.get-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project-content\n      description: Get the code content of a script project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.get-project-content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-project-content\n      description: Update the code content of a script project\n      hints:\n        readOnly: false\n        idempotent: true\n      call: google-apps-script.update-project-content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project-metrics\n      description: Get execution metrics for a script project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.get-project-metrics\n      outputParameters:\n \
  \     - type: object\n        mapping: $.\n    - name: list-deployments\n      description: List deployments of an Apps Script project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n      description: Create a deployment of an Apps Script project\n      hints:\n        readOnly: false\n      call: google-apps-script.create-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get a specific deployment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.get-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-deployment\n      description: Update a deployment\n      hints:\n        readOnly: false\n        idempotent: true\n      call: google-apps-script.update-deployment\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-deployment\n      description: Delete a deployment\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-apps-script.delete-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-versions\n      description: List versions of a script project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.list-versions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-version\n      description: Create a new immutable version\n      hints:\n        readOnly: false\n      call: google-apps-script.create-version\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-version\n      description: Get a specific version\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.get-version\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-script\n      description: Run a function in an Apps Script project\n      hints:\n        readOnly: false\n      call: google-apps-script.run-script\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-processes\n      description: List execution processes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.list-processes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-script-processes\n      description: List a specific script's executed processes\n      hints:\n        readOnly: true\n        openWorld: true\n      call: google-apps-script.list-script-processes\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
