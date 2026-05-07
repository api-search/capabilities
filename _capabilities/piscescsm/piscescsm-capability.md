---
categories: []
consumed_apis: []
description: The piscesCSM API allows users to integrate piscesCSM drug-pair cancer sensitivity prediction into research pipelines. Submit a pair of small molecules as SMILES strings, then poll the prediction status using the returned job identifier. Results include predictions across multiple cancer types and molecular descriptors for both drugs.
layout: capability
name: piscesCSM API
operations:
- description: Submit a drug-pair prediction job
  method: POST
  name: submitprediction
  path: /predict
- description: Retrieve prediction results
  method: GET
  name: getprediction
  path: /predict
personas: []
provider_name: piscesCSM
provider_slug: piscescsm
search_terms:
- retrieve prediction results
- bioinformatics
- getprediction
- submitprediction
- cancer
- piscescsm
- api
- submit a drug-pair prediction job
- drug discovery
slug: piscescsm-capability
source_filename: piscescsm-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: piscesCSM API\n  description: The piscesCSM API allows users to integrate piscesCSM drug-pair cancer sensitivity prediction into research\n    pipelines. Submit a pair of small molecules as SMILES strings, then poll the prediction status using the returned job\n    identifier. Results include predictions across multiple cancer types and molecular descriptors for both drugs.\n  tags:\n  - Piscescsm\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: piscescsm\n    baseUri: https://biosig.lab.uq.edu.au/piscescsm/api\n    description: piscesCSM API HTTP API.\n    resources:\n    - name: predict\n      path: /predict\n      operations:\n      - name: submitprediction\n        method: POST\n        description: Submit a drug-pair prediction job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \  - name: getprediction\n        method: GET\n        description: Retrieve prediction results\n        inputParameters:\n        - name: job_id\n          in: query\n          type: string\n          required: true\n          description: Job identifier returned by submitPrediction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: piscescsm-rest\n    description: REST adapter for piscesCSM API.\n    resources:\n    - path: /predict\n      name: submitprediction\n      operations:\n      - method: POST\n        name: submitprediction\n        description: Submit a drug-pair prediction job\n        call: piscescsm.submitprediction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /predict\n      name: getprediction\n      operations:\n      - method: GET\n        name: getprediction\n        description: Retrieve\
  \ prediction results\n        call: piscescsm.getprediction\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: piscescsm-mcp\n    transport: http\n    description: MCP adapter for piscesCSM API for AI agent use.\n    tools:\n    - name: submitprediction\n      description: Submit a drug-pair prediction job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: piscescsm.submitprediction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getprediction\n      description: Retrieve prediction results\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: piscescsm.getprediction\n      with:\n        job_id: tools.job_id\n      inputParameters:\n      - name: job_id\n        type: string\n        description: Job identifier returned by submitPrediction.\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/piscescsm/refs/heads/main/capabilities/piscescsm-capability.yaml
tags:
- Piscescsm
- API
tools:
- description: Submit a drug-pair prediction job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: submitprediction
- description: Retrieve prediction results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprediction
---
