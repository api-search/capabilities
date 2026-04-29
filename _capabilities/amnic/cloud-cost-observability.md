---
categories: []
consumed_apis:
- amnic-api
description: Workflow capability for FinOps practitioners and engineering teams to programmatically retrieve cloud cost data, apply custom filters, and integrate Amnic cost analytics into reporting pipelines and AI-assisted cost optimization workflows.
layout: capability
name: Amnic Cloud Cost Observability
operations:
- description: Returns the filter dimensions and values configured in a saved Amnic Cost Analyzer chart.
  method: GET
  name: get-chart-filters
  path: /v1/charts/{uuid}/filters
- description: Retrieves cloud cost data by applying custom filters to a saved Amnic cost chart.
  method: POST
  name: get-chart-data
  path: /v1/charts/{uuid}/data
personas: []
provider_name: Amnic
provider_slug: amnic
search_terms:
- cost observability
- get chart data
- get chart filters
- management and optimization of cloud infrastructure costs across aws, gcp, azure, and kubernetes.
- cost optimization
- engineering manager integrating cloud cost data into ci/cd pipelines and automated reporting workflows.
- retrieve configured filters for a saved cost analysis chart.
- retrieve the filter dimensions configured in a saved amnic cost chart for understanding available cost segmentation options.
- get cost chart data
- retrieves cloud cost data by applying custom filters to a saved amnic cost chart.
- amnic
- azure
- retrieve cloud cost data from an amnic saved chart with custom filters for ai-powered finops analysis, anomaly investigation, and cost optimization recommendations.
- finops workflow for retrieving and analyzing cloud cost data programmatically.
- google cloud
- cloud cost management
- cloud cost management specialist responsible for cost visibility, optimization, and governance across cloud environments.
- cloud cost observability
- finance professionals consuming cloud cost reports for budgeting, forecasting, and chargeback allocation.
- Finance Team
- cloud cost
- aws
- Engineering Lead
- finops
- retrieve cloud cost data from a saved chart with optional custom filters.
- FinOps Practitioner
- kubernetes
- get cost chart filters
- returns the filter dimensions and values configured in a saved amnic cost analyzer chart.
slug: cloud-cost-observability
source_filename: cloud-cost-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Amnic Cloud Cost Observability\"\n  description: \"Workflow capability for FinOps practitioners and engineering teams to programmatically retrieve cloud cost data, apply custom filters, and integrate Amnic cost analytics into reporting pipelines and AI-assisted cost optimization workflows.\"\n  tags:\n    - Amnic\n    - FinOps\n    - Cloud Cost\n    - Cost Observability\n    - Cost Optimization\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMNIC_API_KEY: AMNIC_API_KEY\n\ncapability:\n  consumes:\n    - import: amnic-api\n      location: ./shared/amnic-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cloud-cost-api\n      description: \"Unified REST API for cloud cost observability and FinOps reporting automation.\"\n      resources:\n        - path: /v1/charts/{uuid}/filters\n          name: cost-chart-filters\n          description: \"Retrieve\
  \ configured filters for a saved cost analysis chart.\"\n          operations:\n            - method: GET\n              name: get-chart-filters\n              description: \"Returns the filter dimensions and values configured in a saved Amnic Cost Analyzer chart.\"\n              call: \"amnic-api.get-chart-filters\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/charts/{uuid}/data\n          name: cost-chart-data\n          description: \"Retrieve cloud cost data from a saved chart with optional custom filters.\"\n          operations:\n            - method: POST\n              name: get-chart-data\n              description: \"Retrieves cloud cost data by applying custom filters to a saved Amnic cost chart.\"\n              call: \"amnic-api.get-chart-data\"\n              with:\n                uuid: \"rest.uuid\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cloud-cost-mcp\n      transport: http\n      description: \"MCP server for AI-assisted cloud cost analysis and FinOps automation.\"\n      tools:\n        - name: get-cost-chart-filters\n          description: \"Retrieve the filter dimensions configured in a saved Amnic cost chart for understanding available cost segmentation options.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"amnic-api.get-chart-filters\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cost-chart-data\n          description: \"Retrieve cloud cost data from an Amnic saved chart with custom filters for AI-powered FinOps analysis, anomaly investigation, and cost optimization recommendations.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"amnic-api.get-chart-data\"\n          with:\n            uuid: \"tools.uuid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amnic/refs/heads/main/capabilities/cloud-cost-observability.yaml
tags:
- Amnic
- FinOps
- Cloud Cost
- Cost Observability
- Cost Optimization
tools:
- description: Retrieve the filter dimensions configured in a saved Amnic cost chart for understanding available cost segmentation options.
  hints:
    openWorld: true
    readOnly: true
  name: get-cost-chart-filters
- description: Retrieve cloud cost data from an Amnic saved chart with custom filters for AI-powered FinOps analysis, anomaly investigation, and cost optimization recommendations.
  hints:
    openWorld: true
    readOnly: true
  name: get-cost-chart-data
---
