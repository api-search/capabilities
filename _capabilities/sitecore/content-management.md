---
categories: []
consumed_apis:
- xm-cloud-rest
- content-hub-rest
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
- list content hub entities (assets)
- get a specific content hub digital asset by id
- list all xm cloud sites
- list sites
- create publishing job
- list pages for an xm cloud site
- content management
- get details of a specific site collection
- list xm cloud content publishing jobs
- publishing
- manage content publishing workflows
- list pages for a site
- create a new xm cloud site collection
- manage xm cloud sites
- list publishing jobs
- create and queue a content publishing job to experience edge
- list all sites in the tenant
- get details of a site collection
- create a new page in a site
- manage xm cloud site collections
- list all site collections in xm cloud tenant
- list pages
- list content publishing jobs
- search content hub assets using query language
- get site
- create a new page within an xm cloud site
- list content hub digital assets
- get asset
- digital asset management
- create page
- list all xm cloud site collections
- create site
- search assets
- create and queue a publishing job
- get collection
- headless cms
- create collection
- manage pages within xm cloud sites
- get details of a specific xm cloud site
- sitecore
- list assets
- manage content hub digital assets
- manage a specific site collection
- list collections
- create a new xm cloud site
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Sitecore Content Management\"\n  description: >-\n    Unified capability for managing the full content lifecycle across XM Cloud sites\n    and Content Hub digital assets. Enables developers and content operations teams\n    to automate site provisioning, page management, publishing workflows, and digital\n    asset operations from a single interface.\n  tags:\n    - Sitecore\n    - Content Management\n    - Headless CMS\n    - Digital Asset Management\n    - Publishing\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      XM_CLOUD_API_TOKEN: XM_CLOUD_API_TOKEN\n      CONTENT_HUB_TOKEN: CONTENT_HUB_TOKEN\n      CONTENT_HUB_TENANT: CONTENT_HUB_TENANT\n\ncapability:\n  consumes:\n    - import: xm-cloud-rest\n      location: ./shared/xm-cloud-rest.yaml\n    - import: content-hub-rest\n      location: ./shared/content-hub-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n\
  \      namespace: content-management-api\n      description: \"Unified REST API for Sitecore content management across XM Cloud and Content Hub.\"\n      resources:\n        - path: /v1/collections\n          name: collections\n          description: \"Manage XM Cloud site collections\"\n          operations:\n            - method: GET\n              name: list-collections\n              description: \"List all site collections in XM Cloud tenant\"\n              call: \"xm-cloud-rest.list-collections\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-collection\n              description: \"Create a new XM Cloud site collection\"\n              call: \"xm-cloud-rest.create-collection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/collections/{id}\n          name: collection\n          description: \"Manage\
  \ a specific site collection\"\n          operations:\n            - method: GET\n              name: get-collection\n              description: \"Get details of a site collection\"\n              call: \"xm-cloud-rest.get-collection\"\n              with:\n                collectionId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/sites\n          name: sites\n          description: \"Manage XM Cloud sites\"\n          operations:\n            - method: GET\n              name: list-sites\n              description: \"List all sites in the tenant\"\n              call: \"xm-cloud-rest.list-sites\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-site\n              description: \"Create a new XM Cloud site\"\n              call: \"xm-cloud-rest.create-site\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/pages\n          name: pages\n          description: \"Manage pages within XM Cloud sites\"\n          operations:\n            - method: GET\n              name: list-pages\n              description: \"List pages for a site\"\n              call: \"xm-cloud-rest.list-pages\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-page\n              description: \"Create a new page in a site\"\n              call: \"xm-cloud-rest.create-page\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/publishing-jobs\n          name: publishing-jobs\n          description: \"Manage content publishing workflows\"\n          operations:\n            - method: GET\n              name: list-publishing-jobs\n              description: \"List\
  \ content publishing jobs\"\n              call: \"xm-cloud-rest.list-publishing-jobs\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-publishing-job\n              description: \"Create and queue a publishing job\"\n              call: \"xm-cloud-rest.create-publishing-job\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/assets\n          name: assets\n          description: \"Manage Content Hub digital assets\"\n          operations:\n            - method: GET\n              name: list-assets\n              description: \"List Content Hub entities (assets)\"\n              call: \"content-hub-rest.list-entities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: search-assets\n              description: \"\
  Search Content Hub assets using query language\"\n              call: \"content-hub-rest.query-entities\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: content-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Sitecore content management.\"\n      tools:\n        - name: list-collections\n          description: \"List all XM Cloud site collections\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.list-collections\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-collection\n          description: \"Get details of a specific site collection\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.get-collection\"\n          with:\n            collectionId: \"tools.collectionId\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-collection\n          description: \"Create a new XM Cloud site collection\"\n          call: \"xm-cloud-rest.create-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-sites\n          description: \"List all XM Cloud sites\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.list-sites\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-site\n          description: \"Get details of a specific XM Cloud site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.get-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name:\
  \ create-site\n          description: \"Create a new XM Cloud site\"\n          call: \"xm-cloud-rest.create-site\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-pages\n          description: \"List pages for an XM Cloud site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.list-pages\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: create-page\n          description: \"Create a new page within an XM Cloud site\"\n          call: \"xm-cloud-rest.create-page\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-publishing-jobs\n          description: \"List XM Cloud content publishing jobs\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"xm-cloud-rest.list-publishing-jobs\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: create-publishing-job\n          description: \"Create and queue a content publishing job to Experience Edge\"\n          call: \"xm-cloud-rest.create-publishing-job\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-assets\n          description: \"List Content Hub digital assets\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"content-hub-rest.list-entities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-asset\n          description: \"Get a specific Content Hub digital asset by ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"content-hub-rest.get-entity\"\n          with:\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"\
  $.\"\n\n        - name: search-assets\n          description: \"Search Content Hub assets using query language\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"content-hub-rest.query-entities\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
