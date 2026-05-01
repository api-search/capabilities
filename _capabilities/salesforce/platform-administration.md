---
api_specs:
- filename: salesforce-openapi.yml
  format: yaml
  label: salesforce-platform
  slug: salesforce-platform
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/openapi/salesforce-openapi.yml
categories:
- identity-access
consumed_apis:
- salesforce-platform
- salesforce-rest
- salesforce-ui
description: Unified capability for Salesforce platform administration workflows combining the platform API and UI API for identity management, OAuth administration, metadata exploration, and application configuration. Used by Salesforce admins and platform engineers.
layout: capability
name: Salesforce Platform Administration
operations:
- description: Get the authenticated user's profile information.
  method: GET
  name: get-user-info
  path: /v1/user-info
- description: List available Salesforce REST API versions.
  method: GET
  name: list-api-versions
  path: /v1/api-versions
- description: Get current API limit usage and quotas.
  method: GET
  name: get-org-limits
  path: /v1/limits
- description: Get the app switcher menu items.
  method: GET
  name: get-app-switcher-menu
  path: /v1/app-menu
- description: List all SObject types in the org.
  method: GET
  name: list-sobjects
  path: /v1/sobjects
- description: Get full metadata for an SObject type.
  method: GET
  name: full-describe-sobject
  path: /v1/sobjects/{sobjectType}/describe
- description: Get UI-ready metadata for an object.
  method: GET
  name: get-object-info
  path: /v1/object-info/{objectApiName}
- description: Get picklist values for all picklist fields on an object.
  method: GET
  name: get-picklist-values
  path: /v1/picklist-values/{objectApiName}/{recordTypeId}
personas: []
provider_name: Salesforce
provider_slug: salesforce
search_terms:
- get lookup records
- commerce
- crm
- ui-ready object metadata.
- marketing
- customer service
- get the app switcher menu items available to the current user.
- list sobjects
- salesforce api version information.
- full sobject metadata.
- full describe sobject
- list all sobject types available in the salesforce org.
- platform administration
- search lookup field records for typeahead.
- analytics
- platform
- list api versions
- identity
- picklist value retrieval.
- get list views
- get current api limit usage and quotas.
- get picklist values
- app switcher menu items.
- enterprise
- get user info
- get app switcher menu
- list available salesforce rest api versions.
- list all sobject types in the org.
- get picklist values for all picklist fields on an object.
- get full metadata for a salesforce sobject type including all fields.
- ai
- get object info
- get the authenticated user's profile information.
- get ui-ready metadata about a salesforce object.
- get org limits
- salesforce
- oauth
- org api limits.
- get ui-ready metadata for an object.
- get current api limit usage and remaining quotas for the org.
- sales
- metadata
- get full metadata for an sobject type.
- cloud
- authenticated user information.
- sobject type listing.
- get picklist values for all picklist fields on an object for a given record type.
- get the app switcher menu items.
- get list views for a salesforce object.
slug: platform-administration
source_filename: platform-administration.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Salesforce Platform Administration\"\n  description: \"Unified capability for Salesforce platform administration workflows combining the platform API and UI API for identity management, OAuth administration, metadata exploration, and application configuration. Used by Salesforce admins and platform engineers.\"\n  tags:\n    - Salesforce\n    - Platform Administration\n    - Identity\n    - OAuth\n    - Metadata\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      SALESFORCE_ACCESS_TOKEN: SALESFORCE_ACCESS_TOKEN\n      SALESFORCE_CLIENT_ID: SALESFORCE_CLIENT_ID\n      SALESFORCE_CLIENT_SECRET: SALESFORCE_CLIENT_SECRET\n\ncapability:\n  consumes:\n    - import: salesforce-platform\n      location: ./shared/salesforce.yaml\n    - import: salesforce-rest\n      location: ./shared/rest-api.yaml\n    - import: salesforce-ui\n      location: ./shared/ui-api.yaml\n\n  exposes:\n    - type:\
  \ rest\n      port: 8082\n      namespace: platform-administration-api\n      description: \"Unified REST API for Salesforce platform administration.\"\n      resources:\n        - path: /v1/user-info\n          name: user-info\n          description: \"Authenticated user information.\"\n          operations:\n            - method: GET\n              name: get-user-info\n              description: \"Get the authenticated user's profile information.\"\n              call: \"salesforce-platform.get-user-info\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/api-versions\n          name: api-versions\n          description: \"Salesforce API version information.\"\n          operations:\n            - method: GET\n              name: list-api-versions\n              description: \"List available Salesforce REST API versions.\"\n              call: \"salesforce-rest.list-api-versions\"\n              outputParameters:\n\
  \                - type: object\n                  mapping: \"$.\"\n        - path: /v1/limits\n          name: limits\n          description: \"Org API limits.\"\n          operations:\n            - method: GET\n              name: get-org-limits\n              description: \"Get current API limit usage and quotas.\"\n              call: \"salesforce-rest.get-org-limits\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/app-menu\n          name: app-menu\n          description: \"App switcher menu items.\"\n          operations:\n            - method: GET\n              name: get-app-switcher-menu\n              description: \"Get the app switcher menu items.\"\n              call: \"salesforce-rest.get-app-switcher-menu\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sobjects\n          name: sobjects\n          description: \"SObject type\
  \ listing.\"\n          operations:\n            - method: GET\n              name: list-sobjects\n              description: \"List all SObject types in the org.\"\n              call: \"salesforce-rest.list-sobjects\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/sobjects/{sobjectType}/describe\n          name: sobject-describe\n          description: \"Full SObject metadata.\"\n          operations:\n            - method: GET\n              name: full-describe-sobject\n              description: \"Get full metadata for an SObject type.\"\n              call: \"salesforce-rest.full-describe-sobject\"\n              with:\n                sobjectType: \"rest.sobjectType\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/object-info/{objectApiName}\n          name: object-info\n          description: \"UI-ready object metadata.\"\n         \
  \ operations:\n            - method: GET\n              name: get-object-info\n              description: \"Get UI-ready metadata for an object.\"\n              call: \"salesforce-ui.get-object-info\"\n              with:\n                objectApiName: \"rest.objectApiName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/picklist-values/{objectApiName}/{recordTypeId}\n          name: picklist-values\n          description: \"Picklist value retrieval.\"\n          operations:\n            - method: GET\n              name: get-picklist-values\n              description: \"Get picklist values for all picklist fields on an object.\"\n              call: \"salesforce-ui.get-picklist-values\"\n              with:\n                objectApiName: \"rest.objectApiName\"\n                recordTypeId: \"rest.recordTypeId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n\n    - type: mcp\n      port: 9092\n      namespace: platform-administration-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Salesforce platform administration.\"\n      tools:\n        - name: get-user-info\n          description: \"Get the authenticated user's profile information.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-platform.get-user-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-api-versions\n          description: \"List available Salesforce REST API versions.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.list-api-versions\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-org-limits\n          description: \"Get current API limit usage and remaining quotas for the org.\"\n          hints:\n\
  \            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-org-limits\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-app-switcher-menu\n          description: \"Get the app switcher menu items available to the current user.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.get-app-switcher-menu\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sobjects\n          description: \"List all SObject types available in the Salesforce org.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.list-sobjects\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: full-describe-sobject\n          description: \"Get full metadata for a Salesforce SObject type including\
  \ all fields.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-rest.full-describe-sobject\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-object-info\n          description: \"Get UI-ready metadata about a Salesforce object.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-object-info\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-picklist-values\n          description: \"Get picklist values for all picklist fields on an object for a given record type.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-picklist-values\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-list-views\n          description: \"Get list views\
  \ for a Salesforce object.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-lists-by-object\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-lookup-records\n          description: \"Search lookup field records for typeahead.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"salesforce-ui.get-lookup-records\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/salesforce/refs/heads/main/capabilities/platform-administration.yaml
tags:
- Salesforce
- Platform Administration
- Identity
- OAuth
- Metadata
tools:
- description: Get the authenticated user's profile information.
  hints:
    idempotent: true
    readOnly: true
  name: get-user-info
- description: List available Salesforce REST API versions.
  hints:
    idempotent: true
    readOnly: true
  name: list-api-versions
- description: Get current API limit usage and remaining quotas for the org.
  hints:
    idempotent: true
    readOnly: true
  name: get-org-limits
- description: Get the app switcher menu items available to the current user.
  hints:
    idempotent: true
    readOnly: true
  name: get-app-switcher-menu
- description: List all SObject types available in the Salesforce org.
  hints:
    idempotent: true
    readOnly: true
  name: list-sobjects
- description: Get full metadata for a Salesforce SObject type including all fields.
  hints:
    idempotent: true
    readOnly: true
  name: full-describe-sobject
- description: Get UI-ready metadata about a Salesforce object.
  hints:
    idempotent: true
    readOnly: true
  name: get-object-info
- description: Get picklist values for all picklist fields on an object for a given record type.
  hints:
    idempotent: true
    readOnly: true
  name: get-picklist-values
- description: Get list views for a Salesforce object.
  hints:
    idempotent: true
    readOnly: true
  name: get-list-views
- description: Search lookup field records for typeahead.
  hints:
    idempotent: true
    readOnly: true
  name: get-lookup-records
---
