---
categories: []
consumed_apis: []
description: The Service Management API allows management of managed services used by Google Cloud Endpoints. It enables creating, configuring, and deploying API service configurations and managing service rollouts.
layout: capability
name: Google Cloud Endpoints Google Cloud Service Management API
operations:
- description: Google Cloud Endpoints List managed services
  method: GET
  name: listservices
  path: /v1/services
- description: Google Cloud Endpoints Create a managed service
  method: POST
  name: createservice
  path: /v1/services
- description: Google Cloud Endpoints Get a managed service
  method: GET
  name: getservice
  path: /v1/services/{serviceName}
- description: Google Cloud Endpoints Delete a managed service
  method: DELETE
  name: deleteservice
  path: /v1/services/{serviceName}
- description: Google Cloud Endpoints List service configurations
  method: GET
  name: listserviceconfigs
  path: /v1/services/{serviceName}/configs
- description: Google Cloud Endpoints Create a service configuration
  method: POST
  name: createserviceconfig
  path: /v1/services/{serviceName}/configs
- description: Google Cloud Endpoints List service rollouts
  method: GET
  name: listservicerollouts
  path: /v1/services/{serviceName}/rollouts
- description: Google Cloud Endpoints Create a service rollout
  method: POST
  name: createservicerollout
  path: /v1/services/{serviceName}/rollouts
personas: []
provider_name: Google Cloud Endpoints
provider_slug: google-cloud-endpoints
search_terms:
- getservice
- api
- authentication
- monitoring
- google cloud endpoints create a managed service
- api management
- listservicerollouts
- listserviceconfigs
- google
- createservicerollout
- google cloud endpoints list managed services
- api gateway
- google cloud endpoints create a service rollout
- google cloud endpoints list service rollouts
- google cloud endpoints get a managed service
- google cloud endpoints create a service configuration
- createserviceconfig
- rate limiting
- cloud
- endpoints
- google cloud endpoints delete a managed service
- google cloud endpoints list service configurations
- google cloud
- deleteservice
- createservice
- listservices
slug: google-cloud-endpoints-capability
source_filename: google-cloud-endpoints-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Endpoints Google Cloud Service Management API\n  description: The Service Management API allows management of managed services used by Google Cloud Endpoints. It enables\n    creating, configuring, and deploying API service configurations and managing service rollouts.\n  tags:\n  - Google\n  - Cloud\n  - Endpoints\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-endpoints\n    baseUri: https://servicemanagement.googleapis.com\n    description: Google Cloud Endpoints Google Cloud Service Management API HTTP API.\n    resources:\n    - name: v1-services\n      path: /v1/services\n      operations:\n      - name: listservices\n        method: GET\n        description: Google Cloud Endpoints List managed services\n        inputParameters:\n        - name: producerProjectId\n          in: query\n          type: string\n        - name: pageSize\n\
  \          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservice\n        method: POST\n        description: Google Cloud Endpoints Create a managed service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-services-servicename\n      path: /v1/services/{serviceName}\n      operations:\n      - name: getservice\n        method: GET\n        description: Google Cloud Endpoints Get a managed service\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteservice\n        method:\
  \ DELETE\n        description: Google Cloud Endpoints Delete a managed service\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-services-servicename-configs\n      path: /v1/services/{serviceName}/configs\n      operations:\n      - name: listserviceconfigs\n        method: GET\n        description: Google Cloud Endpoints List service configurations\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createserviceconfig\n        method: POST\n        description: Google Cloud Endpoints Create a service configuration\n        inputParameters:\n        - name: serviceName\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-services-servicename-rollouts\n      path: /v1/services/{serviceName}/rollouts\n      operations:\n      - name: listservicerollouts\n        method: GET\n        description: Google Cloud Endpoints List service rollouts\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservicerollout\n        method: POST\n        description: Google Cloud Endpoints Create a service rollout\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-endpoints-rest\n    description: REST adapter for Google Cloud Endpoints Google Cloud Service Management API.\n    resources:\n    - path: /v1/services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description: Google Cloud Endpoints List managed services\n        call: google-cloud-endpoints.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services\n      name: createservice\n      operations:\n      - method: POST\n        name: createservice\n        description: Google Cloud Endpoints Create a managed service\n        call: google-cloud-endpoints.createservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}\n      name: getservice\n      operations:\n      - method: GET\n\
  \        name: getservice\n        description: Google Cloud Endpoints Get a managed service\n        call: google-cloud-endpoints.getservice\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}\n      name: deleteservice\n      operations:\n      - method: DELETE\n        name: deleteservice\n        description: Google Cloud Endpoints Delete a managed service\n        call: google-cloud-endpoints.deleteservice\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}/configs\n      name: listserviceconfigs\n      operations:\n      - method: GET\n        name: listserviceconfigs\n        description: Google Cloud Endpoints List service configurations\n        call: google-cloud-endpoints.listserviceconfigs\n        with:\n          serviceName: rest.serviceName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}/configs\n      name: createserviceconfig\n      operations:\n      - method: POST\n        name: createserviceconfig\n        description: Google Cloud Endpoints Create a service configuration\n        call: google-cloud-endpoints.createserviceconfig\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}/rollouts\n      name: listservicerollouts\n      operations:\n      - method: GET\n        name: listservicerollouts\n        description: Google Cloud Endpoints List service rollouts\n        call: google-cloud-endpoints.listservicerollouts\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/services/{serviceName}/rollouts\n      name: createservicerollout\n      operations:\n\
  \      - method: POST\n        name: createservicerollout\n        description: Google Cloud Endpoints Create a service rollout\n        call: google-cloud-endpoints.createservicerollout\n        with:\n          serviceName: rest.serviceName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-endpoints-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Endpoints Google Cloud Service Management API for AI agent use.\n    tools:\n    - name: listservices\n      description: Google Cloud Endpoints List managed services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-endpoints.listservices\n      with:\n        producerProjectId: tools.producerProjectId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: producerProjectId\n        type: string\n        description:\
  \ producerProjectId\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservice\n      description: Google Cloud Endpoints Create a managed service\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-endpoints.createservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Google Cloud Endpoints Get a managed service\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-endpoints.getservice\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: deleteservice\n      description: Google Cloud Endpoints Delete a managed service\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-endpoints.deleteservice\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listserviceconfigs\n      description: Google Cloud Endpoints List service configurations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-endpoints.listserviceconfigs\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: createserviceconfig\n      description: Google Cloud Endpoints Create a service configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-endpoints.createserviceconfig\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservicerollouts\n      description: Google Cloud Endpoints List service rollouts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-endpoints.listservicerollouts\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: createservicerollout\n      description: Google Cloud Endpoints Create a service rollout\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-endpoints.createservicerollout\n      with:\n        serviceName: tools.serviceName\n      inputParameters:\n      - name: serviceName\n        type: string\n        description: serviceName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-endpoints/refs/heads/main/capabilities/google-cloud-endpoints-capability.yaml
tags:
- Google
- Cloud
- Endpoints
- API
tools:
- description: Google Cloud Endpoints List managed services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Google Cloud Endpoints Create a managed service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservice
- description: Google Cloud Endpoints Get a managed service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: Google Cloud Endpoints Delete a managed service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteservice
- description: Google Cloud Endpoints List service configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listserviceconfigs
- description: Google Cloud Endpoints Create a service configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createserviceconfig
- description: Google Cloud Endpoints List service rollouts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservicerollouts
- description: Google Cloud Endpoints Create a service rollout
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservicerollout
---
