---
categories:
- analytics
consumed_apis:
- gmp-admin
description: Unified workflow for managing Google Marketing Platform organizations and their Analytics account integrations including service level configuration. Used by marketing platform administrators and analytics managers.
layout: capability
name: Google Marketing Platform Analytics Administration
operations:
- description: List Marketing Platform organizations.
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List analytics account links.
  method: GET
  name: list-analytics-links
  path: /v1/organizations/{id}/analytics-links
- description: Create an analytics account link.
  method: POST
  name: create-analytics-link
  path: /v1/organizations/{id}/analytics-links
- description: Delete an analytics account link.
  method: DELETE
  name: delete-analytics-link
  path: /v1/analytics-links/{id}
personas: []
provider_name: Google Marketing Platform Admin
provider_slug: google-marketing-platform
search_terms:
- organization management
- list analytics links
- analytics
- list google marketing platform organizations.
- analytics account link management.
- create an analytics account link.
- create analytics link
- organization management.
- platform administration
- delete analytics link
- delete an analytics account link.
- list organizations
- set property service level
- list marketing platform organizations.
- marketing
- list analytics account links.
- google marketing platform
- list analytics account links for an organization.
- individual analytics link management.
- set analytics property service level (standard or 360).
slug: marketing-analytics
source_filename: marketing-analytics.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Marketing Platform Analytics Administration\"\n  description: \"Unified workflow for managing Google Marketing Platform organizations and their Analytics account integrations including service level configuration. Used by marketing platform administrators and analytics managers.\"\n  tags:\n    - Google Marketing Platform\n    - Analytics\n    - Platform Administration\n    - Organization Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GMP_ACCESS_TOKEN: GMP_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: gmp-admin\n      location: ./shared/admin-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: gmp-analytics-admin-api\n      description: \"Unified REST API for Google Marketing Platform analytics administration.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"\
  Organization management.\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List Marketing Platform organizations.\"\n              call: \"gmp-admin.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{id}/analytics-links\n          name: analytics-links\n          description: \"Analytics account link management.\"\n          operations:\n            - method: GET\n              name: list-analytics-links\n              description: \"List analytics account links.\"\n              call: \"gmp-admin.list-analytics-links\"\n              with:\n                parent: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-analytics-link\n              description: \"Create an analytics account link.\"\n\
  \              call: \"gmp-admin.create-analytics-link\"\n              with:\n                parent: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analytics-links/{id}\n          name: analytics-link-details\n          description: \"Individual analytics link management.\"\n          operations:\n            - method: DELETE\n              name: delete-analytics-link\n              description: \"Delete an analytics account link.\"\n              call: \"gmp-admin.delete-analytics-link\"\n              with:\n                name: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9080\n      namespace: gmp-analytics-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Marketing Platform analytics administration.\"\n      tools:\n        - name: list-organizations\n     \
  \     description: \"List Google Marketing Platform organizations.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"gmp-admin.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analytics-links\n          description: \"List analytics account links for an organization.\"\n          hints:\n            readOnly: true\n          call: \"gmp-admin.list-analytics-links\"\n          with:\n            parent: \"tools.organizationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-analytics-link\n          description: \"Create an analytics account link.\"\n          hints:\n            readOnly: false\n          call: \"gmp-admin.create-analytics-link\"\n          with:\n            parent: \"tools.organizationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\
  \        - name: delete-analytics-link\n          description: \"Delete an analytics account link.\"\n          hints:\n            destructive: true\n            idempotent: true\n          call: \"gmp-admin.delete-analytics-link\"\n          with:\n            name: \"tools.linkName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-property-service-level\n          description: \"Set Analytics property service level (Standard or 360).\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"gmp-admin.set-property-service-level\"\n          with:\n            analyticsAccountLink: \"tools.analyticsAccountLink\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-marketing-platform/refs/heads/main/capabilities/marketing-analytics.yaml
tags:
- Google Marketing Platform
- Analytics
- Platform Administration
- Organization Management
tools:
- description: List Google Marketing Platform organizations.
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: List analytics account links for an organization.
  hints:
    readOnly: true
  name: list-analytics-links
- description: Create an analytics account link.
  hints:
    readOnly: false
  name: create-analytics-link
- description: Delete an analytics account link.
  hints:
    destructive: true
    idempotent: true
  name: delete-analytics-link
- description: Set Analytics property service level (Standard or 360).
  hints:
    idempotent: true
    readOnly: false
  name: set-property-service-level
---
