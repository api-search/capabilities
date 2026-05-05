---
categories: []
consumed_apis:
- stackrox
description: Unified workflow capability for Kubernetes security operations using StackRox. Combines alert triage, policy management, deployment risk analysis, container image vulnerability scanning, compliance checking, and cluster monitoring into a single security operations interface. Designed for security engineers, platform teams, and AI agents operating cloud-native security programs.
layout: capability
name: StackRox Kubernetes Security
operations:
- description: List security alerts
  method: GET
  name: list-alerts
  path: /v1/alerts
- description: Get alert details
  method: GET
  name: get-alert
  path: /v1/alerts/{id}
- description: Resolve an alert
  method: PATCH
  name: resolve-alert
  path: /v1/alerts/{id}
- description: List deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: List container images
  method: GET
  name: list-images
  path: /v1/images
- description: Scan an image for vulnerabilities
  method: POST
  name: scan-image
  path: /v1/images
- description: List security policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: Create a security policy
  method: POST
  name: create-policy
  path: /v1/policies
- description: List available compliance standards
  method: GET
  name: list-compliance-standards
  path: /v1/compliance/standards
- description: Get compliance scan results
  method: GET
  name: get-compliance-results
  path: /v1/compliance/results
- description: List all clusters
  method: GET
  name: list-clusters
  path: /v1/clusters
- description: Search across all resources
  method: GET
  name: search
  path: /v1/search
personas: []
provider_name: StackRox
provider_slug: stackrox
search_terms:
- monitored deployments
- container security
- container images
- scan image
- compliance standards
- list compliance standards
- security
- resolve an alert
- get compliance results
- get compliance scan results
- list all kubernetes clusters registered with stackrox
- open source
- get alert
- kubernetes security
- get deployment
- get alert details
- scan a container image for cves and vulnerabilities
- search across all stackrox resources (alerts, deployments, images, policies)
- list available compliance standards
- list active security policy violation alerts in stackrox
- list all kubernetes deployments monitored by stackrox
- list security policies
- resolve alert
- list deployments
- list security alerts
- compliance results
- single alert
- scan an image for vulnerabilities
- universal search
- list container images
- mark a security alert as resolved
- list alerts
- list container images and their vulnerability status
- get full details for a specific security alert
- search
- vulnerability management
- security policy violation alerts
- security policies
- list all clusters
- list clusters
- get compliance scan results for the cluster
- list stackrox security policies
- compliance
- create a security policy
- list images
- create policy
- kubernetes clusters
- get risk analysis and details for a specific deployment
- search across all resources
- list policies
- kubernetes
- runtime protection
- get details for a specific security policy
- get policy
- list available compliance standards (cis benchmarks, nist, pci-dss)
slug: kubernetes-security
source_filename: kubernetes-security.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"StackRox Kubernetes Security\"\n  description: >-\n    Unified workflow capability for Kubernetes security operations using StackRox.\n    Combines alert triage, policy management, deployment risk analysis, container\n    image vulnerability scanning, compliance checking, and cluster monitoring into\n    a single security operations interface. Designed for security engineers,\n    platform teams, and AI agents operating cloud-native security programs.\n  tags:\n    - Kubernetes Security\n    - Container Security\n    - Compliance\n    - Runtime Protection\n    - Vulnerability Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      STACKROX_API_TOKEN: STACKROX_API_TOKEN\n      STACKROX_CENTRAL_HOST: STACKROX_CENTRAL_HOST\n\ncapability:\n  consumes:\n    - import: stackrox\n      location: ./shared/stackrox-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n     \
  \ namespace: stackrox-security-api\n      description: \"Unified REST API for Kubernetes security operations with StackRox.\"\n      resources:\n        - path: /v1/alerts\n          name: alerts\n          description: \"Security policy violation alerts\"\n          operations:\n            - method: GET\n              name: list-alerts\n              description: \"List security alerts\"\n              call: \"stackrox.list-alerts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alerts/{id}\n          name: alert\n          description: \"Single alert\"\n          operations:\n            - method: GET\n              name: get-alert\n              description: \"Get alert details\"\n              call: \"stackrox.get-alert\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n  \
  \            name: resolve-alert\n              description: \"Resolve an alert\"\n              call: \"stackrox.resolve-alert\"\n              with:\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments\n          name: deployments\n          description: \"Monitored deployments\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List deployments\"\n              call: \"stackrox.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/images\n          name: images\n          description: \"Container images\"\n          operations:\n            - method: GET\n              name: list-images\n              description: \"List container images\"\n              call: \"stackrox.list-images\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: scan-image\n              description: \"Scan an image for vulnerabilities\"\n              call: \"stackrox.scan-image\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/policies\n          name: policies\n          description: \"Security policies\"\n          operations:\n            - method: GET\n              name: list-policies\n              description: \"List security policies\"\n              call: \"stackrox.list-policies\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-policy\n              description: \"Create a security policy\"\n              call: \"stackrox.create-policy\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n\
  \        - path: /v1/compliance/standards\n          name: compliance-standards\n          description: \"Compliance standards\"\n          operations:\n            - method: GET\n              name: list-compliance-standards\n              description: \"List available compliance standards\"\n              call: \"stackrox.list-compliance-standards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/compliance/results\n          name: compliance-results\n          description: \"Compliance results\"\n          operations:\n            - method: GET\n              name: get-compliance-results\n              description: \"Get compliance scan results\"\n              call: \"stackrox.get-compliance-results\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/clusters\n          name: clusters\n          description: \"Kubernetes clusters\"\n  \
  \        operations:\n            - method: GET\n              name: list-clusters\n              description: \"List all clusters\"\n              call: \"stackrox.list-clusters\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/search\n          name: search\n          description: \"Universal search\"\n          operations:\n            - method: GET\n              name: search\n              description: \"Search across all resources\"\n              call: \"stackrox.search\"\n              with:\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: stackrox-security-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Kubernetes security operations.\"\n      tools:\n        - name: list-alerts\n          description: \"List active security policy violation\
  \ alerts in StackRox\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackrox.list-alerts\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-alert\n          description: \"Get full details for a specific security alert\"\n          hints:\n            readOnly: true\n          call: \"stackrox.get-alert\"\n          with:\n            id: \"tools.alert_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: resolve-alert\n          description: \"Mark a security alert as resolved\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"stackrox.resolve-alert\"\n          with:\n            id: \"tools.alert_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-deployments\n\
  \          description: \"List all Kubernetes deployments monitored by StackRox\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackrox.list-deployments\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment\n          description: \"Get risk analysis and details for a specific deployment\"\n          hints:\n            readOnly: true\n          call: \"stackrox.get-deployment\"\n          with:\n            id: \"tools.deployment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-images\n          description: \"List container images and their vulnerability status\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackrox.list-images\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: scan-image\n          description: \"Scan a container image for CVEs and vulnerabilities\"\n          hints:\n            readOnly: false\n          call: \"stackrox.scan-image\"\n          with:\n            image_name: \"tools.image_name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-policies\n          description: \"List StackRox security policies\"\n          hints:\n            readOnly: true\n          call: \"stackrox.list-policies\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-policy\n          description: \"Get details for a specific security policy\"\n          hints:\n            readOnly: true\n          call: \"stackrox.get-policy\"\n          with:\n            id: \"tools.policy_id\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n\n        - name: list-compliance-standards\n          description: \"List available compliance standards (CIS Benchmarks, NIST, PCI-DSS)\"\n          hints:\n            readOnly: true\n          call: \"stackrox.list-compliance-standards\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-compliance-results\n          description: \"Get compliance scan results for the cluster\"\n          hints:\n            readOnly: true\n          call: \"stackrox.get-compliance-results\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-clusters\n          description: \"List all Kubernetes clusters registered with StackRox\"\n          hints:\n            readOnly: true\n          call: \"stackrox.list-clusters\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search\n          description: \"Search across\
  \ all StackRox resources (alerts, deployments, images, policies)\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"stackrox.search\"\n          with:\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/stackrox/refs/heads/main/capabilities/kubernetes-security.yaml
tags:
- Kubernetes Security
- Container Security
- Compliance
- Runtime Protection
- Vulnerability Management
tools:
- description: List active security policy violation alerts in StackRox
  hints:
    openWorld: true
    readOnly: true
  name: list-alerts
- description: Get full details for a specific security alert
  hints:
    readOnly: true
  name: get-alert
- description: Mark a security alert as resolved
  hints:
    idempotent: true
    readOnly: false
  name: resolve-alert
- description: List all Kubernetes deployments monitored by StackRox
  hints:
    openWorld: true
    readOnly: true
  name: list-deployments
- description: Get risk analysis and details for a specific deployment
  hints:
    readOnly: true
  name: get-deployment
- description: List container images and their vulnerability status
  hints:
    openWorld: true
    readOnly: true
  name: list-images
- description: Scan a container image for CVEs and vulnerabilities
  hints:
    readOnly: false
  name: scan-image
- description: List StackRox security policies
  hints:
    readOnly: true
  name: list-policies
- description: Get details for a specific security policy
  hints:
    readOnly: true
  name: get-policy
- description: List available compliance standards (CIS Benchmarks, NIST, PCI-DSS)
  hints:
    readOnly: true
  name: list-compliance-standards
- description: Get compliance scan results for the cluster
  hints:
    readOnly: true
  name: get-compliance-results
- description: List all Kubernetes clusters registered with StackRox
  hints:
    readOnly: true
  name: list-clusters
- description: Search across all StackRox resources (alerts, deployments, images, policies)
  hints:
    openWorld: true
    readOnly: true
  name: search
---
