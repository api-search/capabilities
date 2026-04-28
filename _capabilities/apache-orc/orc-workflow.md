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
- apache orc
- columnar storage
- convert to orc
- get column statistics
- get metadata about an orc file
- data processing
- file format
- convert
- Data Engineer
- get the schema of an orc file
- get file metadata
- compression
- Data Analyst
- reads orc files and analyzes column statistics
- list orc files
- merge multiple orc files into one
- apache
- list files
- get column statistics from an orc file
- merge orc files
- open source
- list available orc files
- big data
- convert csv, json, or parquet to orc format
- get file schema
- manages orc file creation, conversion, and schema evolution
- hadoop
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
