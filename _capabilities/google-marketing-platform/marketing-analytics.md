---
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
- platform administration
- list analytics links
- marketing
- set property service level
- organization management.
- analytics
- delete an analytics account link.
- create analytics link
- list organizations
- delete analytics link
- google marketing platform
- create an analytics account link.
- list analytics account links for an organization.
- organization management
- list marketing platform organizations.
- set analytics property service level (standard or 360).
- analytics account link management.
- individual analytics link management.
- list google marketing platform organizations.
- list analytics account links.
slug: marketing-analytics
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
