---
categories: []
consumed_apis: []
description: The Flyte Admin API is the control-plane REST API exposed by the flyteadmin service. It is generated from the flyteidl protocol buffer definitions via gRPC-Gateway and provides JSON over HTTP access to the same operations exposed via gRPC. The API is used to register and manage projects, tasks, workflows, and launch plans, to create and inspect workflow, node, and task executions, to receive lifecycle events, to proxy data to and from upstream object stores, and to read and write matchable attribute overrides at the project, domain, and workflow levels. The same REST API powers the Flyte Conso
layout: capability
name: Flyte Admin API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /api/v1/projects
- description: Register a project
  method: POST
  name: registerproject
  path: /api/v1/projects
- description: Update a project
  method: PUT
  name: updateproject
  path: /api/v1/projects/{id}
- description: Register a task
  method: POST
  name: createtask
  path: /api/v1/tasks
- description: List tasks
  method: GET
  name: listtasks
  path: /api/v1/tasks/{id.project}/{id.domain}
- description: List tasks for a name
  method: GET
  name: listtasksbyname
  path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}
- description: Retrieve a task
  method: GET
  name: gettask
  path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}/{id.version}
- description: List task identifiers
  method: GET
  name: listtaskids
  path: /api/v1/task_ids/{project}/{domain}
- description: Register a workflow
  method: POST
  name: createworkflow
  path: /api/v1/workflows
- description: List workflows
  method: GET
  name: listworkflows
  path: /api/v1/workflows/{id.project}/{id.domain}
- description: List workflows for a name
  method: GET
  name: listworkflowsbyname
  path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}
- description: Retrieve a workflow
  method: GET
  name: getworkflow
  path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}/{id.version}
- description: List workflow identifiers
  method: GET
  name: listworkflowids
  path: /api/v1/workflow_ids/{project}/{domain}
- description: Register a launch plan
  method: POST
  name: createlaunchplan
  path: /api/v1/launch_plans
- description: List launch plans
  method: GET
  name: listlaunchplans
  path: /api/v1/launch_plans/{id.project}/{id.domain}
- description: List launch plans for a name
  method: GET
  name: listlaunchplansbyname
  path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}
- description: Retrieve a launch plan
  method: GET
  name: getlaunchplan
  path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}/{id.version}
- description: Update launch plan state
  method: PUT
  name: updatelaunchplan
  path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}/{id.version}
- description: List active launch plans
  method: GET
  name: listactivelaunchplans
  path: /api/v1/active_launch_plans/{project}/{domain}
- description: Get the active launch plan for a name
  method: GET
  name: getactivelaunchplan
  path: /api/v1/active_launch_plans/{id.project}/{id.domain}/{id.name}
- description: List launch plan identifiers
  method: GET
  name: listlaunchplanids
  path: /api/v1/launch_plan_ids/{project}/{domain}
- description: Create a workflow execution
  method: POST
  name: createexecution
  path: /api/v1/executions
- description: Relaunch a workflow execution
  method: POST
  name: relaunchexecution
  path: /api/v1/executions/relaunch
- description: Recover a workflow execution
  method: POST
  name: recoverexecution
  path: /api/v1/executions/recover
- description: List workflow executions
  method: GET
  name: listexecutions
  path: /api/v1/executions/{id.project}/{id.domain}
- description: Retrieve a workflow execution
  method: GET
  name: getexecution
  path: /api/v1/executions/{id.project}/{id.domain}/{id.name}
- description: Terminate a workflow execution
  method: DELETE
  name: terminateexecution
  path: /api/v1/executions/{id.project}/{id.domain}/{id.name}
- description: Retrieve execution metrics
  method: GET
  name: getexecutionmetrics
  path: /api/v1/metrics/executions/{id.project}/{id.domain}/{id.name}
- description: Retrieve signed data URLs for a workflow execution
  method: GET
  name: getexecutiondata
  path: /api/v1/data/executions/{id.project}/{id.domain}/{id.name}
- description: List node executions for a workflow execution
  method: GET
  name: listnodeexecutions
  path: /api/v1/node_executions/{workflow_execution_id.project}/{workflow_execution_id.domain}/{workflow_execution_id.name}
- description: List task executions for a node execution
  method: GET
  name: listtaskexecutions
  path: /api/v1/task_executions/{node_execution_id.execution_id.project}/{node_execution_id.execution_id.domain}/{node_execution_id.execution_id.name}/{node_execution_id.node_id}
- description: Submit a workflow execution event
  method: POST
  name: createworkflowevent
  path: /api/v1/events/workflows
- description: Submit a node execution event
  method: POST
  name: createnodeevent
  path: /api/v1/events/nodes
- description: Submit a task execution event
  method: POST
  name: createtaskevent
  path: /api/v1/events/tasks
- description: List named entities
  method: GET
  name: listnamedentities
  path: /api/v1/named_entities/{resource_type}/{project}/{domain}
- description: Retrieve a named entity
  method: GET
  name: getnamedentity
  path: /api/v1/named_entities/{resource_type}/{id.project}/{id.domain}/{id.name}
- description: Update a named entity
  method: PUT
  name: updatenamedentity
  path: /api/v1/named_entities/{resource_type}/{id.project}/{id.domain}/{id.name}
- description: List matchable attributes
  method: GET
  name: listmatchableattributes
  path: /api/v1/matchable_attributes
- description: Retrieve project attributes
  method: GET
  name: getprojectattributes
  path: /api/v1/project_attributes/{project}
- description: Update project attributes
  method: PUT
  name: updateprojectattributes
  path: /api/v1/project_attributes/{attributes.project}
- description: Retrieve project-domain attributes
  method: GET
  name: getprojectdomainattributes
  path: /api/v1/project_domain_attributes/{project}/{domain}
- description: Update project-domain attributes
  method: PUT
  name: updateprojectdomainattributes
  path: /api/v1/project_domain_attributes/{attributes.project}/{attributes.domain}
- description: Retrieve workflow attributes
  method: GET
  name: getworkflowattributes
  path: /api/v1/workflow_attributes/{project}/{domain}/{workflow}
- description: Update workflow attributes
  method: PUT
  name: updateworkflowattributes
  path: /api/v1/workflow_attributes/{attributes.project}/{attributes.domain}/{attributes.workflow}
- description: Retrieve flyteadmin version
  method: GET
  name: getversion
  path: /api/v1/version
personas: []
provider_name: Flyte
provider_slug: flyte
search_terms:
- retrieve signed data urls for a workflow execution
- terminate a workflow execution
- get the active launch plan for a name
- list workflows for a name
- list node executions for a workflow execution
- api
- createworkflow
- getversion
- list workflows
- listworkflowsbyname
- list task executions for a node execution
- list launch plans
- getworkflowattributes
- list projects
- listlaunchplans
- createnodeevent
- list tasks for a name
- listtaskids
- list active launch plans
- listworkflowids
- createtask
- list named entities
- getactivelaunchplan
- submit a task execution event
- retrieve a named entity
- registerproject
- updateproject
- submit a workflow execution event
- listworkflows
- register a task
- retrieve a task
- getprojectattributes
- kubernetes
- getexecution
- listtaskexecutions
- listtasks
- terminateexecution
- listprojects
- cncf
- update workflow attributes
- listactivelaunchplans
- relaunch a workflow execution
- listlaunchplanids
- gettask
- recoverexecution
- list launch plan identifiers
- retrieve a workflow execution
- createworkflowevent
- relaunchexecution
- updatenamedentity
- updatelaunchplan
- list workflow executions
- retrieve a workflow
- machine learning
- updateprojectdomainattributes
- workflow automation
- updateprojectattributes
- listmatchableattributes
- register a project
- getexecutionmetrics
- listtasksbyname
- getworkflow
- submit a node execution event
- retrieve project-domain attributes
- getexecutiondata
- update launch plan state
- list matchable attributes
- getnamedentity
- retrieve project attributes
- getprojectdomainattributes
- retrieve execution metrics
- flyte
- list task identifiers
- getlaunchplan
- listnodeexecutions
- list tasks
- update project-domain attributes
- recover a workflow execution
- update project attributes
- createtaskevent
- retrieve workflow attributes
- createexecution
- list workflow identifiers
- createlaunchplan
- retrieve a launch plan
- updateworkflowattributes
- register a launch plan
- list launch plans for a name
- listlaunchplansbyname
- update a project
- data orchestration
- update a named entity
- retrieve flyteadmin version
- listnamedentities
- listexecutions
- create a workflow execution
- register a workflow
slug: flyte-capability
source_filename: flyte-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Flyte Admin API\n  description: The Flyte Admin API is the control-plane REST API exposed by the flyteadmin service. It is generated from the\n    flyteidl protocol buffer definitions via gRPC-Gateway and provides JSON over HTTP access to the same operations exposed\n    via gRPC. The API is used to register and manage projects, tasks, workflows, and launch plans, to create and inspect workflow,\n    node, and task executions, to receive lifecycle events, to proxy data to and from upstream object stores, and to read\n    and write matchable attribute overrides at the project, domain, and workflow levels. The same REST API powers the Flyte\n    Conso\n  tags:\n  - Flyte\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: flyte\n    baseUri: http://localhost:30080\n    description: Flyte Admin API HTTP API.\n    resources:\n    - name: api-v1-projects\n      path: /api/v1/projects\n\
  \      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: registerproject\n        method: POST\n        description: Register a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-projects-id\n      path: /api/v1/projects/{id}\n      operations:\n      - name: updateproject\n        method: PUT\n        description: Update a project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-tasks\n      path: /api/v1/tasks\n      operations:\n      - name: createtask\n        method: POST\n        description:\
  \ Register a task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-tasks-id-project-id-domain\n      path: /api/v1/tasks/{id.project}/{id.domain}\n      operations:\n      - name: listtasks\n        method: GET\n        description: List tasks\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-tasks-id-project-id-domain-id-name\n      path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: listtasksbyname\n        method: GET\n        description: List tasks for a name\n        inputParameters:\n        - name: id.project\n          in: path\n  \
  \        type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-tasks-id-project-id-domain-id-name-id-ver\n      path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}/{id.version}\n      operations:\n      - name: gettask\n        method: GET\n        description: Retrieve a task\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        - name: id.version\n          in: path\n          type: string\n     \
  \     required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-task-ids-project-domain\n      path: /api/v1/task_ids/{project}/{domain}\n      operations:\n      - name: listtaskids\n        method: GET\n        description: List task identifiers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-workflows\n      path: /api/v1/workflows\n      operations:\n      - name: createworkflow\n        method: POST\n        description: Register a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: api-v1-workflows-id-project-id-domain\n      path: /api/v1/workflows/{id.project}/{id.domain}\n      operations:\n      - name: listworkflows\n        method: GET\n        description: List workflows\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-workflows-id-project-id-domain-id-name\n      path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: listworkflowsbyname\n        method: GET\n        description: List workflows for a name\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n\
  \          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-workflows-id-project-id-domain-id-name-id\n      path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}/{id.version}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Retrieve a workflow\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        - name: id.version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: api-v1-workflow-ids-project-domain\n      path: /api/v1/workflow_ids/{project}/{domain}\n      operations:\n      - name: listworkflowids\n        method: GET\n        description: List workflow identifiers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-launch-plans\n      path: /api/v1/launch_plans\n      operations:\n      - name: createlaunchplan\n        method: POST\n        description: Register a launch plan\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-launch-plans-id-project-id-domain\n      path: /api/v1/launch_plans/{id.project}/{id.domain}\n\
  \      operations:\n      - name: listlaunchplans\n        method: GET\n        description: List launch plans\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-launch-plans-id-project-id-domain-id-name\n      path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: listlaunchplansbyname\n        method: GET\n        description: List launch plans for a name\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-launch-plans-id-project-id-domain-id-name\n      path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}/{id.version}\n      operations:\n      - name: getlaunchplan\n        method: GET\n        description: Retrieve a launch plan\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        - name: id.version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatelaunchplan\n     \
  \   method: PUT\n        description: Update launch plan state\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        - name: id.version\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-active-launch-plans-project-domain\n      path: /api/v1/active_launch_plans/{project}/{domain}\n      operations:\n      - name: listactivelaunchplans\n        method: GET\n        description: List active launch plans\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in:\
  \ path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-active-launch-plans-id-project-id-domain-\n      path: /api/v1/active_launch_plans/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: getactivelaunchplan\n        method: GET\n        description: Get the active launch plan for a name\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-launch-plan-ids-project-domain\n      path: /api/v1/launch_plan_ids/{project}/{domain}\n\
  \      operations:\n      - name: listlaunchplanids\n        method: GET\n        description: List launch plan identifiers\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-executions\n      path: /api/v1/executions\n      operations:\n      - name: createexecution\n        method: POST\n        description: Create a workflow execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-executions-relaunch\n      path: /api/v1/executions/relaunch\n      operations:\n      - name: relaunchexecution\n        method: POST\n        description: Relaunch a workflow execution\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-executions-recover\n      path: /api/v1/executions/recover\n      operations:\n      - name: recoverexecution\n        method: POST\n        description: Recover a workflow execution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-executions-id-project-id-domain\n      path: /api/v1/executions/{id.project}/{id.domain}\n      operations:\n      - name: listexecutions\n        method: GET\n        description: List workflow executions\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: api-v1-executions-id-project-id-domain-id-name\n      path: /api/v1/executions/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: getexecution\n        method: GET\n        description: Retrieve a workflow execution\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: terminateexecution\n        method: DELETE\n        description: Terminate a workflow execution\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n\
  \          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-metrics-executions-id-project-id-domain-i\n      path: /api/v1/metrics/executions/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: getexecutionmetrics\n        method: GET\n        description: Retrieve execution metrics\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-data-executions-id-project-id-domain-id-n\n\
  \      path: /api/v1/data/executions/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: getexecutiondata\n        method: GET\n        description: Retrieve signed data URLs for a workflow execution\n        inputParameters:\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-node-executions-workflow-execution-id-pro\n      path: /api/v1/node_executions/{workflow_execution_id.project}/{workflow_execution_id.domain}/{workflow_execution_id.name}\n      operations:\n      - name: listnodeexecutions\n        method: GET\n        description: List node executions for a workflow execution\n     \
  \   inputParameters:\n        - name: workflow_execution_id.project\n          in: path\n          type: string\n          required: true\n        - name: workflow_execution_id.domain\n          in: path\n          type: string\n          required: true\n        - name: workflow_execution_id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-task-executions-node-execution-id-executi\n      path: /api/v1/task_executions/{node_execution_id.execution_id.project}/{node_execution_id.execution_id.domain}/{node_execution_id.execution_id.name}/{node_execution_id.node_id}\n      operations:\n      - name: listtaskexecutions\n        method: GET\n        description: List task executions for a node execution\n        inputParameters:\n        - name: node_execution_id.execution_id.project\n          in: path\n          type: string\n\
  \          required: true\n        - name: node_execution_id.execution_id.domain\n          in: path\n          type: string\n          required: true\n        - name: node_execution_id.execution_id.name\n          in: path\n          type: string\n          required: true\n        - name: node_execution_id.node_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-events-workflows\n      path: /api/v1/events/workflows\n      operations:\n      - name: createworkflowevent\n        method: POST\n        description: Submit a workflow execution event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-events-nodes\n      path: /api/v1/events/nodes\n      operations:\n      - name: createnodeevent\n        method: POST\n        description:\
  \ Submit a node execution event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-events-tasks\n      path: /api/v1/events/tasks\n      operations:\n      - name: createtaskevent\n        method: POST\n        description: Submit a task execution event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-named-entities-resource-type-project-doma\n      path: /api/v1/named_entities/{resource_type}/{project}/{domain}\n      operations:\n      - name: listnamedentities\n        method: GET\n        description: List named entities\n        inputParameters:\n        - name: resource_type\n          in: path\n          type: string\n          required: true\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n       \
  \   type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-named-entities-resource-type-id-project-i\n      path: /api/v1/named_entities/{resource_type}/{id.project}/{id.domain}/{id.name}\n      operations:\n      - name: getnamedentity\n        method: GET\n        description: Retrieve a named entity\n        inputParameters:\n        - name: resource_type\n          in: path\n          type: string\n          required: true\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenamedentity\n\
  \        method: PUT\n        description: Update a named entity\n        inputParameters:\n        - name: resource_type\n          in: path\n          type: string\n          required: true\n        - name: id.project\n          in: path\n          type: string\n          required: true\n        - name: id.domain\n          in: path\n          type: string\n          required: true\n        - name: id.name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-matchable-attributes\n      path: /api/v1/matchable_attributes\n      operations:\n      - name: listmatchableattributes\n        method: GET\n        description: List matchable attributes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-project-attributes-project\n     \
  \ path: /api/v1/project_attributes/{project}\n      operations:\n      - name: getprojectattributes\n        method: GET\n        description: Retrieve project attributes\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-project-attributes-attributes-project\n      path: /api/v1/project_attributes/{attributes.project}\n      operations:\n      - name: updateprojectattributes\n        method: PUT\n        description: Update project attributes\n        inputParameters:\n        - name: attributes.project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-project-domain-attributes-project-domain\n      path: /api/v1/project_domain_attributes/{project}/{domain}\n\
  \      operations:\n      - name: getprojectdomainattributes\n        method: GET\n        description: Retrieve project-domain attributes\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-project-domain-attributes-attributes-proj\n      path: /api/v1/project_domain_attributes/{attributes.project}/{attributes.domain}\n      operations:\n      - name: updateprojectdomainattributes\n        method: PUT\n        description: Update project-domain attributes\n        inputParameters:\n        - name: attributes.project\n          in: path\n          type: string\n          required: true\n        - name: attributes.domain\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-workflow-attributes-project-domain-workfl\n      path: /api/v1/workflow_attributes/{project}/{domain}/{workflow}\n      operations:\n      - name: getworkflowattributes\n        method: GET\n        description: Retrieve workflow attributes\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: domain\n          in: path\n          type: string\n          required: true\n        - name: workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-workflow-attributes-attributes-project-at\n      path: /api/v1/workflow_attributes/{attributes.project}/{attributes.domain}/{attributes.workflow}\n\
  \      operations:\n      - name: updateworkflowattributes\n        method: PUT\n        description: Update workflow attributes\n        inputParameters:\n        - name: attributes.project\n          in: path\n          type: string\n          required: true\n        - name: attributes.domain\n          in: path\n          type: string\n          required: true\n        - name: attributes.workflow\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v1-version\n      path: /api/v1/version\n      operations:\n      - name: getversion\n        method: GET\n        description: Retrieve flyteadmin version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: flyte-rest\n    description: REST adapter\
  \ for Flyte Admin API.\n    resources:\n    - path: /api/v1/projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: flyte.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects\n      name: registerproject\n      operations:\n      - method: POST\n        name: registerproject\n        description: Register a project\n        call: flyte.registerproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/projects/{id}\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Update a project\n        call: flyte.updateproject\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/tasks\n      name: createtask\n      operations:\n      - method: POST\n\
  \        name: createtask\n        description: Register a task\n        call: flyte.createtask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/tasks/{id.project}/{id.domain}\n      name: listtasks\n      operations:\n      - method: GET\n        name: listtasks\n        description: List tasks\n        call: flyte.listtasks\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}\n      name: listtasksbyname\n      operations:\n      - method: GET\n        name: listtasksbyname\n        description: List tasks for a name\n        call: flyte.listtasksbyname\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/tasks/{id.project}/{id.domain}/{id.name}/{id.version}\n\
  \      name: gettask\n      operations:\n      - method: GET\n        name: gettask\n        description: Retrieve a task\n        call: flyte.gettask\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n          id.version: rest.id.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/task_ids/{project}/{domain}\n      name: listtaskids\n      operations:\n      - method: GET\n        name: listtaskids\n        description: List task identifiers\n        call: flyte.listtaskids\n        with:\n          project: rest.project\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/workflows\n      name: createworkflow\n      operations:\n      - method: POST\n        name: createworkflow\n        description: Register a workflow\n        call: flyte.createworkflow\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /api/v1/workflows/{id.project}/{id.domain}\n      name: listworkflows\n      operations:\n      - method: GET\n        name: listworkflows\n        description: List workflows\n        call: flyte.listworkflows\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}\n      name: listworkflowsbyname\n      operations:\n      - method: GET\n        name: listworkflowsbyname\n        description: List workflows for a name\n        call: flyte.listworkflowsbyname\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/workflows/{id.project}/{id.domain}/{id.name}/{id.version}\n      name: getworkflow\n \
  \     operations:\n      - method: GET\n        name: getworkflow\n        description: Retrieve a workflow\n        call: flyte.getworkflow\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n          id.version: rest.id.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/workflow_ids/{project}/{domain}\n      name: listworkflowids\n      operations:\n      - method: GET\n        name: listworkflowids\n        description: List workflow identifiers\n        call: flyte.listworkflowids\n        with:\n          project: rest.project\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/launch_plans\n      name: createlaunchplan\n      operations:\n      - method: POST\n        name: createlaunchplan\n        description: Register a launch plan\n        call: flyte.createlaunchplan\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/v1/launch_plans/{id.project}/{id.domain}\n      name: listlaunchplans\n      operations:\n      - method: GET\n        name: listlaunchplans\n        description: List launch plans\n        call: flyte.listlaunchplans\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}\n      name: listlaunchplansbyname\n      operations:\n      - method: GET\n        name: listlaunchplansbyname\n        description: List launch plans for a name\n        call: flyte.listlaunchplansbyname\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}/{id.version}\n\
  \      name: getlaunchplan\n      operations:\n      - method: GET\n        name: getlaunchplan\n        description: Retrieve a launch plan\n        call: flyte.getlaunchplan\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n          id.version: rest.id.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/launch_plans/{id.project}/{id.domain}/{id.name}/{id.version}\n      name: updatelaunchplan\n      operations:\n      - method: PUT\n        name: updatelaunchplan\n        description: Update launch plan state\n        call: flyte.updatelaunchplan\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n          id.name: rest.id.name\n          id.version: rest.id.version\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/active_launch_plans/{project}/{domain}\n      name: listactivelaunchplans\n\
  \      operations:\n      - method: GET\n        name: listactivelaunchplans\n        description: List active launch plans\n        call: flyte.listactivelaunchplans\n        with:\n          project: rest.project\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v1/active_launch_plans/{id.project}/{id.domain}/{id.name}\n      name: getactivelaunchplan\n      operations:\n      - method: GET\n        name: getactivelaunchplan\n        description: Get the active launch plan for a name\n        call: flyte.getactivelaunchplan\n        with:\n          id.project: rest.id.project\n          id.domain: rest.id.domain\n  \n\n# --- truncated at 32 KB (67 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/flyte/refs/heads/main/capabilities/flyte-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/flyte/refs/heads/main/capabilities/flyte-capability.yaml
tags:
- Flyte
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Register a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registerproject
- description: Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Register a task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtask
- description: List tasks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasks
- description: List tasks for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtasksbyname
- description: Retrieve a task
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettask
- description: List task identifiers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskids
- description: Register a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflow
- description: List workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflows
- description: List workflows for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowsbyname
- description: Retrieve a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: List workflow identifiers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowids
- description: Register a launch plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createlaunchplan
- description: List launch plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlaunchplans
- description: List launch plans for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlaunchplansbyname
- description: Retrieve a launch plan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlaunchplan
- description: Update launch plan state
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatelaunchplan
- description: List active launch plans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivelaunchplans
- description: Get the active launch plan for a name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactivelaunchplan
- description: List launch plan identifiers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlaunchplanids
- description: Create a workflow execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createexecution
- description: Relaunch a workflow execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: relaunchexecution
- description: Recover a workflow execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: recoverexecution
- description: List workflow executions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexecutions
- description: Retrieve a workflow execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecution
- description: Terminate a workflow execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: terminateexecution
- description: Retrieve execution metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecutionmetrics
- description: Retrieve signed data URLs for a workflow execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecutiondata
- description: List node executions for a workflow execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnodeexecutions
- description: List task executions for a node execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtaskexecutions
- description: Submit a workflow execution event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflowevent
- description: Submit a node execution event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnodeevent
- description: Submit a task execution event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtaskevent
- description: List named entities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamedentities
- description: Retrieve a named entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnamedentity
- description: Update a named entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatenamedentity
- description: List matchable attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmatchableattributes
- description: Retrieve project attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectattributes
- description: Update project attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectattributes
- description: Retrieve project-domain attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectdomainattributes
- description: Update project-domain attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectdomainattributes
- description: Retrieve workflow attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowattributes
- description: Update workflow attributes
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkflowattributes
- description: Retrieve flyteadmin version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getversion
---
