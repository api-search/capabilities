---
categories: []
consumed_apis: []
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
- analytics
- list all einstein prediction builder definitions in the org.
- list prediction definitions
- salesforce einstein
- einstein prediction definitions.
- list all einstein discovery stories.
- list all einstein discovery analytics stories.
- list einstein discovery prediction models for advanced analytics.
- get ai insights for specified salesforce records.
- create a new einstein discovery story from a dataset for automated insights.
- list einstein analytics dashboards for business intelligence.
- prediction results for a definition.
- einstein discovery analytics stories.
- get statistical insights from an einstein discovery story.
- get statistical insights and key findings from an einstein discovery story.
- list discovery stories
- statistical insights from a discovery story.
- artificial intelligence
- create story
- list einstein discovery prediction models.
- business intelligence
- list all einstein prediction definitions.
- crm
- ai-generated insights for salesforce records.
- machine learning
- einstein discovery prediction models.
- get ai-generated insights and prediction factors for salesforce records.
- list discovery models
- create a new einstein discovery story.
- computer vision
- create a new einstein prediction definition.
- list analytics dashboards
- list models
- natural language processing
- get story stats
- list dashboards
- list predictions
- list stories
- create discovery story
- list prediction results for a definition.
- get ai record insights
- list prediction results for a given einstein prediction builder definition.
- predictive analytics
- create prediction definition
- einstein analytics dashboards.
- list einstein analytics dashboards.
- salesforce
slug: predictive-intelligence
source_filename: predictive-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Salesforce Einstein Predictive Intelligence\n  description: Workflow capability combining Einstein Prediction Builder and Einstein Discovery APIs for AI-driven predictive\n    analytics. Manage prediction definitions, retrieve AI record insights, analyze Einstein Discovery stories, and use prediction\n    models for business intelligence. Designed for Salesforce admins, data scientists, and business analysts building intelligent\n    CRM workflows.\n  tags:\n  - Analytics\n  - Artificial Intelligence\n  - Business Intelligence\n  - Machine Learning\n  - Predictive Analytics\n  - Salesforce Einstein\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n    SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: einstein-prediction-builder\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v58.0'\n\
  \    description: Salesforce Einstein Prediction Builder REST API.\n    authentication:\n      type: bearer\n      token: '{{env.SALESFORCE_OAUTH2_TOKEN}}'\n    resources:\n    - name: prediction-definitions\n      path: /einstein/prediction-definitions\n      description: Einstein prediction definitions for custom AI models.\n      operations:\n      - name: list-prediction-definitions\n        method: GET\n        description: List all Einstein prediction definitions in the org.\n        outputRawFormat: json\n        outputParameters:\n        - name: predictionDefinitions\n          type: object\n          value: $.\n      - name: create-prediction-definition\n        method: POST\n        description: Create a new Einstein prediction definition.\n        outputRawFormat: json\n        outputParameters:\n        - name: predictionDefinition\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      \
  \      predictionField: '{{tools.predictionField}}'\n            outcomeGoal: '{{tools.outcomeGoal}}'\n      - name: get-prediction-definition\n        method: GET\n        description: Get details of a specific prediction definition.\n        inputParameters:\n        - name: predictionDefinitionId\n          in: path\n          type: string\n          required: true\n          description: Prediction definition ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: predictionDefinition\n          type: object\n          value: $.\n      - name: update-prediction-definition\n        method: PATCH\n        description: Update an existing prediction definition.\n        inputParameters:\n        - name: predictionDefinitionId\n          in: path\n          type: string\n          required: true\n          description: Prediction definition ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: predictionDefinition\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-prediction-definition\n        method: DELETE\n        description: Delete a prediction definition.\n        inputParameters:\n        - name: predictionDefinitionId\n          in: path\n          type: string\n          required: true\n          description: Prediction definition ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-predictions\n        method: GET\n        description: List prediction results for a definition.\n        inputParameters:\n        - name: predictionDefinitionId\n          in: path\n          type: string\n          required: true\n          description: Prediction definition ID.\n        - name: recordId\n          in: query\n          type: string\n          required: false\n          description: Filter predictions by Salesforce\
  \ record ID.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of predictions to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: predictions\n          type: object\n          value: $.\n    - name: ai-record-insights\n      path: /einstein/ai-record-insights\n      description: AI-generated insights for Salesforce records.\n      operations:\n      - name: get-ai-record-insights\n        method: POST\n        description: Get AI insights for specified Salesforce records.\n        outputRawFormat: json\n        outputParameters:\n        - name: insights\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            predictionDefinition: '{{tools.predictionDefinition}}'\n            inputRecords: '{{tools.inputRecords}}'\n  - type: http\n    namespace: einstein-discovery\n    baseUri: '{{env.SALESFORCE_INSTANCE_URL}}/services/data/v58.0'\n\
  \    description: Salesforce Einstein Discovery (Wave Analytics) REST API.\n    authentication:\n      type: bearer\n      token: '{{env.SALESFORCE_OAUTH2_TOKEN}}'\n    resources:\n    - name: stories\n      path: /wave/stories\n      description: Einstein Discovery stories for AI-powered analytics.\n      operations:\n      - name: list-stories\n        method: GET\n        description: List all Einstein Discovery stories.\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query to filter stories by name.\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of stories to return per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: stories\n          type: object\n          value: $.\n      - name: create-story\n        method: POST\n        description: Create a new Einstein Discovery\
  \ story from a dataset.\n        outputRawFormat: json\n        outputParameters:\n        - name: story\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            datasetId: '{{tools.datasetId}}'\n            label: '{{tools.label}}'\n      - name: get-story\n        method: GET\n        description: Get details of a specific Einstein Discovery story.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: Story ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: story\n          type: object\n          value: $.\n      - name: delete-story\n        method: DELETE\n        description: Delete an Einstein Discovery story.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: Story ID.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-story-stats\n        method: GET\n        description: Get statistical insights from an Einstein Discovery story.\n        inputParameters:\n        - name: storyId\n          in: path\n          type: string\n          required: true\n          description: Story ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: stats\n          type: object\n          value: $.\n    - name: models\n      path: /wave/models\n      description: Einstein Discovery prediction models.\n      operations:\n      - name: list-models\n        method: GET\n        description: List all Einstein Discovery prediction models.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of models to return per page.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: models\n          type: object\n          value: $.\n      - name: get-model\n        method: GET\n        description: Get a specific Einstein Discovery prediction model.\n        inputParameters:\n        - name: modelId\n          in: path\n          type: string\n          required: true\n          description: Model ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: model\n          type: object\n          value: $.\n    - name: dashboards\n      path: /wave/dashboards\n      description: Einstein Analytics dashboards.\n      operations:\n      - name: list-dashboards\n        method: GET\n        description: List all Einstein Analytics dashboards.\n        inputParameters:\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of dashboards per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: dashboards\n          type: object\n\
  \          value: $.\n      - name: get-dashboard\n        method: GET\n        description: Get a specific analytics dashboard.\n        inputParameters:\n        - name: dashboardId\n          in: path\n          type: string\n          required: true\n          description: Dashboard ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: dashboard\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: einstein-predictive-intelligence-api\n    description: Unified REST API for Salesforce Einstein predictive intelligence.\n    resources:\n    - path: /v1/prediction-definitions\n      name: prediction-definitions\n      description: Einstein prediction definitions.\n      operations:\n      - method: GET\n        name: list-prediction-definitions\n        description: List all Einstein prediction definitions.\n        call: einstein-prediction-builder.list-prediction-definitions\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n      - method: POST\n        name: create-prediction-definition\n        description: Create a new Einstein prediction definition.\n        call: einstein-prediction-builder.create-prediction-definition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/prediction-definitions/{id}/predictions\n      name: predictions\n      description: Prediction results for a definition.\n      operations:\n      - method: GET\n        name: list-predictions\n        description: List prediction results for a definition.\n        call: einstein-prediction-builder.list-predictions\n        with:\n          predictionDefinitionId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai-record-insights\n      name: ai-record-insights\n      description: AI-generated insights for Salesforce records.\n      operations:\n      - method: POST\n        name: get-ai-record-insights\n\
  \        description: Get AI insights for specified Salesforce records.\n        call: einstein-prediction-builder.get-ai-record-insights\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stories\n      name: stories\n      description: Einstein Discovery analytics stories.\n      operations:\n      - method: GET\n        name: list-stories\n        description: List all Einstein Discovery stories.\n        call: einstein-discovery.list-stories\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-story\n        description: Create a new Einstein Discovery story.\n        call: einstein-discovery.create-story\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/stories/{id}/stats\n      name: story-stats\n      description: Statistical insights from a Discovery story.\n      operations:\n      - method: GET\n        name: get-story-stats\n     \
  \   description: Get statistical insights from an Einstein Discovery story.\n        call: einstein-discovery.get-story-stats\n        with:\n          storyId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models\n      name: models\n      description: Einstein Discovery prediction models.\n      operations:\n      - method: GET\n        name: list-models\n        description: List Einstein Discovery prediction models.\n        call: einstein-discovery.list-models\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/dashboards\n      name: dashboards\n      description: Einstein Analytics dashboards.\n      operations:\n      - method: GET\n        name: list-dashboards\n        description: List Einstein Analytics dashboards.\n        call: einstein-discovery.list-dashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace:\
  \ einstein-predictive-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted Salesforce Einstein predictive intelligence.\n    tools:\n    - name: list-prediction-definitions\n      description: List all Einstein Prediction Builder definitions in the org.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-prediction-builder.list-prediction-definitions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ai-record-insights\n      description: Get AI-generated insights and prediction factors for Salesforce records.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-prediction-builder.get-ai-record-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-predictions\n      description: List prediction results for a given Einstein Prediction Builder definition.\n      hints:\n        readOnly: true\n        idempotent: true\n\
  \      call: einstein-prediction-builder.list-predictions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-discovery-stories\n      description: List all Einstein Discovery analytics stories.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-discovery.list-stories\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-story-stats\n      description: Get statistical insights and key findings from an Einstein Discovery story.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-discovery.get-story-stats\n      with:\n        storyId: tools.storyId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-discovery-models\n      description: List Einstein Discovery prediction models for advanced analytics.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-discovery.list-models\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: list-analytics-dashboards\n      description: List Einstein Analytics dashboards for business intelligence.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: einstein-discovery.list-dashboards\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-discovery-story\n      description: Create a new Einstein Discovery story from a dataset for automated insights.\n      hints:\n        readOnly: false\n        destructive: false\n      call: einstein-discovery.create-story\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
