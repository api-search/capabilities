---
categories:
- ci-cd
consumed_apis: []
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
- data integration
- list database and service connections
- restore a deployment from a backup
- restore deployment
- create a new oci goldengate deployment
- publish stream pipeline
- get deployment
- deployment backup management
- unpublish stream pipeline
- list ggsa stream analytics pipelines
- stop a running oci deployment
- upgrade an oci deployment to a newer version
- get details of a specific oci deployment
- check status of an asynchronous operation
- list pipelines
- real-time replication
- connection management
- stream analytics pipeline management
- list data replication pipelines
- upgrade deployment
- create pipeline
- list deployments
- create a new connection for a source or target system
- create a new data replication pipeline
- enterprise
- start pipeline
- data replication pipelines
- list backups
- get deployment details
- list asynchronous work requests
- list oci goldengate deployments in a compartment
- start a stopped pipeline
- publish a stream analytics pipeline to the spark runtime
- database
- list deployment backups
- get work request
- platform administration
- start a stopped oci deployment
- stop deployment
- unpublish a stream analytics pipeline
- oci goldengate deployment lifecycle management
- create deployment
- cloud management
- create a new oci deployment
- oci
- list connections
- async operation tracking
- oracle goldengate
- list stream pipelines
- list oci goldengate deployments
- start deployment
- create backup
- data synchronization
- cdc
- individual deployment operations
- list work requests
- create a deployment backup
- create connection
slug: cloud-management
source_filename: cloud-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Oracle GoldenGate Cloud Management\n  description: Unified workflow for managing Oracle GoldenGate cloud deployments in OCI. Combines the OCI Cloud Service API\n    with Stream Analytics for cloud platform administrators managing deployment lifecycle, connections, pipelines, backups,\n    and stream analytics in Oracle Cloud.\n  tags:\n  - Oracle GoldenGate\n  - OCI\n  - Cloud Management\n  - Platform Administration\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    OCI_API_KEY: OCI_API_KEY\n    GGSA_USERNAME: GGSA_USERNAME\n    GGSA_PASSWORD: GGSA_PASSWORD\ncapability:\n  consumes:\n  - type: http\n    namespace: goldengate-cloud\n    baseUri: https://goldengate.{region}.oci.oraclecloud.com\n    description: OCI GoldenGate Cloud Service API\n    authentication:\n      type: bearer\n      token: '{{OCI_API_KEY}}'\n    resources:\n    - name: deployments\n      path: /20200407/deployments\n      description:\
  \ GoldenGate deployment management in OCI\n      operations:\n      - name: list-deployments\n        method: GET\n        description: Returns a list of GoldenGate deployments in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Creates a new GoldenGate deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            compartmentId: '{{tools.compartmentId}}'\n            subnetId: '{{tools.subnetId}}'\n      - name: get-deployment\n        method: GET\n    \
  \    description: Returns details of a specific deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-deployment\n        method: PUT\n        description: Updates a deployment's configuration\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n      - name: delete-deployment\n        method: DELETE\n        description: Deletes a deployment\n        inputParameters:\n\
  \        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-deployment\n        method: POST\n        description: Starts a stopped deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-deployment\n        method: POST\n        description: Stops a running deployment\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n  \
  \      outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upgrade-deployment\n        method: POST\n        description: Upgrades a deployment to a newer version\n        inputParameters:\n        - name: deploymentId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: connections\n      path: /20200407/connections\n      description: Database and service connection management\n      operations:\n      - name: list-connections\n        method: GET\n        description: Returns a list of connections in a compartment\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n      \
  \  outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-connection\n        method: POST\n        description: Creates a new connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            compartmentId: '{{tools.compartmentId}}'\n            connectionType: '{{tools.connectionType}}'\n      - name: get-connection\n        method: GET\n        description: Returns a specific connection\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-connection\n        method: DELETE\n \
  \       description: Deletes a connection\n        inputParameters:\n        - name: connectionId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the connection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pipelines\n      path: /20200407/pipelines\n      description: Data replication pipeline management\n      operations:\n      - name: list-pipelines\n        method: GET\n        description: Returns a list of data replication pipelines\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-pipeline\n        method: POST\n        description: Creates a new pipeline\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            compartmentId: '{{tools.compartmentId}}'\n      - name: get-pipeline\n        method: GET\n        description: Returns a specific pipeline\n        inputParameters:\n        - name: pipelineId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-pipeline\n        method: POST\n        description: Starts a stopped pipeline\n        inputParameters:\n        - name: pipelineId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the pipeline\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: stop-pipeline\n        method: POST\n        description: Stops a running pipeline\n        inputParameters:\n        - name: pipelineId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the pipeline\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-backups\n      path: /20200407/deploymentBackups\n      description: Deployment backup management\n      operations:\n      - name: list-deployment-backups\n        method: GET\n        description: Returns a list of deployment backups\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: create-deployment-backup\n        method: POST\n        description: Creates a backup of a deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            displayName: '{{tools.displayName}}'\n            deploymentId: '{{tools.deploymentId}}'\n      - name: restore-deployment\n        method: POST\n        description: Restores a deployment from a backup\n        inputParameters:\n        - name: deploymentBackupId\n          in: path\n          type: string\n          required: true\n          description: The OCID of the backup\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: work-requests\n      path: /20200407/workRequests\n      description: Asynchronous operation tracking\n      operations:\n      - name:\
  \ list-work-requests\n        method: GET\n        description: Returns a list of work requests\n        inputParameters:\n        - name: compartmentId\n          in: query\n          type: string\n          required: true\n          description: The OCID of the compartment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-work-request\n        method: GET\n        description: Returns a specific work request\n        inputParameters:\n        - name: workRequestId\n          in: path\n          type: string\n          required: true\n          description: The work request ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: goldengate-stream-analytics\n    baseUri: https://{ggsa-host}:{port}/osa\n    description: Oracle GoldenGate Stream Analytics REST API\n    authentication:\n  \
  \    type: basic\n      username: '{{GGSA_USERNAME}}'\n      password: '{{GGSA_PASSWORD}}'\n    resources:\n    - name: pipelines\n      path: /services/v1/pipelines\n      description: Stream processing pipeline management\n      operations:\n      - name: list-pipelines\n        method: GET\n        description: Returns a list of all GGSA pipelines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: export-pipeline\n        method: GET\n        description: Exports a pipeline and all its dependencies as JSON\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Pipeline identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-pipeline\n        method: PATCH\n        description: Publishes a pipeline to the Spark\
  \ runtime\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Pipeline identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: unpublish-pipeline\n        method: PATCH\n        description: Unpublishes a pipeline, stopping execution\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Pipeline identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: artifacts\n      path: /services/v1/artifacts\n      description: Import and export GGSA artifacts\n      operations:\n      - name: import-artifacts\n        method: PATCH\n        description: Imports GGSA artifacts from a JSON document\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            pipeline: '{{tools.pipeline}}'\n    - name: users\n      path: /services/v1/authorizations\n      description: User management and authorization\n      operations:\n      - name: list-users\n        method: GET\n        description: Returns users for a specific role\n        inputParameters:\n        - name: role\n          in: path\n          type: string\n          required: true\n          description: Authorization role\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-user\n        method: GET\n        description: Returns details of a specific user\n        inputParameters:\n        - name: role\n          in: path\n          type: string\n          required: true\n          description: Authorization role\n        - name: user\n          in: path\n  \
  \        type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Creates a new user with the specified role\n        inputParameters:\n        - name: role\n          in: path\n          type: string\n          required: true\n          description: Authorization role\n        - name: user\n          in: path\n          type: string\n          required: true\n          description: Username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            password: '{{tools.password}}'\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: cloud-management-api\n    description: Unified REST API for Oracle GoldenGate cloud deployment management.\n\
  \    resources:\n    - path: /v1/deployments\n      name: deployments\n      description: OCI GoldenGate deployment lifecycle management\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List OCI GoldenGate deployments\n        call: goldengate-cloud.list-deployments\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n        description: Create a new OCI deployment\n        call: goldengate-cloud.create-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{deploymentId}\n      name: deployment-detail\n      description: Individual deployment operations\n      operations:\n      - method: GET\n        name: get-deployment\n        description: Get deployment details\n        call: goldengate-cloud.get-deployment\n        with:\n          deploymentId:\
  \ rest.deploymentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connections\n      name: connections\n      description: Connection management\n      operations:\n      - method: GET\n        name: list-connections\n        description: List database and service connections\n        call: goldengate-cloud.list-connections\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pipelines\n      name: pipelines\n      description: Data replication pipelines\n      operations:\n      - method: GET\n        name: list-pipelines\n        description: List data replication pipelines\n        call: goldengate-cloud.list-pipelines\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/backups\n      name: backups\n      description: Deployment backup management\n\
  \      operations:\n      - method: GET\n        name: list-backups\n        description: List deployment backups\n        call: goldengate-cloud.list-deployment-backups\n        with:\n          compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stream-pipelines\n      name: stream-pipelines\n      description: Stream analytics pipeline management\n      operations:\n      - method: GET\n        name: list-stream-pipelines\n        description: List GGSA stream analytics pipelines\n        call: goldengate-stream-analytics.list-pipelines\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/work-requests\n      name: work-requests\n      description: Async operation tracking\n      operations:\n      - method: GET\n        name: list-work-requests\n        description: List asynchronous work requests\n        call: goldengate-cloud.list-work-requests\n        with:\n        \
  \  compartmentId: rest.compartmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: cloud-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Oracle GoldenGate cloud management.\n    tools:\n    - name: list-deployments\n      description: List OCI GoldenGate deployments in a compartment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-cloud.list-deployments\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get details of a specific OCI deployment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-cloud.get-deployment\n      with:\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n      description: Create\
  \ a new OCI GoldenGate deployment\n      hints:\n        readOnly: false\n      call: goldengate-cloud.create-deployment\n      with:\n        displayName: tools.displayName\n        compartmentId: tools.compartmentId\n        subnetId: tools.subnetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-deployment\n      description: Start a stopped OCI deployment\n      hints:\n        readOnly: false\n      call: goldengate-cloud.start-deployment\n      with:\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-deployment\n      description: Stop a running OCI deployment\n      hints:\n        readOnly: false\n      call: goldengate-cloud.stop-deployment\n      with:\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upgrade-deployment\n      description: Upgrade an OCI deployment to a newer version\n    \
  \  hints:\n        readOnly: false\n      call: goldengate-cloud.upgrade-deployment\n      with:\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-connections\n      description: List database and service connections\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-cloud.list-connections\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-connection\n      description: Create a new connection for a source or target system\n      hints:\n        readOnly: false\n      call: goldengate-cloud.create-connection\n      with:\n        displayName: tools.displayName\n        compartmentId: tools.compartmentId\n        connectionType: tools.connectionType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pipelines\n      description: List data replication\
  \ pipelines\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-cloud.list-pipelines\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-pipeline\n      description: Create a new data replication pipeline\n      hints:\n        readOnly: false\n      call: goldengate-cloud.create-pipeline\n      with:\n        displayName: tools.displayName\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-pipeline\n      description: Start a stopped pipeline\n      hints:\n        readOnly: false\n      call: goldengate-cloud.start-pipeline\n      with:\n        pipelineId: tools.pipelineId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-backups\n      description: List deployment backups\n      hints:\n        readOnly: true\n        openWorld: true\n      call:\
  \ goldengate-cloud.list-deployment-backups\n      with:\n        compartmentId: tools.compartmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-backup\n      description: Create a deployment backup\n      hints:\n        readOnly: false\n      call: goldengate-cloud.create-deployment-backup\n      with:\n        displayName: tools.displayName\n        deploymentId: tools.deploymentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: restore-deployment\n      description: Restore a deployment from a backup\n      hints:\n        readOnly: false\n      call: goldengate-cloud.restore-deployment\n      with:\n        deploymentBackupId: tools.deploymentBackupId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-stream-pipelines\n      description: List GGSA stream analytics pipelines\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-stream-analytics.list-pipelines\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-stream-pipeline\n      description: Publish a stream analytics pipeline to the Spark runtime\n      hints:\n        readOnly: false\n      call: goldengate-stream-analytics.publish-pipeline\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: unpublish-stream-pipeline\n      description: Unpublish a stream analytics pipeline\n      hints:\n        readOnly: false\n      call: goldengate-stream-analytics.unpublish-pipeline\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-work-request\n      description: Check status of an asynchronous operation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: goldengate-cloud.get-work-request\n      with:\n        workRequestId: tools.workRequestId\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n"
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
