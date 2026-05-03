---
categories: []
consumed_apis:
- analytics-cloud
- analytics-cloud-content-network
description: Unified workflow capability for managing analytics content across SAP Analytics Cloud, including story lifecycle management, content network publishing, and file repository governance. Used by BI administrators and content authors.
layout: capability
name: SAP BI Tools Analytics Content Management
operations:
- description: List all analytics stories on the tenant.
  method: GET
  name: list-stories
  path: /v1/stories
- description: Get a story by ID.
  method: GET
  name: get-story
  path: /v1/stories/{storyId}
- description: List repository resources (stories, models, folders).
  method: GET
  name: list-resources
  path: /v1/resources
- description: List Content Network items.
  method: GET
  name: list-content-items
  path: /v1/content-items
- description: Get a content item by ID.
  method: GET
  name: get-content-item
  path: /v1/content-items/{itemId}
- description: List calendar events and planning tasks.
  method: GET
  name: list-calendars
  path: /v1/calendars
personas: []
provider_name: SAP BI Tools
provider_slug: sap-bi-tools
search_terms:
- get a story by id.
- list content items in the sap analytics cloud content network.
- single analytics story.
- list stories
- planning calendars.
- import content item
- analytics
- list repository resources (stories, models, folders).
- content management
- get details of a specific analytics story by id.
- list planning calendar events and collaborative tasks.
- get a content item by id.
- list all analytics stories on the sap analytics cloud tenant.
- business intelligence
- list resources
- list content network items.
- publish content item
- sap
- list calendars
- import a content package from the content network into the local tenant.
- analytics story management.
- list calendar events and planning tasks.
- reporting
- list file repository resources (stories, models, folders).
- single content network item.
- publish a local analytics artifact to the content network for sharing.
- content network items.
- list content items
- data visualization
- get story
- get content item
- file repository resources.
- list all analytics stories on the tenant.
slug: analytics-content-management
source_filename: analytics-content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SAP BI Tools Analytics Content Management\"\n  description: \"Unified workflow capability for managing analytics content across SAP Analytics Cloud, including story lifecycle management, content network publishing, and file repository governance. Used by BI administrators and content authors.\"\n  tags:\n    - Analytics\n    - Business Intelligence\n    - Content Management\n    - SAP\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SAP_AC_OAUTH_TOKEN: SAP_AC_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: analytics-cloud\n      location: ./shared/analytics-cloud.yaml\n    - import: analytics-cloud-content-network\n      location: ./shared/analytics-cloud-content-network.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: analytics-content-management-api\n      description: \"Unified REST API for SAP Analytics Cloud content lifecycle management.\"\
  \n      resources:\n        - path: /v1/stories\n          name: stories\n          description: \"Analytics story management.\"\n          operations:\n            - method: GET\n              name: list-stories\n              description: \"List all analytics stories on the tenant.\"\n              call: \"analytics-cloud.list-stories\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/stories/{storyId}\n          name: story\n          description: \"Single analytics story.\"\n          operations:\n            - method: GET\n              name: get-story\n              description: \"Get a story by ID.\"\n              call: \"analytics-cloud.get-story\"\n              with:\n                storyId: \"rest.storyId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/resources\n          name: resources\n          description: \"File repository\
  \ resources.\"\n          operations:\n            - method: GET\n              name: list-resources\n              description: \"List repository resources (stories, models, folders).\"\n              call: \"analytics-cloud.list-resources\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/content-items\n          name: content-items\n          description: \"Content Network items.\"\n          operations:\n            - method: GET\n              name: list-content-items\n              description: \"List Content Network items.\"\n              call: \"analytics-cloud-content-network.list-content-items\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n        - path: /v1/content-items/{itemId}\n          name: content-item\n          description: \"Single Content Network item.\"\n          operations:\n            - method: GET\n              name: get-content-item\n\
  \              description: \"Get a content item by ID.\"\n              call: \"analytics-cloud-content-network.get-content-item\"\n              with:\n                itemId: \"rest.itemId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/calendars\n          name: calendars\n          description: \"Planning calendars.\"\n          operations:\n            - method: GET\n              name: list-calendars\n              description: \"List calendar events and planning tasks.\"\n              call: \"analytics-cloud.list-calendars\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: analytics-content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SAP Analytics Cloud content management.\"\n      tools:\n        - name: list-stories\n          description: \"List all analytics\
  \ stories on the SAP Analytics Cloud tenant.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-cloud.list-stories\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-story\n          description: \"Get details of a specific analytics story by ID.\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"analytics-cloud.get-story\"\n          with:\n            storyId: \"tools.storyId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-resources\n          description: \"List file repository resources (stories, models, folders).\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-cloud.list-resources\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: list-content-items\n\
  \          description: \"List content items in the SAP Analytics Cloud Content Network.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-cloud-content-network.list-content-items\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: publish-content-item\n          description: \"Publish a local analytics artifact to the Content Network for sharing.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"analytics-cloud-content-network.publish-content-item\"\n          with:\n            name: \"tools.name\"\n            resourceId: \"tools.resourceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: import-content-item\n          description: \"Import a content package from the Content Network into the local tenant.\"\n          hints:\n            readOnly: false\n            openWorld:\
  \ false\n          call: \"analytics-cloud-content-network.import-content-item\"\n          with:\n            itemId: \"tools.itemId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-calendars\n          description: \"List planning calendar events and collaborative tasks.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"analytics-cloud.list-calendars\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sap-bi-tools/refs/heads/main/capabilities/analytics-content-management.yaml
tags:
- Analytics
- Business Intelligence
- Content Management
- SAP
tools:
- description: List all analytics stories on the SAP Analytics Cloud tenant.
  hints:
    openWorld: true
    readOnly: true
  name: list-stories
- description: Get details of a specific analytics story by ID.
  hints:
    openWorld: false
    readOnly: true
  name: get-story
- description: List file repository resources (stories, models, folders).
  hints:
    openWorld: true
    readOnly: true
  name: list-resources
- description: List content items in the SAP Analytics Cloud Content Network.
  hints:
    openWorld: true
    readOnly: true
  name: list-content-items
- description: Publish a local analytics artifact to the Content Network for sharing.
  hints:
    openWorld: false
    readOnly: false
  name: publish-content-item
- description: Import a content package from the Content Network into the local tenant.
  hints:
    openWorld: false
    readOnly: false
  name: import-content-item
- description: List planning calendar events and collaborative tasks.
  hints:
    openWorld: true
    readOnly: true
  name: list-calendars
---
