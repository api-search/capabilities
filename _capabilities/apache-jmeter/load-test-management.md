---
categories: []
consumed_apis: []
description: Workflow capability for QA engineers and performance engineers to manage and monitor Apache JMeter load tests via the REST API.
layout: capability
name: Apache JMeter Load Test Management
operations:
- description: ''
  method: POST
  name: start-test
  path: /v1/tests/run
- description: ''
  method: GET
  name: get-status
  path: /v1/tests/status
- description: ''
  method: GET
  name: get-results
  path: /v1/tests/results
personas: []
provider_name: Apache JMeter
provider_slug: apache-jmeter
search_terms:
- performance testing
- apache jmeter
- stress testing
- stop the currently running jmeter load test
- get results
- java
- open source
- retrieve performance test results including response times and throughput
- get test status
- QA Engineer
- get status
- get test results
- Performance Engineer
- start load test
- get current status and metrics of a running jmeter test
- start an apache jmeter load test with a specified test plan
- api testing
- qa engineers who run and monitor jmeter load tests
- start test
- stop load test
- engineers who analyze performance test results and tune systems
- qa automation
- performance engineering
- load testing
slug: load-test-management
source_filename: load-test-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Apache JMeter Load Test Management\n  description: Workflow capability for QA engineers and performance engineers to manage and monitor Apache JMeter load tests\n    via the REST API.\n  tags:\n  - Apache JMeter\n  - Load Testing\n  - Performance Engineering\n  - QA Automation\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    JMETER_API_URL: JMETER_API_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: jmeter-rest-api\n    baseUri: http://localhost:4445\n    description: Apache JMeter REST API\n    resources:\n    - name: run\n      path: /run\n      description: Test execution control\n      operations:\n      - name: start-test\n        method: POST\n        description: Start a JMeter test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status\n      path: /status\n      description: Test status\
  \ monitoring\n      operations:\n      - name: get-status\n        method: GET\n        description: Get test status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: results\n      path: /results\n      description: Test results\n      operations:\n      - name: get-results\n        method: GET\n        description: Get test results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jmeter-load-test-api\n    description: Unified REST API for Apache JMeter load test management.\n    resources:\n    - path: /v1/tests/run\n      name: test-run\n      operations:\n      - method: POST\n        name: start-test\n        call: jmeter-rest-api.start-test\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tests/status\n      name:\
  \ test-status\n      operations:\n      - method: GET\n        name: get-status\n        call: jmeter-rest-api.get-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tests/results\n      name: test-results\n      operations:\n      - method: GET\n        name: get-results\n        call: jmeter-rest-api.get-results\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jmeter-load-test-mcp\n    transport: http\n    description: MCP server for AI-assisted Apache JMeter load test management.\n    tools:\n    - name: start-load-test\n      description: Start an Apache JMeter load test with a specified test plan\n      hints:\n        readOnly: false\n      call: jmeter-rest-api.start-test\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-load-test\n      description: Stop the currently running JMeter load test\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n      call: jmeter-rest-api.stop-test\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-test-status\n      description: Get current status and metrics of a running JMeter test\n      hints:\n        readOnly: true\n        openWorld: true\n      call: jmeter-rest-api.get-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-test-results\n      description: Retrieve performance test results including response times and throughput\n      hints:\n        readOnly: true\n        openWorld: true\n      call: jmeter-rest-api.get-results\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-jmeter/refs/heads/main/capabilities/load-test-management.yaml
tags:
- Apache JMeter
- Load Testing
- Performance Engineering
- QA Automation
tools:
- description: Start an Apache JMeter load test with a specified test plan
  hints:
    readOnly: false
  name: start-load-test
- description: Stop the currently running JMeter load test
  hints:
    destructive: false
    readOnly: false
  name: stop-load-test
- description: Get current status and metrics of a running JMeter test
  hints:
    openWorld: true
    readOnly: true
  name: get-test-status
- description: Retrieve performance test results including response times and throughput
  hints:
    openWorld: true
    readOnly: true
  name: get-test-results
---
