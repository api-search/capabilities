---
categories: []
consumed_apis: []
description: API for managing Cloud Native Application Bundles (CNAB). This API provides endpoints for managing CNAB bundles, claims, claim results, dependencies, parameter sources, relocation mappings, and installation status.
layout: capability
name: Application Research CNAB Bundle API
operations:
- description: Application Research List all bundles
  method: GET
  name: listbundles
  path: /bundles
- description: Application Research Create a new bundle
  method: POST
  name: createbundle
  path: /bundles
- description: Application Research Get a bundle by name
  method: GET
  name: getbundle
  path: /bundles/{name}
- description: Application Research Update an existing bundle
  method: PUT
  name: updatebundle
  path: /bundles/{name}
- description: Application Research Delete a bundle
  method: DELETE
  name: deletebundle
  path: /bundles/{name}
- description: Application Research Execute a bundle action
  method: POST
  name: executebundleaction
  path: /bundles/{name}/actions/{action}
- description: Application Research List all claims
  method: GET
  name: listclaims
  path: /claims
- description: Application Research Create a new claim
  method: POST
  name: createclaim
  path: /claims
- description: Application Research Get a claim by ID
  method: GET
  name: getclaim
  path: /claims/{id}
- description: Application Research List results for a claim
  method: GET
  name: listclaimresults
  path: /claims/{id}/results
- description: Application Research Get a claim result by ID
  method: GET
  name: getclaimresult
  path: /results/{id}
- description: Application Research List all installations
  method: GET
  name: listinstallations
  path: /installations
- description: Application Research Get installation status
  method: GET
  name: getinstallationstatus
  path: /installations/{name}/status
personas: []
provider_name: Application Research
provider_slug: application-research
search_terms:
- application research update an existing bundle
- application research delete a bundle
- createclaim
- application research list all installations
- api
- workload specifications
- declaring service dependencies (databases, caches, queues) needed by applications
- cloud native
- updatebundle
- defining platform-agnostic application workload requirements
- application research list all claims
- createbundle
- application research get a bundle by name
- listbundles
- application research get installation status
- integration
- specifications
- research
- application
- deletebundle
- packaging and distributing application bundles
- application research list results for a claim
- application research execute a bundle action
- application research get a claim by id
- application research create a new bundle
- getclaim
- application research get a claim result by id
- listinstallations
- listclaimresults
- executebundleaction
- getclaimresult
- application research list all bundles
- getinstallationstatus
- application dependencies
- application research create a new claim
- listclaims
- getbundle
slug: application-research-capability
source_filename: application-research-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Application Research CNAB Bundle API\n  description: API for managing Cloud Native Application Bundles (CNAB). This API provides endpoints for managing CNAB bundles,\n    claims, claim results, dependencies, parameter sources, relocation mappings, and installation status.\n  tags:\n  - Application\n  - Research\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: application-research\n    baseUri: https://api.example.com/v1\n    description: Application Research CNAB Bundle API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{APPLICATION_RESEARCH_TOKEN}}'\n    resources:\n    - name: bundles\n      path: /bundles\n      operations:\n      - name: listbundles\n        method: GET\n        description: Application Research List all bundles\n        inputParameters:\n        - name: keyword\n          in: query\n          type: string\n          description:\
  \ Filter bundles by keyword\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbundle\n        method: POST\n        description: Application Research Create a new bundle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bundles-name\n      path: /bundles/{name}\n      operations:\n      - name: getbundle\n        method: GET\n        description: Application Research Get a bundle by name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebundle\n        method: PUT\n        description: Application Research Update an existing bundle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebundle\n        method: DELETE\n\
  \        description: Application Research Delete a bundle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: bundles-name-actions-action\n      path: /bundles/{name}/actions/{action}\n      operations:\n      - name: executebundleaction\n        method: POST\n        description: Application Research Execute a bundle action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims\n      path: /claims\n      operations:\n      - name: listclaims\n        method: GET\n        description: Application Research List all claims\n        inputParameters:\n        - name: installation\n          in: query\n          type: string\n          description: Filter by installation name\n        - name: action\n          in: query\n          type: string\n          description: Filter by action type\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createclaim\n        method: POST\n        description: Application Research Create a new claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims-id\n      path: /claims/{id}\n      operations:\n      - name: getclaim\n        method: GET\n        description: Application Research Get a claim by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: claims-id-results\n      path: /claims/{id}/results\n      operations:\n      - name: listclaimresults\n        method: GET\n        description: Application Research List results for a claim\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results-id\n\
  \      path: /results/{id}\n      operations:\n      - name: getclaimresult\n        method: GET\n        description: Application Research Get a claim result by ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: installations\n      path: /installations\n      operations:\n      - name: listinstallations\n        method: GET\n        description: Application Research List all installations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: installations-name-status\n      path: /installations/{name}/status\n      operations:\n      - name: getinstallationstatus\n        method: GET\n        description: Application Research Get installation status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port:\
  \ 8080\n    namespace: application-research-rest\n    description: REST adapter for Application Research CNAB Bundle API.\n    resources:\n    - path: /bundles\n      name: listbundles\n      operations:\n      - method: GET\n        name: listbundles\n        description: Application Research List all bundles\n        call: application-research.listbundles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bundles\n      name: createbundle\n      operations:\n      - method: POST\n        name: createbundle\n        description: Application Research Create a new bundle\n        call: application-research.createbundle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bundles/{name}\n      name: getbundle\n      operations:\n      - method: GET\n        name: getbundle\n        description: Application Research Get a bundle by name\n        call: application-research.getbundle\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /bundles/{name}\n      name: updatebundle\n      operations:\n      - method: PUT\n        name: updatebundle\n        description: Application Research Update an existing bundle\n        call: application-research.updatebundle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bundles/{name}\n      name: deletebundle\n      operations:\n      - method: DELETE\n        name: deletebundle\n        description: Application Research Delete a bundle\n        call: application-research.deletebundle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /bundles/{name}/actions/{action}\n      name: executebundleaction\n      operations:\n      - method: POST\n        name: executebundleaction\n        description: Application Research Execute a bundle action\n        call: application-research.executebundleaction\n        outputParameters:\n        - type: object\n      \
  \    mapping: $.\n    - path: /claims\n      name: listclaims\n      operations:\n      - method: GET\n        name: listclaims\n        description: Application Research List all claims\n        call: application-research.listclaims\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims\n      name: createclaim\n      operations:\n      - method: POST\n        name: createclaim\n        description: Application Research Create a new claim\n        call: application-research.createclaim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims/{id}\n      name: getclaim\n      operations:\n      - method: GET\n        name: getclaim\n        description: Application Research Get a claim by ID\n        call: application-research.getclaim\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /claims/{id}/results\n      name: listclaimresults\n      operations:\n      - method: GET\n\
  \        name: listclaimresults\n        description: Application Research List results for a claim\n        call: application-research.listclaimresults\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /results/{id}\n      name: getclaimresult\n      operations:\n      - method: GET\n        name: getclaimresult\n        description: Application Research Get a claim result by ID\n        call: application-research.getclaimresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /installations\n      name: listinstallations\n      operations:\n      - method: GET\n        name: listinstallations\n        description: Application Research List all installations\n        call: application-research.listinstallations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /installations/{name}/status\n      name: getinstallationstatus\n      operations:\n      - method: GET\n        name:\
  \ getinstallationstatus\n        description: Application Research Get installation status\n        call: application-research.getinstallationstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: application-research-mcp\n    transport: http\n    description: MCP adapter for Application Research CNAB Bundle API for AI agent use.\n    tools:\n    - name: listbundles\n      description: Application Research List all bundles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.listbundles\n      with:\n        keyword: tools.keyword\n      inputParameters:\n      - name: keyword\n        type: string\n        description: Filter bundles by keyword\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbundle\n      description: Application Research Create a new bundle\n      hints:\n        readOnly: false\n    \
  \    destructive: false\n        idempotent: false\n      call: application-research.createbundle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbundle\n      description: Application Research Get a bundle by name\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.getbundle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebundle\n      description: Application Research Update an existing bundle\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: application-research.updatebundle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebundle\n      description: Application Research Delete a bundle\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: application-research.deletebundle\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: executebundleaction\n      description: Application Research Execute a bundle action\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: application-research.executebundleaction\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclaims\n      description: Application Research List all claims\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.listclaims\n      with:\n        installation: tools.installation\n        action: tools.action\n      inputParameters:\n      - name: installation\n        type: string\n        description: Filter by installation name\n      - name: action\n        type: string\n        description: Filter by action type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createclaim\n      description: Application Research\
  \ Create a new claim\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: application-research.createclaim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclaim\n      description: Application Research Get a claim by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.getclaim\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclaimresults\n      description: Application Research List results for a claim\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.listclaimresults\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getclaimresult\n      description: Application Research Get a claim result by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: application-research.getclaimresult\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstallations\n      description: Application Research List all installations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.listinstallations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstallationstatus\n      description: Application Research Get installation status\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: application-research.getinstallationstatus\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    APPLICATION_RESEARCH_TOKEN: APPLICATION_RESEARCH_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/application-research/refs/heads/main/capabilities/application-research-capability.yaml
tags:
- Application
- Research
- API
tools:
- description: Application Research List all bundles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbundles
- description: Application Research Create a new bundle
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbundle
- description: Application Research Get a bundle by name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbundle
- description: Application Research Update an existing bundle
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebundle
- description: Application Research Delete a bundle
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebundle
- description: Application Research Execute a bundle action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executebundleaction
- description: Application Research List all claims
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaims
- description: Application Research Create a new claim
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createclaim
- description: Application Research Get a claim by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclaim
- description: Application Research List results for a claim
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclaimresults
- description: Application Research Get a claim result by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclaimresult
- description: Application Research List all installations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstallations
- description: Application Research Get installation status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstallationstatus
---
