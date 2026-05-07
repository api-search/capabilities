---
categories: []
consumed_apis: []
description: Workflow capability for QA engineers and mobile developers to run automated tests on real physical devices and desktop browsers using AWS Device Farm. Combines project management, device pool configuration, test scheduling, artifact collection, and remote access session management.
layout: capability
name: AWS Device Farm Mobile and Browser Testing
operations:
- description: List all Device Farm test projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a new test project
  method: POST
  name: create-project
  path: /v1/projects
- description: List available real physical devices
  method: GET
  name: list-devices
  path: /v1/devices
- description: List device pools
  method: GET
  name: list-device-pools
  path: /v1/device-pools
- description: Create a device pool with filter rules
  method: POST
  name: create-device-pool
  path: /v1/device-pools
- description: Upload an app or test package
  method: POST
  name: create-upload
  path: /v1/uploads
- description: List uploads for a project
  method: GET
  name: list-uploads
  path: /v1/uploads
- description: Schedule a test run on real devices
  method: POST
  name: schedule-run
  path: /v1/runs
- description: List test runs for a project
  method: GET
  name: list-runs
  path: /v1/runs
- description: Get test run results and status
  method: GET
  name: get-run
  path: /v1/runs/{runArn}
- description: Stop a running test
  method: DELETE
  name: stop-run
  path: /v1/runs/{runArn}
- description: Start a remote access session on a device
  method: POST
  name: create-remote-access-session
  path: /v1/remote-access-sessions
- description: List remote access sessions
  method: GET
  name: list-remote-access-sessions
  path: /v1/remote-access-sessions
- description: List Selenium test grid projects
  method: GET
  name: list-test-grid-projects
  path: /v1/test-grid-projects
- description: Create a new Selenium test grid project
  method: POST
  name: create-test-grid-project
  path: /v1/test-grid-projects
personas: []
provider_name: Amazon Device Farm
provider_slug: amazon-device-farm
search_terms:
- create a signed url for selenium remotewebdriver to connect to device farm
- upload an app or test package
- schedule run
- list test runs for a project
- list test grid projects
- list available real physical devices for testing
- browser testing
- quality assurance
- individual run management
- list available real physical devices
- get upload
- schedule a test run on real physical devices
- testing web applications in selenium-powered desktop browsers
- create remote access session
- Mobile Developer
- mobile testing
- create test grid url
- list artifacts
- mobile app developer running tests on real devices to validate app quality
- list all test runs for a project
- list selenium test grid projects for browser testing
- amazon device farm
- create device pool
- test project management
- list device pools
- start a remote access session on a device
- create upload
- check the status of an uploaded app or test package
- real device catalog
- list unique problems
- test run lifecycle
- create a new device farm test project
- list remote access sessions
- schedule a test run on real devices
- device pool configuration
- start an interactive remote access session on a real device
- list uploads
- create test grid project
- stop remote access session
- list runs
- stop run
- list test artifacts like screenshots, logs, and videos from a run
- end-to-end testing workflow for mobile apps on real devices and web apps in browsers
- quality assurance engineer managing test infrastructure and running automated test suites
- QA Engineer
- create project
- list projects
- create a device pool with rules to filter devices for testing
- stop an active remote access session
- list uploads for a project
- create a device pool with filter rules
- test automation
- list all aws device farm test projects
- list device pools configured for a project
- get the status and results of a test run
- list jobs within a test run
- list unique problems found across test runs
- list all device farm test projects
- list selenium test grid projects
- selenium browser test grid projects
- list devices
- list jobs
- create a new test project
- remote device access sessions
- aws
- create a new selenium test grid project
- application testing
- get test run results and status
- stop a currently running test
- interactive remote access to real devices for debugging
- get run
- device testing
- testing mobile applications on real physical ios and android devices
- create an upload slot and get a pre-signed url to upload your app or test package
- app and test artifact uploads
- stop a running test
slug: mobile-browser-testing
source_filename: mobile-browser-testing.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: AWS Device Farm Mobile and Browser Testing\n  description: Workflow capability for QA engineers and mobile developers to run automated tests on real physical devices\n    and desktop browsers using AWS Device Farm. Combines project management, device pool configuration, test scheduling, artifact\n    collection, and remote access session management.\n  tags:\n  - Amazon Device Farm\n  - Mobile Testing\n  - Browser Testing\n  - Quality Assurance\n  - Test Automation\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: device-farm\n    baseUri: https://devicefarm.us-west-2.amazonaws.com\n    description: AWS Device Farm REST API for mobile and browser testing.\n    authentication:\n      type: apikey\n      key: Authorization\n\
  \      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: projects\n      path: /\n      description: Project management\n      operations:\n      - name: create-project\n        method: POST\n        description: Creates a Device Farm project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-projects\n        method: POST\n        description: Lists projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-project\n        method: POST\n        description: Gets project information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: runs\n      path: /\n      description: Test run management\n      operations:\n      - name: schedule-run\n        method: POST\n        description:\
  \ Schedules a test run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-run\n        method: POST\n        description: Gets test run information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-runs\n        method: POST\n        description: Lists test runs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-run\n        method: POST\n        description: Stops a running test\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-pools\n      path: /\n      description: Device pool management\n      operations:\n      - name: create-device-pool\n        method: POST\n        description: Creates a device pool\
  \ with specified rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-device-pools\n        method: POST\n        description: Lists device pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-device-pool\n        method: POST\n        description: Gets device pool information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: devices\n      path: /\n      description: Device catalog\n      operations:\n      - name: list-devices\n        method: POST\n        description: Lists available devices\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-device\n        method: POST\n        description: Gets information\
  \ about a device type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: uploads\n      path: /\n      description: Upload management for apps and test scripts\n      operations:\n      - name: create-upload\n        method: POST\n        description: Creates an upload for an app or test scripts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-uploads\n        method: POST\n        description: Lists uploads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-upload\n        method: POST\n        description: Gets upload information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: remote-access-sessions\n      path: /\n\
  \      description: Remote access session management\n      operations:\n      - name: create-remote-access-session\n        method: POST\n        description: Starts a remote access session on a device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-remote-access-sessions\n        method: POST\n        description: Lists remote access sessions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: stop-remote-access-session\n        method: POST\n        description: Stops a remote access session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: test-grid-projects\n      path: /\n      description: Selenium test grid project management\n      operations:\n      - name: create-test-grid-project\n        method: POST\n\
  \        description: Creates a Selenium testing project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-test-grid-projects\n        method: GET\n        description: Lists Selenium test grid projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-test-grid-url\n        method: POST\n        description: Creates a signed URL for Selenium RemoteWebDriver\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /\n      description: Job management\n      operations:\n      - name: list-jobs\n        method: POST\n        description: Lists jobs in a test run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: get-job\n        method: POST\n        description: Gets job information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mobile-browser-testing-api\n    description: Unified REST API for AWS Device Farm mobile and browser testing workflows.\n    resources:\n    - path: /v1/projects\n      name: projects\n      description: Test project management\n      operations:\n      - method: GET\n        name: list-projects\n        description: List all Device Farm test projects\n        call: device-farm.list-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-project\n        description: Create a new test project\n        call: device-farm.create-project\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/devices\n      name: devices\n\
  \      description: Real device catalog\n      operations:\n      - method: GET\n        name: list-devices\n        description: List available real physical devices\n        call: device-farm.list-devices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/device-pools\n      name: device-pools\n      description: Device pool configuration\n      operations:\n      - method: GET\n        name: list-device-pools\n        description: List device pools\n        call: device-farm.list-device-pools\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-device-pool\n        description: Create a device pool with filter rules\n        call: device-farm.create-device-pool\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/uploads\n      name: uploads\n      description: App and test artifact uploads\n      operations:\n      - method: POST\n        name:\
  \ create-upload\n        description: Upload an app or test package\n        call: device-farm.create-upload\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-uploads\n        description: List uploads for a project\n        call: device-farm.list-uploads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs\n      name: runs\n      description: Test run lifecycle\n      operations:\n      - method: POST\n        name: schedule-run\n        description: Schedule a test run on real devices\n        call: device-farm.schedule-run\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-runs\n        description: List test runs for a project\n        call: device-farm.list-runs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/runs/{runArn}\n      name: run\n      description: Individual\
  \ run management\n      operations:\n      - method: GET\n        name: get-run\n        description: Get test run results and status\n        call: device-farm.get-run\n        with:\n          arn: rest.runArn\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: stop-run\n        description: Stop a running test\n        call: device-farm.stop-run\n        with:\n          arn: rest.runArn\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/remote-access-sessions\n      name: remote-access-sessions\n      description: Remote device access sessions\n      operations:\n      - method: POST\n        name: create-remote-access-session\n        description: Start a remote access session on a device\n        call: device-farm.create-remote-access-session\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: list-remote-access-sessions\n\
  \        description: List remote access sessions\n        call: device-farm.list-remote-access-sessions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/test-grid-projects\n      name: test-grid-projects\n      description: Selenium browser test grid projects\n      operations:\n      - method: GET\n        name: list-test-grid-projects\n        description: List Selenium test grid projects\n        call: device-farm.list-test-grid-projects\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-test-grid-project\n        description: Create a new Selenium test grid project\n        call: device-farm.create-test-grid-project\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mobile-browser-testing-mcp\n    transport: http\n    description: MCP server for AI-assisted mobile and browser test automation with AWS Device\
  \ Farm.\n    tools:\n    - name: list-projects\n      description: List all AWS Device Farm test projects\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-projects\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new Device Farm test project\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.create-project\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-devices\n      description: List available real physical devices for testing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-devices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-device-pools\n      description: List device pools configured for a project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-device-pools\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-device-pool\n      description: Create a device pool with rules to filter devices for testing\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.create-device-pool\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-upload\n      description: Create an upload slot and get a pre-signed URL to upload your app or test package\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.create-upload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-upload\n      description: Check the status of an uploaded app or test package\n      hints:\n        readOnly: true\n        openWorld: false\n      call: device-farm.get-upload\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: schedule-run\n      description: Schedule a test run on real\
  \ physical devices\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.schedule-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-run\n      description: Get the status and results of a test run\n      hints:\n        readOnly: true\n        openWorld: false\n      call: device-farm.get-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-runs\n      description: List all test runs for a project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-runs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-run\n      description: Stop a currently running test\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: device-farm.stop-run\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List jobs\
  \ within a test run\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-remote-access-session\n      description: Start an interactive remote access session on a real device\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.create-remote-access-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: stop-remote-access-session\n      description: Stop an active remote access session\n      hints:\n        readOnly: false\n        destructive: true\n      call: device-farm.stop-remote-access-session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-test-grid-projects\n      description: List Selenium test grid projects for browser testing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-test-grid-projects\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-test-grid-url\n      description: Create a signed URL for Selenium RemoteWebDriver to connect to Device Farm\n      hints:\n        readOnly: false\n        destructive: false\n      call: device-farm.create-test-grid-url\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-artifacts\n      description: List test artifacts like screenshots, logs, and videos from a run\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-artifacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-unique-problems\n      description: List unique problems found across test runs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: device-farm.list-unique-problems\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-device-farm/refs/heads/main/capabilities/mobile-browser-testing.yaml
tags:
- Amazon Device Farm
- Mobile Testing
- Browser Testing
- Quality Assurance
- Test Automation
tools:
- description: List all AWS Device Farm test projects
  hints:
    openWorld: true
    readOnly: true
  name: list-projects
- description: Create a new Device Farm test project
  hints:
    destructive: false
    readOnly: false
  name: create-project
- description: List available real physical devices for testing
  hints:
    openWorld: true
    readOnly: true
  name: list-devices
- description: List device pools configured for a project
  hints:
    openWorld: true
    readOnly: true
  name: list-device-pools
- description: Create a device pool with rules to filter devices for testing
  hints:
    destructive: false
    readOnly: false
  name: create-device-pool
- description: Create an upload slot and get a pre-signed URL to upload your app or test package
  hints:
    destructive: false
    readOnly: false
  name: create-upload
- description: Check the status of an uploaded app or test package
  hints:
    openWorld: false
    readOnly: true
  name: get-upload
- description: Schedule a test run on real physical devices
  hints:
    destructive: false
    readOnly: false
  name: schedule-run
- description: Get the status and results of a test run
  hints:
    openWorld: false
    readOnly: true
  name: get-run
- description: List all test runs for a project
  hints:
    openWorld: true
    readOnly: true
  name: list-runs
- description: Stop a currently running test
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: stop-run
- description: List jobs within a test run
  hints:
    openWorld: true
    readOnly: true
  name: list-jobs
- description: Start an interactive remote access session on a real device
  hints:
    destructive: false
    readOnly: false
  name: create-remote-access-session
- description: Stop an active remote access session
  hints:
    destructive: true
    readOnly: false
  name: stop-remote-access-session
- description: List Selenium test grid projects for browser testing
  hints:
    openWorld: true
    readOnly: true
  name: list-test-grid-projects
- description: Create a signed URL for Selenium RemoteWebDriver to connect to Device Farm
  hints:
    destructive: false
    readOnly: false
  name: create-test-grid-url
- description: List test artifacts like screenshots, logs, and videos from a run
  hints:
    openWorld: true
    readOnly: true
  name: list-artifacts
- description: List unique problems found across test runs
  hints:
    openWorld: true
    readOnly: true
  name: list-unique-problems
---
