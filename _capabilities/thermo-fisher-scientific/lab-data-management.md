---
categories: []
consumed_apis:
- samplemanager
- nanodrop
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
- individual nanodrop measurement with spectrum.
- biosciences
- laboratory
- test results for a sample.
- list stored nanodrop measurements.
- check the operational status and readiness of the nanodrop ultra spectrophotometer.
- get full measurement data including absorbance spectrum.
- nanodrop get methods
- export nanodrop data for lims integration.
- lims get sample
- sample management
- lims submit results
- export nanodrop ultra measurements in json, csv, or xml format for lims or eln integration.
- submit results
- trigger a samplemanager workflow.
- nanodrop instrument status.
- browse entity
- nanodrop list measurements
- nanodrop export data
- check nanodrop ultra instrument readiness.
- nanodrop spectrophotometric measurements.
- trigger laboratory workflows.
- browse samplemanager entity records.
- get all analytical test results for a specific laboratory sample.
- trigger a named automated workflow in samplemanager lims.
- nanodrop perform measurement
- get details for a specific laboratory sample.
- scientific instruments
- nanodrop get status
- list laboratory samples from samplemanager lims with optional status and date filtering.
- perform measurement
- get measurement
- get sample results
- submit test results to samplemanager lims.
- fortune 500
- life sciences
- nanodrop get measurement
- perform a nanodrop measurement.
- get test results for a specific sample.
- submit test results.
- get sample
- spectrophotometry
- list laboratory samples from samplemanager lims.
- export nanodrop measurement data.
- lims list samples
- individual sample data.
- get instrument status
- export measurements
- lims
- list measurements
- laboratory sample management.
- perform a uv-vis spectrophotometric measurement on loaded sample (dna, rna, protein quantification).
- list stored nanodrop ultra measurements with concentration, purity ratios, and spectra.
- lims get sample results
- browse samplemanager entities.
- browse any samplemanager lims entity type (sample, test, result, customer, batch_header, analysis).
- list available measurement methods on the nanodrop ultra (dna-50, rna-40, protein a280, etc.).
- get full nanodrop measurement data including complete uv-vis absorbance spectrum.
- get details for a specific laboratory sample by identity or barcode.
- list samples
- automation
- diagnostics
- trigger workflow
- lims trigger workflow
- lims browse entity
- submit analytical test results for samples in samplemanager lims.
slug: lab-data-management
source_filename: lab-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Thermo Fisher Scientific Lab Data Management\"\n  description: \"Workflow capability for laboratory data management combining SampleManager LIMS and NanoDrop Ultra spectrophotometer APIs. Covers sample lifecycle, result entry, instrument measurements, and LIMS integration for life science laboratories.\"\n  tags:\n    - Life Sciences\n    - Laboratory\n    - LIMS\n    - Spectrophotometry\n    - Sample Management\n    - Automation\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAMPLEMANAGER_TOKEN: SAMPLEMANAGER_TOKEN\n      NANODROP_HOST: NANODROP_HOST\n\ncapability:\n  consumes:\n    - import: samplemanager\n      location: ./shared/samplemanager-lims.yaml\n    - import: nanodrop\n      location: ./shared/nanodrop-ultra.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: thermo-fisher-lab-api\n      description: \"Unified REST API for Thermo Fisher Scientific\
  \ lab data management workflows.\"\n      resources:\n        - path: /v1/samples\n          name: samples\n          description: \"Laboratory sample management.\"\n          operations:\n            - method: GET\n              name: list-samples\n              description: \"List laboratory samples from SampleManager LIMS.\"\n              call: \"samplemanager.get-samples\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/samples/{sampleId}\n          name: sample\n          description: \"Individual sample data.\"\n          operations:\n            - method: GET\n              name: get-sample\n              description: \"Get details for a specific laboratory sample.\"\n              call: \"samplemanager.get-sample-by-id\"\n              with:\n                sampleId: \"rest.sampleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path:\
  \ /v1/samples/{sampleId}/results\n          name: sample-results\n          description: \"Test results for a sample.\"\n          operations:\n            - method: GET\n              name: get-sample-results\n              description: \"Get test results for a specific sample.\"\n              call: \"samplemanager.get-sample-results\"\n              with:\n                sampleId: \"rest.sampleId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/results\n          name: results\n          description: \"Submit test results.\"\n          operations:\n            - method: POST\n              name: submit-results\n              description: \"Submit test results to SampleManager LIMS.\"\n              call: \"samplemanager.submit-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/entities/{entity}\n          name: entities\n    \
  \      description: \"Browse SampleManager entities.\"\n          operations:\n            - method: GET\n              name: browse-entity\n              description: \"Browse SampleManager entity records.\"\n              call: \"samplemanager.browse-entity\"\n              with:\n                entity: \"rest.entity\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/workflows/{workflowName}/trigger\n          name: workflow-trigger\n          description: \"Trigger laboratory workflows.\"\n          operations:\n            - method: POST\n              name: trigger-workflow\n              description: \"Trigger a SampleManager workflow.\"\n              call: \"samplemanager.trigger-workflow\"\n              with:\n                workflowName: \"rest.workflowName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/instrument/status\n\
  \          name: instrument-status\n          description: \"NanoDrop instrument status.\"\n          operations:\n            - method: GET\n              name: get-instrument-status\n              description: \"Check NanoDrop Ultra instrument readiness.\"\n              call: \"nanodrop.get-instrument-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/spectrophotometry/measurements\n          name: spectrophotometry-measurements\n          description: \"NanoDrop spectrophotometric measurements.\"\n          operations:\n            - method: GET\n              name: list-measurements\n              description: \"List stored NanoDrop measurements.\"\n              call: \"nanodrop.get-measurements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: perform-measurement\n              description: \"Perform\
  \ a NanoDrop measurement.\"\n              call: \"nanodrop.perform-measurement\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/spectrophotometry/measurements/{measurementId}\n          name: spectrophotometry-measurement\n          description: \"Individual NanoDrop measurement with spectrum.\"\n          operations:\n            - method: GET\n              name: get-measurement\n              description: \"Get full measurement data including absorbance spectrum.\"\n              call: \"nanodrop.get-measurement-by-id\"\n              with:\n                measurementId: \"rest.measurementId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/spectrophotometry/export\n          name: spectrophotometry-export\n          description: \"Export NanoDrop measurement data.\"\n          operations:\n            - method: POST\n             \
  \ name: export-measurements\n              description: \"Export NanoDrop data for LIMS integration.\"\n              call: \"nanodrop.export-measurements\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: thermo-fisher-lab-mcp\n      transport: http\n      description: \"MCP server for AI-assisted laboratory data management using Thermo Fisher Scientific APIs.\"\n      tools:\n        - name: lims-list-samples\n          description: \"List laboratory samples from SampleManager LIMS with optional status and date filtering.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"samplemanager.get-samples\"\n          outputParameters:\n            - type: array\n              mapping: \"$.samples\"\n\n        - name: lims-get-sample\n          description: \"Get details for a specific laboratory sample by identity or barcode.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"samplemanager.get-sample-by-id\"\n          with:\n            sampleId: \"tools.sampleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lims-get-sample-results\n          description: \"Get all analytical test results for a specific laboratory sample.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"samplemanager.get-sample-results\"\n          with:\n            sampleId: \"tools.sampleId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lims-submit-results\n          description: \"Submit analytical test results for samples in SampleManager LIMS.\"\n          hints:\n            readOnly: false\n          call: \"samplemanager.submit-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n       \
  \ - name: lims-browse-entity\n          description: \"Browse any SampleManager LIMS entity type (SAMPLE, TEST, RESULT, CUSTOMER, BATCH_HEADER, ANALYSIS).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"samplemanager.browse-entity\"\n          with:\n            entity: \"tools.entity\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: lims-trigger-workflow\n          description: \"Trigger a named automated workflow in SampleManager LIMS.\"\n          hints:\n            readOnly: false\n          call: \"samplemanager.trigger-workflow\"\n          with:\n            workflowName: \"tools.workflowName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-get-status\n          description: \"Check the operational status and readiness of the NanoDrop Ultra spectrophotometer.\"\n          hints:\n            readOnly: true\n\
  \            idempotent: true\n          call: \"nanodrop.get-instrument-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-perform-measurement\n          description: \"Perform a UV-Vis spectrophotometric measurement on loaded sample (DNA, RNA, protein quantification).\"\n          hints:\n            readOnly: false\n          call: \"nanodrop.perform-measurement\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-list-measurements\n          description: \"List stored NanoDrop Ultra measurements with concentration, purity ratios, and spectra.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nanodrop.get-measurements\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-get-measurement\n          description: \"Get full NanoDrop measurement\
  \ data including complete UV-Vis absorbance spectrum.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nanodrop.get-measurement-by-id\"\n          with:\n            measurementId: \"tools.measurementId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-get-methods\n          description: \"List available measurement methods on the NanoDrop Ultra (DNA-50, RNA-40, Protein A280, etc.).\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nanodrop.get-methods\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: nanodrop-export-data\n          description: \"Export NanoDrop Ultra measurements in JSON, CSV, or XML format for LIMS or ELN integration.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"nanodrop.export-measurements\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
