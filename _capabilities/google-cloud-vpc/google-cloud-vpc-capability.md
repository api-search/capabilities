---
categories: []
consumed_apis: []
description: Provides programmatic access to manage virtual private cloud networks, subnets, firewall rules, routes, and peering connections within Google Cloud.
layout: capability
name: Google Cloud VPC API
operations:
- description: Google Cloud VPC List VPC networks
  method: GET
  name: listnetworks
  path: /projects/{project}/global/networks
- description: Google Cloud VPC Create a VPC network
  method: POST
  name: createnetwork
  path: /projects/{project}/global/networks
- description: Google Cloud VPC Get a VPC network
  method: GET
  name: getnetwork
  path: /projects/{project}/global/networks/{network}
- description: Google Cloud VPC Delete a VPC network
  method: DELETE
  name: deletenetwork
  path: /projects/{project}/global/networks/{network}
- description: Google Cloud VPC List subnetworks
  method: GET
  name: listsubnetworks
  path: /projects/{project}/regions/{region}/subnetworks
- description: Google Cloud VPC List firewall rules
  method: GET
  name: listfirewalls
  path: /projects/{project}/global/firewalls
- description: Google Cloud VPC List routes
  method: GET
  name: listroutes
  path: /projects/{project}/global/routes
personas: []
provider_name: Google Cloud VPC
provider_slug: google-cloud-vpc
search_terms:
- vpc
- createnetwork
- networking
- google cloud vpc get a vpc network
- listroutes
- listfirewalls
- google cloud vpc delete a vpc network
- firewall
- google cloud vpc list subnetworks
- google cloud vpc create a vpc network
- cloud
- google
- google cloud vpc list routes
- google cloud vpc list vpc networks
- google cloud vpc list firewall rules
- listsubnetworks
- api
- getnetwork
- listnetworks
- virtual networks
- deletenetwork
- google cloud
slug: google-cloud-vpc-capability
source_filename: google-cloud-vpc-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud VPC API\n  description: Provides programmatic access to manage virtual private cloud networks, subnets, firewall rules, routes, and\n    peering connections within Google Cloud.\n  tags:\n  - Google\n  - Cloud\n  - Vpc\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-vpc\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud VPC API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_VPC_TOKEN}}'\n    resources:\n    - name: projects-project-global-networks\n      path: /projects/{project}/global/networks\n      operations:\n      - name: listnetworks\n        method: GET\n        description: Google Cloud VPC List VPC networks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnetwork\n        method: POST\n        description: Google Cloud VPC Create a VPC network\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-networks-network\n      path: /projects/{project}/global/networks/{network}\n      operations:\n      - name: getnetwork\n        method: GET\n        description: Google Cloud VPC Get a VPC network\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: network\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: deletenetwork\n        method: DELETE\n        description: Google Cloud VPC Delete a VPC network\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: network\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-regions-region-subnetworks\n      path: /projects/{project}/regions/{region}/subnetworks\n      operations:\n      - name: listsubnetworks\n        method: GET\n        description: Google Cloud VPC List subnetworks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: region\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-firewalls\n      path: /projects/{project}/global/firewalls\n      operations:\n      - name: listfirewalls\n        method: GET\n        description: Google Cloud VPC List firewall rules\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-routes\n      path: /projects/{project}/global/routes\n      operations:\n      - name: listroutes\n        method: GET\n        description: Google Cloud VPC List routes\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-vpc-rest\n    description: REST adapter for Google Cloud VPC API.\n    resources:\n    - path: /projects/{project}/global/networks\n      name: listnetworks\n      operations:\n      - method: GET\n        name: listnetworks\n        description: Google Cloud VPC List VPC networks\n        call: google-cloud-vpc.listnetworks\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/networks\n      name: createnetwork\n      operations:\n      - method: POST\n        name: createnetwork\n        description: Google Cloud VPC Create a VPC network\n        call: google-cloud-vpc.createnetwork\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/networks/{network}\n      name: getnetwork\n      operations:\n\
  \      - method: GET\n        name: getnetwork\n        description: Google Cloud VPC Get a VPC network\n        call: google-cloud-vpc.getnetwork\n        with:\n          project: rest.project\n          network: rest.network\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/networks/{network}\n      name: deletenetwork\n      operations:\n      - method: DELETE\n        name: deletenetwork\n        description: Google Cloud VPC Delete a VPC network\n        call: google-cloud-vpc.deletenetwork\n        with:\n          project: rest.project\n          network: rest.network\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/regions/{region}/subnetworks\n      name: listsubnetworks\n      operations:\n      - method: GET\n        name: listsubnetworks\n        description: Google Cloud VPC List subnetworks\n        call: google-cloud-vpc.listsubnetworks\n        with:\n\
  \          project: rest.project\n          region: rest.region\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/firewalls\n      name: listfirewalls\n      operations:\n      - method: GET\n        name: listfirewalls\n        description: Google Cloud VPC List firewall rules\n        call: google-cloud-vpc.listfirewalls\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/routes\n      name: listroutes\n      operations:\n      - method: GET\n        name: listroutes\n        description: Google Cloud VPC List routes\n        call: google-cloud-vpc.listroutes\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-vpc-mcp\n    transport: http\n    description: MCP adapter for Google Cloud\
  \ VPC API for AI agent use.\n    tools:\n    - name: listnetworks\n      description: Google Cloud VPC List VPC networks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vpc.listnetworks\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnetwork\n      description: Google Cloud VPC Create a VPC network\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-vpc.createnetwork\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnetwork\n      description: Google\
  \ Cloud VPC Get a VPC network\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vpc.getnetwork\n      with:\n        project: tools.project\n        network: tools.network\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: network\n        type: string\n        description: network\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenetwork\n      description: Google Cloud VPC Delete a VPC network\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-vpc.deletenetwork\n      with:\n        project: tools.project\n        network: tools.network\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: network\n        type: string\n  \
  \      description: network\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsubnetworks\n      description: Google Cloud VPC List subnetworks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vpc.listsubnetworks\n      with:\n        project: tools.project\n        region: tools.region\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: region\n        type: string\n        description: region\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfirewalls\n      description: Google Cloud VPC List firewall rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vpc.listfirewalls\n      with:\n        project: tools.project\n      inputParameters:\n     \
  \ - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroutes\n      description: Google Cloud VPC List routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-vpc.listroutes\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_VPC_TOKEN: GOOGLE_CLOUD_VPC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-vpc/refs/heads/main/capabilities/google-cloud-vpc-capability.yaml
tags:
- Google
- Cloud
- Vpc
- API
tools:
- description: Google Cloud VPC List VPC networks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnetworks
- description: Google Cloud VPC Create a VPC network
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnetwork
- description: Google Cloud VPC Get a VPC network
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetwork
- description: Google Cloud VPC Delete a VPC network
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenetwork
- description: Google Cloud VPC List subnetworks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsubnetworks
- description: Google Cloud VPC List firewall rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfirewalls
- description: Google Cloud VPC List routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutes
---
