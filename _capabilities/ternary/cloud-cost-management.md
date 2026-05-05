---
api_specs:
- filename: ternary-openapi.yml
  format: yaml
  label: ternary
  slug: ternary
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/ternary/refs/heads/main/openapi/ternary-openapi.yml
categories: []
consumed_apis:
- ternary
description: Workflow capability for FinOps teams managing multi-cloud costs using Ternary. Combines cost allocation, anomaly detection, commitment tracking, budgeting, forecasting, and reporting into a unified workflow for cloud financial operations teams, engineers, and finance stakeholders.
layout: capability
name: Ternary Cloud Cost Management
operations:
- description: List all cost allocation rules
  method: GET
  name: list-cost-allocations
  path: /v1/cost-allocations
- description: Create a new cost allocation rule
  method: POST
  name: create-cost-allocation
  path: /v1/cost-allocations
- description: Get details of a cost allocation rule
  method: GET
  name: get-cost-allocation
  path: /v1/cost-allocations/{allocation_id}
- description: Update a cost allocation rule
  method: PUT
  name: update-cost-allocation
  path: /v1/cost-allocations/{allocation_id}
- description: Delete a cost allocation rule
  method: DELETE
  name: delete-cost-allocation
  path: /v1/cost-allocations/{allocation_id}
- description: List detected cost anomalies
  method: GET
  name: list-anomalies
  path: /v1/anomalies
- description: Get details of a specific anomaly
  method: GET
  name: get-anomaly
  path: /v1/anomalies/{anomaly_id}
- description: Acknowledge a cost anomaly
  method: POST
  name: acknowledge-anomaly
  path: /v1/anomalies/{anomaly_id}/acknowledge
- description: List cloud commitments with utilization data
  method: GET
  name: list-commitments
  path: /v1/commitments
- description: Get details of a commitment
  method: GET
  name: get-commitment
  path: /v1/commitments/{commitment_id}
- description: List cloud cost budgets
  method: GET
  name: list-budgets
  path: /v1/budgets
- description: Create a new cloud cost budget
  method: POST
  name: create-budget
  path: /v1/budgets
- description: Get details of a budget
  method: GET
  name: get-budget
  path: /v1/budgets/{budget_id}
- description: Update a cloud cost budget
  method: PUT
  name: update-budget
  path: /v1/budgets/{budget_id}
- description: Delete a cloud cost budget
  method: DELETE
  name: delete-budget
  path: /v1/budgets/{budget_id}
- description: List saved cost reports
  method: GET
  name: list-reports
  path: /v1/reports
- description: Create a new cost report
  method: POST
  name: create-report
  path: /v1/reports
- description: Execute a saved report and retrieve cost data
  method: POST
  name: run-report
  path: /v1/reports/{report_id}/data
- description: Get Kubernetes pod label configuration
  method: GET
  name: list-kubernetes-pod-labels
  path: /v1/kubernetes/pod-labels
- description: Update Kubernetes pod label configuration
  method: PUT
  name: update-kubernetes-pod-labels
  path: /v1/kubernetes/pod-labels
personas: []
provider_name: Ternary
provider_slug: ternary
search_terms:
- manage a specific cost allocation rule
- update a cost allocation rule
- get details of a cost allocation rule
- update kubernetes pod label configuration for cost allocation
- create a new cost allocation rule
- delete budget
- list detected cost anomalies
- update budget
- list reports
- list cloud commitment purchases (ris, savings plans, cuds) with utilization
- get a specific budget with current spend vs target
- list saved cost reports
- create a new cost report
- finops
- anomaly detection
- list kubernetes pod labels
- multi-cloud
- get anomaly
- update kubernetes pod label configuration
- list cloud commitments with utilization data
- delete a cost allocation rule
- get commitment
- create budget
- get details of a commitment
- cost reports and analytics
- list budgets
- acknowledge a cost anomaly to indicate the team is aware of the spike
- cloud commitment purchases and discount tracking
- get full details of a specific cloud cost anomaly including affected resources
- list commitments
- acknowledge anomaly
- execute a saved cost report and retrieve the resulting cost breakdown data
- get kubernetes pod labels
- acknowledge a detected anomaly
- execute a saved report and retrieve cost data
- get details of a specific cloud commitment including utilization and savings
- acknowledge a cost anomaly
- create a new cloud cost budget with alert thresholds
- create a new cost allocation rule to distribute shared cloud costs
- create cost allocation
- kubernetes pod label configuration for cost allocation
- budgeting
- list cost allocations
- get kubernetes pod label configuration used for cost allocation across clusters
- create a new cloud cost budget
- update a cloud cost budget
- manage a specific cost anomaly
- kubernetes
- update an existing cloud cost budget
- list cloud cost budgets with current spend and forecasted amounts
- cost allocation rules for distributing shared cloud costs
- cost optimization
- ternary
- cloud cost budgets with spend thresholds
- list detected cloud cost anomalies with optional filters by status, provider, and date range
- update cost allocation
- delete cost allocation
- list anomalies
- google cloud
- cloud cost anomalies detected by ml algorithms
- get kubernetes pod label configuration
- get details of a specific cost allocation rule
- list all cost allocation rules
- get details of a specific anomaly
- get budget
- run report
- get details of a budget
- list saved cost reports and dashboards
- list cloud cost budgets
- execute a saved report
- list all cost allocation rules for distributing shared cloud costs across teams
- update an existing cost allocation rule
- details for a specific commitment
- get cost allocation
- manage a specific budget
- cloud cost management
- create report
- delete a cloud cost budget
- update kubernetes pod labels
slug: cloud-cost-management
source_filename: cloud-cost-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ternary Cloud Cost Management\"\n  description: >-\n    Workflow capability for FinOps teams managing multi-cloud costs using\n    Ternary. Combines cost allocation, anomaly detection, commitment tracking,\n    budgeting, forecasting, and reporting into a unified workflow for cloud\n    financial operations teams, engineers, and finance stakeholders.\n  tags:\n    - Ternary\n    - FinOps\n    - Cloud Cost Management\n    - Anomaly Detection\n    - Cost Optimization\n    - Budgeting\n    - Google Cloud\n    - Multi-Cloud\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TERNARY_API_KEY: TERNARY_API_KEY\n\ncapability:\n  consumes:\n    - import: ternary\n      location: ./shared/ternary.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: ternary-cost-management-api\n      description: \"Unified REST API for multi-cloud cost management and FinOps workflows.\"\
  \n      resources:\n        - path: /v1/cost-allocations\n          name: cost-allocations\n          description: \"Cost allocation rules for distributing shared cloud costs\"\n          operations:\n            - method: GET\n              name: list-cost-allocations\n              description: \"List all cost allocation rules\"\n              call: \"ternary.list-cost-allocations\"\n              with:\n                page_size: \"rest.page_size\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cost-allocation\n              description: \"Create a new cost allocation rule\"\n              call: \"ternary.create-cost-allocation\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cost-allocations/{allocation_id}\n          name: cost-allocation\n          description: \"Manage a specific cost allocation rule\"\
  \n          operations:\n            - method: GET\n              name: get-cost-allocation\n              description: \"Get details of a cost allocation rule\"\n              call: \"ternary.get-cost-allocation\"\n              with:\n                allocation_id: \"rest.allocation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-cost-allocation\n              description: \"Update a cost allocation rule\"\n              call: \"ternary.update-cost-allocation\"\n              with:\n                allocation_id: \"rest.allocation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-cost-allocation\n              description: \"Delete a cost allocation rule\"\n              call: \"ternary.delete-cost-allocation\"\n              with:\n                allocation_id:\
  \ \"rest.allocation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/anomalies\n          name: anomalies\n          description: \"Cloud cost anomalies detected by ML algorithms\"\n          operations:\n            - method: GET\n              name: list-anomalies\n              description: \"List detected cost anomalies\"\n              call: \"ternary.list-anomalies\"\n              with:\n                status: \"rest.status\"\n                cloud_provider: \"rest.cloud_provider\"\n                start_date: \"rest.start_date\"\n                end_date: \"rest.end_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/anomalies/{anomaly_id}\n          name: anomaly\n          description: \"Manage a specific cost anomaly\"\n          operations:\n            - method: GET\n              name: get-anomaly\n              description:\
  \ \"Get details of a specific anomaly\"\n              call: \"ternary.get-anomaly\"\n              with:\n                anomaly_id: \"rest.anomaly_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/anomalies/{anomaly_id}/acknowledge\n          name: acknowledge-anomaly\n          description: \"Acknowledge a detected anomaly\"\n          operations:\n            - method: POST\n              name: acknowledge-anomaly\n              description: \"Acknowledge a cost anomaly\"\n              call: \"ternary.acknowledge-anomaly\"\n              with:\n                anomaly_id: \"rest.anomaly_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commitments\n          name: commitments\n          description: \"Cloud commitment purchases and discount tracking\"\n          operations:\n            - method: GET\n              name: list-commitments\n\
  \              description: \"List cloud commitments with utilization data\"\n              call: \"ternary.list-commitments\"\n              with:\n                cloud_provider: \"rest.cloud_provider\"\n                status: \"rest.status\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/commitments/{commitment_id}\n          name: commitment\n          description: \"Details for a specific commitment\"\n          operations:\n            - method: GET\n              name: get-commitment\n              description: \"Get details of a commitment\"\n              call: \"ternary.get-commitment\"\n              with:\n                commitment_id: \"rest.commitment_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/budgets\n          name: budgets\n          description: \"Cloud cost budgets with spend thresholds\"\n          operations:\n\
  \            - method: GET\n              name: list-budgets\n              description: \"List cloud cost budgets\"\n              call: \"ternary.list-budgets\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-budget\n              description: \"Create a new cloud cost budget\"\n              call: \"ternary.create-budget\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/budgets/{budget_id}\n          name: budget\n          description: \"Manage a specific budget\"\n          operations:\n            - method: GET\n              name: get-budget\n              description: \"Get details of a budget\"\n              call: \"ternary.get-budget\"\n              with:\n                budget_id: \"rest.budget_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n            - method: PUT\n              name: update-budget\n              description: \"Update a cloud cost budget\"\n              call: \"ternary.update-budget\"\n              with:\n                budget_id: \"rest.budget_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-budget\n              description: \"Delete a cloud cost budget\"\n              call: \"ternary.delete-budget\"\n              with:\n                budget_id: \"rest.budget_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"Cost reports and analytics\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List saved cost reports\"\n              call: \"ternary.list-reports\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-report\n              description: \"Create a new cost report\"\n              call: \"ternary.create-report\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports/{report_id}/data\n          name: report-data\n          description: \"Execute a saved report\"\n          operations:\n            - method: POST\n              name: run-report\n              description: \"Execute a saved report and retrieve cost data\"\n              call: \"ternary.run-report\"\n              with:\n                report_id: \"rest.report_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/kubernetes/pod-labels\n          name: kubernetes-pod-labels\n          description: \"Kubernetes pod label configuration for cost allocation\"\n\
  \          operations:\n            - method: GET\n              name: list-kubernetes-pod-labels\n              description: \"Get Kubernetes pod label configuration\"\n              call: \"ternary.list-kubernetes-pod-labels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-kubernetes-pod-labels\n              description: \"Update Kubernetes pod label configuration\"\n              call: \"ternary.update-kubernetes-pod-labels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: ternary-cost-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud cost management and FinOps workflows.\"\n      tools:\n        - name: list-cost-allocations\n          description: \"List all cost allocation rules for distributing shared cloud costs across teams\"\
  \n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.list-cost-allocations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cost-allocation\n          description: \"Create a new cost allocation rule to distribute shared cloud costs\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"ternary.create-cost-allocation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-cost-allocation\n          description: \"Get details of a specific cost allocation rule\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.get-cost-allocation\"\n          with:\n            allocation_id: \"tools.allocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n   \
  \     - name: update-cost-allocation\n          description: \"Update an existing cost allocation rule\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"ternary.update-cost-allocation\"\n          with:\n            allocation_id: \"tools.allocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cost-allocation\n          description: \"Delete a cost allocation rule\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ternary.delete-cost-allocation\"\n          with:\n            allocation_id: \"tools.allocation_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-anomalies\n          description: \"List detected cloud cost anomalies with optional filters by status, provider, and date range\"\n       \
  \   hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.list-anomalies\"\n          with:\n            status: \"tools.status\"\n            cloud_provider: \"tools.cloud_provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-anomaly\n          description: \"Get full details of a specific cloud cost anomaly including affected resources\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.get-anomaly\"\n          with:\n            anomaly_id: \"tools.anomaly_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: acknowledge-anomaly\n          description: \"Acknowledge a cost anomaly to indicate the team is aware of the spike\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"ternary.acknowledge-anomaly\"\
  \n          with:\n            anomaly_id: \"tools.anomaly_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-commitments\n          description: \"List cloud commitment purchases (RIs, Savings Plans, CUDs) with utilization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.list-commitments\"\n          with:\n            cloud_provider: \"tools.cloud_provider\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-commitment\n          description: \"Get details of a specific cloud commitment including utilization and savings\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.get-commitment\"\n          with:\n            commitment_id: \"tools.commitment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name:\
  \ list-budgets\n          description: \"List cloud cost budgets with current spend and forecasted amounts\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.list-budgets\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-budget\n          description: \"Create a new cloud cost budget with alert thresholds\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"ternary.create-budget\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-budget\n          description: \"Get a specific budget with current spend vs target\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.get-budget\"\n          with:\n            budget_id: \"tools.budget_id\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: update-budget\n          description: \"Update an existing cloud cost budget\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"ternary.update-budget\"\n          with:\n            budget_id: \"tools.budget_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-budget\n          description: \"Delete a cloud cost budget\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"ternary.delete-budget\"\n          with:\n            budget_id: \"tools.budget_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List saved cost reports and dashboards\"\n          hints:\n            readOnly: true\n            openWorld: false\n  \
  \        call: \"ternary.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: run-report\n          description: \"Execute a saved cost report and retrieve the resulting cost breakdown data\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.run-report\"\n          with:\n            report_id: \"tools.report_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-kubernetes-pod-labels\n          description: \"Get Kubernetes pod label configuration used for cost allocation across clusters\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"ternary.list-kubernetes-pod-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-kubernetes-pod-labels\n          description: \"Update Kubernetes pod label configuration\
  \ for cost allocation\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"ternary.update-kubernetes-pod-labels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ternary/refs/heads/main/capabilities/cloud-cost-management.yaml
tags:
- Ternary
- FinOps
- Cloud Cost Management
- Anomaly Detection
- Cost Optimization
- Budgeting
- Google Cloud
- Multi-Cloud
tools:
- description: List all cost allocation rules for distributing shared cloud costs across teams
  hints:
    openWorld: false
    readOnly: true
  name: list-cost-allocations
- description: Create a new cost allocation rule to distribute shared cloud costs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-cost-allocation
- description: Get details of a specific cost allocation rule
  hints:
    openWorld: false
    readOnly: true
  name: get-cost-allocation
- description: Update an existing cost allocation rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-cost-allocation
- description: Delete a cost allocation rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cost-allocation
- description: List detected cloud cost anomalies with optional filters by status, provider, and date range
  hints:
    openWorld: false
    readOnly: true
  name: list-anomalies
- description: Get full details of a specific cloud cost anomaly including affected resources
  hints:
    openWorld: false
    readOnly: true
  name: get-anomaly
- description: Acknowledge a cost anomaly to indicate the team is aware of the spike
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-anomaly
- description: List cloud commitment purchases (RIs, Savings Plans, CUDs) with utilization
  hints:
    openWorld: false
    readOnly: true
  name: list-commitments
- description: Get details of a specific cloud commitment including utilization and savings
  hints:
    openWorld: false
    readOnly: true
  name: get-commitment
- description: List cloud cost budgets with current spend and forecasted amounts
  hints:
    openWorld: false
    readOnly: true
  name: list-budgets
- description: Create a new cloud cost budget with alert thresholds
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-budget
- description: Get a specific budget with current spend vs target
  hints:
    openWorld: false
    readOnly: true
  name: get-budget
- description: Update an existing cloud cost budget
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-budget
- description: Delete a cloud cost budget
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-budget
- description: List saved cost reports and dashboards
  hints:
    openWorld: false
    readOnly: true
  name: list-reports
- description: Execute a saved cost report and retrieve the resulting cost breakdown data
  hints:
    openWorld: false
    readOnly: true
  name: run-report
- description: Get Kubernetes pod label configuration used for cost allocation across clusters
  hints:
    openWorld: false
    readOnly: true
  name: get-kubernetes-pod-labels
- description: Update Kubernetes pod label configuration for cost allocation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-kubernetes-pod-labels
---
