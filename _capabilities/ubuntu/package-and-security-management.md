---
categories: []
consumed_apis: []
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
- ubuntu cve vulnerability database.
- search for snap packages in the canonical snap store.
- list all available snap store categories.
- query ubuntu cves
- containers
- devops
- ubuntu
- list cves
- snap store categories.
- get detailed information about a snap.
- list ubuntu security notices for a specific release.
- individual snap package details.
- list all available snap categories.
- list security notices
- open source
- search snaps
- cve
- get snap details
- linux
- query cves affecting ubuntu packages.
- query cves affecting ubuntu packages by package name, priority, or keyword.
- list snap categories
- search for snap packages in the snap store.
- canonical
- enterprise
- list ubuntu security notices for vulnerabilities.
- snap
- cloud
- get detailed information about a specific snap package.
- ubuntu security notices.
- snap package search and discovery.
- get snap info
- security
- package management
slug: package-and-security-management
source_filename: package-and-security-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ubuntu Package and Security Management\n  description: Workflow capability combining the Snap Store API (package discovery and management) and Ubuntu Security CVE\n    API (vulnerability intelligence). Supports DevOps engineers, system administrators, and security teams managing Ubuntu\n    deployments.\n  tags:\n  - Ubuntu\n  - Package Management\n  - Security\n  - Snap\n  - CVE\n  - Canonical\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: snap-store\n    baseUri: https://api.snapcraft.io\n    description: Snap Store Devices API for snap discovery and management.\n    resources:\n    - name: snap-search\n      path: /v2/snaps/search\n      description: Search for snaps in the Snap Store.\n      operations:\n      - name: search-snaps\n        method: GET\n        description: Search for snaps by name, keyword, or category.\n        inputParameters:\n\
  \        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query string.\n        - name: category\n          in: query\n          type: string\n          required: false\n          description: Filter by snap category.\n        - name: Snap-Device-Series\n          in: header\n          type: string\n          required: true\n          description: 'Snap device series (default: 16).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snap-info\n      path: /v2/snaps/info/{snap_name}\n      description: Detailed information about a specific snap.\n      operations:\n      - name: get-snap-info\n        method: GET\n        description: Get detailed information about a snap and its released revisions.\n        inputParameters:\n        - name: snap_name\n          in: path\n          type: string\n          required: true\n          description:\
  \ The snap package name.\n        - name: Snap-Device-Series\n          in: header\n          type: string\n          required: true\n          description: 'Snap device series (default: 16).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: snap-categories\n      path: /v2/snaps/categories\n      description: Available snap categories.\n      operations:\n      - name: list-snap-categories\n        method: GET\n        description: Returns all available snap categories in the store.\n        inputParameters:\n        - name: Snap-Device-Series\n          in: header\n          type: string\n          required: true\n          description: 'Snap device series (default: 16).'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: ubuntu-cve\n    baseUri: https://ubuntu.com/security\n    description:\
  \ Ubuntu Security CVE API for vulnerability and notice queries.\n    resources:\n    - name: cves\n      path: /cves.json\n      description: Ubuntu CVE database query.\n      operations:\n      - name: list-cves\n        method: GET\n        description: Returns a paginated list of CVEs affecting Ubuntu packages.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query for CVE IDs or descriptions.\n        - name: package\n          in: query\n          type: string\n          required: false\n          description: Filter by affected package name.\n        - name: priority\n          in: query\n          type: string\n          required: false\n          description: Filter by priority level (critical, high, medium, low, negligible).\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name:\
  \ limit\n          in: query\n          type: integer\n          required: false\n          description: Number of CVEs per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices\n      path: /notices.json\n      description: Ubuntu Security Notices.\n      operations:\n      - name: list-notices\n        method: GET\n        description: Returns Ubuntu Security Notices for published vulnerabilities.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of notices per page.\n        - name: release\n          in: query\n          type: string\n          required: false\n          description: Filter by Ubuntu release codename.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ubuntu-pkg-security-api\n    description: Unified REST API for Ubuntu package management and security intelligence.\n    resources:\n    - path: /v1/snaps\n      name: snaps\n      description: Snap package search and discovery.\n      operations:\n      - method: GET\n        name: search-snaps\n        description: Search for snap packages in the Snap Store.\n        call: snap-store.search-snaps\n        with:\n          q: rest.q\n          category: rest.category\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/snaps/{snap_name}\n      name: snap\n      description: Individual snap package details.\n      operations:\n      - method: GET\n        name: get-snap-info\n        description: Get detailed information about a snap.\n        call: snap-store.get-snap-info\n        with:\n    \
  \      snap_name: rest.snap_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/snap-categories\n      name: snap-categories\n      description: Snap Store categories.\n      operations:\n      - method: GET\n        name: list-snap-categories\n        description: List all available snap categories.\n        call: snap-store.list-snap-categories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cves\n      name: cves\n      description: Ubuntu CVE vulnerability database.\n      operations:\n      - method: GET\n        name: list-cves\n        description: Query CVEs affecting Ubuntu packages.\n        call: ubuntu-cve.list-cves\n        with:\n          q: rest.q\n          package: rest.package\n          priority: rest.priority\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/security-notices\n   \
  \   name: security-notices\n      description: Ubuntu Security Notices.\n      operations:\n      - method: GET\n        name: list-security-notices\n        description: List Ubuntu Security Notices for vulnerabilities.\n        call: ubuntu-cve.list-notices\n        with:\n          release: rest.release\n          limit: rest.limit\n          offset: rest.offset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ubuntu-pkg-security-mcp\n    transport: http\n    description: MCP server for AI-assisted Ubuntu package discovery and security analysis.\n    tools:\n    - name: search-snaps\n      description: Search for snap packages in the Canonical Snap Store.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: snap-store.search-snaps\n      with:\n        q: tools.query\n        category: tools.category\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-snap-details\n\
  \      description: Get detailed information about a specific snap package.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: snap-store.get-snap-info\n      with:\n        snap_name: tools.snap_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-snap-categories\n      description: List all available Snap Store categories.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: snap-store.list-snap-categories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: query-ubuntu-cves\n      description: Query CVEs affecting Ubuntu packages by package name, priority, or keyword.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ubuntu-cve.list-cves\n      with:\n        q: tools.query\n        package: tools.package\n        priority: tools.priority\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-security-notices\n      description: List Ubuntu Security Notices for a specific release.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: ubuntu-cve.list-notices\n      with:\n        release: tools.release\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
