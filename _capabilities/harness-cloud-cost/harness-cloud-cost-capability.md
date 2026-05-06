---
categories: []
consumed_apis: []
description: The Harness Cloud Cost Management (CCM) API provides programmatic access to cloud cost data, perspectives, budgets, anomaly detection, and AI-driven recommendations across AWS, Azure, GCP, and Kubernetes environments. CCM enables FinOps practices by exposing granular cost details across namespaces, nodes, pods, accounts, and services.
layout: capability
name: Harness Cloud Cost Management API
operations:
- description: List perspectives
  method: GET
  name: listperspectives
  path: /ccm/api/perspective
- description: Create a perspective
  method: POST
  name: createperspective
  path: /ccm/api/perspective
- description: Get a perspective
  method: GET
  name: getperspective
  path: /ccm/api/perspective/{perspectiveId}
- description: Update a perspective
  method: PUT
  name: updateperspective
  path: /ccm/api/perspective/{perspectiveId}
- description: Delete a perspective
  method: DELETE
  name: deleteperspective
  path: /ccm/api/perspective/{perspectiveId}
- description: List budgets
  method: GET
  name: listbudgets
  path: /ccm/api/budgets
- description: Create a budget
  method: POST
  name: createbudget
  path: /ccm/api/budgets
- description: Get a budget
  method: GET
  name: getbudget
  path: /ccm/api/budgets/{budgetId}
- description: Update a budget
  method: PUT
  name: updatebudget
  path: /ccm/api/budgets/{budgetId}
- description: Delete a budget
  method: DELETE
  name: deletebudget
  path: /ccm/api/budgets/{budgetId}
- description: List cost recommendations
  method: GET
  name: listrecommendations
  path: /ccm/api/recommendation/overview/list
- description: Get a recommendation
  method: GET
  name: getrecommendation
  path: /ccm/api/recommendation/{recommendationId}
- description: List anomalies
  method: GET
  name: listanomalies
  path: /ccm/api/anomaly
- description: Get an anomaly
  method: GET
  name: getanomaly
  path: /ccm/api/anomaly/{anomalyId}
- description: List cost categories
  method: GET
  name: listcostcategories
  path: /ccm/api/business-mapping
- description: Create a cost category
  method: POST
  name: createcostcategory
  path: /ccm/api/business-mapping
- description: List connectors
  method: GET
  name: listconnectors
  path: /ng/api/connectors
personas: []
provider_name: Harness Cloud Cost Management
provider_slug: harness-cloud-cost
search_terms:
- deletebudget
- get a perspective
- getbudget
- list connectors
- list perspectives
- cost
- createperspective
- listcostcategories
- finops
- createcostcategory
- budgets
- create a cost category
- get a recommendation
- listrecommendations
- delete a budget
- getperspective
- cloud
- get a budget
- updateperspective
- kubernetes
- delete a perspective
- list cost recommendations
- listanomalies
- getanomaly
- list cost categories
- update a budget
- list anomalies
- harness
- create a perspective
- getrecommendation
- api
- createbudget
- create a budget
- update a perspective
- listperspectives
- cloud cost management
- deleteperspective
- updatebudget
- get an anomaly
- list budgets
- listbudgets
- recommendations
- listconnectors
- anomaly detection
slug: harness-cloud-cost-capability
source_filename: harness-cloud-cost-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Harness Cloud Cost Management API\n  description: The Harness Cloud Cost Management (CCM) API provides programmatic access to cloud cost data, perspectives,\n    budgets, anomaly detection, and AI-driven recommendations across AWS, Azure, GCP, and Kubernetes environments. CCM enables\n    FinOps practices by exposing granular cost details across namespaces, nodes, pods, accounts, and services.\n  tags:\n  - Harness\n  - Cloud\n  - Cost\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: harness-cloud-cost\n    baseUri: https://app.harness.io\n    description: Harness Cloud Cost Management API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{HARNESS_CLOUD_COST_TOKEN}}'\n    resources:\n    - name: ccm-api-perspective\n      path: /ccm/api/perspective\n      operations:\n      - name: listperspectives\n        method:\
  \ GET\n        description: List perspectives\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createperspective\n        method: POST\n        description: Create a perspective\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-perspective-perspectiveid\n      path: /ccm/api/perspective/{perspectiveId}\n      operations:\n      - name: getperspective\n        method: GET\n        description: Get a perspective\n        inputParameters:\n        - name: perspectiveId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateperspective\n        method: PUT\n        description: Update a perspective\n        inputParameters:\n        - name: perspectiveId\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteperspective\n        method: DELETE\n        description: Delete a perspective\n        inputParameters:\n        - name: perspectiveId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-budgets\n      path: /ccm/api/budgets\n      operations:\n      - name: listbudgets\n        method: GET\n        description: List budgets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbudget\n        method: POST\n        description: Create a budget\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: ccm-api-budgets-budgetid\n      path: /ccm/api/budgets/{budgetId}\n      operations:\n      - name: getbudget\n        method: GET\n        description: Get a budget\n        inputParameters:\n        - name: budgetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebudget\n        method: PUT\n        description: Update a budget\n        inputParameters:\n        - name: budgetId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebudget\n        method: DELETE\n        description: Delete a budget\n        inputParameters:\n        - name: budgetId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-recommendation-overview-list\n      path: /ccm/api/recommendation/overview/list\n      operations:\n      - name: listrecommendations\n        method: GET\n        description: List cost recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-recommendation-recommendationid\n      path: /ccm/api/recommendation/{recommendationId}\n      operations:\n      - name: getrecommendation\n        method: GET\n        description: Get a recommendation\n        inputParameters:\n        - name: recommendationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-anomaly\n\
  \      path: /ccm/api/anomaly\n      operations:\n      - name: listanomalies\n        method: GET\n        description: List anomalies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-anomaly-anomalyid\n      path: /ccm/api/anomaly/{anomalyId}\n      operations:\n      - name: getanomaly\n        method: GET\n        description: Get an anomaly\n        inputParameters:\n        - name: anomalyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ccm-api-business-mapping\n      path: /ccm/api/business-mapping\n      operations:\n      - name: listcostcategories\n        method: GET\n        description: List cost categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: createcostcategory\n        method: POST\n        description: Create a cost category\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ng-api-connectors\n      path: /ng/api/connectors\n      operations:\n      - name: listconnectors\n        method: GET\n        description: List connectors\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: harness-cloud-cost-rest\n    description: REST adapter for Harness Cloud Cost Management API.\n    resources:\n    - path: /ccm/api/perspective\n      name: listperspectives\n      operations:\n      - method: GET\n        name: listperspectives\n        description: List perspectives\n        call:\
  \ harness-cloud-cost.listperspectives\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/perspective\n      name: createperspective\n      operations:\n      - method: POST\n        name: createperspective\n        description: Create a perspective\n        call: harness-cloud-cost.createperspective\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/perspective/{perspectiveId}\n      name: getperspective\n      operations:\n      - method: GET\n        name: getperspective\n        description: Get a perspective\n        call: harness-cloud-cost.getperspective\n        with:\n          perspectiveId: rest.perspectiveId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/perspective/{perspectiveId}\n      name: updateperspective\n      operations:\n      - method: PUT\n        name: updateperspective\n        description: Update a perspective\n        call:\
  \ harness-cloud-cost.updateperspective\n        with:\n          perspectiveId: rest.perspectiveId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/perspective/{perspectiveId}\n      name: deleteperspective\n      operations:\n      - method: DELETE\n        name: deleteperspective\n        description: Delete a perspective\n        call: harness-cloud-cost.deleteperspective\n        with:\n          perspectiveId: rest.perspectiveId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/budgets\n      name: listbudgets\n      operations:\n      - method: GET\n        name: listbudgets\n        description: List budgets\n        call: harness-cloud-cost.listbudgets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/budgets\n      name: createbudget\n      operations:\n      - method: POST\n        name: createbudget\n        description: Create a budget\n\
  \        call: harness-cloud-cost.createbudget\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/budgets/{budgetId}\n      name: getbudget\n      operations:\n      - method: GET\n        name: getbudget\n        description: Get a budget\n        call: harness-cloud-cost.getbudget\n        with:\n          budgetId: rest.budgetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/budgets/{budgetId}\n      name: updatebudget\n      operations:\n      - method: PUT\n        name: updatebudget\n        description: Update a budget\n        call: harness-cloud-cost.updatebudget\n        with:\n          budgetId: rest.budgetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/budgets/{budgetId}\n      name: deletebudget\n      operations:\n      - method: DELETE\n        name: deletebudget\n        description: Delete a budget\n        call: harness-cloud-cost.deletebudget\n\
  \        with:\n          budgetId: rest.budgetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/recommendation/overview/list\n      name: listrecommendations\n      operations:\n      - method: GET\n        name: listrecommendations\n        description: List cost recommendations\n        call: harness-cloud-cost.listrecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/recommendation/{recommendationId}\n      name: getrecommendation\n      operations:\n      - method: GET\n        name: getrecommendation\n        description: Get a recommendation\n        call: harness-cloud-cost.getrecommendation\n        with:\n          recommendationId: rest.recommendationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/anomaly\n      name: listanomalies\n      operations:\n      - method: GET\n        name: listanomalies\n        description:\
  \ List anomalies\n        call: harness-cloud-cost.listanomalies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/anomaly/{anomalyId}\n      name: getanomaly\n      operations:\n      - method: GET\n        name: getanomaly\n        description: Get an anomaly\n        call: harness-cloud-cost.getanomaly\n        with:\n          anomalyId: rest.anomalyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/business-mapping\n      name: listcostcategories\n      operations:\n      - method: GET\n        name: listcostcategories\n        description: List cost categories\n        call: harness-cloud-cost.listcostcategories\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ccm/api/business-mapping\n      name: createcostcategory\n      operations:\n      - method: POST\n        name: createcostcategory\n        description: Create a cost category\n        call:\
  \ harness-cloud-cost.createcostcategory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ng/api/connectors\n      name: listconnectors\n      operations:\n      - method: GET\n        name: listconnectors\n        description: List connectors\n        call: harness-cloud-cost.listconnectors\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: harness-cloud-cost-mcp\n    transport: http\n    description: MCP adapter for Harness Cloud Cost Management API for AI agent use.\n    tools:\n    - name: listperspectives\n      description: List perspectives\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.listperspectives\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createperspective\n      description: Create a perspective\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: false\n      call: harness-cloud-cost.createperspective\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getperspective\n      description: Get a perspective\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.getperspective\n      with:\n        perspectiveId: tools.perspectiveId\n      inputParameters:\n      - name: perspectiveId\n        type: string\n        description: perspectiveId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateperspective\n      description: Update a perspective\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.updateperspective\n      with:\n        perspectiveId: tools.perspectiveId\n      inputParameters:\n      - name: perspectiveId\n        type: string\n        description: perspectiveId\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteperspective\n      description: Delete a perspective\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: harness-cloud-cost.deleteperspective\n      with:\n        perspectiveId: tools.perspectiveId\n      inputParameters:\n      - name: perspectiveId\n        type: string\n        description: perspectiveId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbudgets\n      description: List budgets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.listbudgets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbudget\n      description: Create a budget\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harness-cloud-cost.createbudget\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbudget\n      description: Get a budget\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.getbudget\n      with:\n        budgetId: tools.budgetId\n      inputParameters:\n      - name: budgetId\n        type: string\n        description: budgetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebudget\n      description: Update a budget\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.updatebudget\n      with:\n        budgetId: tools.budgetId\n      inputParameters:\n      - name: budgetId\n        type: string\n        description: budgetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebudget\n      description: Delete a budget\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: harness-cloud-cost.deletebudget\n      with:\n        budgetId: tools.budgetId\n      inputParameters:\n      - name: budgetId\n        type: string\n        description: budgetId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecommendations\n      description: List cost recommendations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.listrecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecommendation\n      description: Get a recommendation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.getrecommendation\n      with:\n        recommendationId: tools.recommendationId\n      inputParameters:\n      - name: recommendationId\n\
  \        type: string\n        description: recommendationId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listanomalies\n      description: List anomalies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.listanomalies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getanomaly\n      description: Get an anomaly\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.getanomaly\n      with:\n        anomalyId: tools.anomalyId\n      inputParameters:\n      - name: anomalyId\n        type: string\n        description: anomalyId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcostcategories\n      description: List cost categories\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: harness-cloud-cost.listcostcategories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcostcategory\n      description: Create a cost category\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: harness-cloud-cost.createcostcategory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listconnectors\n      description: List connectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: harness-cloud-cost.listconnectors\n      with:\n        type: tools.type\n      inputParameters:\n      - name: type\n        type: string\n        description: type\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    HARNESS_CLOUD_COST_TOKEN: HARNESS_CLOUD_COST_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/harness-cloud-cost/refs/heads/main/capabilities/harness-cloud-cost-capability.yaml
tags:
- Harness
- Cloud
- Cost
- API
tools:
- description: List perspectives
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listperspectives
- description: Create a perspective
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createperspective
- description: Get a perspective
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperspective
- description: Update a perspective
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateperspective
- description: Delete a perspective
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteperspective
- description: List budgets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbudgets
- description: Create a budget
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbudget
- description: Get a budget
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbudget
- description: Update a budget
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatebudget
- description: Delete a budget
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebudget
- description: List cost recommendations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecommendations
- description: Get a recommendation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecommendation
- description: List anomalies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listanomalies
- description: Get an anomaly
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getanomaly
- description: List cost categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcostcategories
- description: Create a cost category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcostcategory
- description: List connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listconnectors
---
