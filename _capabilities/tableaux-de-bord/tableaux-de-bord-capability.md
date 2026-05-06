---
categories: []
consumed_apis: []
description: The Grafana HTTP API provides programmatic access to dashboard management, datasource configuration, organization management, user administration, annotation management, and alerting. Grafana is an open-source observability and analytics platform for infrastructure, application, and business monitoring.
layout: capability
name: Grafana Dashboard API
operations:
- description: Create Or Update Dashboard
  method: POST
  name: createorupdatedashboard
  path: /dashboards/db
- description: Get Dashboard By UID
  method: GET
  name: getdashboardbyuid
  path: /dashboards/uid/{uid}
- description: Delete Dashboard By UID
  method: DELETE
  name: deletedashboardbyuid
  path: /dashboards/uid/{uid}
- description: Search Dashboards
  method: GET
  name: searchdashboards
  path: /search
- description: List Datasources
  method: GET
  name: listdatasources
  path: /datasources
- description: Create Datasource
  method: POST
  name: createdatasource
  path: /datasources
- description: Get Datasource By ID
  method: GET
  name: getdatasourcebyid
  path: /datasources/{id}
- description: Update Datasource
  method: PUT
  name: updatedatasource
  path: /datasources/{id}
- description: Delete Datasource
  method: DELETE
  name: deletedatasource
  path: /datasources/{id}
- description: List Organizations
  method: GET
  name: listorganizations
  path: /orgs
- description: Create Organization
  method: POST
  name: createorganization
  path: /orgs
- description: List Organization Users
  method: GET
  name: listorgusers
  path: /org/users
- description: Search Teams
  method: GET
  name: searchteams
  path: /teams/search
- description: List Annotations
  method: GET
  name: listannotations
  path: /annotations
- description: Create Annotation
  method: POST
  name: createannotation
  path: /annotations
- description: List Folders
  method: GET
  name: listfolders
  path: /folders
- description: Create Folder
  method: POST
  name: createfolder
  path: /folders
- description: List Alert Rules
  method: GET
  name: listalertrules
  path: /v1/provisioning/alert-rules
- description: Create Alert Rule
  method: POST
  name: createalertrule
  path: /v1/provisioning/alert-rules
personas: []
provider_name: Tableaux De Bord
provider_slug: tableaux-de-bord
search_terms:
- create datasource
- createalertrule
- search dashboards
- delete dashboard by uid
- createdatasource
- delete datasource
- list organizations
- searchteams
- create annotation
- update datasource
- analytics
- updatedatasource
- get dashboard by uid
- list organization users
- create or update dashboard
- list folders
- createfolder
- tableaux
- searchdashboards
- listfolders
- dashboards
- deletedashboardbyuid
- monitoring
- getdashboardbyuid
- list annotations
- listdatasources
- listorgusers
- listorganizations
- data visualization
- create organization
- listannotations
- bord
- createannotation
- metabase
- grafana
- api
- createorganization
- get datasource by id
- deletedatasource
- business intelligence
- getdatasourcebyid
- list datasources
- search teams
- de
- createorupdatedashboard
- create folder
- create alert rule
- list alert rules
- listalertrules
slug: tableaux-de-bord-capability
source_filename: tableaux-de-bord-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grafana Dashboard API\n  description: The Grafana HTTP API provides programmatic access to dashboard management, datasource configuration, organization\n    management, user administration, annotation management, and alerting. Grafana is an open-source observability and analytics\n    platform for infrastructure, application, and business monitoring.\n  tags:\n  - Tableaux\n  - De\n  - Bord\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: tableaux-de-bord\n    baseUri: https://localhost:3000/api\n    description: Grafana Dashboard API HTTP API.\n    authentication:\n      type: basic\n      username: '{{TABLEAUX_DE_BORD_USERNAME}}'\n      password: '{{TABLEAUX_DE_BORD_PASSWORD}}'\n    resources:\n    - name: dashboards-db\n      path: /dashboards/db\n      operations:\n      - name: createorupdatedashboard\n        method: POST\n        description: Create Or Update Dashboard\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboards-uid-uid\n      path: /dashboards/uid/{uid}\n      operations:\n      - name: getdashboardbyuid\n        method: GET\n        description: Get Dashboard By UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n          description: Dashboard unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedashboardbyuid\n        method: DELETE\n        description: Delete Dashboard By UID\n        inputParameters:\n        - name: uid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n \
  \     operations:\n      - name: searchdashboards\n        method: GET\n        description: Search Dashboards\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          description: Search query string\n        - name: tag\n          in: query\n          type: string\n          description: Filter by tag\n        - name: type\n          in: query\n          type: string\n          description: Resource type filter\n        - name: folderIds\n          in: query\n          type: array\n          description: Folder IDs to search within\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources\n      path: /datasources\n      operations:\n      - name: listdatasources\n        method: GET\n        description: List Datasources\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: createdatasource\n        method: POST\n        description: Create Datasource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasources-id\n      path: /datasources/{id}\n      operations:\n      - name: getdatasourcebyid\n        method: GET\n        description: Get Datasource By ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatasource\n        method: PUT\n        description: Update Datasource\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deletedatasource\n        method: DELETE\n        description: Delete Datasource\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: orgs\n      path: /orgs\n      operations:\n      - name: listorganizations\n        method: GET\n        description: List Organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganization\n        method: POST\n        description: Create Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: org-users\n      path: /org/users\n      operations:\n      - name: listorgusers\n        method: GET\n\
  \        description: List Organization Users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: teams-search\n      path: /teams/search\n      operations:\n      - name: searchteams\n        method: GET\n        description: Search Teams\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: perpage\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: annotations\n      path: /annotations\n      operations:\n      - name: listannotations\n        method: GET\n        description: List Annotations\n        inputParameters:\n        - name: from\n          in: query\n          type: integer\n          description: Start time in milliseconds\n    \
  \    - name: to\n          in: query\n          type: integer\n          description: End time in milliseconds\n        - name: dashboardId\n          in: query\n          type: integer\n        - name: panelId\n          in: query\n          type: integer\n        - name: tags\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createannotation\n        method: POST\n        description: Create Annotation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: folders\n      path: /folders\n      operations:\n      - name: listfolders\n        method: GET\n        description: List Folders\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n      - name: createfolder\n        method: POST\n        description: Create Folder\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-provisioning-alert-rules\n      path: /v1/provisioning/alert-rules\n      operations:\n      - name: listalertrules\n        method: GET\n        description: List Alert Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalertrule\n        method: POST\n        description: Create Alert Rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tableaux-de-bord-rest\n    description: REST adapter for Grafana Dashboard API.\n    resources:\n    - path: /dashboards/db\n      name: createorupdatedashboard\n      operations:\n\
  \      - method: POST\n        name: createorupdatedashboard\n        description: Create Or Update Dashboard\n        call: tableaux-de-bord.createorupdatedashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/uid/{uid}\n      name: getdashboardbyuid\n      operations:\n      - method: GET\n        name: getdashboardbyuid\n        description: Get Dashboard By UID\n        call: tableaux-de-bord.getdashboardbyuid\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboards/uid/{uid}\n      name: deletedashboardbyuid\n      operations:\n      - method: DELETE\n        name: deletedashboardbyuid\n        description: Delete Dashboard By UID\n        call: tableaux-de-bord.deletedashboardbyuid\n        with:\n          uid: rest.uid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: searchdashboards\n\
  \      operations:\n      - method: GET\n        name: searchdashboards\n        description: Search Dashboards\n        call: tableaux-de-bord.searchdashboards\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources\n      name: listdatasources\n      operations:\n      - method: GET\n        name: listdatasources\n        description: List Datasources\n        call: tableaux-de-bord.listdatasources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources\n      name: createdatasource\n      operations:\n      - method: POST\n        name: createdatasource\n        description: Create Datasource\n        call: tableaux-de-bord.createdatasource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: getdatasourcebyid\n      operations:\n      - method: GET\n        name: getdatasourcebyid\n        description: Get Datasource By ID\n      \
  \  call: tableaux-de-bord.getdatasourcebyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: updatedatasource\n      operations:\n      - method: PUT\n        name: updatedatasource\n        description: Update Datasource\n        call: tableaux-de-bord.updatedatasource\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /datasources/{id}\n      name: deletedatasource\n      operations:\n      - method: DELETE\n        name: deletedatasource\n        description: Delete Datasource\n        call: tableaux-de-bord.deletedatasource\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: List Organizations\n       \
  \ call: tableaux-de-bord.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /orgs\n      name: createorganization\n      operations:\n      - method: POST\n        name: createorganization\n        description: Create Organization\n        call: tableaux-de-bord.createorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /org/users\n      name: listorgusers\n      operations:\n      - method: GET\n        name: listorgusers\n        description: List Organization Users\n        call: tableaux-de-bord.listorgusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /teams/search\n      name: searchteams\n      operations:\n      - method: GET\n        name: searchteams\n        description: Search Teams\n        call: tableaux-de-bord.searchteams\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations\n      name:\
  \ listannotations\n      operations:\n      - method: GET\n        name: listannotations\n        description: List Annotations\n        call: tableaux-de-bord.listannotations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /annotations\n      name: createannotation\n      operations:\n      - method: POST\n        name: createannotation\n        description: Create Annotation\n        call: tableaux-de-bord.createannotation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders\n      name: listfolders\n      operations:\n      - method: GET\n        name: listfolders\n        description: List Folders\n        call: tableaux-de-bord.listfolders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /folders\n      name: createfolder\n      operations:\n      - method: POST\n        name: createfolder\n        description: Create Folder\n        call: tableaux-de-bord.createfolder\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules\n      name: listalertrules\n      operations:\n      - method: GET\n        name: listalertrules\n        description: List Alert Rules\n        call: tableaux-de-bord.listalertrules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/provisioning/alert-rules\n      name: createalertrule\n      operations:\n      - method: POST\n        name: createalertrule\n        description: Create Alert Rule\n        call: tableaux-de-bord.createalertrule\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tableaux-de-bord-mcp\n    transport: http\n    description: MCP adapter for Grafana Dashboard API for AI agent use.\n    tools:\n    - name: createorupdatedashboard\n      description: Create Or Update Dashboard\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: false\n      call: tableaux-de-bord.createorupdatedashboard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdashboardbyuid\n      description: Get Dashboard By UID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.getdashboardbyuid\n      with:\n        uid: tools.uid\n      inputParameters:\n      - name: uid\n        type: string\n        description: Dashboard unique identifier\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedashboardbyuid\n      description: Delete Dashboard By UID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tableaux-de-bord.deletedashboardbyuid\n      with:\n        uid: tools.uid\n      inputParameters:\n      - name: uid\n        type: string\n        description: uid\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: searchdashboards\n      description: Search Dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.searchdashboards\n      with:\n        query: tools.query\n        tag: tools.tag\n        type: tools.type\n        folderIds: tools.folderIds\n        limit: tools.limit\n      inputParameters:\n      - name: query\n        type: string\n        description: Search query string\n      - name: tag\n        type: string\n        description: Filter by tag\n      - name: type\n        type: string\n        description: Resource type filter\n      - name: folderIds\n        type: array\n        description: Folder IDs to search within\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatasources\n      description: List Datasources\n      hints:\n      \
  \  readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listdatasources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatasource\n      description: Create Datasource\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tableaux-de-bord.createdatasource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdatasourcebyid\n      description: Get Datasource By ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.getdatasourcebyid\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedatasource\n      description: Update Datasource\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.updatedatasource\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedatasource\n      description: Delete Datasource\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tableaux-de-bord.deletedatasource\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganizations\n      description: List Organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listorganizations\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: createorganization\n      description: Create Organization\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tableaux-de-bord.createorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorgusers\n      description: List Organization Users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listorgusers\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchteams\n      description: Search Teams\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.searchteams\n      with:\n        query: tools.query\n        page: tools.page\n        perpage: tools.perpage\n      inputParameters:\n      - name: query\n        type: string\n        description: query\n      - name: page\n        type: integer\n\
  \        description: page\n      - name: perpage\n        type: integer\n        description: perpage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listannotations\n      description: List Annotations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listannotations\n      with:\n        from: tools.from\n        to: tools.to\n        dashboardId: tools.dashboardId\n        panelId: tools.panelId\n        tags: tools.tags\n        limit: tools.limit\n      inputParameters:\n      - name: from\n        type: integer\n        description: Start time in milliseconds\n      - name: to\n        type: integer\n        description: End time in milliseconds\n      - name: dashboardId\n        type: integer\n        description: dashboardId\n      - name: panelId\n        type: integer\n        description: panelId\n      - name: tags\n        type: array\n        description: tags\n    \
  \  - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createannotation\n      description: Create Annotation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tableaux-de-bord.createannotation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfolders\n      description: List Folders\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listfolders\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfolder\n      description: Create Folder\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tableaux-de-bord.createfolder\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalertrules\n      description: List Alert Rules\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: tableaux-de-bord.listalertrules\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalertrule\n      description: Create Alert Rule\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tableaux-de-bord.createalertrule\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    TABLEAUX_DE_BORD_USERNAME: TABLEAUX_DE_BORD_USERNAME\n    TABLEAUX_DE_BORD_PASSWORD: TABLEAUX_DE_BORD_PASSWORD\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tableaux-de-bord/refs/heads/main/capabilities/tableaux-de-bord-capability.yaml
tags:
- Tableaux
- De
- Bord
- API
tools:
- description: Create Or Update Dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorupdatedashboard
- description: Get Dashboard By UID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboardbyuid
- description: Delete Dashboard By UID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboardbyuid
- description: Search Dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdashboards
- description: List Datasources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatasources
- description: Create Datasource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatasource
- description: Get Datasource By ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasourcebyid
- description: Update Datasource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedatasource
- description: Delete Datasource
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatasource
- description: List Organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Create Organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganization
- description: List Organization Users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorgusers
- description: Search Teams
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchteams
- description: List Annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listannotations
- description: Create Annotation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createannotation
- description: List Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfolders
- description: Create Folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfolder
- description: List Alert Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalertrules
- description: Create Alert Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalertrule
---
