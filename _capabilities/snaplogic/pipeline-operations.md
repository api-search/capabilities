---
categories: []
consumed_apis: []
description: Unified workflow capability for monitoring, controlling, and managing SnapLogic integration pipeline executions. Provides operations teams, DataOps engineers, and platform administrators with programmatic access to pipeline execution state, performance metrics, and operational controls. Uses the SnapLogic Public APIs for runtime management and asset control.
layout: capability
name: SnapLogic Pipeline Operations
operations:
- description: List Pipeline Executions
  method: GET
  name: list-executions
  path: /v1/executions
- description: Get Pipeline Execution
  method: GET
  name: get-execution
  path: /v1/executions/{ruuid}
- description: Stop Pipeline Execution
  method: POST
  name: stop-execution
  path: /v1/executions/{ruuid}/stop
- description: Get Execution Metrics
  method: GET
  name: get-metrics
  path: /v1/metrics
- description: Get Asset Privileges
  method: GET
  name: get-privileges
  path: /v1/assets/{path}/privileges
- description: Create Project
  method: POST
  name: create-project
  path: /v1/projects/{path}
- description: Delete Project
  method: DELETE
  name: delete-project
  path: /v1/projects/{path}
personas: []
provider_name: SnapLogic
provider_slug: snaplogic
search_terms:
- asset access control management
- data integration
- integration
- get metrics
- retrieve pipeline execution performance metrics and concurrency stats for the snaplogic org
- grant asset access
- get privileges
- get the status and details of a specific snaplogic pipeline execution
- stop a running snaplogic pipeline execution by its runtime uuid
- get current user's access privileges for a snaplogic project or asset path
- create a new snaplogic project or project space
- monitoring
- get asset privileges
- ai
- create project
- get pipeline execution
- project lifecycle management
- list executions
- integrations
- ipaas
- delete project
- list all pipeline executions
- stop a running pipeline execution
- list pipeline executions
- list all running and recent pipeline executions in the snaplogic organization
- get execution metrics
- grant access permissions to a user or group for a snaplogic project
- api management
- management
- pipeline execution performance metrics
- stop execution
- get execution
- dataops
- get or control a specific execution
- delete a snaplogic project or project space
- snaplogic
- stop pipeline execution
- automation
slug: pipeline-operations
source_filename: pipeline-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SnapLogic Pipeline Operations\n  description: Unified workflow capability for monitoring, controlling, and managing SnapLogic integration pipeline executions.\n    Provides operations teams, DataOps engineers, and platform administrators with programmatic access to pipeline execution\n    state, performance metrics, and operational controls. Uses the SnapLogic Public APIs for runtime management and asset\n    control.\n  tags:\n  - Automation\n  - DataOps\n  - Integration\n  - iPaaS\n  - Monitoring\n  - SnapLogic\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SNAPLOGIC_JWT_TOKEN: SNAPLOGIC_JWT_TOKEN\n    SNAPLOGIC_ORG: SNAPLOGIC_ORG\ncapability:\n  consumes:\n  - type: http\n    namespace: snaplogic-api\n    baseUri: https://{{SNAPLOGIC_ORG}}.snaplogic.com/api/1\n    description: SnapLogic Public APIs for platform management and pipeline execution\n    authentication:\n      type: bearer\n  \
  \    token: '{{SNAPLOGIC_JWT_TOKEN}}'\n    resources:\n    - name: pipeline-executions\n      path: /runtime/{{SNAPLOGIC_ORG}}\n      description: List and manage pipeline executions\n      operations:\n      - name: list-pipeline-executions\n        method: GET\n        description: List Pipeline Executions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipeline-execution\n      path: /runtime/{{SNAPLOGIC_ORG}}/{ruuid}\n      description: Manage a specific pipeline execution\n      operations:\n      - name: get-pipeline-execution\n        method: GET\n        description: Get Pipeline Execution\n        inputParameters:\n        - name: ruuid\n          in: path\n          type: string\n          required: true\n          description: Runtime UUID of the pipeline execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: stop-pipeline\n      path: /runtime/stop/{{SNAPLOGIC_ORG}}/{ruuid}\n      description: Stop a running pipeline\n      operations:\n      - name: stop-pipeline-execution\n        method: POST\n        description: Stop Pipeline Execution\n        inputParameters:\n        - name: ruuid\n          in: path\n          type: string\n          required: true\n          description: Runtime UUID of the pipeline execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: execution-metrics\n      path: /runtime/apistats/{{SNAPLOGIC_ORG}}\n      description: Retrieve execution performance metrics\n      operations:\n      - name: get-execution-metrics\n        method: GET\n        description: Get Execution Metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: asset-acl\n      path: /assetapi/acl/{path}\n\
  \      description: Manage asset access control\n      operations:\n      - name: get-asset-privileges\n        method: GET\n        description: Get Asset Privileges\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: grant-asset-access\n        method: POST\n        description: Grant Asset Access\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the asset\n        body:\n          type: json\n          data:\n            perms: '{{tools.perms}}'\n            users: '{{tools.users}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path:\
  \ /assetapi/project/{path}\n      description: Manage projects and project spaces\n      operations:\n      - name: create-project\n        method: POST\n        description: Create Project\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path for the new project\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete Project\n        inputParameters:\n        - name: path\n          in: path\n          type: string\n          required: true\n          description: Path to the project to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type:\
  \ rest\n    port: 8080\n    namespace: snaplogic-ops-api\n    description: Unified REST API for SnapLogic pipeline operations and platform management.\n    resources:\n    - path: /v1/executions\n      name: executions\n      description: List all pipeline executions\n      operations:\n      - method: GET\n        name: list-executions\n        description: List Pipeline Executions\n        call: snaplogic-api.list-pipeline-executions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{ruuid}\n      name: execution\n      description: Get or control a specific execution\n      operations:\n      - method: GET\n        name: get-execution\n        description: Get Pipeline Execution\n        call: snaplogic-api.get-pipeline-execution\n        with:\n          ruuid: rest.ruuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{ruuid}/stop\n      name: stop-execution\n      description:\
  \ Stop a running pipeline execution\n      operations:\n      - method: POST\n        name: stop-execution\n        description: Stop Pipeline Execution\n        call: snaplogic-api.stop-pipeline-execution\n        with:\n          ruuid: rest.ruuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/metrics\n      name: metrics\n      description: Pipeline execution performance metrics\n      operations:\n      - method: GET\n        name: get-metrics\n        description: Get Execution Metrics\n        call: snaplogic-api.get-execution-metrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets/{path}/privileges\n      name: asset-privileges\n      description: Asset access control management\n      operations:\n      - method: GET\n        name: get-privileges\n        description: Get Asset Privileges\n        call: snaplogic-api.get-asset-privileges\n        with:\n          path: rest.path\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{path}\n      name: projects\n      description: Project lifecycle management\n      operations:\n      - method: POST\n        name: create-project\n        description: Create Project\n        call: snaplogic-api.create-project\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-project\n        description: Delete Project\n        call: snaplogic-api.delete-project\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: snaplogic-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted SnapLogic pipeline operations and platform management.\n    tools:\n    - name: list-pipeline-executions\n      description: List all running and recent pipeline executions in\
  \ the SnapLogic organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snaplogic-api.list-pipeline-executions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-pipeline-execution\n      description: Get the status and details of a specific SnapLogic pipeline execution\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snaplogic-api.get-pipeline-execution\n      with:\n        ruuid: tools.ruuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-pipeline-execution\n      description: Stop a running SnapLogic pipeline execution by its runtime UUID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snaplogic-api.stop-pipeline-execution\n      with:\n        ruuid: tools.ruuid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-metrics\n      description: Retrieve pipeline\
  \ execution performance metrics and concurrency stats for the SnapLogic org\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snaplogic-api.get-execution-metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset-privileges\n      description: Get current user's access privileges for a SnapLogic project or asset path\n      hints:\n        readOnly: true\n        openWorld: false\n      call: snaplogic-api.get-asset-privileges\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: grant-asset-access\n      description: Grant access permissions to a user or group for a SnapLogic project\n      hints:\n        readOnly: false\n        destructive: false\n      call: snaplogic-api.grant-asset-access\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create\
  \ a new SnapLogic project or project space\n      hints:\n        readOnly: false\n        destructive: false\n      call: snaplogic-api.create-project\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-project\n      description: Delete a SnapLogic project or project space\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: snaplogic-api.delete-project\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snaplogic/refs/heads/main/capabilities/pipeline-operations.yaml
tags:
- Automation
- DataOps
- Integration
- iPaaS
- Monitoring
- SnapLogic
tools:
- description: List all running and recent pipeline executions in the SnapLogic organization
  hints:
    openWorld: false
    readOnly: true
  name: list-pipeline-executions
- description: Get the status and details of a specific SnapLogic pipeline execution
  hints:
    openWorld: false
    readOnly: true
  name: get-pipeline-execution
- description: Stop a running SnapLogic pipeline execution by its runtime UUID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stop-pipeline-execution
- description: Retrieve pipeline execution performance metrics and concurrency stats for the SnapLogic org
  hints:
    openWorld: false
    readOnly: true
  name: get-execution-metrics
- description: Get current user's access privileges for a SnapLogic project or asset path
  hints:
    openWorld: false
    readOnly: true
  name: get-asset-privileges
- description: Grant access permissions to a user or group for a SnapLogic project
  hints:
    destructive: false
    readOnly: false
  name: grant-asset-access
- description: Create a new SnapLogic project or project space
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: Delete a SnapLogic project or project space
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
---
