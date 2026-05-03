---
api_specs:
- filename: snyk-container-openapi.yml
  format: yaml
  label: snyk-container
  slug: snyk-container
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/snyk-container/refs/heads/main/openapi/snyk-container-openapi.yml
categories: []
consumed_apis:
- snyk-container
description: Unified container security workflow combining Snyk Container's project management, vulnerability scanning, issue tracking, SBOM generation, and registry target management. Designed for DevSecOps engineers, platform security teams, and SREs integrating container security into CI/CD pipelines.
layout: capability
name: Snyk Container Security
operations:
- description: List all container image and Kubernetes scanning projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Register a new container image for scanning
  method: POST
  name: create-project
  path: /v1/projects
- description: Get details of a specific container scanning project
  method: GET
  name: get-project
  path: /v1/projects/{id}
- description: Delete a container scanning project
  method: DELETE
  name: delete-project
  path: /v1/projects/{id}
- description: List vulnerability issues from container scans filtered by severity and status
  method: GET
  name: list-issues
  path: /v1/issues
- description: List CVEs and vulnerabilities for packages in container images
  method: GET
  name: list-package-issues
  path: /v1/package-issues
- description: List all container registries and image sources configured for scanning
  method: GET
  name: list-targets
  path: /v1/targets
- description: Add a new container registry as a scan target
  method: POST
  name: create-target
  path: /v1/targets
- description: Generate SBOM (CycloneDX or SPDX) for a container project
  method: GET
  name: get-sbom
  path: /v1/projects/{id}/sbom
personas: []
provider_name: Snyk Container
provider_slug: snyk-container
search_terms:
- delete container project
- package-level vulnerability issues in container images
- create registry target
- list all container registries and image sources configured for scanning
- manage container scanning projects
- security
- list projects
- delete a container scanning project
- generate sbom (cyclonedx or spdx) for a container project
- list package issues
- get container project
- container security
- open source
- devsecops
- individual container project operations
- snyk
- list all container image and kubernetes scanning projects
- get details of a specific container scanning project
- get project sbom
- create project
- delete project
- list registry targets
- list container issues
- look up cves and security issues for specific packages (by purl) found in container images
- kubernetes
- list all container vulnerability issues, filterable by severity (critical/high/medium/low) and status
- remove a container scanning project from snyk monitoring
- get details of a specific container scanning project including status and settings
- generate and download an sbom (cyclonedx or spdx format) for a container scanning project
- container registry scan targets
- container vulnerability issues
- register a new container image for scanning
- add a new container registry as a scan target
- list all container registries and image sources configured as scan targets in snyk
- list targets
- container images
- sbom
- software bill of materials
- create target
- list container projects
- containers
- list all snyk container scanning projects including container images, kubernetes monitors, and helm releases
- get sbom
- list cves and vulnerabilities for packages in container images
- vulnerability management
- list vulnerability issues from container scans filtered by severity and status
- get project
- ci/cd
- add a new container registry as a snyk scan target
- list issues
slug: container-security
source_filename: container-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Snyk Container Security\"\n  description: >-\n    Unified container security workflow combining Snyk Container's project management, vulnerability scanning, issue tracking, SBOM generation, and registry target management. Designed for DevSecOps engineers, platform security teams, and SREs integrating container security into CI/CD pipelines.\n  tags:\n    - Snyk\n    - Container Security\n    - Vulnerability Management\n    - Kubernetes\n    - DevSecOps\n    - SBOM\n    - CI/CD\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SNYK_API_TOKEN: SNYK_API_TOKEN\n      SNYK_ORG_ID: SNYK_ORG_ID\n\ncapability:\n  consumes:\n    - import: snyk-container\n      location: ./shared/snyk-container.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: container-security-api\n      description: \"Unified REST API for container security scanning and vulnerability management.\"\
  \n      resources:\n        - path: /v1/projects\n          name: container-projects\n          description: \"Manage container scanning projects\"\n          operations:\n            - method: GET\n              name: list-projects\n              description: \"List all container image and Kubernetes scanning projects\"\n              call: \"snyk-container.list-container-projects\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n            - method: POST\n              name: create-project\n              description: \"Register a new container image for scanning\"\n              call: \"snyk-container.create-container-project\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\
  \n\n        - path: /v1/projects/{id}\n          name: container-project\n          description: \"Individual container project operations\"\n          operations:\n            - method: GET\n              name: get-project\n              description: \"Get details of a specific container scanning project\"\n              call: \"snyk-container.get-container-project\"\n              with:\n                org_id: \"rest.org_id\"\n                project_id: \"rest.id\"\n                version: \"2024-10-15\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n            - method: DELETE\n              name: delete-project\n              description: \"Delete a container scanning project\"\n              call: \"snyk-container.delete-container-project\"\n              with:\n                org_id: \"rest.org_id\"\n                project_id: \"rest.id\"\n                version: \"2024-10-15\"\n              outputParameters:\n   \
  \             - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/issues\n          name: vulnerabilities\n          description: \"Container vulnerability issues\"\n          operations:\n            - method: GET\n              name: list-issues\n              description: \"List vulnerability issues from container scans filtered by severity and status\"\n              call: \"snyk-container.list-container-issues\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n                severity: \"rest.severity\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/package-issues\n          name: package-vulnerabilities\n          description: \"Package-level vulnerability issues in container images\"\n          operations:\n            - method: GET\n              name: list-package-issues\n          \
  \    description: \"List CVEs and vulnerabilities for packages in container images\"\n              call: \"snyk-container.list-package-issues\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n                purl: \"rest.purl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/targets\n          name: registry-targets\n          description: \"Container registry scan targets\"\n          operations:\n            - method: GET\n              name: list-targets\n              description: \"List all container registries and image sources configured for scanning\"\n              call: \"snyk-container.list-targets\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n            - method: POST\n        \
  \      name: create-target\n              description: \"Add a new container registry as a scan target\"\n              call: \"snyk-container.create-target\"\n              with:\n                org_id: \"rest.org_id\"\n                version: \"2024-10-15\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.data\"\n\n        - path: /v1/projects/{id}/sbom\n          name: sbom\n          description: \"Software Bill of Materials\"\n          operations:\n            - method: GET\n              name: get-sbom\n              description: \"Generate SBOM (CycloneDX or SPDX) for a container project\"\n              call: \"snyk-container.get-project-sbom\"\n              with:\n                org_id: \"rest.org_id\"\n                project_id: \"rest.id\"\n                version: \"2024-10-15\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \    - type: mcp\n      port: 9090\n      namespace: container-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted container security scanning, vulnerability analysis, and remediation.\"\n      tools:\n        - name: list-container-projects\n          description: \"List all Snyk Container scanning projects including container images, Kubernetes monitors, and Helm releases\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snyk-container.list-container-projects\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: get-container-project\n          description: \"Get details of a specific container scanning project including status and settings\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snyk-container.get-container-project\"\
  \n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: list-container-issues\n          description: \"List all container vulnerability issues, filterable by severity (critical/high/medium/low) and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snyk-container.list-container-issues\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: list-package-issues\n          description: \"Look up CVEs and security issues for specific packages (by purl) found in container images\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"snyk-container.list-package-issues\"\n          with:\n            org_id:\
  \ \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: get-project-sbom\n          description: \"Generate and download an SBOM (CycloneDX or SPDX format) for a container scanning project\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snyk-container.get-project-sbom\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-registry-targets\n          description: \"List all container registries and image sources configured as scan targets in Snyk\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"snyk-container.list-targets\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: create-registry-target\n          description: \"Add a new container registry as a Snyk scan target\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"snyk-container.create-target\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n              mapping: \"$.data\"\n\n        - name: delete-container-project\n          description: \"Remove a container scanning project from Snyk monitoring\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"snyk-container.delete-container-project\"\n          with:\n            org_id: \"{{SNYK_ORG_ID}}\"\n            version: \"2024-10-15\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/snyk-container/refs/heads/main/capabilities/container-security.yaml
tags:
- Snyk
- Container Security
- Vulnerability Management
- Kubernetes
- DevSecOps
- SBOM
- CI/CD
tools:
- description: List all Snyk Container scanning projects including container images, Kubernetes monitors, and Helm releases
  hints:
    openWorld: false
    readOnly: true
  name: list-container-projects
- description: Get details of a specific container scanning project including status and settings
  hints:
    openWorld: false
    readOnly: true
  name: get-container-project
- description: List all container vulnerability issues, filterable by severity (critical/high/medium/low) and status
  hints:
    openWorld: false
    readOnly: true
  name: list-container-issues
- description: Look up CVEs and security issues for specific packages (by purl) found in container images
  hints:
    openWorld: true
    readOnly: true
  name: list-package-issues
- description: Generate and download an SBOM (CycloneDX or SPDX format) for a container scanning project
  hints:
    openWorld: false
    readOnly: true
  name: get-project-sbom
- description: List all container registries and image sources configured as scan targets in Snyk
  hints:
    openWorld: false
    readOnly: true
  name: list-registry-targets
- description: Add a new container registry as a Snyk scan target
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-registry-target
- description: Remove a container scanning project from Snyk monitoring
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-container-project
---
