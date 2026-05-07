---
categories: []
consumed_apis: []
description: The n8n public REST API provides programmatic access to n8n instance resources including workflows, executions, credentials, users, tags, variables, projects, source control, audit, data tables, community packages, folders, and insights.
layout: capability
name: n8n Public API
operations:
- description: Generate an audit
  method: POST
  name: generateaudit
  path: /audit
- description: Create a credential
  method: POST
  name: createcredential
  path: /credentials
- description: Delete credential by ID
  method: DELETE
  name: deletecredential
  path: /credentials/{id}
- description: Test a credential
  method: POST
  name: testcredential
  path: /credentials/{id}/test
- description: Show credential data schema
  method: GET
  name: getcredentialschema
  path: /credentials/schema/{credentialTypeName}
- description: Transfer a credential to another project
  method: PUT
  name: transfercredential
  path: /credentials/{id}/transfer
- description: Retrieve all executions
  method: GET
  name: getexecutions
  path: /executions
- description: Retrieve an execution
  method: GET
  name: getexecution
  path: /executions/{id}
- description: Delete an execution
  method: DELETE
  name: deleteexecution
  path: /executions/{id}
- description: Retry an execution
  method: POST
  name: retryexecution
  path: /executions/{id}/retry
- description: Stop an execution
  method: POST
  name: stopexecution
  path: /executions/{id}/stop
- description: Stop multiple executions
  method: POST
  name: stopexecutions
  path: /executions/stop
- description: Update tags on an execution
  method: PUT
  name: updateexecutiontags
  path: /executions/{id}/tags
- description: Create a tag
  method: POST
  name: createtag
  path: /tags
- description: Retrieve all tags
  method: GET
  name: gettags
  path: /tags
- description: Retrieves a tag
  method: GET
  name: gettag
  path: /tags/{id}
- description: Delete a tag
  method: DELETE
  name: deletetag
  path: /tags/{id}
- description: Update a tag
  method: PUT
  name: updatetag
  path: /tags/{id}
- description: Create a workflow
  method: POST
  name: createworkflow
  path: /workflows
- description: Retrieve all workflows
  method: GET
  name: getworkflows
  path: /workflows
- description: Retrieves a workflow
  method: GET
  name: getworkflow
  path: /workflows/{id}
- description: Delete a workflow
  method: DELETE
  name: deleteworkflow
  path: /workflows/{id}
- description: Update a workflow
  method: PUT
  name: updateworkflow
  path: /workflows/{id}
- description: Retrieves a specific version of a workflow
  method: GET
  name: getworkflowversion
  path: /workflows/{id}/{versionId}
- description: Activate a workflow
  method: POST
  name: activateworkflow
  path: /workflows/{id}/activate
- description: Deactivate a workflow
  method: POST
  name: deactivateworkflow
  path: /workflows/{id}/deactivate
- description: Archive a workflow
  method: POST
  name: archiveworkflow
  path: /workflows/{id}/archive
- description: Unarchive a workflow
  method: POST
  name: unarchiveworkflow
  path: /workflows/{id}/unarchive
- description: Transfer a workflow to another project
  method: PUT
  name: transferworkflow
  path: /workflows/{id}/transfer
- description: Get workflow tags
  method: GET
  name: getworkflowtags
  path: /workflows/{id}/tags
- description: Update tags of a workflow
  method: PUT
  name: updateworkflowtags
  path: /workflows/{id}/tags
- description: Retrieve all users
  method: GET
  name: getusers
  path: /users
- description: Create multiple users
  method: POST
  name: createusers
  path: /users
- description: Get user by ID/Email
  method: GET
  name: getuser
  path: /users/{id}
- description: Delete a user
  method: DELETE
  name: deleteuser
  path: /users/{id}
- description: Change a user's global role
  method: PATCH
  name: changeuserrole
  path: /users/{id}/role
- description: Pull changes from the remote repository
  method: POST
  name: sourcecontrolpull
  path: /source-control/pull
- description: Create a variable
  method: POST
  name: createvariable
  path: /variables
- description: Retrieve variables
  method: GET
  name: getvariables
  path: /variables
- description: Delete a variable
  method: DELETE
  name: deletevariable
  path: /variables/{id}
- description: Update a variable
  method: PUT
  name: updatevariable
  path: /variables/{id}
- description: List all data tables
  method: GET
  name: listdatatables
  path: /data-tables
- description: Create a data table
  method: POST
  name: createdatatable
  path: /data-tables
- description: Get a data table
  method: GET
  name: getdatatable
  path: /data-tables/{dataTableId}
- description: Delete a data table
  method: DELETE
  name: deletedatatable
  path: /data-tables/{dataTableId}
- description: Update a data table
  method: PATCH
  name: updatedatatable
  path: /data-tables/{dataTableId}
- description: List rows in a data table
  method: GET
  name: listdatatablerows
  path: /data-tables/{dataTableId}/rows
- description: Insert rows into a data table
  method: POST
  name: insertdatatablerows
  path: /data-tables/{dataTableId}/rows
- description: Update rows in a data table
  method: POST
  name: updatedatatablerows
  path: /data-tables/{dataTableId}/rows/update
- description: Upsert rows in a data table
  method: POST
  name: upsertdatatablerows
  path: /data-tables/{dataTableId}/rows/upsert
- description: Delete rows in a data table
  method: POST
  name: deletedatatablerows
  path: /data-tables/{dataTableId}/rows/delete
- description: List columns in a data table
  method: GET
  name: listdatatablecolumns
  path: /data-tables/{dataTableId}/columns
- description: Add a column to a data table
  method: POST
  name: adddatatablecolumn
  path: /data-tables/{dataTableId}/columns
- description: Delete a column from a data table
  method: DELETE
  name: deletedatatablecolumn
  path: /data-tables/{dataTableId}/columns/{columnId}
- description: Create a project
  method: POST
  name: createproject
  path: /projects
- description: Retrieve projects
  method: GET
  name: getprojects
  path: /projects
- description: Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{projectId}
- description: Update a project
  method: PUT
  name: updateproject
  path: /projects/{projectId}
- description: Get project users
  method: GET
  name: getprojectusers
  path: /projects/{projectId}/users
- description: Add users to a project
  method: POST
  name: addprojectusers
  path: /projects/{projectId}/users
personas: []
provider_name: N8n
provider_slug: n8n
search_terms:
- updateexecutiontags
- archiveworkflow
- update tags of a workflow
- api
- getworkflowtags
- createworkflow
- delete a user
- getprojects
- delete a data table
- deletetag
- getexecutions
- retrieves a specific version of a workflow
- deleteexecution
- add users to a project
- get user by id/email
- deleteuser
- createdatatable
- retrieve all users
- agents
- retrieve variables
- deleteproject
- getexecution
- getworkflowversion
- addprojectusers
- gettag
- insert rows into a data table
- listdatatablecolumns
- create a variable
- update a workflow
- activateworkflow
- deletedatatablerows
- integrations
- sourcecontrolpull
- deletevariable
- delete a workflow
- stop an execution
- adddatatablecolumn
- listdatatablerows
- create multiple users
- gettags
- insertdatatablerows
- pull changes from the remote repository
- get a data table
- n8n
- create a project
- upsert rows in a data table
- deletedatatable
- list rows in a data table
- updateworkflowtags
- upsertdatatablerows
- artificial intelligence
- create a credential
- updateproject
- stopexecutions
- list columns in a data table
- update a variable
- getworkflows
- generate an audit
- create a data table
- list all data tables
- createvariable
- update a project
- transferworkflow
- stopexecution
- transfer a workflow to another project
- getcredentialschema
- update a tag
- update a data table
- update tags on an execution
- updatetag
- create a tag
- transfer a credential to another project
- update rows in a data table
- delete a tag
- retrieve projects
- retrieve all executions
- retrieves a tag
- delete a variable
- listdatatables
- activate a workflow
- retrieves a workflow
- deletedatatablecolumn
- show credential data schema
- change a user's global role
- retrieve all workflows
- delete a column from a data table
- delete an execution
- unarchiveworkflow
- unarchive a workflow
- getprojectusers
- deactivateworkflow
- createtag
- stop multiple executions
- testcredential
- createusers
- retryexecution
- delete a project
- createproject
- archive a workflow
- updatedatatable
- generateaudit
- retrieve all tags
- add a column to a data table
- getusers
- updatedatatablerows
- deleteworkflow
- createcredential
- updatevariable
- delete rows in a data table
- getvariables
- updateworkflow
- changeuserrole
- getuser
- getworkflow
- create a workflow
- get project users
- retry an execution
- deletecredential
- delete credential by id
- transfercredential
- retrieve an execution
- test a credential
- get workflow tags
- deactivate a workflow
- getdatatable
slug: n8n-capability
source_filename: n8n-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: n8n Public API\n  description: The n8n public REST API provides programmatic access to n8n instance resources including workflows, executions,\n    credentials, users, tags, variables, projects, source control, audit, data tables, community packages, folders, and insights.\n  tags:\n  - N8n\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: n8n\n    baseUri: https://app.n8n.cloud/api/v1\n    description: n8n Public API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-N8N-API-KEY\n      value: '{{N8N_TOKEN}}'\n    resources:\n    - name: audit\n      path: /audit\n      operations:\n      - name: generateaudit\n        method: POST\n        description: Generate an audit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials\n      path: /credentials\n\
  \      operations:\n      - name: createcredential\n        method: POST\n        description: Create a credential\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-id\n      path: /credentials/{id}\n      operations:\n      - name: deletecredential\n        method: DELETE\n        description: Delete credential by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The credential ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-id-test\n      path: /credentials/{id}/test\n      operations:\n      - name: testcredential\n        method: POST\n        description: Test a credential\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-schema-credentialtypename\n      path: /credentials/schema/{credentialTypeName}\n      operations:\n      - name: getcredentialschema\n        method: GET\n        description: Show credential data schema\n        inputParameters:\n        - name: credentialTypeName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: credentials-id-transfer\n      path: /credentials/{id}/transfer\n      operations:\n      - name: transfercredential\n        method: PUT\n        description: Transfer a credential to another project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: executions\n      path: /executions\n      operations:\n      - name: getexecutions\n        method: GET\n        description: Retrieve all executions\n        inputParameters:\n        - name: includeData\n          in: query\n          type: boolean\n        - name: status\n          in: query\n          type: string\n        - name: workflowId\n          in: query\n          type: string\n        - name: projectId\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: number\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions-id\n      path: /executions/{id}\n      operations:\n      - name: getexecution\n        method: GET\n        description: Retrieve an execution\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: number\n          required: true\n        - name: includeData\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteexecution\n        method: DELETE\n        description: Delete an execution\n        inputParameters:\n        - name: id\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions-id-retry\n      path: /executions/{id}/retry\n      operations:\n      - name: retryexecution\n        method: POST\n        description: Retry an execution\n        inputParameters:\n        - name: id\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: executions-id-stop\n      path: /executions/{id}/stop\n      operations:\n      - name: stopexecution\n        method: POST\n        description: Stop an execution\n        inputParameters:\n        - name: id\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions-stop\n      path: /executions/stop\n      operations:\n      - name: stopexecutions\n        method: POST\n        description: Stop multiple executions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: executions-id-tags\n      path: /executions/{id}/tags\n      operations:\n      - name: updateexecutiontags\n        method: PUT\n        description: Update tags on an execution\n        inputParameters:\n  \
  \      - name: id\n          in: path\n          type: number\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags\n      path: /tags\n      operations:\n      - name: createtag\n        method: POST\n        description: Create a tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: gettags\n        method: GET\n        description: Retrieve all tags\n        inputParameters:\n        - name: limit\n          in: query\n          type: number\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tags-id\n      path: /tags/{id}\n      operations:\n      - name: gettag\n        method: GET\n        description: Retrieves a tag\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetag\n        method: DELETE\n        description: Delete a tag\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetag\n        method: PUT\n        description: Update a tag\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows\n      path: /workflows\n      operations:\n      - name: createworkflow\n        method:\
  \ POST\n        description: Create a workflow\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getworkflows\n        method: GET\n        description: Retrieve all workflows\n        inputParameters:\n        - name: active\n          in: query\n          type: boolean\n        - name: tags\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: string\n        - name: projectId\n          in: query\n          type: string\n        - name: excludePinnedData\n          in: query\n          type: boolean\n        - name: limit\n          in: query\n          type: number\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id\n      path: /workflows/{id}\n      operations:\n      - name:\
  \ getworkflow\n        method: GET\n        description: Retrieves a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: excludePinnedData\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteworkflow\n        method: DELETE\n        description: Delete a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflow\n        method: PUT\n        description: Update a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-versionid\n      path: /workflows/{id}/{versionId}\n      operations:\n      - name: getworkflowversion\n        method: GET\n        description: Retrieves a specific version of a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: versionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-activate\n      path: /workflows/{id}/activate\n      operations:\n      - name: activateworkflow\n        method: POST\n        description: Activate a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: workflows-id-deactivate\n      path: /workflows/{id}/deactivate\n      operations:\n      - name: deactivateworkflow\n        method: POST\n        description: Deactivate a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-archive\n      path: /workflows/{id}/archive\n      operations:\n      - name: archiveworkflow\n        method: POST\n        description: Archive a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-unarchive\n      path: /workflows/{id}/unarchive\n   \
  \   operations:\n      - name: unarchiveworkflow\n        method: POST\n        description: Unarchive a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-transfer\n      path: /workflows/{id}/transfer\n      operations:\n      - name: transferworkflow\n        method: PUT\n        description: Transfer a workflow to another project\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows-id-tags\n      path: /workflows/{id}/tags\n      operations:\n      - name: getworkflowtags\n        method: GET\n        description: Get workflow tags\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkflowtags\n        method: PUT\n        description: Update tags of a workflow\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: getusers\n        method: GET\n        description: Retrieve all users\n        inputParameters:\n        - name: limit\n          in: query\n          type: number\n        - name: cursor\n          in: query\n          type: string\n        - name: includeRole\n          in: query\n          type: boolean\n        - name: projectId\n          in: query\n     \
  \     type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusers\n        method: POST\n        description: Create multiple users\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id\n      path: /users/{id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get user by ID/Email\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: includeRole\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: id\n          in: path\n         \
  \ type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-id-role\n      path: /users/{id}/role\n      operations:\n      - name: changeuserrole\n        method: PATCH\n        description: Change a user's global role\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: source-control-pull\n      path: /source-control/pull\n      operations:\n      - name: sourcecontrolpull\n        method: POST\n        description: Pull changes from the remote repository\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables\n      path: /variables\n      operations:\n      - name:\
  \ createvariable\n        method: POST\n        description: Create a variable\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getvariables\n        method: GET\n        description: Retrieve variables\n        inputParameters:\n        - name: limit\n          in: query\n          type: number\n        - name: cursor\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: variables-id\n      path: /variables/{id}\n      operations:\n      - name: deletevariable\n        method: DELETE\n        description: Delete a variable\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \     - name: updatevariable\n        method: PUT\n        description: Update a variable\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables\n      path: /data-tables\n      operations:\n      - name: listdatatables\n        method: GET\n        description: List all data tables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdatatable\n        method: POST\n        description: Create a data table\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid\n      path: /data-tables/{dataTableId}\n      operations:\n      - name: getdatatable\n        method: GET\n       \
  \ description: Get a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedatatable\n        method: DELETE\n        description: Delete a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedatatable\n        method: PATCH\n        description: Update a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid-rows\n\
  \      path: /data-tables/{dataTableId}/rows\n      operations:\n      - name: listdatatablerows\n        method: GET\n        description: List rows in a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: insertdatatablerows\n        method: POST\n        description: Insert rows into a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid-rows-update\n      path: /data-tables/{dataTableId}/rows/update\n      operations:\n      - name: updatedatatablerows\n        method: POST\n        description: Update rows in a data\
  \ table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid-rows-upsert\n      path: /data-tables/{dataTableId}/rows/upsert\n      operations:\n      - name: upsertdatatablerows\n        method: POST\n        description: Upsert rows in a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid-rows-delete\n      path: /data-tables/{dataTableId}/rows/delete\n      operations:\n      - name: deletedatatablerows\n        method: POST\n        description: Delete rows in a data table\n        inputParameters:\n      \
  \  - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: data-tables-datatableid-columns\n      path: /data-tables/{dataTableId}/columns\n      operations:\n      - name: listdatatablecolumns\n        method: GET\n        description: List columns in a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: adddatatablecolumn\n        method: POST\n        description: Add a column to a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: data-tables-datatableid-columns-columnid\n      path: /data-tables/{dataTableId}/columns/{columnId}\n      operations:\n      - name: deletedatatablecolumn\n        method: DELETE\n        description: Delete a column from a data table\n        inputParameters:\n        - name: dataTableId\n          in: path\n          type: string\n          required: true\n        - name: columnId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      operations:\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getprojects\n        method: GET\n        description: Retrieve\
  \ projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid\n      path: /projects/{projectId}\n      operations:\n      - name: deleteproject\n        method: DELETE\n        description: Delete a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateproject\n        method: PUT\n        description: Update a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-users\n      path: /projects/{projectId}/users\n      operations:\n\
  \      - name: getprojectusers\n        method: GET\n        description: Get project users\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addprojectusers\n        method: POST\n        description: Add users to a project\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: n8n-rest\n    description: REST adapter for n8n Public API.\n    resources:\n    - path: /audit\n      name: generateaudit\n      operations:\n      - method: POST\n        name: generateaudit\n        description: Generate an audit\n        call: n8n.generateaudit\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials\n      name: createcredential\n      operations:\n      - method: POST\n        name: createcredential\n        description: Create a credential\n        call: n8n.createcredential\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{id}\n      name: deletecredential\n      operations:\n      - method: DELETE\n        name: deletecredential\n        description: Delete credential by ID\n        call: n8n.deletecredential\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{id}/test\n      name: testcredential\n      operations:\n      - method: POST\n        name: testcredential\n        description: Test a credential\n        call: n8n.testcredential\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /credentials/schema/{credentialTypeName}\n      name: getcredentialschema\n      operations:\n      - method: GET\n        name: getcredentialschema\n        description: Show credential data schema\n        call: n8n.getcredentialschema\n        with:\n          credentialTypeName: rest.credentialTypeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /credentials/{id}/transfer\n      name: transfercredential\n      operations:\n      - method: PUT\n        name: transfercredential\n        description: Transfer a credential to another project\n        call: n8n.transfercredential\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /executions\n      name: getexecutions\n      operations:\n      - method: GET\n        name: getexecutions\n        description: Retrieve all executions\n        call: n8n.getexecutions\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /executions/{id}\n      name: getexecution\n      operations:\n      - method: GET\n        name: getexecution\n        description: Retrieve an execution\n        call: n8n.getexecution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /executions/{id}\n      name: deleteexecution\n      operations:\n      - method: DELETE\n        name: deleteexecution\n        description: Delete an execution\n        call: n8n.deleteexecution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /executions/{id}/retry\n      name: retryexecution\n      operations:\n      - method: POST\n        name: retryexecution\n        description: Retry an execution\n        call: n8n.retryexecution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /executions/{id}/stop\n      name: stopexecution\n      operations:\n      - method: POST\n        name: stopexecution\n        description: Stop an execution\n        call: n8n.stopexecution\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /executions/stop\n      name: stopexecutions\n      operations:\n      - method: POST\n        name: stopexecutions\n        description: Stop multiple executions\n        call: n8n.stopexecutions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /executions/{id}/tags\n      name: updateexecutiontags\n      operations:\n      - method: PUT\n        name: updateexecutiontags\n        description: Update tags on an execution\n        call: n8n.updateexecutiontags\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags\n      name: createtag\n      operations:\n   \
  \   - method: POST\n        name: createtag\n        description: Create a tag\n        call: n8n.createtag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags\n      name: gettags\n      operations:\n      - method: GET\n        name: gettags\n        description: Retrieve all tags\n        call: n8n.gettags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{id}\n      name: gettag\n      operations:\n      - method: GET\n        name: gettag\n        description: Retrieves a tag\n        call: n8n.gettag\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tags/{id}\n      name: deletetag\n      operations:\n      - method: DELETE\n        name: deletetag\n        description: Delete a tag\n        call: n8n.deletetag\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /tags/{id}\n      name: updatetag\n      operations:\n      - method: PUT\n        name: updatetag\n        description: Update a tag\n        call: n8n.updatetag\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows\n      name: createworkflow\n      operations:\n      - method: POST\n        name: createworkflow\n        description: Create a workflow\n        call: n8n.createworkflow\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows\n      name: getworkflows\n      operations:\n      - method: GET\n        name: getworkflows\n        description: Retrieve all workflows\n        call: n8n.getworkflows\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}\n      name: getworkflow\n      operations:\n      - method: GET\n        name: getworkflow\n        description: Retrieves a workflow\n      \
  \  call: n8n.getworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}\n      name: deleteworkflow\n      operations:\n      - method: DELETE\n        name: deleteworkflow\n        description: Delete a workflow\n        call: n8n.deleteworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}\n      name: updateworkflow\n      operations:\n      - method: PUT\n        name: updateworkflow\n        description: Update a workflow\n        call: n8n.updateworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/{versionId}\n      name: getworkflowversion\n      operations:\n      - method: GET\n        name: getworkflowversion\n        description: Retrieves a specific version of a workflow\n        call: n8n.getworkflowversion\n\
  \        with:\n          id: rest.id\n          versionId: rest.versionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/activate\n      name: activateworkflow\n      operations:\n      - method: POST\n        name: activateworkflow\n        description: Activate a workflow\n        call: n8n.activateworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/deactivate\n      name: deactivateworkflow\n      operations:\n      - method: POST\n        name: deactivateworkflow\n        description: Deactivate a workflow\n        call: n8n.deactivateworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/archive\n      name: archiveworkflow\n      operations:\n      - method: POST\n        name: archiveworkflow\n        description: Archive a workflow\n\
  \        call: n8n.archiveworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/unarchive\n      name: unarchiveworkflow\n      operations:\n      - method: POST\n        name: unarchiveworkflow\n        description: Unarchive a workflow\n        call: n8n.unarchiveworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/transfer\n      name: transferworkflow\n      operations:\n      - method: PUT\n        name: transferworkflow\n        description: Transfer a workflow to another project\n        call: n8n.transferworkflow\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workflows/{id}/tags\n      name: getworkflowtags\n      operations:\n      - method: GET\n        name: getwor\n\n# --- truncated at 32 KB (65 KB total) ---\n\
  # Full source: https://raw.githubusercontent.com/api-evangelist/n8n/refs/heads/main/capabilities/n8n-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/n8n/refs/heads/main/capabilities/n8n-capability.yaml
tags:
- N8n
- API
tools:
- description: Generate an audit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateaudit
- description: Create a credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcredential
- description: Delete credential by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecredential
- description: Test a credential
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testcredential
- description: Show credential data schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredentialschema
- description: Transfer a credential to another project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: transfercredential
- description: Retrieve all executions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecutions
- description: Retrieve an execution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexecution
- description: Delete an execution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteexecution
- description: Retry an execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retryexecution
- description: Stop an execution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopexecution
- description: Stop multiple executions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stopexecutions
- description: Update tags on an execution
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateexecutiontags
- description: Create a tag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtag
- description: Retrieve all tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettags
- description: Retrieves a tag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettag
- description: Delete a tag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetag
- description: Update a tag
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetag
- description: Create a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkflow
- description: Retrieve all workflows
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflows
- description: Retrieves a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflow
- description: Delete a workflow
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkflow
- description: Update a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkflow
- description: Retrieves a specific version of a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowversion
- description: Activate a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: activateworkflow
- description: Deactivate a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deactivateworkflow
- description: Archive a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: archiveworkflow
- description: Unarchive a workflow
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unarchiveworkflow
- description: Transfer a workflow to another project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: transferworkflow
- description: Get workflow tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkflowtags
- description: Update tags of a workflow
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkflowtags
- description: Retrieve all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusers
- description: Create multiple users
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusers
- description: Get user by ID/Email
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: Change a user's global role
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: changeuserrole
- description: Pull changes from the remote repository
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sourcecontrolpull
- description: Create a variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvariable
- description: Retrieve variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvariables
- description: Delete a variable
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevariable
- description: Update a variable
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevariable
- description: List all data tables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatatables
- description: Create a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatatable
- description: Get a data table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatatable
- description: Delete a data table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatatable
- description: Update a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedatatable
- description: List rows in a data table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatatablerows
- description: Insert rows into a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: insertdatatablerows
- description: Update rows in a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedatatablerows
- description: Upsert rows in a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: upsertdatatablerows
- description: Delete rows in a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletedatatablerows
- description: List columns in a data table
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdatatablecolumns
- description: Add a column to a data table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: adddatatablecolumn
- description: Delete a column from a data table
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedatatablecolumn
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Retrieve projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojects
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Get project users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectusers
- description: Add users to a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addprojectusers
---
