---
categories: []
consumed_apis: []
description: Workflow capability for container and Kubernetes security scanning using Trivy. Covers vulnerability detection in container images and packages, Kubernetes CRD-based security reports via Trivy Operator, and server health management. Supports DevSecOps pipelines integrating vulnerability scanning into CI/CD workflows.
layout: capability
name: Trivy Security Scanning
operations:
- description: Check if Trivy server is running
  method: GET
  name: health-check
  path: /v1/health
- description: Get server and vulnerability database versions
  method: GET
  name: get-version
  path: /v1/version
personas: []
provider_name: Trivy
provider_slug: trivy
search_terms:
- devsecops
- health check
- get version
- vulnerability scanning
- cloud security
- containers
- open source
- trivy server health status
- sbom
- check if trivy security scanner server is running and healthy
- trivy health check
- trivy get version
- check if trivy server is running
- trivy server and database version
- security
- get server and vulnerability database versions
- get trivy server version and vulnerability database version
- kubernetes
slug: security-scanning
source_filename: security-scanning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trivy Security Scanning\n  description: Workflow capability for container and Kubernetes security scanning using Trivy. Covers vulnerability detection\n    in container images and packages, Kubernetes CRD-based security reports via Trivy Operator, and server health management.\n    Supports DevSecOps pipelines integrating vulnerability scanning into CI/CD workflows.\n  tags:\n  - Security\n  - Vulnerability Scanning\n  - Containers\n  - Kubernetes\n  - DevSecOps\n  - Open Source\n  - SBOM\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIVY_TOKEN: TRIVY_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trivy-server\n    baseUri: http://localhost:4954\n    description: Trivy server HTTP API for health checks and version information\n    authentication:\n      type: apikey\n      key: Trivy-Token\n      value: '{{TRIVY_TOKEN}}'\n      placement: header\n    resources:\n    - name:\
  \ health\n      path: /healthz\n      description: Server health check\n      operations:\n      - name: health-check\n        method: GET\n        description: Check if Trivy server is running and healthy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: version\n      path: /version\n      description: Server version information\n      operations:\n      - name: get-version\n        method: GET\n        description: Get Trivy server and database version information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trivy-security-api\n    description: Unified REST API for Trivy security scanning operations.\n    resources:\n    - path: /v1/health\n      name: health\n      description: Trivy server health status\n      operations:\n      - method: GET\n        name:\
  \ health-check\n        description: Check if Trivy server is running\n        call: trivy-server.health-check\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/version\n      name: version\n      description: Trivy server and database version\n      operations:\n      - method: GET\n        name: get-version\n        description: Get server and vulnerability database versions\n        call: trivy-server.get-version\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trivy-security-mcp\n    transport: http\n    description: MCP server for AI-assisted security scanning with Trivy.\n    tools:\n    - name: trivy-health-check\n      description: Check if Trivy security scanner server is running and healthy\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trivy-server.health-check\n      outputParameters:\n      - type: object\n        mapping: $.\n    -\
  \ name: trivy-get-version\n      description: Get Trivy server version and vulnerability database version\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trivy-server.get-version\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trivy/refs/heads/main/capabilities/security-scanning.yaml
tags:
- Security
- Vulnerability Scanning
- Containers
- Kubernetes
- DevSecOps
- Open Source
- SBOM
tools:
- description: Check if Trivy security scanner server is running and healthy
  hints:
    openWorld: false
    readOnly: true
  name: trivy-health-check
- description: Get Trivy server version and vulnerability database version
  hints:
    openWorld: false
    readOnly: true
  name: trivy-get-version
---
