---
categories: []
consumed_apis: []
description: The API Gateway API enables creation and management of API gateways, API configurations, and APIs. It provides secure access to serverless backend services through well-defined REST APIs described using OpenAPI specifications.
layout: capability
name: Google Cloud API Gateway API
operations:
- description: Google Cloud API Gateway List gateways
  method: GET
  name: listgateways
  path: /v1/projects/{project}/locations/{location}/gateways
- description: Google Cloud API Gateway Create a gateway
  method: POST
  name: creategateway
  path: /v1/projects/{project}/locations/{location}/gateways
- description: Google Cloud API Gateway Get a gateway
  method: GET
  name: getgateway
  path: /v1/projects/{project}/locations/{location}/gateways/{gateway}
- description: Google Cloud API Gateway Update a gateway
  method: PATCH
  name: updategateway
  path: /v1/projects/{project}/locations/{location}/gateways/{gateway}
- description: Google Cloud API Gateway Delete a gateway
  method: DELETE
  name: deletegateway
  path: /v1/projects/{project}/locations/{location}/gateways/{gateway}
- description: Google Cloud API Gateway List APIs
  method: GET
  name: listapis
  path: /v1/projects/{project}/locations/global/apis
- description: Google Cloud API Gateway Create an API
  method: POST
  name: createapi
  path: /v1/projects/{project}/locations/global/apis
- description: Google Cloud API Gateway Get an API
  method: GET
  name: getapi
  path: /v1/projects/{project}/locations/global/apis/{api}
- description: Google Cloud API Gateway Delete an API
  method: DELETE
  name: deleteapi
  path: /v1/projects/{project}/locations/global/apis/{api}
- description: Google Cloud API Gateway List API configurations
  method: GET
  name: listapiconfigs
  path: /v1/projects/{project}/locations/global/apis/{api}/configs
- description: Google Cloud API Gateway Create an API configuration
  method: POST
  name: createapiconfig
  path: /v1/projects/{project}/locations/global/apis/{api}/configs
personas: []
provider_name: Google Cloud API Gateway
provider_slug: google-cloud-api-gateway
search_terms:
- google cloud api gateway list apis
- google cloud api gateway get an api
- listapis
- updategateway
- google cloud api gateway create a gateway
- deleteapi
- gateway
- serverless
- cloud
- google
- google cloud api gateway update a gateway
- security
- createapi
- google cloud api gateway delete an api
- deletegateway
- listgateways
- google cloud api gateway list gateways
- api
- google cloud api gateway create an api configuration
- authentication
- api gateway
- api management
- creategateway
- google cloud api gateway delete a gateway
- google cloud api gateway list api configurations
- getapi
- createapiconfig
- getgateway
- google cloud api gateway get a gateway
- google cloud api gateway create an api
- google cloud
- listapiconfigs
slug: google-cloud-api-gateway-capability
source_filename: google-cloud-api-gateway-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud API Gateway API\n  description: The API Gateway API enables creation and management of API gateways, API configurations, and APIs. It provides\n    secure access to serverless backend services through well-defined REST APIs described using OpenAPI specifications.\n  tags:\n  - Google\n  - Cloud\n  - Api\n  - Gateway\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-api-gateway\n    baseUri: https://apigateway.googleapis.com\n    description: Google Cloud API Gateway API HTTP API.\n    resources:\n    - name: v1-projects-project-locations-location-gateways\n      path: /v1/projects/{project}/locations/{location}/gateways\n      operations:\n      - name: listgateways\n        method: GET\n        description: Google Cloud API Gateway List gateways\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n \
  \         required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategateway\n        method: POST\n        description: Google Cloud API Gateway Create a gateway\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: gatewayId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-location-gateways-\n      path: /v1/projects/{project}/locations/{location}/gateways/{gateway}\n      operations:\n      - name: getgateway\n        method: GET\n        description:\
  \ Google Cloud API Gateway Get a gateway\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: gateway\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updategateway\n        method: PATCH\n        description: Google Cloud API Gateway Update a gateway\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: gateway\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n      - name: deletegateway\n        method: DELETE\n        description: Google Cloud API Gateway Delete a gateway\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: gateway\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-global-apis\n      path: /v1/projects/{project}/locations/global/apis\n      operations:\n      - name: listapis\n        method: GET\n        description: Google Cloud API Gateway List APIs\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createapi\n        method: POST\n        description: Google Cloud API Gateway Create an API\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: apiId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-global-apis-api\n      path: /v1/projects/{project}/locations/global/apis/{api}\n      operations:\n      - name: getapi\n        method: GET\n        description: Google Cloud API Gateway Get an API\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleteapi\n        method: DELETE\n        description: Google Cloud API Gateway Delete an API\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-project-locations-global-apis-api-co\n      path: /v1/projects/{project}/locations/global/apis/{api}/configs\n      operations:\n      - name: listapiconfigs\n        method: GET\n        description: Google Cloud API Gateway List API configurations\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapiconfig\n        method: POST\n        description: Google Cloud API Gateway Create an API configuration\n        inputParameters:\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: api\n          in: path\n          type: string\n          required: true\n        - name: apiConfigId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-api-gateway-rest\n    description: REST adapter for Google Cloud API Gateway API.\n    resources:\n    - path: /v1/projects/{project}/locations/{location}/gateways\n      name: listgateways\n      operations:\n      - method: GET\n        name: listgateways\n\
  \        description: Google Cloud API Gateway List gateways\n        call: google-cloud-api-gateway.listgateways\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/gateways\n      name: creategateway\n      operations:\n      - method: POST\n        name: creategateway\n        description: Google Cloud API Gateway Create a gateway\n        call: google-cloud-api-gateway.creategateway\n        with:\n          project: rest.project\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/gateways/{gateway}\n      name: getgateway\n      operations:\n      - method: GET\n        name: getgateway\n        description: Google Cloud API Gateway Get a gateway\n        call: google-cloud-api-gateway.getgateway\n        with:\n\
  \          project: rest.project\n          location: rest.location\n          gateway: rest.gateway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/gateways/{gateway}\n      name: updategateway\n      operations:\n      - method: PATCH\n        name: updategateway\n        description: Google Cloud API Gateway Update a gateway\n        call: google-cloud-api-gateway.updategateway\n        with:\n          project: rest.project\n          location: rest.location\n          gateway: rest.gateway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/{location}/gateways/{gateway}\n      name: deletegateway\n      operations:\n      - method: DELETE\n        name: deletegateway\n        description: Google Cloud API Gateway Delete a gateway\n        call: google-cloud-api-gateway.deletegateway\n        with:\n          project: rest.project\n\
  \          location: rest.location\n          gateway: rest.gateway\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis\n      name: listapis\n      operations:\n      - method: GET\n        name: listapis\n        description: Google Cloud API Gateway List APIs\n        call: google-cloud-api-gateway.listapis\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis\n      name: createapi\n      operations:\n      - method: POST\n        name: createapi\n        description: Google Cloud API Gateway Create an API\n        call: google-cloud-api-gateway.createapi\n        with:\n          project: rest.project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis/{api}\n      name: getapi\n      operations:\n \
  \     - method: GET\n        name: getapi\n        description: Google Cloud API Gateway Get an API\n        call: google-cloud-api-gateway.getapi\n        with:\n          project: rest.project\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis/{api}\n      name: deleteapi\n      operations:\n      - method: DELETE\n        name: deleteapi\n        description: Google Cloud API Gateway Delete an API\n        call: google-cloud-api-gateway.deleteapi\n        with:\n          project: rest.project\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis/{api}/configs\n      name: listapiconfigs\n      operations:\n      - method: GET\n        name: listapiconfigs\n        description: Google Cloud API Gateway List API configurations\n        call: google-cloud-api-gateway.listapiconfigs\n\
  \        with:\n          project: rest.project\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project}/locations/global/apis/{api}/configs\n      name: createapiconfig\n      operations:\n      - method: POST\n        name: createapiconfig\n        description: Google Cloud API Gateway Create an API configuration\n        call: google-cloud-api-gateway.createapiconfig\n        with:\n          project: rest.project\n          api: rest.api\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-api-gateway-mcp\n    transport: http\n    description: MCP adapter for Google Cloud API Gateway API for AI agent use.\n    tools:\n    - name: listgateways\n      description: Google Cloud API Gateway List gateways\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-api-gateway.listgateways\n\
  \      with:\n        project: tools.project\n        location: tools.location\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: creategateway\n      description: Google Cloud API Gateway Create a gateway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-api-gateway.creategateway\n      with:\n        project: tools.project\n        location: tools.location\n        gatewayId: tools.gatewayId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: gatewayId\n        type: string\n      \
  \  description: gatewayId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgateway\n      description: Google Cloud API Gateway Get a gateway\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-api-gateway.getgateway\n      with:\n        project: tools.project\n        location: tools.location\n        gateway: tools.gateway\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: gateway\n        type: string\n        description: gateway\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updategateway\n      description: Google Cloud API Gateway Update a gateway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: google-cloud-api-gateway.updategateway\n      with:\n        project: tools.project\n        location: tools.location\n        gateway: tools.gateway\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: gateway\n        type: string\n        description: gateway\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletegateway\n      description: Google Cloud API Gateway Delete a gateway\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-api-gateway.deletegateway\n      with:\n        project: tools.project\n        location: tools.location\n        gateway: tools.gateway\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n \
  \       required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: gateway\n        type: string\n        description: gateway\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapis\n      description: Google Cloud API Gateway List APIs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-api-gateway.listapis\n      with:\n        project: tools.project\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapi\n      description: Google Cloud API Gateway Create an API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-api-gateway.createapi\n      with:\n        project: tools.project\n\
  \        apiId: tools.apiId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: apiId\n        type: string\n        description: apiId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapi\n      description: Google Cloud API Gateway Get an API\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-api-gateway.getapi\n      with:\n        project: tools.project\n        api: tools.api\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapi\n      description: Google Cloud API Gateway Delete an API\n      hints:\n        readOnly: false\n        destructive: true\n\
  \        idempotent: true\n      call: google-cloud-api-gateway.deleteapi\n      with:\n        project: tools.project\n        api: tools.api\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapiconfigs\n      description: Google Cloud API Gateway List API configurations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-api-gateway.listapiconfigs\n      with:\n        project: tools.project\n        api: tools.api\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: createapiconfig\n      description: Google Cloud API Gateway Create an API configuration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-api-gateway.createapiconfig\n      with:\n        project: tools.project\n        api: tools.api\n        apiConfigId: tools.apiConfigId\n      inputParameters:\n      - name: project\n        type: string\n        description: project\n        required: true\n      - name: api\n        type: string\n        description: api\n        required: true\n      - name: apiConfigId\n        type: string\n        description: apiConfigId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-api-gateway/refs/heads/main/capabilities/google-cloud-api-gateway-capability.yaml
tags:
- Google
- Cloud
- Api
- Gateway
- API
tools:
- description: Google Cloud API Gateway List gateways
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgateways
- description: Google Cloud API Gateway Create a gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategateway
- description: Google Cloud API Gateway Get a gateway
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgateway
- description: Google Cloud API Gateway Update a gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategateway
- description: Google Cloud API Gateway Delete a gateway
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegateway
- description: Google Cloud API Gateway List APIs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapis
- description: Google Cloud API Gateway Create an API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapi
- description: Google Cloud API Gateway Get an API
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapi
- description: Google Cloud API Gateway Delete an API
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapi
- description: Google Cloud API Gateway List API configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapiconfigs
- description: Google Cloud API Gateway Create an API configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapiconfig
---
