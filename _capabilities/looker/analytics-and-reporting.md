---
consumed_apis:
- looker
description: Unified workflow for business intelligence analytics including dashboards, looks, queries, and user management. Used by data analysts and BI administrators.
layout: capability
name: Looker Analytics and Reporting
operations:
- description: List all looks.
  method: GET
  name: list-looks
  path: /v1/looks
- description: Get look details.
  method: GET
  name: get-look
  path: /v1/looks/{id}
- description: Update a look.
  method: PATCH
  name: update-look
  path: /v1/looks/{id}
- description: Delete a look.
  method: DELETE
  name: delete-look
  path: /v1/looks/{id}
- description: List all dashboards.
  method: GET
  name: list-dashboards
  path: /v1/dashboards
- description: Create a dashboard.
  method: POST
  name: create-dashboard
  path: /v1/dashboards
- description: Get dashboard details.
  method: GET
  name: get-dashboard
  path: /v1/dashboards/{id}
- description: Update a dashboard.
  method: PATCH
  name: update-dashboard
  path: /v1/dashboards/{id}
- description: Delete a dashboard.
  method: DELETE
  name: delete-dashboard
  path: /v1/dashboards/{id}
- description: Create a query.
  method: POST
  name: create-query
  path: /v1/queries
- description: Get query details.
  method: GET
  name: get-query
  path: /v1/queries/{id}
- description: List all users.
  method: GET
  name: list-users
  path: /v1/users
- description: Create a user.
  method: POST
  name: create-user
  path: /v1/users
personas: []
provider_name: Looker
provider_slug: looker
search_terms:
- get query details.
- delete user
- run a saved query.
- list all looks.
- create a new dashboard.
- bi platform
- list all dashboards.
- create a new user.
- get look
- delete a look.
- search for dashboards.
- look management.
- delete a dashboard.
- get query
- create dashboard
- create user
- update user
- create a dashboard.
- run a look and return results.
- get user
- delete dashboard
- update a user.
- delete look
- get user details.
- run look
- individual dashboard management.
- query management.
- data analytics
- list users
- user management.
- get look details.
- create query
- search looks
- update a dashboard.
- search for looks by title.
- update a look.
- list looks
- create a user.
- list all users.
- dashboard management.
- update dashboard
- list dashboards
- get dashboard details.
- search dashboards
- run query
- data visualization
- business intelligence
- individual look management.
- analytics
- delete a user.
- list all saved looks.
- get dashboard
- looker
- dashboards
- update look
- create a query.
- individual query operations.
slug: analytics-and-reporting
tags:
- Looker
- Business Intelligence
- Analytics
- Dashboards
tools:
- description: List all saved looks.
  hints:
    openWorld: true
    readOnly: true
  name: list-looks
- description: Search for looks by title.
  hints:
    readOnly: true
  name: search-looks
- description: Get look details.
  hints:
    readOnly: true
  name: get-look
- description: Update a look.
  hints:
    idempotent: true
    readOnly: false
  name: update-look
- description: Delete a look.
  hints:
    destructive: true
    idempotent: true
  name: delete-look
- description: Run a look and return results.
  hints:
    readOnly: true
  name: run-look
- description: List all dashboards.
  hints:
    openWorld: true
    readOnly: true
  name: list-dashboards
- description: Search for dashboards.
  hints:
    readOnly: true
  name: search-dashboards
- description: Create a new dashboard.
  hints:
    readOnly: false
  name: create-dashboard
- description: Get dashboard details.
  hints:
    readOnly: true
  name: get-dashboard
- description: Update a dashboard.
  hints:
    idempotent: true
    readOnly: false
  name: update-dashboard
- description: Delete a dashboard.
  hints:
    destructive: true
    idempotent: true
  name: delete-dashboard
- description: Create a query.
  hints:
    readOnly: false
  name: create-query
- description: Get query details.
  hints:
    readOnly: true
  name: get-query
- description: Run a saved query.
  hints:
    readOnly: true
  name: run-query
- description: List all users.
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Create a new user.
  hints:
    readOnly: false
  name: create-user
- description: Get user details.
  hints:
    readOnly: true
  name: get-user
- description: Update a user.
  hints:
    idempotent: true
    readOnly: false
  name: update-user
- description: Delete a user.
  hints:
    destructive: true
    idempotent: true
  name: delete-user
---
