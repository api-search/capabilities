---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Cloud Cost Finops
operations: []
personas: []
provider_name: Cloudability
provider_slug: cloudability
search_terms:
- cloud cost management
- multi-cloud
- cost optimization
- recommendations
- reporting
- finops
slug: cloud-cost-finops
source_filename: cloud-cost-finops.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Cloudability (Apptio / IBM).\n# Capabilities map FinOps verbs against the Cloudability v3 REST API:\n# reporting, business mappings, rightsizing, anomalies, vendor onboarding,\n# views, and budgets.\nprovider: cloudability\nname: Cloudability\ndescription: >-\n  Capabilities cover building cost-and-usage reports, managing business\n  mapping allocation rules, surfacing rightsizing recommendations, querying\n  cost anomalies, onboarding cloud vendor credentials, and managing views\n  and budgets across AWS, Azure, GCP and other cloud accounts.\ncapabilities:\n  - id: cloudability.reporting.run\n    name: Run cost report\n    description: Build and execute a cost-and-usage query for a date range.\n    api: cloudability:api-v3\n    inputs:\n      - metrics\n      - dimensions\n      - filters\n      - start_date\n      - end_date\n      - sort\n    outputs:\n      - results\n      - row_count\n\n  - id: cloudability.reporting.dimensions\n   \
  \ name: List reporting dimensions\n    description: Return the list of dimensions available for reporting queries.\n    api: cloudability:api-v3\n    outputs:\n      - dimensions\n\n  - id: cloudability.reporting.metrics\n    name: List reporting metrics\n    description: Return the list of metrics available for reporting queries.\n    api: cloudability:api-v3\n    outputs:\n      - metrics\n\n  - id: cloudability.business-mappings.list\n    name: List business mappings\n    description: Return all configured business mappings.\n    api: cloudability:business-mappings\n    inputs:\n      - limit\n      - offset\n    outputs:\n      - items\n      - total\n\n  - id: cloudability.business-mappings.create\n    name: Create business mapping\n    description: Define a new rule-based dimension for cost allocation.\n    api: cloudability:business-mappings\n    inputs:\n      - name\n      - kind\n      - default_value\n      - statements\n    outputs:\n      - id\n      - status\n\n  - id: cloudability.business-mappings.update\n\
  \    name: Update business mapping\n    description: Update statements, name, or default value of an existing mapping.\n    api: cloudability:business-mappings\n    inputs:\n      - id\n      - name\n      - default_value\n      - statements\n    outputs:\n      - status\n\n  - id: cloudability.rightsizing.list\n    name: List rightsizing recommendations\n    description: Return active rightsizing recommendations across vendors.\n    api: cloudability:rightsizing\n    inputs:\n      - vendor\n      - service\n      - account_id\n      - limit\n      - offset\n    outputs:\n      - items\n      - estimated_savings\n\n  - id: cloudability.anomalies.list\n    name: List cost anomalies\n    description: Return open cost anomalies on a dimension.\n    api: cloudability:anomalies\n    inputs:\n      - dimension_type\n      - severity\n      - status\n      - from_date\n      - to_date\n    outputs:\n      - items\n\n  - id: cloudability.anomalies.acknowledge\n    name: Acknowledge anomaly\n\
  \    description: Mark a detected anomaly as reviewed or dismissed.\n    api: cloudability:anomalies\n    inputs:\n      - anomaly_id\n      - status\n      - note\n    outputs:\n      - status\n\n  - id: cloudability.vendors.list\n    name: List vendor credentials\n    description: List configured cloud vendor connections (AWS, Azure, GCP, OCI).\n    api: cloudability:vendor-credentials\n    outputs:\n      - items\n\n  - id: cloudability.vendors.add\n    name: Add vendor credential\n    description: Onboard a new payer account, billing scope, or billing project.\n    api: cloudability:vendor-credentials\n    inputs:\n      - vendor\n      - account_identifier\n      - role_arn\n      - bucket\n      - region\n    outputs:\n      - id\n      - verification\n\n  - id: cloudability.views.list\n    name: List views\n    description: Return saved cost-explorer views.\n    api: cloudability:api-v3\n    outputs:\n      - items\n\n  - id: cloudability.budgets.list\n    name: List budgets\n \
  \   description: Return configured spend budgets and current consumption.\n    api: cloudability:api-v3\n    outputs:\n      - items\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloudability/refs/heads/main/capabilities/cloud-cost-finops.yaml
tags: []
tools: []
---
