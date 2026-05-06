---
categories: []
consumed_apis: []
description: Provides programmatic access to manage interconnect connections, attachments, and locations for hybrid cloud connectivity between on-premises networks and Google Cloud.
layout: capability
name: Google Cloud Interconnect API
operations:
- description: Google Cloud Interconnect List interconnects
  method: GET
  name: listinterconnects
  path: /projects/{project}/global/interconnects
- description: Google Cloud Interconnect Create an interconnect
  method: POST
  name: createinterconnect
  path: /projects/{project}/global/interconnects
- description: Google Cloud Interconnect Get an interconnect
  method: GET
  name: getinterconnect
  path: /projects/{project}/global/interconnects/{interconnect}
- description: Google Cloud Interconnect Delete an interconnect
  method: DELETE
  name: deleteinterconnect
  path: /projects/{project}/global/interconnects/{interconnect}
- description: Google Cloud Interconnect List interconnect attachments
  method: GET
  name: listinterconnectattachments
  path: /projects/{project}/regions/{region}/interconnectAttachments
- description: Google Cloud Interconnect List interconnect locations
  method: GET
  name: listinterconnectlocations
  path: /projects/{project}/global/interconnectLocations
personas: []
provider_name: Google Cloud Interconnect
provider_slug: google-cloud-interconnect
search_terms:
- networking
- listinterconnects
- google cloud interconnect list interconnect locations
- createinterconnect
- listinterconnectattachments
- listinterconnectlocations
- google cloud interconnect delete an interconnect
- hybrid cloud
- cloud
- google
- dedicated connectivity
- getinterconnect
- google cloud interconnect create an interconnect
- interconnect
- api
- google cloud interconnect list interconnect attachments
- google cloud interconnect get an interconnect
- deleteinterconnect
- google cloud
- google cloud interconnect list interconnects
slug: google-cloud-interconnect-capability
source_filename: google-cloud-interconnect-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Interconnect API\n  description: Provides programmatic access to manage interconnect connections, attachments, and locations for hybrid cloud\n    connectivity between on-premises networks and Google Cloud.\n  tags:\n  - Google\n  - Cloud\n  - Interconnect\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-interconnect\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud Interconnect API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_INTERCONNECT_TOKEN}}'\n    resources:\n    - name: projects-project-global-interconnects\n      path: /projects/{project}/global/interconnects\n      operations:\n      - name: listinterconnects\n        method: GET\n        description: Google Cloud Interconnect List interconnects\n        inputParameters:\n        - name: project\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinterconnect\n        method: POST\n        description: Google Cloud Interconnect Create an interconnect\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-interconnects-interconne\n      path: /projects/{project}/global/interconnects/{interconnect}\n      operations:\n      - name: getinterconnect\n        method: GET\n        description: Google Cloud Interconnect Get an interconnect\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: interconnect\n          in: path\n     \
  \     type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinterconnect\n        method: DELETE\n        description: Google Cloud Interconnect Delete an interconnect\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: interconnect\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-interconnectatta\n      path: /projects/{project}/regions/{region}/interconnectAttachments\n      operations:\n      - name: listinterconnectattachments\n        method: GET\n        description: Google Cloud Interconnect List interconnect attachments\n        inputParameters:\n        - name: project\n \
  \         in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-interconnectlocations\n      path: /projects/{project}/global/interconnectLocations\n      operations:\n      - name: listinterconnectlocations\n        method: GET\n        description: Google Cloud Interconnect List interconnect locations\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-interconnect-rest\n    description: REST adapter for Google Cloud Interconnect API.\n    resources:\n    - path:\
  \ /projects/{project}/global/interconnects\n      name: listinterconnects\n      operations:\n      - method: GET\n        name: listinterconnects\n        description: Google Cloud Interconnect List interconnects\n        call: google-cloud-interconnect.listinterconnects\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/interconnects\n      name: createinterconnect\n      operations:\n      - method: POST\n        name: createinterconnect\n        description: Google Cloud Interconnect Create an interconnect\n        call: google-cloud-interconnect.createinterconnect\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/interconnects/{interconnect}\n      name: getinterconnect\n      operations:\n      - method: GET\n        name: getinterconnect\n        description:\
  \ Google Cloud Interconnect Get an interconnect\n        call: google-cloud-interconnect.getinterconnect\n        with:\n          project: rest.project\n          interconnect: rest.interconnect\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/interconnects/{interconnect}\n      name: deleteinterconnect\n      operations:\n      - method: DELETE\n        name: deleteinterconnect\n        description: Google Cloud Interconnect Delete an interconnect\n        call: google-cloud-interconnect.deleteinterconnect\n        with:\n          project: rest.project\n          interconnect: rest.interconnect\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/interconnectAttachments\n      name: listinterconnectattachments\n      operations:\n      - method: GET\n        name: listinterconnectattachments\n        description: Google Cloud Interconnect List interconnect\
  \ attachments\n        call: google-cloud-interconnect.listinterconnectattachments\n        with:\n          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/interconnectLocations\n      name: listinterconnectlocations\n      operations:\n      - method: GET\n        name: listinterconnectlocations\n        description: Google Cloud Interconnect List interconnect locations\n        call: google-cloud-interconnect.listinterconnectlocations\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-interconnect-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Interconnect API for AI agent use.\n    tools:\n    - name: listinterconnects\n      description: Google Cloud Interconnect List interconnects\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: google-cloud-interconnect.listinterconnects\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinterconnect\n      description: Google Cloud Interconnect Create an interconnect\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-interconnect.createinterconnect\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinterconnect\n      description: Google Cloud Interconnect Get an interconnect\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: google-cloud-interconnect.getinterconnect\n      with:\n        project: tools.project\n        interconnect: tools.interconnect\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: interconnect\n        type: string\n        description: interconnect\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinterconnect\n      description: Google Cloud Interconnect Delete an interconnect\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-interconnect.deleteinterconnect\n      with:\n        project: tools.project\n        interconnect: tools.interconnect\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: interconnect\n        type: string\n        description:\
  \ interconnect\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinterconnectattachments\n      description: Google Cloud Interconnect List interconnect attachments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-interconnect.listinterconnectattachments\n      with:\n        project: tools.project\n        region: tools.region\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinterconnectlocations\n      description: Google Cloud Interconnect List interconnect locations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-interconnect.listinterconnectlocations\n\
  \      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_INTERCONNECT_TOKEN: GOOGLE_CLOUD_INTERCONNECT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-interconnect/refs/heads/main/capabilities/google-cloud-interconnect-capability.yaml
tags:
- Google
- Cloud
- Interconnect
- API
tools:
- description: Google Cloud Interconnect List interconnects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinterconnects
- description: Google Cloud Interconnect Create an interconnect
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinterconnect
- description: Google Cloud Interconnect Get an interconnect
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinterconnect
- description: Google Cloud Interconnect Delete an interconnect
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinterconnect
- description: Google Cloud Interconnect List interconnect attachments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinterconnectattachments
- description: Google Cloud Interconnect List interconnect locations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinterconnectlocations
---
