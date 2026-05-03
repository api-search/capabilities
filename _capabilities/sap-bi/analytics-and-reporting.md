---
categories: []
consumed_apis:
- sap-bi-analytics-cloud
- sap-bi-businessobjects
description: Workflow capability for creating, managing, and distributing analytics content across SAP Analytics Cloud and SAP BusinessObjects BI Platform. Supports story authoring, report scheduling, and content governance. Used by BI developers, analysts, and report consumers.
layout: capability
name: SAP Business Intelligence Analytics and Reporting
operations:
- description: List analytics stories.
  method: GET
  name: list-stories
  path: /v1/stories
- description: Get a story by ID.
  method: GET
  name: get-story
  path: /v1/stories/{storyId}
- description: List analytics models.
  method: GET
  name: list-models
  path: /v1/models
- description: List BusinessObjects reports.
  method: GET
  name: list-reports
  path: /v1/reports
- description: List InfoStore content objects.
  method: GET
  name: list-content-objects
  path: /v1/content-objects
personas: []
provider_name: SAP Business Intelligence
provider_slug: sap-bi
search_terms:
- businessobjects reports.
- list models
- get a story by id.
- analytics data models.
- single analytics story.
- list stories
- browse content library
- list reports
- analytics
- list businessobjects reports.
- list reports available in the sap businessobjects bi platform.
- business intelligence
- create a new analytics story in sap analytics cloud.
- list analytics stories.
- analytics stories and dashboards.
- bi platform infostore objects.
- browse content objects in the sap businessobjects infostore repository.
- list infostore content objects.
- list content objects
- sap
- reporting
- list analytics models.
- create story
- data visualization
- get story
- list analytics data models in sap analytics cloud.
- get details of a specific analytics story.
- list analytics stories in sap analytics cloud.
slug: analytics-and-reporting
source_filename: analytics-and-reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP Business Intelligence Analytics and Reporting\"\n  description: \"Workflow capability for creating, managing, and distributing analytics content across SAP Analytics Cloud and SAP BusinessObjects BI Platform. Supports story authoring, report scheduling, and content governance. Used by BI developers, analysts, and report consumers.\"\n  tags:\n    - Analytics\n    - Business Intelligence\n    - Reporting\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_BI_OAUTH_TOKEN: SAP_BI_OAUTH_TOKEN\n      SAP_BOBJ_LOGON_TOKEN: SAP_BOBJ_LOGON_TOKEN\n\ncapability:\n  consumes:\n    - import: sap-bi-analytics-cloud\n      location: ./shared/analytics-cloud.yaml\n    - import: sap-bi-businessobjects\n      location: ./shared/businessobjects-platform.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: sap-bi-analytics-reporting-api\n      description: \"\
  Unified REST API for SAP Business Intelligence analytics and reporting workflows.\"\n      resources:\n        - path: /v1/stories\n          name: stories\n          description: \"Analytics stories and dashboards.\"\n          operations:\n            - method: GET\n              name: list-stories\n              description: \"List analytics stories.\"\n              call: \"sap-bi-analytics-cloud.list-stories\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/stories/{storyId}\n          name: story\n          description: \"Single analytics story.\"\n          operations:\n            - method: GET\n              name: get-story\n              description: \"Get a story by ID.\"\n              call: \"sap-bi-analytics-cloud.get-story\"\n              with:\n                storyId: \"rest.storyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path:\
  \ /v1/models\n          name: models\n          description: \"Analytics data models.\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List analytics models.\"\n              call: \"sap-bi-analytics-cloud.list-models\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/reports\n          name: reports\n          description: \"BusinessObjects reports.\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List BusinessObjects reports.\"\n              call: \"sap-bi-businessobjects.list-reports\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/content-objects\n          name: content-objects\n          description: \"BI Platform InfoStore objects.\"\n          operations:\n            - method: GET\n              name:\
  \ list-content-objects\n              description: \"List InfoStore content objects.\"\n              call: \"sap-bi-businessobjects.list-info-objects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: sap-bi-analytics-reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP BI analytics and reporting.\"\n      tools:\n        - name: list-stories\n          description: \"List analytics stories in SAP Analytics Cloud.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-analytics-cloud.list-stories\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-story\n          description: \"Get details of a specific analytics story.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"sap-bi-analytics-cloud.get-story\"\
  \n          with:\n            storyId: \"tools.storyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-story\n          description: \"Create a new analytics story in SAP Analytics Cloud.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"sap-bi-analytics-cloud.create-story\"\n          with:\n            name: \"tools.name\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-models\n          description: \"List analytics data models in SAP Analytics Cloud.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-analytics-cloud.list-models\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-reports\n          description: \"List reports available in the SAP BusinessObjects BI Platform.\"\n          hints:\n  \
  \          readOnly: true\n            openWorld: true\n          call: \"sap-bi-businessobjects.list-reports\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: browse-content-library\n          description: \"Browse content objects in the SAP BusinessObjects InfoStore repository.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"sap-bi-businessobjects.list-info-objects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi/refs/heads/main/capabilities/analytics-and-reporting.yaml
tags:
- Analytics
- Business Intelligence
- Reporting
- SAP
tools:
- description: List analytics stories in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-stories
- description: Get details of a specific analytics story.
  hints:
    openWorld: false
    readOnly: true
  name: get-story
- description: Create a new analytics story in SAP Analytics Cloud.
  hints:
    openWorld: false
    readOnly: false
  name: create-story
- description: List analytics data models in SAP Analytics Cloud.
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: List reports available in the SAP BusinessObjects BI Platform.
  hints:
    openWorld: true
    readOnly: true
  name: list-reports
- description: Browse content objects in the SAP BusinessObjects InfoStore repository.
  hints:
    openWorld: true
    readOnly: true
  name: browse-content-library
---
