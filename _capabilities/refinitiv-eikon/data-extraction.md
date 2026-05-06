---
categories: []
consumed_apis: []
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
- extract data
- tick history extractions.
- tick history get job status
- search datascope for instruments.
- corporate actions
- datascope extract data
- on-demand data extractions.
- search datascope select for financial instruments by ric, isin, cusip, or ticker.
- datascope search instruments
- search instruments
- list extracted files
- market data
- analytics
- execute a tick history extraction.
- execute a datascope select on-demand extraction for pricing, corporate actions, or reference data.
- list files from completed extractions.
- execute an on-demand tick history extraction for time-and-sales or intraday bars.
- extract tick history
- datascope list extracted files
- list all tick history extraction jobs and their current statuses.
- cancel a running tick history extraction job.
- data extraction
- list files produced by completed datascope extractions.
- tick history list jobs
- tick history extract
- execute a datascope select on-demand extraction.
- individual tick extraction job.
- tick history cancel job
- list instrument lists
- get tick extraction job status.
- financial news
- tick history
- trading
- get tick job status
- create instrument list
- cancel tick job
- financial data
- real-time data
- quantitative analysis
- instrument search.
- datascope list instrument lists
- datascope select
- list tick extraction jobs.
- refinitiv eikon
- extracted data files.
- tick extraction job monitoring.
- list all instrument lists.
- list tick jobs
- list all saved instrument lists for datascope extractions.
- create a new instrument list.
- get the current status and details of a specific tick history extraction job.
- cancel a running tick extraction job.
- instrument list management.
slug: data-extraction
source_filename: data-extraction.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Refinitiv Eikon Data Extraction\n  description: Unified workflow capability for data engineers and quant analysts extracting bulk financial data from Refinitiv\n    Eikon via DataScope Select and Tick History REST APIs. Combines pricing, corporate actions, reference data, and tick-level\n    market data extraction workflows into a single interface.\n  tags:\n  - Refinitiv Eikon\n  - Data Extraction\n  - DataScope Select\n  - Tick History\n  - Corporate Actions\n  - Quantitative Analysis\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    DATASCOPE_TOKEN: DATASCOPE_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: eikon-datascope\n    baseUri: https://selectapi.datascope.refinitiv.com/RestApi/v1\n    description: DataScope Select REST API for batch data extraction.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Token {{DATASCOPE_TOKEN}}\n      placement:\
  \ header\n    resources:\n    - name: extractions\n      path: /Extractions\n      description: On-demand data extraction operations.\n      operations:\n      - name: extract-raw\n        method: POST\n        description: Execute an on-demand raw data extraction.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ExtractionRequest: '{{tools.extractionRequest}}'\n      - name: extract-with-notes\n        method: POST\n        description: Execute an on-demand extraction and return data with notes.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ExtractionRequest: '{{tools.extractionRequest}}'\n      - name: list-extracted-files\n        method:\
  \ GET\n        description: List files produced by completed extractions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-extracted-file\n        method: GET\n        description: Download the contents of a specific extracted file.\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the extracted file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instrument-search\n      path: /Search/InstrumentSearch\n      description: Instrument search and validation.\n      operations:\n      - name: search-instruments\n        method: POST\n        description: Search for instruments by identifier or name.\n        inputParameters: []\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            SearchString: '{{tools.searchString}}'\n            IdentifierType: '{{tools.identifierType}}'\n    - name: instrument-lists\n      path: /InstrumentLists\n      description: Management of instrument lists for extractions.\n      operations:\n      - name: list-instrument-lists\n        method: GET\n        description: Retrieve all instrument lists.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-instrument-list\n        method: POST\n        description: Create a new instrument list.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n    \
  \        Name: '{{tools.name}}'\n            InstrumentIdentifiers: '{{tools.instruments}}'\n    - name: schedules\n      path: /Schedules\n      description: Extraction schedule management.\n      operations:\n      - name: list-schedules\n        method: GET\n        description: List all extraction schedules.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-schedule\n        method: POST\n        description: Create a new extraction schedule.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            ListId: '{{tools.listId}}'\n            ReportTemplateId: '{{tools.reportTemplateId}}'\n  - type: http\n    namespace: eikon-tick-history\n    baseUri: https://selectapi.datascope.refinitiv.com/RestApi/v1\n\
  \    description: LSEG Tick History REST API for historical tick data.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Token {{DATASCOPE_TOKEN}}\n      placement: header\n    resources:\n    - name: tick-extractions\n      path: /Extractions/ExtractRaw\n      description: On-demand tick history extraction.\n      operations:\n      - name: extract-tick-history\n        method: POST\n        description: Execute an on-demand tick history extraction.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            ExtractionRequest: '{{tools.extractionRequest}}'\n    - name: tick-files\n      path: /Extractions/ExtractedFiles\n      description: Extracted tick data file management.\n      operations:\n      - name: list-extracted-files\n        method: GET\n        description: List files from completed\
  \ tick history extractions.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: download-extracted-file\n        method: GET\n        description: Download a tick history data file.\n        inputParameters:\n        - name: fileId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the extracted file.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /Jobs/Jobs\n      description: Extraction job monitoring.\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List all extraction jobs and their statuses.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ get-job-status\n        method: GET\n        description: Get the status of a specific extraction job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the job.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-job\n        method: DELETE\n        description: Cancel a running extraction job.\n        inputParameters:\n        - name: jobId\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the job to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: eikon-extraction-api\n    description: Unified REST API for Refinitiv Eikon bulk data extraction.\n    resources:\n    -\
  \ path: /v1/extractions\n      name: extractions\n      description: On-demand data extractions.\n      operations:\n      - method: POST\n        name: extract-data\n        description: Execute a DataScope Select on-demand extraction.\n        call: eikon-datascope.extract-raw\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/extractions/files\n      name: extracted-files\n      description: Extracted data files.\n      operations:\n      - method: GET\n        name: list-extracted-files\n        description: List files from completed extractions.\n        call: eikon-datascope.list-extracted-files\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instruments/search\n      name: instrument-search\n      description: Instrument search.\n      operations:\n      - method: POST\n        name: search-instruments\n        description: Search DataScope for instruments.\n        call: eikon-datascope.search-instruments\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instrument-lists\n      name: instrument-lists\n      description: Instrument list management.\n      operations:\n      - method: GET\n        name: list-instrument-lists\n        description: List all instrument lists.\n        call: eikon-datascope.list-instrument-lists\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-instrument-list\n        description: Create a new instrument list.\n        call: eikon-datascope.create-instrument-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tick-history/extractions\n      name: tick-extractions\n      description: Tick history extractions.\n      operations:\n      - method: POST\n        name: extract-tick-history\n        description: Execute a tick history extraction.\n        call: eikon-tick-history.extract-tick-history\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/tick-history/jobs\n      name: tick-jobs\n      description: Tick extraction job monitoring.\n      operations:\n      - method: GET\n        name: list-tick-jobs\n        description: List tick extraction jobs.\n        call: eikon-tick-history.list-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tick-history/jobs/{jobId}\n      name: tick-job-detail\n      description: Individual tick extraction job.\n      operations:\n      - method: GET\n        name: get-tick-job-status\n        description: Get tick extraction job status.\n        call: eikon-tick-history.get-job-status\n        with:\n          jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-tick-job\n        description: Cancel a running tick extraction job.\n        call: eikon-tick-history.cancel-job\n        with:\n         \
  \ jobId: rest.jobId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9081\n    namespace: eikon-extraction-mcp\n    transport: http\n    description: MCP server for AI-assisted Refinitiv Eikon bulk data extraction.\n    tools:\n    - name: datascope-extract-data\n      description: Execute a DataScope Select on-demand extraction for pricing, corporate actions, or reference data.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: eikon-datascope.extract-raw\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datascope-search-instruments\n      description: Search DataScope Select for financial instruments by RIC, ISIN, CUSIP, or ticker.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-datascope.search-instruments\n      with:\n        searchString: tools.searchString\n        identifierType: tools.identifierType\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: datascope-list-instrument-lists\n      description: List all saved instrument lists for DataScope extractions.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-datascope.list-instrument-lists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datascope-list-extracted-files\n      description: List files produced by completed DataScope extractions.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-datascope.list-extracted-files\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tick-history-extract\n      description: Execute an on-demand tick history extraction for time-and-sales or intraday bars.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: eikon-tick-history.extract-tick-history\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tick-history-list-jobs\n \
  \     description: List all tick history extraction jobs and their current statuses.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-tick-history.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tick-history-get-job-status\n      description: Get the current status and details of a specific tick history extraction job.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: eikon-tick-history.get-job-status\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: tick-history-cancel-job\n      description: Cancel a running tick history extraction job.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: eikon-tick-history.cancel-job\n      with:\n        jobId: tools.jobId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
