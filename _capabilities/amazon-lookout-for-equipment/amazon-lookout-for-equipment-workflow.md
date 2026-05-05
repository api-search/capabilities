---
categories: []
consumed_apis:
- lookout-for-equipment
description: Unified workflow capability for Amazon Lookout for Equipment combining resource management and operations.
layout: capability
name: Amazon Lookout for Equipment Workflow
operations: []
personas: []
provider_name: Amazon Lookout for Equipment
provider_slug: amazon-lookout-for-equipment
search_terms:
- Developer
- datasets list datasets
- datasets describe dataset
- creates a container (dataset) for a collection of data being ingested for analysis.
- datasets create dataset
- workflow
- provides a json containing the overall information about a specific dataset.
- Administrator
- integrates api into applications
- manages resources and configurations
- aws
- equipment monitoring
- industrial iot
- lists all datasets currently available in your account.
- amazon lookout for equipment
- predictive maintenance
- unified workflow for amazon lookout for equipment resource management
- machine learning
slug: amazon-lookout-for-equipment-workflow
source_filename: amazon-lookout-for-equipment-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Lookout for Equipment Workflow\n  description: Unified workflow capability for Amazon Lookout for Equipment combining resource management and operations.\n  tags:\n  - Amazon Lookout for Equipment\n  - AWS\n  - Workflow\n  created: '2026-04-19'\n  modified: '2026-04-19'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - import: lookout-for-equipment\n    location: ./shared/lookout-for-equipment.yaml\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lookout-for-equipment-api\n    description: REST API for Amazon Lookout for Equipment workflow.\n    resources: []\n  - type: mcp\n    port: 9090\n    namespace: lookout-for-equipment-mcp\n    transport: http\n    description: MCP server for Amazon Lookout for Equipment.\n    tools:\n    - name: datasets-create-dataset\n      description: Creates a container (dataset) for\
  \ a collection of data being ingested for analysis.\n      hints:\n        readOnly: false\n        idempotent: false\n      call: lookout-for-equipment.createdataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasets-list-datasets\n      description: Lists all datasets currently available in your account.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lookout-for-equipment.listdatasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: datasets-describe-dataset\n      description: Provides a JSON containing the overall information about a specific dataset.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: lookout-for-equipment.describedataset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-lookout-for-equipment/refs/heads/main/capabilities/amazon-lookout-for-equipment-workflow.yaml
tags:
- Amazon Lookout for Equipment
- Workflow
tools:
- description: Creates a container (dataset) for a collection of data being ingested for analysis.
  hints:
    idempotent: false
    readOnly: false
  name: datasets-create-dataset
- description: Lists all datasets currently available in your account.
  hints:
    idempotent: true
    readOnly: true
  name: datasets-list-datasets
- description: Provides a JSON containing the overall information about a specific dataset.
  hints:
    idempotent: true
    readOnly: true
  name: datasets-describe-dataset
---
