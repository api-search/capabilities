---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Poi Workflow
operations: []
personas: []
provider_name: Apache POI
provider_slug: apache-poi
search_terms:
- excel
- microsoft office
- workflow for extracting data from excel, word, and powerpoint files
- java
- developer generating automated excel or word reports
- engineer extracting and transforming data from office files
- word
- open source
- document processing
- powerpoint
- apache
- creation, manipulation, and conversion of office documents
- end-to-end workflow for creating and manipulating office documents
- extracting structured data from office file formats
- java developer building office document generation features
slug: poi-workflow
source_filename: poi-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache POI Document Processing Workflow\ndescription: Workflow capability for creating and manipulating Microsoft Office documents using Apache POI.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache POI API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-poi/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/poi-api.yaml\nworkflow:\n  name: poi-workflow\n  description: Process and transform Microsoft Office documents using Apache POI.\n  steps:\n    - name: create-workbook\n      description: Create a new Excel workbook\n      api: Apache POI API\n      operation: createWorkbook\n    - name: get-cells\n      description: Extract cell data from a workbook sheet\n      api: Apache POI API\n      operation: getCells\n    - name: create-document\n      description: Create a Word document\n      api: Apache POI API\n      operation: createDocument\n    - name: create-presentation\n      description: Create a PowerPoint presentation\n      api:\
  \ Apache POI API\n      operation: createPresentation\n    - name: convert-document\n      description: Convert between Office formats\n      api: Apache POI API\n      operation: convertDocument\nexposes:\n  - type: rest\n    port: 8080\n    paths:\n      - /workbooks\n      - /workbooks/{workbookId}\n      - /workbooks/{workbookId}/sheets\n      - /documents\n      - /documents/{documentId}\n      - /presentations\n      - /presentations/{presentationId}\n      - /convert\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-workbooks\n        description: List Excel workbooks\n        operation: listWorkbooks\n      - name: create-workbook\n        description: Create an Excel workbook\n        operation: createWorkbook\n      - name: get-cells\n        description: Get cell data from a sheet\n        operation: getCells\n      - name: create-document\n        description: Create a Word document\n        operation: createDocument\n      - name: get-document\n        description:\
  \ Retrieve a Word document\n        operation: getDocument\n      - name: create-presentation\n        description: Create a PowerPoint presentation\n        operation: createPresentation\n      - name: get-presentation\n        description: Retrieve a PowerPoint presentation\n        operation: getPresentation\n      - name: convert-document\n        description: Convert between Office document formats\n        operation: convertDocument\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-poi/refs/heads/main/capabilities/poi-workflow.yaml
tags: []
tools: []
---
