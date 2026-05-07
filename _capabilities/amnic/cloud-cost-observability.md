---
categories: []
consumed_apis: []
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
- get chart data
- get chart filters
- cost optimization
- retrieves cloud cost data by applying custom filters to a saved amnic cost chart.
- retrieve configured filters for a saved cost analysis chart.
- engineering manager integrating cloud cost data into ci/cd pipelines and automated reporting workflows.
- FinOps Practitioner
- retrieve the filter dimensions configured in a saved amnic cost chart for understanding available cost segmentation options.
- kubernetes
- get cost chart data
- get cost chart filters
- retrieve cloud cost data from an amnic saved chart with custom filters for ai-powered finops analysis, anomaly investigation, and cost optimization recommendations.
- cloud cost observability
- Finance Team
- returns the filter dimensions and values configured in a saved amnic cost analyzer chart.
- management and optimization of cloud infrastructure costs across aws, gcp, azure, and kubernetes.
- finance professionals consuming cloud cost reports for budgeting, forecasting, and chargeback allocation.
- cloud cost
- cloud cost management
- azure
- amnic
- google cloud
- finops workflow for retrieving and analyzing cloud cost data programmatically.
- cost observability
- cloud cost management specialist responsible for cost visibility, optimization, and governance across cloud environments.
- retrieve cloud cost data from a saved chart with optional custom filters.
- finops
- Engineering Lead
slug: cloud-cost-observability
source_filename: cloud-cost-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amnic Cloud Cost Observability\n  description: Workflow capability for FinOps practitioners and engineering teams to programmatically retrieve cloud cost\n    data, apply custom filters, and integrate Amnic cost analytics into reporting pipelines and AI-assisted cost optimization\n    workflows.\n  tags:\n  - Amnic\n  - FinOps\n  - Cloud Cost\n  - Cost Observability\n  - Cost Optimization\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AMNIC_API_KEY: AMNIC_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: amnic-api\n    baseUri: https://api.amnic.com/orchestrator\n    description: Amnic Cloud Cost Observability API for retrieving saved chart data and filters.\n    authentication:\n      type: apikey\n      key: X-API-Key\n      value: '{{AMNIC_API_KEY}}'\n      placement: header\n    resources:\n    - name: chart-filters\n      path: /v1/external/view/{uuid}/filters\n      description:\
  \ Retrieve filters configured in a saved Cost Analyzer chart.\n      operations:\n      - name: get-chart-filters\n        method: GET\n        description: Returns the filters configured in a saved chart identified by its UUID.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the saved chart.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chart-data\n      path: /v1/external/view/{uuid}\n      description: Retrieve saved chart cost data with optional custom filters.\n      operations:\n      - name: get-chart-data\n        method: POST\n        description: Retrieves saved chart data by providing additional custom filters.\n        inputParameters:\n        - name: uuid\n          in: path\n          type: string\n          required: true\n          description: The unique identifier\
  \ of the saved chart.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filters: '{{tools.filters}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cloud-cost-api\n    description: Unified REST API for cloud cost observability and FinOps reporting automation.\n    resources:\n    - path: /v1/charts/{uuid}/filters\n      name: cost-chart-filters\n      description: Retrieve configured filters for a saved cost analysis chart.\n      operations:\n      - method: GET\n        name: get-chart-filters\n        description: Returns the filter dimensions and values configured in a saved Amnic Cost Analyzer chart.\n        call: amnic-api.get-chart-filters\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/charts/{uuid}/data\n      name: cost-chart-data\n    \
  \  description: Retrieve cloud cost data from a saved chart with optional custom filters.\n      operations:\n      - method: POST\n        name: get-chart-data\n        description: Retrieves cloud cost data by applying custom filters to a saved Amnic cost chart.\n        call: amnic-api.get-chart-data\n        with:\n          uuid: rest.uuid\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cloud-cost-mcp\n    transport: http\n    description: MCP server for AI-assisted cloud cost analysis and FinOps automation.\n    tools:\n    - name: get-cost-chart-filters\n      description: Retrieve the filter dimensions configured in a saved Amnic cost chart for understanding available cost\n        segmentation options.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amnic-api.get-chart-filters\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-cost-chart-data\n      description: Retrieve cloud cost data from an Amnic saved chart with custom filters for AI-powered FinOps analysis,\n        anomaly investigation, and cost optimization recommendations.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amnic-api.get-chart-data\n      with:\n        uuid: tools.uuid\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
