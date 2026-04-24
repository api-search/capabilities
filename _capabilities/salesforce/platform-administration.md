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
- platform administration
- ai
- get list views for a salesforce object.
- ui-ready object metadata.
- picklist value retrieval.
- list available salesforce rest api versions.
- marketing
- commerce
- full sobject metadata.
- customer service
- get current api limit usage and remaining quotas for the org.
- list api versions
- list sobjects
- salesforce
- cloud
- analytics
- get the app switcher menu items.
- get full metadata for a salesforce sobject type including all fields.
- sobject type listing.
- get ui-ready metadata about a salesforce object.
- salesforce api version information.
- get current api limit usage and quotas.
- full describe sobject
- get object info
- get the authenticated user's profile information.
- oauth
- get picklist values for all picklist fields on an object for a given record type.
- list all sobject types in the org.
- get picklist values
- get app switcher menu
- search lookup field records for typeahead.
- get org limits
- get lookup records
- crm
- app switcher menu items.
- get full metadata for an sobject type.
- get user info
- get the app switcher menu items available to the current user.
- enterprise
- metadata
- sales
- get ui-ready metadata for an object.
- org api limits.
- authenticated user information.
- identity
- get picklist values for all picklist fields on an object.
- platform
- list all sobject types available in the salesforce org.
- get list views
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
