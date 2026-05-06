---
categories: []
consumed_apis: []
description: Amazon EMR (Elastic MapReduce) provides a managed big data platform that simplifies running open-source frameworks such as Apache Spark and Hadoop to process and analyze vast amounts of data. This API enables you to create and manage clusters, add processing steps, configure auto-scaling, and monitor cluster health and performance.
layout: capability
name: Amazon EMR API
operations:
- description: Amazon EMR Create and Start an EMR Cluster
  method: POST
  name: runjobflow
  path: /
personas: []
provider_name: Amazon EMR
provider_slug: amazon-emr
search_terms:
- runjobflow
- big data platform for running apache spark, hadoop, and other frameworks
- hadoop
- developers building applications using amazon emr
- amazon web services
- apache spark
- amazon emr create and start an emr cluster
- api
- emr
- analytics
- amazon
- operations teams managing amazon emr infrastructure
- big data
- unified capability for managing amazon emr resources. combines amazon emr apis for data engineer workflows in big data processing.
- data processing
slug: amazon-emr-capability
source_filename: amazon-emr-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon EMR API\n  description: Amazon EMR (Elastic MapReduce) provides a managed big data platform that simplifies running open-source frameworks\n    such as Apache Spark and Hadoop to process and analyze vast amounts of data. This API enables you to create and manage\n    clusters, add processing steps, configure auto-scaling, and monitor cluster health and performance.\n  tags:\n  - Amazon\n  - Emr\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-emr\n    baseUri: https://elasticmapreduce.us-east-1.amazonaws.com\n    description: Amazon EMR API HTTP API.\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: runjobflow\n        method: POST\n        description: Amazon EMR Create and Start an EMR Cluster\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: amazon-emr-rest\n    description: REST adapter for Amazon EMR API.\n    resources:\n    - path: /\n      name: runjobflow\n      operations:\n      - method: POST\n        name: runjobflow\n        description: Amazon EMR Create and Start an EMR Cluster\n        call: amazon-emr.runjobflow\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: amazon-emr-mcp\n    transport: http\n    description: MCP adapter for Amazon EMR API for AI agent use.\n    tools:\n    - name: runjobflow\n      description: Amazon EMR Create and Start an EMR Cluster\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: amazon-emr.runjobflow\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-emr/refs/heads/main/capabilities/amazon-emr-capability.yaml
tags:
- Amazon
- Emr
- API
tools:
- description: Amazon EMR Create and Start an EMR Cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runjobflow
---
