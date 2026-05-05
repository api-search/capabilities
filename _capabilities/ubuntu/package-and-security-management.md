---
categories: []
consumed_apis:
- snap-store
- ubuntu-cve
description: Workflow capability combining the Snap Store API (package discovery and management) and Ubuntu Security CVE API (vulnerability intelligence). Supports DevOps engineers, system administrators, and security teams managing Ubuntu deployments.
layout: capability
name: Ubuntu Package and Security Management
operations:
- description: Search for snap packages in the Snap Store.
  method: GET
  name: search-snaps
  path: /v1/snaps
- description: Get detailed information about a snap.
  method: GET
  name: get-snap-info
  path: /v1/snaps/{snap_name}
- description: List all available snap categories.
  method: GET
  name: list-snap-categories
  path: /v1/snap-categories
- description: Query CVEs affecting Ubuntu packages.
  method: GET
  name: list-cves
  path: /v1/cves
- description: List Ubuntu Security Notices for vulnerabilities.
  method: GET
  name: list-security-notices
  path: /v1/security-notices
personas: []
provider_name: Ubuntu
provider_slug: ubuntu
search_terms:
- snap package search and discovery.
- query cves affecting ubuntu packages.
- containers
- search for snap packages in the canonical snap store.
- security
- cloud
- enterprise
- open source
- get detailed information about a snap.
- list cves
- list all available snap categories.
- list ubuntu security notices for a specific release.
- cve
- snap
- list security notices
- query ubuntu cves
- ubuntu
- ubuntu cve vulnerability database.
- search snaps
- get snap info
- devops
- list ubuntu security notices for vulnerabilities.
- individual snap package details.
- query cves affecting ubuntu packages by package name, priority, or keyword.
- search for snap packages in the snap store.
- linux
- list snap categories
- list all available snap store categories.
- get detailed information about a specific snap package.
- ubuntu security notices.
- get snap details
- canonical
- package management
- snap store categories.
slug: package-and-security-management
source_filename: package-and-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ubuntu Package and Security Management\"\n  description: >-\n    Workflow capability combining the Snap Store API (package discovery and management)\n    and Ubuntu Security CVE API (vulnerability intelligence). Supports DevOps engineers,\n    system administrators, and security teams managing Ubuntu deployments.\n  tags:\n    - Ubuntu\n    - Package Management\n    - Security\n    - Snap\n    - CVE\n    - Canonical\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: snap-store\n      location: ./shared/snap-store.yaml\n    - import: ubuntu-cve\n      location: ./shared/security-cve.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ubuntu-pkg-security-api\n      description: \"Unified REST API for Ubuntu package management and security intelligence.\"\n      resources:\n        - path: /v1/snaps\n          name: snaps\n\
  \          description: \"Snap package search and discovery.\"\n          operations:\n            - method: GET\n              name: search-snaps\n              description: \"Search for snap packages in the Snap Store.\"\n              call: \"snap-store.search-snaps\"\n              with:\n                q: \"rest.q\"\n                category: \"rest.category\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/snaps/{snap_name}\n          name: snap\n          description: \"Individual snap package details.\"\n          operations:\n            - method: GET\n              name: get-snap-info\n              description: \"Get detailed information about a snap.\"\n              call: \"snap-store.get-snap-info\"\n              with:\n                snap_name: \"rest.snap_name\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/snap-categories\n\
  \          name: snap-categories\n          description: \"Snap Store categories.\"\n          operations:\n            - method: GET\n              name: list-snap-categories\n              description: \"List all available snap categories.\"\n              call: \"snap-store.list-snap-categories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/cves\n          name: cves\n          description: \"Ubuntu CVE vulnerability database.\"\n          operations:\n            - method: GET\n              name: list-cves\n              description: \"Query CVEs affecting Ubuntu packages.\"\n              call: \"ubuntu-cve.list-cves\"\n              with:\n                q: \"rest.q\"\n                package: \"rest.package\"\n                priority: \"rest.priority\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n  \
  \                mapping: \"$.\"\n\n        - path: /v1/security-notices\n          name: security-notices\n          description: \"Ubuntu Security Notices.\"\n          operations:\n            - method: GET\n              name: list-security-notices\n              description: \"List Ubuntu Security Notices for vulnerabilities.\"\n              call: \"ubuntu-cve.list-notices\"\n              with:\n                release: \"rest.release\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ubuntu-pkg-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Ubuntu package discovery and security analysis.\"\n      tools:\n        - name: search-snaps\n          description: \"Search for snap packages in the Canonical Snap Store.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"snap-store.search-snaps\"\n          with:\n            q: \"tools.query\"\n            category: \"tools.category\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-snap-details\n          description: \"Get detailed information about a specific snap package.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"snap-store.get-snap-info\"\n          with:\n            snap_name: \"tools.snap_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-snap-categories\n          description: \"List all available Snap Store categories.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"snap-store.list-snap-categories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-ubuntu-cves\n\
  \          description: \"Query CVEs affecting Ubuntu packages by package name, priority, or keyword.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ubuntu-cve.list-cves\"\n          with:\n            q: \"tools.query\"\n            package: \"tools.package\"\n            priority: \"tools.priority\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-security-notices\n          description: \"List Ubuntu Security Notices for a specific release.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ubuntu-cve.list-notices\"\n          with:\n            release: \"tools.release\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ubuntu/refs/heads/main/capabilities/package-and-security-management.yaml
tags:
- Ubuntu
- Package Management
- Security
- Snap
- CVE
- Canonical
tools:
- description: Search for snap packages in the Canonical Snap Store.
  hints:
    openWorld: true
    readOnly: true
  name: search-snaps
- description: Get detailed information about a specific snap package.
  hints:
    openWorld: true
    readOnly: true
  name: get-snap-details
- description: List all available Snap Store categories.
  hints:
    openWorld: true
    readOnly: true
  name: list-snap-categories
- description: Query CVEs affecting Ubuntu packages by package name, priority, or keyword.
  hints:
    openWorld: true
    readOnly: true
  name: query-ubuntu-cves
- description: List Ubuntu Security Notices for a specific release.
  hints:
    openWorld: true
    readOnly: true
  name: list-security-notices
---
