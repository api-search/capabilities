---
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
- apache
- manages orc file creation, conversion, and schema evolution
- list files
- big data
- convert to orc
- hadoop
- get column statistics
- data processing
- merge orc files
- convert csv, json, or parquet to orc format
- list orc files
- file format
- get file schema
- get the schema of an orc file
- merge multiple orc files into one
- convert
- Data Engineer
- get column statistics from an orc file
- reads orc files and analyzes column statistics
- apache orc
- columnar storage
- compression
- get metadata about an orc file
- get file metadata
- list available orc files
- Data Analyst
- open source
slug: orc-workflow
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
