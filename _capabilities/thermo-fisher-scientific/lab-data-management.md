---
categories: []
consumed_apis: []
description: Workflow capability for laboratory data management combining SampleManager LIMS and NanoDrop Ultra spectrophotometer APIs. Covers sample lifecycle, result entry, instrument measurements, and LIMS integration for life science laboratories.
layout: capability
name: Thermo Fisher Scientific Lab Data Management
operations:
- description: List laboratory samples from SampleManager LIMS.
  method: GET
  name: list-samples
  path: /v1/samples
- description: Get details for a specific laboratory sample.
  method: GET
  name: get-sample
  path: /v1/samples/{sampleId}
- description: Get test results for a specific sample.
  method: GET
  name: get-sample-results
  path: /v1/samples/{sampleId}/results
- description: Submit test results to SampleManager LIMS.
  method: POST
  name: submit-results
  path: /v1/results
- description: Browse SampleManager entity records.
  method: GET
  name: browse-entity
  path: /v1/entities/{entity}
- description: Trigger a SampleManager workflow.
  method: POST
  name: trigger-workflow
  path: /v1/workflows/{workflowName}/trigger
- description: Check NanoDrop Ultra instrument readiness.
  method: GET
  name: get-instrument-status
  path: /v1/instrument/status
- description: List stored NanoDrop measurements.
  method: GET
  name: list-measurements
  path: /v1/spectrophotometry/measurements
- description: Perform a NanoDrop measurement.
  method: POST
  name: perform-measurement
  path: /v1/spectrophotometry/measurements
- description: Get full measurement data including absorbance spectrum.
  method: GET
  name: get-measurement
  path: /v1/spectrophotometry/measurements/{measurementId}
- description: Export NanoDrop data for LIMS integration.
  method: POST
  name: export-measurements
  path: /v1/spectrophotometry/export
personas: []
provider_name: Thermo Fisher Scientific
provider_slug: thermo-fisher-scientific
search_terms:
- spectrophotometry
- get sample results
- individual sample data.
- check the operational status and readiness of the nanodrop ultra spectrophotometer.
- nanodrop list measurements
- get instrument status
- sample management
- get sample
- list laboratory samples from samplemanager lims.
- browse samplemanager entity records.
- list stored nanodrop measurements.
- perform a nanodrop measurement.
- list laboratory samples from samplemanager lims with optional status and date filtering.
- trigger a named automated workflow in samplemanager lims.
- nanodrop instrument status.
- list samples
- browse entity
- nanodrop spectrophotometric measurements.
- get full nanodrop measurement data including complete uv-vis absorbance spectrum.
- get test results for a specific sample.
- list available measurement methods on the nanodrop ultra (dna-50, rna-40, protein a280, etc.).
- laboratory sample management.
- lims submit results
- list measurements
- get full measurement data including absorbance spectrum.
- test results for a sample.
- lims get sample results
- perform measurement
- biosciences
- get details for a specific laboratory sample by identity or barcode.
- get measurement
- get details for a specific laboratory sample.
- lims get sample
- lims
- get all analytical test results for a specific laboratory sample.
- submit analytical test results for samples in samplemanager lims.
- laboratory
- lims list samples
- nanodrop perform measurement
- check nanodrop ultra instrument readiness.
- export nanodrop data for lims integration.
- nanodrop get measurement
- nanodrop get methods
- scientific instruments
- submit test results.
- lims trigger workflow
- perform a uv-vis spectrophotometric measurement on loaded sample (dna, rna, protein quantification).
- life sciences
- fortune 500
- export nanodrop measurement data.
- export measurements
- trigger workflow
- diagnostics
- individual nanodrop measurement with spectrum.
- browse any samplemanager lims entity type (sample, test, result, customer, batch_header, analysis).
- nanodrop get status
- lims browse entity
- submit results
- nanodrop export data
- list stored nanodrop ultra measurements with concentration, purity ratios, and spectra.
- trigger laboratory workflows.
- browse samplemanager entities.
- trigger a samplemanager workflow.
- submit test results to samplemanager lims.
- export nanodrop ultra measurements in json, csv, or xml format for lims or eln integration.
- automation
slug: lab-data-management
source_filename: lab-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Thermo Fisher Scientific Lab Data Management\n  description: Workflow capability for laboratory data management combining SampleManager LIMS and NanoDrop Ultra spectrophotometer\n    APIs. Covers sample lifecycle, result entry, instrument measurements, and LIMS integration for life science laboratories.\n  tags:\n  - Life Sciences\n  - Laboratory\n  - LIMS\n  - Spectrophotometry\n  - Sample Management\n  - Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SAMPLEMANAGER_TOKEN: SAMPLEMANAGER_TOKEN\n    NANODROP_HOST: NANODROP_HOST\ncapability:\n  consumes:\n  - type: http\n    namespace: samplemanager\n    baseUri: https://{server}:56105/smpwcfrestvgsm\n    description: Thermo Scientific SampleManager LIMS REST API.\n    authentication:\n      type: bearer\n      token: '{{SAMPLEMANAGER_TOKEN}}'\n    resources:\n    - name: samples\n      path: /mobile/samples\n      description: Laboratory\
  \ sample records.\n      operations:\n      - name: get-samples\n        method: GET\n        description: Retrieve laboratory samples with filtering by status and date.\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Sample status filter (A, C, X, L).\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: From date filter (YYYY-MM-DD).\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description: To date filter (YYYY-MM-DD).\n        - name: pagesize\n          in: query\n          type: integer\n          required: false\n          description: Records per page.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: sample-by-id\n      path: /mobile/samples/{sampleId}\n      description: Retrieve a specific sample by identity.\n      operations:\n      - name: get-sample-by-id\n        method: GET\n        description: Get details for a specific laboratory sample.\n        inputParameters:\n        - name: sampleId\n          in: path\n          type: string\n          required: true\n          description: Sample identity or barcode.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sample-results\n      path: /mobile/samples/{sampleId}/results\n      description: Test results for a sample.\n      operations:\n      - name: get-sample-results\n        method: GET\n        description: Get all test results for a specific sample.\n        inputParameters:\n        - name: sampleId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Sample identity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-entry\n      path: /mobile/results\n      description: Submit test results.\n      operations:\n      - name: submit-results\n        method: POST\n        description: Submit test results for samples in SampleManager.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            sample_id: '{{tools.sample_id}}'\n            results: '{{tools.results}}'\n    - name: entity-browse\n      path: /mobile/browses/{entity}\n      description: Browse SampleManager entities.\n      operations:\n      - name: browse-entity\n        method: GET\n        description: Browse records for any SampleManager entity type.\n        inputParameters:\n        - name: entity\n       \
  \   in: path\n          type: string\n          required: true\n          description: Entity name (SAMPLE, TEST, RESULT, CUSTOMER, etc.).\n        - name: criteria\n          in: query\n          type: string\n          required: false\n          description: Filter criteria.\n        - name: pagesize\n          in: query\n          type: integer\n          required: false\n          description: Records per page.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflow-trigger\n      path: /mobile/workflows/{workflowName}/trigger\n      description: Trigger SampleManager workflows.\n      operations:\n      - name: trigger-workflow\n        method: POST\n        description: Trigger a named workflow in SampleManager.\n        inputParameters:\n        - name: workflowName\n\
  \          in: path\n          type: string\n          required: true\n          description: Workflow name to trigger.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data: {}\n  - type: http\n    namespace: nanodrop\n    baseUri: http://{{NANODROP_HOST}}:8080\n    description: NanoDrop Ultra instrument local REST API.\n    resources:\n    - name: instrument-status\n      path: /api/status\n      description: Instrument status and metadata.\n      operations:\n      - name: get-instrument-status\n        method: GET\n        description: Get current status and readiness of the NanoDrop Ultra instrument.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measure\n      path: /api/measure\n      description: Perform a sample measurement.\n      operations:\n      - name: perform-measurement\n\
  \        method: POST\n        description: Initiate a sample measurement using the specified method.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            method: '{{tools.method}}'\n            sample_id: '{{tools.sample_id}}'\n            sample_name: '{{tools.sample_name}}'\n            operator: '{{tools.operator}}'\n    - name: measurements\n      path: /api/measurements\n      description: Stored measurement records.\n      operations:\n      - name: get-measurements\n        method: GET\n        description: Retrieve stored measurements with date and method filtering.\n        inputParameters:\n        - name: from_date\n          in: query\n          type: string\n          required: false\n          description: From date filter.\n        - name: to_date\n          in: query\n          type: string\n          required: false\n          description:\
  \ To date filter.\n        - name: method\n          in: query\n          type: string\n          required: false\n          description: Method filter.\n        - name: sample_id\n          in: query\n          type: string\n          required: false\n          description: Sample ID filter.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: measurement-by-id\n      path: /api/measurements/{measurementId}\n      description: Retrieve a specific measurement with full spectrum data.\n      operations:\n      - name: get-measurement-by-id\n        method: GET\n        description: Get full measurement data including spectrum for a specific measurement ID.\n        inputParameters:\n        - name: measurementId\n          in: path\n          type: string\n\
  \          required: true\n          description: Unique measurement identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: methods\n      path: /api/methods\n      description: Available measurement methods.\n      operations:\n      - name: get-methods\n        method: GET\n        description: List available measurement methods configured on the instrument.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export\n      path: /api/export\n      description: Export measurement data.\n      operations:\n      - name: export-measurements\n        method: POST\n        description: Export measurements in CSV, JSON, or XML format for LIMS integration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type:\
  \ json\n          data:\n            format: '{{tools.format}}'\n            from_date: '{{tools.from_date}}'\n            to_date: '{{tools.to_date}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: thermo-fisher-lab-api\n    description: Unified REST API for Thermo Fisher Scientific lab data management workflows.\n    resources:\n    - path: /v1/samples\n      name: samples\n      description: Laboratory sample management.\n      operations:\n      - method: GET\n        name: list-samples\n        description: List laboratory samples from SampleManager LIMS.\n        call: samplemanager.get-samples\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/samples/{sampleId}\n      name: sample\n      description: Individual sample data.\n      operations:\n      - method: GET\n        name: get-sample\n        description: Get details for a specific laboratory sample.\n        call: samplemanager.get-sample-by-id\n        with:\n        \
  \  sampleId: rest.sampleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/samples/{sampleId}/results\n      name: sample-results\n      description: Test results for a sample.\n      operations:\n      - method: GET\n        name: get-sample-results\n        description: Get test results for a specific sample.\n        call: samplemanager.get-sample-results\n        with:\n          sampleId: rest.sampleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/results\n      name: results\n      description: Submit test results.\n      operations:\n      - method: POST\n        name: submit-results\n        description: Submit test results to SampleManager LIMS.\n        call: samplemanager.submit-results\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/entities/{entity}\n      name: entities\n      description: Browse SampleManager entities.\n      operations:\n  \
  \    - method: GET\n        name: browse-entity\n        description: Browse SampleManager entity records.\n        call: samplemanager.browse-entity\n        with:\n          entity: rest.entity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workflows/{workflowName}/trigger\n      name: workflow-trigger\n      description: Trigger laboratory workflows.\n      operations:\n      - method: POST\n        name: trigger-workflow\n        description: Trigger a SampleManager workflow.\n        call: samplemanager.trigger-workflow\n        with:\n          workflowName: rest.workflowName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instrument/status\n      name: instrument-status\n      description: NanoDrop instrument status.\n      operations:\n      - method: GET\n        name: get-instrument-status\n        description: Check NanoDrop Ultra instrument readiness.\n        call: nanodrop.get-instrument-status\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spectrophotometry/measurements\n      name: spectrophotometry-measurements\n      description: NanoDrop spectrophotometric measurements.\n      operations:\n      - method: GET\n        name: list-measurements\n        description: List stored NanoDrop measurements.\n        call: nanodrop.get-measurements\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: perform-measurement\n        description: Perform a NanoDrop measurement.\n        call: nanodrop.perform-measurement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spectrophotometry/measurements/{measurementId}\n      name: spectrophotometry-measurement\n      description: Individual NanoDrop measurement with spectrum.\n      operations:\n      - method: GET\n        name: get-measurement\n        description: Get full measurement data including\
  \ absorbance spectrum.\n        call: nanodrop.get-measurement-by-id\n        with:\n          measurementId: rest.measurementId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spectrophotometry/export\n      name: spectrophotometry-export\n      description: Export NanoDrop measurement data.\n      operations:\n      - method: POST\n        name: export-measurements\n        description: Export NanoDrop data for LIMS integration.\n        call: nanodrop.export-measurements\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: thermo-fisher-lab-mcp\n    transport: http\n    description: MCP server for AI-assisted laboratory data management using Thermo Fisher Scientific APIs.\n    tools:\n    - name: lims-list-samples\n      description: List laboratory samples from SampleManager LIMS with optional status and date filtering.\n      hints:\n        readOnly: true\n        idempotent:\
  \ true\n      call: samplemanager.get-samples\n      outputParameters:\n      - type: array\n        mapping: $.samples\n    - name: lims-get-sample\n      description: Get details for a specific laboratory sample by identity or barcode.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: samplemanager.get-sample-by-id\n      with:\n        sampleId: tools.sampleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lims-get-sample-results\n      description: Get all analytical test results for a specific laboratory sample.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: samplemanager.get-sample-results\n      with:\n        sampleId: tools.sampleId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lims-submit-results\n      description: Submit analytical test results for samples in SampleManager LIMS.\n      hints:\n        readOnly: false\n      call: samplemanager.submit-results\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lims-browse-entity\n      description: Browse any SampleManager LIMS entity type (SAMPLE, TEST, RESULT, CUSTOMER, BATCH_HEADER, ANALYSIS).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: samplemanager.browse-entity\n      with:\n        entity: tools.entity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lims-trigger-workflow\n      description: Trigger a named automated workflow in SampleManager LIMS.\n      hints:\n        readOnly: false\n      call: samplemanager.trigger-workflow\n      with:\n        workflowName: tools.workflowName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-get-status\n      description: Check the operational status and readiness of the NanoDrop Ultra spectrophotometer.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nanodrop.get-instrument-status\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-perform-measurement\n      description: Perform a UV-Vis spectrophotometric measurement on loaded sample (DNA, RNA, protein quantification).\n      hints:\n        readOnly: false\n      call: nanodrop.perform-measurement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-list-measurements\n      description: List stored NanoDrop Ultra measurements with concentration, purity ratios, and spectra.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nanodrop.get-measurements\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-get-measurement\n      description: Get full NanoDrop measurement data including complete UV-Vis absorbance spectrum.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nanodrop.get-measurement-by-id\n      with:\n        measurementId: tools.measurementId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-get-methods\n      description: List available measurement methods on the NanoDrop Ultra (DNA-50, RNA-40, Protein A280, etc.).\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nanodrop.get-methods\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nanodrop-export-data\n      description: Export NanoDrop Ultra measurements in JSON, CSV, or XML format for LIMS or ELN integration.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: nanodrop.export-measurements\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/thermo-fisher-scientific/refs/heads/main/capabilities/lab-data-management.yaml
tags:
- Life Sciences
- Laboratory
- LIMS
- Spectrophotometry
- Sample Management
- Automation
tools:
- description: List laboratory samples from SampleManager LIMS with optional status and date filtering.
  hints:
    idempotent: true
    readOnly: true
  name: lims-list-samples
- description: Get details for a specific laboratory sample by identity or barcode.
  hints:
    idempotent: true
    readOnly: true
  name: lims-get-sample
- description: Get all analytical test results for a specific laboratory sample.
  hints:
    idempotent: true
    readOnly: true
  name: lims-get-sample-results
- description: Submit analytical test results for samples in SampleManager LIMS.
  hints:
    readOnly: false
  name: lims-submit-results
- description: Browse any SampleManager LIMS entity type (SAMPLE, TEST, RESULT, CUSTOMER, BATCH_HEADER, ANALYSIS).
  hints:
    idempotent: true
    readOnly: true
  name: lims-browse-entity
- description: Trigger a named automated workflow in SampleManager LIMS.
  hints:
    readOnly: false
  name: lims-trigger-workflow
- description: Check the operational status and readiness of the NanoDrop Ultra spectrophotometer.
  hints:
    idempotent: true
    readOnly: true
  name: nanodrop-get-status
- description: Perform a UV-Vis spectrophotometric measurement on loaded sample (DNA, RNA, protein quantification).
  hints:
    readOnly: false
  name: nanodrop-perform-measurement
- description: List stored NanoDrop Ultra measurements with concentration, purity ratios, and spectra.
  hints:
    idempotent: true
    readOnly: true
  name: nanodrop-list-measurements
- description: Get full NanoDrop measurement data including complete UV-Vis absorbance spectrum.
  hints:
    idempotent: true
    readOnly: true
  name: nanodrop-get-measurement
- description: List available measurement methods on the NanoDrop Ultra (DNA-50, RNA-40, Protein A280, etc.).
  hints:
    idempotent: true
    readOnly: true
  name: nanodrop-get-methods
- description: Export NanoDrop Ultra measurements in JSON, CSV, or XML format for LIMS or ELN integration.
  hints:
    idempotent: true
    readOnly: true
  name: nanodrop-export-data
---
