---
categories: []
consumed_apis: []
description: The Assured Workloads API enables programmatic management of compliance- controlled workload environments on Google Cloud. It supports creating workloads with specific compliance regimes, monitoring violations, and managing organizational policies for regulatory compliance.
layout: capability
name: Google Cloud Assured Workloads API
operations:
- description: Google Cloud Assured Workloads List workloads
  method: GET
  name: listworkloads
  path: /organizations/{organizationId}/locations/{location}/workloads
- description: Google Cloud Assured Workloads Create a workload
  method: POST
  name: createworkload
  path: /organizations/{organizationId}/locations/{location}/workloads
- description: Google Cloud Assured Workloads Get a workload
  method: GET
  name: getworkload
  path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}
- description: Google Cloud Assured Workloads Update a workload
  method: PATCH
  name: updateworkload
  path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}
- description: Google Cloud Assured Workloads Delete a workload
  method: DELETE
  name: deleteworkload
  path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}
- description: Google Cloud Assured Workloads List violations
  method: GET
  name: listviolations
  path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}/violations
personas: []
provider_name: Google Cloud Assured Workloads
provider_slug: google-cloud-assured-workloads
search_terms:
- listviolations
- governance
- regulatory
- google cloud assured workloads update a workload
- updateworkload
- assured
- getworkload
- google cloud assured workloads create a workload
- api
- google cloud assured workloads get a workload
- google cloud assured workloads delete a workload
- createworkload
- compliance
- hipaa
- fedramp
- google
- cloud
- deleteworkload
- google cloud assured workloads list workloads
- listworkloads
- workloads
- google cloud assured workloads list violations
- data residency
slug: google-cloud-assured-workloads-capability
source_filename: google-cloud-assured-workloads-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Assured Workloads API\n  description: The Assured Workloads API enables programmatic management of compliance- controlled workload environments on\n    Google Cloud. It supports creating workloads with specific compliance regimes, monitoring violations, and managing organizational\n    policies for regulatory compliance.\n  tags:\n  - Google\n  - Cloud\n  - Assured\n  - Workloads\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-assured-workloads\n    baseUri: https://assuredworkloads.googleapis.com/v1\n    description: Google Cloud Assured Workloads API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_ASSURED_WORKLOADS_TOKEN}}'\n    resources:\n    - name: organizations-organizationid-locations-location-\n      path: /organizations/{organizationId}/locations/{location}/workloads\n      operations:\n      - name:\
  \ listworkloads\n        method: GET\n        description: Google Cloud Assured Workloads List workloads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkload\n        method: POST\n        description: Google Cloud Assured Workloads Create a workload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-locations-location-\n      path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}\n      operations:\n      - name: getworkload\n        method: GET\n        description: Google Cloud Assured Workloads Get a workload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkload\n        method: PATCH\n        description: Google Cloud Assured Workloads\
  \ Update a workload\n        inputParameters:\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkload\n        method: DELETE\n        description: Google Cloud Assured Workloads Delete a workload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-organizationid-locations-location-\n      path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}/violations\n      operations:\n      - name: listviolations\n        method: GET\n        description: Google Cloud Assured Workloads List violations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-assured-workloads-rest\n\
  \    description: REST adapter for Google Cloud Assured Workloads API.\n    resources:\n    - path: /organizations/{organizationId}/locations/{location}/workloads\n      name: listworkloads\n      operations:\n      - method: GET\n        name: listworkloads\n        description: Google Cloud Assured Workloads List workloads\n        call: google-cloud-assured-workloads.listworkloads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/locations/{location}/workloads\n      name: createworkload\n      operations:\n      - method: POST\n        name: createworkload\n        description: Google Cloud Assured Workloads Create a workload\n        call: google-cloud-assured-workloads.createworkload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}\n      name: getworkload\n      operations:\n      - method: GET\n  \
  \      name: getworkload\n        description: Google Cloud Assured Workloads Get a workload\n        call: google-cloud-assured-workloads.getworkload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}\n      name: updateworkload\n      operations:\n      - method: PATCH\n        name: updateworkload\n        description: Google Cloud Assured Workloads Update a workload\n        call: google-cloud-assured-workloads.updateworkload\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}\n      name: deleteworkload\n      operations:\n      - method: DELETE\n        name: deleteworkload\n        description: Google Cloud Assured Workloads Delete a workload\n        call: google-cloud-assured-workloads.deleteworkload\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /organizations/{organizationId}/locations/{location}/workloads/{workloadId}/violations\n      name: listviolations\n      operations:\n      - method: GET\n        name: listviolations\n        description: Google Cloud Assured Workloads List violations\n        call: google-cloud-assured-workloads.listviolations\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-assured-workloads-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Assured Workloads API for AI agent use.\n    tools:\n    - name: listworkloads\n      description: Google Cloud Assured Workloads List workloads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-assured-workloads.listworkloads\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkload\n      description: Google Cloud Assured\
  \ Workloads Create a workload\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-assured-workloads.createworkload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkload\n      description: Google Cloud Assured Workloads Get a workload\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-assured-workloads.getworkload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkload\n      description: Google Cloud Assured Workloads Update a workload\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-assured-workloads.updateworkload\n      with:\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: deleteworkload\n      description: Google Cloud Assured Workloads Delete a workload\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-assured-workloads.deleteworkload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listviolations\n      description: Google Cloud Assured Workloads List violations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-assured-workloads.listviolations\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_ASSURED_WORKLOADS_TOKEN: GOOGLE_CLOUD_ASSURED_WORKLOADS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-assured-workloads/refs/heads/main/capabilities/google-cloud-assured-workloads-capability.yaml
tags:
- Google
- Cloud
- Assured
- Workloads
- API
tools:
- description: Google Cloud Assured Workloads List workloads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkloads
- description: Google Cloud Assured Workloads Create a workload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkload
- description: Google Cloud Assured Workloads Get a workload
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkload
- description: Google Cloud Assured Workloads Update a workload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateworkload
- description: Google Cloud Assured Workloads Delete a workload
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkload
- description: Google Cloud Assured Workloads List violations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listviolations
---
