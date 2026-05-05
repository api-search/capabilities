---
categories: []
consumed_apis:
- searchstax-provisioning
description: Unified capability for managing SearchStax Solr search infrastructure including deployment lifecycle, health monitoring, backup and restore operations, and usage reporting. Designed for DevOps and platform engineers managing production Solr clusters on AWS, Azure, or Google Cloud.
layout: capability
name: SearchStax Search Infrastructure Management
operations:
- description: List all Solr deployments
  method: GET
  name: list-deployments
  path: /v1/deployments
- description: Provision a new Solr deployment
  method: POST
  name: create-deployment
  path: /v1/deployments
- description: Get deployment configuration and status
  method: GET
  name: get-deployment
  path: /v1/deployments/{uid}
- description: Delete a deployment
  method: DELETE
  name: delete-deployment
  path: /v1/deployments/{uid}
- description: Check deployment health status
  method: GET
  name: get-deployment-health
  path: /v1/deployments/{uid}/health
- description: List deployment backups
  method: GET
  name: list-backups
  path: /v1/deployments/{uid}/backups
- description: Create deployment backup
  method: POST
  name: create-backup
  path: /v1/deployments/{uid}/backups
- description: List all nodes in a deployment
  method: GET
  name: list-nodes
  path: /v1/deployments/{uid}/nodes
- description: Get usage data for a billing period
  method: GET
  name: get-usage
  path: /v1/usage/{year}/{month}
personas: []
provider_name: SearchStax
provider_slug: searchstax
search_terms:
- cloud management
- provision a new solr deployment
- list all available backups for a solr deployment
- list deployment backups
- full-text search
- get usage
- get deployment
- search infrastructure
- get deployment configuration and status
- solr deployment management
- get billable usage data for dedicated solr deployments in a specific month
- get usage data for a billing period
- get full configuration and status details for a specific solr deployment
- deployment health monitoring
- create backup
- list deployments
- site search
- usage and billing reporting
- list all solr and zookeeper nodes in a deployment with their addresses and status
- deployments
- devops
- create deployment backup
- backup and restore operations
- delete deployment
- create deployment
- get deployment health
- delete a solr deployment and optionally retain its backups
- check the operational health status of a solr deployment (ok, warn, or error)
- create an on-demand backup of a solr deployment
- search
- delete a deployment
- solr
- list nodes
- deployment node management
- list backups
- list all nodes in a deployment
- specific deployment operations
- provision a new managed solr deployment on aws, azure, or google cloud
- list all solr deployments
- list all solr deployments in the searchstax account with their status and configuration
- check deployment health status
- managed search
slug: search-infrastructure-management
source_filename: search-infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SearchStax Search Infrastructure Management\"\n  description: >-\n    Unified capability for managing SearchStax Solr search infrastructure including\n    deployment lifecycle, health monitoring, backup and restore operations, and usage\n    reporting. Designed for DevOps and platform engineers managing production Solr\n    clusters on AWS, Azure, or Google Cloud.\n  tags:\n    - Search Infrastructure\n    - Solr\n    - Deployments\n    - DevOps\n    - Cloud Management\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SEARCHSTAX_TOKEN: SEARCHSTAX_TOKEN\n      SEARCHSTAX_ACCOUNT: SEARCHSTAX_ACCOUNT\n\ncapability:\n  consumes:\n    - import: searchstax-provisioning\n      location: ./shared/provisioning.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: search-infrastructure-api\n      description: \"Unified REST API for SearchStax Solr infrastructure management.\"\
  \n      resources:\n        - path: /v1/deployments\n          name: deployments\n          description: \"Solr deployment management\"\n          operations:\n            - method: GET\n              name: list-deployments\n              description: \"List all Solr deployments\"\n              call: \"searchstax-provisioning.list-deployments\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-deployment\n              description: \"Provision a new Solr deployment\"\n              call: \"searchstax-provisioning.create-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{uid}\n          name: deployment-detail\n          description: \"Specific deployment operations\"\n          operations:\n            - method: GET\n              name: get-deployment\n              description: \"Get\
  \ deployment configuration and status\"\n              call: \"searchstax-provisioning.get-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-deployment\n              description: \"Delete a deployment\"\n              call: \"searchstax-provisioning.delete-deployment\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{uid}/health\n          name: deployment-health\n          description: \"Deployment health monitoring\"\n          operations:\n            - method: GET\n              name: get-deployment-health\n              description: \"Check deployment health status\"\n              call: \"searchstax-provisioning.get-deployment-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{uid}/backups\n\
  \          name: backups\n          description: \"Backup and restore operations\"\n          operations:\n            - method: GET\n              name: list-backups\n              description: \"List deployment backups\"\n              call: \"searchstax-provisioning.list-backups\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-backup\n              description: \"Create deployment backup\"\n              call: \"searchstax-provisioning.create-backup\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/deployments/{uid}/nodes\n          name: nodes\n          description: \"Deployment node management\"\n          operations:\n            - method: GET\n              name: list-nodes\n              description: \"List all nodes in a deployment\"\n              call: \"searchstax-provisioning.list-nodes\"\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/usage/{year}/{month}\n          name: usage\n          description: \"Usage and billing reporting\"\n          operations:\n            - method: GET\n              name: get-usage\n              description: \"Get usage data for a billing period\"\n              call: \"searchstax-provisioning.get-usage\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: search-infrastructure-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SearchStax Solr infrastructure management.\"\n      tools:\n        - name: list-deployments\n          description: \"List all Solr deployments in the SearchStax account with their status and configuration\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.list-deployments\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-deployment\n          description: \"Provision a new managed Solr deployment on AWS, Azure, or Google Cloud\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"searchstax-provisioning.create-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment\n          description: \"Get full configuration and status details for a specific Solr deployment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.get-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-deployment\n          description: \"Delete a Solr deployment and optionally retain its backups\"\n          hints:\n           \
  \ readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"searchstax-provisioning.delete-deployment\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-deployment-health\n          description: \"Check the operational health status of a Solr deployment (OK, Warn, or Error)\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.get-deployment-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-backups\n          description: \"List all available backups for a Solr deployment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.list-backups\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-backup\n          description: \"Create\
  \ an on-demand backup of a Solr deployment\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"searchstax-provisioning.create-backup\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-nodes\n          description: \"List all Solr and ZooKeeper nodes in a deployment with their addresses and status\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.list-nodes\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-usage\n          description: \"Get billable usage data for dedicated Solr deployments in a specific month\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"searchstax-provisioning.get-usage\"\n          outputParameters:\n            - type: object\n              mapping:\
  \ \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/searchstax/refs/heads/main/capabilities/search-infrastructure-management.yaml
tags:
- Search Infrastructure
- Solr
- Deployments
- DevOps
- Cloud Management
tools:
- description: List all Solr deployments in the SearchStax account with their status and configuration
  hints:
    openWorld: false
    readOnly: true
  name: list-deployments
- description: Provision a new managed Solr deployment on AWS, Azure, or Google Cloud
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-deployment
- description: Get full configuration and status details for a specific Solr deployment
  hints:
    openWorld: false
    readOnly: true
  name: get-deployment
- description: Delete a Solr deployment and optionally retain its backups
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-deployment
- description: Check the operational health status of a Solr deployment (OK, Warn, or Error)
  hints:
    openWorld: false
    readOnly: true
  name: get-deployment-health
- description: List all available backups for a Solr deployment
  hints:
    openWorld: false
    readOnly: true
  name: list-backups
- description: Create an on-demand backup of a Solr deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-backup
- description: List all Solr and ZooKeeper nodes in a deployment with their addresses and status
  hints:
    openWorld: false
    readOnly: true
  name: list-nodes
- description: Get billable usage data for dedicated Solr deployments in a specific month
  hints:
    openWorld: false
    readOnly: true
  name: get-usage
---
