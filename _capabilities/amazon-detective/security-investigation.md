---
categories: []
consumed_apis:
- detective
description: Workflow capability for SOC analysts and security engineers to conduct end-to-end security investigations using Amazon Detective. Combines behavior graph management, member account administration, investigation lifecycle management, and indicator analysis into a unified workflow for threat hunting and security forensics.
layout: capability
name: Amazon Detective Security Investigation
operations:
- description: List all behavior graphs
  method: GET
  name: list-graphs
  path: /v1/graphs
- description: Create a new behavior graph
  method: POST
  name: create-graph
  path: /v1/graphs
- description: List member accounts contributing to the behavior graph
  method: GET
  name: list-members
  path: /v1/graphs/{graphArn}/members
- description: Invite AWS accounts to become member accounts
  method: POST
  name: create-members
  path: /v1/graphs/{graphArn}/members
- description: Remove member accounts from the behavior graph
  method: DELETE
  name: delete-members
  path: /v1/graphs/{graphArn}/members
- description: List all investigations in a behavior graph
  method: GET
  name: list-investigations
  path: /v1/investigations
- description: Start a new investigation on an IAM user or role
  method: POST
  name: start-investigation
  path: /v1/investigations
- description: Get results and status of an investigation
  method: GET
  name: get-investigation
  path: /v1/investigations/{investigationId}
- description: Archive or reactivate an investigation
  method: PUT
  name: update-investigation-state
  path: /v1/investigations/{investigationId}
- description: Get indicators of compromise from an investigation
  method: GET
  name: list-indicators
  path: /v1/investigations/{investigationId}/indicators
- description: List data source packages in the behavior graph
  method: GET
  name: list-datasource-packages
  path: /v1/datasources
personas: []
provider_name: Amazon Detective
provider_slug: amazon-detective
search_terms:
- invite aws accounts to become member accounts
- update investigation state
- remove member accounts from a behavior graph
- list detective administrator accounts in the organization
- list all investigations in a behavior graph
- get indicators of compromise from an investigation
- security
- list indicators
- list all behavior graphs
- SOC Analyst
- get the organization behavior graph configuration including auto-enable settings
- get members
- security investigation
- member account management for the behavior graph
- start a new investigation on an iam user or role
- enable additional data source packages like eks audit logs or ad audit logs
- list investigations
- list organization admin accounts
- end-to-end security investigation workflow for soc analysts
- Security Engineer
- delete members
- aws
- list member accounts contributing to the behavior graph
- security investigation lifecycle management
- get the results, severity, and status of a security investigation
- security engineer managing the detective behavior graph, member accounts, and data sources
- invite aws accounts to contribute data to a behavior graph
- list members
- get results and status of an investigation
- list datasource packages
- amazon detective
- end-to-end security investigation using machine learning and graph analysis
- get investigation
- data source package management
- multi-account security management via aws organizations integration
- create a new behavior graph
- list all amazon detective behavior graphs
- create graph
- archive a completed investigation or reactivate an archived one
- managing the detective behavior graph and contributing member accounts
- get detailed membership information for specific accounts
- list data source packages and their ingest status in a behavior graph
- threat hunting
- get indicators of compromise (ttps, flagged ips, impossible travel) from an investigation
- list data source packages in the behavior graph
- start investigation
- forensics
- update datasource packages
- soc
- security operations center analyst using detective to investigate alerts and hunt threats
- investigation
- behavior graph management for security investigation
- create members
- list member accounts contributing data to a behavior graph
- create a new amazon detective behavior graph to begin security monitoring
- individual investigation management
- remove member accounts from the behavior graph
- initiate a detective investigation on a suspicious iam user or role
- describe organization configuration
- list all security investigations with filtering by severity, status, and state
- archive or reactivate an investigation
- list graphs
- indicators of compromise from an investigation
slug: security-investigation
source_filename: security-investigation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Detective Security Investigation\n  description: >-\n    Workflow capability for SOC analysts and security engineers to conduct end-to-end security\n    investigations using Amazon Detective. Combines behavior graph management, member account\n    administration, investigation lifecycle management, and indicator analysis into a unified\n    workflow for threat hunting and security forensics.\n  tags:\n    - Amazon Detective\n    - Security Investigation\n    - Forensics\n    - Threat Hunting\n    - SOC\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_SESSION_TOKEN: AWS_SESSION_TOKEN\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: detective\n      location: ./shared/detective-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n \
  \     namespace: security-investigation-api\n      description: Unified REST API for Amazon Detective security investigation workflows.\n      resources:\n        - path: /v1/graphs\n          name: graphs\n          description: Behavior graph management for security investigation\n          operations:\n            - method: GET\n              name: list-graphs\n              description: List all behavior graphs\n              call: \"detective.list-graphs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-graph\n              description: Create a new behavior graph\n              call: \"detective.create-graph\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/graphs/{graphArn}/members\n          name: members\n          description: Member account management for the behavior graph\n          operations:\n\
  \            - method: GET\n              name: list-members\n              description: List member accounts contributing to the behavior graph\n              call: \"detective.list-members\"\n              with:\n                GraphArn: \"rest.graphArn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-members\n              description: Invite AWS accounts to become member accounts\n              call: \"detective.create-members\"\n              with:\n                GraphArn: \"rest.graphArn\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-members\n              description: Remove member accounts from the behavior graph\n              call: \"detective.delete-members\"\n              with:\n                GraphArn: \"rest.graphArn\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations\n          name: investigations\n          description: Security investigation lifecycle management\n          operations:\n            - method: GET\n              name: list-investigations\n              description: List all investigations in a behavior graph\n              call: \"detective.list-investigations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: start-investigation\n              description: Start a new investigation on an IAM user or role\n              call: \"detective.start-investigation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations/{investigationId}\n          name: investigation\n          description: Individual investigation management\n          operations:\n    \
  \        - method: GET\n              name: get-investigation\n              description: Get results and status of an investigation\n              call: \"detective.get-investigation\"\n              with:\n                InvestigationId: \"rest.investigationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-investigation-state\n              description: Archive or reactivate an investigation\n              call: \"detective.update-investigation-state\"\n              with:\n                InvestigationId: \"rest.investigationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/investigations/{investigationId}/indicators\n          name: indicators\n          description: Indicators of compromise from an investigation\n          operations:\n            - method: GET\n              name: list-indicators\n\
  \              description: Get indicators of compromise from an investigation\n              call: \"detective.list-indicators\"\n              with:\n                InvestigationId: \"rest.investigationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/datasources\n          name: datasources\n          description: Data source package management\n          operations:\n            - method: GET\n              name: list-datasource-packages\n              description: List data source packages in the behavior graph\n              call: \"detective.list-datasource-packages\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: security-investigation-mcp\n      transport: http\n      description: MCP server for AI-assisted security investigation and threat hunting with Amazon Detective.\n      tools:\n      \
  \  - name: list-graphs\n          description: List all Amazon Detective behavior graphs\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"detective.list-graphs\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-graph\n          description: Create a new Amazon Detective behavior graph to begin security monitoring\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"detective.create-graph\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-members\n          description: List member accounts contributing data to a behavior graph\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"detective.list-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-members\n         \
  \ description: Get detailed membership information for specific accounts\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"detective.get-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-members\n          description: Invite AWS accounts to contribute data to a behavior graph\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"detective.create-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-members\n          description: Remove member accounts from a behavior graph\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"detective.delete-members\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: start-investigation\n          description: Initiate a Detective\
  \ investigation on a suspicious IAM user or role\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"detective.start-investigation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-investigation\n          description: Get the results, severity, and status of a security investigation\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"detective.get-investigation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-investigations\n          description: List all security investigations with filtering by severity, status, and state\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"detective.list-investigations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-investigation-state\n\
  \          description: Archive a completed investigation or reactivate an archived one\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"detective.update-investigation-state\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-indicators\n          description: Get indicators of compromise (TTPs, flagged IPs, impossible travel) from an investigation\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"detective.list-indicators\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-datasource-packages\n          description: List data source packages and their ingest status in a behavior graph\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"detective.list-datasource-packages\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: update-datasource-packages\n          description: Enable additional data source packages like EKS audit logs or AD audit logs\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"detective.update-datasource-packages\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-organization-configuration\n          description: Get the organization behavior graph configuration including auto-enable settings\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"detective.describe-organization-configuration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-organization-admin-accounts\n          description: List Detective administrator accounts in the organization\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"detective.list-organization-admin-accounts\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-detective/refs/heads/main/capabilities/security-investigation.yaml
tags:
- Amazon Detective
- Security Investigation
- Forensics
- Threat Hunting
- SOC
- AWS
tools:
- description: List all Amazon Detective behavior graphs
  hints:
    openWorld: true
    readOnly: true
  name: list-graphs
- description: Create a new Amazon Detective behavior graph to begin security monitoring
  hints:
    destructive: false
    readOnly: false
  name: create-graph
- description: List member accounts contributing data to a behavior graph
  hints:
    openWorld: true
    readOnly: true
  name: list-members
- description: Get detailed membership information for specific accounts
  hints:
    openWorld: false
    readOnly: true
  name: get-members
- description: Invite AWS accounts to contribute data to a behavior graph
  hints:
    destructive: false
    readOnly: false
  name: create-members
- description: Remove member accounts from a behavior graph
  hints:
    destructive: true
    readOnly: false
  name: delete-members
- description: Initiate a Detective investigation on a suspicious IAM user or role
  hints:
    destructive: false
    readOnly: false
  name: start-investigation
- description: Get the results, severity, and status of a security investigation
  hints:
    openWorld: false
    readOnly: true
  name: get-investigation
- description: List all security investigations with filtering by severity, status, and state
  hints:
    openWorld: true
    readOnly: true
  name: list-investigations
- description: Archive a completed investigation or reactivate an archived one
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-investigation-state
- description: Get indicators of compromise (TTPs, flagged IPs, impossible travel) from an investigation
  hints:
    openWorld: true
    readOnly: true
  name: list-indicators
- description: List data source packages and their ingest status in a behavior graph
  hints:
    openWorld: true
    readOnly: true
  name: list-datasource-packages
- description: Enable additional data source packages like EKS audit logs or AD audit logs
  hints:
    destructive: false
    readOnly: false
  name: update-datasource-packages
- description: Get the organization behavior graph configuration including auto-enable settings
  hints:
    openWorld: false
    readOnly: true
  name: describe-organization-configuration
- description: List Detective administrator accounts in the organization
  hints:
    openWorld: true
    readOnly: true
  name: list-organization-admin-accounts
---
