---
categories: []
consumed_apis:
- analytics-cloud-data-export
- businessobjects-bi-platform
description: Workflow capability for extracting data from SAP Analytics Cloud models and managing BusinessObjects reports. Combines data export pipelines with traditional BI report scheduling and delivery. Used by data engineers, BI developers, and operations teams.
layout: capability
name: SAP BI Tools Data Extraction and Reporting
operations:
- description: List available namespaces for data export.
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: List available models (providers) for data export.
  method: GET
  name: list-providers
  path: /v1/namespaces/{namespaceId}/providers
- description: Extract fact data from a planning model.
  method: GET
  name: get-fact-data
  path: /v1/models/{modelId}/fact-data
- description: Extract master data (dimension members) from a model.
  method: GET
  name: get-master-data
  path: /v1/models/{modelId}/master-data
- description: Browse reports in the InfoStore repository.
  method: GET
  name: browse-reports
  path: /v1/reports
- description: Schedule a BusinessObjects report for immediate execution.
  method: POST
  name: schedule-report
  path: /v1/reports/{reportId}/schedule
- description: List completed report instances in the BI Inbox.
  method: GET
  name: list-inbox-items
  path: /v1/inbox
personas: []
provider_name: SAP BI Tools
provider_slug: sap-bi-tools
search_terms:
- browse reports
- list providers
- data export
- sap
- extract fact data
- extract master data (dimension members) from an analytics model.
- businessobjects report repository.
- bi user inbox.
- extract fact data from a planning model.
- get fact data
- list completed report instances in the user's bi inbox.
- model master data.
- data export namespaces.
- list inbox items
- list available namespaces for data export.
- schedule a businessobjects report for immediate execution.
- get master data
- search reports
- schedule a report for execution.
- extract fact data (transactional records) from an analytics model.
- analytics
- get odata metadata describing the structure of a planning model.
- list analytics models available for data export from sap analytics cloud.
- model fact data.
- model providers for data export.
- extract master data (dimension members) from a model.
- browse reports in the infostore repository.
- list export models
- list namespaces
- get model metadata
- reporting
- extract master data
- search for businessobjects reports and documents in the cms repository.
- data visualization
- schedule report
- business intelligence
- list available models (providers) for data export.
- list completed report instances in the bi inbox.
slug: data-extraction-and-reporting
source_filename: data-extraction-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP BI Tools Data Extraction and Reporting\"\n  description: \"Workflow capability for extracting data from SAP Analytics Cloud models and managing BusinessObjects reports. Combines data export pipelines with traditional BI report scheduling and delivery. Used by data engineers, BI developers, and operations teams.\"\n  tags:\n    - Analytics\n    - Business Intelligence\n    - Data Export\n    - Reporting\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_AC_OAUTH_TOKEN: SAP_AC_OAUTH_TOKEN\n      SAP_BOBJ_LOGON_TOKEN: SAP_BOBJ_LOGON_TOKEN\n\ncapability:\n  consumes:\n    - import: analytics-cloud-data-export\n      location: ./shared/analytics-cloud-data-export.yaml\n    - import: businessobjects-bi-platform\n      location: ./shared/businessobjects-bi-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: data-extraction-reporting-api\n\
  \      description: \"Unified REST API for SAP data extraction and BI report management.\"\n      resources:\n        - path: /v1/namespaces\n          name: namespaces\n          description: \"Data export namespaces.\"\n          operations:\n            - method: GET\n              name: list-namespaces\n              description: \"List available namespaces for data export.\"\n              call: \"analytics-cloud-data-export.list-namespaces\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/namespaces/{namespaceId}/providers\n          name: providers\n          description: \"Model providers for data export.\"\n          operations:\n            - method: GET\n              name: list-providers\n              description: \"List available models (providers) for data export.\"\n              call: \"analytics-cloud-data-export.list-providers\"\n              with:\n                namespaceId: \"rest.namespaceId\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{modelId}/fact-data\n          name: fact-data\n          description: \"Model fact data.\"\n          operations:\n            - method: GET\n              name: get-fact-data\n              description: \"Extract fact data from a planning model.\"\n              call: \"analytics-cloud-data-export.get-fact-data\"\n              with:\n                modelId: \"rest.modelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{modelId}/master-data\n          name: master-data\n          description: \"Model master data.\"\n          operations:\n            - method: GET\n              name: get-master-data\n              description: \"Extract master data (dimension members) from a model.\"\n              call: \"analytics-cloud-data-export.get-master-data\"\n              with:\n\
  \                modelId: \"rest.modelId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"BusinessObjects report repository.\"\n          operations:\n            - method: GET\n              name: browse-reports\n              description: \"Browse reports in the InfoStore repository.\"\n              call: \"businessobjects-bi-platform.get-infostore-root\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{reportId}/schedule\n          name: report-schedule\n          description: \"Schedule a report for execution.\"\n          operations:\n            - method: POST\n              name: schedule-report\n              description: \"Schedule a BusinessObjects report for immediate execution.\"\n              call: \"businessobjects-bi-platform.schedule-document\"\n           \
  \   with:\n                documentId: \"rest.reportId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/inbox\n          name: inbox\n          description: \"BI user inbox.\"\n          operations:\n            - method: GET\n              name: list-inbox-items\n              description: \"List completed report instances in the BI Inbox.\"\n              call: \"businessobjects-bi-platform.list-inbox-items\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: data-extraction-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted data extraction and BI report management.\"\n      tools:\n        - name: list-export-models\n          description: \"List analytics models available for data export from SAP Analytics Cloud.\"\n          hints:\n            readOnly: true\n          \
  \  openWorld: true\n          call: \"analytics-cloud-data-export.list-providers\"\n          with:\n            namespaceId: \"tools.namespaceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model-metadata\n          description: \"Get OData metadata describing the structure of a planning model.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"analytics-cloud-data-export.get-model-metadata\"\n          with:\n            modelId: \"tools.modelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: extract-fact-data\n          description: \"Extract fact data (transactional records) from an analytics model.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"analytics-cloud-data-export.get-fact-data\"\n          with:\n            modelId: \"tools.modelId\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: extract-master-data\n          description: \"Extract master data (dimension members) from an analytics model.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"analytics-cloud-data-export.get-master-data\"\n          with:\n            modelId: \"tools.modelId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-reports\n          description: \"Search for BusinessObjects reports and documents in the CMS repository.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"businessobjects-bi-platform.execute-cms-query\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: schedule-report\n          description: \"Schedule a BusinessObjects report for immediate execution.\"\
  \n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"businessobjects-bi-platform.schedule-document\"\n          with:\n            documentId: \"tools.documentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-inbox-items\n          description: \"List completed report instances in the user's BI Inbox.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"businessobjects-bi-platform.list-inbox-items\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi-tools/refs/heads/main/capabilities/data-extraction-and-reporting.yaml
tags:
- Analytics
- Business Intelligence
- Data Export
- Reporting
- SAP
tools:
- description: List analytics models available for data export from SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-export-models
- description: Get OData metadata describing the structure of a planning model.
  hints:
    openWorld: false
    readOnly: true
  name: get-model-metadata
- description: Extract fact data (transactional records) from an analytics model.
  hints:
    openWorld: false
    readOnly: true
  name: extract-fact-data
- description: Extract master data (dimension members) from an analytics model.
  hints:
    openWorld: false
    readOnly: true
  name: extract-master-data
- description: Search for BusinessObjects reports and documents in the CMS repository.
  hints:
    openWorld: true
    readOnly: true
  name: search-reports
- description: Schedule a BusinessObjects report for immediate execution.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: schedule-report
- description: List completed report instances in the user's BI Inbox.
  hints:
    openWorld: true
    readOnly: true
  name: list-inbox-items
---
