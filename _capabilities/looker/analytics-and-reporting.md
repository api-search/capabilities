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
- bi platform
- create user
- get look
- update a user.
- business intelligence
- list all looks.
- list looks
- create dashboard
- list dashboards
- search dashboards
- get dashboard details.
- run a saved query.
- get user
- get look details.
- individual dashboard management.
- analytics
- search looks
- create a new dashboard.
- delete a dashboard.
- update a look.
- user management.
- run a look and return results.
- delete look
- look management.
- update user
- update dashboard
- update a dashboard.
- create a user.
- list all saved looks.
- get query details.
- delete dashboard
- run query
- run look
- search for dashboards.
- individual query operations.
- search for looks by title.
- create a new user.
- dashboard management.
- data analytics
- individual look management.
- query management.
- create query
- create a query.
- create a dashboard.
- delete a user.
- get dashboard
- list all users.
- get user details.
- dashboards
- update look
- get query
- data visualization
- delete a look.
- list all dashboards.
- delete user
- looker
- list users
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
