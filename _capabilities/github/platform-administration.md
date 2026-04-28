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
- list repositories accessible to the installation
- update a team
- authenticated app
- get installation
- organization management
- create org repo
- list team repos
- suspend an app installation
- source control
- listInstallationsForTheAuthenticatedApp
- list org packages
- createAnInstallationAccessTokenForAnApp
- list organization members
- t1
- getAnOrganization
- set membership
- createTeam
- get the authenticated app
- delete an organization package
- get an organization package
- delete team
- list app installations
- list packages
- list org package versions
- list teams
- get an app by slug
- updateTeam
- team management
- create installation token
- remove member
- suspend installation
- update team
- list organization webhooks
- get authenticated app
- create an access token
- list team repositories
- get webhook config
- get an app installation
- list installation repos
- organizations
- app installations
- list webhooks
- update app webhook configuration
- platform administration
- getTheAuthenticatedApp
- teams
- code
- list organization packages
- platform
- list installations
- list team members
- create team
- member management
- create an installation access token
- software development
- remove an organization member
- getAnInstallationForTheAuthenticatedApp
- github
- list org repos
- list repositories
- add or update team repository permissions
- list members
- delete org package
- get app webhook configuration
- listPackagesForAnOrganization
- create an organization repository
- pipelines
- create webhook
- delete an installation
- set organization membership
- get a team
- delete a team
- unsuspend installation
- listOrganizationWebhooks
- list organization package versions
- get org package
- unsuspend an app installation
- getTeamByName
- organization webhooks
- add team repo
- get team
- create a team
- packages
- individual installation
- update an organization
- get app
- update organization
- updateAnOrganization
- add or update team membership
- organization repositories
- add team member
- listOrganizationMembers
- get an installation
- installation access tokens
- apps
- list organization repositories
- get an organization
- listTeams
- create an organization webhook
- organization packages
- individual team operations
- listOrganizationRepositories
- update webhook config
- get organization
- deleteAnInstallationForTheAuthenticatedApp
slug: platform-administration
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"GitHub Platform Administration\"\n  description: \"Unified workflow for platform administration combining GitHub Apps, organizations, teams, and packages. Used by platform administrators for managing app integrations, organization governance, team access control, and package registry operations.\"\n  tags:\n    - GitHub\n    - Platform Administration\n    - Apps\n    - Organizations\n    - Teams\n    - Packages\n  personas:\n    - platform administrators\n    - IT administrators\n    - github org owners\n  created: \"2026-04-17\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GITHUB_TOKEN: GITHUB_TOKEN\n\ncapability:\n  consumes:\n    - import: github-apps\n      location: \"./shared/apps.yaml\"\n    - import: github-orgs\n      location: \"./shared/orgs.yaml\"\n    - import: github-packages\n      location: \"./shared/packages.yaml\"\n\n  exposes:\n    - type: rest\n      port: 8085\n      namespace:\
  \ github-platform-admin-api\n      description: \"Unified REST API for platform administration combining apps, organizations, teams, and packages.\"\n      resources:\n        - path: /v1/app\n          name: app\n          description: \"Authenticated app\"\n          operations:\n            - method: GET\n              name: getTheAuthenticatedApp\n              description: \"Get the authenticated app\"\n              call: \"github-apps.getTheAuthenticatedApp\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/app/installations\n          name: installations\n          description: \"App installations\"\n          operations:\n            - method: GET\n              name: listInstallationsForTheAuthenticatedApp\n              description: \"List installations\"\n              call: \"github-apps.listInstallationsForTheAuthenticatedApp\"\n              outputParameters:\n                - type: object\n       \
  \           mapping: \"$.\"\n        - path: /v1/app/installations/{installation_id}\n          name: installation\n          description: \"Individual installation\"\n          operations:\n            - method: GET\n              name: getAnInstallationForTheAuthenticatedApp\n              description: \"Get an installation\"\n              call: \"github-apps.getAnInstallationForTheAuthenticatedApp\"\n              with:\n                installation_id: \"rest.installation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: deleteAnInstallationForTheAuthenticatedApp\n              description: \"Delete an installation\"\n              call: \"github-apps.deleteAnInstallationForTheAuthenticatedApp\"\n              with:\n                installation_id: \"rest.installation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n  \
  \      - path: /v1/app/installations/{installation_id}/access-tokens\n          name: installation-tokens\n          description: \"Installation access tokens\"\n          operations:\n            - method: POST\n              name: createAnInstallationAccessTokenForAnApp\n              description: \"Create an access token\"\n              call: \"github-apps.createAnInstallationAccessTokenForAnApp\"\n              with:\n                installation_id: \"rest.installation_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}\n          name: organization\n          description: \"Organization management\"\n          operations:\n            - method: GET\n              name: getAnOrganization\n              description: \"Get an organization\"\n              call: \"github-orgs.getAnOrganization\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n     \
  \           - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateAnOrganization\n              description: \"Update an organization\"\n              call: \"github-orgs.updateAnOrganization\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/members\n          name: members\n          description: \"Member management\"\n          operations:\n            - method: GET\n              name: listOrganizationMembers\n              description: \"List members\"\n              call: \"github-orgs.listOrganizationMembers\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/teams\n          name: teams\n          description: \"Team management\"\n     \
  \     operations:\n            - method: GET\n              name: listTeams\n              description: \"List teams\"\n              call: \"github-orgs.listTeams\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: createTeam\n              description: \"Create a team\"\n              call: \"github-orgs.createTeam\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/teams/{team_slug}\n          name: team\n          description: \"Individual team operations\"\n          operations:\n            - method: GET\n              name: getTeamByName\n              description: \"Get a team\"\n              call: \"github-orgs.getTeamByName\"\n              with:\n                org: \"rest.org\"\
  \n                team_slug: \"rest.team_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PATCH\n              name: updateTeam\n              description: \"Update a team\"\n              call: \"github-orgs.updateTeam\"\n              with:\n                org: \"rest.org\"\n                team_slug: \"rest.team_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: deleteTeam\n              description: \"Delete a team\"\n              call: \"github-orgs.deleteTeam\"\n              with:\n                org: \"rest.org\"\n                team_slug: \"rest.team_slug\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/packages\n          name: org-packages\n          description: \"Organization packages\"\n   \
  \       operations:\n            - method: GET\n              name: listPackagesForAnOrganization\n              description: \"List packages\"\n              call: \"github-packages.listPackagesForAnOrganization\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/webhooks\n          name: webhooks\n          description: \"Organization webhooks\"\n          operations:\n            - method: GET\n              name: listOrganizationWebhooks\n              description: \"List webhooks\"\n              call: \"github-orgs.listOrganizationWebhooks\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/organizations/{org}/repos\n          name: org-repos\n          description: \"Organization repositories\"\n          operations:\n\
  \            - method: GET\n              name: listOrganizationRepositories\n              description: \"List repositories\"\n              call: \"github-orgs.listOrganizationRepositories\"\n              with:\n                org: \"rest.org\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9085\n      namespace: github-platform-admin-mcp\n      transport: http\n      description: \"MCP server for AI-assisted platform administration.\"\n      tools:\n        - name: get-authenticated-app\n          description: \"Get the authenticated app\"\n          call: \"github-apps.getTheAuthenticatedApp\"\n          hints:\n            readOnly: true\n        - name: get-app\n          description: \"Get an app by slug\"\n          call: \"github-apps.getAnApp\"\n          hints:\n            readOnly: true\n        - name: list-installations\n          description: \"List app installations\"\n          call:\
  \ \"github-apps.listInstallationsForTheAuthenticatedApp\"\n          hints:\n            readOnly: true\n        - name: get-installation\n          description: \"Get an app installation\"\n          call: \"github-apps.getAnInstallationForTheAuthenticatedApp\"\n          hints:\n            readOnly: true\n        - name: create-installation-token\n          description: \"Create an installation access token\"\n          call: \"github-apps.createAnInstallationAccessTokenForAnApp\"\n        - name: suspend-installation\n          description: \"Suspend an app installation\"\n          call: \"github-apps.suspendAnAppInstallation\"\n        - name: unsuspend-installation\n          description: \"Unsuspend an app installation\"\n          call: \"github-apps.unsuspendAnAppInstallation\"\n        - name: list-installation-repos\n          description: \"List repositories accessible to the installation\"\n          call: \"github-apps.listRepositoriesAccessibleToTheAppInstallation\"\n \
  \         hints:\n            readOnly: true\n        - name: get-webhook-config\n          description: \"Get app webhook configuration\"\n          call: \"github-apps.getwebhookConfigurationForAnApp\"\n          hints:\n            readOnly: true\n        - name: update-webhook-config\n          description: \"Update app webhook configuration\"\n          call: \"github-apps.updatewebhookConfigurationForAnApp\"\n          hints:\n            idempotent: true\n        - name: get-organization\n          description: \"Get an organization\"\n          call: \"github-orgs.getAnOrganization\"\n          hints:\n            readOnly: true\n        - name: update-organization\n          description: \"Update an organization\"\n          call: \"github-orgs.updateAnOrganization\"\n          hints:\n            idempotent: true\n        - name: list-members\n          description: \"List organization members\"\n          call: \"github-orgs.listOrganizationMembers\"\n          hints:\n    \
  \        readOnly: true\n        - name: set-membership\n          description: \"Set organization membership\"\n          call: \"github-orgs.setOrganizationMembershipForUser\"\n          hints:\n            idempotent: true\n        - name: remove-member\n          description: \"Remove an organization member\"\n          call: \"github-orgs.removeAnOrganizationMember\"\n          hints:\n            destructive: true\n        - name: list-teams\n          description: \"List teams\"\n          call: \"github-orgs.listTeams\"\n          hints:\n            readOnly: true\n        - name: create-team\n          description: \"Create a team\"\n          call: \"github-orgs.createTeam\"\n        - name: get-team\n          description: \"Get a team\"\n          call: \"github-orgs.getTeamByName\"\n          hints:\n            readOnly: true\n        - name: update-team\n          description: \"Update a team\"\n          call: \"github-orgs.updateTeam\"\n          hints:\n            idempotent:\
  \ true\n        - name: delete-team\n          description: \"Delete a team\"\n          call: \"github-orgs.deleteTeam\"\n          hints:\n            destructive: true\n        - name: list-team-members\n          description: \"List team members\"\n          call: \"github-orgs.listTeamMembers\"\n          hints:\n            readOnly: true\n        - name: add-team-member\n          description: \"Add or update team membership\"\n          call: \"github-orgs.addOrUpdateTeamMembershipForUser\"\n          hints:\n            idempotent: true\n        - name: list-team-repos\n          description: \"List team repositories\"\n          call: \"github-orgs.listTeamRepositories\"\n          hints:\n            readOnly: true\n        - name: add-team-repo\n          description: \"Add or update team repository permissions\"\n          call: \"github-orgs.addOrUpdateTeamRepositoryPermissions\"\n          hints:\n            idempotent: true\n        - name: list-org-packages\n        \
  \  description: \"List organization packages\"\n          call: \"github-packages.listPackagesForAnOrganization\"\n          hints:\n            readOnly: true\n        - name: get-org-package\n          description: \"Get an organization package\"\n          call: \"github-packages.getPackageForAnOrganization\"\n          hints:\n            readOnly: true\n        - name: delete-org-package\n          description: \"Delete an organization package\"\n          call: \"github-packages.deletePackageForAnOrganization\"\n          hints:\n            destructive: true\n        - name: list-org-package-versions\n          description: \"List organization package versions\"\n          call: \"github-packages.listPackageVersionsForPackageOwnedByAnOrganization\"\n          hints:\n            readOnly: true\n        - name: list-org-repos\n          description: \"List organization repositories\"\n          call: \"github-orgs.listOrganizationRepositories\"\n          hints:\n            readOnly:\
  \ true\n        - name: create-org-repo\n          description: \"Create an organization repository\"\n          call: \"github-orgs.createAnOrganizationRepository\"\n        - name: list-webhooks\n          description: \"List organization webhooks\"\n          call: \"github-orgs.listOrganizationWebhooks\"\n          hints:\n            readOnly: true\n        - name: create-webhook\n          description: \"Create an organization webhook\"\n          call: \"github-orgs.createAnOrganizationWebhook\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/github/refs/heads/main/capabilities/platform-administration.yaml
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
