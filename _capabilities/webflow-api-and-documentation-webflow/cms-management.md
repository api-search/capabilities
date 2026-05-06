---
categories: []
consumed_apis: []
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
- create a webhook for webflow events
- update a cms item
- list cms collections for a site
- list items in a cms collection
- no-code
- publish cms items to make them live on the webflow site
- list items
- delete item
- list webhooks registered for a webflow site
- list collections
- update an existing webflow cms content item
- list cms collections in a webflow site
- publishing
- create webhook
- publish a webflow site to custom domains
- cms collection management
- delete an item from a webflow cms collection
- publish cms items
- content management
- list all webflow sites available with the api key
- register a webhook to receive webflow site events
- update cms item
- list sites
- delete cms item
- ecommerce
- webhook management
- webflow
- update item
- publish a webflow site
- create item
- delete a cms item
- sites
- cms
- list webhooks for a site
- publish site
- webflow site management
- create a new cms item
- single cms item operations
- list all items in a webflow cms collection
- web development
- create cms item
- list all available webflow sites
- list webhooks
- create a new content item in a webflow cms collection
- publish a webflow site to make changes live
- cms item management
slug: cms-management
source_filename: cms-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Webflow CMS Management\n  description: 'Webflow CMS management workflow combining the Data API for programmatic content operations: site publishing,\n    CMS collection and item management, webhook configuration, and content automation. Used by content managers, developers\n    building CMS integrations, and marketing automation teams.'\n  tags:\n  - Webflow\n  - CMS\n  - Content Management\n  - Publishing\n  - Sites\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBFLOW_API_KEY: WEBFLOW_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: webflow-data\n    baseUri: https://api.webflow.com/v2\n    description: Webflow Data API v2 for sites, CMS, ecommerce, and more.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{WEBFLOW_API_KEY}}\n      placement: header\n    resources:\n    - name: sites\n      path: /sites\n      description: Webflow sites\
  \ within a workspace.\n      operations:\n      - name: list-sites\n        method: GET\n        description: List Sites\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-site\n        method: GET\n        description: Get Site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-site\n        method: POST\n        description: Publish Site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site.\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customDomains: '{{tools.customDomains}}'\n    - name: collections\n      path: /sites/{site_id}/collections\n      description: CMS collections within a Webflow site.\n      operations:\n      - name: list-collections\n        method: GET\n        description: List Collections\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-collection\n        method: GET\n        description: Get Collection\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection.\n    \
  \    outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /collections/{collection_id}/items\n      description: CMS items within a Webflow collection.\n      operations:\n      - name: list-items\n        method: GET\n        description: List Collection Items\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Offset to start returning items from.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: create-item\n        method: POST\n        description: Create Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fieldData: '{{tools.fieldData}}'\n            isArchived: '{{tools.isArchived}}'\n            isDraft: '{{tools.isDraft}}'\n      - name: update-item\n        method: PATCH\n        description: Update Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection.\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for\
  \ a CMS item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fieldData: '{{tools.fieldData}}'\n      - name: delete-item\n        method: DELETE\n        description: Delete Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection.\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS item.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-item\n        method: POST\n        description: Publish Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Unique identifier for a CMS collection.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            itemIds: '{{tools.itemIds}}'\n    - name: webhooks\n      path: /sites/{site_id}/webhooks\n      description: Webhooks for real-time event notifications from Webflow.\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List Webhooks\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create Webhook\n        inputParameters:\n        - name: site_id\n          in:\
  \ path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            triggerType: '{{tools.triggerType}}'\n            url: '{{tools.url}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: webflow-cms-api\n    description: Unified REST API for Webflow CMS content management workflows.\n    resources:\n    - path: /v1/sites\n      name: sites\n      description: Webflow site management\n      operations:\n      - method: GET\n        name: list-sites\n        description: List all available Webflow sites\n        call: webflow-data.list-sites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites/{site_id}/publish\n      name: site-publish\n      description: Publish a Webflow site\n      operations:\n\
  \      - method: POST\n        name: publish-site\n        description: Publish a Webflow site to custom domains\n        call: webflow-data.publish-site\n        with:\n          site_id: rest.site_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: CMS collection management\n      operations:\n      - method: GET\n        name: list-collections\n        description: List CMS collections for a site\n        call: webflow-data.list-collections\n        with:\n          site_id: rest.site_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: CMS item management\n      operations:\n      - method: GET\n        name: list-items\n        description: List items in a CMS collection\n        call: webflow-data.list-items\n        with:\n          collection_id: rest.collection_id\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n      - method: POST\n        name: create-item\n        description: Create a new CMS item\n        call: webflow-data.create-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items/{item_id}\n      name: item\n      description: Single CMS item operations\n      operations:\n      - method: PATCH\n        name: update-item\n        description: Update a CMS item\n        call: webflow-data.update-item\n        with:\n          collection_id: rest.collection_id\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-item\n        description: Delete a CMS item\n        call: webflow-data.delete-item\n        with:\n          collection_id: rest.collection_id\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name:\
  \ webhooks\n      description: Webhook management\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhooks for a site\n        call: webflow-data.list-webhooks\n        with:\n          site_id: rest.site_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a webhook for Webflow events\n        call: webflow-data.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: webflow-cms-mcp\n    transport: http\n    description: MCP server for AI-assisted Webflow CMS content management.\n    tools:\n    - name: list-sites\n      description: List all Webflow sites available with the API key\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-sites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ publish-site\n      description: Publish a Webflow site to make changes live\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.publish-site\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-collections\n      description: List CMS collections in a Webflow site\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-collections\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-items\n      description: List all items in a Webflow CMS collection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-items\n      with:\n        collection_id: tools.collection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cms-item\n      description: Create a new content item in a Webflow\
  \ CMS collection\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.create-item\n      with:\n        collection_id: tools.collection_id\n        fieldData: tools.fieldData\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-cms-item\n      description: Update an existing Webflow CMS content item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: webflow-data.update-item\n      with:\n        collection_id: tools.collection_id\n        item_id: tools.item_id\n        fieldData: tools.fieldData\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-cms-items\n      description: Publish CMS items to make them live on the Webflow site\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.publish-item\n      with:\n        collection_id: tools.collection_id\n        itemIds: tools.itemIds\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cms-item\n      description: Delete an item from a Webflow CMS collection\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: webflow-data.delete-item\n      with:\n        collection_id: tools.collection_id\n        item_id: tools.item_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List webhooks registered for a Webflow site\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webflow-data.list-webhooks\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Register a webhook to receive Webflow site events\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.create-webhook\n      with:\n        site_id: tools.site_id\n\
  \        triggerType: tools.triggerType\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
