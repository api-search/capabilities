---
categories: []
consumed_apis: []
description: Workflow capability for platform and migration teams to manage mainframe application modernization, including application lifecycle management, environment configuration, and batch job execution on AWS.
layout: capability
name: Amazon Mainframe Modernization - Migration Workflow
operations:
- description: Create a modernization application
  method: POST
  name: create-application
  path: /v1/applications
- description: List modernization applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: Create a runtime environment
  method: POST
  name: create-environment
  path: /v1/environments
- description: List runtime environments
  method: GET
  name: list-environments
  path: /v1/environments
- description: Start a batch job
  method: POST
  name: start-batch-job
  path: /v1/applications/{id}/batch-jobs
- description: List batch jobs
  method: GET
  name: list-batch-jobs
  path: /v1/applications/{id}/batch-jobs
personas: []
provider_name: Amazon Mainframe Modernization
provider_slug: amazon-mainframe-modernization
search_terms:
- list environments
- mainframe
- create runtime environment
- develops and deploys modernized cobol/mainframe applications and manages batch job execution
- list batch job execution history for an application
- create a modernization application
- amazon
- create modernization application
- environment provisioning for running modernized applications
- cobol
- modernization
- batch job executions
- start a batch job
- execution of batch jobs migrated from mainframe
- runtime environments
- batch jobs
- list modernization applications
- creation and management of modernized mainframe applications
- create a runtime environment for modernized mainframe applications
- workflow for managing mainframe application modernization, environments, and batch jobs
- list batch job executions
- manages runtime environments and deployment infrastructure for modernized mainframe applications
- start batch job
- list runtime environments
- get application details
- list batch jobs
- list all mainframe applications being modernized
- Mainframe Developer
- migration
- create a runtime environment
- get details and status of a modernization application
- batch processing
- Platform Engineer
- create application
- start a batch job execution for a modernized mainframe application
- list applications
- create environment
- create a new mainframe modernization application on aws
- list all runtime environments available for deployment
- modernization applications
slug: modernization-workflow
source_filename: modernization-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Mainframe Modernization - Migration Workflow\n  description: Workflow capability for platform and migration teams to manage mainframe application modernization, including\n    application lifecycle management, environment configuration, and batch job execution on AWS.\n  tags:\n  - Amazon\n  - Mainframe\n  - Migration\n  - Modernization\n  - COBOL\n  - Batch Jobs\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: mainframe-modernization\n    baseUri: https://m2.amazonaws.com\n    description: AWS Mainframe Modernization REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: AWS4-HMAC-SHA256 {{AWS_ACCESS_KEY_ID}}\n      placement: header\n    resources:\n    - name: applications\n     \
  \ path: /applications\n      description: Manage modernization applications\n      operations:\n      - name: create-application\n        method: POST\n        description: Create a new modernization application\n        inputParameters:\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Application configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-applications\n        method: GET\n        description: List all modernization applications\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-application\n        method: GET\n        description: Get application details\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application\
  \ ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: environments\n      path: /environments\n      description: Manage runtime environments\n      operations:\n      - name: create-environment\n        method: POST\n        description: Create a runtime environment\n        inputParameters:\n        - name: body\n          in: body\n          type: object\n          required: true\n          description: Environment configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-environments\n        method: GET\n        description: List runtime environments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: batch-jobs\n      path: /applications/{applicationId}/batch-job-executions\n      description: Manage batch\
  \ job executions\n      operations:\n      - name: start-batch-job\n        method: POST\n        description: Start a batch job execution\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-batch-job-executions\n        method: GET\n        description: List batch job executions\n        inputParameters:\n        - name: applicationId\n          in: path\n          type: string\n          required: true\n          description: Application ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: modernization-api\n    description: Unified REST API for mainframe modernization workflows.\n    resources:\n\
  \    - path: /v1/applications\n      name: applications\n      description: Modernization applications\n      operations:\n      - method: POST\n        name: create-application\n        description: Create a modernization application\n        call: mainframe-modernization.create-application\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-applications\n        description: List modernization applications\n        call: mainframe-modernization.list-applications\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/environments\n      name: environments\n      description: Runtime environments\n      operations:\n      - method: POST\n        name: create-environment\n        description: Create a runtime environment\n        call: mainframe-modernization.create-environment\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-environments\n\
  \        description: List runtime environments\n        call: mainframe-modernization.list-environments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/applications/{id}/batch-jobs\n      name: batch-jobs\n      description: Batch job executions\n      operations:\n      - method: POST\n        name: start-batch-job\n        description: Start a batch job\n        call: mainframe-modernization.start-batch-job\n        with:\n          applicationId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-batch-jobs\n        description: List batch jobs\n        call: mainframe-modernization.list-batch-job-executions\n        with:\n          applicationId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: modernization-mcp\n    transport: http\n    description: MCP server for AI-assisted mainframe modernization\
  \ workflows.\n    tools:\n    - name: create-modernization-application\n      description: Create a new mainframe modernization application on AWS\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mainframe-modernization.create-application\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-modernization-applications\n      description: List all mainframe applications being modernized\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mainframe-modernization.list-applications\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-application-details\n      description: Get details and status of a modernization application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mainframe-modernization.get-application\n      with:\n        applicationId: tools.applicationId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-runtime-environment\n      description: Create a runtime environment for modernized mainframe applications\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mainframe-modernization.create-environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-runtime-environments\n      description: List all runtime environments available for deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mainframe-modernization.list-environments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-batch-job\n      description: Start a batch job execution for a modernized mainframe application\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: mainframe-modernization.start-batch-job\n\
  \      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-batch-job-executions\n      description: List batch job execution history for an application\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mainframe-modernization.list-batch-job-executions\n      with:\n        applicationId: tools.applicationId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-mainframe-modernization/refs/heads/main/capabilities/modernization-workflow.yaml
tags:
- Amazon
- Mainframe
- Migration
- Modernization
- COBOL
- Batch Jobs
tools:
- description: Create a new mainframe modernization application on AWS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-modernization-application
- description: List all mainframe applications being modernized
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-modernization-applications
- description: Get details and status of a modernization application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-application-details
- description: Create a runtime environment for modernized mainframe applications
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-runtime-environment
- description: List all runtime environments available for deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-runtime-environments
- description: Start a batch job execution for a modernized mainframe application
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: start-batch-job
- description: List batch job execution history for an application
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-batch-job-executions
---
