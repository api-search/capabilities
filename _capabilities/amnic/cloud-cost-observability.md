---
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
- retrieve the filter dimensions configured in a saved amnic cost chart for understanding available cost segmentation options.
- finops
- finance professionals consuming cloud cost reports for budgeting, forecasting, and chargeback allocation.
- aws
- kubernetes
- retrieve cloud cost data from an amnic saved chart with custom filters for ai-powered finops analysis, anomaly investigation, and cost optimization recommendations.
- cloud cost management specialist responsible for cost visibility, optimization, and governance across cloud environments.
- amnic
- get chart data
- google cloud
- azure
- cloud cost management
- FinOps Practitioner
- Finance Team
- finops workflow for retrieving and analyzing cloud cost data programmatically.
- get cost chart data
- Engineering Lead
- cost observability
- get cost chart filters
- engineering manager integrating cloud cost data into ci/cd pipelines and automated reporting workflows.
- retrieve cloud cost data from a saved chart with optional custom filters.
- management and optimization of cloud infrastructure costs across aws, gcp, azure, and kubernetes.
- cost optimization
- cloud cost observability
- returns the filter dimensions and values configured in a saved amnic cost analyzer chart.
- cloud cost
- get chart filters
- retrieves cloud cost data by applying custom filters to a saved amnic cost chart.
- retrieve configured filters for a saved cost analysis chart.
slug: cloud-cost-observability
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
