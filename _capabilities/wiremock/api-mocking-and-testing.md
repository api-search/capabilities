---
categories: []
consumed_apis: []
description: Unified capability for API mocking and integration testing workflows using WireMock. Enables developers and QA engineers to create, manage, and verify mock API stubs; record and replay real traffic; debug unmatched requests; and manage stateful test scenarios — all through a single orchestrated interface.
layout: capability
name: WireMock API Mocking and Testing
operations:
- description: List all registered stub mappings.
  method: GET
  name: list-stub-mappings
  path: /v1/mappings
- description: Register a new stub mapping to mock an API endpoint.
  method: POST
  name: create-stub-mapping
  path: /v1/mappings
- description: Remove all stub mappings.
  method: DELETE
  name: delete-all-stub-mappings
  path: /v1/mappings
- description: Get a stub mapping by UUID.
  method: GET
  name: get-stub-mapping
  path: /v1/mappings/{stubMappingId}
- description: Update a stub mapping.
  method: PUT
  name: update-stub-mapping
  path: /v1/mappings/{stubMappingId}
- description: Delete a stub mapping.
  method: DELETE
  name: delete-stub-mapping
  path: /v1/mappings/{stubMappingId}
- description: List all requests logged in the journal.
  method: GET
  name: list-requests
  path: /v1/requests
- description: Clear the request journal.
  method: DELETE
  name: delete-all-requests
  path: /v1/requests
- description: Get a specific logged request by UUID.
  method: GET
  name: get-request
  path: /v1/requests/{requestId}
- description: Get requests that didn't match any stub.
  method: GET
  name: get-unmatched-requests
  path: /v1/requests/unmatched
- description: List all scenarios and their current state.
  method: GET
  name: list-scenarios
  path: /v1/scenarios
- description: Get the current recording status.
  method: GET
  name: get-recording-status
  path: /v1/recordings/status
personas: []
provider_name: WireMock
provider_slug: wiremock
search_terms:
- create stub mapping
- stubs
- find requests
- integration testing
- update stub mapping
- wiremock
- find stub mappings by metadata
- access a specific logged request.
- remove all stub mappings.
- find logged requests closest to matching a specific request pattern.
- list stub mappings
- get a specific stub mapping by its uuid to inspect its request/response configuration.
- remove a specific stub mapping by uuid.
- find stub mappings that match specific metadata criteria.
- list all registered stub mappings. use this to see what api endpoints are currently mocked.
- api mocking
- get recording status
- find near misses for request
- get the current recording status.
- mock server
- get a specific logged request by uuid.
- manage stateful test scenarios.
- find stub mappings that are closest to matching a specific request — helps debug near misses.
- list scenarios
- find near misses for pattern
- delete all stub mappings
- list requests
- get requests that did not match any stub mapping — useful for debugging missing stubs.
- count requests
- stop recording
- check whether wiremock is currently recording (neverstarted, recording, or stopped).
- list all requests logged in the request journal since the last reset.
- take snapshot
- update settings
- get requests that didn't match any stub.
- mocking
- manage a specific stub mapping.
- find logged requests matching specific url and method criteria.
- list all stateful scenarios and their current state for stateful mock testing.
- register a new stub mapping to mock an api endpoint.
- reset all
- get a stub mapping by uuid.
- get request
- check recording status.
- start recording real api traffic as stub mappings from a target base url.
- import a batch of stub mappings from a json definition.
- start recording
- get unmatched requests
- update global wiremock server settings such as fixed response delay.
- reset all stub mappings and the request journal to clean default state.
- list all scenarios and their current state.
- delete all requests
- update an existing stub mapping to change its request matcher or response.
- import stub mappings
- list all registered stub mappings.
- testing
- list all requests logged in the journal.
- count how many requests matching specific criteria were received.
- platform
- stop recording and retrieve the captured stub mappings.
- delete stub mapping
- access the request journal.
- update a stub mapping.
- take a snapshot of current request traffic as stub mappings.
- reset all scenario states back to their initial state.
- create a new stub mapping to mock an api endpoint with a specific request pattern and response.
- create and manage stub mappings that define mock api behavior.
- delete a stub mapping.
- reset scenarios
- clear the request journal.
- get stub mapping
- inspect unmatched requests for debugging.
slug: api-mocking-and-testing
source_filename: api-mocking-and-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WireMock API Mocking and Testing\n  description: Unified capability for API mocking and integration testing workflows using WireMock. Enables developers and\n    QA engineers to create, manage, and verify mock API stubs; record and replay real traffic; debug unmatched requests; and\n    manage stateful test scenarios — all through a single orchestrated interface.\n  tags:\n  - API Mocking\n  - Integration Testing\n  - Mock Server\n  - Stubs\n  - Testing\n  - WireMock\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WIREMOCK_BASE_URL: WIREMOCK_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: wiremock-admin\n    baseUri: '{{env.WIREMOCK_BASE_URL}}'\n    description: WireMock Admin REST API for managing mock server state.\n    resources:\n    - name: stub-mappings\n      path: /__admin/mappings\n      description: Manage stub mappings that define mock API behavior.\n      operations:\n\
  \      - name: list-stub-mappings\n        method: GET\n        description: Get All Stub Mappings\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Start index of results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-stub-mapping\n        method: POST\n        description: Create a New Stub Mapping\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            request: '{{tools.request}}'\n            response: '{{tools.response}}'\n      - name: delete-all-stub-mappings\n        method: DELETE\n        description:\
  \ Delete All Stub Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stub-mapping-by-id\n      path: /__admin/mappings/{stubMappingId}\n      description: Operations on a specific stub mapping by UUID.\n      operations:\n      - name: get-stub-mapping\n        method: GET\n        description: Get Stub Mapping by ID\n        inputParameters:\n        - name: stubMappingId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the stub mapping.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-stub-mapping\n        method: PUT\n        description: Update a Stub Mapping\n        inputParameters:\n        - name: stubMappingId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the stub mapping.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            request: '{{tools.request}}'\n            response: '{{tools.response}}'\n      - name: delete-stub-mapping\n        method: DELETE\n        description: Delete a Stub Mapping\n        inputParameters:\n        - name: stubMappingId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the stub mapping.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stub-mappings-reset\n      path: /__admin/mappings/reset\n      description: Reset stub mappings to defaults.\n      operations:\n      - name: reset-stub-mappings\n        method: POST\n        description: Reset Stub Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: stub-mappings-save\n      path: /__admin/mappings/save\n      description: Persist stub mappings to the backing store.\n      operations:\n      - name: save-stub-mappings\n        method: POST\n        description: Persist Stub Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stub-mappings-import\n      path: /__admin/mappings/import\n      description: Import stub mappings.\n      operations:\n      - name: import-stub-mappings\n        method: POST\n        description: Import Stub Mappings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            mappings: '{{tools.mappings}}'\n    - name: stub-mappings-find-by-metadata\n      path: /__admin/mappings/find-by-metadata\n      description: Find stubs\
  \ by matching on their metadata.\n      operations:\n      - name: find-stub-mappings-by-metadata\n        method: POST\n        description: Find Stub Mappings by Metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            matchesJsonPath: '{{tools.matchesJsonPath}}'\n    - name: requests\n      path: /__admin/requests\n      description: Access logged requests and responses in the request journal.\n      operations:\n      - name: list-requests\n        method: GET\n        description: Get All Requests in Journal\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n          required: false\n          description: Maximum number of results to return.\n        - name: since\n          in: query\n          type: string\n          required: false\n          description: Only return requests after this date\
  \ (ISO 8601).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-all-requests\n        method: DELETE\n        description: Delete All Requests in Journal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: request-by-id\n      path: /__admin/requests/{requestId}\n      description: Operations on a specific logged request.\n      operations:\n      - name: get-request\n        method: GET\n        description: Get Request by ID\n        inputParameters:\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the logged request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-request\n        method: DELETE\n        description:\
  \ Delete Request by ID\n        inputParameters:\n        - name: requestId\n          in: path\n          type: string\n          required: true\n          description: The UUID of the logged request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: requests-find\n      path: /__admin/requests/find\n      description: Find requests matching specified criteria.\n      operations:\n      - name: find-requests\n        method: POST\n        description: Find Requests by Criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            method: '{{tools.method}}'\n    - name: requests-count\n      path: /__admin/requests/count\n      description: Count requests matching specified criteria.\n      operations:\n      - name: count-requests\n\
  \        method: POST\n        description: Count Requests by Criteria\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            method: '{{tools.method}}'\n    - name: requests-unmatched\n      path: /__admin/requests/unmatched\n      description: Get requests that weren't matched by any stub mapping.\n      operations:\n      - name: get-unmatched-requests\n        method: GET\n        description: Find Unmatched Requests\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: near-misses-request\n      path: /__admin/near-misses/request\n      description: Find near misses for closest stub mappings.\n      operations:\n      - name: find-near-misses-for-request\n        method: POST\n        description: Find Near Misses Matching Specific\
  \ Request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            method: '{{tools.method}}'\n    - name: near-misses-request-pattern\n      path: /__admin/near-misses/request-pattern\n      description: Find near misses for closest logged requests to a pattern.\n      operations:\n      - name: find-near-misses-for-pattern\n        method: POST\n        description: Find Near Misses Matching Request Pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            urlPattern: '{{tools.urlPattern}}'\n            method: '{{tools.method}}'\n    - name: recordings-start\n      path: /__admin/recordings/start\n      description: Begin recording stub mappings from live traffic.\n      operations:\n\
  \      - name: start-recording\n        method: POST\n        description: Start Recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetBaseUrl: '{{tools.targetBaseUrl}}'\n    - name: recordings-stop\n      path: /__admin/recordings/stop\n      description: End recording of stub mappings.\n      operations:\n      - name: stop-recording\n        method: POST\n        description: Stop Recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recordings-status\n      path: /__admin/recordings/status\n      description: Get the current recording status.\n      operations:\n      - name: get-recording-status\n        method: GET\n        description: Get Recording Status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: recordings-snapshot\n      path: /__admin/recordings/snapshot\n      description: Take a snapshot recording of current state.\n      operations:\n      - name: take-snapshot\n        method: POST\n        description: Take a Snapshot Recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetBaseUrl: '{{tools.targetBaseUrl}}'\n    - name: scenarios\n      path: /__admin/scenarios\n      description: Manage stateful scenarios.\n      operations:\n      - name: list-scenarios\n        method: GET\n        description: Get All Scenarios\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scenarios-reset\n      path: /__admin/scenarios/reset\n      description: Reset state of all scenarios.\n     \
  \ operations:\n      - name: reset-scenarios\n        method: POST\n        description: Reset the State of All Scenarios\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: settings\n      path: /__admin/settings\n      description: Configure global WireMock settings.\n      operations:\n      - name: update-settings\n        method: POST\n        description: Update Global Settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fixedDelay: '{{tools.fixedDelay}}'\n    - name: system-reset\n      path: /__admin/reset\n      description: Reset mappings and request journal.\n      operations:\n      - name: reset-all\n        method: POST\n        description: Reset Mappings and Request Journal\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: system-shutdown\n      path: /__admin/shutdown\n      description: Shutdown the WireMock server.\n      operations:\n      - name: shutdown-server\n        method: POST\n        description: Shutdown the WireMock Server\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: wiremock-mocking-api\n    description: Unified REST API for WireMock API mocking and integration testing.\n    resources:\n    - path: /v1/mappings\n      name: stub-mappings\n      description: Create and manage stub mappings that define mock API behavior.\n      operations:\n      - method: GET\n        name: list-stub-mappings\n        description: List all registered stub mappings.\n        call: wiremock-admin.list-stub-mappings\n        with:\n          limit: rest.limit\n          offset: rest.offset\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-stub-mapping\n        description: Register a new stub mapping to mock an API endpoint.\n        call: wiremock-admin.create-stub-mapping\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-all-stub-mappings\n        description: Remove all stub mappings.\n        call: wiremock-admin.delete-all-stub-mappings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mappings/{stubMappingId}\n      name: stub-mapping\n      description: Manage a specific stub mapping.\n      operations:\n      - method: GET\n        name: get-stub-mapping\n        description: Get a stub mapping by UUID.\n        call: wiremock-admin.get-stub-mapping\n        with:\n          stubMappingId: rest.stubMappingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    \
  \  - method: PUT\n        name: update-stub-mapping\n        description: Update a stub mapping.\n        call: wiremock-admin.update-stub-mapping\n        with:\n          stubMappingId: rest.stubMappingId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-stub-mapping\n        description: Delete a stub mapping.\n        call: wiremock-admin.delete-stub-mapping\n        with:\n          stubMappingId: rest.stubMappingId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests\n      name: requests\n      description: Access the request journal.\n      operations:\n      - method: GET\n        name: list-requests\n        description: List all requests logged in the journal.\n        call: wiremock-admin.list-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-all-requests\n        description: Clear\
  \ the request journal.\n        call: wiremock-admin.delete-all-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests/{requestId}\n      name: request\n      description: Access a specific logged request.\n      operations:\n      - method: GET\n        name: get-request\n        description: Get a specific logged request by UUID.\n        call: wiremock-admin.get-request\n        with:\n          requestId: rest.requestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/requests/unmatched\n      name: unmatched-requests\n      description: Inspect unmatched requests for debugging.\n      operations:\n      - method: GET\n        name: get-unmatched-requests\n        description: Get requests that didn't match any stub.\n        call: wiremock-admin.get-unmatched-requests\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scenarios\n      name: scenarios\n\
  \      description: Manage stateful test scenarios.\n      operations:\n      - method: GET\n        name: list-scenarios\n        description: List all scenarios and their current state.\n        call: wiremock-admin.list-scenarios\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings/status\n      name: recording-status\n      description: Check recording status.\n      operations:\n      - method: GET\n        name: get-recording-status\n        description: Get the current recording status.\n        call: wiremock-admin.get-recording-status\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: wiremock-mocking-mcp\n    transport: http\n    description: MCP server for AI-assisted API mocking, test stub management, and request verification.\n    tools:\n    - name: list-stub-mappings\n      description: List all registered stub mappings. Use this to see what API endpoints\
  \ are currently mocked.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wiremock-admin.list-stub-mappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-stub-mapping\n      description: Create a new stub mapping to mock an API endpoint with a specific request pattern and response.\n      hints:\n        readOnly: false\n        destructive: false\n      call: wiremock-admin.create-stub-mapping\n      with:\n        request: tools.request\n        response: tools.response\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-stub-mapping\n      description: Get a specific stub mapping by its UUID to inspect its request/response configuration.\n      hints:\n        readOnly: true\n      call: wiremock-admin.get-stub-mapping\n      with:\n        stubMappingId: tools.stubMappingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-stub-mapping\n      description:\
  \ Update an existing stub mapping to change its request matcher or response.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: wiremock-admin.update-stub-mapping\n      with:\n        stubMappingId: tools.stubMappingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-stub-mapping\n      description: Remove a specific stub mapping by UUID.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wiremock-admin.delete-stub-mapping\n      with:\n        stubMappingId: tools.stubMappingId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-stub-mappings\n      description: Import a batch of stub mappings from a JSON definition.\n      hints:\n        readOnly: false\n      call: wiremock-admin.import-stub-mappings\n      with:\n        mappings: tools.mappings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-stub-mappings-by-metadata\n\
  \      description: Find stub mappings that match specific metadata criteria.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wiremock-admin.find-stub-mappings-by-metadata\n      with:\n        matchesJsonPath: tools.matchesJsonPath\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-requests\n      description: List all requests logged in the request journal since the last reset.\n      hints:\n        readOnly: true\n      call: wiremock-admin.list-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-requests\n      description: Find logged requests matching specific URL and method criteria.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wiremock-admin.find-requests\n      with:\n        url: tools.url\n        method: tools.method\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: count-requests\n      description: Count how\
  \ many requests matching specific criteria were received.\n      hints:\n        readOnly: true\n      call: wiremock-admin.count-requests\n      with:\n        url: tools.url\n        method: tools.method\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-unmatched-requests\n      description: Get requests that did not match any stub mapping — useful for debugging missing stubs.\n      hints:\n        readOnly: true\n      call: wiremock-admin.get-unmatched-requests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-near-misses-for-request\n      description: Find stub mappings that are closest to matching a specific request — helps debug near misses.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wiremock-admin.find-near-misses-for-request\n      with:\n        url: tools.url\n        method: tools.method\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: find-near-misses-for-pattern\n\
  \      description: Find logged requests closest to matching a specific request pattern.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wiremock-admin.find-near-misses-for-pattern\n      with:\n        urlPattern: tools.urlPattern\n        method: tools.method\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-recording\n      description: Start recording real API traffic as stub mappings from a target base URL.\n      hints:\n        readOnly: false\n        destructive: false\n      call: wiremock-admin.start-recording\n      with:\n        targetBaseUrl: tools.targetBaseUrl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-recording\n      description: Stop recording and retrieve the captured stub mappings.\n      hints:\n        readOnly: false\n      call: wiremock-admin.stop-recording\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recording-status\n\
  \      description: Check whether WireMock is currently recording (NeverStarted, Recording, or Stopped).\n      hints:\n        readOnly: true\n      call: wiremock-admin.get-recording-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: take-snapshot\n      description: Take a snapshot of current request traffic as stub mappings.\n      hints:\n        readOnly: false\n      call: wiremock-admin.take-snapshot\n      with:\n        targetBaseUrl: tools.targetBaseUrl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-scenarios\n      description: List all stateful scenarios and their current state for stateful mock testing.\n      hints:\n        readOnly: true\n      call: wiremock-admin.list-scenarios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reset-scenarios\n      description: Reset all scenario states back to their initial state.\n      hints:\n        readOnly: false\n     \
  \   idempotent: true\n      call: wiremock-admin.reset-scenarios\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-settings\n      description: Update global WireMock server settings such as fixed response delay.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: wiremock-admin.update-settings\n      with:\n        fixedDelay: tools.fixedDelay\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reset-all\n      description: Reset all stub mappings and the request journal to clean default state.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: wiremock-admin.reset-all\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wiremock/refs/heads/main/capabilities/api-mocking-and-testing.yaml
tags:
- API Mocking
- Integration Testing
- Mock Server
- Stubs
- Testing
- WireMock
tools:
- description: List all registered stub mappings. Use this to see what API endpoints are currently mocked.
  hints:
    openWorld: true
    readOnly: true
  name: list-stub-mappings
- description: Create a new stub mapping to mock an API endpoint with a specific request pattern and response.
  hints:
    destructive: false
    readOnly: false
  name: create-stub-mapping
- description: Get a specific stub mapping by its UUID to inspect its request/response configuration.
  hints:
    readOnly: true
  name: get-stub-mapping
- description: Update an existing stub mapping to change its request matcher or response.
  hints:
    idempotent: true
    readOnly: false
  name: update-stub-mapping
- description: Remove a specific stub mapping by UUID.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-stub-mapping
- description: Import a batch of stub mappings from a JSON definition.
  hints:
    readOnly: false
  name: import-stub-mappings
- description: Find stub mappings that match specific metadata criteria.
  hints:
    openWorld: true
    readOnly: true
  name: find-stub-mappings-by-metadata
- description: List all requests logged in the request journal since the last reset.
  hints:
    readOnly: true
  name: list-requests
- description: Find logged requests matching specific URL and method criteria.
  hints:
    openWorld: true
    readOnly: true
  name: find-requests
- description: Count how many requests matching specific criteria were received.
  hints:
    readOnly: true
  name: count-requests
- description: Get requests that did not match any stub mapping — useful for debugging missing stubs.
  hints:
    readOnly: true
  name: get-unmatched-requests
- description: Find stub mappings that are closest to matching a specific request — helps debug near misses.
  hints:
    openWorld: true
    readOnly: true
  name: find-near-misses-for-request
- description: Find logged requests closest to matching a specific request pattern.
  hints:
    openWorld: true
    readOnly: true
  name: find-near-misses-for-pattern
- description: Start recording real API traffic as stub mappings from a target base URL.
  hints:
    destructive: false
    readOnly: false
  name: start-recording
- description: Stop recording and retrieve the captured stub mappings.
  hints:
    readOnly: false
  name: stop-recording
- description: Check whether WireMock is currently recording (NeverStarted, Recording, or Stopped).
  hints:
    readOnly: true
  name: get-recording-status
- description: Take a snapshot of current request traffic as stub mappings.
  hints:
    readOnly: false
  name: take-snapshot
- description: List all stateful scenarios and their current state for stateful mock testing.
  hints:
    readOnly: true
  name: list-scenarios
- description: Reset all scenario states back to their initial state.
  hints:
    idempotent: true
    readOnly: false
  name: reset-scenarios
- description: Update global WireMock server settings such as fixed response delay.
  hints:
    idempotent: true
    readOnly: false
  name: update-settings
- description: Reset all stub mappings and the request journal to clean default state.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: reset-all
---
