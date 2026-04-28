---
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
- oauth
- get current api limit usage and remaining quotas for the org.
- get full metadata for a salesforce sobject type including all fields.
- picklist value retrieval.
- get picklist values
- get the app switcher menu items available to the current user.
- get list views
- list available salesforce rest api versions.
- org api limits.
- search lookup field records for typeahead.
- get full metadata for an sobject type.
- get picklist values for all picklist fields on an object.
- get current api limit usage and quotas.
- get object info
- list all sobject types in the org.
- app switcher menu items.
- analytics
- platform
- cloud
- get the app switcher menu items.
- get ui-ready metadata about a salesforce object.
- list sobjects
- enterprise
- get list views for a salesforce object.
- commerce
- marketing
- get picklist values for all picklist fields on an object for a given record type.
- identity
- get org limits
- get ui-ready metadata for an object.
- ai
- ui-ready object metadata.
- list api versions
- metadata
- full describe sobject
- get user info
- get app switcher menu
- list all sobject types available in the salesforce org.
- full sobject metadata.
- sales
- salesforce
- get lookup records
- crm
- authenticated user information.
- salesforce api version information.
- customer service
- sobject type listing.
- platform administration
- get the authenticated user's profile information.
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
