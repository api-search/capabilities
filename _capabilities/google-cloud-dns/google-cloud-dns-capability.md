---
categories: []
consumed_apis: []
description: Manages DNS zones and resource record sets on Google Cloud, including creating managed zones, configuring DNS records, and managing DNS policies.
layout: capability
name: Google Cloud DNS API
operations:
- description: Google Cloud DNS List Managed Zones
  method: GET
  name: listmanagedzones
  path: /projects/{project}/managedZones
- description: Google Cloud DNS Create Managed Zone
  method: POST
  name: createmanagedzone
  path: /projects/{project}/managedZones
- description: Google Cloud DNS Get Managed Zone
  method: GET
  name: getmanagedzone
  path: /projects/{project}/managedZones/{managedZone}
- description: Google Cloud DNS Update Managed Zone
  method: PATCH
  name: patchmanagedzone
  path: /projects/{project}/managedZones/{managedZone}
- description: Google Cloud DNS Delete Managed Zone
  method: DELETE
  name: deletemanagedzone
  path: /projects/{project}/managedZones/{managedZone}
- description: Google Cloud DNS List Resource Record Sets
  method: GET
  name: listresourcerecordsets
  path: /projects/{project}/managedZones/{managedZone}/rrsets
- description: Google Cloud DNS Create Resource Record Set
  method: POST
  name: createresourcerecordset
  path: /projects/{project}/managedZones/{managedZone}/rrsets
- description: Google Cloud DNS List Changes
  method: GET
  name: listchanges
  path: /projects/{project}/managedZones/{managedZone}/changes
- description: Google Cloud DNS Create Change
  method: POST
  name: createchange
  path: /projects/{project}/managedZones/{managedZone}/changes
- description: Google Cloud DNS List Policies
  method: GET
  name: listpolicies
  path: /projects/{project}/policies
personas: []
provider_name: Google Cloud DNS
provider_slug: google-cloud-dns
search_terms:
- networking
- google cloud dns create change
- google cloud dns update managed zone
- name resolution
- createmanagedzone
- dns
- deletemanagedzone
- domain names
- google cloud dns delete managed zone
- getmanagedzone
- google cloud dns list resource record sets
- cloud
- createresourcerecordset
- listpolicies
- google
- listchanges
- google cloud dns create resource record set
- createchange
- google cloud dns list managed zones
- api
- patchmanagedzone
- google cloud dns list policies
- google cloud dns list changes
- listresourcerecordsets
- google cloud dns get managed zone
- google cloud dns create managed zone
- google cloud
- listmanagedzones
slug: google-cloud-dns-capability
source_filename: google-cloud-dns-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud DNS API\n  description: Manages DNS zones and resource record sets on Google Cloud, including creating managed zones, configuring DNS\n    records, and managing DNS policies.\n  tags:\n  - Google\n  - Cloud\n  - Dns\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-dns\n    baseUri: https://dns.googleapis.com/dns/v1\n    description: Google Cloud DNS API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DNS_TOKEN}}'\n    resources:\n    - name: projects-project-managedzones\n      path: /projects/{project}/managedZones\n      operations:\n      - name: listmanagedzones\n        method: GET\n        description: Google Cloud DNS List Managed Zones\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n\
  \          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmanagedzone\n        method: POST\n        description: Google Cloud DNS Create Managed Zone\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-managedzones-managedzone\n      path: /projects/{project}/managedZones/{managedZone}\n      operations:\n      - name: getmanagedzone\n        method: GET\n        description: Google Cloud DNS Get Managed Zone\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n \
  \         type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchmanagedzone\n        method: PATCH\n        description: Google Cloud DNS Update Managed Zone\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletemanagedzone\n        method: DELETE\n        description: Google Cloud DNS Delete Managed Zone\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-managedzones-managedzone-rrsets\n      path: /projects/{project}/managedZones/{managedZone}/rrsets\n      operations:\n      - name: listresourcerecordsets\n        method: GET\n        description: Google Cloud DNS List Resource Record Sets\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: query\n          type: string\n        - name: type\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createresourcerecordset\n        method: POST\n        description: Google Cloud DNS Create Resource Record Set\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-managedzones-managedzone-change\n      path: /projects/{project}/managedZones/{managedZone}/changes\n      operations:\n      - name: listchanges\n        method: GET\n        description: Google Cloud DNS List Changes\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchange\n        method: POST\n        description: Google Cloud\
  \ DNS Create Change\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: managedZone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-policies\n      path: /projects/{project}/policies\n      operations:\n      - name: listpolicies\n        method: GET\n        description: Google Cloud DNS List Policies\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-dns-rest\n    description: REST adapter for Google Cloud DNS API.\n    resources:\n    - path: /projects/{project}/managedZones\n\
  \      name: listmanagedzones\n      operations:\n      - method: GET\n        name: listmanagedzones\n        description: Google Cloud DNS List Managed Zones\n        call: google-cloud-dns.listmanagedzones\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones\n      name: createmanagedzone\n      operations:\n      - method: POST\n        name: createmanagedzone\n        description: Google Cloud DNS Create Managed Zone\n        call: google-cloud-dns.createmanagedzone\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}\n      name: getmanagedzone\n      operations:\n      - method: GET\n        name: getmanagedzone\n        description: Google Cloud DNS Get Managed Zone\n        call: google-cloud-dns.getmanagedzone\n        with:\n         \
  \ project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}\n      name: patchmanagedzone\n      operations:\n      - method: PATCH\n        name: patchmanagedzone\n        description: Google Cloud DNS Update Managed Zone\n        call: google-cloud-dns.patchmanagedzone\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}\n      name: deletemanagedzone\n      operations:\n      - method: DELETE\n        name: deletemanagedzone\n        description: Google Cloud DNS Delete Managed Zone\n        call: google-cloud-dns.deletemanagedzone\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n        \
  \  mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}/rrsets\n      name: listresourcerecordsets\n      operations:\n      - method: GET\n        name: listresourcerecordsets\n        description: Google Cloud DNS List Resource Record Sets\n        call: google-cloud-dns.listresourcerecordsets\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}/rrsets\n      name: createresourcerecordset\n      operations:\n      - method: POST\n        name: createresourcerecordset\n        description: Google Cloud DNS Create Resource Record Set\n        call: google-cloud-dns.createresourcerecordset\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}/changes\n\
  \      name: listchanges\n      operations:\n      - method: GET\n        name: listchanges\n        description: Google Cloud DNS List Changes\n        call: google-cloud-dns.listchanges\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/managedZones/{managedZone}/changes\n      name: createchange\n      operations:\n      - method: POST\n        name: createchange\n        description: Google Cloud DNS Create Change\n        call: google-cloud-dns.createchange\n        with:\n          project: rest.project\n          managedZone: rest.managedZone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/policies\n      name: listpolicies\n      operations:\n      - method: GET\n        name: listpolicies\n        description: Google Cloud DNS List Policies\n        call: google-cloud-dns.listpolicies\n\
  \        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-dns-mcp\n    transport: http\n    description: MCP adapter for Google Cloud DNS API for AI agent use.\n    tools:\n    - name: listmanagedzones\n      description: Google Cloud DNS List Managed Zones\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dns.listmanagedzones\n      with:\n        project: tools.project\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ createmanagedzone\n      description: Google Cloud DNS Create Managed Zone\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dns.createmanagedzone\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmanagedzone\n      description: Google Cloud DNS Get Managed Zone\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dns.getmanagedzone\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: patchmanagedzone\n      description: Google Cloud DNS Update Managed Zone\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dns.patchmanagedzone\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletemanagedzone\n      description: Google Cloud DNS Delete Managed Zone\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-dns.deletemanagedzone\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n      inputParameters:\n      -\
  \ name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listresourcerecordsets\n      description: Google Cloud DNS List Resource Record Sets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dns.listresourcerecordsets\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n        name: tools.name\n        type: tools.type\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      - name: name\n        type: string\n        description: name\n      - name: type\n        type: string\n        description:\
  \ type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createresourcerecordset\n      description: Google Cloud DNS Create Resource Record Set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dns.createresourcerecordset\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listchanges\n      description: Google Cloud DNS List Changes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dns.listchanges\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n\
  \      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createchange\n      description: Google Cloud DNS Create Change\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-dns.createchange\n      with:\n        project: tools.project\n        managedZone: tools.managedZone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: managedZone\n        type: string\n        description: managedZone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpolicies\n      description: Google Cloud DNS List Policies\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: google-cloud-dns.listpolicies\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DNS_TOKEN: GOOGLE_CLOUD_DNS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-dns/refs/heads/main/capabilities/google-cloud-dns-capability.yaml
tags:
- Google
- Cloud
- Dns
- API
tools:
- description: Google Cloud DNS List Managed Zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmanagedzones
- description: Google Cloud DNS Create Managed Zone
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmanagedzone
- description: Google Cloud DNS Get Managed Zone
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmanagedzone
- description: Google Cloud DNS Update Managed Zone
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchmanagedzone
- description: Google Cloud DNS Delete Managed Zone
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletemanagedzone
- description: Google Cloud DNS List Resource Record Sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listresourcerecordsets
- description: Google Cloud DNS Create Resource Record Set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresourcerecordset
- description: Google Cloud DNS List Changes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchanges
- description: Google Cloud DNS Create Change
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchange
- description: Google Cloud DNS List Policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpolicies
---
