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
- QA Engineer
- api testing
- performance testing
- performance engineering
- get results
- get current status and metrics of a running jmeter test
- start an apache jmeter load test with a specified test plan
- Performance Engineer
- get test results
- retrieve performance test results including response times and throughput
- load testing
- stop the currently running jmeter load test
- open source
- start load test
- stop load test
- qa automation
- get test status
- apache jmeter
- java
- stress testing
- get status
- qa engineers who run and monitor jmeter load tests
- start test
- engineers who analyze performance test results and tune systems
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
