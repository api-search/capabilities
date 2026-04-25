---
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
- refresh auth token
- administrators who configure and manage ofbiz erp modules and business processes.
- invoke service post
- crm
- invoke an ofbiz rest service via get method. useful for read-only service calls like product lookups, order queries, and data retrieval.
- invoke ofbiz service via get with query parameters.
- refresh jwt access tokens.
- obtain jwt access tokens for api authentication.
- invoke ofbiz service via post with json body.
- ERP Administrator
- refresh an expired access token.
- apache ofbiz
- get token
- engineers integrating external systems with ofbiz via the rest api.
- apache
- authenticate and obtain jwt token.
- get auth token
- invoke service get
- ofbiz service discovery.
- list all exported ofbiz rest services.
- supply chain
- refresh an expired ofbiz jwt access token using a refresh token.
- e-commerce
- refresh token
- integrated management of core business processes including finance, hr, supply chain, and manufacturing.
- list services
- business applications
- end-to-end erp workflow covering authentication and ofbiz service invocation.
- open source
- invoke ofbiz services by name.
- java
- erp
- list all ofbiz services exported via the rest plugin for discovery.
- authenticate to apache ofbiz and obtain a jwt access token for subsequent api calls.
- invoke an ofbiz rest service via post method. used for write operations like creating orders, updating inventory, and processing payments.
- Integration Engineer
- automated execution of ofbiz business logic services via rest api calls.
slug: apache-ofbiz-erp-operations
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
