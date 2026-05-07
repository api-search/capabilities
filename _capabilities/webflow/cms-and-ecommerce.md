---
categories: []
consumed_apis: []
description: Unified Webflow capability combining Data API for CMS content management and ecommerce operations. Enables content managers to create and publish CMS items, developers to automate workflows via webhooks, and ecommerce managers to manage products and orders. Primary workflow for organizations using Webflow as a headless CMS or ecommerce platform.
layout: capability
name: Webflow CMS and Ecommerce
operations:
- description: List all Webflow sites
  method: GET
  name: list-sites
  path: /v1/sites
- description: Publish site to all domains
  method: POST
  name: publish-site
  path: /v1/sites/{site_id}/publish
- description: List CMS collections
  method: GET
  name: list-collections
  path: /v1/collections
- description: List CMS items
  method: GET
  name: list-items
  path: /v1/items
- description: Create a CMS item
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
- description: List webhooks
  method: GET
  name: list-webhooks
  path: /v1/webhooks
- description: Create a webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
personas: []
provider_name: Webflow
provider_slug: webflow
search_terms:
- sites
- web development
- publish cms items
- publish site to all domains
- publish a webflow site
- list items
- update item
- create a new content item in a webflow cms collection
- publishing
- publish a webflow site to make changes live
- ecommerce
- update a cms item
- create item
- delete a cms item permanently
- create webhook
- list cms collections
- publish cms items to make them live on the webflow site
- create a webhook to receive webflow site events
- create a cms item
- list sites
- list all items in a webflow cms collection
- delete a cms item
- cms
- update an existing webflow cms item
- list webhooks
- cms item management
- list all webflow sites accessible with the api key
- list collections
- list all webflow sites
- list cms items
- webhook event subscriptions
- delete cms item
- list registered webhooks for a webflow site
- delete item
- webflow
- create a webhook
- cms collection management
- content management
- publish site
- update cms item
- list cms collections in a webflow site
- create cms item
- webflow site management
- no-code
- single cms item operations
slug: cms-and-ecommerce
source_filename: cms-and-ecommerce.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Webflow CMS and Ecommerce\n  description: Unified Webflow capability combining Data API for CMS content management and ecommerce operations. Enables\n    content managers to create and publish CMS items, developers to automate workflows via webhooks, and ecommerce managers\n    to manage products and orders. Primary workflow for organizations using Webflow as a headless CMS or ecommerce platform.\n  tags:\n  - Webflow\n  - CMS\n  - Content Management\n  - Ecommerce\n  - Publishing\n  - Sites\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WEBFLOW_API_KEY: WEBFLOW_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: webflow-data\n    baseUri: https://api.webflow.com/v2\n    description: Webflow Data API v2\n    authentication:\n      type: apikey\n      key: Authorization\n      value: Bearer {{WEBFLOW_API_KEY}}\n      placement: header\n    resources:\n    - name: sites\n      path:\
  \ /sites\n      description: Webflow sites within a workspace\n      operations:\n      - name: list-sites\n        method: GET\n        description: List Sites\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-site\n        method: GET\n        description: Get Site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-site\n        method: POST\n        description: Publish Site\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            customDomains: '{{tools.customDomains}}'\n    - name: collections\n      path: /sites/{site_id}/collections\n      description: CMS collections within a Webflow site\n      operations:\n      - name: list-collections\n        method: GET\n        description: List Collections\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-collection\n        method: GET\n        description: Get Collection\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier\
  \ for a CMS collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: items\n      path: /collections/{collection_id}/items\n      description: CMS items within a Webflow collection\n      operations:\n      - name: list-items\n        method: GET\n        description: List Collection Items\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of items to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-item\n        method: POST\n        description: Create Item\n        inputParameters:\n        - name: collection_id\n  \
  \        in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            fieldData: '{{tools.fieldData}}'\n            isDraft: '{{tools.isDraft}}'\n      - name: update-item\n        method: PATCH\n        description: Update Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n        \
  \  data:\n            fieldData: '{{tools.fieldData}}'\n      - name: delete-item\n        method: DELETE\n        description: Delete Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS item\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: publish-item\n        method: POST\n        description: Publish Item\n        inputParameters:\n        - name: collection_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a CMS collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n        body:\n          type: json\n          data:\n            itemIds: '{{tools.itemIds}}'\n    - name: webhooks\n      path: /sites/{site_id}/webhooks\n      description: Webhooks for Webflow site event notifications\n      operations:\n      - name: list-webhooks\n        method: GET\n        description: List Webhooks\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-webhook\n        method: POST\n        description: Create Webhook\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier for a Webflow site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            triggerType: '{{tools.triggerType}}'\n            url: '{{tools.url}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: webflow-cms-ecommerce-api\n    description: Unified REST API for Webflow CMS and ecommerce management.\n    resources:\n    - path: /v1/sites\n      name: sites\n      description: Webflow site management\n      operations:\n      - method: GET\n        name: list-sites\n        description: List all Webflow sites\n        call: webflow-data.list-sites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites/{site_id}/publish\n      name: site-publish\n      description: Publish a Webflow site\n      operations:\n      - method: POST\n        name: publish-site\n        description: Publish site to all domains\n        call: webflow-data.publish-site\n        with:\n          site_id: rest.site_id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/collections\n      name: collections\n      description: CMS collection management\n      operations:\n      - method: GET\n        name: list-collections\n        description: List CMS collections\n        call: webflow-data.list-collections\n        with:\n          site_id: rest.site_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/items\n      name: items\n      description: CMS item management\n      operations:\n      - method: GET\n        name: list-items\n        description: List CMS items\n        call: webflow-data.list-items\n        with:\n          collection_id: rest.collection_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-item\n        description: Create a CMS item\n        call: webflow-data.create-item\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/items/{item_id}\n      name: item\n      description: Single CMS item operations\n      operations:\n      - method: PATCH\n        name: update-item\n        description: Update a CMS item\n        call: webflow-data.update-item\n        with:\n          collection_id: rest.collection_id\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-item\n        description: Delete a CMS item\n        call: webflow-data.delete-item\n        with:\n          collection_id: rest.collection_id\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Webhook event subscriptions\n      operations:\n      - method: GET\n        name: list-webhooks\n        description: List webhooks\n        call: webflow-data.list-webhooks\n        with:\n          site_id: rest.site_id\n      \
  \  outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-webhook\n        description: Create a webhook\n        call: webflow-data.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: webflow-cms-ecommerce-mcp\n    transport: http\n    description: MCP server for AI-assisted Webflow CMS and ecommerce management.\n    tools:\n    - name: list-sites\n      description: List all Webflow sites accessible with the API key\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-sites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-site\n      description: Publish a Webflow site to make changes live\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.publish-site\n      with:\n        site_id: tools.site_id\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: list-collections\n      description: List CMS collections in a Webflow site\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-collections\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-cms-items\n      description: List all items in a Webflow CMS collection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: webflow-data.list-items\n      with:\n        collection_id: tools.collection_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-cms-item\n      description: Create a new content item in a Webflow CMS collection\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.create-item\n      with:\n        collection_id: tools.collection_id\n        fieldData: tools.fieldData\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: update-cms-item\n      description: Update an existing Webflow CMS item\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: webflow-data.update-item\n      with:\n        collection_id: tools.collection_id\n        item_id: tools.item_id\n        fieldData: tools.fieldData\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-cms-items\n      description: Publish CMS items to make them live on the Webflow site\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.publish-item\n      with:\n        collection_id: tools.collection_id\n        itemIds: tools.itemIds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-cms-item\n      description: Delete a CMS item permanently\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: webflow-data.delete-item\n\
  \      with:\n        collection_id: tools.collection_id\n        item_id: tools.item_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-webhooks\n      description: List registered webhooks for a Webflow site\n      hints:\n        readOnly: true\n        openWorld: false\n      call: webflow-data.list-webhooks\n      with:\n        site_id: tools.site_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Create a webhook to receive Webflow site events\n      hints:\n        readOnly: false\n        destructive: false\n      call: webflow-data.create-webhook\n      with:\n        site_id: tools.site_id\n        triggerType: tools.triggerType\n        url: tools.url\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/webflow/refs/heads/main/capabilities/cms-and-ecommerce.yaml
tags:
- Webflow
- CMS
- Content Management
- Ecommerce
- Publishing
- Sites
tools:
- description: List all Webflow sites accessible with the API key
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
  name: list-cms-items
- description: Create a new content item in a Webflow CMS collection
  hints:
    destructive: false
    readOnly: false
  name: create-cms-item
- description: Update an existing Webflow CMS item
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
- description: Delete a CMS item permanently
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cms-item
- description: List registered webhooks for a Webflow site
  hints:
    openWorld: false
    readOnly: true
  name: list-webhooks
- description: Create a webhook to receive Webflow site events
  hints:
    destructive: false
    readOnly: false
  name: create-webhook
---
