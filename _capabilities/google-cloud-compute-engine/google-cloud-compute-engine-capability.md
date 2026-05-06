---
categories: []
consumed_apis: []
description: Creates and runs virtual machines on Google Cloud infrastructure, with support for managing disks, networks, and firewall rules.
layout: capability
name: Google Cloud Compute Engine Google Compute Engine API
operations:
- description: Google Cloud Compute Engine List Instances
  method: GET
  name: listinstances
  path: /projects/{project}/zones/{zone}/instances
- description: Google Cloud Compute Engine Create Instance
  method: POST
  name: insertinstance
  path: /projects/{project}/zones/{zone}/instances
- description: Google Cloud Compute Engine Get Instance
  method: GET
  name: getinstance
  path: /projects/{project}/zones/{zone}/instances/{instance}
- description: Google Cloud Compute Engine Delete Instance
  method: DELETE
  name: deleteinstance
  path: /projects/{project}/zones/{zone}/instances/{instance}
- description: Google Cloud Compute Engine List Disks
  method: GET
  name: listdisks
  path: /projects/{project}/zones/{zone}/disks
- description: Google Cloud Compute Engine List Networks
  method: GET
  name: listnetworks
  path: /projects/{project}/global/networks
- description: Google Cloud Compute Engine List Firewalls
  method: GET
  name: listfirewalls
  path: /projects/{project}/global/firewalls
personas: []
provider_name: Google Cloud Compute Engine
provider_slug: google-cloud-compute-engine
search_terms:
- compute
- google cloud compute engine list instances
- listfirewalls
- google cloud compute engine get instance
- infrastructure
- deleteinstance
- iaas
- google cloud compute engine list networks
- virtual machines
- cloud
- engine
- google
- google cloud compute engine create instance
- getinstance
- google cloud compute engine list firewalls
- insertinstance
- api
- listdisks
- listnetworks
- listinstances
- google cloud compute engine list disks
- google cloud compute engine delete instance
- google cloud
slug: google-cloud-compute-engine-capability
source_filename: google-cloud-compute-engine-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Compute Engine Google Compute Engine API\n  description: Creates and runs virtual machines on Google Cloud infrastructure, with support for managing disks, networks,\n    and firewall rules.\n  tags:\n  - Google\n  - Cloud\n  - Compute\n  - Engine\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-compute-engine\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud Compute Engine Google Compute Engine API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_COMPUTE_ENGINE_TOKEN}}'\n    resources:\n    - name: projects-project-zones-zone-instances\n      path: /projects/{project}/zones/{zone}/instances\n      operations:\n      - name: listinstances\n        method: GET\n        description: Google Cloud Compute Engine List Instances\n        inputParameters:\n        - name: project\n\
  \          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: maxResults\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertinstance\n        method: POST\n        description: Google Cloud Compute Engine Create Instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-zones-zone-instances-instance\n      path: /projects/{project}/zones/{zone}/instances/{instance}\n\
  \      operations:\n      - name: getinstance\n        method: GET\n        description: Google Cloud Compute Engine Get Instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstance\n        method: DELETE\n        description: Google Cloud Compute Engine Delete Instance\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        - name: instance\n          in: path\n          type: string\n          required: true\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-zones-zone-disks\n      path: /projects/{project}/zones/{zone}/disks\n      operations:\n      - name: listdisks\n        method: GET\n        description: Google Cloud Compute Engine List Disks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: zone\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-networks\n      path: /projects/{project}/global/networks\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Google Cloud Compute Engine List Networks\n        inputParameters:\n        - name: project\n          in: path\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-firewalls\n      path: /projects/{project}/global/firewalls\n      operations:\n      - name: listfirewalls\n        method: GET\n        description: Google Cloud Compute Engine List Firewalls\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-compute-engine-rest\n    description: REST adapter for Google Cloud Compute Engine Google Compute Engine API.\n    resources:\n    - path: /projects/{project}/zones/{zone}/instances\n      name: listinstances\n      operations:\n      - method: GET\n        name: listinstances\n      \
  \  description: Google Cloud Compute Engine List Instances\n        call: google-cloud-compute-engine.listinstances\n        with:\n          project: rest.project\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/zones/{zone}/instances\n      name: insertinstance\n      operations:\n      - method: POST\n        name: insertinstance\n        description: Google Cloud Compute Engine Create Instance\n        call: google-cloud-compute-engine.insertinstance\n        with:\n          project: rest.project\n          zone: rest.zone\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/zones/{zone}/instances/{instance}\n      name: getinstance\n      operations:\n      - method: GET\n        name: getinstance\n        description: Google Cloud Compute Engine Get Instance\n        call: google-cloud-compute-engine.getinstance\n        with:\n          project:\
  \ rest.project\n          zone: rest.zone\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/zones/{zone}/instances/{instance}\n      name: deleteinstance\n      operations:\n      - method: DELETE\n        name: deleteinstance\n        description: Google Cloud Compute Engine Delete Instance\n        call: google-cloud-compute-engine.deleteinstance\n        with:\n          project: rest.project\n          zone: rest.zone\n          instance: rest.instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/zones/{zone}/disks\n      name: listdisks\n      operations:\n      - method: GET\n        name: listdisks\n        description: Google Cloud Compute Engine List Disks\n        call: google-cloud-compute-engine.listdisks\n        with:\n          project: rest.project\n          zone: rest.zone\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /projects/{project}/global/networks\n      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Google Cloud Compute Engine List Networks\n        call: google-cloud-compute-engine.listnetworks\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/firewalls\n      name: listfirewalls\n      operations:\n      - method: GET\n        name: listfirewalls\n        description: Google Cloud Compute Engine List Firewalls\n        call: google-cloud-compute-engine.listfirewalls\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-compute-engine-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Compute Engine Google Compute Engine API for AI\
  \ agent use.\n    tools:\n    - name: listinstances\n      description: Google Cloud Compute Engine List Instances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-compute-engine.listinstances\n      with:\n        project: tools.project\n        zone: tools.zone\n        maxResults: tools.maxResults\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      - name: maxResults\n        type: integer\n        description: maxResults\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: insertinstance\n      description: Google Cloud Compute Engine Create Instance\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: google-cloud-compute-engine.insertinstance\n      with:\n        project: tools.project\n        zone: tools.zone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstance\n      description: Google Cloud Compute Engine Get Instance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-compute-engine.getinstance\n      with:\n        project: tools.project\n        zone: tools.zone\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n\
  \      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstance\n      description: Google Cloud Compute Engine Delete Instance\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-compute-engine.deleteinstance\n      with:\n        project: tools.project\n        zone: tools.zone\n        instance: tools.instance\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      - name: instance\n        type: string\n        description: instance\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdisks\n      description: Google Cloud Compute Engine List Disks\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-compute-engine.listdisks\n      with:\n        project: tools.project\n        zone: tools.zone\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: zone\n        type: string\n        description: zone\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listnetworks\n      description: Google Cloud Compute Engine List Networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-compute-engine.listnetworks\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfirewalls\n      description: Google\
  \ Cloud Compute Engine List Firewalls\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-compute-engine.listfirewalls\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_COMPUTE_ENGINE_TOKEN: GOOGLE_CLOUD_COMPUTE_ENGINE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-compute-engine/refs/heads/main/capabilities/google-cloud-compute-engine-capability.yaml
tags:
- Google
- Cloud
- Compute
- Engine
- API
tools:
- description: Google Cloud Compute Engine List Instances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstances
- description: Google Cloud Compute Engine Create Instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertinstance
- description: Google Cloud Compute Engine Get Instance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstance
- description: Google Cloud Compute Engine Delete Instance
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstance
- description: Google Cloud Compute Engine List Disks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdisks
- description: Google Cloud Compute Engine List Networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Google Cloud Compute Engine List Firewalls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfirewalls
---
