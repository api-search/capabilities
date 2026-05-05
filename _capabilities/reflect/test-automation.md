---
api_specs:
- filename: reflect-openapi.yml
  format: yaml
  label: reflect
  slug: reflect
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/reflect/refs/heads/main/openapi/reflect-openapi.yml
categories: []
consumed_apis:
- reflect
description: Workflow capability for QA engineers and DevOps teams managing and executing automated end-to-end tests through the Reflect API. Supports listing available tests, triggering test runs with parameter overrides, and monitoring execution status for CI/CD pipeline integration.
layout: capability
name: Reflect Test Automation
operations:
- description: List all automated end-to-end tests.
  method: GET
  name: list-tests
  path: /v1/tests
- description: Trigger a test run.
  method: POST
  name: run-test
  path: /v1/tests/{testId}/executions
- description: Check test execution status.
  method: GET
  name: get-execution-status
  path: /v1/executions/{executionId}
personas: []
provider_name: Reflect
provider_slug: reflect
search_terms:
- available tests catalog.
- trigger a test run.
- test execution triggers.
- get execution status
- reflect
- list all automated end-to-end tests.
- ai testing
- list all automated end-to-end tests available in the reflect account.
- artificial intelligence
- automated testing
- end-to-end testing
- ci/cd
- check the current status of a reflect test execution and retrieve per-test results.
- testing
- check test execution status.
- end-to-end tests
- qa
- automation
- run test
- list tests
- test execution status.
- trigger a reflect automated test execution, with optional overrides for target hostnames, parameters, cookies, headers, and session storage.
slug: test-automation
source_filename: test-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Reflect Test Automation\"\n  description: >-\n    Workflow capability for QA engineers and DevOps teams managing and\n    executing automated end-to-end tests through the Reflect API. Supports\n    listing available tests, triggering test runs with parameter overrides,\n    and monitoring execution status for CI/CD pipeline integration.\n  tags:\n    - Reflect\n    - Testing\n    - Automation\n    - CI/CD\n    - End-to-End Tests\n    - QA\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      REFLECT_API_KEY: REFLECT_API_KEY\n\ncapability:\n  consumes:\n    - import: reflect\n      location: ./shared/reflect.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: reflect-automation-api\n      description: \"Unified REST API for Reflect test automation workflows.\"\n      resources:\n        - path: /v1/tests\n          name: tests\n          description: \"Available\
  \ tests catalog.\"\n          operations:\n            - method: GET\n              name: list-tests\n              description: \"List all automated end-to-end tests.\"\n              call: \"reflect.list-tests\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/tests/{testId}/executions\n          name: test-runs\n          description: \"Test execution triggers.\"\n          operations:\n            - method: POST\n              name: run-test\n              description: \"Trigger a test run.\"\n              call: \"reflect.run-test\"\n              with:\n                test-id: \"rest.testId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/executions/{executionId}\n          name: executions\n          description: \"Test execution status.\"\n          operations:\n            - method: GET\n              name: get-execution-status\n\
  \              description: \"Check test execution status.\"\n              call: \"reflect.get-execution-status\"\n              with:\n                execution-id: \"rest.executionId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: reflect-automation-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Reflect test automation.\"\n      tools:\n        - name: list-tests\n          description: \"List all automated end-to-end tests available in the Reflect account.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reflect.list-tests\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: run-test\n          description: \"Trigger a Reflect automated test execution, with optional overrides for target hostnames, parameters, cookies, headers, and session storage.\"\
  \n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"reflect.run-test\"\n          with:\n            test-id: \"tools.testId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-execution-status\n          description: \"Check the current status of a Reflect test execution and retrieve per-test results.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"reflect.get-execution-status\"\n          with:\n            execution-id: \"tools.executionId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reflect/refs/heads/main/capabilities/test-automation.yaml
tags:
- Reflect
- Testing
- Automation
- CI/CD
- End-to-End Tests
- QA
tools:
- description: List all automated end-to-end tests available in the Reflect account.
  hints:
    openWorld: false
    readOnly: true
  name: list-tests
- description: Trigger a Reflect automated test execution, with optional overrides for target hostnames, parameters, cookies, headers, and session storage.
  hints:
    openWorld: false
    readOnly: false
  name: run-test
- description: Check the current status of a Reflect test execution and retrieve per-test results.
  hints:
    openWorld: false
    readOnly: true
  name: get-execution-status
---
