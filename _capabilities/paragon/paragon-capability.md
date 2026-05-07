---
categories: []
consumed_apis: []
description: The Proxy API allows you to directly access any of the third-party provider's API methods on behalf of your Connected Users. Along with Workflows, the Proxy API is one of two primary ways to build integrations with Paragon. The Proxy API accepts requests with body contents specified as application/json and supports any HTTP verb including GET, POST, PUT, PATCH, and DELETE.
layout: capability
name: Paragon Proxy API
operations:
- description: Paragon Proxy GET request to integration
  method: GET
  name: proxygetrequest
  path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}
- description: Paragon Proxy POST request to integration
  method: POST
  name: proxypostrequest
  path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}
- description: Paragon Proxy PUT request to integration
  method: PUT
  name: proxyputrequest
  path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}
- description: Paragon Proxy PATCH request to integration
  method: PATCH
  name: proxypatchrequest
  path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}
- description: Paragon Proxy DELETE request to integration
  method: DELETE
  name: proxydeleterequest
  path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}
- description: Paragon Proxy GET request to custom integration
  method: GET
  name: proxycustomgetrequest
  path: /projects/{projectId}/sdk/proxy/custom/{integrationId}/{apiPath}
- description: Paragon Proxy POST request to custom integration
  method: POST
  name: proxycustompostrequest
  path: /projects/{projectId}/sdk/proxy/custom/{integrationId}/{apiPath}
personas: []
provider_name: Paragon
provider_slug: paragon
search_terms:
- embedded ipaas
- paragon proxy put request to integration
- paragon
- integrations
- proxygetrequest
- paragon proxy post request to integration
- proxypatchrequest
- proxycustompostrequest
- paragon proxy delete request to integration
- proxycustomgetrequest
- paragon proxy get request to integration
- paragon proxy post request to custom integration
- proxyputrequest
- proxypostrequest
- api
- proxydeleterequest
- paragon proxy get request to custom integration
- paragon proxy patch request to integration
slug: paragon-capability
source_filename: paragon-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Paragon Proxy API\n  description: The Proxy API allows you to directly access any of the third-party provider's API methods on behalf of your\n    Connected Users. Along with Workflows, the Proxy API is one of two primary ways to build integrations with Paragon. The\n    Proxy API accepts requests with body contents specified as application/json and supports any HTTP verb including GET,\n    POST, PUT, PATCH, and DELETE.\n  tags:\n  - Paragon\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: paragon\n    baseUri: https://proxy.useparagon.com\n    description: Paragon Proxy API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PARAGON_TOKEN}}'\n    resources:\n    - name: projects-projectid-sdk-proxy-integrationtype-api\n      path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      operations:\n      - name: proxygetrequest\n        method:\
  \ GET\n        description: Paragon Proxy GET request to integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationType\n          in: path\n          type: string\n          required: true\n          description: The type of integration to proxy the request to (e.g., salesforce, hubspot, slack).\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the third-party provider to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxypostrequest\n        method: POST\n        description: Paragon Proxy POST request to integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \          description: Your Paragon Project ID.\n        - name: integrationType\n          in: path\n          type: string\n          required: true\n          description: The type of integration to proxy the request to.\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the third-party provider to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxyputrequest\n        method: PUT\n        description: Paragon Proxy PUT request to integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationType\n          in: path\n          type: string\n          required: true\n          description: The type of integration to proxy the request to.\n\
  \        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the third-party provider to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxypatchrequest\n        method: PATCH\n        description: Paragon Proxy PATCH request to integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationType\n          in: path\n          type: string\n          required: true\n          description: The type of integration to proxy the request to.\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the third-party provider to send the request to.\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxydeleterequest\n        method: DELETE\n        description: Paragon Proxy DELETE request to integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationType\n          in: path\n          type: string\n          required: true\n          description: The type of integration to proxy the request to.\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the third-party provider to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-sdk-proxy-custom-integrationi\n      path: /projects/{projectId}/sdk/proxy/custom/{integrationId}/{apiPath}\n\
  \      operations:\n      - name: proxycustomgetrequest\n        method: GET\n        description: Paragon Proxy GET request to custom integration\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: The ID of the custom integration.\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the custom integration to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: proxycustompostrequest\n        method: POST\n        description: Paragon Proxy POST request to custom integration\n        inputParameters:\n        - name: projectId\n          in: path\n       \
  \   type: string\n          required: true\n          description: Your Paragon Project ID.\n        - name: integrationId\n          in: path\n          type: string\n          required: true\n          description: The ID of the custom integration.\n        - name: apiPath\n          in: path\n          type: string\n          required: true\n          description: The API path of the custom integration to send the request to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: paragon-rest\n    description: REST adapter for Paragon Proxy API.\n    resources:\n    - path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      name: proxygetrequest\n      operations:\n      - method: GET\n        name: proxygetrequest\n        description: Paragon Proxy GET request to integration\n        call: paragon.proxygetrequest\n        with:\n     \
  \     projectId: rest.projectId\n          integrationType: rest.integrationType\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      name: proxypostrequest\n      operations:\n      - method: POST\n        name: proxypostrequest\n        description: Paragon Proxy POST request to integration\n        call: paragon.proxypostrequest\n        with:\n          projectId: rest.projectId\n          integrationType: rest.integrationType\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      name: proxyputrequest\n      operations:\n      - method: PUT\n        name: proxyputrequest\n        description: Paragon Proxy PUT request to integration\n        call: paragon.proxyputrequest\n        with:\n          projectId: rest.projectId\n\
  \          integrationType: rest.integrationType\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      name: proxypatchrequest\n      operations:\n      - method: PATCH\n        name: proxypatchrequest\n        description: Paragon Proxy PATCH request to integration\n        call: paragon.proxypatchrequest\n        with:\n          projectId: rest.projectId\n          integrationType: rest.integrationType\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/{integrationType}/{apiPath}\n      name: proxydeleterequest\n      operations:\n      - method: DELETE\n        name: proxydeleterequest\n        description: Paragon Proxy DELETE request to integration\n        call: paragon.proxydeleterequest\n        with:\n          projectId: rest.projectId\n       \
  \   integrationType: rest.integrationType\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/custom/{integrationId}/{apiPath}\n      name: proxycustomgetrequest\n      operations:\n      - method: GET\n        name: proxycustomgetrequest\n        description: Paragon Proxy GET request to custom integration\n        call: paragon.proxycustomgetrequest\n        with:\n          projectId: rest.projectId\n          integrationId: rest.integrationId\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/sdk/proxy/custom/{integrationId}/{apiPath}\n      name: proxycustompostrequest\n      operations:\n      - method: POST\n        name: proxycustompostrequest\n        description: Paragon Proxy POST request to custom integration\n        call: paragon.proxycustompostrequest\n        with:\n          projectId:\
  \ rest.projectId\n          integrationId: rest.integrationId\n          apiPath: rest.apiPath\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: paragon-mcp\n    transport: http\n    description: MCP adapter for Paragon Proxy API for AI agent use.\n    tools:\n    - name: proxygetrequest\n      description: Paragon Proxy GET request to integration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paragon.proxygetrequest\n      with:\n        projectId: tools.projectId\n        integrationType: tools.integrationType\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationType\n        type: string\n        description: The type of integration to proxy the request to (e.g., salesforce, hubspot, slack).\n        required: true\n\
  \      - name: apiPath\n        type: string\n        description: The API path of the third-party provider to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxypostrequest\n      description: Paragon Proxy POST request to integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paragon.proxypostrequest\n      with:\n        projectId: tools.projectId\n        integrationType: tools.integrationType\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationType\n        type: string\n        description: The type of integration to proxy the request to.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the third-party provider to send the request to.\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxyputrequest\n      description: Paragon Proxy PUT request to integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: paragon.proxyputrequest\n      with:\n        projectId: tools.projectId\n        integrationType: tools.integrationType\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationType\n        type: string\n        description: The type of integration to proxy the request to.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the third-party provider to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxypatchrequest\n      description:\
  \ Paragon Proxy PATCH request to integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paragon.proxypatchrequest\n      with:\n        projectId: tools.projectId\n        integrationType: tools.integrationType\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationType\n        type: string\n        description: The type of integration to proxy the request to.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the third-party provider to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxydeleterequest\n      description: Paragon Proxy DELETE request to integration\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: paragon.proxydeleterequest\n      with:\n        projectId: tools.projectId\n        integrationType: tools.integrationType\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationType\n        type: string\n        description: The type of integration to proxy the request to.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the third-party provider to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxycustomgetrequest\n      description: Paragon Proxy GET request to custom integration\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: paragon.proxycustomgetrequest\n      with:\n        projectId: tools.projectId\n        integrationId:\
  \ tools.integrationId\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description: Your Paragon Project ID.\n        required: true\n      - name: integrationId\n        type: string\n        description: The ID of the custom integration.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the custom integration to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: proxycustompostrequest\n      description: Paragon Proxy POST request to custom integration\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: paragon.proxycustompostrequest\n      with:\n        projectId: tools.projectId\n        integrationId: tools.integrationId\n        apiPath: tools.apiPath\n      inputParameters:\n      - name: projectId\n        type: string\n        description:\
  \ Your Paragon Project ID.\n        required: true\n      - name: integrationId\n        type: string\n        description: The ID of the custom integration.\n        required: true\n      - name: apiPath\n        type: string\n        description: The API path of the custom integration to send the request to.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PARAGON_TOKEN: PARAGON_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/paragon/refs/heads/main/capabilities/paragon-capability.yaml
tags:
- Paragon
- API
tools:
- description: Paragon Proxy GET request to integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: proxygetrequest
- description: Paragon Proxy POST request to integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxypostrequest
- description: Paragon Proxy PUT request to integration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: proxyputrequest
- description: Paragon Proxy PATCH request to integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxypatchrequest
- description: Paragon Proxy DELETE request to integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: proxydeleterequest
- description: Paragon Proxy GET request to custom integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: proxycustomgetrequest
- description: Paragon Proxy POST request to custom integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: proxycustompostrequest
---
