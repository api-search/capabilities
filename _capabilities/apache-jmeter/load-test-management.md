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
- get status
- performance engineering
- load testing
- Performance Engineer
- java
- engineers who analyze performance test results and tune systems
- QA Engineer
- performance testing
- stress testing
- get current status and metrics of a running jmeter test
- apache jmeter
- start load test
- get test results
- qa engineers who run and monitor jmeter load tests
- get results
- api testing
- qa automation
- stop the currently running jmeter load test
- start an apache jmeter load test with a specified test plan
- stop load test
- get test status
- start test
- retrieve performance test results including response times and throughput
- open source
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
