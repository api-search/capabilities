---
categories: []
consumed_apis:
- einstein-prediction-builder
- einstein-discovery
description: Workflow capability combining Einstein Prediction Builder and Einstein Discovery APIs for AI-driven predictive analytics. Manage prediction definitions, retrieve AI record insights, analyze Einstein Discovery stories, and use prediction models for business intelligence. Designed for Salesforce admins, data scientists, and business analysts building intelligent CRM workflows.
layout: capability
name: Salesforce Einstein Predictive Intelligence
operations:
- description: List all Einstein prediction definitions.
  method: GET
  name: list-prediction-definitions
  path: /v1/prediction-definitions
- description: Create a new Einstein prediction definition.
  method: POST
  name: create-prediction-definition
  path: /v1/prediction-definitions
- description: List prediction results for a definition.
  method: GET
  name: list-predictions
  path: /v1/prediction-definitions/{id}/predictions
- description: Get AI insights for specified Salesforce records.
  method: POST
  name: get-ai-record-insights
  path: /v1/ai-record-insights
- description: List all Einstein Discovery stories.
  method: GET
  name: list-stories
  path: /v1/stories
- description: Create a new Einstein Discovery story.
  method: POST
  name: create-story
  path: /v1/stories
- description: Get statistical insights from an Einstein Discovery story.
  method: GET
  name: get-story-stats
  path: /v1/stories/{id}/stats
- description: List Einstein Discovery prediction models.
  method: GET
  name: list-models
  path: /v1/models
- description: List Einstein Analytics dashboards.
  method: GET
  name: list-dashboards
  path: /v1/dashboards
personas: []
provider_name: Salesforce Einstein
provider_slug: salesforce-einstein
search_terms:
- list all einstein prediction builder definitions in the org.
- list all einstein prediction definitions.
- list stories
- list models
- predictive analytics
- list discovery stories
- salesforce einstein
- get ai insights for specified salesforce records.
- list prediction results for a given einstein prediction builder definition.
- list einstein analytics dashboards for business intelligence.
- business intelligence
- list all einstein discovery analytics stories.
- analytics
- computer vision
- create prediction definition
- list all einstein discovery stories.
- list prediction definitions
- create a new einstein prediction definition.
- natural language processing
- list analytics dashboards
- artificial intelligence
- list prediction results for a definition.
- prediction results for a definition.
- einstein discovery prediction models.
- statistical insights from a discovery story.
- create a new einstein discovery story from a dataset for automated insights.
- list dashboards
- list einstein discovery prediction models for advanced analytics.
- list einstein analytics dashboards.
- list einstein discovery prediction models.
- salesforce
- ai-generated insights for salesforce records.
- einstein discovery analytics stories.
- list predictions
- get statistical insights and key findings from an einstein discovery story.
- machine learning
- einstein analytics dashboards.
- crm
- create story
- get statistical insights from an einstein discovery story.
- create discovery story
- get story stats
- get ai-generated insights and prediction factors for salesforce records.
- create a new einstein discovery story.
- list discovery models
- einstein prediction definitions.
- get ai record insights
slug: predictive-intelligence
source_filename: predictive-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Einstein Predictive Intelligence\"\n  description: >-\n    Workflow capability combining Einstein Prediction Builder and Einstein Discovery\n    APIs for AI-driven predictive analytics. Manage prediction definitions, retrieve\n    AI record insights, analyze Einstein Discovery stories, and use prediction models\n    for business intelligence. Designed for Salesforce admins, data scientists, and\n    business analysts building intelligent CRM workflows.\n  tags:\n    - Analytics\n    - Artificial Intelligence\n    - Business Intelligence\n    - Machine Learning\n    - Predictive Analytics\n    - Salesforce Einstein\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n      SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\n\ncapability:\n  consumes:\n    - import: einstein-prediction-builder\n      location: ./shared/einstein-prediction-builder.yaml\n\
  \    - import: einstein-discovery\n      location: ./shared/einstein-discovery.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: einstein-predictive-intelligence-api\n      description: \"Unified REST API for Salesforce Einstein predictive intelligence.\"\n      resources:\n        - path: /v1/prediction-definitions\n          name: prediction-definitions\n          description: \"Einstein prediction definitions.\"\n          operations:\n            - method: GET\n              name: list-prediction-definitions\n              description: \"List all Einstein prediction definitions.\"\n              call: \"einstein-prediction-builder.list-prediction-definitions\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-prediction-definition\n              description: \"Create a new Einstein prediction definition.\"\n              call: \"einstein-prediction-builder.create-prediction-definition\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/prediction-definitions/{id}/predictions\n          name: predictions\n          description: \"Prediction results for a definition.\"\n          operations:\n            - method: GET\n              name: list-predictions\n              description: \"List prediction results for a definition.\"\n              call: \"einstein-prediction-builder.list-predictions\"\n              with:\n                predictionDefinitionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ai-record-insights\n          name: ai-record-insights\n          description: \"AI-generated insights for Salesforce records.\"\n          operations:\n            - method: POST\n              name: get-ai-record-insights\n              description: \"Get AI insights for specified Salesforce records.\"\n         \
  \     call: \"einstein-prediction-builder.get-ai-record-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stories\n          name: stories\n          description: \"Einstein Discovery analytics stories.\"\n          operations:\n            - method: GET\n              name: list-stories\n              description: \"List all Einstein Discovery stories.\"\n              call: \"einstein-discovery.list-stories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-story\n              description: \"Create a new Einstein Discovery story.\"\n              call: \"einstein-discovery.create-story\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stories/{id}/stats\n          name: story-stats\n          description: \"Statistical insights\
  \ from a Discovery story.\"\n          operations:\n            - method: GET\n              name: get-story-stats\n              description: \"Get statistical insights from an Einstein Discovery story.\"\n              call: \"einstein-discovery.get-story-stats\"\n              with:\n                storyId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models\n          name: models\n          description: \"Einstein Discovery prediction models.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List Einstein Discovery prediction models.\"\n              call: \"einstein-discovery.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/dashboards\n          name: dashboards\n          description: \"Einstein Analytics dashboards.\"\n          operations:\n\
  \            - method: GET\n              name: list-dashboards\n              description: \"List Einstein Analytics dashboards.\"\n              call: \"einstein-discovery.list-dashboards\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: einstein-predictive-intelligence-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce Einstein predictive intelligence.\"\n      tools:\n        - name: list-prediction-definitions\n          description: \"List all Einstein Prediction Builder definitions in the org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-prediction-builder.list-prediction-definitions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-ai-record-insights\n          description: \"Get AI-generated insights and prediction factors\
  \ for Salesforce records.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-prediction-builder.get-ai-record-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-predictions\n          description: \"List prediction results for a given Einstein Prediction Builder definition.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-prediction-builder.list-predictions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-discovery-stories\n          description: \"List all Einstein Discovery analytics stories.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-discovery.list-stories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-story-stats\n \
  \         description: \"Get statistical insights and key findings from an Einstein Discovery story.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-discovery.get-story-stats\"\n          with:\n            storyId: \"tools.storyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-discovery-models\n          description: \"List Einstein Discovery prediction models for advanced analytics.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-discovery.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-dashboards\n          description: \"List Einstein Analytics dashboards for business intelligence.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"einstein-discovery.list-dashboards\"\n    \
  \      outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-discovery-story\n          description: \"Create a new Einstein Discovery story from a dataset for automated insights.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"einstein-discovery.create-story\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-einstein/refs/heads/main/capabilities/predictive-intelligence.yaml
tags:
- Analytics
- Artificial Intelligence
- Business Intelligence
- Machine Learning
- Predictive Analytics
- Salesforce Einstein
tools:
- description: List all Einstein Prediction Builder definitions in the org.
  hints:
    idempotent: true
    readOnly: true
  name: list-prediction-definitions
- description: Get AI-generated insights and prediction factors for Salesforce records.
  hints:
    idempotent: true
    readOnly: true
  name: get-ai-record-insights
- description: List prediction results for a given Einstein Prediction Builder definition.
  hints:
    idempotent: true
    readOnly: true
  name: list-predictions
- description: List all Einstein Discovery analytics stories.
  hints:
    idempotent: true
    readOnly: true
  name: list-discovery-stories
- description: Get statistical insights and key findings from an Einstein Discovery story.
  hints:
    idempotent: true
    readOnly: true
  name: get-story-stats
- description: List Einstein Discovery prediction models for advanced analytics.
  hints:
    idempotent: true
    readOnly: true
  name: list-discovery-models
- description: List Einstein Analytics dashboards for business intelligence.
  hints:
    idempotent: true
    readOnly: true
  name: list-analytics-dashboards
- description: Create a new Einstein Discovery story from a dataset for automated insights.
  hints:
    destructive: false
    readOnly: false
  name: create-discovery-story
---
