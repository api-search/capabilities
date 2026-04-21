---
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
- create site
- add user
- delete data source
- update a site
- sign in to tableau server or cloud
- get details of a specific site
- get data source
- list all sites
- data visualization
- analytics
- list data sources on a site
- get workbook
- get details of a specific data source
- single site operations
- sign out from tableau
- site management
- update site configuration
- data source operations
- dashboards
- delete a workbook
- list users on a site
- list sites
- delete a data source
- content management
- delete site
- get details of a specific workbook
- business intelligence
- list workbooks on a site
- user operations
- update site
- list users
- administration
- list workbooks
- delete workbook
- sign in
- list data sources
- get site details
- delete a site
- sign out
- create a new site
- get site
- list all sites on the server
- workbook operations
- tableau
- add a user to a site
slug: content-management
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
