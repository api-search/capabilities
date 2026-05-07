---
categories: []
consumed_apis: []
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
- get deployment health
- delete deployment
- provision a new managed solr deployment on aws, azure, or google cloud
- devops
- get deployment
- create an on-demand backup of a solr deployment
- full-text search
- get usage data for a billing period
- list all solr deployments
- cloud management
- get deployment configuration and status
- delete a solr deployment and optionally retain its backups
- check the operational health status of a solr deployment (ok, warn, or error)
- list deployment backups
- provision a new solr deployment
- delete a deployment
- list all nodes in a deployment
- search infrastructure
- backup and restore operations
- specific deployment operations
- list all solr and zookeeper nodes in a deployment with their addresses and status
- site search
- check deployment health status
- deployments
- deployment health monitoring
- deployment node management
- usage and billing reporting
- get full configuration and status details for a specific solr deployment
- create deployment backup
- list backups
- list all available backups for a solr deployment
- create deployment
- list all solr deployments in the searchstax account with their status and configuration
- list nodes
- search
- solr
- managed search
- get usage
- solr deployment management
- create backup
- get billable usage data for dedicated solr deployments in a specific month
- list deployments
slug: search-infrastructure-management
source_filename: search-infrastructure-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SearchStax Search Infrastructure Management\n  description: Unified capability for managing SearchStax Solr search infrastructure including deployment lifecycle, health\n    monitoring, backup and restore operations, and usage reporting. Designed for DevOps and platform engineers managing production\n    Solr clusters on AWS, Azure, or Google Cloud.\n  tags:\n  - Search Infrastructure\n  - Solr\n  - Deployments\n  - DevOps\n  - Cloud Management\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SEARCHSTAX_TOKEN: SEARCHSTAX_TOKEN\n    SEARCHSTAX_ACCOUNT: SEARCHSTAX_ACCOUNT\ncapability:\n  consumes:\n  - type: http\n    namespace: searchstax-provisioning\n    baseUri: https://app.searchstax.com/api/rest/v2\n    description: SearchStax Provisioning API for Solr deployment management\n    authentication:\n      type: bearer\n      token: '{{SEARCHSTAX_TOKEN}}'\n    resources:\n    - name: deployments\n\
  \      path: /account/{account_name}/deployment/\n      description: Manage Solr deployments\n      operations:\n      - name: list-deployments\n        method: GET\n        description: List all Solr deployments for the account\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n          description: SearchStax account name\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-deployment\n        method: POST\n        description: Create a new Solr deployment\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n          description: SearchStax account name\n        body:\n          type: json\n          data:\n   \
  \         name: '{{tools.name}}'\n            application: Solr\n            application_version: '{{tools.application_version}}'\n            plan: '{{tools.plan}}'\n            region_id: '{{tools.region_id}}'\n            cloud_provider_id: '{{tools.cloud_provider_id}}'\n            termination_lock: '{{tools.termination_lock}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-detail\n      path: /account/{account_name}/deployment/{uid}/\n      description: Manage a specific deployment\n      operations:\n      - name: get-deployment\n        method: GET\n        description: Get deployment details\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: delete-deployment\n        method: DELETE\n        description: Delete a deployment\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deployment-health\n      path: /account/{account_name}/deployment/{uid}/deployment-health/\n      description: Check deployment health\n      operations:\n      - name: get-deployment-health\n        method: GET\n        description: Get deployment health status\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: backup\n      path: /account/{account_name}/deployment/{uid}/backup/\n      description: Manage deployment backups\n      operations:\n      - name: list-backups\n        method: GET\n        description: List all backups for a deployment\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-backup\n        method: POST\n        description: Create a deployment backup\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n        \
  \  required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nodes\n      path: /account/{account_name}/deployment/{uid}/server/\n      description: Manage deployment nodes\n      operations:\n      - name: list-nodes\n        method: GET\n        description: List all nodes in a deployment\n        inputParameters:\n        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usage\n      path: /account/{account_name}/usage/{year}/{month}/\n      description: View usage and billing data\n      operations:\n      - name: get-usage\n        method: GET\n        description: Get usage data for a billing period\n        inputParameters:\n\
  \        - name: account_name\n          in: path\n          type: string\n          required: true\n        - name: year\n          in: path\n          type: integer\n          required: true\n        - name: month\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: search-infrastructure-api\n    description: Unified REST API for SearchStax Solr infrastructure management.\n    resources:\n    - path: /v1/deployments\n      name: deployments\n      description: Solr deployment management\n      operations:\n      - method: GET\n        name: list-deployments\n        description: List all Solr deployments\n        call: searchstax-provisioning.list-deployments\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-deployment\n\
  \        description: Provision a new Solr deployment\n        call: searchstax-provisioning.create-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{uid}\n      name: deployment-detail\n      description: Specific deployment operations\n      operations:\n      - method: GET\n        name: get-deployment\n        description: Get deployment configuration and status\n        call: searchstax-provisioning.get-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-deployment\n        description: Delete a deployment\n        call: searchstax-provisioning.delete-deployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{uid}/health\n      name: deployment-health\n      description: Deployment health monitoring\n      operations:\n      - method: GET\n        name: get-deployment-health\n       \
  \ description: Check deployment health status\n        call: searchstax-provisioning.get-deployment-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{uid}/backups\n      name: backups\n      description: Backup and restore operations\n      operations:\n      - method: GET\n        name: list-backups\n        description: List deployment backups\n        call: searchstax-provisioning.list-backups\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-backup\n        description: Create deployment backup\n        call: searchstax-provisioning.create-backup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/deployments/{uid}/nodes\n      name: nodes\n      description: Deployment node management\n      operations:\n      - method: GET\n        name: list-nodes\n        description: List all nodes in a deployment\n        call:\
  \ searchstax-provisioning.list-nodes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/usage/{year}/{month}\n      name: usage\n      description: Usage and billing reporting\n      operations:\n      - method: GET\n        name: get-usage\n        description: Get usage data for a billing period\n        call: searchstax-provisioning.get-usage\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: search-infrastructure-mcp\n    transport: http\n    description: MCP server for AI-assisted SearchStax Solr infrastructure management.\n    tools:\n    - name: list-deployments\n      description: List all Solr deployments in the SearchStax account with their status and configuration\n      hints:\n        readOnly: true\n        openWorld: false\n      call: searchstax-provisioning.list-deployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-deployment\n\
  \      description: Provision a new managed Solr deployment on AWS, Azure, or Google Cloud\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: searchstax-provisioning.create-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment\n      description: Get full configuration and status details for a specific Solr deployment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: searchstax-provisioning.get-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-deployment\n      description: Delete a Solr deployment and optionally retain its backups\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: searchstax-provisioning.delete-deployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-deployment-health\n      description: Check the\
  \ operational health status of a Solr deployment (OK, Warn, or Error)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: searchstax-provisioning.get-deployment-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-backups\n      description: List all available backups for a Solr deployment\n      hints:\n        readOnly: true\n        openWorld: false\n      call: searchstax-provisioning.list-backups\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-backup\n      description: Create an on-demand backup of a Solr deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: searchstax-provisioning.create-backup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-nodes\n      description: List all Solr and ZooKeeper nodes in a deployment with their addresses and status\n      hints:\n        readOnly:\
  \ true\n        openWorld: false\n      call: searchstax-provisioning.list-nodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-usage\n      description: Get billable usage data for dedicated Solr deployments in a specific month\n      hints:\n        readOnly: true\n        openWorld: false\n      call: searchstax-provisioning.get-usage\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
