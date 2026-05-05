---
categories: []
consumed_apis:
- webflow-data
description: 'Webflow CMS management workflow combining the Data API for programmatic content operations: site publishing, CMS collection and item management, webhook configuration, and content automation. Used by content managers, developers building CMS integrations, and marketing automation teams.'
layout: capability
name: Webflow CMS Management
operations:
- description: List all available Webflow sites
  method: GET
  name: list-sites
  path: /v1/sites
- description: Publish a Webflow site to custom domains
  method: POST
  name: publish-site
  path: /v1/sites/{site_id}/publish
- description: List CMS collections for a site
  method: GET
  name: list-collections
  path: /v1/collections
- description: List items in a CMS collection
  method: GET
  name: list-items
  path: /v1/items
- description: Create a new CMS item
  method: POST
  name: create-item
  path: /v1/items
- description: Update a CMS item
  method: PATCH
  name: update-item
  path: /v1/items/{item_id}
- description: Delete a CMS item
  method: DELETE
  name: delete-item
  path: /v1/items/{item_id}
- description: List webhooks for a site
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook for Webflow events
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Webflow API and Documentation
provider_slug: webflow-api-and-documentation-webflow
search_terms:
- cms
- delete an item from a webflow cms collection
- publish a webflow site to custom domains
- list sites
- ecommerce
- list all items in a webflow cms collection
- delete cms item
- create item
- register a webhook to receive webflow site events
- create cms item
- list cms collections in a webflow site
- create a new content item in a webflow cms collection
- update item
- webflow site management
- publish site
- list webhooks for a site
- create a webhook for webflow events
- publishing
- list webhooks registered for a webflow site
- web development
- list all webflow sites available with the api key
- create webhook
- delete a cms item
- update a cms item
- list items
- webflow
- single cms item operations
- no-code
- list cms collections for a site
- publish a webflow site
- update cms item
- delete item
- publish a webflow site to make changes live
- list all available webflow sites
- webhook management
- create a new cms item
- list items in a cms collection
- cms collection management
- sites
- publish cms items to make them live on the webflow site
- cms item management
- content management
- publish cms items
- list collections
- list webhooks
- update an existing webflow cms content item
slug: cms-management
source_filename: cms-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Webflow CMS Management\"\n  description: >-\n    Webflow CMS management workflow combining the Data API for programmatic\n    content operations: site publishing, CMS collection and item management,\n    webhook configuration, and content automation. Used by content managers,\n    developers building CMS integrations, and marketing automation teams.\n  tags:\n    - Webflow\n    - CMS\n    - Content Management\n    - Publishing\n    - Sites\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      WEBFLOW_API_KEY: WEBFLOW_API_KEY\n\ncapability:\n  consumes:\n    - import: webflow-data\n      location: ./shared/data-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: webflow-cms-api\n      description: \"Unified REST API for Webflow CMS content management workflows.\"\n      resources:\n        - path: /v1/sites\n          name: sites\n          description: \"\
  Webflow site management\"\n          operations:\n            - method: GET\n              name: list-sites\n              description: \"List all available Webflow sites\"\n              call: \"webflow-data.list-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sites/{site_id}/publish\n          name: site-publish\n          description: \"Publish a Webflow site\"\n          operations:\n            - method: POST\n              name: publish-site\n              description: \"Publish a Webflow site to custom domains\"\n              call: \"webflow-data.publish-site\"\n              with:\n                site_id: \"rest.site_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/collections\n          name: collections\n          description: \"CMS collection management\"\n          operations:\n            - method: GET\n           \
  \   name: list-collections\n              description: \"List CMS collections for a site\"\n              call: \"webflow-data.list-collections\"\n              with:\n                site_id: \"rest.site_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/items\n          name: items\n          description: \"CMS item management\"\n          operations:\n            - method: GET\n              name: list-items\n              description: \"List items in a CMS collection\"\n              call: \"webflow-data.list-items\"\n              with:\n                collection_id: \"rest.collection_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-item\n              description: \"Create a new CMS item\"\n              call: \"webflow-data.create-item\"\n              outputParameters:\n                - type:\
  \ object\n                  mapping: \"$.\"\n        - path: /v1/items/{item_id}\n          name: item\n          description: \"Single CMS item operations\"\n          operations:\n            - method: PATCH\n              name: update-item\n              description: \"Update a CMS item\"\n              call: \"webflow-data.update-item\"\n              with:\n                collection_id: \"rest.collection_id\"\n                item_id: \"rest.item_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-item\n              description: \"Delete a CMS item\"\n              call: \"webflow-data.delete-item\"\n              with:\n                collection_id: \"rest.collection_id\"\n                item_id: \"rest.item_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/webhooks\n          name: webhooks\n\
  \          description: \"Webhook management\"\n          operations:\n            - method: GET\n              name: list-webhooks\n              description: \"List webhooks for a site\"\n              call: \"webflow-data.list-webhooks\"\n              with:\n                site_id: \"rest.site_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-webhook\n              description: \"Create a webhook for Webflow events\"\n              call: \"webflow-data.create-webhook\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: webflow-cms-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Webflow CMS content management.\"\n      tools:\n        - name: list-sites\n          description: \"List all Webflow sites available with the API key\"\n          hints:\n\
  \            readOnly: true\n            openWorld: true\n          call: \"webflow-data.list-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-site\n          description: \"Publish a Webflow site to make changes live\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webflow-data.publish-site\"\n          with:\n            site_id: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-collections\n          description: \"List CMS collections in a Webflow site\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webflow-data.list-collections\"\n          with:\n            site_id: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-items\n          description: \"List all items\
  \ in a Webflow CMS collection\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"webflow-data.list-items\"\n          with:\n            collection_id: \"tools.collection_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cms-item\n          description: \"Create a new content item in a Webflow CMS collection\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webflow-data.create-item\"\n          with:\n            collection_id: \"tools.collection_id\"\n            fieldData: \"tools.fieldData\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-cms-item\n          description: \"Update an existing Webflow CMS content item\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"webflow-data.update-item\"\
  \n          with:\n            collection_id: \"tools.collection_id\"\n            item_id: \"tools.item_id\"\n            fieldData: \"tools.fieldData\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-cms-items\n          description: \"Publish CMS items to make them live on the Webflow site\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webflow-data.publish-item\"\n          with:\n            collection_id: \"tools.collection_id\"\n            itemIds: \"tools.itemIds\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-cms-item\n          description: \"Delete an item from a Webflow CMS collection\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"webflow-data.delete-item\"\n          with:\n            collection_id: \"tools.collection_id\"\
  \n            item_id: \"tools.item_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-webhooks\n          description: \"List webhooks registered for a Webflow site\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"webflow-data.list-webhooks\"\n          with:\n            site_id: \"tools.site_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-webhook\n          description: \"Register a webhook to receive Webflow site events\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"webflow-data.create-webhook\"\n          with:\n            site_id: \"tools.site_id\"\n            triggerType: \"tools.triggerType\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/webflow-api-and-documentation-webflow/refs/heads/main/capabilities/cms-management.yaml
tags:
- Webflow
- CMS
- Content Management
- Publishing
- Sites
tools:
- description: List all Webflow sites available with the API key
  hints:
    openWorld: true
    readOnly: true
  name: list-sites
- description: Publish a Webflow site to make changes live
  hints:
    destructive: false
    readOnly: false
  name: publish-site
- description: List CMS collections in a Webflow site
  hints:
    openWorld: true
    readOnly: true
  name: list-collections
- description: List all items in a Webflow CMS collection
  hints:
    openWorld: true
    readOnly: true
  name: list-items
- description: Create a new content item in a Webflow CMS collection
  hints:
    destructive: false
    readOnly: false
  name: create-cms-item
- description: Update an existing Webflow CMS content item
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-cms-item
- description: Publish CMS items to make them live on the Webflow site
  hints:
    destructive: false
    readOnly: false
  name: publish-cms-items
- description: Delete an item from a Webflow CMS collection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cms-item
- description: List webhooks registered for a Webflow site
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: Register a webhook to receive Webflow site events
  hints:
    destructive: false
    readOnly: false
  name: create-webhook
---
