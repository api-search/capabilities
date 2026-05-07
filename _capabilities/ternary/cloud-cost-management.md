---
categories: []
consumed_apis: []
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
- execute a saved report
- get a specific budget with current spend vs target
- create a new cost allocation rule to distribute shared cloud costs
- list cloud cost budgets
- create report
- list detected cost anomalies
- manage a specific budget
- cost allocation rules for distributing shared cloud costs
- update a cloud cost budget
- cloud commitment purchases and discount tracking
- update budget
- get details of a cost allocation rule
- anomaly detection
- list anomalies
- get budget
- list cloud commitment purchases (ris, savings plans, cuds) with utilization
- list detected cloud cost anomalies with optional filters by status, provider, and date range
- get cost allocation
- delete a cost allocation rule
- google cloud
- acknowledge a detected anomaly
- update kubernetes pod labels
- update a cost allocation rule
- finops
- get kubernetes pod label configuration used for cost allocation across clusters
- list cloud commitments with utilization data
- list reports
- cost optimization
- cloud cost budgets with spend thresholds
- list saved cost reports and dashboards
- get details of a specific anomaly
- create cost allocation
- create budget
- execute a saved cost report and retrieve the resulting cost breakdown data
- ternary
- details for a specific commitment
- create a new cloud cost budget
- cloud cost management
- list all cost allocation rules for distributing shared cloud costs across teams
- run report
- get details of a commitment
- acknowledge a cost anomaly to indicate the team is aware of the spike
- multi-cloud
- get full details of a specific cloud cost anomaly including affected resources
- get anomaly
- get details of a specific cloud commitment including utilization and savings
- kubernetes
- get details of a specific cost allocation rule
- delete cost allocation
- update an existing cost allocation rule
- get kubernetes pod labels
- list budgets
- delete a cloud cost budget
- delete budget
- list commitments
- update kubernetes pod label configuration for cost allocation
- manage a specific cost allocation rule
- acknowledge anomaly
- get kubernetes pod label configuration
- create a new cost allocation rule
- create a new cloud cost budget with alert thresholds
- get details of a budget
- list cloud cost budgets with current spend and forecasted amounts
- list kubernetes pod labels
- execute a saved report and retrieve cost data
- create a new cost report
- acknowledge a cost anomaly
- list cost allocations
- list all cost allocation rules
- cost reports and analytics
- manage a specific cost anomaly
- kubernetes pod label configuration for cost allocation
- cloud cost anomalies detected by ml algorithms
- update cost allocation
- get commitment
- update an existing cloud cost budget
- budgeting
- list saved cost reports
- update kubernetes pod label configuration
slug: cloud-cost-management
source_filename: cloud-cost-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Ternary Cloud Cost Management\n  description: Workflow capability for FinOps teams managing multi-cloud costs using Ternary. Combines cost allocation, anomaly\n    detection, commitment tracking, budgeting, forecasting, and reporting into a unified workflow for cloud financial operations\n    teams, engineers, and finance stakeholders.\n  tags:\n  - Ternary\n  - FinOps\n  - Cloud Cost Management\n  - Anomaly Detection\n  - Cost Optimization\n  - Budgeting\n  - Google Cloud\n  - Multi-Cloud\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TERNARY_API_KEY: TERNARY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: ternary\n    baseUri: https://api.ternary.app\n    description: Ternary FinOps platform REST API\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{env.TERNARY_API_KEY}}'\n      placement: header\n    resources:\n    - name: cost-allocations\n\
  \      path: /v1/cost-allocations\n      description: Cost allocation rules management\n      operations:\n      - name: list-cost-allocations\n        method: GET\n        description: Returns a list of cost allocation rules\n        inputParameters:\n        - name: page_token\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        - name: page_size\n          in: query\n          type: integer\n          required: false\n          description: Number of results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-cost-allocation\n        method: POST\n        description: Creates a new cost allocation rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n\
  \            description: '{{tools.description}}'\n            allocation_type: '{{tools.allocation_type}}'\n            source_labels: '{{tools.source_labels}}'\n            target_cost_centers: '{{tools.target_cost_centers}}'\n      - name: get-cost-allocation\n        method: GET\n        description: Returns details of a specific cost allocation rule\n        inputParameters:\n        - name: allocation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the cost allocation rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-cost-allocation\n        method: PUT\n        description: Updates an existing cost allocation rule\n        inputParameters:\n        - name: allocation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the cost allocation\
  \ rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            allocation_type: '{{tools.allocation_type}}'\n      - name: delete-cost-allocation\n        method: DELETE\n        description: Deletes a cost allocation rule\n        inputParameters:\n        - name: allocation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the cost allocation rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anomalies\n      path: /v1/anomalies\n      description: Cloud cost anomaly detection\n      operations:\n      - name: list-anomalies\n        method: GET\n        description: Returns a list of detected cloud cost anomalies\n        inputParameters:\n        -\
  \ name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by anomaly status\n        - name: cloud_provider\n          in: query\n          type: string\n          required: false\n          description: Filter by cloud provider\n        - name: start_date\n          in: query\n          type: string\n          required: false\n          description: Filter anomalies from this date\n        - name: end_date\n          in: query\n          type: string\n          required: false\n          description: Filter anomalies up to this date\n        - name: page_token\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-anomaly\n        method: GET\n        description: Returns details of a specific cost anomaly\n        inputParameters:\n\
  \        - name: anomaly_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the anomaly\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: acknowledge-anomaly\n        method: POST\n        description: Marks an anomaly as acknowledged\n        inputParameters:\n        - name: anomaly_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the anomaly\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            comment: '{{tools.comment}}'\n    - name: commitments\n      path: /v1/commitments\n      description: Cloud commitment management\n      operations:\n      - name: list-commitments\n        method: GET\n        description:\
  \ Returns a list of cloud commitment purchases\n        inputParameters:\n        - name: cloud_provider\n          in: query\n          type: string\n          required: false\n          description: Filter by cloud provider\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by commitment status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-commitment\n        method: GET\n        description: Returns details of a specific cloud commitment\n        inputParameters:\n        - name: commitment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the commitment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: budgets\n      path: /v1/budgets\n      description:\
  \ Cloud cost budgets and forecasting\n      operations:\n      - name: list-budgets\n        method: GET\n        description: Returns a list of cloud cost budgets\n        inputParameters:\n        - name: page_token\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-budget\n        method: POST\n        description: Creates a new cloud cost budget\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            amount: '{{tools.amount}}'\n            period: '{{tools.period}}'\n            alert_thresholds: '{{tools.alert_thresholds}}'\n      - name: get-budget\n        method: GET\n        description: Returns details\
  \ of a specific budget\n        inputParameters:\n        - name: budget_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the budget\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-budget\n        method: PUT\n        description: Updates an existing cloud cost budget\n        inputParameters:\n        - name: budget_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the budget\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            amount: '{{tools.amount}}'\n      - name: delete-budget\n        method: DELETE\n        description: Deletes a cloud cost budget\n        inputParameters:\n\
  \        - name: budget_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the budget\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reports\n      path: /v1/reports\n      description: Cost reporting and analytics\n      operations:\n      - name: list-reports\n        method: GET\n        description: Returns a list of saved cost reports\n        inputParameters:\n        - name: page_token\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-report\n        method: POST\n        description: Creates a new cost report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            dimensions: '{{tools.dimensions}}'\n            filters: '{{tools.filters}}'\n            time_range: '{{tools.time_range}}'\n      - name: run-report\n        method: POST\n        description: Executes a saved report and returns cost data\n        inputParameters:\n        - name: report_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the report\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            start_date: '{{tools.start_date}}'\n            end_date: '{{tools.end_date}}'\n    - name: kubernetes\n      path: /v1/kubernetes\n      description: Kubernetes cost allocation configuration\n      operations:\n      - name: list-kubernetes-pod-labels\n   \
  \     method: GET\n        description: Returns Kubernetes pod label configuration for cost allocation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-kubernetes-pod-labels\n        method: PUT\n        description: Updates Kubernetes pod label configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            labels: '{{tools.labels}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ternary-cost-management-api\n    description: Unified REST API for multi-cloud cost management and FinOps workflows.\n    resources:\n    - path: /v1/cost-allocations\n      name: cost-allocations\n      description: Cost allocation rules for distributing shared cloud costs\n      operations:\n      - method: GET\n        name: list-cost-allocations\n     \
  \   description: List all cost allocation rules\n        call: ternary.list-cost-allocations\n        with:\n          page_size: rest.page_size\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-cost-allocation\n        description: Create a new cost allocation rule\n        call: ternary.create-cost-allocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cost-allocations/{allocation_id}\n      name: cost-allocation\n      description: Manage a specific cost allocation rule\n      operations:\n      - method: GET\n        name: get-cost-allocation\n        description: Get details of a cost allocation rule\n        call: ternary.get-cost-allocation\n        with:\n          allocation_id: rest.allocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-cost-allocation\n        description: Update a cost\
  \ allocation rule\n        call: ternary.update-cost-allocation\n        with:\n          allocation_id: rest.allocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-cost-allocation\n        description: Delete a cost allocation rule\n        call: ternary.delete-cost-allocation\n        with:\n          allocation_id: rest.allocation_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/anomalies\n      name: anomalies\n      description: Cloud cost anomalies detected by ML algorithms\n      operations:\n      - method: GET\n        name: list-anomalies\n        description: List detected cost anomalies\n        call: ternary.list-anomalies\n        with:\n          status: rest.status\n          cloud_provider: rest.cloud_provider\n          start_date: rest.start_date\n          end_date: rest.end_date\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/anomalies/{anomaly_id}\n      name: anomaly\n      description: Manage a specific cost anomaly\n      operations:\n      - method: GET\n        name: get-anomaly\n        description: Get details of a specific anomaly\n        call: ternary.get-anomaly\n        with:\n          anomaly_id: rest.anomaly_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/anomalies/{anomaly_id}/acknowledge\n      name: acknowledge-anomaly\n      description: Acknowledge a detected anomaly\n      operations:\n      - method: POST\n        name: acknowledge-anomaly\n        description: Acknowledge a cost anomaly\n        call: ternary.acknowledge-anomaly\n        with:\n          anomaly_id: rest.anomaly_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commitments\n      name: commitments\n      description: Cloud commitment purchases and discount tracking\n      operations:\n      - method: GET\n\
  \        name: list-commitments\n        description: List cloud commitments with utilization data\n        call: ternary.list-commitments\n        with:\n          cloud_provider: rest.cloud_provider\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/commitments/{commitment_id}\n      name: commitment\n      description: Details for a specific commitment\n      operations:\n      - method: GET\n        name: get-commitment\n        description: Get details of a commitment\n        call: ternary.get-commitment\n        with:\n          commitment_id: rest.commitment_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/budgets\n      name: budgets\n      description: Cloud cost budgets with spend thresholds\n      operations:\n      - method: GET\n        name: list-budgets\n        description: List cloud cost budgets\n        call: ternary.list-budgets\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-budget\n        description: Create a new cloud cost budget\n        call: ternary.create-budget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/budgets/{budget_id}\n      name: budget\n      description: Manage a specific budget\n      operations:\n      - method: GET\n        name: get-budget\n        description: Get details of a budget\n        call: ternary.get-budget\n        with:\n          budget_id: rest.budget_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-budget\n        description: Update a cloud cost budget\n        call: ternary.update-budget\n        with:\n          budget_id: rest.budget_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-budget\n        description: Delete a cloud cost budget\n\
  \        call: ternary.delete-budget\n        with:\n          budget_id: rest.budget_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports\n      name: reports\n      description: Cost reports and analytics\n      operations:\n      - method: GET\n        name: list-reports\n        description: List saved cost reports\n        call: ternary.list-reports\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-report\n        description: Create a new cost report\n        call: ternary.create-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/reports/{report_id}/data\n      name: report-data\n      description: Execute a saved report\n      operations:\n      - method: POST\n        name: run-report\n        description: Execute a saved report and retrieve cost data\n        call: ternary.run-report\n        with:\n          report_id:\
  \ rest.report_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/kubernetes/pod-labels\n      name: kubernetes-pod-labels\n      description: Kubernetes pod label configuration for cost allocation\n      operations:\n      - method: GET\n        name: list-kubernetes-pod-labels\n        description: Get Kubernetes pod label configuration\n        call: ternary.list-kubernetes-pod-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-kubernetes-pod-labels\n        description: Update Kubernetes pod label configuration\n        call: ternary.update-kubernetes-pod-labels\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: ternary-cost-management-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud cost management and FinOps workflows.\n    tools:\n    - name: list-cost-allocations\n    \
  \  description: List all cost allocation rules for distributing shared cloud costs across teams\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-cost-allocations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cost-allocation\n      description: Create a new cost allocation rule to distribute shared cloud costs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ternary.create-cost-allocation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cost-allocation\n      description: Get details of a specific cost allocation rule\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.get-cost-allocation\n      with:\n        allocation_id: tools.allocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-cost-allocation\n      description: Update an existing\
  \ cost allocation rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ternary.update-cost-allocation\n      with:\n        allocation_id: tools.allocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cost-allocation\n      description: Delete a cost allocation rule\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ternary.delete-cost-allocation\n      with:\n        allocation_id: tools.allocation_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-anomalies\n      description: List detected cloud cost anomalies with optional filters by status, provider, and date range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-anomalies\n      with:\n        status: tools.status\n        cloud_provider: tools.cloud_provider\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: get-anomaly\n      description: Get full details of a specific cloud cost anomaly including affected resources\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.get-anomaly\n      with:\n        anomaly_id: tools.anomaly_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge-anomaly\n      description: Acknowledge a cost anomaly to indicate the team is aware of the spike\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ternary.acknowledge-anomaly\n      with:\n        anomaly_id: tools.anomaly_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-commitments\n      description: List cloud commitment purchases (RIs, Savings Plans, CUDs) with utilization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-commitments\n      with:\n        cloud_provider:\
  \ tools.cloud_provider\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-commitment\n      description: Get details of a specific cloud commitment including utilization and savings\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.get-commitment\n      with:\n        commitment_id: tools.commitment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-budgets\n      description: List cloud cost budgets with current spend and forecasted amounts\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-budgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-budget\n      description: Create a new cloud cost budget with alert thresholds\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: ternary.create-budget\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: get-budget\n      description: Get a specific budget with current spend vs target\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.get-budget\n      with:\n        budget_id: tools.budget_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-budget\n      description: Update an existing cloud cost budget\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ternary.update-budget\n      with:\n        budget_id: tools.budget_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-budget\n      description: Delete a cloud cost budget\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: ternary.delete-budget\n      with:\n        budget_id: tools.budget_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-reports\n\
  \      description: List saved cost reports and dashboards\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-reports\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: run-report\n      description: Execute a saved cost report and retrieve the resulting cost breakdown data\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.run-report\n      with:\n        report_id: tools.report_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-kubernetes-pod-labels\n      description: Get Kubernetes pod label configuration used for cost allocation across clusters\n      hints:\n        readOnly: true\n        openWorld: false\n      call: ternary.list-kubernetes-pod-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-kubernetes-pod-labels\n      description: Update Kubernetes pod label configuration for cost allocation\n\
  \      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: ternary.update-kubernetes-pod-labels\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
