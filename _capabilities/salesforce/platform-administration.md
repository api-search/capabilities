---
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
- get current api limit usage and remaining quotas for the org.
- get ui-ready metadata for an object.
- customer service
- get ui-ready metadata about a salesforce object.
- get current api limit usage and quotas.
- get org limits
- get lookup records
- get list views
- oauth
- search lookup field records for typeahead.
- list all sobject types available in the salesforce org.
- analytics
- get picklist values
- ai
- enterprise
- list sobjects
- get full metadata for an sobject type.
- full describe sobject
- salesforce api version information.
- get the authenticated user's profile information.
- get list views for a salesforce object.
- authenticated user information.
- org api limits.
- get app switcher menu
- sobject type listing.
- platform
- app switcher menu items.
- get picklist values for all picklist fields on an object for a given record type.
- platform administration
- get picklist values for all picklist fields on an object.
- identity
- commerce
- get full metadata for a salesforce sobject type including all fields.
- picklist value retrieval.
- get object info
- crm
- full sobject metadata.
- metadata
- list available salesforce rest api versions.
- cloud
- list api versions
- sales
- salesforce
- ui-ready object metadata.
- get user info
- get the app switcher menu items.
- list all sobject types in the org.
- get the app switcher menu items available to the current user.
- marketing
slug: platform-administration
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
