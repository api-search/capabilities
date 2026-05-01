---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Cloud Cost Finops
operations: []
personas: []
provider_name: CloudZero
provider_slug: cloudzero
search_terms:
- finops
- cost allocation
- cloud cost management
- unit economics
- telemetry
- budgets
- cost optimization
slug: cloud-cost-finops
source_filename: cloud-cost-finops.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for CloudZero.\n# Capabilities map FinOps verbs against the CloudZero V2 REST API: billing\n# queries, insights, budgets, allocation telemetry, unit metric telemetry,\n# and AnyCost ingestion.\nprovider: cloudzero\nname: CloudZero\ndescription: >-\n  Capabilities cover querying billing costs and dimensions, managing\n  insights and budgets, sending allocation and unit metric telemetry,\n  and ingesting cost data from any source via the AnyCost framework.\ncapabilities:\n  - id: cloudzero.billing.costs\n    name: Query billing costs\n    description: Return cost rows for a date range with selected dimensions and metrics.\n    api: cloudzero:billing\n    inputs:\n      - start_date\n      - end_date\n      - dimensions\n      - metrics\n      - filter\n      - page\n      - page_size\n    outputs:\n      - results\n      - total\n\n  - id: cloudzero.billing.dimensions\n    name: List billing dimensions\n    description: Return the set of dimensions\
  \ available for billing queries.\n    api: cloudzero:billing\n    outputs:\n      - dimensions\n\n  - id: cloudzero.insights.list\n    name: List insights\n    description: Return cost insights and recommendations.\n    api: cloudzero:insights\n    inputs:\n      - page\n      - page_size\n      - status\n      - severity\n    outputs:\n      - items\n      - total\n\n  - id: cloudzero.insights.create\n    name: Create insight\n    description: Record a new actionable cost insight.\n    api: cloudzero:insights\n    inputs:\n      - title\n      - description\n      - severity\n      - estimated_savings\n      - assigned_to\n    outputs:\n      - insight_id\n      - status\n\n  - id: cloudzero.insights.update\n    name: Update insight\n    description: Update status, owner, or savings estimate of an existing insight.\n    api: cloudzero:insights\n    inputs:\n      - insight_id\n      - status\n      - assigned_to\n      - notes\n    outputs:\n      - status\n\n  - id: cloudzero.insights.delete\n\
  \    name: Delete insight\n    description: Remove an insight from the platform.\n    api: cloudzero:insights\n    inputs:\n      - insight_id\n    outputs:\n      - status\n\n  - id: cloudzero.budgets.list\n    name: List budgets\n    description: Return configured spend budgets and current consumption.\n    api: cloudzero:budgets\n    inputs:\n      - page\n      - page_size\n    outputs:\n      - items\n      - total\n\n  - id: cloudzero.budgets.create\n    name: Create budget\n    description: Create a new cost-and-usage budget with thresholds and alerts.\n    api: cloudzero:budgets\n    inputs:\n      - name\n      - amount\n      - currency\n      - period\n      - thresholds\n      - filter\n    outputs:\n      - budget_id\n      - status\n\n  - id: cloudzero.budgets.update\n    name: Update budget\n    description: Update amount, thresholds, or alert routing on an existing budget.\n    api: cloudzero:budgets\n    inputs:\n      - budget_id\n      - amount\n      - thresholds\n\
  \    outputs:\n      - status\n\n  - id: cloudzero.budgets.delete\n    name: Delete budget\n    description: Remove a budget definition.\n    api: cloudzero:budgets\n    inputs:\n      - budget_id\n    outputs:\n      - status\n\n  - id: cloudzero.allocation-telemetry.sum\n    name: Send allocation telemetry (sum)\n    description: Submit allocation values that are summed into the named stream.\n    api: cloudzero:allocation-telemetry\n    inputs:\n      - stream_name\n      - records\n    outputs:\n      - accepted\n      - rejected\n\n  - id: cloudzero.allocation-telemetry.replace\n    name: Replace allocation telemetry\n    description: Replace allocation values for a date range in the named stream.\n    api: cloudzero:allocation-telemetry\n    inputs:\n      - stream_name\n      - records\n      - start_date\n      - end_date\n    outputs:\n      - status\n\n  - id: cloudzero.allocation-telemetry.delete\n    name: Delete allocation telemetry\n    description: Delete allocation telemetry\
  \ for a stream and date range.\n    api: cloudzero:allocation-telemetry\n    inputs:\n      - stream_name\n      - start_date\n      - end_date\n    outputs:\n      - status\n\n  - id: cloudzero.unit-metric-telemetry.send\n    name: Send unit metric telemetry\n    description: Submit unit-metric records (cost-per-customer, cost-per-transaction).\n    api: cloudzero:unit-metric-telemetry\n    inputs:\n      - stream_name\n      - records\n    outputs:\n      - accepted\n      - rejected\n\n  - id: cloudzero.unit-metric-telemetry.delete\n    name: Delete unit metric telemetry\n    description: Delete unit-metric records for a stream.\n    api: cloudzero:unit-metric-telemetry\n    inputs:\n      - stream_name\n      - start_date\n      - end_date\n    outputs:\n      - status\n\n  - id: cloudzero.anycost.ingest\n    name: Ingest AnyCost billing drop\n    description: Upload a Common Bill Format (CBF) billing drop for a connection.\n    api: cloudzero:anycost\n    inputs:\n      - connection_id\n\
  \      - month\n      - billing_drop\n    outputs:\n      - drop_id\n      - status\n\n  - id: cloudzero.anycost.list-drops\n    name: List AnyCost billing drops\n    description: List historical billing drops for a connection.\n    api: cloudzero:anycost\n    inputs:\n      - connection_id\n    outputs:\n      - items\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudzero/refs/heads/main/capabilities/cloud-cost-finops.yaml
tags: []
tools: []
---
