---
categories: []
consumed_apis: []
description: PerfectScale provides a public API for managing Kubernetes cost optimization, cluster monitoring, workload metrics, and automation audit logs. Available with the EXPERT package.
layout: capability
name: PerfectScale Public API
operations:
- description: Obtain access token
  method: POST
  name: authenticate
  path: /auth/public_auth
- description: List clusters
  method: GET
  name: listclusters
  path: /clusters
- description: Get cluster details
  method: GET
  name: getcluster
  path: /clusters/{cluster_uid}
- description: Remove cluster
  method: DELETE
  name: deletecluster
  path: /clusters/{cluster_uid}
- description: List cluster workloads
  method: GET
  name: listworkloads
  path: /clusters/{cluster_uid}/workloads
- description: Retrieve automation audit logs
  method: POST
  name: getautomationauditlogs
  path: /automation/audit_logs
personas: []
provider_name: PerfectScale
provider_slug: perfectscale
search_terms:
- cost optimization
- remove cluster
- authenticate
- perfectscale
- get cluster details
- listworkloads
- obtain access token
- deletecluster
- kubernetes
- getcluster
- list cluster workloads
- listclusters
- api
- list clusters
- retrieve automation audit logs
- getautomationauditlogs
- finops
slug: perfectscale-capability
source_filename: perfectscale-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PerfectScale Public API\n  description: PerfectScale provides a public API for managing Kubernetes cost optimization, cluster monitoring, workload\n    metrics, and automation audit logs. Available with the EXPERT package.\n  tags:\n  - Perfectscale\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: perfectscale\n    baseUri: https://api.app.perfectscale.io/public/v1\n    description: PerfectScale Public API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PERFECTSCALE_TOKEN}}'\n    resources:\n    - name: auth-public-auth\n      path: /auth/public_auth\n      operations:\n      - name: authenticate\n        method: POST\n        description: Obtain access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters\n      operations:\n\
  \      - name: listclusters\n        method: GET\n        description: List clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters-cluster-uid\n      path: /clusters/{cluster_uid}\n      operations:\n      - name: getcluster\n        method: GET\n        description: Get cluster details\n        inputParameters:\n        - name: cluster_uid\n          in: path\n          type: string\n          required: true\n        - name: period\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecluster\n        method: DELETE\n        description: Remove cluster\n        inputParameters:\n        - name: cluster_uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: clusters-cluster-uid-workloads\n      path: /clusters/{cluster_uid}/workloads\n      operations:\n      - name: listworkloads\n        method: GET\n        description: List cluster workloads\n        inputParameters:\n        - name: cluster_uid\n          in: path\n          type: string\n          required: true\n        - name: period\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: automation-audit-logs\n      path: /automation/audit_logs\n      operations:\n      - name: getautomationauditlogs\n        method: POST\n        description: Retrieve automation audit logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: perfectscale-rest\n    description:\
  \ REST adapter for PerfectScale Public API.\n    resources:\n    - path: /auth/public_auth\n      name: authenticate\n      operations:\n      - method: POST\n        name: authenticate\n        description: Obtain access token\n        call: perfectscale.authenticate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: List clusters\n        call: perfectscale.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{cluster_uid}\n      name: getcluster\n      operations:\n      - method: GET\n        name: getcluster\n        description: Get cluster details\n        call: perfectscale.getcluster\n        with:\n          cluster_uid: rest.cluster_uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{cluster_uid}\n      name: deletecluster\n\
  \      operations:\n      - method: DELETE\n        name: deletecluster\n        description: Remove cluster\n        call: perfectscale.deletecluster\n        with:\n          cluster_uid: rest.cluster_uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/{cluster_uid}/workloads\n      name: listworkloads\n      operations:\n      - method: GET\n        name: listworkloads\n        description: List cluster workloads\n        call: perfectscale.listworkloads\n        with:\n          cluster_uid: rest.cluster_uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /automation/audit_logs\n      name: getautomationauditlogs\n      operations:\n      - method: POST\n        name: getautomationauditlogs\n        description: Retrieve automation audit logs\n        call: perfectscale.getautomationauditlogs\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n\
  \    namespace: perfectscale-mcp\n    transport: http\n    description: MCP adapter for PerfectScale Public API for AI agent use.\n    tools:\n    - name: authenticate\n      description: Obtain access token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: perfectscale.authenticate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: List clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perfectscale.listclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcluster\n      description: Get cluster details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perfectscale.getcluster\n      with:\n        cluster_uid: tools.cluster_uid\n        period: tools.period\n      inputParameters:\n      - name: cluster_uid\n   \
  \     type: string\n        description: cluster_uid\n        required: true\n      - name: period\n        type: string\n        description: period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecluster\n      description: Remove cluster\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: perfectscale.deletecluster\n      with:\n        cluster_uid: tools.cluster_uid\n      inputParameters:\n      - name: cluster_uid\n        type: string\n        description: cluster_uid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkloads\n      description: List cluster workloads\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: perfectscale.listworkloads\n      with:\n        cluster_uid: tools.cluster_uid\n        period: tools.period\n      inputParameters:\n      - name: cluster_uid\n\
  \        type: string\n        description: cluster_uid\n        required: true\n      - name: period\n        type: string\n        description: period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getautomationauditlogs\n      description: Retrieve automation audit logs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: perfectscale.getautomationauditlogs\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PERFECTSCALE_TOKEN: PERFECTSCALE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/perfectscale/refs/heads/main/capabilities/perfectscale-capability.yaml
tags:
- Perfectscale
- API
tools:
- description: Obtain access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: authenticate
- description: List clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: Get cluster details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcluster
- description: Remove cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecluster
- description: List cluster workloads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkloads
- description: Retrieve automation audit logs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getautomationauditlogs
---
