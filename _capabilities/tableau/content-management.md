---
categories:
- content-management
consumed_apis:
- tableau-rest
description: Workflow for managing Tableau content including workbooks, data sources, views, sites, users, and permissions. Used by Tableau administrators and content managers.
layout: capability
name: Tableau Content Management
operations:
- description: List all sites
  method: GET
  name: list-sites
  path: /v1/sites
- description: Create a new site
  method: POST
  name: create-site
  path: /v1/sites
- description: Get site details
  method: GET
  name: get-site
  path: /v1/sites/{siteId}
- description: Update a site
  method: PUT
  name: update-site
  path: /v1/sites/{siteId}
- description: Delete a site
  method: DELETE
  name: delete-site
  path: /v1/sites/{siteId}
- description: List workbooks on a site
  method: GET
  name: list-workbooks
  path: /v1/workbooks
- description: List data sources on a site
  method: GET
  name: list-data-sources
  path: /v1/data-sources
- description: List users on a site
  method: GET
  name: list-users
  path: /v1/users
personas: []
provider_name: Tableau
provider_slug: tableau
search_terms:
- administration
- list all sites
- analytics
- content management
- create a new site
- sign out from tableau
- sign out
- data visualization
- delete a data source
- get details of a specific data source
- update site
- list workbooks
- dashboards
- get site details
- site management
- delete site
- create site
- user operations
- get details of a specific workbook
- list data sources
- add a user to a site
- delete a site
- delete a workbook
- tableau
- workbook operations
- get workbook
- get data source
- get site
- update site configuration
- update a site
- delete workbook
- list sites
- delete data source
- list users on a site
- list workbooks on a site
- data source operations
- add user
- single site operations
- business intelligence
- list data sources on a site
- get details of a specific site
- sign in
- list all sites on the server
- list users
- sign in to tableau server or cloud
slug: content-management
source_filename: content-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Tableau Content Management\"\n  description: \"Workflow for managing Tableau content including workbooks, data sources, views, sites, users, and permissions. Used by Tableau administrators and content managers.\"\n  tags:\n    - Tableau\n    - Content Management\n    - Analytics\n    - Administration\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      TABLEAU_AUTH_TOKEN: TABLEAU_AUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: tableau-rest\n      location: ./shared/tableau-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: tableau-content-api\n      description: \"Unified REST API for Tableau content management.\"\n      resources:\n        - path: /v1/sites\n          name: sites\n          description: \"Site management\"\n          operations:\n            - method: GET\n              name: list-sites\n              description: \"List all sites\"\
  \n              call: \"tableau-rest.query-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-site\n              description: \"Create a new site\"\n              call: \"tableau-rest.create-site\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sites/{siteId}\n          name: site\n          description: \"Single site operations\"\n          operations:\n            - method: GET\n              name: get-site\n              description: \"Get site details\"\n              call: \"tableau-rest.query-site\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-site\n              description: \"Update a site\"\n              call: \"tableau-rest.update-site\"\
  \n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-site\n              description: \"Delete a site\"\n              call: \"tableau-rest.delete-site\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/workbooks\n          name: workbooks\n          description: \"Workbook operations\"\n          operations:\n            - method: GET\n              name: list-workbooks\n              description: \"List workbooks on a site\"\n              call: \"tableau-rest.query-workbooks\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/data-sources\n          name:\
  \ data-sources\n          description: \"Data source operations\"\n          operations:\n            - method: GET\n              name: list-data-sources\n              description: \"List data sources on a site\"\n              call: \"tableau-rest.query-data-sources\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/users\n          name: users\n          description: \"User operations\"\n          operations:\n            - method: GET\n              name: list-users\n              description: \"List users on a site\"\n              call: \"tableau-rest.get-users\"\n              with:\n                siteId: \"rest.siteId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: tableau-content-mcp\n      transport: http\n      description: \"MCP server\
  \ for AI-assisted Tableau content management.\"\n      tools:\n        - name: sign-in\n          description: \"Sign in to Tableau Server or Cloud\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tableau-rest.sign-in\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: sign-out\n          description: \"Sign out from Tableau\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tableau-rest.sign-out\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sites\n          description: \"List all sites on the server\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.query-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-site\n          description: \"Create a\
  \ new site\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tableau-rest.create-site\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-site\n          description: \"Get details of a specific site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.query-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-site\n          description: \"Update site configuration\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"tableau-rest.update-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-site\n          description: \"Delete a site\"\n    \
  \      hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tableau-rest.delete-site\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-workbooks\n          description: \"List workbooks on a site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.query-workbooks\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-workbook\n          description: \"Get details of a specific workbook\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.query-workbook\"\n          with:\n            siteId: \"tools.siteId\"\n            workbookId: \"tools.workbookId\"\n          outputParameters:\n   \
  \         - type: object\n              mapping: \"$.\"\n        - name: delete-workbook\n          description: \"Delete a workbook\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tableau-rest.delete-workbook\"\n          with:\n            siteId: \"tools.siteId\"\n            workbookId: \"tools.workbookId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-data-sources\n          description: \"List data sources on a site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.query-data-sources\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-data-source\n          description: \"Get details of a specific data source\"\n          hints:\n            readOnly: true\n        \
  \    idempotent: true\n          call: \"tableau-rest.query-data-source\"\n          with:\n            siteId: \"tools.siteId\"\n            datasourceId: \"tools.datasourceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-data-source\n          description: \"Delete a data source\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"tableau-rest.delete-data-source\"\n          with:\n            siteId: \"tools.siteId\"\n            datasourceId: \"tools.datasourceId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-users\n          description: \"List users on a site\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"tableau-rest.get-users\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n           \
  \ - type: object\n              mapping: \"$.\"\n        - name: add-user\n          description: \"Add a user to a site\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"tableau-rest.add-user\"\n          with:\n            siteId: \"tools.siteId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tableau/refs/heads/main/capabilities/content-management.yaml
tags:
- Tableau
- Content Management
- Analytics
- Administration
tools:
- description: Sign in to Tableau Server or Cloud
  hints:
    idempotent: false
    readOnly: false
  name: sign-in
- description: Sign out from Tableau
  hints:
    idempotent: true
    readOnly: false
  name: sign-out
- description: List all sites on the server
  hints:
    idempotent: true
    readOnly: true
  name: list-sites
- description: Create a new site
  hints:
    idempotent: false
    readOnly: false
  name: create-site
- description: Get details of a specific site
  hints:
    idempotent: true
    readOnly: true
  name: get-site
- description: Update site configuration
  hints:
    idempotent: true
    readOnly: false
  name: update-site
- description: Delete a site
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-site
- description: List workbooks on a site
  hints:
    idempotent: true
    readOnly: true
  name: list-workbooks
- description: Get details of a specific workbook
  hints:
    idempotent: true
    readOnly: true
  name: get-workbook
- description: Delete a workbook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-workbook
- description: List data sources on a site
  hints:
    idempotent: true
    readOnly: true
  name: list-data-sources
- description: Get details of a specific data source
  hints:
    idempotent: true
    readOnly: true
  name: get-data-source
- description: Delete a data source
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-data-source
- description: List users on a site
  hints:
    idempotent: true
    readOnly: true
  name: list-users
- description: Add a user to a site
  hints:
    idempotent: false
    readOnly: false
  name: add-user
---
