---
categories: []
consumed_apis: []
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
- get execution status
- testing
- automation
- check the current status of a reflect test execution and retrieve per-test results.
- ci/cd
- reflect
- check test execution status.
- test execution triggers.
- test execution status.
- run test
- automated testing
- artificial intelligence
- trigger a reflect automated test execution, with optional overrides for target hostnames, parameters, cookies, headers, and session storage.
- end-to-end testing
- ai testing
- qa
- list all automated end-to-end tests.
- trigger a test run.
- available tests catalog.
- list tests
- end-to-end tests
- list all automated end-to-end tests available in the reflect account.
slug: test-automation
source_filename: test-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reflect Test Automation\n  description: Workflow capability for QA engineers and DevOps teams managing and executing automated end-to-end tests through\n    the Reflect API. Supports listing available tests, triggering test runs with parameter overrides, and monitoring execution\n    status for CI/CD pipeline integration.\n  tags:\n  - Reflect\n  - Testing\n  - Automation\n  - CI/CD\n  - End-to-End Tests\n  - QA\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REFLECT_API_KEY: REFLECT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: reflect\n    baseUri: https://api.reflect.run/v1\n    description: Reflect API for test management and execution.\n    authentication:\n      type: apikey\n      key: X-API-KEY\n      value: '{{REFLECT_API_KEY}}'\n      placement: header\n    resources:\n    - name: tests\n      path: /tests\n      description: Test management.\n      operations:\n\
  \      - name: list-tests\n        method: GET\n        description: List all tests in the account.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: run-test\n        method: POST\n        description: Execute a specific test by ID.\n        inputParameters:\n        - name: test-id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the test to run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            overrides:\n              hostnames: '{{tools.hostnames}}'\n              parameters: '{{tools.parameters}}'\n              headers: '{{tools.headers}}'\n            variables: '{{tools.variables}}'\n            emailFailures: '{{tools.emailFailures}}'\n    - name: executions\n\
  \      path: /executions\n      description: Test execution status.\n      operations:\n      - name: get-execution-status\n        method: GET\n        description: Get the status of a specific test execution.\n        inputParameters:\n        - name: execution-id\n          in: path\n          type: integer\n          required: true\n          description: The ID of the execution to check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: reflect-automation-api\n    description: Unified REST API for Reflect test automation workflows.\n    resources:\n    - path: /v1/tests\n      name: tests\n      description: Available tests catalog.\n      operations:\n      - method: GET\n        name: list-tests\n        description: List all automated end-to-end tests.\n        call: reflect.list-tests\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n    - path: /v1/tests/{testId}/executions\n      name: test-runs\n      description: Test execution triggers.\n      operations:\n      - method: POST\n        name: run-test\n        description: Trigger a test run.\n        call: reflect.run-test\n        with:\n          test-id: rest.testId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/executions/{executionId}\n      name: executions\n      description: Test execution status.\n      operations:\n      - method: GET\n        name: get-execution-status\n        description: Check test execution status.\n        call: reflect.get-execution-status\n        with:\n          execution-id: rest.executionId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: reflect-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Reflect test automation.\n    tools:\n    - name: list-tests\n \
  \     description: List all automated end-to-end tests available in the Reflect account.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reflect.list-tests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-test\n      description: Trigger a Reflect automated test execution, with optional overrides for target hostnames, parameters, cookies,\n        headers, and session storage.\n      hints:\n        readOnly: false\n        openWorld: false\n      call: reflect.run-test\n      with:\n        test-id: tools.testId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-execution-status\n      description: Check the current status of a Reflect test execution and retrieve per-test results.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reflect.get-execution-status\n      with:\n        execution-id: tools.executionId\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n"
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
