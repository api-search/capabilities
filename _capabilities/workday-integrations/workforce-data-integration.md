---
categories: []
consumed_apis: []
description: Unified capability for workforce data integration combining Workday REST API for HCM data access, RaaS for report-based data extraction, and Prism Analytics for loading external data into Workday. Enables HR systems integrators to build bidirectional workforce data pipelines.
layout: capability
name: Workday Integrations Workforce Data Integration
operations:
- description: List workers
  method: GET
  name: list-workers
  path: /v1/workers
- description: Get worker details
  method: GET
  name: get-worker
  path: /v1/workers/{workerId}
- description: List organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List positions
  method: GET
  name: list-positions
  path: /v1/positions
- description: Execute and retrieve report data
  method: GET
  name: get-report
  path: /v1/reports/{reportName}
- description: List Prism datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Create a Prism dataset
  method: POST
  name: create-dataset
  path: /v1/datasets
personas: []
provider_name: Workday Integrations
provider_slug: workday-integrations
search_terms:
- integrations
- analytics
- get benefit enrollments for a worker
- publish a prism analytics dataset for reporting
- enterprise software
- get report
- list prism datasets
- organizational structure
- workforce data
- prism analytics dataset management
- workday
- upload external data to a prism analytics dataset
- position records
- get worker details
- hcm
- integration
- list workday organizational structures
- execute and retrieve report data
- hr
- finance
- get detailed information about a specific worker
- get report metadata
- list prism analytics datasets
- get worker compensation
- create dataset
- list job profiles
- list workday workers including employees and contingent workers
- create a new prism analytics dataset
- create a prism dataset
- execute a workday raas report and return data
- list organizations
- individual worker data
- cloud
- list workers
- erp
- get field metadata for a workday report
- upload data to dataset
- list datasets
- list job profiles in workday
- get worker benefits
- get worker
- get compensation data for a worker
- report-as-a-service data access
- list workday position records
- worker record access
- publish dataset
- list positions
slug: workforce-data-integration
source_filename: workforce-data-integration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Workday Integrations Workforce Data Integration\n  description: Unified capability for workforce data integration combining Workday REST API for HCM data access, RaaS for\n    report-based data extraction, and Prism Analytics for loading external data into Workday. Enables HR systems integrators\n    to build bidirectional workforce data pipelines.\n  tags:\n  - Workday\n  - Integrations\n  - Workforce Data\n  - HCM\n  - Integration\n  - Analytics\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WORKDAY_INTEGRATIONS_ACCESS_TOKEN: WORKDAY_INTEGRATIONS_ACCESS_TOKEN\n    WORKDAY_TENANT: WORKDAY_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: workday-rest\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/v1/{tenant}\n    description: Workday REST API for business objects\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_INTEGRATIONS_ACCESS_TOKEN}}'\n    resources:\n\
  \    - name: workers\n      path: /workers\n      description: Worker record management\n      operations:\n      - name: list-workers\n        method: GET\n        description: List workers\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker\n        method: GET\n        description: Get a worker\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: get-worker-compensation\n        method: GET\n        description: Get worker compensation\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-worker-benefits\n        method: GET\n        description: Get worker benefit enrollments\n        inputParameters:\n        - name: workerId\n          in: path\n          type: string\n          required: true\n          description: Worker identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      description: Organization management\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List organizations\n\
  \        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-organization\n        method: GET\n        description: Get an organization\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions\n      description: Position management\n      operations:\n      - name: list-positions\n        method: GET\n        description: List positions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: job-profiles\n      path: /jobProfiles\n      description: Job profile management\n      operations:\n      - name: list-job-profiles\n        method: GET\n        description: List job profiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: business-processes\n      path: /businessProcesses\n      description: Business process workflow management\n      operations:\n      - name: list-business-processes\n        method: GET\n        description: List business processes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: raas\n    baseUri: https://wd2-impl-services1.workday.com/ccx/service/customreport2/{tenant}\n    description: Workday Report-as-a-Service API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_INTEGRATIONS_ACCESS_TOKEN}}'\n    resources:\n\
  \    - name: reports\n      path: /reports\n      description: Report execution\n      operations:\n      - name: get-report\n        method: GET\n        description: Get report data\n        inputParameters:\n        - name: reportName\n          in: path\n          type: string\n          required: true\n          description: Report name\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Output format (json, csv, xml)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-report-metadata\n        method: GET\n        description: Get report field metadata\n        inputParameters:\n        - name: reportName\n          in: path\n          type: string\n          required: true\n          description: Report name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n  - type: http\n    namespace: prism-analytics\n    baseUri: https://wd2-impl-services1.workday.com/ccx/api/prismAnalytics/v2/{tenant}\n    description: Workday Prism Analytics data ingestion API\n    authentication:\n      type: bearer\n      token: '{{WORKDAY_INTEGRATIONS_ACCESS_TOKEN}}'\n    resources:\n    - name: datasets\n      path: /datasets\n      description: Prism Analytics dataset management\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List datasets\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dataset\n        method: POST\n        description: Create a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            schema: '{{tools.schema}}'\n      - name: get-dataset\n        method: GET\n        description: Get a dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: upload-data-to-dataset\n        method: POST\n        description: Upload data to a dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \    body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: publish-dataset\n        method: POST\n        description: Publish a dataset\n        inputParameters:\n        - name: datasetId\n          in: path\n          type: string\n          required: true\n          description: Dataset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: workday-integrations-api\n    description: Unified REST API for Workday workforce data integration.\n    resources:\n    - path: /v1/workers\n      name: workers\n      description: Worker record access\n      operations:\n      - method: GET\n        name: list-workers\n        description: List workers\n        call: workday-rest.list-workers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workers/{workerId}\n      name:\
  \ worker-detail\n      description: Individual worker data\n      operations:\n      - method: GET\n        name: get-worker\n        description: Get worker details\n        call: workday-rest.get-worker\n        with:\n          workerId: rest.workerId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations\n      name: organizations\n      description: Organizational structure\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List organizations\n        call: workday-rest.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/positions\n      name: positions\n      description: Position records\n      operations:\n      - method: GET\n        name: list-positions\n        description: List positions\n        call: workday-rest.list-positions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{reportName}\n\
  \      name: reports\n      description: Report-as-a-Service data access\n      operations:\n      - method: GET\n        name: get-report\n        description: Execute and retrieve report data\n        call: raas.get-report\n        with:\n          reportName: rest.reportName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets\n      name: datasets\n      description: Prism Analytics dataset management\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List Prism datasets\n        call: prism-analytics.list-datasets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dataset\n        description: Create a Prism dataset\n        call: prism-analytics.create-dataset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: workday-integrations-mcp\n    transport: http\n  \
  \  description: MCP server for AI-assisted Workday workforce data integration.\n    tools:\n    - name: list-workers\n      description: List Workday workers including employees and contingent workers\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.list-workers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-worker\n      description: Get detailed information about a specific worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.get-worker\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-worker-compensation\n      description: Get compensation data for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.get-worker-compensation\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-worker-benefits\n      description: Get benefit enrollments for a worker\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.get-worker-benefits\n      with:\n        workerId: tools.workerId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-organizations\n      description: List Workday organizational structures\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-positions\n      description: List Workday position records\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.list-positions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-profiles\n      description: List job profiles in Workday\n      hints:\n        readOnly: true\n        openWorld: true\n      call: workday-rest.list-job-profiles\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report\n      description: Execute a Workday RaaS report and return data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: raas.get-report\n      with:\n        reportName: tools.reportName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-report-metadata\n      description: Get field metadata for a Workday report\n      hints:\n        readOnly: true\n        openWorld: true\n      call: raas.get-report-metadata\n      with:\n        reportName: tools.reportName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datasets\n      description: List Prism Analytics datasets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: prism-analytics.list-datasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dataset\n      description: Create a new Prism\
  \ Analytics dataset\n      hints:\n        readOnly: false\n        destructive: false\n      call: prism-analytics.create-dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: upload-data-to-dataset\n      description: Upload external data to a Prism Analytics dataset\n      hints:\n        readOnly: false\n        destructive: false\n      call: prism-analytics.upload-data-to-dataset\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-dataset\n      description: Publish a Prism Analytics dataset for reporting\n      hints:\n        readOnly: false\n        destructive: false\n      call: prism-analytics.publish-dataset\n      with:\n        datasetId: tools.datasetId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/workday-integrations/refs/heads/main/capabilities/workforce-data-integration.yaml
tags:
- Workday
- Integrations
- Workforce Data
- HCM
- Integration
- Analytics
tools:
- description: List Workday workers including employees and contingent workers
  hints:
    openWorld: true
    readOnly: true
  name: list-workers
- description: Get detailed information about a specific worker
  hints:
    openWorld: true
    readOnly: true
  name: get-worker
- description: Get compensation data for a worker
  hints:
    openWorld: true
    readOnly: true
  name: get-worker-compensation
- description: Get benefit enrollments for a worker
  hints:
    openWorld: true
    readOnly: true
  name: get-worker-benefits
- description: List Workday organizational structures
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List Workday position records
  hints:
    openWorld: true
    readOnly: true
  name: list-positions
- description: List job profiles in Workday
  hints:
    openWorld: true
    readOnly: true
  name: list-job-profiles
- description: Execute a Workday RaaS report and return data
  hints:
    openWorld: false
    readOnly: true
  name: get-report
- description: Get field metadata for a Workday report
  hints:
    openWorld: true
    readOnly: true
  name: get-report-metadata
- description: List Prism Analytics datasets
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Create a new Prism Analytics dataset
  hints:
    destructive: false
    readOnly: false
  name: create-dataset
- description: Upload external data to a Prism Analytics dataset
  hints:
    destructive: false
    readOnly: false
  name: upload-data-to-dataset
- description: Publish a Prism Analytics dataset for reporting
  hints:
    destructive: false
    readOnly: false
  name: publish-dataset
---
