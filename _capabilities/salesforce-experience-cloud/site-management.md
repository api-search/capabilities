---
categories: []
consumed_apis:
- exp-cloud-sites
- exp-cloud-cms
description: Workflow capability for managing Salesforce Experience Cloud digital experience sites and CMS content. Combines site configuration, CMS content management, and publishing workflows for digital experience administrators and developers.
layout: capability
name: Salesforce Experience Cloud Site Management
operations:
- description: List all Experience Cloud sites.
  method: GET
  name: list-sites
  path: /v1/sites
- description: Create a new Experience Cloud site.
  method: POST
  name: create-site
  path: /v1/sites
- description: Get an Experience Cloud site by ID.
  method: GET
  name: get-site
  path: /v1/sites/{siteId}
- description: Update site configuration.
  method: PATCH
  name: update-site
  path: /v1/sites/{siteId}
- description: Publish an Experience Cloud site.
  method: POST
  name: publish-site
  path: /v1/sites/{siteId}/publish
- description: List all CMS channels.
  method: GET
  name: list-cms-channels
  path: /v1/cms/channels
- description: List CMS content items.
  method: GET
  name: list-cms-contents
  path: /v1/cms/contents
- description: Create a new CMS content item.
  method: POST
  name: create-cms-content
  path: /v1/cms/contents
- description: Get a CMS content item.
  method: GET
  name: get-cms-content
  path: /v1/cms/contents/{contentId}
- description: Update a CMS content item.
  method: PATCH
  name: update-cms-content
  path: /v1/cms/contents/{contentId}
- description: Publish a CMS content item.
  method: POST
  name: publish-cms-content
  path: /v1/cms/contents/{contentId}/publish
personas: []
provider_name: Salesforce Experience Cloud
provider_slug: salesforce-experience-cloud
search_terms:
- cms
- cms content delivery channels.
- list sites
- customer portal
- create experience cloud site
- create a new cms content item in salesforce experience cloud.
- list cms contents
- list cms content items across channels.
- list all experience cloud digital experience sites.
- list cms content items.
- communities
- digital experiences
- publish a cms content item to make it live on digital experiences.
- publish site
- publishing
- create site
- experience cloud
- publish a cms content item.
- list all experience cloud sites.
- create cms content
- digital experience
- get site
- list all cms channels.
- update a cms content item.
- get a specific experience cloud site by id.
- get cms content
- create a new experience cloud digital experience site.
- list all cms delivery channels for content publishing.
- partner portal
- get a cms content item.
- update site
- create a new cms content item.
- publish an experience cloud site to make it publicly accessible.
- salesforce experience cloud
- crm
- update site configuration.
- get an experience cloud site by id.
- list experience cloud sites
- publish an experience cloud site.
- create a new experience cloud site.
- publish experience cloud site
- sites
- list cms channels
- update cms content
- cms content items.
- get experience cloud site
- content management
- publish cms content
- list cms content
- experience cloud sites.
slug: site-management
source_filename: site-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Experience Cloud Site Management\"\n  description: >-\n    Workflow capability for managing Salesforce Experience Cloud digital experience\n    sites and CMS content. Combines site configuration, CMS content management,\n    and publishing workflows for digital experience administrators and developers.\n  tags:\n    - CMS\n    - Communities\n    - Content Management\n    - Digital Experiences\n    - Publishing\n    - Salesforce Experience Cloud\n    - Sites\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_OAUTH2_TOKEN: SALESFORCE_OAUTH2_TOKEN\n      SALESFORCE_INSTANCE_URL: SALESFORCE_INSTANCE_URL\n\ncapability:\n  consumes:\n    - import: exp-cloud-sites\n      location: ./shared/sites-api.yaml\n    - import: exp-cloud-cms\n      location: ./shared/cms-connect-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: exp-cloud-site-management-api\n\
  \      description: \"Unified REST API for Experience Cloud site and content management.\"\n      resources:\n        - path: /v1/sites\n          name: sites\n          description: \"Experience Cloud sites.\"\n          operations:\n            - method: GET\n              name: list-sites\n              description: \"List all Experience Cloud sites.\"\n              call: \"exp-cloud-sites.list-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-site\n              description: \"Create a new Experience Cloud site.\"\n              call: \"exp-cloud-sites.create-site\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sites/{siteId}\n          name: site-by-id\n          operations:\n            - method: GET\n              name: get-site\n              description: \"Get an Experience Cloud site by ID.\"\
  \n              call: \"exp-cloud-sites.get-site\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-site\n              description: \"Update site configuration.\"\n              call: \"exp-cloud-sites.update-site\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sites/{siteId}/publish\n          name: publish-site\n          operations:\n            - method: POST\n              name: publish-site\n              description: \"Publish an Experience Cloud site.\"\n              call: \"exp-cloud-sites.publish-site\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        -\
  \ path: /v1/cms/channels\n          name: cms-channels\n          description: \"CMS content delivery channels.\"\n          operations:\n            - method: GET\n              name: list-cms-channels\n              description: \"List all CMS channels.\"\n              call: \"exp-cloud-cms.list-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cms/contents\n          name: cms-contents\n          description: \"CMS content items.\"\n          operations:\n            - method: GET\n              name: list-cms-contents\n              description: \"List CMS content items.\"\n              call: \"exp-cloud-cms.list-contents\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-cms-content\n              description: \"Create a new CMS content item.\"\n              call: \"exp-cloud-cms.create-content\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cms/contents/{contentId}\n          name: cms-content-by-id\n          operations:\n            - method: GET\n              name: get-cms-content\n              description: \"Get a CMS content item.\"\n              call: \"exp-cloud-cms.get-content\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: update-cms-content\n              description: \"Update a CMS content item.\"\n              call: \"exp-cloud-cms.update-content\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/cms/contents/{contentId}/publish\n          name: publish-content\n          operations:\n\
  \            - method: POST\n              name: publish-cms-content\n              description: \"Publish a CMS content item.\"\n              call: \"exp-cloud-cms.publish-content\"\n              with:\n                contentId: \"rest.contentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: exp-cloud-site-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce Experience Cloud site management.\"\n      tools:\n        - name: list-experience-cloud-sites\n          description: \"List all Experience Cloud digital experience sites.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-sites.list-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-experience-cloud-site\n          description: \"Get a specific Experience\
  \ Cloud site by ID.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-sites.get-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-experience-cloud-site\n          description: \"Create a new Experience Cloud digital experience site.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-sites.create-site\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-experience-cloud-site\n          description: \"Publish an Experience Cloud site to make it publicly accessible.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-sites.publish-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            -\
  \ type: object\n              mapping: \"$.\"\n        - name: list-cms-channels\n          description: \"List all CMS delivery channels for content publishing.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-cms.list-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-cms-content\n          description: \"List CMS content items across channels.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"exp-cloud-cms.list-contents\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-cms-content\n          description: \"Create a new CMS content item in Salesforce Experience Cloud.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-cms.create-content\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: publish-cms-content\n          description: \"Publish a CMS content item to make it live on digital experiences.\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"exp-cloud-cms.publish-content\"\n          with:\n            contentId: \"tools.contentId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce-experience-cloud/refs/heads/main/capabilities/site-management.yaml
tags:
- CMS
- Communities
- Content Management
- Digital Experiences
- Publishing
- Salesforce Experience Cloud
- Sites
tools:
- description: List all Experience Cloud digital experience sites.
  hints:
    idempotent: true
    readOnly: true
  name: list-experience-cloud-sites
- description: Get a specific Experience Cloud site by ID.
  hints:
    idempotent: true
    readOnly: true
  name: get-experience-cloud-site
- description: Create a new Experience Cloud digital experience site.
  hints:
    destructive: false
    readOnly: false
  name: create-experience-cloud-site
- description: Publish an Experience Cloud site to make it publicly accessible.
  hints:
    destructive: false
    readOnly: false
  name: publish-experience-cloud-site
- description: List all CMS delivery channels for content publishing.
  hints:
    idempotent: true
    readOnly: true
  name: list-cms-channels
- description: List CMS content items across channels.
  hints:
    idempotent: true
    readOnly: true
  name: list-cms-content
- description: Create a new CMS content item in Salesforce Experience Cloud.
  hints:
    destructive: false
    readOnly: false
  name: create-cms-content
- description: Publish a CMS content item to make it live on digital experiences.
  hints:
    destructive: false
    readOnly: false
  name: publish-cms-content
---
