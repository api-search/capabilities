---
categories:
- crm-sales
consumed_apis:
- ofbiz
description: Workflow capability for ERP and business process automation using Apache OFBiz REST API. Covers authentication, service discovery, and invocation of OFBiz services for ERP, CRM, e-commerce, and supply chain operations. Intended for ERP administrators and integration engineers.
layout: capability
name: Apache OFBiz ERP Operations
operations:
- description: Authenticate and obtain JWT token.
  method: POST
  name: get-token
  path: /v1/auth/token
- description: Refresh an expired access token.
  method: POST
  name: refresh-token
  path: /v1/auth/refresh
- description: List all exported OFBiz REST services.
  method: GET
  name: list-services
  path: /v1/services
- description: Invoke OFBiz service via GET with query parameters.
  method: GET
  name: invoke-service-get
  path: /v1/services/{serviceName}
- description: Invoke OFBiz service via POST with JSON body.
  method: POST
  name: invoke-service-post
  path: /v1/services/{serviceName}
personas: []
provider_name: Apache OFBiz
provider_slug: apache-ofbiz
search_terms:
- refresh an expired access token.
- refresh auth token
- invoke ofbiz service via post with json body.
- java
- invoke service post
- get token
- authenticate to apache ofbiz and obtain a jwt access token for subsequent api calls.
- invoke an ofbiz rest service via post method. used for write operations like creating orders, updating inventory, and processing payments.
- authenticate and obtain jwt token.
- crm
- administrators who configure and manage ofbiz erp modules and business processes.
- refresh jwt access tokens.
- invoke ofbiz service via get with query parameters.
- supply chain
- e-commerce
- integrated management of core business processes including finance, hr, supply chain, and manufacturing.
- invoke an ofbiz rest service via get method. useful for read-only service calls like product lookups, order queries, and data retrieval.
- list all ofbiz services exported via the rest plugin for discovery.
- refresh token
- business applications
- ofbiz service discovery.
- list services
- obtain jwt access tokens for api authentication.
- list all exported ofbiz rest services.
- get auth token
- apache ofbiz
- invoke ofbiz services by name.
- refresh an expired ofbiz jwt access token using a refresh token.
- end-to-end erp workflow covering authentication and ofbiz service invocation.
- ERP Administrator
- invoke service get
- Integration Engineer
- automated execution of ofbiz business logic services via rest api calls.
- apache
- engineers integrating external systems with ofbiz via the rest api.
- open source
- erp
slug: apache-ofbiz-erp-operations
source_filename: apache-ofbiz-erp-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Apache OFBiz ERP Operations\n  description: Workflow capability for ERP and business process automation using Apache OFBiz REST API. Covers authentication, service discovery, and invocation of OFBiz services for ERP, CRM, e-commerce, and supply chain operations. Intended for ERP administrators and integration engineers.\n  tags:\n    - Apache OFBiz\n    - ERP\n    - CRM\n    - E-Commerce\n    - Business Applications\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      OFBIZ_USERNAME: OFBIZ_USERNAME\n      OFBIZ_PASSWORD: OFBIZ_PASSWORD\n      OFBIZ_TOKEN: OFBIZ_TOKEN\n\ncapability:\n  consumes:\n    - import: ofbiz\n      location: ./shared/apache-ofbiz.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ofbiz-erp-api\n      description: Unified REST API for Apache OFBiz ERP operations.\n      resources:\n        - path: /v1/auth/token\n          name: auth-token\n\
  \          description: Obtain JWT access tokens for API authentication.\n          operations:\n            - method: POST\n              name: get-token\n              description: Authenticate and obtain JWT token.\n              call: \"ofbiz.get-token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/auth/refresh\n          name: auth-refresh\n          description: Refresh JWT access tokens.\n          operations:\n            - method: POST\n              name: refresh-token\n              description: Refresh an expired access token.\n              call: \"ofbiz.refresh-token\"\n              with:\n                refreshToken: \"rest.refresh_token\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services\n          name: services\n          description: OFBiz service discovery.\n          operations:\n            - method: GET\n\
  \              name: list-services\n              description: List all exported OFBiz REST services.\n              call: \"ofbiz.get-services\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/services/{serviceName}\n          name: service-invoke\n          description: Invoke OFBiz services by name.\n          operations:\n            - method: GET\n              name: invoke-service-get\n              description: Invoke OFBiz service via GET with query parameters.\n              call: \"ofbiz.invoke-service-get\"\n              with:\n                serviceName: \"rest.serviceName\"\n                inParams: \"rest.inParams\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: invoke-service-post\n              description: Invoke OFBiz service via POST with JSON body.\n              call: \"ofbiz.invoke-service-post\"\
  \n              with:\n                serviceName: \"rest.serviceName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ofbiz-erp-mcp\n      transport: http\n      description: MCP server for AI-assisted Apache OFBiz ERP operations.\n      tools:\n        - name: get-auth-token\n          description: Authenticate to Apache OFBiz and obtain a JWT access token for subsequent API calls.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"ofbiz.get-token\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: refresh-auth-token\n          description: Refresh an expired OFBiz JWT access token using a refresh token.\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"ofbiz.refresh-token\"\n          with:\n            refreshToken: \"tools.refreshToken\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-services\n          description: List all OFBiz services exported via the REST plugin for discovery.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ofbiz.get-services\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: invoke-service-get\n          description: Invoke an OFBiz REST service via GET method. Useful for read-only service calls like product lookups, order queries, and data retrieval.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ofbiz.invoke-service-get\"\n          with:\n            serviceName: \"tools.serviceName\"\n            inParams: \"tools.inParams\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: invoke-service-post\n          description: Invoke\
  \ an OFBiz REST service via POST method. Used for write operations like creating orders, updating inventory, and processing payments.\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"ofbiz.invoke-service-post\"\n          with:\n            serviceName: \"tools.serviceName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-ofbiz/refs/heads/main/capabilities/apache-ofbiz-erp-operations.yaml
tags:
- Apache OFBiz
- ERP
- CRM
- E-Commerce
- Business Applications
tools:
- description: Authenticate to Apache OFBiz and obtain a JWT access token for subsequent API calls.
  hints:
    openWorld: false
    readOnly: false
  name: get-auth-token
- description: Refresh an expired OFBiz JWT access token using a refresh token.
  hints:
    openWorld: false
    readOnly: false
  name: refresh-auth-token
- description: List all OFBiz services exported via the REST plugin for discovery.
  hints:
    openWorld: false
    readOnly: true
  name: list-services
- description: Invoke an OFBiz REST service via GET method. Useful for read-only service calls like product lookups, order queries, and data retrieval.
  hints:
    openWorld: true
    readOnly: true
  name: invoke-service-get
- description: Invoke an OFBiz REST service via POST method. Used for write operations like creating orders, updating inventory, and processing payments.
  hints:
    openWorld: true
    readOnly: false
  name: invoke-service-post
---
