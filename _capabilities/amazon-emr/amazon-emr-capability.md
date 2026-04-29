---
categories: []
consumed_apis:
- emr
description: Unified capability for managing Amazon EMR resources. Combines Amazon EMR APIs for Data Engineer workflows in Big Data Processing.
layout: capability
name: Amazon EMR Management
operations:
- description: Amazon EMR Create and Start an EMR Cluster
  method: POST
  name: RunJobFlow
  path: /v1/RunJobFlow
personas: []
provider_name: Amazon EMR
provider_slug: amazon-emr
search_terms:
- apache spark
- aws
- operations teams managing amazon emr infrastructure
- big data
- hadoop
- data processing
- big data platform for running apache spark, hadoop, and other frameworks
- RunJobFlow
- analytics
- amazon emr create and start an emr cluster
- unified capability for managing amazon emr resources. combines amazon emr apis for data engineer workflows in big data processing.
- amazon web services
- developers building applications using amazon emr
slug: amazon-emr-capability
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon EMR Management\n  description: Unified capability for managing Amazon EMR resources. Combines Amazon EMR APIs for Data Engineer workflows in Big Data Processing.\n  tags:\n  - Amazon Web Services\n  - Big Data\n  - Analytics\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_API_KEY: AWS_API_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - import: emr\n    location: ./shared/emr.yaml\n  exposes:\n  - type: rest\n    port: 8188\n    namespace: amazon-emr-workflow-api\n    description: Unified REST API for Amazon EMR management.\n    resources:\n    - path: /v1/RunJobFlow\n      name: RunJobFlow\n      description: Amazon EMR Create and Start an EMR Cluster\n      operations:\n      - method: POST\n        name: RunJobFlow\n        description: Amazon EMR Create and Start an EMR Cluster\n        call: api.RunJobFlow\n        outputParameters:\n        - type: object\n     \
  \     mapping: $.\n  - type: mcp\n    port: 9198\n    namespace: amazon-emr-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon EMR management.\n    tools:\n    - name: RunJobFlow\n      description: Amazon EMR Create and Start an EMR Cluster\n      hints:\n        readOnly: false\n      call: api.RunJobFlow\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-emr/refs/heads/main/capabilities/amazon-emr-capability.yaml
tags:
- Amazon Web Services
- Big Data
- Analytics
tools:
- description: Amazon EMR Create and Start an EMR Cluster
  hints:
    readOnly: false
  name: RunJobFlow
---
