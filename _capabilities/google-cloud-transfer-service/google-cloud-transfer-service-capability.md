---
categories: []
consumed_apis: []
description: The Storage Transfer API provides programmatic access to Google Cloud Storage Transfer Service for creating, managing, and monitoring data transfer jobs between cloud storage systems and on-premises storage. It supports scheduling transfers, configuring transfer options, managing agent pools, and monitoring transfer operations.
layout: capability
name: Google Cloud Transfer Service Google Storage Transfer API
operations:
- description: Google Cloud Transfer Service List transfer jobs
  method: GET
  name: listtransferjobs
  path: /transferJobs
- description: Google Cloud Transfer Service Create a transfer job
  method: POST
  name: createtransferjob
  path: /transferJobs
- description: Google Cloud Transfer Service Get a transfer job
  method: GET
  name: gettransferjob
  path: /transferJobs/{jobName}
- description: Google Cloud Transfer Service Update a transfer job
  method: PATCH
  name: updatetransferjob
  path: /transferJobs/{jobName}
- description: Google Cloud Transfer Service Run a transfer job
  method: POST
  name: runtransferjob
  path: /transferJobs/{jobName}:run
- description: Google Cloud Transfer Service List transfer operations
  method: GET
  name: listtransferoperations
  path: /transferOperations
- description: Google Cloud Transfer Service List agent pools
  method: GET
  name: listagentpools
  path: /projects/{projectId}/agentPools
- description: Google Cloud Transfer Service Create an agent pool
  method: POST
  name: createagentpool
  path: /projects/{projectId}/agentPools
personas: []
provider_name: Google Cloud Transfer Service
provider_slug: google-cloud-transfer-service
search_terms:
- createagentpool
- api
- google cloud transfer service list transfer jobs
- google cloud transfer service list transfer operations
- transfer
- s3
- listagentpools
- cloud storage
- migration
- service
- listtransferoperations
- google cloud transfer service get a transfer job
- google
- runtransferjob
- data transfer
- gettransferjob
- google cloud transfer service run a transfer job
- listtransferjobs
- google cloud transfer service create a transfer job
- updatetransferjob
- cloud
- storage
- google cloud transfer service list agent pools
- azure
- google cloud transfer service create an agent pool
- createtransferjob
- google cloud transfer service update a transfer job
slug: google-cloud-transfer-service-capability
source_filename: google-cloud-transfer-service-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Transfer Service Google Storage Transfer API\n  description: The Storage Transfer API provides programmatic access to Google Cloud Storage Transfer Service for creating,\n    managing, and monitoring data transfer jobs between cloud storage systems and on-premises storage. It supports scheduling\n    transfers, configuring transfer options, managing agent pools, and monitoring transfer operations.\n  tags:\n  - Google\n  - Cloud\n  - Transfer\n  - Service\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-transfer-service\n    baseUri: https://storagetransfer.googleapis.com/v1\n    description: Google Cloud Transfer Service Google Storage Transfer API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_TRANSFER_SERVICE_TOKEN}}'\n    resources:\n    - name: transferjobs\n      path: /transferJobs\n      operations:\n\
  \      - name: listtransferjobs\n        method: GET\n        description: Google Cloud Transfer Service List transfer jobs\n        inputParameters:\n        - name: filter\n          in: query\n          type: string\n          required: true\n          description: JSON filter for transfer jobs. Must include projectId field.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of results to return\n        - name: pageToken\n          in: query\n          type: string\n          description: Page token for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtransferjob\n        method: POST\n        description: Google Cloud Transfer Service Create a transfer job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transferjobs-jobname\n\
  \      path: /transferJobs/{jobName}\n      operations:\n      - name: gettransferjob\n        method: GET\n        description: Google Cloud Transfer Service Get a transfer job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n        - name: projectId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetransferjob\n        method: PATCH\n        description: Google Cloud Transfer Service Update a transfer job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transferjobs-jobname-run\n      path: /transferJobs/{jobName}:run\n      operations:\n\
  \      - name: runtransferjob\n        method: POST\n        description: Google Cloud Transfer Service Run a transfer job\n        inputParameters:\n        - name: jobName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transferoperations\n      path: /transferOperations\n      operations:\n      - name: listtransferoperations\n        method: GET\n        description: Google Cloud Transfer Service List transfer operations\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: The name of the type being listed (transferOperations)\n        - name: filter\n          in: query\n          type: string\n          required: true\n          description: JSON filter for operations\n        - name: pageSize\n          in: query\n          type: integer\n\
  \        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-agentpools\n      path: /projects/{projectId}/agentPools\n      operations:\n      - name: listagentpools\n        method: GET\n        description: Google Cloud Transfer Service List agent pools\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createagentpool\n        method: POST\n        description: Google Cloud Transfer Service Create an agent pool\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: agentPoolId\n          in: query\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-transfer-service-rest\n    description: REST adapter for Google Cloud Transfer Service Google Storage Transfer API.\n    resources:\n    - path: /transferJobs\n      name: listtransferjobs\n      operations:\n      - method: GET\n        name: listtransferjobs\n        description: Google Cloud Transfer Service List transfer jobs\n        call: google-cloud-transfer-service.listtransferjobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transferJobs\n      name: createtransferjob\n      operations:\n      - method: POST\n        name: createtransferjob\n        description: Google Cloud Transfer Service Create a transfer job\n        call: google-cloud-transfer-service.createtransferjob\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /transferJobs/{jobName}\n      name: gettransferjob\n      operations:\n      - method: GET\n        name: gettransferjob\n        description: Google Cloud Transfer Service Get a transfer job\n        call: google-cloud-transfer-service.gettransferjob\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transferJobs/{jobName}\n      name: updatetransferjob\n      operations:\n      - method: PATCH\n        name: updatetransferjob\n        description: Google Cloud Transfer Service Update a transfer job\n        call: google-cloud-transfer-service.updatetransferjob\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transferJobs/{jobName}:run\n      name: runtransferjob\n      operations:\n      - method: POST\n        name: runtransferjob\n        description: Google Cloud\
  \ Transfer Service Run a transfer job\n        call: google-cloud-transfer-service.runtransferjob\n        with:\n          jobName: rest.jobName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /transferOperations\n      name: listtransferoperations\n      operations:\n      - method: GET\n        name: listtransferoperations\n        description: Google Cloud Transfer Service List transfer operations\n        call: google-cloud-transfer-service.listtransferoperations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/agentPools\n      name: listagentpools\n      operations:\n      - method: GET\n        name: listagentpools\n        description: Google Cloud Transfer Service List agent pools\n        call: google-cloud-transfer-service.listagentpools\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/agentPools\n\
  \      name: createagentpool\n      operations:\n      - method: POST\n        name: createagentpool\n        description: Google Cloud Transfer Service Create an agent pool\n        call: google-cloud-transfer-service.createagentpool\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-transfer-service-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Transfer Service Google Storage Transfer API for AI agent use.\n    tools:\n    - name: listtransferjobs\n      description: Google Cloud Transfer Service List transfer jobs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-transfer-service.listtransferjobs\n      with:\n        filter: tools.filter\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: filter\n   \
  \     type: string\n        description: JSON filter for transfer jobs. Must include projectId field.\n        required: true\n      - name: pageSize\n        type: integer\n        description: Maximum number of results to return\n      - name: pageToken\n        type: string\n        description: Page token for pagination\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtransferjob\n      description: Google Cloud Transfer Service Create a transfer job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-transfer-service.createtransferjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettransferjob\n      description: Google Cloud Transfer Service Get a transfer job\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-transfer-service.gettransferjob\n      with:\n        jobName: tools.jobName\n\
  \        projectId: tools.projectId\n      inputParameters:\n      - name: jobName\n        type: string\n        description: jobName\n        required: true\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatetransferjob\n      description: Google Cloud Transfer Service Update a transfer job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-transfer-service.updatetransferjob\n      with:\n        jobName: tools.jobName\n      inputParameters:\n      - name: jobName\n        type: string\n        description: jobName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: runtransferjob\n      description: Google Cloud Transfer Service Run a transfer job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent:\
  \ false\n      call: google-cloud-transfer-service.runtransferjob\n      with:\n        jobName: tools.jobName\n      inputParameters:\n      - name: jobName\n        type: string\n        description: jobName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtransferoperations\n      description: Google Cloud Transfer Service List transfer operations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-transfer-service.listtransferoperations\n      with:\n        name: tools.name\n        filter: tools.filter\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: name\n        type: string\n        description: The name of the type being listed (transferOperations)\n        required: true\n      - name: filter\n        type: string\n        description: JSON filter for operations\n        required: true\n    \
  \  - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listagentpools\n      description: Google Cloud Transfer Service List agent pools\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-transfer-service.listagentpools\n      with:\n        projectId: tools.projectId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createagentpool\n      description: Google Cloud Transfer Service Create an agent pool\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-transfer-service.createagentpool\n      with:\n        projectId: tools.projectId\n\
  \        agentPoolId: tools.agentPoolId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: agentPoolId\n        type: string\n        description: agentPoolId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_TRANSFER_SERVICE_TOKEN: GOOGLE_CLOUD_TRANSFER_SERVICE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-transfer-service/refs/heads/main/capabilities/google-cloud-transfer-service-capability.yaml
tags:
- Google
- Cloud
- Transfer
- Service
- API
tools:
- description: Google Cloud Transfer Service List transfer jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransferjobs
- description: Google Cloud Transfer Service Create a transfer job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransferjob
- description: Google Cloud Transfer Service Get a transfer job
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransferjob
- description: Google Cloud Transfer Service Update a transfer job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatetransferjob
- description: Google Cloud Transfer Service Run a transfer job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runtransferjob
- description: Google Cloud Transfer Service List transfer operations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtransferoperations
- description: Google Cloud Transfer Service List agent pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listagentpools
- description: Google Cloud Transfer Service Create an agent pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createagentpool
---
