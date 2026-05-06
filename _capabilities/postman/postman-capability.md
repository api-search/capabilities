---
categories: []
consumed_apis: []
description: 'The Postman APIs API enables you to manage your API definitions in Postman''s API Builder. You can create APIs, manage versions, add schemas (OpenAPI, GraphQL, etc.), and link collections, environments, mock servers, monitors, and documentation to your API definitions. ## Authentication All requests require an API key passed in the `x-api-key` header. ## Rate Limits Standard Postman API rate limits apply.'
layout: capability
name: Postman APIs API
operations:
- description: Postman Get all APIs
  method: GET
  name: getallapis
  path: /apis
- description: Postman Create an API
  method: POST
  name: createapi
  path: /apis
- description: Postman Get an API
  method: GET
  name: getapi
  path: /apis/{apiId}
- description: Postman Update an API
  method: PUT
  name: updateapi
  path: /apis/{apiId}
- description: Postman Delete an API
  method: DELETE
  name: deleteapi
  path: /apis/{apiId}
- description: Postman Get all API versions
  method: GET
  name: getapiversions
  path: /apis/{apiId}/versions
- description: Postman Create an API version
  method: POST
  name: createapiversion
  path: /apis/{apiId}/versions
- description: Postman Get an API version
  method: GET
  name: getapiversion
  path: /apis/{apiId}/versions/{versionId}
- description: Postman Update an API version
  method: PUT
  name: updateapiversion
  path: /apis/{apiId}/versions/{versionId}
- description: Postman Delete an API version
  method: DELETE
  name: deleteapiversion
  path: /apis/{apiId}/versions/{versionId}
- description: Postman Get all API schemas
  method: GET
  name: getapischemas
  path: /apis/{apiId}/schemas
- description: Postman Create an API schema
  method: POST
  name: createapischema
  path: /apis/{apiId}/schemas
- description: Postman Get an API schema
  method: GET
  name: getapischema
  path: /apis/{apiId}/schemas/{schemaId}
- description: Postman Get API schema files
  method: GET
  name: getapischemafiles
  path: /apis/{apiId}/schemas/{schemaId}/files
- description: Postman Get API comments
  method: GET
  name: getapicomments
  path: /apis/{apiId}/comments
- description: Postman Create an API comment
  method: POST
  name: createapicomment
  path: /apis/{apiId}/comments
personas: []
provider_name: Postman
provider_slug: postman
search_terms:
- postman create an api
- postman create an api schema
- environments
- network
- postman update an api
- createapicomment
- getapischemafiles
- postman get api schema files
- deleteapi
- postman get an api
- postman update an api version
- deleteapiversion
- workspaces
- postman create an api comment
- collaboration
- getapischemas
- getapiversions
- api development
- getallapis
- postman delete an api
- postman create an api version
- createapi
- api monitoring
- postman get an api schema
- postman get all api versions
- collections
- mcp
- postman get all apis
- postman get all api schemas
- postman get an api version
- api governance
- mocking
- postman
- api documentation
- getapiversion
- getapischema
- api
- discovery
- mock servers
- createapischema
- workflows
- postman get api comments
- createapiversion
- client
- testing
- getapicomments
- postman delete an api version
- platform
- api testing
- ai agent builder
- updateapiversion
- getapi
- clients
- updateapi
- automation
slug: postman-capability
source_filename: postman-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Postman APIs API\n  description: 'The Postman APIs API enables you to manage your API definitions in Postman''s API Builder. You can create\n    APIs, manage versions, add schemas (OpenAPI, GraphQL, etc.), and link collections, environments, mock servers, monitors,\n    and documentation to your API definitions. ## Authentication All requests require an API key passed in the `x-api-key`\n    header. ## Rate Limits Standard Postman API rate limits apply.'\n  tags:\n  - Postman\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: postman\n    baseUri: https://api.getpostman.com\n    description: Postman APIs API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{POSTMAN_TOKEN}}'\n    resources:\n    - name: apis\n      path: /apis\n      operations:\n      - name: getallapis\n        method: GET\n        description:\
  \ Postman Get all APIs\n        inputParameters:\n        - name: workspace\n          in: query\n          type: string\n          required: true\n          description: The workspace ID to get APIs from. Required.\n        - name: cursor\n          in: query\n          type: string\n          description: Pagination cursor.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: createdBy\n          in: query\n          type: integer\n          description: Filter by creator user ID.\n        - name: description\n          in: query\n          type: string\n          description: Filter by description text (partial match).\n        - name: name\n          in: query\n          type: string\n          description: Filter by API name (partial match).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapi\n\
  \        method: POST\n        description: Postman Create an API\n        inputParameters:\n        - name: workspace\n          in: query\n          type: string\n          required: true\n          description: The workspace ID to create the API in. Required.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid\n      path: /apis/{apiId}\n      operations:\n      - name: getapi\n        method: GET\n        description: Postman Get an API\n        inputParameters:\n        - name: include\n          in: query\n          type: array\n          description: Additional data to include in the response.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapi\n        method: PUT\n        description: Postman Update an API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deleteapi\n        method: DELETE\n        description: Postman Delete an API\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-versions\n      path: /apis/{apiId}/versions\n      operations:\n      - name: getapiversions\n        method: GET\n        description: Postman Get all API versions\n        inputParameters:\n        - name: cursor\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapiversion\n        method: POST\n        description: Postman Create an API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-versions-versionid\n\
  \      path: /apis/{apiId}/versions/{versionId}\n      operations:\n      - name: getapiversion\n        method: GET\n        description: Postman Get an API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapiversion\n        method: PUT\n        description: Postman Update an API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteapiversion\n        method: DELETE\n        description: Postman Delete an API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-schemas\n      path: /apis/{apiId}/schemas\n      operations:\n      - name: getapischemas\n        method: GET\n        description: Postman Get all API schemas\n        inputParameters:\n        - name: cursor\n  \
  \        in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapischema\n        method: POST\n        description: Postman Create an API schema\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-schemas-schemaid\n      path: /apis/{apiId}/schemas/{schemaId}\n      operations:\n      - name: getapischema\n        method: GET\n        description: Postman Get an API schema\n        inputParameters:\n        - name: schemaId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-schemas-schemaid-files\n      path: /apis/{apiId}/schemas/{schemaId}/files\n\
  \      operations:\n      - name: getapischemafiles\n        method: GET\n        description: Postman Get API schema files\n        inputParameters:\n        - name: schemaId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-apiid-comments\n      path: /apis/{apiId}/comments\n      operations:\n      - name: getapicomments\n        method: GET\n        description: Postman Get API comments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapicomment\n        method: POST\n        description: Postman Create an API comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: postman-rest\n    description:\
  \ REST adapter for Postman APIs API.\n    resources:\n    - path: /apis\n      name: getallapis\n      operations:\n      - method: GET\n        name: getallapis\n        description: Postman Get all APIs\n        call: postman.getallapis\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis\n      name: createapi\n      operations:\n      - method: POST\n        name: createapi\n        description: Postman Create an API\n        call: postman.createapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}\n      name: getapi\n      operations:\n      - method: GET\n        name: getapi\n        description: Postman Get an API\n        call: postman.getapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}\n      name: updateapi\n      operations:\n      - method: PUT\n        name: updateapi\n        description: Postman Update an API\n        call:\
  \ postman.updateapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}\n      name: deleteapi\n      operations:\n      - method: DELETE\n        name: deleteapi\n        description: Postman Delete an API\n        call: postman.deleteapi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/versions\n      name: getapiversions\n      operations:\n      - method: GET\n        name: getapiversions\n        description: Postman Get all API versions\n        call: postman.getapiversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/versions\n      name: createapiversion\n      operations:\n      - method: POST\n        name: createapiversion\n        description: Postman Create an API version\n        call: postman.createapiversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/versions/{versionId}\n\
  \      name: getapiversion\n      operations:\n      - method: GET\n        name: getapiversion\n        description: Postman Get an API version\n        call: postman.getapiversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/versions/{versionId}\n      name: updateapiversion\n      operations:\n      - method: PUT\n        name: updateapiversion\n        description: Postman Update an API version\n        call: postman.updateapiversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/versions/{versionId}\n      name: deleteapiversion\n      operations:\n      - method: DELETE\n        name: deleteapiversion\n        description: Postman Delete an API version\n        call: postman.deleteapiversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/schemas\n      name: getapischemas\n      operations:\n      - method: GET\n     \
  \   name: getapischemas\n        description: Postman Get all API schemas\n        call: postman.getapischemas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/schemas\n      name: createapischema\n      operations:\n      - method: POST\n        name: createapischema\n        description: Postman Create an API schema\n        call: postman.createapischema\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/schemas/{schemaId}\n      name: getapischema\n      operations:\n      - method: GET\n        name: getapischema\n        description: Postman Get an API schema\n        call: postman.getapischema\n        with:\n          schemaId: rest.schemaId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/schemas/{schemaId}/files\n      name: getapischemafiles\n      operations:\n      - method: GET\n        name: getapischemafiles\n        description:\
  \ Postman Get API schema files\n        call: postman.getapischemafiles\n        with:\n          schemaId: rest.schemaId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/comments\n      name: getapicomments\n      operations:\n      - method: GET\n        name: getapicomments\n        description: Postman Get API comments\n        call: postman.getapicomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/{apiId}/comments\n      name: createapicomment\n      operations:\n      - method: POST\n        name: createapicomment\n        description: Postman Create an API comment\n        call: postman.createapicomment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: postman-mcp\n    transport: http\n    description: MCP adapter for Postman APIs API for AI agent use.\n    tools:\n    - name: getallapis\n      description: Postman\
  \ Get all APIs\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getallapis\n      with:\n        workspace: tools.workspace\n        cursor: tools.cursor\n        limit: tools.limit\n        createdBy: tools.createdBy\n        description: tools.description\n        name: tools.name\n      inputParameters:\n      - name: workspace\n        type: string\n        description: The workspace ID to get APIs from. Required.\n        required: true\n      - name: cursor\n        type: string\n        description: Pagination cursor.\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      - name: createdBy\n        type: integer\n        description: Filter by creator user ID.\n      - name: description\n        type: string\n        description: Filter by description text (partial match).\n      - name: name\n        type: string\n        description: Filter by API name (partial\
  \ match).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapi\n      description: Postman Create an API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postman.createapi\n      with:\n        workspace: tools.workspace\n      inputParameters:\n      - name: workspace\n        type: string\n        description: The workspace ID to create the API in. Required.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapi\n      description: Postman Get an API\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapi\n      with:\n        include: tools.include\n      inputParameters:\n      - name: include\n        type: array\n        description: Additional data to include in the response.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapi\n\
  \      description: Postman Update an API\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: postman.updateapi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapi\n      description: Postman Delete an API\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: postman.deleteapi\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapiversions\n      description: Postman Get all API versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapiversions\n      with:\n        cursor: tools.cursor\n        limit: tools.limit\n      inputParameters:\n      - name: cursor\n        type: string\n        description: cursor\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: createapiversion\n      description: Postman Create an API version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postman.createapiversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapiversion\n      description: Postman Get an API version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapiversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapiversion\n      description: Postman Update an API version\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: postman.updateapiversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteapiversion\n      description: Postman Delete an API version\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: postman.deleteapiversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapischemas\n      description: Postman Get all API schemas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapischemas\n      with:\n        cursor: tools.cursor\n        limit: tools.limit\n      inputParameters:\n      - name: cursor\n        type: string\n        description: cursor\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapischema\n      description: Postman Create an API schema\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postman.createapischema\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapischema\n      description: Postman Get an API schema\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: postman.getapischema\n      with:\n        schemaId: tools.schemaId\n      inputParameters:\n      - name: schemaId\n        type: string\n        description: schemaId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapischemafiles\n      description: Postman Get API schema files\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapischemafiles\n      with:\n        schemaId: tools.schemaId\n      inputParameters:\n      - name: schemaId\n        type: string\n        description: schemaId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapicomments\n      description: Postman Get API comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: postman.getapicomments\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: createapicomment\n      description: Postman Create an API comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: postman.createapicomment\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    POSTMAN_TOKEN: POSTMAN_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/postman/refs/heads/main/capabilities/postman-capability.yaml
tags:
- Postman
- API
tools:
- description: Postman Get all APIs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallapis
- description: Postman Create an API
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapi
- description: Postman Get an API
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapi
- description: Postman Update an API
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapi
- description: Postman Delete an API
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapi
- description: Postman Get all API versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiversions
- description: Postman Create an API version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapiversion
- description: Postman Get an API version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapiversion
- description: Postman Update an API version
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateapiversion
- description: Postman Delete an API version
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapiversion
- description: Postman Get all API schemas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapischemas
- description: Postman Create an API schema
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapischema
- description: Postman Get an API schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapischema
- description: Postman Get API schema files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapischemafiles
- description: Postman Get API comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapicomments
- description: Postman Create an API comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapicomment
---
