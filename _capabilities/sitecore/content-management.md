---
categories: []
consumed_apis: []
description: Unified capability for managing the full content lifecycle across XM Cloud sites and Content Hub digital assets. Enables developers and content operations teams to automate site provisioning, page management, publishing workflows, and digital asset operations from a single interface.
layout: capability
name: Sitecore Content Management
operations:
- description: List all site collections in XM Cloud tenant
  method: GET
  name: list-collections
  path: /v1/collections
- description: Create a new XM Cloud site collection
  method: POST
  name: create-collection
  path: /v1/collections
- description: Get details of a site collection
  method: GET
  name: get-collection
  path: /v1/collections/{id}
- description: List all sites in the tenant
  method: GET
  name: list-sites
  path: /v1/sites
- description: Create a new XM Cloud site
  method: POST
  name: create-site
  path: /v1/sites
- description: List pages for a site
  method: GET
  name: list-pages
  path: /v1/pages
- description: Create a new page in a site
  method: POST
  name: create-page
  path: /v1/pages
- description: List content publishing jobs
  method: GET
  name: list-publishing-jobs
  path: /v1/publishing-jobs
- description: Create and queue a publishing job
  method: POST
  name: create-publishing-job
  path: /v1/publishing-jobs
- description: List Content Hub entities (assets)
  method: GET
  name: list-assets
  path: /v1/assets
- description: Search Content Hub assets using query language
  method: POST
  name: search-assets
  path: /v1/assets
personas: []
provider_name: sitecore
provider_slug: sitecore
search_terms:
- list all xm cloud sites
- get a specific content hub digital asset by id
- get details of a site collection
- manage a specific site collection
- list content hub digital assets
- publishing
- list all site collections in xm cloud tenant
- search assets
- manage xm cloud sites
- create site
- get site
- create and queue a publishing job
- create a new page in a site
- list pages for an xm cloud site
- list sites
- create a new page within an xm cloud site
- list publishing jobs
- digital asset management
- manage xm cloud site collections
- manage content publishing workflows
- list assets
- get details of a specific xm cloud site
- create publishing job
- list collections
- create and queue a content publishing job to experience edge
- create a new xm cloud site
- list all sites in the tenant
- list content publishing jobs
- content management
- manage pages within xm cloud sites
- list pages
- create a new xm cloud site collection
- list all xm cloud site collections
- create collection
- create page
- get asset
- get details of a specific site collection
- headless cms
- get collection
- list content hub entities (assets)
- manage content hub digital assets
- sitecore
- list xm cloud content publishing jobs
- list pages for a site
- search content hub assets using query language
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sitecore Content Management\n  description: Unified capability for managing the full content lifecycle across XM Cloud sites and Content Hub digital assets.\n    Enables developers and content operations teams to automate site provisioning, page management, publishing workflows,\n    and digital asset operations from a single interface.\n  tags:\n  - Sitecore\n  - Content Management\n  - Headless CMS\n  - Digital Asset Management\n  - Publishing\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    XM_CLOUD_API_TOKEN: XM_CLOUD_API_TOKEN\n    CONTENT_HUB_TOKEN: CONTENT_HUB_TOKEN\n    CONTENT_HUB_TENANT: CONTENT_HUB_TENANT\ncapability:\n  consumes:\n  - type: http\n    namespace: xm-cloud-rest\n    baseUri: https://xmapps-api.sitecorecloud.io\n    description: Sitecore XM Cloud REST API for site and publishing management\n    authentication:\n      type: bearer\n      token: '{{XM_CLOUD_API_TOKEN}}'\n\
  \    resources:\n    - name: collections\n      path: /api/v1/collections\n      description: Manage site collections within an XM Cloud tenant\n      operations:\n      - name: list-collections\n        method: GET\n        description: List all site collections in the tenant\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-collection\n        method: POST\n        description: Create a new site collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            displayName: '{{tools.displayName}}'\n      - name: validate-collection-name\n        method: POST\n        description: Validate a proposed collection name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n    - name: collection\n      path: /api/v1/collections/{collectionId}\n      description: Manage a specific site collection\n      operations:\n      - name: get-collection\n        method: GET\n        description: Get a site collection by ID\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the site collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-collection\n        method: PUT\n        description: Update a site collection\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the site collection\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n      - name: delete-collection\n        method: DELETE\n        description: Delete a site collection\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the site collection\n    - name: sites\n      path: /api/v1/sites\n      description: Manage sites within an XM Cloud tenant\n      operations:\n      - name: list-sites\n        method: GET\n        description: List all sites in the tenant\n        inputParameters:\n        - name: collectionId\n          in: query\n          type: string\n          required: false\n          description: Filter sites by collection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n\
  \          value: $.\n      - name: create-site\n        method: POST\n        description: Create a new site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            collectionId: '{{tools.collectionId}}'\n            language: '{{tools.language}}'\n    - name: site\n      path: /api/v1/sites/{siteId}\n      description: Manage a specific site\n      operations:\n      - name: get-site\n        method: GET\n        description: Get a site by ID\n        inputParameters:\n        - name: siteId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-site\n        method: DELETE\n        description:\
  \ Delete a site\n        inputParameters:\n        - name: siteId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the site\n    - name: pages\n      path: /api/v1/pages\n      description: Manage pages within an XM Cloud site\n      operations:\n      - name: list-pages\n        method: GET\n        description: List pages for a site\n        inputParameters:\n        - name: siteId\n          in: query\n          type: string\n          required: false\n          description: Filter by site\n        - name: language\n          in: query\n          type: string\n          required: false\n          description: Language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: create-page\n        method: POST\n        description: Create a new page in a site\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            siteId: '{{tools.siteId}}'\n            parentId: '{{tools.parentId}}'\n            templateId: '{{tools.templateId}}'\n            language: '{{tools.language}}'\n    - name: publishing-jobs\n      path: /authoring/publishing/v1/jobs\n      description: Manage content publishing jobs\n      operations:\n      - name: list-publishing-jobs\n        method: GET\n        description: List publishing jobs for the tenant\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by job status\n        - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Number of jobs per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: create-publishing-job\n        method: POST\n        description: Create and queue a publishing job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            targetId: '{{tools.targetId}}'\n            itemIds: '{{tools.itemIds}}'\n            languages: '{{tools.languages}}'\n  - type: http\n    namespace: content-hub-rest\n    baseUri: https://{{CONTENT_HUB_TENANT}}.stylelabs.io/api\n    description: Sitecore Content Hub REST API for digital asset management\n    authentication:\n      type: bearer\n      token: '{{CONTENT_HUB_TOKEN}}'\n    resources:\n    - name: entities\n      path: /entities\n      description: Manage Content Hub entities (assets, metadata, configurations)\n      operations:\n      - name: list-entities\n        method: GET\n        description: List Content Hub entities with filtering\n       \
  \ inputParameters:\n        - name: take\n          in: query\n          type: integer\n          required: false\n          description: Number of entities to return\n        - name: skip\n          in: query\n          type: integer\n          required: false\n          description: Offset for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-entity\n        method: POST\n        description: Create a new Content Hub entity\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            identifier: '{{tools.identifier}}'\n    - name: entity\n      path: /entities/{id}\n      description: Manage a specific Content Hub entity\n      operations:\n      - name: get-entity\n        method: GET\n        description: Get a Content Hub entity by ID\n     \
  \   inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The entity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-entity\n        method: PUT\n        description: Update a Content Hub entity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The entity ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            properties: '{{tools.properties}}'\n    - name: search\n      path: /entities/query\n      description: Search Content Hub entities using query language\n      operations:\n      - name: query-entities\n        method: POST\n        description: Search entities using Content\
  \ Hub query language\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            take: '{{tools.take}}'\n    - name: jobs\n      path: /jobs\n      description: Manage Content Hub processing jobs\n      operations:\n      - name: list-jobs\n        method: GET\n        description: List Content Hub jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: content-management-api\n    description: Unified REST API for Sitecore content management across XM Cloud and Content Hub.\n    resources:\n    - path: /v1/collections\n      name: collections\n      description: Manage XM Cloud site collections\n      operations:\n      - method: GET\n        name: list-collections\n        description:\
  \ List all site collections in XM Cloud tenant\n        call: xm-cloud-rest.list-collections\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-collection\n        description: Create a new XM Cloud site collection\n        call: xm-cloud-rest.create-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/collections/{id}\n      name: collection\n      description: Manage a specific site collection\n      operations:\n      - method: GET\n        name: get-collection\n        description: Get details of a site collection\n        call: xm-cloud-rest.get-collection\n        with:\n          collectionId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sites\n      name: sites\n      description: Manage XM Cloud sites\n      operations:\n      - method: GET\n        name: list-sites\n        description: List all sites in the tenant\n\
  \        call: xm-cloud-rest.list-sites\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-site\n        description: Create a new XM Cloud site\n        call: xm-cloud-rest.create-site\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages\n      name: pages\n      description: Manage pages within XM Cloud sites\n      operations:\n      - method: GET\n        name: list-pages\n        description: List pages for a site\n        call: xm-cloud-rest.list-pages\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-page\n        description: Create a new page in a site\n        call: xm-cloud-rest.create-page\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/publishing-jobs\n      name: publishing-jobs\n      description: Manage content publishing workflows\n      operations:\n \
  \     - method: GET\n        name: list-publishing-jobs\n        description: List content publishing jobs\n        call: xm-cloud-rest.list-publishing-jobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-publishing-job\n        description: Create and queue a publishing job\n        call: xm-cloud-rest.create-publishing-job\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/assets\n      name: assets\n      description: Manage Content Hub digital assets\n      operations:\n      - method: GET\n        name: list-assets\n        description: List Content Hub entities (assets)\n        call: content-hub-rest.list-entities\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: search-assets\n        description: Search Content Hub assets using query language\n        call: content-hub-rest.query-entities\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: content-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Sitecore content management.\n    tools:\n    - name: list-collections\n      description: List all XM Cloud site collections\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.list-collections\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-collection\n      description: Get details of a specific site collection\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.get-collection\n      with:\n        collectionId: tools.collectionId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-collection\n      description: Create a new XM Cloud site collection\n      call: xm-cloud-rest.create-collection\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-sites\n      description: List all XM Cloud sites\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.list-sites\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-site\n      description: Get details of a specific XM Cloud site\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.get-site\n      with:\n        siteId: tools.siteId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-site\n      description: Create a new XM Cloud site\n      call: xm-cloud-rest.create-site\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-pages\n      description: List pages for an XM Cloud site\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.list-pages\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: create-page\n      description:\
  \ Create a new page within an XM Cloud site\n      call: xm-cloud-rest.create-page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-publishing-jobs\n      description: List XM Cloud content publishing jobs\n      hints:\n        readOnly: true\n        idempotent: true\n      call: xm-cloud-rest.list-publishing-jobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-publishing-job\n      description: Create and queue a content publishing job to Experience Edge\n      call: xm-cloud-rest.create-publishing-job\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-assets\n      description: List Content Hub digital assets\n      hints:\n        readOnly: true\n        idempotent: true\n      call: content-hub-rest.list-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-asset\n      description: Get a specific Content Hub digital asset by ID\n\
  \      hints:\n        readOnly: true\n        idempotent: true\n      call: content-hub-rest.get-entity\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-assets\n      description: Search Content Hub assets using query language\n      hints:\n        readOnly: true\n        openWorld: true\n      call: content-hub-rest.query-entities\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sitecore/refs/heads/main/capabilities/content-management.yaml
tags:
- Sitecore
- Content Management
- Headless CMS
- Digital Asset Management
- Publishing
tools:
- description: List all XM Cloud site collections
  hints:
    idempotent: true
    readOnly: true
  name: list-collections
- description: Get details of a specific site collection
  hints:
    idempotent: true
    readOnly: true
  name: get-collection
- description: Create a new XM Cloud site collection
  hints: {}
  name: create-collection
- description: List all XM Cloud sites
  hints:
    idempotent: true
    readOnly: true
  name: list-sites
- description: Get details of a specific XM Cloud site
  hints:
    idempotent: true
    readOnly: true
  name: get-site
- description: Create a new XM Cloud site
  hints: {}
  name: create-site
- description: List pages for an XM Cloud site
  hints:
    idempotent: true
    readOnly: true
  name: list-pages
- description: Create a new page within an XM Cloud site
  hints: {}
  name: create-page
- description: List XM Cloud content publishing jobs
  hints:
    idempotent: true
    readOnly: true
  name: list-publishing-jobs
- description: Create and queue a content publishing job to Experience Edge
  hints: {}
  name: create-publishing-job
- description: List Content Hub digital assets
  hints:
    idempotent: true
    readOnly: true
  name: list-assets
- description: Get a specific Content Hub digital asset by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-asset
- description: Search Content Hub assets using query language
  hints:
    openWorld: true
    readOnly: true
  name: search-assets
---
