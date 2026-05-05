---
categories: []
consumed_apis:
- document-understanding
- orchestrator
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
- data extraction
- extract document
- list du projects
- list document understanding projects
- classify a document to identify its type (invoice, contract, form, etc.)
- list available ml extractors for a document understanding project
- ocr
- list available document understanding projects
- oversees the automation program pipeline, prioritization, and roi tracking
- robotic process automation
- list jobs
- monitors and manages running automations, robots, queues, and alerts
- uipath
- get document extraction results
- automation jobs for document processing
- digitize a document using ocr to extract text content
- manage automation pipeline, users, licenses, and quality
- Platform Administrator
- core rpa automation lifecycle from development to execution
- QA Engineer
- document understanding
- document classification
- document ocr digitization
- document processing
- get extraction result
- classify document
- creates and manages test projects, test cases, and execution reports
- document understanding projects
- orchestrator list jobs
- manage robots, jobs, queues, and assets in orchestrator
- extract document data
- artificial intelligence
- intelligent document processing
- enterprise automation
- list projects
- RPA Developer
- classify a document type
- orchestration
- platform configuration including users, groups, and licenses
- ocr digitize a document
- extract structured data fields from a document using an ml extractor
- list extractors
- machine learning
- extract structured data from document
- develops and deploys automation workflows using uipath studio and python sdk
- configures and manages document understanding models and extraction pipelines
- list document processing jobs
- testing
- day-to-day monitoring and management of running automations
- digitize document
- rpa
- CoE Manager
- retrieve the results of an asynchronous data extraction request
- manages users, groups, licenses, and organizational settings
- list orchestrator automation jobs for document processing workflows
- test management and automated quality verification
- extraction result retrieval
- Automation Operator
- intelligent processing of structured and unstructured documents
- automation
- oversight of the automation program including pipeline, compliance, and quality
- ocr, classify, and extract data from documents
- document data extraction
- Document Processing Specialist
slug: intelligent-document-processing
source_filename: intelligent-document-processing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"UiPath Intelligent Document Processing\"\n  description: \"End-to-end workflow for intelligent document processing combining Document Understanding for OCR and data extraction with Orchestrator for automation orchestration. Used by document processing teams and RPA developers building invoice, contract, and form automation workflows.\"\n  tags:\n    - UiPath\n    - Document Understanding\n    - Intelligent Document Processing\n    - OCR\n    - Data Extraction\n    - Machine Learning\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UIPATH_BEARER_TOKEN: UIPATH_BEARER_TOKEN\n\ncapability:\n  consumes:\n    - import: document-understanding\n      location: ./shared/document-understanding.yaml\n    - import: orchestrator\n      location: ./shared/orchestrator.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: idp-api\n      description: \"Unified REST API for\
  \ intelligent document processing using UiPath Document Understanding and Orchestrator.\"\n      resources:\n        - path: /v1/projects\n          name: projects\n          description: \"Document understanding projects\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List document understanding projects\"\n              call: \"document-understanding.list-projects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/digitize\n          name: digitization\n          description: \"Document OCR digitization\"\n          operations:\n            - method: POST\n              name: digitize-document\n              description: \"OCR digitize a document\"\n              call: \"document-understanding.digitize-document\"\n              with:\n                documentUrl: \"rest.documentUrl\"\n                projectId: \"rest.projectId\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/classify\n          name: classification\n          description: \"Document classification\"\n          operations:\n            - method: POST\n              name: classify-document\n              description: \"Classify a document type\"\n              call: \"document-understanding.classify-document\"\n              with:\n                documentUrl: \"rest.documentUrl\"\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/documents/extract\n          name: extraction\n          description: \"Document data extraction\"\n          operations:\n            - method: POST\n              name: extract-document\n              description: \"Extract structured data from document\"\n              call: \"document-understanding.extract-document\"\n \
  \             with:\n                documentUrl: \"rest.documentUrl\"\n                projectId: \"rest.projectId\"\n                extractorId: \"rest.extractorId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/extraction-results/{requestId}\n          name: extraction-results\n          description: \"Extraction result retrieval\"\n          operations:\n            - method: GET\n              name: get-extraction-result\n              description: \"Get document extraction results\"\n              call: \"document-understanding.get-extraction-result\"\n              with:\n                requestId: \"rest.requestId\"\n                projectId: \"rest.projectId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: \"Automation jobs for document processing\"\n          operations:\n    \
  \        - method: GET\n              name: list-jobs\n              description: \"List document processing jobs\"\n              call: \"orchestrator.list-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: idp-mcp\n      transport: http\n      description: \"MCP server for AI-assisted intelligent document processing using UiPath Document Understanding.\"\n      tools:\n        - name: list-du-projects\n          description: \"List available Document Understanding projects\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"document-understanding.list-projects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: digitize-document\n          description: \"Digitize a document using OCR to extract text content\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: false\n          call: \"document-understanding.digitize-document\"\n          with:\n            documentUrl: \"tools.documentUrl\"\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: classify-document\n          description: \"Classify a document to identify its type (invoice, contract, form, etc.)\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"document-understanding.classify-document\"\n          with:\n            documentUrl: \"tools.documentUrl\"\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extract-document-data\n          description: \"Extract structured data fields from a document using an ML extractor\"\n          hints:\n            readOnly: false\n            destructive:\
  \ false\n            idempotent: true\n          call: \"document-understanding.extract-document\"\n          with:\n            documentUrl: \"tools.documentUrl\"\n            projectId: \"tools.projectId\"\n            extractorId: \"tools.extractorId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-extraction-result\n          description: \"Retrieve the results of an asynchronous data extraction request\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"document-understanding.get-extraction-result\"\n          with:\n            requestId: \"tools.requestId\"\n            projectId: \"tools.projectId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-extractors\n          description: \"List available ML extractors for a Document Understanding project\"\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"document-understanding.list-extractors\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: orchestrator-list-jobs\n          description: \"List Orchestrator automation jobs for document processing workflows\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"orchestrator.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
