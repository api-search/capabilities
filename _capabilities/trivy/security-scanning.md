---
api_specs:
- filename: trivy-server-openapi.yml
  format: yaml
  label: trivy-server
  slug: trivy-server
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/trivy/refs/heads/main/openapi/trivy-server-openapi.yml
categories: []
consumed_apis:
- trivy-server
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
- check if trivy server is running
- sbom
- health check
- security
- trivy get version
- get trivy server version and vulnerability database version
- trivy server health status
- kubernetes
- open source
- containers
- devsecops
- trivy server and database version
- get server and vulnerability database versions
- trivy health check
- cloud security
- get version
- vulnerability scanning
- check if trivy security scanner server is running and healthy
slug: security-scanning
source_filename: security-scanning.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Trivy Security Scanning\"\n  description: >-\n    Workflow capability for container and Kubernetes security scanning using Trivy.\n    Covers vulnerability detection in container images and packages, Kubernetes\n    CRD-based security reports via Trivy Operator, and server health management.\n    Supports DevSecOps pipelines integrating vulnerability scanning into CI/CD workflows.\n  tags:\n    - Security\n    - Vulnerability Scanning\n    - Containers\n    - Kubernetes\n    - DevSecOps\n    - Open Source\n    - SBOM\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TRIVY_TOKEN: TRIVY_TOKEN\n\ncapability:\n  consumes:\n    - import: trivy-server\n      location: ./shared/trivy-server.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: trivy-security-api\n      description: \"Unified REST API for Trivy security scanning operations.\"\n      resources:\n  \
  \      - path: /v1/health\n          name: health\n          description: \"Trivy server health status\"\n          operations:\n            - method: GET\n              name: health-check\n              description: \"Check if Trivy server is running\"\n              call: \"trivy-server.health-check\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/version\n          name: version\n          description: \"Trivy server and database version\"\n          operations:\n            - method: GET\n              name: get-version\n              description: \"Get server and vulnerability database versions\"\n              call: \"trivy-server.get-version\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: trivy-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted security scanning with\
  \ Trivy.\"\n      tools:\n        - name: trivy-health-check\n          description: \"Check if Trivy security scanner server is running and healthy\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trivy-server.health-check\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: trivy-get-version\n          description: \"Get Trivy server version and vulnerability database version\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"trivy-server.get-version\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
