---
categories:
- security
consumed_apis: []
description: Workflow capability for DevSecOps engineers and security teams running automated API conformance scans on Kubernetes. Combines scan job management and log retrieval into a unified interface for CI/CD pipeline integration, on-premises security testing, and runtime compliance validation.
layout: capability
name: 42Crunch API Security Scanning
operations:
- description: List all active and completed API conformance scans
  method: GET
  name: list-scans
  path: /v1/scans
- description: Start a new API conformance scan job on Kubernetes
  method: POST
  name: run-scan
  path: /v1/scans
- description: Get the current status of a specific API conformance scan
  method: GET
  name: get-scan-status
  path: /v1/scans/{name}
- description: Cancel and remove a specific API conformance scan job
  method: DELETE
  name: cancel-scan
  path: /v1/scans/{name}
- description: Retrieve execution logs from an API conformance scan
  method: GET
  name: get-scan-logs
  path: /v1/scans/{name}/logs
- description: Check the scan manager service health
  method: GET
  name: check-health
  path: /v1/health
personas: []
provider_name: 42Crunch
provider_slug: 42crunch
search_terms:
- check the scan manager service health
- managing containerized workloads for api scan execution
- DevSecOps Engineer
- manage api conformance scan jobs
- get scan logs
- get the current status of a specific api conformance scan
- start a new 42crunch api conformance scan job on kubernetes using a scan token from the 42crunch platform
- ci/cd
- Security Team
- platform
- cancel api scan
- run api scan
- devsecops
- list scans
- openapi
- retrieve execution logs from an api conformance scan
- get scan status
- cancel scan
- check health
- kubernetes
- check scanner health
- workflow for devsecops engineers running automated api conformance scans on kubernetes with ci/cd pipeline integration.
- retrieve execution logs from an api conformance scan job to diagnose failures or review results
- conformance scanning
- engineers embedding api security scanning into ci/cd pipelines and automating conformance testing as part of the development workflow.
- ensuring apis are secure and compliant with security standards
- cancel and remove a specific api conformance scan job from the kubernetes cluster
- list api scans
- start a new api conformance scan job on kubernetes
- validating api runtime behavior against openapi contract specifications
- check the health status of the 42crunch scan manager service to verify availability
- list all api conformance scan jobs including their current status (started, active, succeeded, failed)
- access scan execution logs
- check or remove a specific scan job
- list all active and completed api conformance scans
- api security
- service health check
- scanning
- get the current status of a specific api conformance scan job (started, active, succeeded, failed, unknown)
- cancel and remove a specific api conformance scan job
- security
- run scan
- security professionals managing api conformance testing, reviewing scan results, and ensuring apis meet security standards before and after deployment.
slug: api-security-scanning
source_filename: api-security-scanning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: 42Crunch API Security Scanning\n  description: Workflow capability for DevSecOps engineers and security teams running automated API conformance scans on Kubernetes.\n    Combines scan job management and log retrieval into a unified interface for CI/CD pipeline integration, on-premises security\n    testing, and runtime compliance validation.\n  tags:\n  - API Security\n  - Conformance Scanning\n  - Kubernetes\n  - DevSecOps\n  - CI/CD\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCAN_MANAGER_URL: SCAN_MANAGER_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: scand-manager\n    baseUri: http://localhost:8090\n    description: 42Crunch API Conformance Scan Jobs Manager for Kubernetes\n    resources:\n    - name: jobs\n      path: /api/job\n      description: Manage API conformance scan jobs\n      operations:\n      - name: list-jobs\n        method: GET\n        description: Get\
  \ status of all conformance scan jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-job\n        method: POST\n        description: Create a new API conformance scan job on Kubernetes\n        body:\n          type: json\n          data:\n            token: '{{tools.token}}'\n            name: '{{tools.name}}'\n            expirationTime: '{{tools.expirationTime}}'\n            platformService: '{{tools.platformService}}'\n            scandImage: '{{tools.scandImage}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: job\n      path: /api/job/{name}\n      description: Manage a specific scan job by name\n      operations:\n      - name: get-job\n        method: GET\n        description: Read the current status of a specific conformance scan job\n        inputParameters:\n        - name: name\n \
  \         in: path\n          type: string\n          required: true\n          description: Scan job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-job\n        method: DELETE\n        description: Delete a conformance scan job by name\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: Scan job name to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: logs\n      path: /api/logs/{name}\n      description: Access scan job execution logs\n      operations:\n      - name: get-logs\n        method: GET\n        description: Retrieve execution logs for a specific conformance scan job\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n\
  \          description: Scan job name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      description: Service health check\n      operations:\n      - name: health-check\n        method: GET\n        description: Check the health status of the scan manager service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: api-security-scanning-api\n    description: Unified REST API for 42Crunch API security scanning workflows.\n    resources:\n    - path: /v1/scans\n      name: scans\n      description: Manage API conformance scan jobs\n      operations:\n      - method: GET\n        name: list-scans\n        description: List all active and completed API conformance scans\n        call: scand-manager.list-jobs\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: run-scan\n        description: Start a new API conformance scan job on Kubernetes\n        call: scand-manager.create-job\n        with:\n          token: rest.token\n          name: rest.name\n          expirationTime: rest.expirationTime\n          platformService: rest.platformService\n          scandImage: rest.scandImage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scans/{name}\n      name: scan\n      description: Check or remove a specific scan job\n      operations:\n      - method: GET\n        name: get-scan-status\n        description: Get the current status of a specific API conformance scan\n        call: scand-manager.get-job\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-scan\n        description: Cancel and remove a specific API\
  \ conformance scan job\n        call: scand-manager.delete-job\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/scans/{name}/logs\n      name: scan-logs\n      description: Access scan execution logs\n      operations:\n      - method: GET\n        name: get-scan-logs\n        description: Retrieve execution logs from an API conformance scan\n        call: scand-manager.get-logs\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/health\n      name: health\n      description: Service health check\n      operations:\n      - method: GET\n        name: check-health\n        description: Check the scan manager service health\n        call: scand-manager.health-check\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: api-security-scanning-mcp\n    transport:\
  \ http\n    description: MCP server for AI-assisted API security scanning and conformance testing workflows.\n    tools:\n    - name: list-api-scans\n      description: List all API conformance scan jobs including their current status (started, active, succeeded, failed)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scand-manager.list-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-api-scan\n      description: Start a new 42Crunch API conformance scan job on Kubernetes using a scan token from the 42Crunch platform\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scand-manager.create-job\n      with:\n        token: tools.token\n        name: tools.name\n        expirationTime: tools.expirationTime\n        platformService: tools.platformService\n        scandImage: tools.scandImage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ get-scan-status\n      description: Get the current status of a specific API conformance scan job (started, active, succeeded, failed, unknown)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scand-manager.get-job\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-api-scan\n      description: Cancel and remove a specific API conformance scan job from the Kubernetes cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: scand-manager.delete-job\n      with:\n        name: tools.name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-scan-logs\n      description: Retrieve execution logs from an API conformance scan job to diagnose failures or review results\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scand-manager.get-logs\n      with:\n        name: tools.name\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-scanner-health\n      description: Check the health status of the 42Crunch scan manager service to verify availability\n      hints:\n        readOnly: true\n        openWorld: false\n      call: scand-manager.health-check\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/42crunch/refs/heads/main/capabilities/api-security-scanning.yaml
tags:
- API Security
- Conformance Scanning
- Kubernetes
- DevSecOps
- CI/CD
tools:
- description: List all API conformance scan jobs including their current status (started, active, succeeded, failed)
  hints:
    openWorld: false
    readOnly: true
  name: list-api-scans
- description: Start a new 42Crunch API conformance scan job on Kubernetes using a scan token from the 42Crunch platform
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: run-api-scan
- description: Get the current status of a specific API conformance scan job (started, active, succeeded, failed, unknown)
  hints:
    openWorld: false
    readOnly: true
  name: get-scan-status
- description: Cancel and remove a specific API conformance scan job from the Kubernetes cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-api-scan
- description: Retrieve execution logs from an API conformance scan job to diagnose failures or review results
  hints:
    openWorld: false
    readOnly: true
  name: get-scan-logs
- description: Check the health status of the 42Crunch scan manager service to verify availability
  hints:
    openWorld: false
    readOnly: true
  name: check-scanner-health
---
