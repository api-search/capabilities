---
categories: []
consumed_apis:
- wiremock-admin
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
- check recording status.
- list all registered stub mappings. use this to see what api endpoints are currently mocked.
- reset all
- list scenarios
- get a specific logged request by uuid.
- reset all stub mappings and the request journal to clean default state.
- find logged requests closest to matching a specific request pattern.
- import a batch of stub mappings from a json definition.
- update settings
- count how many requests matching specific criteria were received.
- get a stub mapping by uuid.
- mock server
- remove all stub mappings.
- list all scenarios and their current state.
- list all requests logged in the request journal since the last reset.
- start recording
- get requests that didn't match any stub.
- stop recording and retrieve the captured stub mappings.
- manage a specific stub mapping.
- get unmatched requests
- access a specific logged request.
- list all stateful scenarios and their current state for stateful mock testing.
- list requests
- take a snapshot of current request traffic as stub mappings.
- get request
- update stub mapping
- take snapshot
- register a new stub mapping to mock an api endpoint.
- check whether wiremock is currently recording (neverstarted, recording, or stopped).
- stubs
- find logged requests matching specific url and method criteria.
- get stub mapping
- stop recording
- create and manage stub mappings that define mock api behavior.
- list stub mappings
- delete all requests
- find stub mappings by metadata
- reset all scenario states back to their initial state.
- create stub mapping
- inspect unmatched requests for debugging.
- count requests
- reset scenarios
- delete stub mapping
- get a specific stub mapping by its uuid to inspect its request/response configuration.
- manage stateful test scenarios.
- update an existing stub mapping to change its request matcher or response.
- get the current recording status.
- get recording status
- list all registered stub mappings.
- delete a stub mapping.
- api mocking
- create a new stub mapping to mock an api endpoint with a specific request pattern and response.
- remove a specific stub mapping by uuid.
- update global wiremock server settings such as fixed response delay.
- start recording real api traffic as stub mappings from a target base url.
- integration testing
- access the request journal.
- find requests
- wiremock
- find near misses for request
- find stub mappings that are closest to matching a specific request — helps debug near misses.
- mocking
- clear the request journal.
- platform
- delete all stub mappings
- get requests that did not match any stub mapping — useful for debugging missing stubs.
- find stub mappings that match specific metadata criteria.
- list all requests logged in the journal.
- import stub mappings
- testing
- update a stub mapping.
- find near misses for pattern
slug: api-mocking-and-testing
source_filename: api-mocking-and-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"WireMock API Mocking and Testing\"\n  description: >-\n    Unified capability for API mocking and integration testing workflows using\n    WireMock. Enables developers and QA engineers to create, manage, and verify\n    mock API stubs; record and replay real traffic; debug unmatched requests;\n    and manage stateful test scenarios — all through a single orchestrated interface.\n  tags:\n    - API Mocking\n    - Integration Testing\n    - Mock Server\n    - Stubs\n    - Testing\n    - WireMock\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WIREMOCK_BASE_URL: WIREMOCK_BASE_URL\n\ncapability:\n  consumes:\n    - import: wiremock-admin\n      location: ./shared/wiremock-admin.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: wiremock-mocking-api\n      description: \"Unified REST API for WireMock API mocking and integration testing.\"\n      resources:\n\
  \        - path: /v1/mappings\n          name: stub-mappings\n          description: \"Create and manage stub mappings that define mock API behavior.\"\n          operations:\n            - method: GET\n              name: list-stub-mappings\n              description: \"List all registered stub mappings.\"\n              call: \"wiremock-admin.list-stub-mappings\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-stub-mapping\n              description: \"Register a new stub mapping to mock an API endpoint.\"\n              call: \"wiremock-admin.create-stub-mapping\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-all-stub-mappings\n              description: \"Remove all\
  \ stub mappings.\"\n              call: \"wiremock-admin.delete-all-stub-mappings\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/mappings/{stubMappingId}\n          name: stub-mapping\n          description: \"Manage a specific stub mapping.\"\n          operations:\n            - method: GET\n              name: get-stub-mapping\n              description: \"Get a stub mapping by UUID.\"\n              call: \"wiremock-admin.get-stub-mapping\"\n              with:\n                stubMappingId: \"rest.stubMappingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-stub-mapping\n              description: \"Update a stub mapping.\"\n              call: \"wiremock-admin.update-stub-mapping\"\n              with:\n                stubMappingId: \"rest.stubMappingId\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-stub-mapping\n              description: \"Delete a stub mapping.\"\n              call: \"wiremock-admin.delete-stub-mapping\"\n              with:\n                stubMappingId: \"rest.stubMappingId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/requests\n          name: requests\n          description: \"Access the request journal.\"\n          operations:\n            - method: GET\n              name: list-requests\n              description: \"List all requests logged in the journal.\"\n              call: \"wiremock-admin.list-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-all-requests\n              description: \"Clear the request journal.\"\n              call:\
  \ \"wiremock-admin.delete-all-requests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/requests/{requestId}\n          name: request\n          description: \"Access a specific logged request.\"\n          operations:\n            - method: GET\n              name: get-request\n              description: \"Get a specific logged request by UUID.\"\n              call: \"wiremock-admin.get-request\"\n              with:\n                requestId: \"rest.requestId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/requests/unmatched\n          name: unmatched-requests\n          description: \"Inspect unmatched requests for debugging.\"\n          operations:\n            - method: GET\n              name: get-unmatched-requests\n              description: \"Get requests that didn't match any stub.\"\n              call: \"wiremock-admin.get-unmatched-requests\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/scenarios\n          name: scenarios\n          description: \"Manage stateful test scenarios.\"\n          operations:\n            - method: GET\n              name: list-scenarios\n              description: \"List all scenarios and their current state.\"\n              call: \"wiremock-admin.list-scenarios\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recordings/status\n          name: recording-status\n          description: \"Check recording status.\"\n          operations:\n            - method: GET\n              name: get-recording-status\n              description: \"Get the current recording status.\"\n              call: \"wiremock-admin.get-recording-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n\
  \      port: 9090\n      namespace: wiremock-mocking-mcp\n      transport: http\n      description: \"MCP server for AI-assisted API mocking, test stub management, and request verification.\"\n      tools:\n        - name: list-stub-mappings\n          description: \"List all registered stub mappings. Use this to see what API endpoints are currently mocked.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wiremock-admin.list-stub-mappings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-stub-mapping\n          description: \"Create a new stub mapping to mock an API endpoint with a specific request pattern and response.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"wiremock-admin.create-stub-mapping\"\n          with:\n            request: \"tools.request\"\n            response: \"tools.response\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-stub-mapping\n          description: \"Get a specific stub mapping by its UUID to inspect its request/response configuration.\"\n          hints:\n            readOnly: true\n          call: \"wiremock-admin.get-stub-mapping\"\n          with:\n            stubMappingId: \"tools.stubMappingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-stub-mapping\n          description: \"Update an existing stub mapping to change its request matcher or response.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wiremock-admin.update-stub-mapping\"\n          with:\n            stubMappingId: \"tools.stubMappingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-stub-mapping\n          description: \"Remove a specific stub mapping by UUID.\"\
  \n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wiremock-admin.delete-stub-mapping\"\n          with:\n            stubMappingId: \"tools.stubMappingId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: import-stub-mappings\n          description: \"Import a batch of stub mappings from a JSON definition.\"\n          hints:\n            readOnly: false\n          call: \"wiremock-admin.import-stub-mappings\"\n          with:\n            mappings: \"tools.mappings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-stub-mappings-by-metadata\n          description: \"Find stub mappings that match specific metadata criteria.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wiremock-admin.find-stub-mappings-by-metadata\"\n          with:\n      \
  \      matchesJsonPath: \"tools.matchesJsonPath\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-requests\n          description: \"List all requests logged in the request journal since the last reset.\"\n          hints:\n            readOnly: true\n          call: \"wiremock-admin.list-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-requests\n          description: \"Find logged requests matching specific URL and method criteria.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wiremock-admin.find-requests\"\n          with:\n            url: \"tools.url\"\n            method: \"tools.method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: count-requests\n          description: \"Count how many requests matching specific criteria were received.\"\
  \n          hints:\n            readOnly: true\n          call: \"wiremock-admin.count-requests\"\n          with:\n            url: \"tools.url\"\n            method: \"tools.method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-unmatched-requests\n          description: \"Get requests that did not match any stub mapping — useful for debugging missing stubs.\"\n          hints:\n            readOnly: true\n          call: \"wiremock-admin.get-unmatched-requests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-near-misses-for-request\n          description: \"Find stub mappings that are closest to matching a specific request — helps debug near misses.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wiremock-admin.find-near-misses-for-request\"\n          with:\n            url: \"tools.url\"\n            method:\
  \ \"tools.method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: find-near-misses-for-pattern\n          description: \"Find logged requests closest to matching a specific request pattern.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"wiremock-admin.find-near-misses-for-pattern\"\n          with:\n            urlPattern: \"tools.urlPattern\"\n            method: \"tools.method\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-recording\n          description: \"Start recording real API traffic as stub mappings from a target base URL.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"wiremock-admin.start-recording\"\n          with:\n            targetBaseUrl: \"tools.targetBaseUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: stop-recording\n          description: \"Stop recording and retrieve the captured stub mappings.\"\n          hints:\n            readOnly: false\n          call: \"wiremock-admin.stop-recording\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-recording-status\n          description: \"Check whether WireMock is currently recording (NeverStarted, Recording, or Stopped).\"\n          hints:\n            readOnly: true\n          call: \"wiremock-admin.get-recording-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: take-snapshot\n          description: \"Take a snapshot of current request traffic as stub mappings.\"\n          hints:\n            readOnly: false\n          call: \"wiremock-admin.take-snapshot\"\n          with:\n            targetBaseUrl: \"tools.targetBaseUrl\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: list-scenarios\n          description: \"List all stateful scenarios and their current state for stateful mock testing.\"\n          hints:\n            readOnly: true\n          call: \"wiremock-admin.list-scenarios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reset-scenarios\n          description: \"Reset all scenario states back to their initial state.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wiremock-admin.reset-scenarios\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-settings\n          description: \"Update global WireMock server settings such as fixed response delay.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"wiremock-admin.update-settings\"\n          with:\n            fixedDelay: \"tools.fixedDelay\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: reset-all\n          description: \"Reset all stub mappings and the request journal to clean default state.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"wiremock-admin.reset-all\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
