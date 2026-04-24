---
consumed_apis:
- pluralsight-user-management
- pluralsight-teams
- pluralsight-licensing-rest
- pluralsight-plan-info
- pluralsight-flow-users
- pluralsight-flow-teams
- pluralsight-flow-integrations
- pluralsight-flow-repos
description: Unified workflow for platform administrators to manage users, teams, licensing, plan configuration, and Flow workspace settings. Combines user management, teams, licensing, plan info, Flow users, Flow teams, Flow integrations, and Flow repos APIs.
layout: capability
name: Pluralsight User And Team Administration
operations:
- description: Query and manage users via GraphQL
  method: POST
  name: manage-users
  path: /v1/users
- description: Query and manage teams via GraphQL
  method: POST
  name: manage-teams
  path: /v1/teams
- description: List pending user invitations
  method: GET
  name: list-invitations
  path: /v1/invitations
- description: Create a new user invitation
  method: POST
  name: create-invitation
  path: /v1/invitations
- description: List users in the plan
  method: GET
  name: list-license-users
  path: /v1/license-users
- description: List teams in the plan
  method: GET
  name: list-license-teams
  path: /v1/license-teams
- description: Retrieve account and plan details
  method: POST
  name: query-plan-info
  path: /v1/plan-info
- description: List Flow workspace users
  method: GET
  name: list-flow-users
  path: /v1/flow-users
- description: Update Flow user accounts
  method: PUT
  name: update-flow-users
  path: /v1/flow-users
- description: List Flow engineering teams
  method: GET
  name: list-flow-teams
  path: /v1/flow-teams
- description: List Flow integrations and connection status
  method: GET
  name: list-integrations
  path: /v1/integrations
- description: Retrieve repository data and metadata
  method: GET
  name: get-repos
  path: /v1/repositories
personas: []
provider_name: Pluralsight
provider_slug: pluralsight
search_terms:
- platform administration
- list flow workspace users
- list pending user invitations
- list flow users in the workspace.
- technology
- query and manage teams via graphql
- list flow users
- list invitations
- update flow users
- manage teams
- flow engineering team management
- flow workspace user management
- list pending user invitations. deprecated - migrate to graphql user management api.
- update flow user accounts
- education
- courses
- list license users
- query and manage users via graphql
- create invitation
- plan user listing (legacy rest, deprecated)
- retrieve repository data and metadata
- query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.
- manage users
- flow integration management and connection status
- list flow engineering teams and team membership data.
- retrieve repository data and metadata across connected source control systems.
- user management including listing, inviting, editing, and removing users
- team administration
- list teams in the plan
- list users in the plan. deprecated - migrate to graphql user management api.
- list teams in the plan. deprecated - migrate to graphql teams api.
- pluralsight
- retrieve account and plan details
- learning
- plan team listing (legacy rest, deprecated)
- get repos
- update, merge, hide, or perform bulk operations on flow user accounts.
- query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.
- create a new user invitation
- skills assessment
- user invitation management (legacy rest, deprecated)
- list flow engineering teams
- licensing
- team management including creating teams, managing membership, and permissions
- list flow teams
- send a new user invitation. deprecated - migrate to graphql user management api.
- engineering metrics
- retrieve account and plan details including subscription tier and configuration.
- list users in the plan
- account and plan details including subscription tier
- list license teams
- list flow integrations and connection status
- connected repository data and metadata
- query plan info
- list flow integrations and check connection status with external tools and services.
- video training
- list integrations
- user management
slug: user-and-team-administration
tags:
- Pluralsight
- User Management
- Team Administration
- Platform Administration
- Licensing
tools:
- description: Query and manage users including listing users, inviting members, editing user details, removing users, and canceling invitations.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-users
- description: Query and manage teams including creating teams, managing membership, assigning managers, and configuring team permissions.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: manage-teams
- description: List pending user invitations. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-invitations
- description: Send a new user invitation. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-invitation
- description: List users in the plan. Deprecated - migrate to GraphQL User Management API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-license-users
- description: List teams in the plan. Deprecated - migrate to GraphQL Teams API.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-license-teams
- description: Retrieve account and plan details including subscription tier and configuration.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-plan-info
- description: List Flow users in the workspace.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-flow-users
- description: Update, merge, hide, or perform bulk operations on Flow user accounts.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-flow-users
- description: List Flow engineering teams and team membership data.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-flow-teams
- description: List Flow integrations and check connection status with external tools and services.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-integrations
- description: Retrieve repository data and metadata across connected source control systems.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-repos
---
