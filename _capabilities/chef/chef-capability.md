---
categories: []
consumed_apis: []
description: REST API for Chef Automate providing visibility into infrastructure convergence, compliance scans, and application deployment. Includes endpoints for nodes, profiles, scans, and reports.
layout: capability
name: Chef Automate API
operations:
- description: List compliance profiles
  method: GET
  name: listcomplianceprofiles
  path: /compliance/profiles
- description: Create a compliance scan job
  method: POST
  name: createscanjob
  path: /compliance/scanner/jobs
- description: Search compliance reports
  method: POST
  name: searchreports
  path: /compliance/reporting/reports
- description: List configuration management nodes
  method: GET
  name: listmanagednodes
  path: /cfgmgmt/nodes
- description: List IAM users
  method: GET
  name: listiamusers
  path: /apis/iam/v2/users
personas: []
provider_name: Chef
provider_slug: chef
search_terms:
- configuration management
- create a compliance scan job
- infrastructure as code
- devops
- application delivery
- listcomplianceprofiles
- listiamusers
- listmanagednodes
- compliance
- habitat
- list configuration management nodes
- inspec
- list iam users
- api
- list compliance profiles
- search compliance reports
- devsecops
- chef
- searchreports
- createscanjob
- automation
slug: chef-capability
source_filename: chef-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Chef Automate API\n  description: REST API for Chef Automate providing visibility into infrastructure convergence, compliance scans, and application\n    deployment. Includes endpoints for nodes, profiles, scans, and reports.\n  tags:\n  - Chef\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: chef\n    baseUri: https://automate.example.com/api/v0\n    description: Chef Automate API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: api-token\n      value: '{{CHEF_TOKEN}}'\n    resources:\n    - name: compliance-profiles\n      path: /compliance/profiles\n      operations:\n      - name: listcomplianceprofiles\n        method: GET\n        description: List compliance profiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-scanner-jobs\n\
  \      path: /compliance/scanner/jobs\n      operations:\n      - name: createscanjob\n        method: POST\n        description: Create a compliance scan job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: compliance-reporting-reports\n      path: /compliance/reporting/reports\n      operations:\n      - name: searchreports\n        method: POST\n        description: Search compliance reports\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cfgmgmt-nodes\n      path: /cfgmgmt/nodes\n      operations:\n      - name: listmanagednodes\n        method: GET\n        description: List configuration management nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apis-iam-v2-users\n      path: /apis/iam/v2/users\n      operations:\n\
  \      - name: listiamusers\n        method: GET\n        description: List IAM users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: chef-rest\n    description: REST adapter for Chef Automate API.\n    resources:\n    - path: /compliance/profiles\n      name: listcomplianceprofiles\n      operations:\n      - method: GET\n        name: listcomplianceprofiles\n        description: List compliance profiles\n        call: chef.listcomplianceprofiles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance/scanner/jobs\n      name: createscanjob\n      operations:\n      - method: POST\n        name: createscanjob\n        description: Create a compliance scan job\n        call: chef.createscanjob\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /compliance/reporting/reports\n\
  \      name: searchreports\n      operations:\n      - method: POST\n        name: searchreports\n        description: Search compliance reports\n        call: chef.searchreports\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cfgmgmt/nodes\n      name: listmanagednodes\n      operations:\n      - method: GET\n        name: listmanagednodes\n        description: List configuration management nodes\n        call: chef.listmanagednodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /apis/iam/v2/users\n      name: listiamusers\n      operations:\n      - method: GET\n        name: listiamusers\n        description: List IAM users\n        call: chef.listiamusers\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: chef-mcp\n    transport: http\n    description: MCP adapter for Chef Automate API for AI agent use.\n    tools:\n    - name: listcomplianceprofiles\n\
  \      description: List compliance profiles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chef.listcomplianceprofiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createscanjob\n      description: Create a compliance scan job\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chef.createscanjob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchreports\n      description: Search compliance reports\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: chef.searchreports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmanagednodes\n      description: List configuration management nodes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chef.listmanagednodes\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: listiamusers\n      description: List IAM users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: chef.listiamusers\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    CHEF_TOKEN: CHEF_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/chef/refs/heads/main/capabilities/chef-capability.yaml
tags:
- Chef
- API
tools:
- description: List compliance profiles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomplianceprofiles
- description: Create a compliance scan job
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createscanjob
- description: Search compliance reports
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchreports
- description: List configuration management nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmanagednodes
- description: List IAM users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listiamusers
---
