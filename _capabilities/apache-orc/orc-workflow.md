---
categories: []
consumed_apis: []
description: Workflow capability for reading, writing, converting, and analyzing Apache ORC columnar files.
layout: capability
name: Apache ORC File Processing Workflow
operations:
- description: List ORC files
  method: GET
  name: list-files
  path: /v1/files
- description: Convert to ORC
  method: POST
  name: convert
  path: /v1/convert
personas: []
provider_name: Apache ORC
provider_slug: apache-orc
search_terms:
- columnar storage
- open source
- compression
- get column statistics from an orc file
- Data Analyst
- manages orc file creation, conversion, and schema evolution
- list files
- get file schema
- get metadata about an orc file
- convert to orc
- file format
- get column statistics
- data processing
- Data Engineer
- convert
- apache
- list orc files
- hadoop
- convert csv, json, or parquet to orc format
- merge orc files
- merge multiple orc files into one
- big data
- get the schema of an orc file
- get file metadata
- reads orc files and analyzes column statistics
- apache orc
- list available orc files
slug: orc-workflow
source_yaml: "naftiko: \"1.0.0-alpha1\"\ninfo:\n  label: \"Apache ORC File Processing Workflow\"\n  description: \"Workflow capability for reading, writing, converting, and analyzing Apache ORC columnar files.\"\n  tags:\n    - Apache ORC\n    - Big Data\n    - Columnar Storage\n    - Data Processing\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\nbinds:\n  - namespace: env\n    keys:\n      ORC_API_KEY: ORC_API_KEY\ncapability:\n  consumes:\n    - type: http\n      namespace: orc\n      baseUri: https://localhost:8080/orc\n      description: \"Apache ORC REST service\"\n      resources:\n        - name: files\n          path: /files\n          description: \"ORC file management\"\n          operations:\n            - name: listFiles\n              method: GET\n              description: \"List ORC files\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n       \
  \ - name: convert\n          path: /convert\n          description: \"File conversion\"\n          operations:\n            - name: convertToOrc\n              method: POST\n              description: \"Convert files to ORC format\"\n              outputRawFormat: json\n              outputParameters:\n                - name: result\n                  type: object\n                  value: \"$.\"\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: orc-api\n      description: \"Unified REST API for ORC file operations.\"\n      resources:\n        - path: /v1/files\n          name: files\n          operations:\n            - method: GET\n              name: list-files\n              description: \"List ORC files\"\n              call: \"orc.listFiles\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/convert\n          name: convert\n          operations:\n            - method: POST\n              name:\
  \ convert\n              description: \"Convert to ORC\"\n              call: \"orc.convertToOrc\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n    - type: mcp\n      port: 9090\n      namespace: orc-mcp\n      transport: http\n      description: \"MCP server for AI-assisted ORC file operations.\"\n      tools:\n        - name: list-orc-files\n          description: \"List available ORC files\"\n          hints:\n            readOnly: true\n          call: \"orc.listFiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-schema\n          description: \"Get the schema of an ORC file\"\n          hints:\n            readOnly: true\n          call: \"orc.getFileSchema\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-metadata\n          description: \"Get metadata about an ORC file\"\n          hints:\n\
  \            readOnly: true\n          call: \"orc.getFileMetadata\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-column-statistics\n          description: \"Get column statistics from an ORC file\"\n          hints:\n            readOnly: true\n          call: \"orc.getColumnStatistics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: convert-to-orc\n          description: \"Convert CSV, JSON, or Parquet to ORC format\"\n          hints:\n            readOnly: false\n          call: \"orc.convertToOrc\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: merge-orc-files\n          description: \"Merge multiple ORC files into one\"\n          hints:\n            readOnly: false\n          call: \"orc.mergeOrcFiles\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-orc/refs/heads/main/capabilities/orc-workflow.yaml
tags:
- Apache ORC
- Big Data
- Columnar Storage
- Data Processing
tools:
- description: List available ORC files
  hints:
    readOnly: true
  name: list-orc-files
- description: Get the schema of an ORC file
  hints:
    readOnly: true
  name: get-file-schema
- description: Get metadata about an ORC file
  hints:
    readOnly: true
  name: get-file-metadata
- description: Get column statistics from an ORC file
  hints:
    readOnly: true
  name: get-column-statistics
- description: Convert CSV, JSON, or Parquet to ORC format
  hints:
    readOnly: false
  name: convert-to-orc
- description: Merge multiple ORC files into one
  hints:
    readOnly: false
  name: merge-orc-files
---
