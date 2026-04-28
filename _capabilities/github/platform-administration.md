---
categories: []
consumed_apis:
- github-apps
- github-orgs
- github-packages
description: Unified workflow for platform administration combining GitHub Apps, organizations, teams, and packages. Used by platform administrators for managing app integrations, organization governance, team access control, and package registry operations.
layout: capability
name: GitHub Platform Administration
operations:
- description: Get the authenticated app
  method: GET
  name: getTheAuthenticatedApp
  path: /v1/app
- description: List installations
  method: GET
  name: listInstallationsForTheAuthenticatedApp
  path: /v1/app/installations
- description: Get an installation
  method: GET
  name: getAnInstallationForTheAuthenticatedApp
  path: /v1/app/installations/{installation_id}
- description: Delete an installation
  method: DELETE
  name: deleteAnInstallationForTheAuthenticatedApp
  path: /v1/app/installations/{installation_id}
- description: Create an access token
  method: POST
  name: createAnInstallationAccessTokenForAnApp
  path: /v1/app/installations/{installation_id}/access-tokens
- description: Get an organization
  method: GET
  name: getAnOrganization
  path: /v1/organizations/{org}
- description: Update an organization
  method: PATCH
  name: updateAnOrganization
  path: /v1/organizations/{org}
- description: List members
  method: GET
  name: listOrganizationMembers
  path: /v1/organizations/{org}/members
- description: List teams
  method: GET
  name: listTeams
  path: /v1/organizations/{org}/teams
- description: Create a team
  method: POST
  name: createTeam
  path: /v1/organizations/{org}/teams
- description: Get a team
  method: GET
  name: getTeamByName
  path: /v1/organizations/{org}/teams/{team_slug}
- description: Update a team
  method: PATCH
  name: updateTeam
  path: /v1/organizations/{org}/teams/{team_slug}
- description: Delete a team
  method: DELETE
  name: deleteTeam
  path: /v1/organizations/{org}/teams/{team_slug}
- description: List packages
  method: GET
  name: listPackagesForAnOrganization
  path: /v1/organizations/{org}/packages
- description: List webhooks
  method: GET
  name: listOrganizationWebhooks
  path: /v1/organizations/{org}/webhooks
- description: List repositories
  method: GET
  name: listOrganizationRepositories
  path: /v1/organizations/{org}/repos
personas: []
provider_name: GitHub
provider_slug: github
search_terms:
- organization management
- listPackagesForAnOrganization
- list webhooks
- packages
- list teams
- delete an installation
- unsuspend installation
- update team
- get an app installation
- list organization packages
- platform
- getTheAuthenticatedApp
- list org package versions
- list members
- create an organization webhook
- get authenticated app
- code
- get team
- member management
- create webhook
- listOrganizationRepositories
- suspend installation
- set organization membership
- remove member
- delete team
- installation access tokens
- list repositories
- listOrganizationWebhooks
- createTeam
- get installation
- updateTeam
- add team repo
- list organization webhooks
- get an organization
- update app webhook configuration
- list organization members
- list organization package versions
- update organization
- delete an organization package
- add team member
- add or update team membership
- getAnInstallationForTheAuthenticatedApp
- get organization
- create an access token
- list team repositories
- get an app by slug
- create team
- authenticated app
- get webhook config
- get an installation
- list org repos
- individual installation
- get app
- create org repo
- github
- organization repositories
- listInstallationsForTheAuthenticatedApp
- unsuspend an app installation
- list app installations
- add or update team repository permissions
- apps
- get an organization package
- list team members
- delete org package
- delete a team
- update an organization
- create a team
- t1
- getAnOrganization
- get org package
- update a team
- software development
- create an installation access token
- list team repos
- teams
- create an organization repository
- getTeamByName
- listOrganizationMembers
- team management
- list installation repos
- listTeams
- pipelines
- app installations
- suspend an app installation
- remove an organization member
- update webhook config
- list organization repositories
- list repositories accessible to the installation
- organization webhooks
- deleteAnInstallationForTheAuthenticatedApp
- organizations
- get the authenticated app
- deleteTeam
- list org packages
- updateAnOrganization
- get a team
- organization packages
- list installations
- list packages
- set membership
- createAnInstallationAccessTokenForAnApp
- create installation token
- source control
- individual team operations
- platform administration
- get app webhook configuration
slug: platform-administration
tags:
- GitHub
- Platform Administration
- Apps
- Organizations
- Teams
- Packages
tools:
- description: Get the authenticated app
  hints:
    readOnly: true
  name: get-authenticated-app
- description: Get an app by slug
  hints:
    readOnly: true
  name: get-app
- description: List app installations
  hints:
    readOnly: true
  name: list-installations
- description: Get an app installation
  hints:
    readOnly: true
  name: get-installation
- description: Create an installation access token
  hints: {}
  name: create-installation-token
- description: Suspend an app installation
  hints: {}
  name: suspend-installation
- description: Unsuspend an app installation
  hints: {}
  name: unsuspend-installation
- description: List repositories accessible to the installation
  hints:
    readOnly: true
  name: list-installation-repos
- description: Get app webhook configuration
  hints:
    readOnly: true
  name: get-webhook-config
- description: Update app webhook configuration
  hints:
    idempotent: true
  name: update-webhook-config
- description: Get an organization
  hints:
    readOnly: true
  name: get-organization
- description: Update an organization
  hints:
    idempotent: true
  name: update-organization
- description: List organization members
  hints:
    readOnly: true
  name: list-members
- description: Set organization membership
  hints:
    idempotent: true
  name: set-membership
- description: Remove an organization member
  hints:
    destructive: true
  name: remove-member
- description: List teams
  hints:
    readOnly: true
  name: list-teams
- description: Create a team
  hints: {}
  name: create-team
- description: Get a team
  hints:
    readOnly: true
  name: get-team
- description: Update a team
  hints:
    idempotent: true
  name: update-team
- description: Delete a team
  hints:
    destructive: true
  name: delete-team
- description: List team members
  hints:
    readOnly: true
  name: list-team-members
- description: Add or update team membership
  hints:
    idempotent: true
  name: add-team-member
- description: List team repositories
  hints:
    readOnly: true
  name: list-team-repos
- description: Add or update team repository permissions
  hints:
    idempotent: true
  name: add-team-repo
- description: List organization packages
  hints:
    readOnly: true
  name: list-org-packages
- description: Get an organization package
  hints:
    readOnly: true
  name: get-org-package
- description: Delete an organization package
  hints:
    destructive: true
  name: delete-org-package
- description: List organization package versions
  hints:
    readOnly: true
  name: list-org-package-versions
- description: List organization repositories
  hints:
    readOnly: true
  name: list-org-repos
- description: Create an organization repository
  hints: {}
  name: create-org-repo
- description: List organization webhooks
  hints:
    readOnly: true
  name: list-webhooks
- description: Create an organization webhook
  hints: {}
  name: create-webhook
---
