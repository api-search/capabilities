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
- deleteTeam
- createTeam
- list organization packages
- list org packages
- deleteAnInstallationForTheAuthenticatedApp
- installation access tokens
- get an organization
- list organization webhooks
- delete an organization package
- add or update team membership
- list team repositories
- listOrganizationRepositories
- unsuspend an app installation
- create org repo
- getTeamByName
- individual installation
- listOrganizationMembers
- authenticated app
- listPackagesForAnOrganization
- get org package
- t1
- create team
- github
- list installations
- apps
- list org package versions
- get an app by slug
- delete an installation
- list team members
- listTeams
- set membership
- unsuspend installation
- add team member
- organizations
- update webhook config
- updateTeam
- get a team
- delete team
- delete org package
- organization webhooks
- create an installation access token
- organization management
- get installation
- get app webhook configuration
- source control
- update organization
- get the authenticated app
- update app webhook configuration
- list packages
- list organization package versions
- organization packages
- getAnInstallationForTheAuthenticatedApp
- platform
- listInstallationsForTheAuthenticatedApp
- list org repos
- create a team
- get webhook config
- individual team operations
- software development
- get an app installation
- list organization repositories
- list app installations
- suspend an app installation
- app installations
- set organization membership
- create an organization repository
- list team repos
- remove an organization member
- listOrganizationWebhooks
- suspend installation
- create an access token
- code
- update an organization
- platform administration
- packages
- get authenticated app
- add team repo
- list installation repos
- get app
- delete a team
- create an organization webhook
- list repositories
- team management
- getTheAuthenticatedApp
- add or update team repository permissions
- get organization
- get an organization package
- update a team
- organization repositories
- list members
- teams
- list teams
- member management
- create installation token
- updateAnOrganization
- get team
- update team
- get an installation
- createAnInstallationAccessTokenForAnApp
- list repositories accessible to the installation
- list webhooks
- list organization members
- getAnOrganization
- pipelines
- remove member
- create webhook
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
