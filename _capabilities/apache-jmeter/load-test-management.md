---
categories: []
consumed_apis:
- jmeter-rest-api
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
- get test status
- qa automation
- performance engineering
- performance testing
- stress testing
- load testing
- stop load test
- get current status and metrics of a running jmeter test
- java
- retrieve performance test results including response times and throughput
- QA Engineer
- engineers who analyze performance test results and tune systems
- apache jmeter
- open source
- start an apache jmeter load test with a specified test plan
- get status
- start load test
- get test results
- get results
- qa engineers who run and monitor jmeter load tests
- stop the currently running jmeter load test
- Performance Engineer
- start test
- api testing
slug: load-test-management
source_filename: load-test-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Apache JMeter Load Test Management\"\n  description: \"Workflow capability for QA engineers and performance engineers to manage and monitor Apache JMeter load tests via the REST API.\"\n  tags:\n    - Apache JMeter\n    - Load Testing\n    - Performance Engineering\n    - QA Automation\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      JMETER_API_URL: JMETER_API_URL\n\ncapability:\n  consumes:\n    - import: jmeter-rest-api\n      location: ./shared/jmeter-rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: jmeter-load-test-api\n      description: \"Unified REST API for Apache JMeter load test management.\"\n      resources:\n        - path: /v1/tests/run\n          name: test-run\n          operations:\n            - method: POST\n              name: start-test\n              call: \"jmeter-rest-api.start-test\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tests/status\n          name: test-status\n          operations:\n            - method: GET\n              name: get-status\n              call: \"jmeter-rest-api.get-status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/tests/results\n          name: test-results\n          operations:\n            - method: GET\n              name: get-results\n              call: \"jmeter-rest-api.get-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: jmeter-load-test-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Apache JMeter load test management.\"\n      tools:\n        - name: start-load-test\n          description: Start an Apache JMeter load test with a specified test plan\n          hints:\n\
  \            readOnly: false\n          call: \"jmeter-rest-api.start-test\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: stop-load-test\n          description: Stop the currently running JMeter load test\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"jmeter-rest-api.stop-test\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-test-status\n          description: Get current status and metrics of a running JMeter test\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"jmeter-rest-api.get-status\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-test-results\n          description: Retrieve performance test results including response times and throughput\n          hints:\n            readOnly: true\n            openWorld:\
  \ true\n          call: \"jmeter-rest-api.get-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
