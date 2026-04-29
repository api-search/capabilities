---
categories:
- ci-cd
consumed_apis:
- goldengate-cloud
- goldengate-stream-analytics
description: Unified workflow for managing Oracle GoldenGate cloud deployments in OCI. Combines the OCI Cloud Service API with Stream Analytics for cloud platform administrators managing deployment lifecycle, connections, pipelines, backups, and stream analytics in Oracle Cloud.
layout: capability
name: Oracle GoldenGate Cloud Management
operations:
- description: List OCI GoldenGate deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Create a new OCI deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: Get deployment details
  method: GET
  name: get-deployment
  path: /v1/deployments/{deploymentId}
- description: List database and service connections
  method: GET
  name: list-connections
  path: /v1/connections
- description: List data replication pipelines
  method: GET
  name: list-pipelines
  path: /v1/pipelines
- description: List deployment backups
  method: GET
  name: list-backups
  path: /v1/backups
- description: List GGSA stream analytics pipelines
  method: GET
  name: list-stream-pipelines
  path: /v1/stream-pipelines
- description: List asynchronous work requests
  method: GET
  name: list-work-requests
  path: /v1/work-requests
personas: []
provider_name: Oracle GoldenGate
provider_slug: oracle-goldengate
search_terms:
- oci goldengate deployment lifecycle management
- list deployment backups
- oci
- create a new connection for a source or target system
- create backup
- create a deployment backup
- list work requests
- platform administration
- cdc
- create deployment
- stop deployment
- list deployments
- unpublish a stream analytics pipeline
- data synchronization
- start deployment
- get details of a specific oci deployment
- check status of an asynchronous operation
- list connections
- connection management
- data replication pipelines
- oracle goldengate
- list oci goldengate deployments
- get deployment
- start a stopped pipeline
- list data replication pipelines
- list asynchronous work requests
- data integration
- database
- stream analytics pipeline management
- async operation tracking
- cloud management
- deployment backup management
- unpublish stream pipeline
- individual deployment operations
- create a new oci deployment
- list ggsa stream analytics pipelines
- upgrade an oci deployment to a newer version
- create a new oci goldengate deployment
- list oci goldengate deployments in a compartment
- restore deployment
- enterprise
- create connection
- upgrade deployment
- publish a stream analytics pipeline to the spark runtime
- list database and service connections
- stop a running oci deployment
- create pipeline
- start pipeline
- publish stream pipeline
- list stream pipelines
- get deployment details
- list pipelines
- start a stopped oci deployment
- restore a deployment from a backup
- create a new data replication pipeline
- get work request
- real-time replication
- list backups
slug: cloud-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Oracle GoldenGate Cloud Management\"\n  description: \"Unified workflow for managing Oracle GoldenGate cloud deployments in OCI. Combines the OCI Cloud Service API with Stream Analytics for cloud platform administrators managing deployment lifecycle, connections, pipelines, backups, and stream analytics in Oracle Cloud.\"\n  tags:\n    - Oracle GoldenGate\n    - OCI\n    - Cloud Management\n    - Platform Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      OCI_API_KEY: OCI_API_KEY\n      GGSA_USERNAME: GGSA_USERNAME\n      GGSA_PASSWORD: GGSA_PASSWORD\n\ncapability:\n  consumes:\n    - import: goldengate-cloud\n      location: ./shared/goldengate-cloud-service.yaml\n    - import: goldengate-stream-analytics\n      location: ./shared/goldengate-stream-analytics.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: cloud-management-api\n      description:\
  \ \"Unified REST API for Oracle GoldenGate cloud deployment management.\"\n      resources:\n        - path: /v1/deployments\n          name: deployments\n          description: \"OCI GoldenGate deployment lifecycle management\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List OCI GoldenGate deployments\"\n              call: \"goldengate-cloud.list-deployments\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Create a new OCI deployment\"\n              call: \"goldengate-cloud.create-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/deployments/{deploymentId}\n          name: deployment-detail\n          description:\
  \ \"Individual deployment operations\"\n          operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get deployment details\"\n              call: \"goldengate-cloud.get-deployment\"\n              with:\n                deploymentId: \"rest.deploymentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/connections\n          name: connections\n          description: \"Connection management\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List database and service connections\"\n              call: \"goldengate-cloud.list-connections\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/pipelines\n          name: pipelines\n          description: \"\
  Data replication pipelines\"\n          operations:\n            - method: GET\n              name: list-pipelines\n              description: \"List data replication pipelines\"\n              call: \"goldengate-cloud.list-pipelines\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/backups\n          name: backups\n          description: \"Deployment backup management\"\n          operations:\n            - method: GET\n              name: list-backups\n              description: \"List deployment backups\"\n              call: \"goldengate-cloud.list-deployment-backups\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stream-pipelines\n          name: stream-pipelines\n          description:\
  \ \"Stream analytics pipeline management\"\n          operations:\n            - method: GET\n              name: list-stream-pipelines\n              description: \"List GGSA stream analytics pipelines\"\n              call: \"goldengate-stream-analytics.list-pipelines\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/work-requests\n          name: work-requests\n          description: \"Async operation tracking\"\n          operations:\n            - method: GET\n              name: list-work-requests\n              description: \"List asynchronous work requests\"\n              call: \"goldengate-cloud.list-work-requests\"\n              with:\n                compartmentId: \"rest.compartmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: cloud-management-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Oracle GoldenGate cloud management.\"\n      tools:\n        - name: list-deployments\n          description: \"List OCI GoldenGate deployments in a compartment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.list-deployments\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-deployment\n          description: \"Get details of a specific OCI deployment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.get-deployment\"\n          with:\n            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-deployment\n          description: \"Create a new OCI GoldenGate deployment\"\n          hints:\n            readOnly:\
  \ false\n          call: \"goldengate-cloud.create-deployment\"\n          with:\n            displayName: \"tools.displayName\"\n            compartmentId: \"tools.compartmentId\"\n            subnetId: \"tools.subnetId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-deployment\n          description: \"Start a stopped OCI deployment\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.start-deployment\"\n          with:\n            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-deployment\n          description: \"Stop a running OCI deployment\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.stop-deployment\"\n          with:\n            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n        - name: upgrade-deployment\n          description: \"Upgrade an OCI deployment to a newer version\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.upgrade-deployment\"\n          with:\n            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-connections\n          description: \"List database and service connections\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.list-connections\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-connection\n          description: \"Create a new connection for a source or target system\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.create-connection\"\n          with:\n\
  \            displayName: \"tools.displayName\"\n            compartmentId: \"tools.compartmentId\"\n            connectionType: \"tools.connectionType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-pipelines\n          description: \"List data replication pipelines\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.list-pipelines\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-pipeline\n          description: \"Create a new data replication pipeline\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.create-pipeline\"\n          with:\n            displayName: \"tools.displayName\"\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n    \
  \          mapping: \"$.\"\n        - name: start-pipeline\n          description: \"Start a stopped pipeline\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.start-pipeline\"\n          with:\n            pipelineId: \"tools.pipelineId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-backups\n          description: \"List deployment backups\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.list-deployment-backups\"\n          with:\n            compartmentId: \"tools.compartmentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-backup\n          description: \"Create a deployment backup\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.create-deployment-backup\"\n          with:\n            displayName: \"tools.displayName\"\n\
  \            deploymentId: \"tools.deploymentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: restore-deployment\n          description: \"Restore a deployment from a backup\"\n          hints:\n            readOnly: false\n          call: \"goldengate-cloud.restore-deployment\"\n          with:\n            deploymentBackupId: \"tools.deploymentBackupId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-stream-pipelines\n          description: \"List GGSA stream analytics pipelines\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-stream-analytics.list-pipelines\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-stream-pipeline\n          description: \"Publish a stream analytics pipeline to the Spark runtime\"\n          hints:\n            readOnly:\
  \ false\n          call: \"goldengate-stream-analytics.publish-pipeline\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: unpublish-stream-pipeline\n          description: \"Unpublish a stream analytics pipeline\"\n          hints:\n            readOnly: false\n          call: \"goldengate-stream-analytics.unpublish-pipeline\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-work-request\n          description: \"Check status of an asynchronous operation\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"goldengate-cloud.get-work-request\"\n          with:\n            workRequestId: \"tools.workRequestId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/oracle-goldengate/refs/heads/main/capabilities/cloud-management.yaml
tags:
- Oracle GoldenGate
- OCI
- Cloud Management
- Platform Administration
tools:
- description: List OCI GoldenGate deployments in a compartment
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Get details of a specific OCI deployment
  hints:
    openWorld: true
    readOnly: true
  name: get-deployment
- description: Create a new OCI GoldenGate deployment
  hints:
    readOnly: false
  name: create-deployment
- description: Start a stopped OCI deployment
  hints:
    readOnly: false
  name: start-deployment
- description: Stop a running OCI deployment
  hints:
    readOnly: false
  name: stop-deployment
- description: Upgrade an OCI deployment to a newer version
  hints:
    readOnly: false
  name: upgrade-deployment
- description: List database and service connections
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: Create a new connection for a source or target system
  hints:
    readOnly: false
  name: create-connection
- description: List data replication pipelines
  hints:
    openWorld: true
    readOnly: true
  name: list-pipelines
- description: Create a new data replication pipeline
  hints:
    readOnly: false
  name: create-pipeline
- description: Start a stopped pipeline
  hints:
    readOnly: false
  name: start-pipeline
- description: List deployment backups
  hints:
    openWorld: true
    readOnly: true
  name: list-backups
- description: Create a deployment backup
  hints:
    readOnly: false
  name: create-backup
- description: Restore a deployment from a backup
  hints:
    readOnly: false
  name: restore-deployment
- description: List GGSA stream analytics pipelines
  hints:
    openWorld: true
    readOnly: true
  name: list-stream-pipelines
- description: Publish a stream analytics pipeline to the Spark runtime
  hints:
    readOnly: false
  name: publish-stream-pipeline
- description: Unpublish a stream analytics pipeline
  hints:
    readOnly: false
  name: unpublish-stream-pipeline
- description: Check status of an asynchronous operation
  hints:
    openWorld: true
    readOnly: true
  name: get-work-request
---
