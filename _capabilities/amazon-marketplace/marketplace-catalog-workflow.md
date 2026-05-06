---
categories: []
consumed_apis: []
description: Workflow capability for ISV sellers and marketplace operators to publish, update, and manage software products and offers on AWS Marketplace using the Catalog API.
layout: capability
name: Amazon Marketplace - Catalog Management Workflow
operations:
- description: List entities available in the marketplace catalog.
  method: POST
  name: list-entities
  path: /v1/entities
- description: Get details of a specific marketplace entity.
  method: GET
  name: describe-entity
  path: /v1/entities
- description: List change sets in the marketplace catalog.
  method: POST
  name: list-change-sets
  path: /v1/change-sets
- description: Get details of a specific change set.
  method: GET
  name: describe-change-set
  path: /v1/change-sets
- description: Start a change set to publish or update a marketplace entity.
  method: POST
  name: start-change-set
  path: /v1/publish
personas: []
provider_name: Amazon Marketplace
provider_slug: amazon-marketplace
search_terms:
- start a change set to publish or update a marketplace entity.
- marketplace
- initiate a change set to publish a new product or update an existing marketplace listing.
- workflow for isv sellers to publish, update, and manage products on aws marketplace.
- list software products, offers, and data products available in the aws marketplace catalog.
- list change sets for tracking publishing and update operations on marketplace entities.
- list entities available in the marketplace catalog.
- amazon
- platform operator managing marketplace listings, policies, and change sets at scale.
- start change set
- get detailed information about a specific aws marketplace entity including its attributes and status.
- cancel an active change set that has not yet completed.
- list change sets
- list entities
- manage change sets for publishing and updating marketplace entities.
- commerce
- isv
- Marketplace Operator
- describe entity
- get details of a specific marketplace entity.
- publishing and updating software products and offers on aws marketplace.
- ISV Seller
- describe marketplace entity
- get details of a specific change set.
- managing resource policies for marketplace entities.
- describe change set
- cancel change set
- get resource policy
- manage marketplace entities (products, offers).
- get the status and details of a specific marketplace change set.
- publish and update marketplace listings.
- software catalog
- retrieve the resource-based policy attached to a marketplace entity.
- list change sets in the marketplace catalog.
- independent software vendor publishing and managing products on aws marketplace.
- list marketplace entities
slug: marketplace-catalog-workflow
source_filename: marketplace-catalog-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Marketplace - Catalog Management Workflow\n  description: Workflow capability for ISV sellers and marketplace operators to publish, update, and manage software products\n    and offers on AWS Marketplace using the Catalog API.\n  tags:\n  - Amazon\n  - Marketplace\n  - Commerce\n  - Software Catalog\n  - ISV\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: marketplace-catalog\n    baseUri: https://catalog.marketplace.us-east-1.amazonaws.com\n    description: AWS Marketplace Catalog API for managing entities and change sets.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: entities\n      path: /ListEntities\n\
  \      description: Manage marketplace entities (products, offers, data products).\n      operations:\n      - name: list-entities\n        method: POST\n        description: List entities in the catalog.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-entity\n        method: GET\n        description: Describe a specific marketplace entity.\n        inputParameters:\n        - name: catalog\n          in: query\n          type: string\n          required: true\n          description: The catalog identifier.\n        - name: entityId\n          in: query\n          type: string\n          required: true\n          description: The entity identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: change-sets\n      path: /ListChangeSets\n      description: Manage change sets for publishing and updating\
  \ entities.\n      operations:\n      - name: list-change-sets\n        method: POST\n        description: List change sets in the catalog.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-change-set\n        method: GET\n        description: Describe a specific change set.\n        inputParameters:\n        - name: catalog\n          in: query\n          type: string\n          required: true\n          description: The catalog identifier.\n        - name: changeSetId\n          in: query\n          type: string\n          required: true\n          description: The change set identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-change-set\n        method: POST\n        description: Start a new change set to update or publish a marketplace entity.\n        body:\n          type: json\n\
  \          data:\n            catalog: '{{tools.catalog}}'\n            changeSet: '{{tools.changeSet}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-change-set\n        method: PATCH\n        description: Cancel an active change set.\n        inputParameters:\n        - name: catalog\n          in: query\n          type: string\n          required: true\n          description: The catalog identifier.\n        - name: changeSetId\n          in: query\n          type: string\n          required: true\n          description: The change set identifier to cancel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource-policies\n      path: /GetResourcePolicy\n      description: Manage resource-based policies for marketplace entities.\n      operations:\n      - name: get-resource-policy\n       \
  \ method: GET\n        description: Get the resource-based policy for a marketplace entity.\n        inputParameters:\n        - name: resourceArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-resource-policy\n        method: POST\n        description: Attach a resource-based policy to a marketplace entity.\n        body:\n          type: json\n          data:\n            resourceArn: '{{tools.resourceArn}}'\n            policy: '{{tools.policy}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-resource-policy\n        method: DELETE\n        description: Delete the resource-based policy from a marketplace entity.\n        inputParameters:\n        - name: resourceArn\n\
  \          in: query\n          type: string\n          required: true\n          description: The ARN of the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /ListTagsForResource\n      description: Manage tags for marketplace resources.\n      operations:\n      - name: list-tags-for-resource\n        method: GET\n        description: List tags for a marketplace resource.\n        inputParameters:\n        - name: resourceArn\n          in: query\n          type: string\n          required: true\n          description: The ARN of the resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: tag-resource\n        method: POST\n        description: Add tags to a marketplace resource.\n        body:\n          type: json\n          data:\n            resourceArn: '{{tools.resourceArn}}'\n\
  \            tags: '{{tools.tags}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: untag-resource\n        method: DELETE\n        description: Remove tags from a marketplace resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: marketplace-workflow-api\n    description: Unified REST API for AWS Marketplace catalog management workflows.\n    resources:\n    - path: /v1/entities\n      name: entities\n      description: Manage marketplace entities (products, offers).\n      operations:\n      - method: POST\n        name: list-entities\n        description: List entities available in the marketplace catalog.\n        call: marketplace-catalog.list-entities\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n \
  \       name: describe-entity\n        description: Get details of a specific marketplace entity.\n        call: marketplace-catalog.describe-entity\n        with:\n          catalog: rest.catalog\n          entityId: rest.entityId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/change-sets\n      name: change-sets\n      description: Manage change sets for publishing and updating marketplace entities.\n      operations:\n      - method: POST\n        name: list-change-sets\n        description: List change sets in the marketplace catalog.\n        call: marketplace-catalog.list-change-sets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: describe-change-set\n        description: Get details of a specific change set.\n        call: marketplace-catalog.describe-change-set\n        with:\n          catalog: rest.catalog\n          changeSetId: rest.changeSetId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/publish\n      name: publish\n      description: Publish and update marketplace listings.\n      operations:\n      - method: POST\n        name: start-change-set\n        description: Start a change set to publish or update a marketplace entity.\n        call: marketplace-catalog.start-change-set\n        with:\n          catalog: rest.catalog\n          changeSet: rest.changeSet\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: marketplace-workflow-mcp\n    transport: http\n    description: MCP server for AI-assisted AWS Marketplace catalog management.\n    tools:\n    - name: list-marketplace-entities\n      description: List software products, offers, and data products available in the AWS Marketplace catalog.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: marketplace-catalog.list-entities\n      outputParameters:\n    \
  \  - type: object\n        mapping: $.\n    - name: describe-marketplace-entity\n      description: Get detailed information about a specific AWS Marketplace entity including its attributes and status.\n      hints:\n        readOnly: true\n      call: marketplace-catalog.describe-entity\n      with:\n        catalog: tools.catalog\n        entityId: tools.entityId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-change-sets\n      description: List change sets for tracking publishing and update operations on marketplace entities.\n      hints:\n        readOnly: true\n      call: marketplace-catalog.list-change-sets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-change-set\n      description: Get the status and details of a specific marketplace change set.\n      hints:\n        readOnly: true\n      call: marketplace-catalog.describe-change-set\n      with:\n        catalog: tools.catalog\n        changeSetId:\
  \ tools.changeSetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-change-set\n      description: Initiate a change set to publish a new product or update an existing marketplace listing.\n      hints:\n        readOnly: false\n      call: marketplace-catalog.start-change-set\n      with:\n        catalog: tools.catalog\n        changeSet: tools.changeSet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-change-set\n      description: Cancel an active change set that has not yet completed.\n      hints:\n        readOnly: false\n        destructive: false\n      call: marketplace-catalog.cancel-change-set\n      with:\n        catalog: tools.catalog\n        changeSetId: tools.changeSetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-resource-policy\n      description: Retrieve the resource-based policy attached to a marketplace entity.\n      hints:\n        readOnly: true\n\
  \      call: marketplace-catalog.get-resource-policy\n      with:\n        resourceArn: tools.resourceArn\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-marketplace/refs/heads/main/capabilities/marketplace-catalog-workflow.yaml
tags:
- Amazon
- Marketplace
- Commerce
- Software Catalog
- ISV
tools:
- description: List software products, offers, and data products available in the AWS Marketplace catalog.
  hints:
    openWorld: true
    readOnly: true
  name: list-marketplace-entities
- description: Get detailed information about a specific AWS Marketplace entity including its attributes and status.
  hints:
    readOnly: true
  name: describe-marketplace-entity
- description: List change sets for tracking publishing and update operations on marketplace entities.
  hints:
    readOnly: true
  name: list-change-sets
- description: Get the status and details of a specific marketplace change set.
  hints:
    readOnly: true
  name: describe-change-set
- description: Initiate a change set to publish a new product or update an existing marketplace listing.
  hints:
    readOnly: false
  name: start-change-set
- description: Cancel an active change set that has not yet completed.
  hints:
    destructive: false
    readOnly: false
  name: cancel-change-set
- description: Retrieve the resource-based policy attached to a marketplace entity.
  hints:
    readOnly: true
  name: get-resource-policy
---
