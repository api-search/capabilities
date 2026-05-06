---
categories: []
consumed_apis: []
description: Workflow capability for Treblle API Intelligence Platform covering project management, request log analysis, performance analytics, endpoint discovery, and automated governance checking. Designed for API teams, DevOps engineers, and platform architects who need real-time API observability and governance.
layout: capability
name: Treblle API Observability
operations:
- description: List all API monitoring projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new API monitoring project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{projectId}
- description: List API request logs with filtering
  method: GET
  name: list-requests
  path: /v1/projects/{projectId}/requests
- description: Get full request/response details
  method: GET
  name: get-request
  path: /v1/projects/{projectId}/requests/{requestId}
- description: Get project analytics and metrics
  method: GET
  name: get-analytics
  path: /v1/projects/{projectId}/analytics
- description: List auto-discovered endpoints from live traffic
  method: GET
  name: list-endpoints
  path: /v1/projects/{projectId}/endpoints
- description: Run automated governance tests against an OpenAPI spec
  method: POST
  name: run-governance-check
  path: /v1/projects/{projectId}/governance
personas: []
provider_name: Treblle
provider_slug: treblle
search_terms:
- list auto-discovered endpoints from live traffic
- get project details
- get auto-discovered api endpoints detected from live traffic
- run governance check
- get or delete a specific project
- run automated governance tests against an openapi spec
- get full request/response details
- get api performance analytics including request counts, error rates, and response times
- create a new api monitoring project
- analytics
- manage api monitoring projects
- developer experience
- insights
- browse api request logs
- security
- api performance analytics
- monitoring
- run 30+ automated governance tests against an openapi specification, scoring design, security, and performance
- get request detail
- list requests
- list discovered endpoints
- get a specific api request detail
- documentation
- create project
- auto-discovered api endpoints
- get project analytics and metrics
- artificial intelligence
- api governance checks
- get analytics
- create a new treblle api monitoring project
- list all api monitoring projects
- get request
- observability
- get full details of a specific api request including headers, body, and errors
- get project
- list projects
- api intelligence
- list all treblle api monitoring projects in the workspace
- list endpoints
- testing
- platform
- get api analytics
- get api request logs with filtering by status code, date range, or search term
- governance
- list api request logs with filtering
- get details of a specific treblle monitoring project
slug: api-observability
source_filename: api-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Treblle API Observability\n  description: Workflow capability for Treblle API Intelligence Platform covering project management, request log analysis,\n    performance analytics, endpoint discovery, and automated governance checking. Designed for API teams, DevOps engineers,\n    and platform architects who need real-time API observability and governance.\n  tags:\n  - Analytics\n  - API Intelligence\n  - Developer Experience\n  - Governance\n  - Monitoring\n  - Observability\n  - Platform\n  - Security\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TREBLLE_API_KEY: TREBLLE_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: treblle\n    baseUri: https://app.treblle.com/api/v1\n    description: Treblle platform API for API intelligence, monitoring, and governance.\n    authentication:\n      type: apikey\n      key: Treblle-Api-Key\n      value: '{{TREBLLE_API_KEY}}'\n      placement:\
  \ header\n    resources:\n    - name: projects\n      path: /projects\n      description: Manage Treblle API monitoring projects\n      operations:\n      - name: list-projects\n        method: GET\n        description: Returns all API monitoring projects in the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-project\n        method: POST\n        description: Create a new API monitoring project\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            environment: '{{tools.environment}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: GET\n        description: Get details of a specific project\n        inputParameters:\n        - name: projectId\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-project\n        method: DELETE\n        description: Delete a project and all associated data\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requests\n      path: /projects/{projectId}/requests\n      description: Access API request logs\n      operations:\n      - name: list-requests\n        method: GET\n        description: Get paginated API request logs for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n          required:\
  \ false\n        - name: per_page\n          in: query\n          type: integer\n          required: false\n        - name: status_code\n          in: query\n          type: integer\n          required: false\n        - name: search\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-request\n        method: GET\n        description: Get full details of a specific API request\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: requestId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analytics\n      path: /projects/{projectId}/analytics\n      description: Access API performance\
  \ analytics\n      operations:\n      - name: get-analytics\n        method: GET\n        description: Get aggregated analytics including request counts, error rates, and response times\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: start_date\n          in: query\n          type: string\n          required: false\n        - name: end_date\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints\n      path: /projects/{projectId}/endpoints\n      description: Browse auto-discovered API endpoints\n      operations:\n      - name: list-endpoints\n        method: GET\n        description: Get auto-discovered endpoints from live traffic\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n  \
  \        required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: governance\n      path: /projects/{projectId}/governance\n      description: Run API governance checks\n      operations:\n      - name: run-governance-check\n        method: POST\n        description: Run 30+ automated governance tests against an OpenAPI specification\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            openapi_spec: '{{tools.openapi_spec}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: treblle-observability-api\n    description: Unified REST API for Treblle API observability and governance workflows.\n    resources:\n    - path: /v1/projects\n\
  \      name: projects\n      description: Manage API monitoring projects\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all API monitoring projects\n        call: treblle.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new API monitoring project\n        call: treblle.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: project\n      description: Get or delete a specific project\n      operations:\n      - method: GET\n        name: get-project\n        description: Get project details\n        call: treblle.get-project\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/requests\n      name: requests\n      description:\
  \ Browse API request logs\n      operations:\n      - method: GET\n        name: list-requests\n        description: List API request logs with filtering\n        call: treblle.list-requests\n        with:\n          projectId: rest.projectId\n          page: rest.page\n          per_page: rest.per_page\n          status_code: rest.status_code\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/requests/{requestId}\n      name: request\n      description: Get a specific API request detail\n      operations:\n      - method: GET\n        name: get-request\n        description: Get full request/response details\n        call: treblle.get-request\n        with:\n          projectId: rest.projectId\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/analytics\n      name: analytics\n      description: API\
  \ performance analytics\n      operations:\n      - method: GET\n        name: get-analytics\n        description: Get project analytics and metrics\n        call: treblle.get-analytics\n        with:\n          projectId: rest.projectId\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/endpoints\n      name: endpoints\n      description: Auto-discovered API endpoints\n      operations:\n      - method: GET\n        name: list-endpoints\n        description: List auto-discovered endpoints from live traffic\n        call: treblle.list-endpoints\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/governance\n      name: governance\n      description: API governance checks\n      operations:\n      - method: POST\n        name: run-governance-check\n\
  \        description: Run automated governance tests against an OpenAPI spec\n        call: treblle.run-governance-check\n        with:\n          projectId: rest.projectId\n          openapi_spec: rest.openapi_spec\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: treblle-observability-mcp\n    transport: http\n    description: MCP server for AI-assisted API observability and governance with Treblle.\n    tools:\n    - name: list-projects\n      description: List all Treblle API monitoring projects in the workspace\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Treblle API monitoring project\n      hints:\n        readOnly: false\n        openWorld: false\n      call: treblle.create-project\n      with:\n        name: tools.name\n      \
  \  description: tools.description\n        environment: tools.environment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project\n      description: Get details of a specific Treblle monitoring project\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.get-project\n      with:\n        projectId: tools.projectId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requests\n      description: Get API request logs with filtering by status code, date range, or search term\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.list-requests\n      with:\n        projectId: tools.projectId\n        page: tools.page\n        per_page: tools.per_page\n        status_code: tools.status_code\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-request-detail\n      description: Get full details of a\
  \ specific API request including headers, body, and errors\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.get-request\n      with:\n        projectId: tools.projectId\n        requestId: tools.requestId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-api-analytics\n      description: Get API performance analytics including request counts, error rates, and response times\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.get-analytics\n      with:\n        projectId: tools.projectId\n        start_date: tools.start_date\n        end_date: tools.end_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-discovered-endpoints\n      description: Get auto-discovered API endpoints detected from live traffic\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.list-endpoints\n      with:\n        projectId: tools.projectId\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-governance-check\n      description: Run 30+ automated governance tests against an OpenAPI specification, scoring design, security, and performance\n      hints:\n        readOnly: true\n        openWorld: false\n      call: treblle.run-governance-check\n      with:\n        projectId: tools.projectId\n        openapi_spec: tools.openapi_spec\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/treblle/refs/heads/main/capabilities/api-observability.yaml
tags:
- Analytics
- API Intelligence
- Developer Experience
- Governance
- Monitoring
- Observability
- Platform
- Security
tools:
- description: List all Treblle API monitoring projects in the workspace
  hints:
    openWorld: false
    readOnly: true
  name: list-projects
- description: Create a new Treblle API monitoring project
  hints:
    openWorld: false
    readOnly: false
  name: create-project
- description: Get details of a specific Treblle monitoring project
  hints:
    openWorld: false
    readOnly: true
  name: get-project
- description: Get API request logs with filtering by status code, date range, or search term
  hints:
    openWorld: false
    readOnly: true
  name: list-requests
- description: Get full details of a specific API request including headers, body, and errors
  hints:
    openWorld: false
    readOnly: true
  name: get-request-detail
- description: Get API performance analytics including request counts, error rates, and response times
  hints:
    openWorld: false
    readOnly: true
  name: get-api-analytics
- description: Get auto-discovered API endpoints detected from live traffic
  hints:
    openWorld: false
    readOnly: true
  name: list-discovered-endpoints
- description: Run 30+ automated governance tests against an OpenAPI specification, scoring design, security, and performance
  hints:
    openWorld: false
    readOnly: true
  name: run-governance-check
---
