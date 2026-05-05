---
categories: []
consumed_apis:
- eikon-datascope
- eikon-tick-history
description: Unified workflow capability for data engineers and quant analysts extracting bulk financial data from Refinitiv Eikon via DataScope Select and Tick History REST APIs. Combines pricing, corporate actions, reference data, and tick-level market data extraction workflows into a single interface.
layout: capability
name: Refinitiv Eikon Data Extraction
operations:
- description: Execute a DataScope Select on-demand extraction.
  method: POST
  name: extract-data
  path: /v1/extractions
- description: List files from completed extractions.
  method: GET
  name: list-extracted-files
  path: /v1/extractions/files
- description: Search DataScope for instruments.
  method: POST
  name: search-instruments
  path: /v1/instruments/search
- description: List all instrument lists.
  method: GET
  name: list-instrument-lists
  path: /v1/instrument-lists
- description: Create a new instrument list.
  method: POST
  name: create-instrument-list
  path: /v1/instrument-lists
- description: Execute a tick history extraction.
  method: POST
  name: extract-tick-history
  path: /v1/tick-history/extractions
- description: List tick extraction jobs.
  method: GET
  name: list-tick-jobs
  path: /v1/tick-history/jobs
- description: Get tick extraction job status.
  method: GET
  name: get-tick-job-status
  path: /v1/tick-history/jobs/{jobId}
- description: Cancel a running tick extraction job.
  method: DELETE
  name: cancel-tick-job
  path: /v1/tick-history/jobs/{jobId}
personas: []
provider_name: Refinitiv Eikon
provider_slug: refinitiv-eikon
search_terms:
- create instrument list
- data extraction
- individual tick extraction job.
- execute a datascope select on-demand extraction for pricing, corporate actions, or reference data.
- list all instrument lists.
- list instrument lists
- list extracted files
- list all saved instrument lists for datascope extractions.
- market data
- datascope search instruments
- on-demand data extractions.
- analytics
- instrument search.
- get tick extraction job status.
- get tick job status
- financial data
- datascope extract data
- extracted data files.
- financial news
- datascope list extracted files
- execute a tick history extraction.
- real-time data
- datascope list instrument lists
- tick history extractions.
- get the current status and details of a specific tick history extraction job.
- corporate actions
- list files produced by completed datascope extractions.
- tick history
- tick extraction job monitoring.
- list all tick history extraction jobs and their current statuses.
- search datascope select for financial instruments by ric, isin, cusip, or ticker.
- tick history cancel job
- cancel a running tick history extraction job.
- tick history get job status
- datascope select
- execute an on-demand tick history extraction for time-and-sales or intraday bars.
- cancel tick job
- search instruments
- list files from completed extractions.
- list tick jobs
- trading
- search datascope for instruments.
- refinitiv eikon
- execute a datascope select on-demand extraction.
- extract tick history
- extract data
- create a new instrument list.
- tick history extract
- cancel a running tick extraction job.
- quantitative analysis
- tick history list jobs
- list tick extraction jobs.
- instrument list management.
slug: data-extraction
source_filename: data-extraction.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Refinitiv Eikon Data Extraction\"\n  description: >-\n    Unified workflow capability for data engineers and quant analysts extracting\n    bulk financial data from Refinitiv Eikon via DataScope Select and Tick History\n    REST APIs. Combines pricing, corporate actions, reference data, and tick-level\n    market data extraction workflows into a single interface.\n  tags:\n    - Refinitiv Eikon\n    - Data Extraction\n    - DataScope Select\n    - Tick History\n    - Corporate Actions\n    - Quantitative Analysis\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      DATASCOPE_TOKEN: DATASCOPE_TOKEN\n\ncapability:\n  consumes:\n    - import: eikon-datascope\n      location: ./shared/datascope-select.yaml\n    - import: eikon-tick-history\n      location: ./shared/tick-history.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: eikon-extraction-api\n      description:\
  \ \"Unified REST API for Refinitiv Eikon bulk data extraction.\"\n      resources:\n        - path: /v1/extractions\n          name: extractions\n          description: \"On-demand data extractions.\"\n          operations:\n            - method: POST\n              name: extract-data\n              description: \"Execute a DataScope Select on-demand extraction.\"\n              call: \"eikon-datascope.extract-raw\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/extractions/files\n          name: extracted-files\n          description: \"Extracted data files.\"\n          operations:\n            - method: GET\n              name: list-extracted-files\n              description: \"List files from completed extractions.\"\n              call: \"eikon-datascope.list-extracted-files\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/instruments/search\n\
  \          name: instrument-search\n          description: \"Instrument search.\"\n          operations:\n            - method: POST\n              name: search-instruments\n              description: \"Search DataScope for instruments.\"\n              call: \"eikon-datascope.search-instruments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/instrument-lists\n          name: instrument-lists\n          description: \"Instrument list management.\"\n          operations:\n            - method: GET\n              name: list-instrument-lists\n              description: \"List all instrument lists.\"\n              call: \"eikon-datascope.list-instrument-lists\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-instrument-list\n              description: \"Create a new instrument list.\"\n              call: \"\
  eikon-datascope.create-instrument-list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tick-history/extractions\n          name: tick-extractions\n          description: \"Tick history extractions.\"\n          operations:\n            - method: POST\n              name: extract-tick-history\n              description: \"Execute a tick history extraction.\"\n              call: \"eikon-tick-history.extract-tick-history\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tick-history/jobs\n          name: tick-jobs\n          description: \"Tick extraction job monitoring.\"\n          operations:\n            - method: GET\n              name: list-tick-jobs\n              description: \"List tick extraction jobs.\"\n              call: \"eikon-tick-history.list-jobs\"\n              outputParameters:\n                - type: object\n    \
  \              mapping: \"$.\"\n\n        - path: /v1/tick-history/jobs/{jobId}\n          name: tick-job-detail\n          description: \"Individual tick extraction job.\"\n          operations:\n            - method: GET\n              name: get-tick-job-status\n              description: \"Get tick extraction job status.\"\n              call: \"eikon-tick-history.get-job-status\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: cancel-tick-job\n              description: \"Cancel a running tick extraction job.\"\n              call: \"eikon-tick-history.cancel-job\"\n              with:\n                jobId: \"rest.jobId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9081\n      namespace: eikon-extraction-mcp\n      transport: http\n\
  \      description: \"MCP server for AI-assisted Refinitiv Eikon bulk data extraction.\"\n      tools:\n        - name: datascope-extract-data\n          description: \"Execute a DataScope Select on-demand extraction for pricing, corporate actions, or reference data.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"eikon-datascope.extract-raw\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: datascope-search-instruments\n          description: \"Search DataScope Select for financial instruments by RIC, ISIN, CUSIP, or ticker.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-datascope.search-instruments\"\n          with:\n            searchString: \"tools.searchString\"\n            identifierType: \"tools.identifierType\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ datascope-list-instrument-lists\n          description: \"List all saved instrument lists for DataScope extractions.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-datascope.list-instrument-lists\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: datascope-list-extracted-files\n          description: \"List files produced by completed DataScope extractions.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-datascope.list-extracted-files\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tick-history-extract\n          description: \"Execute an on-demand tick history extraction for time-and-sales or intraday bars.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"eikon-tick-history.extract-tick-history\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: tick-history-list-jobs\n          description: \"List all tick history extraction jobs and their current statuses.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-tick-history.list-jobs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tick-history-get-job-status\n          description: \"Get the current status and details of a specific tick history extraction job.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"eikon-tick-history.get-job-status\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: tick-history-cancel-job\n          description: \"Cancel a running tick history extraction job.\"\n          hints:\n            readOnly: false\n\
  \            destructive: true\n            idempotent: true\n          call: \"eikon-tick-history.cancel-job\"\n          with:\n            jobId: \"tools.jobId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/refinitiv-eikon/refs/heads/main/capabilities/data-extraction.yaml
tags:
- Refinitiv Eikon
- Data Extraction
- DataScope Select
- Tick History
- Corporate Actions
- Quantitative Analysis
tools:
- description: Execute a DataScope Select on-demand extraction for pricing, corporate actions, or reference data.
  hints:
    openWorld: false
    readOnly: false
  name: datascope-extract-data
- description: Search DataScope Select for financial instruments by RIC, ISIN, CUSIP, or ticker.
  hints:
    openWorld: false
    readOnly: true
  name: datascope-search-instruments
- description: List all saved instrument lists for DataScope extractions.
  hints:
    openWorld: false
    readOnly: true
  name: datascope-list-instrument-lists
- description: List files produced by completed DataScope extractions.
  hints:
    openWorld: false
    readOnly: true
  name: datascope-list-extracted-files
- description: Execute an on-demand tick history extraction for time-and-sales or intraday bars.
  hints:
    openWorld: false
    readOnly: false
  name: tick-history-extract
- description: List all tick history extraction jobs and their current statuses.
  hints:
    openWorld: false
    readOnly: true
  name: tick-history-list-jobs
- description: Get the current status and details of a specific tick history extraction job.
  hints:
    openWorld: false
    readOnly: true
  name: tick-history-get-job-status
- description: Cancel a running tick history extraction job.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: tick-history-cancel-job
---
