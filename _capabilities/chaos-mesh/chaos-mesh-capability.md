---
categories: []
consumed_apis: []
description: The Chaos Mesh Dashboard API provides REST endpoints for managing chaos experiments, schedules, workflows, and events on Kubernetes clusters. Chaos Mesh is a cloud-native chaos engineering platform that supports fault injection into pods, nodes, networks, IO subsystems, and cloud provider resources. The Dashboard API is served by the chaos-dashboard component and is the backend for the Chaos Mesh web UI, accessible at /api on the dashboard server.
layout: capability
name: Chaos Mesh Dashboard API
operations:
- description: Chaos Mesh List chaos experiments
  method: GET
  name: listexperiments
  path: /experiments
- description: Chaos Mesh Create a new chaos experiment
  method: POST
  name: createexperiment
  path: /experiments
- description: Chaos Mesh Batch delete chaos experiments
  method: DELETE
  name: batchdeleteexperiments
  path: /experiments
- description: Chaos Mesh Get a chaos experiment
  method: GET
  name: getexperiment
  path: /experiments/{uid}
- description: Chaos Mesh Delete a chaos experiment
  method: DELETE
  name: deleteexperiment
  path: /experiments/{uid}
- description: Chaos Mesh Pause a chaos experiment
  method: PUT
  name: pauseexperiment
  path: /experiments/pause/{uid}
- description: Chaos Mesh Start a chaos experiment
  method: PUT
  name: startexperiment
  path: /experiments/start/{uid}
- description: Chaos Mesh Get the status of all experiments
  method: GET
  name: getexperimentsstate
  path: /experiments/state
- description: Chaos Mesh List chaos schedules
  method: GET
  name: listschedules
  path: /schedules
- description: Chaos Mesh Create a new schedule
  method: POST
  name: createschedule
  path: /schedules
- description: Chaos Mesh Batch delete schedules
  method: DELETE
  name: batchdeleteschedules
  path: /schedules
- description: Chaos Mesh Get a schedule
  method: GET
  name: getschedule
  path: /schedules/{uid}
- description: Chaos Mesh Delete a schedule
  method: DELETE
  name: deleteschedule
  path: /schedules/{uid}
- description: Chaos Mesh Pause a schedule
  method: PUT
  name: pauseschedule
  path: /schedules/pause/{uid}
- description: Chaos Mesh Start a schedule
  method: PUT
  name: startschedule
  path: /schedules/start/{uid}
- description: Chaos Mesh List workflows
  method: GET
  name: listworkflows
  path: /workflows
- description: Chaos Mesh Create a new workflow
  method: POST
  name: createworkflow
  path: /workflows
- description: Chaos Mesh Get workflow details
  method: GET
  name: getworkflow
  path: /workflows/{uid}
- description: Chaos Mesh Update a workflow
  method: PUT
  name: updateworkflow
  path: /workflows/{uid}
- description: Chaos Mesh Delete a workflow
  method: DELETE
  name: deleteworkflow
  path: /workflows/{uid}
- description: Chaos Mesh Parse an HTTP workflow task
  method: POST
  name: parseworkflowhttptask
  path: /workflows/parse-task/http
- description: Chaos Mesh Render an HTTP workflow task
  method: POST
  name: renderworkflowhttptask
  path: /workflows/render-task/http
- description: Chaos Mesh Validate an HTTP workflow task
  method: POST
  name: validateworkflowhttptask
  path: /workflows/validate-task/http
- description: Chaos Mesh Get archived chaos experiments
  method: GET
  name: listarchivedexperiments
  path: /archives
- description: Chaos Mesh Delete archived experiments
  method: DELETE
  name: batchdeletearchivedexperiments
  path: /archives
- description: Chaos Mesh Get an archived chaos experiment
  method: GET
  name: getarchivedexperiment
  path: /archives/{uid}
- description: Chaos Mesh Delete a specific archived experiment
  method: DELETE
  name: deletearchivedexperiment
  path: /archives/{uid}
- description: Chaos Mesh Get archived schedule experiments
  method: GET
  name: listarchivedschedules
  path: /archives/schedules
- description: Chaos Mesh Delete archived schedules
  method: DELETE
  name: batchdeletearchivedschedules
  path: /archives/schedules
- description: Chaos Mesh Get an archived schedule
  method: GET
  name: getarchivedschedule
  path: /archives/schedules/{uid}
- description: Chaos Mesh Delete an archived schedule
  method: DELETE
  name: deletearchivedschedule
  path: /archives/schedules/{uid}
- description: Chaos Mesh Get archived workflows
  method: GET
  name: listarchivedworkflows
  path: /archives/workflows
- description: Chaos Mesh Delete archived workflows
  method: DELETE
  name: batchdeletearchivedworkflows
  path: /archives/workflows
- description: Chaos Mesh Get an archived workflow
  method: GET
  name: getarchivedworkflow
  path: /archives/workflows/{uid}
- description: Chaos Mesh Delete an archived workflow
  method: DELETE
  name: deletearchivedworkflow
  path: /archives/workflows/{uid}
- description: Chaos Mesh List chaos events
  method: GET
  name: listevents
  path: /events
- description: Chaos Mesh Get an event
  method: GET
  name: getevent
  path: /events/{id}
- description: Chaos Mesh List events for a workflow
  method: GET
  name: listworkflowevents
  path: /events/workflow/{uid}
- description: Chaos Mesh Get Dashboard configuration
  method: GET
  name: getdashboardconfig
  path: /common/config
- description: Chaos Mesh Get all Kubernetes namespaces
  method: GET
  name: listnamespaces
  path: /common/namespaces
- description: Chaos Mesh Get namespaces available for chaos injection
  method: GET
  name: listchaosavailablenamespaces
  path: /common/chaos-available-namespaces
- description: Chaos Mesh Get all available chaos kinds
  method: GET
  name: listchaoskinds
  path: /common/kinds
- description: Chaos Mesh Get pod labels
  method: GET
  name: getpodlabels
  path: /common/labels
- description: Chaos Mesh Get pod annotations
  method: GET
  name: getpodannotations
  path: /common/annotations
- description: Chaos Mesh List pods matching a selector
  method: POST
  name: listpods
  path: /common/pods
- description: Chaos Mesh List physical machines matching a selector
  method: POST
  name: listphysicalmachines
  path: /common/physicalmachines
- description: Chaos Mesh Get RBAC configuration
  method: GET
  name: getrbacconfig
  path: /common/rbac-config
- description: Chaos Mesh List status check templates
  method: GET
  name: liststatuschecktemplates
  path: /templates/statuschecks
- description: Chaos Mesh Create a status check template
  method: POST
  name: createstatuschecktemplate
  path: /templates/statuschecks
- description: Chaos Mesh Get a status check template
  method: GET
  name: getstatuschecktemplate
  path: /templates/statuschecks/statuscheck
- description: Chaos Mesh Update a status check template
  method: PUT
  name: updatestatuschecktemplate
  path: /templates/statuschecks/statuscheck
- description: Chaos Mesh Delete a status check template
  method: DELETE
  name: deletestatuschecktemplate
  path: /templates/statuschecks/statuscheck
personas: []
provider_name: Chaos Mesh
provider_slug: chaos-mesh
search_terms:
- listarchivedexperiments
- chaos mesh list chaos schedules
- createstatuschecktemplate
- chaos mesh delete archived workflows
- listpods
- chaos mesh get a chaos experiment
- api
- listschedules
- createworkflow
- chaos mesh list status check templates
- chaos mesh get an event
- listworkflowevents
- chaos mesh render an http workflow task
- batchdeletearchivedschedules
- getevent
- getpodannotations
- listarchivedschedules
- chaos mesh get archived schedule experiments
- chaos mesh get an archived workflow
- chaos mesh delete archived schedules
- chaos mesh delete a chaos experiment
- chaos mesh list workflows
- deleteexperiment
- chaos mesh batch delete schedules
- cncf
- chaos mesh batch delete chaos experiments
- chaos mesh list chaos events
- listevents
- getarchivedworkflow
- renderworkflowhttptask
- chaos mesh create a new schedule
- chaos mesh create a status check template
- validateworkflowhttptask
- listchaoskinds
- batchdeleteschedules
- getexperiment
- chaos mesh list physical machines matching a selector
- chaos mesh delete a schedule
- chaos mesh get pod annotations
- chaos mesh delete a status check template
- startschedule
- cloud native
- chaos engineering
- chaos mesh pause a chaos experiment
- chaos mesh delete archived experiments
- chaos mesh get a status check template
- batchdeletearchivedexperiments
- pauseschedule
- chaos mesh get workflow details
- chaos mesh delete a specific archived experiment
- chaos mesh list pods matching a selector
- chaos mesh parse an http workflow task
- chaos mesh get namespaces available for chaos injection
- chaos mesh update a status check template
- chaos mesh get an archived chaos experiment
- listphysicalmachines
- createexperiment
- getexperimentsstate
- mesh
- deletestatuschecktemplate
- listnamespaces
- chaos mesh delete a workflow
- listworkflows
- chaos mesh get pod labels
- getarchivedexperiment
- chaos mesh validate an http workflow task
- chaos mesh get a schedule
- chaos mesh list chaos experiments
- fault injection
- chaos mesh get rbac configuration
- chaos mesh get dashboard configuration
- updatestatuschecktemplate
- batchdeleteexperiments
- deleteschedule
- chaos mesh start a chaos experiment
- liststatuschecktemplates
- kubernetes
- observability
- getpodlabels
- createschedule
- pauseexperiment
- chaos mesh delete an archived workflow
- listarchivedworkflows
- getarchivedschedule
- resilience
- chaos mesh list events for a workflow
- chaos mesh delete an archived schedule
- reliability
- chaos mesh get archived chaos experiments
- chaos mesh pause a schedule
- getstatuschecktemplate
- chaos mesh create a new chaos experiment
- listexperiments
- testing
- chaos mesh get all kubernetes namespaces
- deletearchivedworkflow
- chaos
- deleteworkflow
- updateworkflow
- open source
- getschedule
- chaos mesh get archived workflows
- chaos mesh update a workflow
- getworkflow
- chaos mesh get all available chaos kinds
- chaos mesh get an archived schedule
- getrbacconfig
- deletearchivedschedule
- chaos mesh create a new workflow
- listchaosavailablenamespaces
- deletearchivedexperiment
- startexperiment
- getdashboardconfig
- parseworkflowhttptask
- chaos mesh start a schedule
- batchdeletearchivedworkflows
- chaos mesh get the status of all experiments
slug: chaos-mesh-capability
source_filename: chaos-mesh-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Chaos Mesh Dashboard API\n  description: The Chaos Mesh Dashboard API provides REST endpoints for managing chaos experiments, schedules, workflows,\n    and events on Kubernetes clusters. Chaos Mesh is a cloud-native chaos engineering platform that supports fault injection\n    into pods, nodes, networks, IO subsystems, and cloud provider resources. The Dashboard API is served by the chaos-dashboard\n    component and is the backend for the Chaos Mesh web UI, accessible at /api on the dashboard server.\n  tags:\n  - Chaos\n  - Mesh\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chaos-mesh\n    baseUri: http://localhost:2333/api\n    description: Chaos Mesh Dashboard API HTTP API.\n    resources:\n    - name: experiments\n      path: /experiments\n      operations:\n      - name: listexperiments\n        method: GET\n        description: Chaos Mesh List chaos experiments\n\
  \        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter experiments by name (partial match supported).\n        - name: kind\n          in: query\n          type: string\n          description: Filter experiments by chaos kind (e.g., PodChaos, NetworkChaos, IOChaos, StressChaos, TimeChaos, HTTPChaos).\n        - name: status\n          in: query\n          type: string\n          description: Filter experiments by status (e.g., running, paused, finished).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createexperiment\n        method: POST\n        description: Chaos Mesh Create a new chaos experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchdeleteexperiments\n        method: DELETE\n        description: Chaos Mesh Batch\
  \ delete chaos experiments\n        inputParameters:\n        - name: uids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of experiment UIDs to delete.\n        - name: force\n          in: query\n          type: boolean\n          description: Force delete experiments without waiting for fault cleanup.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments-uid\n      path: /experiments/{uid}\n      operations:\n      - name: getexperiment\n        method: GET\n        description: Chaos Mesh Get a chaos experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteexperiment\n        method: DELETE\n        description: Chaos Mesh Delete a chaos experiment\n        inputParameters:\n        - name: force\n          in: query\n\
  \          type: boolean\n          description: Force delete without waiting for fault cleanup.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments-pause-uid\n      path: /experiments/pause/{uid}\n      operations:\n      - name: pauseexperiment\n        method: PUT\n        description: Chaos Mesh Pause a chaos experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments-start-uid\n      path: /experiments/start/{uid}\n      operations:\n      - name: startexperiment\n        method: PUT\n        description: Chaos Mesh Start a chaos experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: experiments-state\n      path: /experiments/state\n      operations:\n      - name: getexperimentsstate\n\
  \        method: GET\n        description: Chaos Mesh Get the status of all experiments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description: Chaos Mesh List chaos schedules\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter schedules by name.\n        - name: kind\n          in: query\n          type: string\n          description: Filter schedules by chaos kind.\n        - name: status\n          in: query\n          type: string\n          description: Filter schedules by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createschedule\n        method: POST\n        description: Chaos Mesh Create a new schedule\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchdeleteschedules\n        method: DELETE\n        description: Chaos Mesh Batch delete schedules\n        inputParameters:\n        - name: uids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of schedule UIDs to delete.\n        - name: force\n          in: query\n          type: boolean\n          description: Force delete schedules without graceful cleanup.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-uid\n      path: /schedules/{uid}\n      operations:\n      - name: getschedule\n        method: GET\n        description: Chaos Mesh Get a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: deleteschedule\n        method: DELETE\n        description: Chaos Mesh Delete a schedule\n        inputParameters:\n        - name: force\n          in: query\n          type: boolean\n          description: Force delete without graceful cleanup.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-pause-uid\n      path: /schedules/pause/{uid}\n      operations:\n      - name: pauseschedule\n        method: PUT\n        description: Chaos Mesh Pause a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-start-uid\n      path: /schedules/start/{uid}\n      operations:\n      - name: startschedule\n        method: PUT\n        description: Chaos Mesh Start a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: workflows\n      path: /workflows\n      operations:\n      - name: listworkflows\n        method: GET\n        description: Chaos Mesh List workflows\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter workflows by name.\n        - name: status\n          in: query\n          type: string\n          description: Filter workflows by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkflow\n        method: POST\n        description: Chaos Mesh Create a new workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-uid\n      path: /workflows/{uid}\n      operations:\n      - name: getworkflow\n        method: GET\n        description: Chaos Mesh Get workflow details\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflow\n        method: PUT\n        description: Chaos Mesh Update a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflow\n        method: DELETE\n        description: Chaos Mesh Delete a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-parse-task-http\n      path: /workflows/parse-task/http\n      operations:\n      - name: parseworkflowhttptask\n        method: POST\n        description: Chaos Mesh Parse an HTTP workflow task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-render-task-http\n      path: /workflows/render-task/http\n      operations:\n\
  \      - name: renderworkflowhttptask\n        method: POST\n        description: Chaos Mesh Render an HTTP workflow task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-validate-task-http\n      path: /workflows/validate-task/http\n      operations:\n      - name: validateworkflowhttptask\n        method: POST\n        description: Chaos Mesh Validate an HTTP workflow task\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archives\n      path: /archives\n      operations:\n      - name: listarchivedexperiments\n        method: GET\n        description: Chaos Mesh Get archived chaos experiments\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by experiment name.\n        - name: kind\n          in: query\n          type: string\n\
  \          description: Filter by chaos kind.\n        - name: start\n          in: query\n          type: string\n          description: Filter events from this timestamp (RFC3339).\n        - name: end\n          in: query\n          type: string\n          description: Filter events up to this timestamp (RFC3339).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchdeletearchivedexperiments\n        method: DELETE\n        description: Chaos Mesh Delete archived experiments\n        inputParameters:\n        - name: uids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of archive UIDs to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archives-uid\n      path: /archives/{uid}\n      operations:\n      - name: getarchivedexperiment\n\
  \        method: GET\n        description: Chaos Mesh Get an archived chaos experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletearchivedexperiment\n        method: DELETE\n        description: Chaos Mesh Delete a specific archived experiment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archives-schedules\n      path: /archives/schedules\n      operations:\n      - name: listarchivedschedules\n        method: GET\n        description: Chaos Mesh Get archived schedule experiments\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by schedule name.\n        - name: kind\n          in: query\n          type: string\n          description: Filter by chaos kind.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: batchdeletearchivedschedules\n        method: DELETE\n        description: Chaos Mesh Delete archived schedules\n        inputParameters:\n        - name: uids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of archive UIDs to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archives-schedules-uid\n      path: /archives/schedules/{uid}\n      operations:\n      - name: getarchivedschedule\n        method: GET\n        description: Chaos Mesh Get an archived schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletearchivedschedule\n        method: DELETE\n        description: Chaos Mesh Delete an archived schedule\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archives-workflows\n      path: /archives/workflows\n      operations:\n      - name: listarchivedworkflows\n        method: GET\n        description: Chaos Mesh Get archived workflows\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter by workflow name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batchdeletearchivedworkflows\n        method: DELETE\n        description: Chaos Mesh Delete archived workflows\n        inputParameters:\n        - name: uids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of archive UIDs to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: archives-workflows-uid\n      path: /archives/workflows/{uid}\n      operations:\n      - name: getarchivedworkflow\n        method: GET\n        description: Chaos Mesh Get an archived workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletearchivedworkflow\n        method: DELETE\n        description: Chaos Mesh Delete an archived workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: listevents\n        method: GET\n        description: Chaos Mesh List chaos events\n        inputParameters:\n        - name: object_id\n          in: query\n          type: string\n          description: Filter events by the UID of the associated experiment or workflow.\n        - name: name\n          in: query\n          type: string\n\
  \          description: Filter events by experiment name.\n        - name: kind\n          in: query\n          type: string\n          description: Filter events by chaos kind.\n        - name: start\n          in: query\n          type: string\n          description: Filter events from this timestamp (RFC3339).\n        - name: end\n          in: query\n          type: string\n          description: Filter events up to this timestamp (RFC3339).\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of events to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-id\n      path: /events/{id}\n      operations:\n      - name: getevent\n        method: GET\n        description: Chaos Mesh Get an event\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ Integer ID of the event.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-workflow-uid\n      path: /events/workflow/{uid}\n      operations:\n      - name: listworkflowevents\n        method: GET\n        description: Chaos Mesh List events for a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-config\n      path: /common/config\n      operations:\n      - name: getdashboardconfig\n        method: GET\n        description: Chaos Mesh Get Dashboard configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-namespaces\n      path: /common/namespaces\n      operations:\n      - name: listnamespaces\n        method: GET\n        description: Chaos Mesh Get all Kubernetes namespaces\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-chaos-available-namespaces\n      path: /common/chaos-available-namespaces\n      operations:\n      - name: listchaosavailablenamespaces\n        method: GET\n        description: Chaos Mesh Get namespaces available for chaos injection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-kinds\n      path: /common/kinds\n      operations:\n      - name: listchaoskinds\n        method: GET\n        description: Chaos Mesh Get all available chaos kinds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-labels\n      path: /common/labels\n      operations:\n      - name: getpodlabels\n        method: GET\n        description: Chaos Mesh Get pod labels\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-annotations\n      path: /common/annotations\n      operations:\n      - name: getpodannotations\n        method: GET\n        description: Chaos Mesh Get pod annotations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-pods\n      path: /common/pods\n      operations:\n      - name: listpods\n        method: POST\n        description: Chaos Mesh List pods matching a selector\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-physicalmachines\n      path: /common/physicalmachines\n      operations:\n      - name: listphysicalmachines\n        method: POST\n        description: Chaos Mesh List physical machines matching a selector\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: common-rbac-config\n      path: /common/rbac-config\n      operations:\n      - name: getrbacconfig\n        method: GET\n        description: Chaos Mesh Get RBAC configuration\n        inputParameters:\n        - name: role\n          in: query\n          type: string\n          description: Role type to generate RBAC config for (manager or viewer).\n        - name: scope\n          in: query\n          type: string\n          description: Scope of the RBAC config (cluster or namespace).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-statuschecks\n      path: /templates/statuschecks\n      operations:\n      - name: liststatuschecktemplates\n        method: GET\n        description: Chaos Mesh List status check templates\n        inputParameters:\n        - name: name\n\
  \          in: query\n          type: string\n          description: Filter templates by name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createstatuschecktemplate\n        method: POST\n        description: Chaos Mesh Create a status check template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-statuschecks-statuscheck\n      path: /templates/statuschecks/statuscheck\n      operations:\n      - name: getstatuschecktemplate\n        method: GET\n        description: Chaos Mesh Get a status check template\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Name of the status check template.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: updatestatuschecktemplate\n        method: PUT\n        description: Chaos Mesh Update a status check template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletestatuschecktemplate\n        method: DELETE\n        description: Chaos Mesh Delete a status check template\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Name of the status check template to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chaos-mesh-rest\n    description: REST adapter for Chaos Mesh Dashboard API.\n    resources:\n    - path: /experiments\n      name: listexperiments\n      operations:\n      - method: GET\n        name: listexperiments\n   \
  \     description: Chaos Mesh List chaos experiments\n        call: chaos-mesh.listexperiments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments\n      name: createexperiment\n      operations:\n      - method: POST\n        name: createexperiment\n        description: Chaos Mesh Create a new chaos experiment\n        call: chaos-mesh.createexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments\n      name: batchdeleteexperiments\n      operations:\n      - method: DELETE\n        name: batchdeleteexperiments\n        description: Chaos Mesh Batch delete chaos experiments\n        call: chaos-mesh.batchdeleteexperiments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments/{uid}\n      name: getexperiment\n      operations:\n      - method: GET\n        name: getexperiment\n        description: Chaos Mesh Get a chaos experiment\n      \
  \  call: chaos-mesh.getexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments/{uid}\n      name: deleteexperiment\n      operations:\n      - method: DELETE\n        name: deleteexperiment\n        description: Chaos Mesh Delete a chaos experiment\n        call: chaos-mesh.deleteexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments/pause/{uid}\n      name: pauseexperiment\n      operations:\n      - method: PUT\n        name: pauseexperiment\n        description: Chaos Mesh Pause a chaos experiment\n        call: chaos-mesh.pauseexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /experiments/start/{uid}\n      name: startexperiment\n      operations:\n      - method: PUT\n        name: startexperiment\n        description: Chaos Mesh Start a chaos experiment\n        call: chaos-mesh.startexperiment\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /experiments/state\n      name: getexperimentsstate\n      operations:\n      - method: GET\n        name: getexperimentsstate\n        description: Chaos Mesh Get the status of all experiments\n        call: chaos-mesh.getexperimentsstate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: Chaos Mesh List chaos schedules\n        call: chaos-mesh.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: createschedule\n      operations:\n      - method: POST\n        name: createschedule\n        description: Chaos Mesh Create a new schedule\n        call: chaos-mesh.createschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: batchdeleteschedules\n\
  \      operations:\n      - method: DELETE\n        name: batchdeleteschedules\n        description: Chaos Mesh Batch delete schedules\n        call: chaos-mesh.batchdeleteschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{uid}\n      name: getschedule\n      operations:\n      - method: GET\n        name: getschedule\n        description: Chaos Mesh Get a schedule\n        call: chaos-mesh.getschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{uid}\n      name: deleteschedule\n      operations:\n      - method: DELETE\n        name: deleteschedule\n        description: Chaos Mesh Delete a schedule\n        call: chaos-mesh.deleteschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/pause/{uid}\n      name: pauseschedule\n      operations:\n      - method: PUT\n        name: pauseschedule\n        description: Chaos Mesh\
  \ Pause a schedule\n        call: chaos-mesh.pauseschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/start/{uid}\n      name: startschedule\n      operations:\n      - method: PUT\n        name: startschedule\n        description: Chaos Mesh Start a schedule\n        call: chaos-mesh.startschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows\n      name: listworkflows\n      operations:\n      - method: GET\n        name: listworkflows\n        description: Chaos Mesh List workflows\n        call: chaos-mesh.listworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows\n      name: createworkflow\n      operations:\n      - method: POST\n        name: createworkflow\n        description: Chaos Mesh Create a new workflow\n        call: chaos-mesh.createworkflow\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /workflows/{uid}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Chaos Mesh Get workflow details\n        call: chaos-mesh.getworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{uid}\n      name: updateworkflow\n      operations:\n      - method: PUT\n        name: updateworkflow\n        description: Chaos Mesh Update a workflow\n        call: chaos-mesh.updateworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{uid}\n      name: deleteworkflow\n      operations:\n      - method: DELETE\n        name: deleteworkflow\n        description: Chaos Mesh Delete a workflow\n        call: chaos-mesh.deleteworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/parse-task/http\n      name: parseworkflowhttptask\n      operations:\n      - method: POST\n\
  \        name: parseworkflowhttptask\n        description: Chaos Mesh Parse an HTTP workflow task\n        call: chaos-mesh.parseworkflowhttptask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/render-task/http\n      name: renderworkflowhttptask\n      operations:\n      - method: POST\n        name: renderworkflowhttptask\n        description: Chaos Mesh Render an HTTP workflow task\n        call: chaos-mesh.renderworkflowhttptask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/validate-task/http\n      name: validateworkflowhttptask\n      operations:\n      - method: POST\n        name: validateworkflowhttptask\n        description: Chaos Mesh Validate an HTTP workflow task\n        call: chaos-mesh.validateworkflowhttptask\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives\n      name: listarchivedexperiments\n      operations:\n      -\
  \ method: GET\n        name: listarchivedexperiments\n        description: Chaos Mesh Get archived chaos experiments\n        call: chaos-mesh.listarchivedexperiments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives\n      name: batchdeletearchivedexperiments\n      operations:\n      - method: DELETE\n        name: batchdeletearchivedexperiments\n        description: Chaos Mesh Delete archived experiments\n        call: chaos-mesh.batchdeletearchivedexperiments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/{uid}\n      name: getarchivedexperiment\n      operations:\n      - method: GET\n        name: getarchivedexperiment\n        description: Chaos Mesh Get an archived chaos experiment\n        call: chaos-mesh.getarchivedexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/{uid}\n      name: deletearchivedexperiment\n      operations:\n\
  \      - method: DELETE\n        name: deletearchivedexperiment\n        description: Chaos Mesh Delete a specific archived experiment\n        call: chaos-mesh.deletearchivedexperiment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/schedules\n      name: listarchivedschedules\n      operations:\n      - method: GET\n        name: listarchivedschedules\n        description: Chaos Mesh Get archived schedule experiments\n        call: chaos-mesh.listarchivedschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/schedules\n      name: batchdeletearchivedschedules\n      operations:\n      - method: DELETE\n        name: batchdeletearchivedschedules\n        description: Chaos Mesh Delete archived schedules\n        call: chaos-mesh.batchdeletearchivedschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/schedules/{uid}\n      name: getarchivedschedule\n\
  \      operations:\n      - method: GET\n        name: getarchivedschedule\n        description: Chaos Mesh Get an archived schedule\n        call: chaos-mesh.getarchivedschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/schedules/{uid}\n      name: deletearchivedschedule\n      operations:\n      - method: DELETE\n        name: deletearchivedschedule\n        description: Chaos Mesh Delete an archived schedule\n        call: chaos-mesh.deletearchivedschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/workflows\n      name: listarchivedworkflows\n      operations:\n      - method: GET\n        name: listarchivedworkflows\n        description: Chaos Mesh Get archived workflows\n        call: chaos-mesh.listarchivedworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/workflows\n      name: batchdeletearchivedworkflows\n      operations:\n\
  \      - method: DELETE\n        name: batchdeletearchivedworkflows\n        description: Chaos Mesh Delete archived workflows\n        call: chaos-mesh.batchdeletearchivedworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/workflows/{uid}\n      name: getarchivedworkflow\n      operations:\n      - method: GET\n        name: getarchivedworkflow\n        description: Chaos Mesh Get an archived workflow\n        call: chaos-mesh.getarchivedworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /archives/workflows/{uid}\n      name: deletearchivedworkflow\n      operations:\n      - method: DELETE\n        name: deletearchivedworkflow\n        description: Chaos Mesh Delete an archived workflow\n        call: chaos-mesh.deletearchivedworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: listevents\n      operations:\n      - method:\
  \ GET\n        name: listevents\n        description: Chaos Mesh List chaos events\n        call: chaos-mesh.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{id}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Chaos Mesh Get an event\n        call: chaos-mesh.getevent\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/workflow/{uid}\n      name: listworkflowevents\n      operations:\n      - method: GET\n        name: listworkflowevents\n        description: Chaos Mesh List events for a workflow\n        call: chaos-mesh.listworkflowevents\n        outputParameters:\n        - type: object\n\n\n# --- truncated at 32 KB (56 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/chaos-mesh/refs/heads/main/capabilities/chaos-mesh-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chaos-mesh/refs/heads/main/capabilities/chaos-mesh-capability.yaml
tags:
- Chaos
- Mesh
- API
tools:
- description: Chaos Mesh List chaos experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listexperiments
- description: Chaos Mesh Create a new chaos experiment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createexperiment
- description: Chaos Mesh Batch delete chaos experiments
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batchdeleteexperiments
- description: Chaos Mesh Get a chaos experiment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexperiment
- description: Chaos Mesh Delete a chaos experiment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteexperiment
- description: Chaos Mesh Pause a chaos experiment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pauseexperiment
- description: Chaos Mesh Start a chaos experiment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startexperiment
- description: Chaos Mesh Get the status of all experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexperimentsstate
- description: Chaos Mesh List chaos schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: Chaos Mesh Create a new schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createschedule
- description: Chaos Mesh Batch delete schedules
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batchdeleteschedules
- description: Chaos Mesh Get a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschedule
- description: Chaos Mesh Delete a schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteschedule
- description: Chaos Mesh Pause a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: pauseschedule
- description: Chaos Mesh Start a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: startschedule
- description: Chaos Mesh List workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflows
- description: Chaos Mesh Create a new workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflow
- description: Chaos Mesh Get workflow details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Chaos Mesh Update a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkflow
- description: Chaos Mesh Delete a workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkflow
- description: Chaos Mesh Parse an HTTP workflow task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: parseworkflowhttptask
- description: Chaos Mesh Render an HTTP workflow task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renderworkflowhttptask
- description: Chaos Mesh Validate an HTTP workflow task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: validateworkflowhttptask
- description: Chaos Mesh Get archived chaos experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarchivedexperiments
- description: Chaos Mesh Delete archived experiments
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batchdeletearchivedexperiments
- description: Chaos Mesh Get an archived chaos experiment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarchivedexperiment
- description: Chaos Mesh Delete a specific archived experiment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletearchivedexperiment
- description: Chaos Mesh Get archived schedule experiments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarchivedschedules
- description: Chaos Mesh Delete archived schedules
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batchdeletearchivedschedules
- description: Chaos Mesh Get an archived schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarchivedschedule
- description: Chaos Mesh Delete an archived schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletearchivedschedule
- description: Chaos Mesh Get archived workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listarchivedworkflows
- description: Chaos Mesh Delete archived workflows
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: batchdeletearchivedworkflows
- description: Chaos Mesh Get an archived workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getarchivedworkflow
- description: Chaos Mesh Delete an archived workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletearchivedworkflow
- description: Chaos Mesh List chaos events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Chaos Mesh Get an event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: Chaos Mesh List events for a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkflowevents
- description: Chaos Mesh Get Dashboard configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardconfig
- description: Chaos Mesh Get all Kubernetes namespaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnamespaces
- description: Chaos Mesh Get namespaces available for chaos injection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchaosavailablenamespaces
- description: Chaos Mesh Get all available chaos kinds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchaoskinds
- description: Chaos Mesh Get pod labels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpodlabels
- description: Chaos Mesh Get pod annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpodannotations
- description: Chaos Mesh List pods matching a selector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listpods
- description: Chaos Mesh List physical machines matching a selector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listphysicalmachines
- description: Chaos Mesh Get RBAC configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrbacconfig
- description: Chaos Mesh List status check templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststatuschecktemplates
- description: Chaos Mesh Create a status check template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstatuschecktemplate
- description: Chaos Mesh Get a status check template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatuschecktemplate
- description: Chaos Mesh Update a status check template
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatestatuschecktemplate
- description: Chaos Mesh Delete a status check template
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletestatuschecktemplate
---
