---
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
- apache jmeter
- java
- get current status and metrics of a running jmeter test
- get test status
- get results
- api testing
- performance testing
- open source
- get status
- Performance Engineer
- stress testing
- engineers who analyze performance test results and tune systems
- retrieve performance test results including response times and throughput
- start load test
- QA Engineer
- performance engineering
- qa automation
- stop the currently running jmeter load test
- start test
- qa engineers who run and monitor jmeter load tests
- start an apache jmeter load test with a specified test plan
- stop load test
- load testing
- get test results
slug: load-test-management
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
