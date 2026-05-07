---
categories: []
consumed_apis: []
description: End-to-end workflow for intelligent document processing combining Document Understanding for OCR and data extraction with Orchestrator for automation orchestration. Used by document processing teams and RPA developers building invoice, contract, and form automation workflows.
layout: capability
name: UiPath Intelligent Document Processing
operations:
- description: List document understanding projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: OCR digitize a document
  method: POST
  name: digitize-document
  path: /v1/documents/digitize
- description: Classify a document type
  method: POST
  name: classify-document
  path: /v1/documents/classify
- description: Extract structured data from document
  method: POST
  name: extract-document
  path: /v1/documents/extract
- description: Get document extraction results
  method: GET
  name: get-extraction-result
  path: /v1/extraction-results/{requestId}
- description: List document processing jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
personas: []
provider_name: UiPath
provider_slug: uipath
search_terms:
- Automation Operator
- oversight of the automation program including pipeline, compliance, and quality
- document understanding projects
- extract structured data from document
- list orchestrator automation jobs for document processing workflows
- testing
- automation
- document classification
- robotic process automation
- intelligent document processing
- classify a document type
- day-to-day monitoring and management of running automations
- extract document data
- develops and deploys automation workflows using uipath studio and python sdk
- uipath
- ocr
- artificial intelligence
- get extraction result
- extract structured data fields from a document using an ml extractor
- manage automation pipeline, users, licenses, and quality
- list document processing jobs
- data extraction
- configures and manages document understanding models and extraction pipelines
- list available ml extractors for a document understanding project
- intelligent processing of structured and unstructured documents
- orchestration
- machine learning
- creates and manages test projects, test cases, and execution reports
- document data extraction
- list extractors
- QA Engineer
- list projects
- extract document
- RPA Developer
- list document understanding projects
- ocr digitize a document
- document ocr digitization
- CoE Manager
- list du projects
- classify document
- test management and automated quality verification
- Platform Administrator
- list jobs
- get document extraction results
- platform configuration including users, groups, and licenses
- document understanding
- digitize document
- manage robots, jobs, queues, and assets in orchestrator
- list available document understanding projects
- extraction result retrieval
- monitors and manages running automations, robots, queues, and alerts
- automation jobs for document processing
- manages users, groups, licenses, and organizational settings
- rpa
- enterprise automation
- classify a document to identify its type (invoice, contract, form, etc.)
- Document Processing Specialist
- document processing
- core rpa automation lifecycle from development to execution
- digitize a document using ocr to extract text content
- ocr, classify, and extract data from documents
- orchestrator list jobs
- retrieve the results of an asynchronous data extraction request
- oversees the automation program pipeline, prioritization, and roi tracking
slug: intelligent-document-processing
source_filename: intelligent-document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: UiPath Intelligent Document Processing\n  description: End-to-end workflow for intelligent document processing combining Document Understanding for OCR and data extraction\n    with Orchestrator for automation orchestration. Used by document processing teams and RPA developers building invoice,\n    contract, and form automation workflows.\n  tags:\n  - UiPath\n  - Document Understanding\n  - Intelligent Document Processing\n  - OCR\n  - Data Extraction\n  - Machine Learning\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: document-understanding\n    baseUri: https://cloud.uipath.com/{organizationName}/{tenantName}/du_/api/framework\n    description: UiPath Document Understanding API for processing and extracting data from documents.\n    authentication:\n      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n\
  \    resources:\n    - name: projects\n      path: /projects\n      description: Manage document understanding projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: List all document understanding projects\n        inputParameters:\n        - name: api-version\n          in: query\n          type: string\n          required: false\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-extractors\n        method: GET\n        description: List available extractors for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-classifiers\n        method: GET\n\
  \        description: List available classifiers for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: digitization\n      path: /projects/{projectId}/digitization/start\n      description: Document digitization (OCR)\n      operations:\n      - name: digitize-document\n        method: POST\n        description: Start document digitization (OCR processing)\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            documentUrl: '{{tools.documentUrl}}'\n\
  \    - name: classification\n      path: /projects/{projectId}/classification/start\n      description: Document classification\n      operations:\n      - name: classify-document\n        method: POST\n        description: Start asynchronous document classification\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            documentUrl: '{{tools.documentUrl}}'\n      - name: get-classification-result\n        method: GET\n        description: Get the result of a classification request\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: requestId\n          in: path\n\
  \          type: string\n          required: true\n          description: Classification request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: extraction\n      path: /projects/{projectId}/extraction/start\n      description: Document data extraction\n      operations:\n      - name: extract-document\n        method: POST\n        description: Start asynchronous document data extraction\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            documentUrl: '{{tools.documentUrl}}'\n            extractorId: '{{tools.extractorId}}'\n      - name: get-extraction-result\n        method: GET\n\
  \        description: Get the result of a data extraction request\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: Extraction request identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: orchestrator\n    baseUri: https://cloud.uipath.com/{organizationName}/{tenantName}/orchestrator_\n    description: UiPath Orchestrator API for managing automation robots, jobs, queues, and assets.\n    authentication:\n      type: bearer\n      token: '{{UIPATH_BEARER_TOKEN}}'\n    resources:\n    - name: jobs\n      path: /odata/Jobs\n      description: Manage automation job execution\n      operations:\n      - name: list-jobs\n        method: GET\n \
  \       description: List automation jobs with filtering\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of records to return\n        - name: $skip\n          in: query\n          type: integer\n          required: false\n          description: Number of records to skip\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get a specific job by key\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Job identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: start-jobs\n        method: POST\n        description: Start one or more automation jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            startInfo: '{{tools.startInfo}}'\n      - name: stop-job\n        method: POST\n        description: Stop a running automation job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            jobId: '{{tools.jobId}}'\n    - name: processes\n      path: /odata/Processes\n      description: Manage automation processes\n      operations:\n      - name: list-processes\n        method: GET\n        description: List deployed automation processes\n        inputParameters:\n        - name: $top\n          in: query\n          type: integer\n\
  \          required: false\n          description: Maximum number of records\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /odata/QueueDefinitions\n      description: Manage transaction queues\n      operations:\n      - name: list-queues\n        method: GET\n        description: List all queue definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new queue definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.queueName}}'\n    - name: queue-items\n      path: /odata/QueueItems\n      description: Manage queue transaction items\n      operations:\n\
  \      - name: list-queue-items\n        method: GET\n        description: List queue transaction items\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-queue-item\n        method: POST\n        description: Add a new item to a queue\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            itemData: '{{tools.itemData}}'\n    - name: assets\n      path: /odata/Assets\n      description: Manage shared assets like credentials and values\n      operations:\n      - name: list-assets\n        method: GET\n        description: List all shared assets\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: create-asset\n        method: POST\n        description: Create a new shared asset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.assetName}}'\n            ValueType: '{{tools.valueType}}'\n      - name: get-asset\n        method: GET\n        description: Get a specific asset by key\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-asset\n        method: PUT\n        description: Update an existing asset\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n\
  \          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Value: '{{tools.value}}'\n      - name: delete-asset\n        method: DELETE\n        description: Delete an asset\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Asset identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: robots\n      path: /odata/Robots\n      description: Manage automation robots\n      operations:\n      - name: list-robots\n        method: GET\n        description: List all registered robots\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: alerts\n      path: /odata/Alerts\n      description: Retrieve system and automation alerts\n      operations:\n      - name: list-alerts\n        method: GET\n        description: List system alerts and notifications\n        inputParameters:\n        - name: $filter\n          in: query\n          type: string\n          required: false\n          description: OData filter expression\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /odata/Webhooks\n      description: Manage webhook subscriptions\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List all webhook subscriptions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create a new webhook subscription\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Url: '{{tools.webhookUrl}}'\n            EventTypes: '{{tools.eventTypes}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Delete a webhook subscription\n        inputParameters:\n        - name: key\n          in: path\n          type: integer\n          required: true\n          description: Webhook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: idp-api\n    description: Unified REST API for intelligent document processing using UiPath Document Understanding and Orchestrator.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Document understanding projects\n      operations:\n      - method: GET\n        name:\
  \ list-projects\n        description: List document understanding projects\n        call: document-understanding.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/digitize\n      name: digitization\n      description: Document OCR digitization\n      operations:\n      - method: POST\n        name: digitize-document\n        description: OCR digitize a document\n        call: document-understanding.digitize-document\n        with:\n          documentUrl: rest.documentUrl\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/classify\n      name: classification\n      description: Document classification\n      operations:\n      - method: POST\n        name: classify-document\n        description: Classify a document type\n        call: document-understanding.classify-document\n        with:\n          documentUrl: rest.documentUrl\n     \
  \     projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/documents/extract\n      name: extraction\n      description: Document data extraction\n      operations:\n      - method: POST\n        name: extract-document\n        description: Extract structured data from document\n        call: document-understanding.extract-document\n        with:\n          documentUrl: rest.documentUrl\n          projectId: rest.projectId\n          extractorId: rest.extractorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extraction-results/{requestId}\n      name: extraction-results\n      description: Extraction result retrieval\n      operations:\n      - method: GET\n        name: get-extraction-result\n        description: Get document extraction results\n        call: document-understanding.get-extraction-result\n        with:\n          requestId: rest.requestId\n          projectId: rest.projectId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Automation jobs for document processing\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List document processing jobs\n        call: orchestrator.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: idp-mcp\n    transport: http\n    description: MCP server for AI-assisted intelligent document processing using UiPath Document Understanding.\n    tools:\n    - name: list-du-projects\n      description: List available Document Understanding projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: document-understanding.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: digitize-document\n      description: Digitize a document using OCR to extract text content\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: document-understanding.digitize-document\n      with:\n        documentUrl: tools.documentUrl\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: classify-document\n      description: Classify a document to identify its type (invoice, contract, form, etc.)\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: document-understanding.classify-document\n      with:\n        documentUrl: tools.documentUrl\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-document-data\n      description: Extract structured data fields from a document using an ML extractor\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: document-understanding.extract-document\n      with:\n\
  \        documentUrl: tools.documentUrl\n        projectId: tools.projectId\n        extractorId: tools.extractorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-extraction-result\n      description: Retrieve the results of an asynchronous data extraction request\n      hints:\n        readOnly: true\n        openWorld: true\n      call: document-understanding.get-extraction-result\n      with:\n        requestId: tools.requestId\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-extractors\n      description: List available ML extractors for a Document Understanding project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: document-understanding.list-extractors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: orchestrator-list-jobs\n      description: List Orchestrator automation jobs for document processing workflows\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: orchestrator.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/uipath/refs/heads/main/capabilities/intelligent-document-processing.yaml
tags:
- UiPath
- Document Understanding
- Intelligent Document Processing
- OCR
- Data Extraction
- Machine Learning
tools:
- description: List available Document Understanding projects
  hints:
    openWorld: true
    readOnly: true
  name: list-du-projects
- description: Digitize a document using OCR to extract text content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: digitize-document
- description: Classify a document to identify its type (invoice, contract, form, etc.)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: classify-document
- description: Extract structured data fields from a document using an ML extractor
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: extract-document-data
- description: Retrieve the results of an asynchronous data extraction request
  hints:
    openWorld: true
    readOnly: true
  name: get-extraction-result
- description: List available ML extractors for a Document Understanding project
  hints:
    openWorld: true
    readOnly: true
  name: list-extractors
- description: List Orchestrator automation jobs for document processing workflows
  hints:
    openWorld: true
    readOnly: true
  name: orchestrator-list-jobs
---
