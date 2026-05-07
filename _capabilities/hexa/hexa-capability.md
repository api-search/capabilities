---
categories: []
consumed_apis: []
description: API specification for the Hex External API
layout: capability
name: Hex API
operations:
- description: Create an embedded url for a project
  method: POST
  name: createpresignedurl
  path: /v1/embedding/createPresignedUrl/{projectId}
- description: Create a new project. Creates a new project in the workspace with the specified title. Optionally provide a description and project language.
  method: POST
  name: createproject
  path: /v1/projects
- description: List all viewable projects, sorted by most recently created first.
  method: GET
  name: listprojects
  path: /v1/projects
- description: Get metadata about a single project.
  method: GET
  name: getproject
  path: /v1/projects/{projectId}
- description: Use this endpoint to add or remove a status (including endorsements) from a project
  method: PATCH
  name: updateproject
  path: /v1/projects/{projectId}
- description: Given a project ID, return the list of warehouse tables queried in the project.
  method: GET
  name: getqueriedtables
  path: /v1/projects/{projectId}/queriedTables
- description: Add a project to collections or remove it from collections. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app". Workspace tokens calling this endpo
  method: PATCH
  name: editprojectsharingcollections
  path: /v1/projects/{projectId}/sharing/collections
- description: Update workspace or public-web sharing for a project. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  method: PATCH
  name: editprojectsharingorgandpublic
  path: /v1/projects/{projectId}/sharing/workspaceAndPublic
- description: Add groups to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  method: PATCH
  name: editprojectsharinggroups
  path: /v1/projects/{projectId}/sharing/groups
- description: Add users to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  method: PATCH
  name: editprojectsharingusers
  path: /v1/projects/{projectId}/sharing/users
- description: Ingest a semantic project from a zip file. This API endpoint is subject to a maximum of 3 requests per minute.
  method: POST
  name: ingestsemanticproject
  path: /v1/semantic-(projects|models)/{semanticProjectId}/ingest
- description: Use this endpoint to add or remove a status (including endorsements) from datasets and views within a semantic project This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails and no change
  method: PATCH
  name: updatesemanticproject
  path: /v1/semantic-(projects|models)/{semanticProjectId}
- description: Trigger a run of the latest published version of a project. This API endpoint is subject to a maximum of 20 requests per minute and 60 requests per hour.
  method: POST
  name: runproject
  path: /v1/projects/{projectId}/runs
- description: Get the status of runs of a project. By default, all run types are returned (API-triggered, scheduled, and publish/refresh runs). Use the `runTriggerFilter` parameter to filter to a specific type.
  method: GET
  name: getprojectruns
  path: /v1/projects/{projectId}/runs
- description: Get the status of a project run.
  method: GET
  name: getrunstatus
  path: /v1/projects/{projectId}/runs/{runId}
- description: Cancel a project run.
  method: DELETE
  name: cancelrun
  path: /v1/projects/{projectId}/runs/{runId}
- description: Get the rendered PNG image of a chart cell from a completed run by staticCellId. The "staticId" path parameter should be the cell's staticId (which remains stable across project versions), as opposed to its cellId (which is scoped to a spec
  method: GET
  name: getchartimagefromrun
  path: /v1/projects/{projectId}/runs/{runId}/cells/{staticId}/image
- description: GET /v1/groups/{groupId}
  method: GET
  name: getgroup
  path: /v1/groups/{groupId}
- description: DELETE /v1/groups/{groupId}
  method: DELETE
  name: deletegroup
  path: /v1/groups/{groupId}
- description: PATCH /v1/groups/{groupId}
  method: PATCH
  name: editgroup
  path: /v1/groups/{groupId}
- description: GET /v1/groups
  method: GET
  name: listgroups
  path: /v1/groups
- description: POST /v1/groups
  method: POST
  name: creategroup
  path: /v1/groups
- description: GET /v1/data-connections/{dataConnectionId}
  method: GET
  name: getdataconnection
  path: /v1/data-connections/{dataConnectionId}
- description: PATCH /v1/data-connections/{dataConnectionId}
  method: PATCH
  name: editdataconnection
  path: /v1/data-connections/{dataConnectionId}
- description: GET /v1/data-connections
  method: GET
  name: listdataconnections
  path: /v1/data-connections
- description: POST /v1/data-connections
  method: POST
  name: createdataconnection
  path: /v1/data-connections
- description: Use this endpoint to add or remove a status (including endorsements) from databases, schemas, and tables within a data connection This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails an
  method: PATCH
  name: updatedataconnectionschema
  path: /v1/data-connections/{dataConnectionId}/schema
- description: GET /v1/users/me
  method: GET
  name: me
  path: /v1/users/me
- description: GET /v1/users
  method: GET
  name: listusers
  path: /v1/users
- description: POST /v1/users/{userId}/deactivate
  method: POST
  name: deactivateuser
  path: /v1/users/{userId}/deactivate
- description: GET /v1/collections/{collectionId}
  method: GET
  name: getcollection
  path: /v1/collections/{collectionId}
- description: PATCH /v1/collections/{collectionId}
  method: PATCH
  name: editcollection
  path: /v1/collections/{collectionId}
- description: GET /v1/collections
  method: GET
  name: listcollections
  path: /v1/collections
- description: POST /v1/collections
  method: POST
  name: createcollection
  path: /v1/collections
- description: GET /v1/guides/draft/list
  method: GET
  name: listdraftguides
  path: /v1/guides/draft/list
- description: 'Update or create guide drafts by filePath. Accepts a dictionary mapping file paths to their contents. For each file: - If the guide doesn''t exist, it will be created. - If the guide exists but has no draft, a new draft will be created. - If'
  method: PUT
  name: upsertguidedraft
  path: /v1/guides/draft
- description: Publish all currently drafted guides.
  method: POST
  name: publishguidedrafts
  path: /v1/guides/publish
- description: DELETE /v1/guides/draft/{orgGuideFileId}
  method: DELETE
  name: deleteguidedraft
  path: /v1/guides/draft/{orgGuideFileId}
- description: List all cells Returns cells from the draft version of the project only, not the published app. Requires a project id for filtering. For SQL and CODE cells, includes the source code content.
  method: GET
  name: listcells
  path: /v1/cells
- description: Create a new cell Creates a new cell in the draft version of a project. Currently only CODE and SQL cell types are supported. Requires EDIT_PROJECT_CONTENTS permission on the project.
  method: POST
  name: createcell
  path: /v1/cells
- description: Get a single cell by ID Returns cells from the draft version of the project only, not the published app. Returns the cell details including id, staticId, cellType, label, dataConnectionId, source contents (for CODE and SQL cells), and proje
  method: GET
  name: getcell
  path: /v1/cells/{cellId}
- description: Update a cell's source and/or data connection Updates the source code and/or data connection ID for a cell. For SQL cells, can update SQL source and data connection ID. For code cells, can update code source. Requires EDIT_PROJECT_CONTENTS
  method: PATCH
  name: updatecell
  path: /v1/cells/{cellId}
- description: Delete a cell Permanently deletes a cell from the draft version of a project. Requires EDIT_PROJECT_CONTENTS permission on the project containing the cell.
  method: DELETE
  name: deletecell
  path: /v1/cells/{cellId}
- description: Get the rendered PNG image of a chart cell from the current notebook session by cellId. The "cellId" path parameter should be the cell's ID (scoped to a specific version), as opposed to its staticId (which remains stable across versions). R
  method: GET
  name: getchartimagefromlogic
  path: /v1/cells/{cellId}/image
personas: []
provider_name: Hex
provider_slug: hexa
search_terms:
- post /v1/data-connections
- me
- get /v1/groups
- api
- create an embedded url for a project
- patch /v1/data-connections/{dataconnectionid}
- get /v1/users/me
- getchartimagefromrun
- getcollection
- get /v1/collections
- createpresignedurl
- getgroup
- listcells
- add users to a project or update/remove their project sharing access. for projects, use `can_view` to grant the ui permission labeled "can explore". use `app_only` to grant the ui permission labeled "can view app".
- hexa
- editprojectsharingorgandpublic
- get the status of runs of a project. by default, all run types are returned (api-triggered, scheduled, and publish/refresh runs). use the `runtriggerfilter` parameter to filter to a specific type.
- editprojectsharingusers
- 'update or create guide drafts by filepath. accepts a dictionary mapping file paths to their contents. for each file: - if the guide doesn''t exist, it will be created. - if the guide exists but has no draft, a new draft will be created. - if'
- createcell
- upsertguidedraft
- deletegroup
- publishguidedrafts
- listdraftguides
- given a project id, return the list of warehouse tables queried in the project.
- creategroup
- ingest a semantic project from a zip file. this api endpoint is subject to a maximum of 3 requests per minute.
- editcollection
- listcollections
- getdataconnection
- get /v1/data-connections
- collaboration
- updateproject
- listgroups
- create a new cell creates a new cell in the draft version of a project. currently only code and sql cell types are supported. requires edit_project_contents permission on the project.
- deleteguidedraft
- runproject
- post /v1/groups
- update a cell's source and/or data connection updates the source code and/or data connection id for a cell. for sql cells, can update sql source and data connection id. for code cells, can update code source. requires edit_project_contents
- use this endpoint to add or remove a status (including endorsements) from datasets and views within a semantic project this endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails and no change
- get metadata about a single project.
- editdataconnection
- editprojectsharinggroups
- get /v1/guides/draft/list
- updatecell
- getproject
- get /v1/collections/{collectionid}
- getprojectruns
- update workspace or public-web sharing for a project. for projects, use `can_view` to grant the ui permission labeled "can explore". use `app_only` to grant the ui permission labeled "can view app".
- createcollection
- delete a cell permanently deletes a cell from the draft version of a project. requires edit_project_contents permission on the project containing the cell.
- get /v1/groups/{groupid}
- ingestsemanticproject
- get the status of a project run.
- getchartimagefromlogic
- notebooks
- delete /v1/groups/{groupid}
- get a single cell by id returns cells from the draft version of the project only, not the published app. returns the cell details including id, staticid, celltype, label, dataconnectionid, source contents (for code and sql cells), and proje
- updatedataconnectionschema
- patch /v1/collections/{collectionid}
- listusers
- getqueriedtables
- delete /v1/guides/draft/{orgguidefileid}
- trigger a run of the latest published version of a project. this api endpoint is subject to a maximum of 20 requests per minute and 60 requests per hour.
- createproject
- analytics
- list all viewable projects, sorted by most recently created first.
- getrunstatus
- get the rendered png image of a chart cell from the current notebook session by cellid. the "cellid" path parameter should be the cell's id (scoped to a specific version), as opposed to its staticid (which remains stable across versions). r
- cancel a project run.
- deactivateuser
- createdataconnection
- editgroup
- patch /v1/groups/{groupid}
- add a project to collections or remove it from collections. for projects, use `can_view` to grant the ui permission labeled "can explore". use `app_only` to grant the ui permission labeled "can view app". workspace tokens calling this endpo
- post /v1/users/{userid}/deactivate
- create a new project. creates a new project in the workspace with the specified title. optionally provide a description and project language.
- list all cells returns cells from the draft version of the project only, not the published app. requires a project id for filtering. for sql and code cells, includes the source code content.
- listdataconnections
- deletecell
- updatesemanticproject
- get /v1/data-connections/{dataconnectionid}
- post /v1/collections
- add groups to a project or update/remove their project sharing access. for projects, use `can_view` to grant the ui permission labeled "can explore". use `app_only` to grant the ui permission labeled "can view app".
- use this endpoint to add or remove a status (including endorsements) from databases, schemas, and tables within a data connection this endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails an
- cancelrun
- get the rendered png image of a chart cell from a completed run by staticcellid. the "staticid" path parameter should be the cell's staticid (which remains stable across project versions), as opposed to its cellid (which is scoped to a spec
- listprojects
- data
- editprojectsharingcollections
- use this endpoint to add or remove a status (including endorsements) from a project
- get /v1/users
- getcell
- publish all currently drafted guides.
slug: hexa-capability
source_filename: hexa-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hex API\n  description: API specification for the Hex External API\n  tags:\n  - Hexa\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hexa\n    baseUri: https://app.hex.tech/api\n    description: Hex API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{HEXA_TOKEN}}'\n    resources:\n    - name: v1-embedding-createpresignedurl-projectid\n      path: /v1/embedding/createPresignedUrl/{projectId}\n      operations:\n      - name: createpresignedurl\n        method: POST\n        description: Create an embedded url for a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects\n      path: /v1/projects\n      operations:\n      - name:\
  \ createproject\n        method: POST\n        description: Create a new project. Creates a new project in the workspace with the specified title. Optionally provide\n          a description and project language.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: listprojects\n        method: GET\n        description: List all viewable projects, sorted by most recently created first.\n        inputParameters:\n        - name: includeArchived\n          in: query\n          type: boolean\n        - name: includeComponents\n          in: query\n          type: boolean\n        - name: includeTrashed\n          in: query\n          type: boolean\n        - name: includeSharing\n          in: query\n          type: boolean\n        - name: statuses\n          in: query\n          type: array\n        - name: categories\n          in: query\n          type: array\n        - name: creatorEmail\n      \
  \    in: query\n          type: string\n        - name: ownerEmail\n          in: query\n          type: string\n        - name: collectionId\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortDirection\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid\n      path: /v1/projects/{projectId}\n      operations:\n      - name: getproject\n        method: GET\n        description: Get metadata about a single project.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name:\
  \ includeSharing\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PATCH\n        description: Use this endpoint to add or remove a status (including endorsements) from a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-queriedtables\n      path: /v1/projects/{projectId}/queriedTables\n      operations:\n      - name: getqueriedtables\n        method: GET\n        description: Given a project ID, return the list of warehouse tables queried in the project.\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n        - name: after\n        \
  \  in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-sharing-collections\n      path: /v1/projects/{projectId}/sharing/collections\n      operations:\n      - name: editprojectsharingcollections\n        method: PATCH\n        description: Add a project to collections or remove it from collections. For projects, use `CAN_VIEW` to grant the\n          UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\". Workspace\n          tokens calling this endpo\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-sharing-workspaceandpublic\n      path: /v1/projects/{projectId}/sharing/workspaceAndPublic\n      operations:\n      - name: editprojectsharingorgandpublic\n        method: PATCH\n        description: Update workspace or public-web sharing for a project. For projects, use `CAN_VIEW` to grant the UI permission\n          labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-sharing-groups\n      path: /v1/projects/{projectId}/sharing/groups\n      operations:\n      - name: editprojectsharinggroups\n        method: PATCH\n        description: Add groups to a project\
  \ or update/remove their project sharing access. For projects, use `CAN_VIEW` to\n          grant the UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-sharing-users\n      path: /v1/projects/{projectId}/sharing/users\n      operations:\n      - name: editprojectsharingusers\n        method: PATCH\n        description: Add users to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to\n          grant the UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n        \
  \  required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-semantic-projects-models-semanticprojectid-in\n      path: /v1/semantic-(projects|models)/{semanticProjectId}/ingest\n      operations:\n      - name: ingestsemanticproject\n        method: POST\n        description: Ingest a semantic project from a zip file. This API endpoint is subject to a maximum of 3 requests per\n          minute.\n        inputParameters:\n        - name: semanticProjectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-semantic-projects-models-semanticprojectid\n      path: /v1/semantic-(projects|models)/{semanticProjectId}\n      operations:\n      - name: updatesemanticproject\n        method: PATCH\n        description: Use this endpoint\
  \ to add or remove a status (including endorsements) from datasets and views within a\n          semantic project This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request\n          fails and no change\n        inputParameters:\n        - name: semanticProjectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-runs\n      path: /v1/projects/{projectId}/runs\n      operations:\n      - name: runproject\n        method: POST\n        description: Trigger a run of the latest published version of a project. This API endpoint is subject to a maximum\n          of 20 requests per minute and 60 requests per hour.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: flag-config-override\n\
  \          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getprojectruns\n        method: GET\n        description: Get the status of runs of a project. By default, all run types are returned (API-triggered, scheduled,\n          and publish/refresh runs). Use the `runTriggerFilter` parameter to filter to a specific type.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: string\n        - name: statusFilter\n          in: query\n          type: string\n        - name: runTriggerFilter\n          in: query\n          type: string\n          description: 'Filter by how the run was triggered Valid values: `API`, `SCHEDULED`, `APP_REFRESH`'\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-runs-runid\n      path: /v1/projects/{projectId}/runs/{runId}\n      operations:\n      - name: getrunstatus\n        method: GET\n        description: Get the status of a project run.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: runId\n          in: path\n          type: string\n          required: true\n        - name: enable-expanded-stats\n          in: header\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancelrun\n        method: DELETE\n        description: Cancel a project run.\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: runId\n        \
  \  in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-projects-projectid-runs-runid-cells-staticid-\n      path: /v1/projects/{projectId}/runs/{runId}/cells/{staticId}/image\n      operations:\n      - name: getchartimagefromrun\n        method: GET\n        description: Get the rendered PNG image of a chart cell from a completed run by staticCellId. The \"staticId\" path\n          parameter should be the cell's staticId (which remains stable across project versions), as opposed to its cellId\n          (which is scoped to a spec\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: runId\n          in: path\n          type: string\n          required: true\n        - name: staticId\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-groups-groupid\n      path: /v1/groups/{groupId}\n      operations:\n      - name: getgroup\n        method: GET\n        description: GET /v1/groups/{groupId}\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletegroup\n        method: DELETE\n        description: DELETE /v1/groups/{groupId}\n        inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editgroup\n        method: PATCH\n        description: PATCH /v1/groups/{groupId}\n \
  \       inputParameters:\n        - name: groupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-groups\n      path: /v1/groups\n      operations:\n      - name: listgroups\n        method: GET\n        description: GET /v1/groups\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortDirection\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: creategroup\n        method: POST\n        description: POST /v1/groups\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-data-connections-dataconnectionid\n      path: /v1/data-connections/{dataConnectionId}\n      operations:\n      - name: getdataconnection\n        method: GET\n        description: GET /v1/data-connections/{dataConnectionId}\n        inputParameters:\n        - name: dataConnectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editdataconnection\n        method: PATCH\n        description: PATCH /v1/data-connections/{dataConnectionId}\n        inputParameters:\n        - name: dataConnectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-data-connections\n\
  \      path: /v1/data-connections\n      operations:\n      - name: listdataconnections\n        method: GET\n        description: GET /v1/data-connections\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortDirection\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdataconnection\n        method: POST\n        description: POST /v1/data-connections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-data-connections-dataconnectionid-schema\n      path: /v1/data-connections/{dataConnectionId}/schema\n\
  \      operations:\n      - name: updatedataconnectionschema\n        method: PATCH\n        description: Use this endpoint to add or remove a status (including endorsements) from databases, schemas, and tables\n          within a data connection This endpoint uses atomic semantics - if any update in the batch fails validation, the\n          entire request fails an\n        inputParameters:\n        - name: dataConnectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-users-me\n      path: /v1/users/me\n      operations:\n      - name: me\n        method: GET\n        description: GET /v1/users/me\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-users\n      path: /v1/users\n      operations:\n      - name: listusers\n        method:\
  \ GET\n        description: GET /v1/users\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        - name: sortDirection\n          in: query\n          type: string\n        - name: groupId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-users-userid-deactivate\n      path: /v1/users/{userId}/deactivate\n      operations:\n      - name: deactivateuser\n        method: POST\n        description: POST /v1/users/{userId}/deactivate\n        inputParameters:\n        - name: userId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-collections-collectionid\n      path: /v1/collections/{collectionId}\n      operations:\n      - name: getcollection\n        method: GET\n        description: GET /v1/collections/{collectionId}\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editcollection\n        method: PATCH\n        description: PATCH /v1/collections/{collectionId}\n        inputParameters:\n        - name: collectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-collections\n      path: /v1/collections\n      operations:\n      - name: listcollections\n\
  \        method: GET\n        description: GET /v1/collections\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: string\n        - name: sortBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcollection\n        method: POST\n        description: POST /v1/collections\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-guides-draft-list\n      path: /v1/guides/draft/list\n      operations:\n      - name: listdraftguides\n        method: GET\n        description: GET /v1/guides/draft/list\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n  \
  \      - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        - name: externalSource\n          in: query\n          type: string\n          description: 'A JSON stringified, URI encoded external source locator example: encodeURIComponent(JSON.stringify({\"source\":\"github\",\"owner\":\"my-org\",\"repo\":\"my-repo\",\"baseUrl'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-guides-draft\n      path: /v1/guides/draft\n      operations:\n      - name: upsertguidedraft\n        method: PUT\n        description: 'Update or create guide drafts by filePath. Accepts a dictionary mapping file paths to their contents.\n          For each file: - If the guide doesn''t exist, it will be created. - If the guide exists but has no draft, a new\n          draft will be created. - If'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-guides-publish\n      path: /v1/guides/publish\n      operations:\n      - name: publishguidedrafts\n        method: POST\n        description: Publish all currently drafted guides.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-guides-draft-orgguidefileid\n      path: /v1/guides/draft/{orgGuideFileId}\n      operations:\n      - name: deleteguidedraft\n        method: DELETE\n        description: DELETE /v1/guides/draft/{orgGuideFileId}\n        inputParameters:\n        - name: orgGuideFileId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cells\n      path: /v1/cells\n      operations:\n      - name: listcells\n        method: GET\n        description:\
  \ List all cells Returns cells from the draft version of the project only, not the published app. Requires\n          a project id for filtering. For SQL and CODE cells, includes the source code content.\n        inputParameters:\n        - name: projectId\n          in: query\n          type: string\n          required: true\n        - name: limit\n          in: query\n          type: string\n        - name: after\n          in: query\n          type: string\n        - name: before\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcell\n        method: POST\n        description: Create a new cell Creates a new cell in the draft version of a project. Currently only CODE and SQL cell\n          types are supported. Requires EDIT_PROJECT_CONTENTS permission on the project.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: v1-cells-cellid\n      path: /v1/cells/{cellId}\n      operations:\n      - name: getcell\n        method: GET\n        description: Get a single cell by ID Returns cells from the draft version of the project only, not the published app.\n          Returns the cell details including id, staticId, cellType, label, dataConnectionId, source contents (for CODE and\n          SQL cells), and proje\n        inputParameters:\n        - name: cellId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecell\n        method: PATCH\n        description: 'Update a cell''s source and/or data connection Updates the source code and/or data connection ID for\n          a cell. For SQL cells, can update SQL source and data connection ID. For code cells, can update code source.\
  \ Requires\n          EDIT_PROJECT_CONTENTS '\n        inputParameters:\n        - name: cellId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecell\n        method: DELETE\n        description: Delete a cell Permanently deletes a cell from the draft version of a project. Requires EDIT_PROJECT_CONTENTS\n          permission on the project containing the cell.\n        inputParameters:\n        - name: cellId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-cells-cellid-image\n      path: /v1/cells/{cellId}/image\n      operations:\n      - name: getchartimagefromlogic\n        method: GET\n        description: Get the rendered PNG image of a chart cell from\
  \ the current notebook session by cellId. The \"cellId\"\n          path parameter should be the cell's ID (scoped to a specific version), as opposed to its staticId (which remains\n          stable across versions). R\n        inputParameters:\n        - name: cellId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hexa-rest\n    description: REST adapter for Hex API.\n    resources:\n    - path: /v1/embedding/createPresignedUrl/{projectId}\n      name: createpresignedurl\n      operations:\n      - method: POST\n        name: createpresignedurl\n        description: Create an embedded url for a project\n        call: hexa.createpresignedurl\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n\
  \      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a new project. Creates a new project in the workspace with the specified title. Optionally provide\n          a description and project language.\n        call: hexa.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List all viewable projects, sorted by most recently created first.\n        call: hexa.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get metadata about a single project.\n        call: hexa.getproject\n        with:\n          projectId: rest.projectId\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}\n      name: updateproject\n      operations:\n      - method: PATCH\n        name: updateproject\n        description: Use this endpoint to add or remove a status (including endorsements) from a project\n        call: hexa.updateproject\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/queriedTables\n      name: getqueriedtables\n      operations:\n      - method: GET\n        name: getqueriedtables\n        description: Given a project ID, return the list of warehouse tables queried in the project.\n        call: hexa.getqueriedtables\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/sharing/collections\n      name: editprojectsharingcollections\n      operations:\n      - method:\
  \ PATCH\n        name: editprojectsharingcollections\n        description: Add a project to collections or remove it from collections. For projects, use `CAN_VIEW` to grant the\n          UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\". Workspace\n          tokens calling this endpo\n        call: hexa.editprojectsharingcollections\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/sharing/workspaceAndPublic\n      name: editprojectsharingorgandpublic\n      operations:\n      - method: PATCH\n        name: editprojectsharingorgandpublic\n        description: Update workspace or public-web sharing for a project. For projects, use `CAN_VIEW` to grant the UI permission\n          labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        call: hexa.editprojectsharingorgandpublic\n\
  \        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/sharing/groups\n      name: editprojectsharinggroups\n      operations:\n      - method: PATCH\n        name: editprojectsharinggroups\n        description: Add groups to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to\n          grant the UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        call: hexa.editprojectsharinggroups\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/sharing/users\n      name: editprojectsharingusers\n      operations:\n      - method: PATCH\n        name: editprojectsharingusers\n        description: Add users to a project or update/remove their project sharing access. For projects, use\
  \ `CAN_VIEW` to\n          grant the UI permission labeled \"Can explore\". Use `APP_ONLY` to grant the UI permission labeled \"Can view app\".\n        call: hexa.editprojectsharingusers\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/semantic-(projects|models)/{semanticProjectId}/ingest\n      name: ingestsemanticproject\n      operations:\n      - method: POST\n        name: ingestsemanticproject\n        description: Ingest a semantic project from a zip file. This API endpoint is subject to a maximum of 3 requests per\n          minute.\n        call: hexa.ingestsemanticproject\n        with:\n          semanticProjectId: rest.semanticProjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/semantic-(projects|models)/{semanticProjectId}\n      name: updatesemanticproject\n      operations:\n      - method: PATCH\n        name: updatesemanticproject\n\
  \        description: Use this endpoint to add or remove a status (including endorsements) from datasets and views within a\n          semantic project This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request\n          fails and no change\n        call: hexa.updatesemanticproject\n        with:\n          semanticProjectId: rest.semanticProjectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/runs\n      name: runproject\n      operations:\n      - method: POST\n        name: runproject\n        description: Trigger a run of the latest published version of a project. This API endpoint is subject to a maximum\n          of 20 requests per minute and 60 requests per hour.\n        call: hexa.runproject\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/runs\n      name:\
  \ getprojectruns\n      operations:\n      - method: GET\n        name: getprojectruns\n        description: Get the status of runs of a project. By default, all run types are returned (API-triggered, scheduled,\n          and publish/refresh runs). Use the `runTriggerFilter` parameter to filter to a specific type.\n        call: hexa.getprojectruns\n        with:\n          projectId: rest.projectId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/runs/{runId}\n      name: getrunstatus\n      operations:\n      - method: GET\n        name: getrunstatus\n        description: Get the status of a project run.\n        call: hexa.getrunstatus\n        with:\n          projectId: rest.projectId\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/runs/{runId}\n      name: cancelrun\n      operations:\n      - method: DELETE\n        name: cancelrun\n\
  \        description: Cancel a project run.\n        call: hexa.cancelrun\n        with:\n          projectId: rest.projectId\n          runId: rest.runId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{projectId}/runs/{runId}/cells/{staticId}/image\n      name: getchartimagefromrun\n      operations:\n      - method: GET\n        name: getchartimagefromrun\n        description: Get the rendered PNG image of a chart cell from a completed run by staticCellId. The \"staticId\" path\n          parameter should be the cell's staticId (which remains stable across project versions), as opposed to its cellId\n          (which is scoped to a spec\n        call: hexa.getchartimagefromrun\n        with:\n          project\n\n# --- truncated at 32 KB (67 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hexa/refs/heads/main/capabilities/hexa-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hexa/refs/heads/main/capabilities/hexa-capability.yaml
tags:
- Hexa
- API
tools:
- description: Create an embedded url for a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpresignedurl
- description: Create a new project. Creates a new project in the workspace with the specified title. Optionally provide a description and project language.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: List all viewable projects, sorted by most recently created first.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Get metadata about a single project.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Use this endpoint to add or remove a status (including endorsements) from a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateproject
- description: Given a project ID, return the list of warehouse tables queried in the project.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getqueriedtables
- description: Add a project to collections or remove it from collections. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app". Workspace tokens calling this endpo
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editprojectsharingcollections
- description: Update workspace or public-web sharing for a project. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editprojectsharingorgandpublic
- description: Add groups to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editprojectsharinggroups
- description: Add users to a project or update/remove their project sharing access. For projects, use `CAN_VIEW` to grant the UI permission labeled "Can explore". Use `APP_ONLY` to grant the UI permission labeled "Can view app".
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editprojectsharingusers
- description: Ingest a semantic project from a zip file. This API endpoint is subject to a maximum of 3 requests per minute.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ingestsemanticproject
- description: Use this endpoint to add or remove a status (including endorsements) from datasets and views within a semantic project This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails and no change
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesemanticproject
- description: Trigger a run of the latest published version of a project. This API endpoint is subject to a maximum of 20 requests per minute and 60 requests per hour.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runproject
- description: Get the status of runs of a project. By default, all run types are returned (API-triggered, scheduled, and publish/refresh runs). Use the `runTriggerFilter` parameter to filter to a specific type.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectruns
- description: Get the status of a project run.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrunstatus
- description: Cancel a project run.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancelrun
- description: Get the rendered PNG image of a chart cell from a completed run by staticCellId. The "staticId" path parameter should be the cell's staticId (which remains stable across project versions), as opposed to its cellId (which is scoped to a spec
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchartimagefromrun
- description: GET /v1/groups/{groupId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgroup
- description: DELETE /v1/groups/{groupId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegroup
- description: PATCH /v1/groups/{groupId}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editgroup
- description: GET /v1/groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listgroups
- description: POST /v1/groups
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creategroup
- description: GET /v1/data-connections/{dataConnectionId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataconnection
- description: PATCH /v1/data-connections/{dataConnectionId}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editdataconnection
- description: GET /v1/data-connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdataconnections
- description: POST /v1/data-connections
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdataconnection
- description: Use this endpoint to add or remove a status (including endorsements) from databases, schemas, and tables within a data connection This endpoint uses atomic semantics - if any update in the batch fails validation, the entire request fails an
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedataconnectionschema
- description: GET /v1/users/me
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: me
- description: GET /v1/users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: POST /v1/users/{userId}/deactivate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateuser
- description: GET /v1/collections/{collectionId}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcollection
- description: PATCH /v1/collections/{collectionId}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editcollection
- description: GET /v1/collections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcollections
- description: POST /v1/collections
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcollection
- description: GET /v1/guides/draft/list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdraftguides
- description: 'Update or create guide drafts by filePath. Accepts a dictionary mapping file paths to their contents. For each file: - If the guide doesn''t exist, it will be created. - If the guide exists but has no draft, a new draft will be created. - If'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: upsertguidedraft
- description: Publish all currently drafted guides.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishguidedrafts
- description: DELETE /v1/guides/draft/{orgGuideFileId}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteguidedraft
- description: List all cells Returns cells from the draft version of the project only, not the published app. Requires a project id for filtering. For SQL and CODE cells, includes the source code content.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcells
- description: Create a new cell Creates a new cell in the draft version of a project. Currently only CODE and SQL cell types are supported. Requires EDIT_PROJECT_CONTENTS permission on the project.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcell
- description: Get a single cell by ID Returns cells from the draft version of the project only, not the published app. Returns the cell details including id, staticId, cellType, label, dataConnectionId, source contents (for CODE and SQL cells), and proje
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcell
- description: Update a cell's source and/or data connection Updates the source code and/or data connection ID for a cell. For SQL cells, can update SQL source and data connection ID. For code cells, can update code source. Requires EDIT_PROJECT_CONTENTS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecell
- description: Delete a cell Permanently deletes a cell from the draft version of a project. Requires EDIT_PROJECT_CONTENTS permission on the project containing the cell.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecell
- description: Get the rendered PNG image of a chart cell from the current notebook session by cellId. The "cellId" path parameter should be the cell's ID (scoped to a specific version), as opposed to its staticId (which remains stable across versions). R
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchartimagefromlogic
---
