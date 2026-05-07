---
categories: []
consumed_apis: []
description: Provides programmatic access to manage load balancers, backend services, health checks, URL maps, and forwarding rules for distributing traffic across Google Cloud resources.
layout: capability
name: Google Cloud Load Balancing API
operations:
- description: Google Cloud Load Balancing List backend services
  method: GET
  name: listbackendservices
  path: /projects/{project}/global/backendServices
- description: Google Cloud Load Balancing Create a backend service
  method: POST
  name: createbackendservice
  path: /projects/{project}/global/backendServices
- description: Google Cloud Load Balancing Get a backend service
  method: GET
  name: getbackendservice
  path: /projects/{project}/global/backendServices/{backendService}
- description: Google Cloud Load Balancing Delete a backend service
  method: DELETE
  name: deletebackendservice
  path: /projects/{project}/global/backendServices/{backendService}
- description: Google Cloud Load Balancing List health checks
  method: GET
  name: listhealthchecks
  path: /projects/{project}/global/healthChecks
- description: Google Cloud Load Balancing List forwarding rules
  method: GET
  name: listforwardingrules
  path: /projects/{project}/global/forwardingRules
- description: Google Cloud Load Balancing List URL maps
  method: GET
  name: listurlmaps
  path: /projects/{project}/global/urlMaps
personas: []
provider_name: Google Cloud Load Balancing
provider_slug: google-cloud-load-balancing
search_terms:
- createbackendservice
- listurlmaps
- networking
- google cloud load balancing delete a backend service
- api
- google cloud load balancing list url maps
- getbackendservice
- google
- google cloud load balancing list health checks
- infrastructure
- google cloud load balancing get a backend service
- listforwardingrules
- google cloud load balancing list backend services
- load balancing
- traffic management
- balancing
- cloud
- listhealthchecks
- google cloud
- deletebackendservice
- load
- listbackendservices
- google cloud load balancing list forwarding rules
- google cloud load balancing create a backend service
slug: google-cloud-load-balancing-capability
source_filename: google-cloud-load-balancing-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Load Balancing API\n  description: Provides programmatic access to manage load balancers, backend services, health checks, URL maps, and forwarding\n    rules for distributing traffic across Google Cloud resources.\n  tags:\n  - Google\n  - Cloud\n  - Load\n  - Balancing\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-load-balancing\n    baseUri: https://compute.googleapis.com/compute/v1\n    description: Google Cloud Load Balancing API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_LOAD_BALANCING_TOKEN}}'\n    resources:\n    - name: projects-project-global-backendservices\n      path: /projects/{project}/global/backendServices\n      operations:\n      - name: listbackendservices\n        method: GET\n        description: Google Cloud Load Balancing List backend services\n        inputParameters:\n       \
  \ - name: project\n          in: path\n          type: string\n          required: true\n          description: Project ID for this request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbackendservice\n        method: POST\n        description: Google Cloud Load Balancing Create a backend service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-backendservices-backends\n      path: /projects/{project}/global/backendServices/{backendService}\n      operations:\n      - name: getbackendservice\n        method: GET\n        description: Google Cloud Load Balancing Get a backend service\n        inputParameters:\n        - name: project\n          in: path\n\
  \          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebackendservice\n        method: DELETE\n        description: Google Cloud Load Balancing Delete a backend service\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: backendService\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-healthchecks\n      path: /projects/{project}/global/healthChecks\n      operations:\n      - name: listhealthchecks\n        method: GET\n        description: Google Cloud Load Balancing List health\
  \ checks\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-forwardingrules\n      path: /projects/{project}/global/forwardingRules\n      operations:\n      - name: listforwardingrules\n        method: GET\n        description: Google Cloud Load Balancing List forwarding rules\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-global-urlmaps\n      path: /projects/{project}/global/urlMaps\n      operations:\n      - name: listurlmaps\n        method: GET\n        description: Google Cloud Load Balancing List URL maps\n        inputParameters:\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-load-balancing-rest\n    description: REST adapter for Google Cloud Load Balancing API.\n    resources:\n    - path: /projects/{project}/global/backendServices\n      name: listbackendservices\n      operations:\n      - method: GET\n        name: listbackendservices\n        description: Google Cloud Load Balancing List backend services\n        call: google-cloud-load-balancing.listbackendservices\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices\n      name: createbackendservice\n      operations:\n      - method: POST\n        name: createbackendservice\n        description:\
  \ Google Cloud Load Balancing Create a backend service\n        call: google-cloud-load-balancing.createbackendservice\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices/{backendService}\n      name: getbackendservice\n      operations:\n      - method: GET\n        name: getbackendservice\n        description: Google Cloud Load Balancing Get a backend service\n        call: google-cloud-load-balancing.getbackendservice\n        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/backendServices/{backendService}\n      name: deletebackendservice\n      operations:\n      - method: DELETE\n        name: deletebackendservice\n        description: Google Cloud Load Balancing Delete a backend service\n        call: google-cloud-load-balancing.deletebackendservice\n\
  \        with:\n          project: rest.project\n          backendService: rest.backendService\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/healthChecks\n      name: listhealthchecks\n      operations:\n      - method: GET\n        name: listhealthchecks\n        description: Google Cloud Load Balancing List health checks\n        call: google-cloud-load-balancing.listhealthchecks\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project}/global/forwardingRules\n      name: listforwardingrules\n      operations:\n      - method: GET\n        name: listforwardingrules\n        description: Google Cloud Load Balancing List forwarding rules\n        call: google-cloud-load-balancing.listforwardingrules\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /projects/{project}/global/urlMaps\n      name: listurlmaps\n      operations:\n      - method: GET\n        name: listurlmaps\n        description: Google Cloud Load Balancing List URL maps\n        call: google-cloud-load-balancing.listurlmaps\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-load-balancing-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Load Balancing API for AI agent use.\n    tools:\n    - name: listbackendservices\n      description: Google Cloud Load Balancing List backend services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-load-balancing.listbackendservices\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: Project ID for this request\n   \
  \     required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbackendservice\n      description: Google Cloud Load Balancing Create a backend service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-load-balancing.createbackendservice\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbackendservice\n      description: Google Cloud Load Balancing Get a backend service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-load-balancing.getbackendservice\n      with:\n        project: tools.project\n        backendService: tools.backendService\n      inputParameters:\n      - name: project\n        type: string\n\
  \        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebackendservice\n      description: Google Cloud Load Balancing Delete a backend service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-load-balancing.deletebackendservice\n      with:\n        project: tools.project\n        backendService: tools.backendService\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: backendService\n        type: string\n        description: backendService\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listhealthchecks\n      description: Google Cloud Load Balancing List health checks\n      hints:\n\
  \        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-load-balancing.listhealthchecks\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listforwardingrules\n      description: Google Cloud Load Balancing List forwarding rules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-load-balancing.listforwardingrules\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listurlmaps\n      description: Google Cloud Load Balancing List URL maps\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: google-cloud-load-balancing.listurlmaps\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_LOAD_BALANCING_TOKEN: GOOGLE_CLOUD_LOAD_BALANCING_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-load-balancing/refs/heads/main/capabilities/google-cloud-load-balancing-capability.yaml
tags:
- Google
- Cloud
- Load
- Balancing
- API
tools:
- description: Google Cloud Load Balancing List backend services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbackendservices
- description: Google Cloud Load Balancing Create a backend service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbackendservice
- description: Google Cloud Load Balancing Get a backend service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbackendservice
- description: Google Cloud Load Balancing Delete a backend service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebackendservice
- description: Google Cloud Load Balancing List health checks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listhealthchecks
- description: Google Cloud Load Balancing List forwarding rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listforwardingrules
- description: Google Cloud Load Balancing List URL maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listurlmaps
---
