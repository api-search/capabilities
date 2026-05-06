---
categories: []
consumed_apis: []
description: The Grafana HTTP API provides programmatic access to Grafana's core functionality including dashboards, data sources, alerts, users, organizations, folders, annotations, and teams. Authentication is handled via API keys, basic auth, or OAuth tokens passed in the Authorization header.
layout: capability
name: Grafana HTTP API
operations:
- description: Create or update a dashboard
  method: POST
  name: createupdatedashboard
  path: /dashboards/db
- description: Get dashboard by UID
  method: GET
  name: getdashboardbyuid
  path: /dashboards/uid/{uid}
- description: Delete dashboard by UID
  method: DELETE
  name: deletedashboardbyuid
  path: /dashboards/uid/{uid}
- description: Search dashboards and folders
  method: GET
  name: searchdashboards
  path: /search
- description: List all data sources
  method: GET
  name: getdatasources
  path: /datasources
- description: Create a data source
  method: POST
  name: createdatasource
  path: /datasources
- description: Get data source by ID
  method: GET
  name: getdatasourcebyid
  path: /datasources/{id}
- description: Update data source by ID
  method: PUT
  name: updatedatasource
  path: /datasources/{id}
- description: Delete data source by ID
  method: DELETE
  name: deletedatasourcebyid
  path: /datasources/{id}
- description: Get data source by UID
  method: GET
  name: getdatasourcebyuid
  path: /datasources/uid/{uid}
- description: List all alert rules
  method: GET
  name: getalertrules
  path: /v1/provisioning/alert-rules
- description: Create an alert rule
  method: POST
  name: createalertrule
  path: /v1/provisioning/alert-rules
- description: Get alert rule by UID
  method: GET
  name: getalertrule
  path: /v1/provisioning/alert-rules/{uid}
- description: Update alert rule
  method: PUT
  name: updatealertrule
  path: /v1/provisioning/alert-rules/{uid}
- description: Delete alert rule
  method: DELETE
  name: deletealertrule
  path: /v1/provisioning/alert-rules/{uid}
- description: List contact points
  method: GET
  name: getcontactpoints
  path: /v1/provisioning/contact-points
- description: Create a contact point
  method: POST
  name: createcontactpoint
  path: /v1/provisioning/contact-points
- description: Create a new user (admin)
  method: POST
  name: admincreateuser
  path: /admin/users
- description: Search users
  method: GET
  name: searchusers
  path: /users
- description: Get user by ID
  method: GET
  name: getuserbyid
  path: /users/{id}
- description: Update user
  method: PUT
  name: updateuser
  path: /users/{id}
- description: Get current user
  method: GET
  name: getcurrentuser
  path: /user
- description: Search organizations
  method: GET
  name: searchorgs
  path: /orgs
- description: Create organization
  method: POST
  name: createorg
  path: /orgs
- description: Get organization by ID
  method: GET
  name: getorgbyid
  path: /orgs/{orgId}
- description: Update organization
  method: PUT
  name: updateorg
  path: /orgs/{orgId}
- description: Delete organization
  method: DELETE
  name: deleteorg
  path: /orgs/{orgId}
- description: Get users in organization
  method: GET
  name: getorgusers
  path: /orgs/{orgId}/users
- description: Add user to organization
  method: POST
  name: addorguser
  path: /orgs/{orgId}/users
- description: List all folders
  method: GET
  name: getfolders
  path: /folders
- description: Create a folder
  method: POST
  name: createfolder
  path: /folders
- description: Get folder by UID
  method: GET
  name: getfolderbyuid
  path: /folders/{uid}
- description: Update folder
  method: PUT
  name: updatefolder
  path: /folders/{uid}
- description: Delete folder
  method: DELETE
  name: deletefolder
  path: /folders/{uid}
- description: Find annotations
  method: GET
  name: getannotations
  path: /annotations
- description: Create annotation
  method: POST
  name: createannotation
  path: /annotations
- description: Delete annotation
  method: DELETE
  name: deleteannotation
  path: /annotations/{id}
- description: Search teams
  method: GET
  name: searchteams
  path: /teams/search
- description: Create team
  method: POST
  name: createteam
  path: /teams
- description: Get team by ID
  method: GET
  name: getteambyid
  path: /teams/{id}
- description: Update team
  method: PUT
  name: updateteam
  path: /teams/{id}
- description: Delete team
  method: DELETE
  name: deleteteam
  path: /teams/{id}
- description: Get team members
  method: GET
  name: getteammembers
  path: /teams/{id}/members
- description: Add team member
  method: POST
  name: addteammember
  path: /teams/{id}/members
personas: []
provider_name: Grafana
provider_slug: grafana
search_terms:
- update organization
- search dashboards and folders
- create an alert rule
- create a new user (admin)
- get data source by uid
- analytics
- updatedatasource
- createfolder
- getannotations
- updatefolder
- alerting
- get users in organization
- getuserbyid
- deletealertrule
- getdashboardbyuid
- getfolders
- create or update a dashboard
- create organization
- grafana
- api
- observability
- createupdatedashboard
- get data source by id
- update user
- update data source by id
- getcontactpoints
- getalertrule
- get team by id
- updateuser
- add team member
- delete dashboard by uid
- getorgbyid
- addteammember
- update alert rule
- getdatasourcebyuid
- searchusers
- metrics
- deletedashboardbyuid
- monitoring
- getalertrules
- getteambyid
- add user to organization
- updateteam
- getteammembers
- list all folders
- getfolderbyuid
- search users
- get current user
- find annotations
- search teams
- createalertrule
- delete folder
- create a contact point
- searchdashboards
- dashboards
- logs
- admincreateuser
- createorg
- createcontactpoint
- updatealertrule
- deletedatasourcebyid
- search organizations
- createannotation
- list all data sources
- create a data source
- getdatasourcebyid
- create a folder
- traces
- updateorg
- addorguser
- createdatasource
- getcurrentuser
- update folder
- delete alert rule
- delete organization
- visualization
- getdatasources
- searchteams
- create annotation
- get team members
- get dashboard by uid
- delete team
- update team
- get user by id
- searchorgs
- get organization by id
- deletefolder
- create team
- deleteannotation
- deleteteam
- getorgusers
- delete annotation
- delete data source by id
- get folder by uid
- list all alert rules
- get alert rule by uid
- createteam
- list contact points
- deleteorg
slug: grafana-capability
source_filename: grafana-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grafana HTTP API\n  description: The Grafana HTTP API provides programmatic access to Grafana's core functionality including dashboards, data\n    sources, alerts, users, organizations, folders, annotations, and teams. Authentication is handled via API keys, basic\n    auth, or OAuth tokens passed in the Authorization header.\n  tags:\n  - Grafana\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grafana\n    baseUri: https://your-instance.grafana.net/api\n    description: Grafana HTTP API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GRAFANA_TOKEN}}'\n    resources:\n    - name: dashboards-db\n      path: /dashboards/db\n      operations:\n      - name: createupdatedashboard\n        method: POST\n        description: Create or update a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: dashboards-uid-uid\n      path: /dashboards/uid/{uid}\n      operations:\n      - name: getdashboardbyuid\n        method: GET\n        description: Get dashboard by UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedashboardbyuid\n        method: DELETE\n        description: Delete dashboard by UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: searchdashboards\n        method: GET\n        description: Search dashboards and folders\n        inputParameters:\n        -\
  \ name: query\n          in: query\n          type: string\n        - name: tag\n          in: query\n          type: array\n        - name: type\n          in: query\n          type: string\n        - name: folderIds\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources\n      path: /datasources\n      operations:\n      - name: getdatasources\n        method: GET\n        description: List all data sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatasource\n        method: POST\n        description: Create a data source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n    - name: datasources-id\n      path: /datasources/{id}\n      operations:\n      - name: getdatasourcebyid\n        method: GET\n        description: Get data source by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatasource\n        method: PUT\n        description: Update data source by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatasourcebyid\n        method: DELETE\n        description: Delete data source by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources-uid-uid\n      path: /datasources/uid/{uid}\n      operations:\n      - name: getdatasourcebyuid\n        method: GET\n        description: Get data source by UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-provisioning-alert-rules\n      path: /v1/provisioning/alert-rules\n      operations:\n      - name: getalertrules\n        method: GET\n        description: List all alert rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalertrule\n        method: POST\n        description: Create an alert rule\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-provisioning-alert-rules-uid\n      path: /v1/provisioning/alert-rules/{uid}\n      operations:\n      - name: getalertrule\n        method: GET\n        description: Get alert rule by UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatealertrule\n        method: PUT\n        description: Update alert rule\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletealertrule\n        method: DELETE\n        description: Delete alert\
  \ rule\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-provisioning-contact-points\n      path: /v1/provisioning/contact-points\n      operations:\n      - name: getcontactpoints\n        method: GET\n        description: List contact points\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontactpoint\n        method: POST\n        description: Create a contact point\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-users\n      path: /admin/users\n      operations:\n      - name: admincreateuser\n        method: POST\n        description: Create a new user (admin)\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: searchusers\n        method: GET\n        description: Search users\n        inputParameters:\n        - name: perpage\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        - name: query\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: getuserbyid\n        method: GET\n        description: Get user by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updateuser\n        method: PUT\n        description: Update user\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs\n      path: /orgs\n      operations:\n      - name: searchorgs\n        method: GET\n        description: Search organizations\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorg\n        method: POST\n        description: Create organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid\n      path: /orgs/{orgId}\n      operations:\n      - name: getorgbyid\n        method: GET\n        description: Get organization by ID\n        inputParameters:\n        - name: orgId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorg\n        method: PUT\n        description: Update organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n      - name: deleteorg\n        method: DELETE\n        description: Delete organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs-orgid-users\n      path: /orgs/{orgId}/users\n      operations:\n      - name: getorgusers\n        method: GET\n        description: Get users in organization\n        inputParameters:\n        - name: orgId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addorguser\n        method: POST\n        description: Add user to organization\n        inputParameters:\n        - name: orgId\n          in: path\n      \
  \    type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      operations:\n      - name: getfolders\n        method: GET\n        description: List all folders\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfolder\n        method: POST\n        description: Create a folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders-uid\n      path: /folders/{uid}\n      operations:\n      - name: getfolderbyuid\n        method: GET\n        description: Get folder by UID\n        inputParameters:\n\
  \        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefolder\n        method: PUT\n        description: Update folder\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefolder\n        method: DELETE\n        description: Delete folder\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: annotations\n      path: /annotations\n      operations:\n      - name: getannotations\n        method: GET\n\
  \        description: Find annotations\n        inputParameters:\n        - name: from\n          in: query\n          type: integer\n        - name: to\n          in: query\n          type: integer\n        - name: dashboardId\n          in: query\n          type: integer\n        - name: panelId\n          in: query\n          type: integer\n        - name: tags\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createannotation\n        method: POST\n        description: Create annotation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: annotations-id\n      path: /annotations/{id}\n      operations:\n      - name: deleteannotation\n        method: DELETE\n        description: Delete annotation\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-search\n      path: /teams/search\n      operations:\n      - name: searchteams\n        method: GET\n        description: Search teams\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams\n      path: /teams\n      operations:\n      - name: createteam\n        method: POST\n        description: Create team\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: teams-id\n      path: /teams/{id}\n      operations:\n      - name: getteambyid\n        method: GET\n        description: Get team by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateteam\n        method: PUT\n        description: Update team\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteteam\n        method: DELETE\n        description: Delete team\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: teams-id-members\n      path: /teams/{id}/members\n      operations:\n      - name: getteammembers\n        method: GET\n        description: Get team members\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addteammember\n        method: POST\n        description: Add team member\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grafana-rest\n    description: REST adapter for Grafana HTTP API.\n    resources:\n    - path: /dashboards/db\n      name:\
  \ createupdatedashboard\n      operations:\n      - method: POST\n        name: createupdatedashboard\n        description: Create or update a dashboard\n        call: grafana.createupdatedashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/uid/{uid}\n      name: getdashboardbyuid\n      operations:\n      - method: GET\n        name: getdashboardbyuid\n        description: Get dashboard by UID\n        call: grafana.getdashboardbyuid\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/uid/{uid}\n      name: deletedashboardbyuid\n      operations:\n      - method: DELETE\n        name: deletedashboardbyuid\n        description: Delete dashboard by UID\n        call: grafana.deletedashboardbyuid\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: searchdashboards\n\
  \      operations:\n      - method: GET\n        name: searchdashboards\n        description: Search dashboards and folders\n        call: grafana.searchdashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources\n      name: getdatasources\n      operations:\n      - method: GET\n        name: getdatasources\n        description: List all data sources\n        call: grafana.getdatasources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources\n      name: createdatasource\n      operations:\n      - method: POST\n        name: createdatasource\n        description: Create a data source\n        call: grafana.createdatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: getdatasourcebyid\n      operations:\n      - method: GET\n        name: getdatasourcebyid\n        description: Get data source by ID\n        call: grafana.getdatasourcebyid\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: updatedatasource\n      operations:\n      - method: PUT\n        name: updatedatasource\n        description: Update data source by ID\n        call: grafana.updatedatasource\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: deletedatasourcebyid\n      operations:\n      - method: DELETE\n        name: deletedatasourcebyid\n        description: Delete data source by ID\n        call: grafana.deletedatasourcebyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/uid/{uid}\n      name: getdatasourcebyuid\n      operations:\n      - method: GET\n        name: getdatasourcebyuid\n        description: Get data source by UID\n        call: grafana.getdatasourcebyuid\n\
  \        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules\n      name: getalertrules\n      operations:\n      - method: GET\n        name: getalertrules\n        description: List all alert rules\n        call: grafana.getalertrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules\n      name: createalertrule\n      operations:\n      - method: POST\n        name: createalertrule\n        description: Create an alert rule\n        call: grafana.createalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules/{uid}\n      name: getalertrule\n      operations:\n      - method: GET\n        name: getalertrule\n        description: Get alert rule by UID\n        call: grafana.getalertrule\n        with:\n          uid: rest.uid\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules/{uid}\n      name: updatealertrule\n      operations:\n      - method: PUT\n        name: updatealertrule\n        description: Update alert rule\n        call: grafana.updatealertrule\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules/{uid}\n      name: deletealertrule\n      operations:\n      - method: DELETE\n        name: deletealertrule\n        description: Delete alert rule\n        call: grafana.deletealertrule\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/contact-points\n      name: getcontactpoints\n      operations:\n      - method: GET\n        name: getcontactpoints\n        description: List contact points\n        call: grafana.getcontactpoints\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /v1/provisioning/contact-points\n      name: createcontactpoint\n      operations:\n      - method: POST\n        name: createcontactpoint\n        description: Create a contact point\n        call: grafana.createcontactpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/users\n      name: admincreateuser\n      operations:\n      - method: POST\n        name: admincreateuser\n        description: Create a new user (admin)\n        call: grafana.admincreateuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users\n      name: searchusers\n      operations:\n      - method: GET\n        name: searchusers\n        description: Search users\n        call: grafana.searchusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: getuserbyid\n      operations:\n      - method: GET\n        name: getuserbyid\n\
  \        description: Get user by ID\n        call: grafana.getuserbyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{id}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update user\n        call: grafana.updateuser\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Get current user\n        call: grafana.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs\n      name: searchorgs\n      operations:\n      - method: GET\n        name: searchorgs\n        description: Search organizations\n        call: grafana.searchorgs\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /orgs\n      name: createorg\n      operations:\n      - method: POST\n        name: createorg\n        description: Create organization\n        call: grafana.createorg\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{orgId}\n      name: getorgbyid\n      operations:\n      - method: GET\n        name: getorgbyid\n        description: Get organization by ID\n        call: grafana.getorgbyid\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{orgId}\n      name: updateorg\n      operations:\n      - method: PUT\n        name: updateorg\n        description: Update organization\n        call: grafana.updateorg\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{orgId}\n      name: deleteorg\n      operations:\n      - method: DELETE\n        name: deleteorg\n\
  \        description: Delete organization\n        call: grafana.deleteorg\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{orgId}/users\n      name: getorgusers\n      operations:\n      - method: GET\n        name: getorgusers\n        description: Get users in organization\n        call: grafana.getorgusers\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs/{orgId}/users\n      name: addorguser\n      operations:\n      - method: POST\n        name: addorguser\n        description: Add user to organization\n        call: grafana.addorguser\n        with:\n          orgId: rest.orgId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders\n      name: getfolders\n      operations:\n      - method: GET\n        name: getfolders\n        description: List all folders\n     \
  \   call: grafana.getfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders\n      name: createfolder\n      operations:\n      - method: POST\n        name: createfolder\n        description: Create a folder\n        call: grafana.createfolder\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders/{uid}\n      name: getfolderbyuid\n      operations:\n      - method: GET\n        name: getfolderbyuid\n        description: Get folder by UID\n        call: grafana.getfolderbyuid\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders/{uid}\n      name: updatefolder\n      operations:\n      - method: PUT\n        name: updatefolder\n        description: Update folder\n        call: grafana.updatefolder\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /folders/{uid}\n      name: deletefolder\n      operations:\n      - method: DELETE\n        name: deletefolder\n        description: Delete folder\n        call: grafana.deletefolder\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations\n      name: getannotations\n      operations:\n      - method: GET\n        name: getannotations\n        description: Find annotations\n        call: grafana.getannotations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations\n      name: createannotation\n      operations:\n      - method: POST\n        name: createannotation\n        description: Create annotation\n        call: grafana.createannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations/{id}\n      name: deleteannotation\n      operations:\n      - method: DELETE\n        name: deleteannotation\n\
  \        description: Delete annotation\n        call: grafana.deleteannotation\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/search\n      name: searchteams\n      operations:\n      - method: GET\n        name: searchteams\n        description: Search teams\n        call: grafana.searchteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams\n      name: createteam\n      operations:\n      - method: POST\n        name: createteam\n        description: Create team\n        call: grafana.createteam\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{id}\n      name: getteambyid\n      operations:\n      - method: GET\n        name: getteambyid\n        description: Get team by ID\n        call: grafana.getteambyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /teams/{id}\n      name: updateteam\n      operations:\n      - method: PUT\n        name: updateteam\n        description: Update team\n        call: grafana.updateteam\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{id}\n      name: deleteteam\n      operations:\n      - method: DELETE\n        name: deleteteam\n        description: Delete team\n        call: grafana.deleteteam\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{id}/members\n      name: getteammembers\n      operations:\n      - method: GET\n        name: getteammembers\n        description: Get team members\n        call: grafana.getteammembers\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/{id}/members\n      name: addteammember\n      operations:\n \
  \     - method: POST\n        name: addteammember\n        description: Add team member\n        call: grafana.addteammember\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grafana-mcp\n    transport: http\n    description: MCP adapter for Grafana HTTP API for AI agent use.\n    tools:\n    - name: createupdatedashboard\n      description: Create or update a dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grafana.createupdatedashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdashboardbyuid\n      description: Get dashboard by UID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana.getdashboardbyuid\n      with:\n        uid: tools.uid\n      inputParameters:\n      - name: uid\n        type: string\n      \
  \  description: uid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedashboardbyuid\n      description: Delete dashboard by UID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: grafana.deletedashboardbyuid\n      with:\n        uid: tools.uid\n      inputParameters:\n      - name: uid\n        type: string\n        description: uid\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchdashboards\n      description: Search dashboards and folders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana.searchdashboards\n      with:\n        query: tools.query\n        tag: tools.tag\n        type: tools.type\n        folderIds: tools.folderIds\n        limit: tools.limit\n        page: tools.page\n      inputParameters:\n      - name: query\n        type: string\n\
  \        description: query\n      - name: tag\n        type: array\n        description: tag\n      - name: type\n        type: string\n        description: type\n      - name: folderIds\n        type: array\n        description: folderIds\n      - name: limit\n        type: integer\n        description: limit\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatasources\n      description: List all data sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana.getdatasources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatasource\n      description: Create a data source\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: grafana.createdatasource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getdatasourcebyid\n      description: Get data source by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana.getdatasourcebyid\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedatasource\n      description: Update data source by ID\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: grafana.updatedatasource\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedatasourcebyid\n      description: Delete data source by ID\n      hints:\n        readOnly: false\n        destructive: t\n\n# --- truncated at 32\
  \ KB (45 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/grafana/refs/heads/main/capabilities/grafana-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grafana/refs/heads/main/capabilities/grafana-capability.yaml
tags:
- Grafana
- API
tools:
- description: Create or update a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createupdatedashboard
- description: Get dashboard by UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardbyuid
- description: Delete dashboard by UID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardbyuid
- description: Search dashboards and folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdashboards
- description: List all data sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasources
- description: Create a data source
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatasource
- description: Get data source by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasourcebyid
- description: Update data source by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedatasource
- description: Delete data source by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatasourcebyid
- description: Get data source by UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasourcebyuid
- description: List all alert rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertrules
- description: Create an alert rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalertrule
- description: Get alert rule by UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertrule
- description: Update alert rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatealertrule
- description: Delete alert rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletealertrule
- description: List contact points
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcontactpoints
- description: Create a contact point
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcontactpoint
- description: Create a new user (admin)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: admincreateuser
- description: Search users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchusers
- description: Get user by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuserbyid
- description: Update user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Search organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchorgs
- description: Create organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorg
- description: Get organization by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorgbyid
- description: Update organization
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateorg
- description: Delete organization
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorg
- description: Get users in organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorgusers
- description: Add user to organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addorguser
- description: List all folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolders
- description: Create a folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfolder
- description: Get folder by UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolderbyuid
- description: Update folder
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefolder
- description: Delete folder
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefolder
- description: Find annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getannotations
- description: Create annotation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createannotation
- description: Delete annotation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteannotation
- description: Search teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchteams
- description: Create team
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createteam
- description: Get team by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteambyid
- description: Update team
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateteam
- description: Delete team
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteteam
- description: Get team members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getteammembers
- description: Add team member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addteammember
---
