---
categories: []
consumed_apis: []
description: The Basecamp API is a REST API that provides programmatic access to Basecamp's project management and team communication platform. It enables developers to manage projects, to-do lists, messages, documents, schedules, campfires, uploads, card tables, templates, and team members across Basecamp accounts. The API uses OAuth 2.0 for authentication and returns JSON responses, with all requests scoped to an account ID in the base URL path. Resources include projects, people, to-dos, message boards, documents, card tables, campfires, questionnaires, and webhooks, covering the full breadth of Basecam
layout: capability
name: Basecamp API
operations:
- description: List projects
  method: GET
  name: listprojects
  path: /projects.json
- description: Create a project
  method: POST
  name: createproject
  path: /projects.json
- description: Get a project
  method: GET
  name: getproject
  path: /projects/{projectId}.json
- description: Update a project
  method: PUT
  name: updateproject
  path: /projects/{projectId}.json
- description: Delete a project
  method: DELETE
  name: deleteproject
  path: /projects/{projectId}.json
- description: List all people
  method: GET
  name: listpeople
  path: /people.json
- description: List people on a project
  method: GET
  name: listprojectpeople
  path: /projects/{projectId}/people.json
- description: Update project access
  method: PUT
  name: updateprojectaccess
  path: /projects/{projectId}/people/users.json
- description: List pingable people
  method: GET
  name: listpingablepeople
  path: /circles/people.json
- description: Get a person
  method: GET
  name: getperson
  path: /people/{personId}.json
- description: Get my profile
  method: GET
  name: getmyprofile
  path: /my/profile.json
- description: Update my profile
  method: PUT
  name: updatemyprofile
  path: /my/profile.json
- description: List templates
  method: GET
  name: listtemplates
  path: /templates.json
- description: Create a template
  method: POST
  name: createtemplate
  path: /templates.json
- description: Get a template
  method: GET
  name: gettemplate
  path: /templates/{templateId}.json
- description: Update a template
  method: PUT
  name: updatetemplate
  path: /templates/{templateId}.json
- description: Delete a template
  method: DELETE
  name: deletetemplate
  path: /templates/{templateId}.json
- description: Create project from template
  method: POST
  name: createprojectfromtemplate
  path: /templates/{templateId}/project_constructions.json
- description: Get project construction status
  method: GET
  name: getprojectconstruction
  path: /templates/{templateId}/project_constructions/{constructionId}.json
- description: List recordings
  method: GET
  name: listrecordings
  path: /projects/recordings.json
- description: Trash a recording
  method: PUT
  name: trashrecording
  path: /recordings/{recordingId}/status/trashed.json
- description: Archive a recording
  method: PUT
  name: archiverecording
  path: /recordings/{recordingId}/status/archived.json
- description: Unarchive a recording
  method: PUT
  name: unarchiverecording
  path: /recordings/{recordingId}/status/active.json
- description: List messages
  method: GET
  name: listmessages
  path: /message_boards/{messageBoardId}/messages.json
- description: Create a message
  method: POST
  name: createmessage
  path: /message_boards/{messageBoardId}/messages.json
- description: Get a message
  method: GET
  name: getmessage
  path: /messages/{messageId}.json
- description: Update a message
  method: PUT
  name: updatemessage
  path: /messages/{messageId}.json
- description: List comments
  method: GET
  name: listcomments
  path: /recordings/{recordingId}/comments.json
- description: Create a comment
  method: POST
  name: createcomment
  path: /recordings/{recordingId}/comments.json
- description: Get a comment
  method: GET
  name: getcomment
  path: /comments/{commentId}.json
- description: Update a comment
  method: PUT
  name: updatecomment
  path: /comments/{commentId}.json
- description: List to-do lists
  method: GET
  name: listtodolists
  path: /todosets/{todosetId}/todolists.json
- description: Create a to-do list
  method: POST
  name: createtodolist
  path: /todosets/{todosetId}/todolists.json
- description: Get a to-do list
  method: GET
  name: gettodolist
  path: /todolists/{todolistId}.json
- description: Update a to-do list
  method: PUT
  name: updatetodolist
  path: /todolists/{todolistId}.json
- description: List to-dos
  method: GET
  name: listtodos
  path: /todolists/{todolistId}/todos.json
- description: Create a to-do
  method: POST
  name: createtodo
  path: /todolists/{todolistId}/todos.json
- description: Get a to-do
  method: GET
  name: gettodo
  path: /todos/{todoId}.json
- description: Update a to-do
  method: PUT
  name: updatetodo
  path: /todos/{todoId}.json
- description: Complete a to-do
  method: POST
  name: completetodo
  path: /todos/{todoId}/completion.json
- description: Uncomplete a to-do
  method: DELETE
  name: uncompletetodo
  path: /todos/{todoId}/completion.json
- description: Reposition a to-do
  method: PUT
  name: repositiontodo
  path: /todos/{todoId}/position.json
- description: Get a schedule
  method: GET
  name: getschedule
  path: /schedules/{scheduleId}.json
- description: Update a schedule
  method: PUT
  name: updateschedule
  path: /schedules/{scheduleId}.json
- description: List schedule entries
  method: GET
  name: listscheduleentries
  path: /schedules/{scheduleId}/entries.json
- description: Create a schedule entry
  method: POST
  name: createscheduleentry
  path: /schedules/{scheduleId}/entries.json
- description: Get a schedule entry
  method: GET
  name: getscheduleentry
  path: /schedule_entries/{entryId}.json
- description: Update a schedule entry
  method: PUT
  name: updatescheduleentry
  path: /schedule_entries/{entryId}.json
- description: List documents
  method: GET
  name: listdocuments
  path: /vaults/{vaultId}/documents.json
- description: Create a document
  method: POST
  name: createdocument
  path: /vaults/{vaultId}/documents.json
- description: Get a document
  method: GET
  name: getdocument
  path: /documents/{documentId}.json
- description: Update a document
  method: PUT
  name: updatedocument
  path: /documents/{documentId}.json
- description: List uploads
  method: GET
  name: listuploads
  path: /vaults/{vaultId}/uploads.json
- description: Create an upload
  method: POST
  name: createupload
  path: /vaults/{vaultId}/uploads.json
- description: Get an upload
  method: GET
  name: getupload
  path: /uploads/{uploadId}.json
- description: Update an upload
  method: PUT
  name: updateupload
  path: /uploads/{uploadId}.json
- description: List campfires
  method: GET
  name: listcampfires
  path: /chats.json
- description: Get a campfire
  method: GET
  name: getcampfire
  path: /chats/{campfireId}.json
- description: List campfire lines
  method: GET
  name: listcampfirelines
  path: /chats/{campfireId}/lines.json
- description: Create a campfire line
  method: POST
  name: createcampfireline
  path: /chats/{campfireId}/lines.json
personas: []
provider_name: Basecamp
provider_slug: basecamp
search_terms:
- developer integrating basecamp into custom workflows and tools
- createdocument
- get a campfire
- updatemessage
- update a template
- update a schedule
- deleteproject
- listuploads
- get a schedule
- update a to-do list
- Developer
- getdocument
- createprojectfromtemplate
- createscheduleentry
- listpingablepeople
- gettemplate
- gettodolist
- delete a template
- getscheduleentry
- trashrecording
- getproject
- list to-dos
- Team Member
- create a comment
- create a schedule entry
- api
- updateupload
- update my profile
- list projects
- update a document
- createmessage
- updateprojectaccess
- updatetodolist
- create a message
- createproject
- update a to-do
- create a document
- list messages
- team communication
- get my profile
- unarchive a recording
- getcomment
- get a to-do
- completetodo
- complete a to-do
- updateproject
- getschedule
- listtodolists
- listtodos
- uncomplete a to-do
- project management
- get project construction status
- updatetodo
- listprojects
- getmyprofile
- basecamp
- archive a recording
- updatecomment
- update an upload
- update a schedule entry
- get an upload
- listcampfirelines
- create a template
- get a project
- get a to-do list
- manager overseeing project progress, tasks, and team communication
- deletetemplate
- getmessage
- updatedocument
- get a person
- list people on a project
- getcampfire
- listtemplates
- reposition a to-do
- listcomments
- list documents
- list templates
- updatemyprofile
- create a campfire line
- get a document
- createupload
- update a comment
- listpeople
- list pingable people
- archiverecording
- uncompletetodo
- get a comment
- project creation and lifecycle management
- getupload
- saas
- list campfires
- delete a project
- get a message
- listscheduleentries
- listmessages
- listrecordings
- list schedule entries
- getprojectconstruction
- listprojectpeople
- list comments
- unarchiverecording
- list to-do lists
- listcampfires
- rest
- get a schedule entry
- list uploads
- gettodo
- update a message
- to-dos, messages, and team member management
- listdocuments
- create a project
- repositiontodo
- list campfire lines
- full basecamp project lifecycle including todos, messages, scheduling, and team management
- Project Manager
- updatetemplate
- createcampfireline
- get a template
- create an upload
- getperson
- createtodolist
- updatescheduleentry
- create project from template
- createtemplate
- individual contributor managing tasks and collaborating on projects
- update a project
- create a to-do
- update project access
- createtodo
- trash a recording
- list recordings
- list all people
- collaboration
- create a to-do list
- createcomment
- updateschedule
slug: basecamp-capability
source_filename: basecamp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Basecamp API\n  description: The Basecamp API is a REST API that provides programmatic access to Basecamp's project management and team\n    communication platform. It enables developers to manage projects, to-do lists, messages, documents, schedules, campfires,\n    uploads, card tables, templates, and team members across Basecamp accounts. The API uses OAuth 2.0 for authentication\n    and returns JSON responses, with all requests scoped to an account ID in the base URL path. Resources include projects,\n    people, to-dos, message boards, documents, card tables, campfires, questionnaires, and webhooks, covering the full breadth\n    of Basecam\n  tags:\n  - Basecamp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: basecamp\n    baseUri: https://3.basecampapi.com/999999999\n    description: Basecamp API HTTP API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{BASECAMP_TOKEN}}'\n    resources:\n    - name: projects-json\n      path: /projects.json\n      operations:\n      - name: listprojects\n        method: GET\n        description: List projects\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter projects by status. Omit for active projects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createproject\n        method: POST\n        description: Create a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-json\n      path: /projects/{projectId}.json\n      operations:\n      - name: getproject\n        method: GET\n        description: Get a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: updateproject\n        method: PUT\n        description: Update a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproject\n        method: DELETE\n        description: Delete a project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-json\n      path: /people.json\n      operations:\n      - name: listpeople\n        method: GET\n        description: List all people\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-people-json\n      path: /projects/{projectId}/people.json\n      operations:\n      - name: listprojectpeople\n        method: GET\n        description: List people on a project\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-people-users-json\n      path: /projects/{projectId}/people/users.json\n      operations:\n      - name: updateprojectaccess\n        method: PUT\n        description: Update project access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: circles-people-json\n      path: /circles/people.json\n      operations:\n      - name: listpingablepeople\n        method: GET\n        description: List pingable people\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people-personid-json\n      path: /people/{personId}.json\n      operations:\n      - name: getperson\n        method: GET\n        description: Get a person\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: my-profile-json\n      path: /my/profile.json\n      operations:\n      - name: getmyprofile\n        method: GET\n        description: Get my profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemyprofile\n        method: PUT\n        description: Update my profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-json\n      path: /templates.json\n      operations:\n      - name: listtemplates\n        method: GET\n        description: List templates\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter templates by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtemplate\n\
  \        method: POST\n        description: Create a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-templateid-json\n      path: /templates/{templateId}.json\n      operations:\n      - name: gettemplate\n        method: GET\n        description: Get a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetemplate\n        method: PUT\n        description: Update a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetemplate\n        method: DELETE\n        description: Delete a template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-templateid-project-constructions-json\n\
  \      path: /templates/{templateId}/project_constructions.json\n      operations:\n      - name: createprojectfromtemplate\n        method: POST\n        description: Create project from template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: templates-templateid-project-constructions-const\n      path: /templates/{templateId}/project_constructions/{constructionId}.json\n      operations:\n      - name: getprojectconstruction\n        method: GET\n        description: Get project construction status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-recordings-json\n      path: /projects/recordings.json\n      operations:\n      - name: listrecordings\n        method: GET\n        description: List recordings\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n\
  \          required: true\n          description: The recording type to list.\n        - name: bucket\n          in: query\n          type: integer\n          description: Filter to a specific project (bucket) ID.\n        - name: status\n          in: query\n          type: string\n          description: Filter by recording status.\n        - name: sort\n          in: query\n          type: string\n          description: Sort field.\n        - name: direction\n          in: query\n          type: string\n          description: Sort direction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recordings-recordingid-status-trashed-json\n      path: /recordings/{recordingId}/status/trashed.json\n      operations:\n      - name: trashrecording\n        method: PUT\n        description: Trash a recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: recordings-recordingid-status-archived-json\n      path: /recordings/{recordingId}/status/archived.json\n      operations:\n      - name: archiverecording\n        method: PUT\n        description: Archive a recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recordings-recordingid-status-active-json\n      path: /recordings/{recordingId}/status/active.json\n      operations:\n      - name: unarchiverecording\n        method: PUT\n        description: Unarchive a recording\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: message-boards-messageboardid-messages-json\n      path: /message_boards/{messageBoardId}/messages.json\n      operations:\n      - name: listmessages\n        method: GET\n        description: List messages\n        inputParameters:\n     \
  \   - name: sort\n          in: query\n          type: string\n          description: Sort field.\n        - name: direction\n          in: query\n          type: string\n          description: Sort direction.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createmessage\n        method: POST\n        description: Create a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages-messageid-json\n      path: /messages/{messageId}.json\n      operations:\n      - name: getmessage\n        method: GET\n        description: Get a message\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemessage\n        method: PUT\n        description: Update a message\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: recordings-recordingid-comments-json\n      path: /recordings/{recordingId}/comments.json\n      operations:\n      - name: listcomments\n        method: GET\n        description: List comments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcomment\n        method: POST\n        description: Create a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments-commentid-json\n      path: /comments/{commentId}.json\n      operations:\n      - name: getcomment\n        method: GET\n        description: Get a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecomment\n        method: PUT\n        description: Update\
  \ a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todosets-todosetid-todolists-json\n      path: /todosets/{todosetId}/todolists.json\n      operations:\n      - name: listtodolists\n        method: GET\n        description: List to-do lists\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtodolist\n        method: POST\n        description: Create a to-do list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todolists-todolistid-json\n      path: /todolists/{todolistId}.json\n      operations:\n      - name: gettodolist\n        method: GET\n        description: Get\
  \ a to-do list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetodolist\n        method: PUT\n        description: Update a to-do list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todolists-todolistid-todos-json\n      path: /todolists/{todolistId}/todos.json\n      operations:\n      - name: listtodos\n        method: GET\n        description: List to-dos\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by status.\n        - name: completed\n          in: query\n          type: boolean\n          description: Set to true to return completed to-dos.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createtodo\n        method: POST\n\
  \        description: Create a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todos-todoid-json\n      path: /todos/{todoId}.json\n      operations:\n      - name: gettodo\n        method: GET\n        description: Get a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatetodo\n        method: PUT\n        description: Update a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todos-todoid-completion-json\n      path: /todos/{todoId}/completion.json\n      operations:\n      - name: completetodo\n        method: POST\n        description: Complete a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ uncompletetodo\n        method: DELETE\n        description: Uncomplete a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: todos-todoid-position-json\n      path: /todos/{todoId}/position.json\n      operations:\n      - name: repositiontodo\n        method: PUT\n        description: Reposition a to-do\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-scheduleid-json\n      path: /schedules/{scheduleId}.json\n      operations:\n      - name: getschedule\n        method: GET\n        description: Get a schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateschedule\n        method: PUT\n        description: Update a schedule\n        outputRawFormat: json\n        outputParameters:\n       \
  \ - name: result\n          type: object\n          value: $.\n    - name: schedules-scheduleid-entries-json\n      path: /schedules/{scheduleId}/entries.json\n      operations:\n      - name: listscheduleentries\n        method: GET\n        description: List schedule entries\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Filter by status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createscheduleentry\n        method: POST\n        description: Create a schedule entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedule-entries-entryid-json\n      path: /schedule_entries/{entryId}.json\n      operations:\n      - name: getscheduleentry\n        method: GET\n        description: Get a schedule entry\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatescheduleentry\n        method: PUT\n        description: Update a schedule entry\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vaults-vaultid-documents-json\n      path: /vaults/{vaultId}/documents.json\n      operations:\n      - name: listdocuments\n        method: GET\n        description: List documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdocument\n        method: POST\n        description: Create a document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid-json\n      path: /documents/{documentId}.json\n      operations:\n      - name: getdocument\n\
  \        method: GET\n        description: Get a document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocument\n        method: PUT\n        description: Update a document\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vaults-vaultid-uploads-json\n      path: /vaults/{vaultId}/uploads.json\n      operations:\n      - name: listuploads\n        method: GET\n        description: List uploads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createupload\n        method: POST\n        description: Create an upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: uploads-uploadid-json\n      path: /uploads/{uploadId}.json\n\
  \      operations:\n      - name: getupload\n        method: GET\n        description: Get an upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateupload\n        method: PUT\n        description: Update an upload\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chats-json\n      path: /chats.json\n      operations:\n      - name: listcampfires\n        method: GET\n        description: List campfires\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: chats-campfireid-json\n      path: /chats/{campfireId}.json\n      operations:\n      - name: getcampfire\n        method: GET\n        description: Get a campfire\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: chats-campfireid-lines-json\n      path: /chats/{campfireId}/lines.json\n      operations:\n      - name: listcampfirelines\n        method: GET\n        description: List campfire lines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcampfireline\n        method: POST\n        description: Create a campfire line\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: basecamp-rest\n    description: REST adapter for Basecamp API.\n    resources:\n    - path: /projects.json\n      name: listprojects\n      operations:\n      - method: GET\n        name: listprojects\n        description: List projects\n        call: basecamp.listprojects\n        outputParameters:\n        - type: object\n          mapping: $.\n    -\
  \ path: /projects.json\n      name: createproject\n      operations:\n      - method: POST\n        name: createproject\n        description: Create a project\n        call: basecamp.createproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}.json\n      name: getproject\n      operations:\n      - method: GET\n        name: getproject\n        description: Get a project\n        call: basecamp.getproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}.json\n      name: updateproject\n      operations:\n      - method: PUT\n        name: updateproject\n        description: Update a project\n        call: basecamp.updateproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}.json\n      name: deleteproject\n      operations:\n      - method: DELETE\n        name: deleteproject\n        description: Delete\
  \ a project\n        call: basecamp.deleteproject\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people.json\n      name: listpeople\n      operations:\n      - method: GET\n        name: listpeople\n        description: List all people\n        call: basecamp.listpeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/people.json\n      name: listprojectpeople\n      operations:\n      - method: GET\n        name: listprojectpeople\n        description: List people on a project\n        call: basecamp.listprojectpeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/people/users.json\n      name: updateprojectaccess\n      operations:\n      - method: PUT\n        name: updateprojectaccess\n        description: Update project access\n        call: basecamp.updateprojectaccess\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /circles/people.json\n      name: listpingablepeople\n      operations:\n      - method: GET\n        name: listpingablepeople\n        description: List pingable people\n        call: basecamp.listpingablepeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/{personId}.json\n      name: getperson\n      operations:\n      - method: GET\n        name: getperson\n        description: Get a person\n        call: basecamp.getperson\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /my/profile.json\n      name: getmyprofile\n      operations:\n      - method: GET\n        name: getmyprofile\n        description: Get my profile\n        call: basecamp.getmyprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /my/profile.json\n      name: updatemyprofile\n      operations:\n      - method: PUT\n        name: updatemyprofile\n     \
  \   description: Update my profile\n        call: basecamp.updatemyprofile\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates.json\n      name: listtemplates\n      operations:\n      - method: GET\n        name: listtemplates\n        description: List templates\n        call: basecamp.listtemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates.json\n      name: createtemplate\n      operations:\n      - method: POST\n        name: createtemplate\n        description: Create a template\n        call: basecamp.createtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}.json\n      name: gettemplate\n      operations:\n      - method: GET\n        name: gettemplate\n        description: Get a template\n        call: basecamp.gettemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}.json\n\
  \      name: updatetemplate\n      operations:\n      - method: PUT\n        name: updatetemplate\n        description: Update a template\n        call: basecamp.updatetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}.json\n      name: deletetemplate\n      operations:\n      - method: DELETE\n        name: deletetemplate\n        description: Delete a template\n        call: basecamp.deletetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}/project_constructions.json\n      name: createprojectfromtemplate\n      operations:\n      - method: POST\n        name: createprojectfromtemplate\n        description: Create project from template\n        call: basecamp.createprojectfromtemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /templates/{templateId}/project_constructions/{constructionId}.json\n      name:\
  \ getprojectconstruction\n      operations:\n      - method: GET\n        name: getprojectconstruction\n        description: Get project construction status\n        call: basecamp.getprojectconstruction\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/recordings.json\n      name: listrecordings\n      operations:\n      - method: GET\n        name: listrecordings\n        description: List recordings\n        call: basecamp.listrecordings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recordings/{recordingId}/status/trashed.json\n      name: trashrecording\n      operations:\n      - method: PUT\n        name: trashrecording\n        description: Trash a recording\n        call: basecamp.trashrecording\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recordings/{recordingId}/status/archived.json\n      name: archiverecording\n      operations:\n      - method:\
  \ PUT\n        name: archiverecording\n        description: Archive a recording\n        call: basecamp.archiverecording\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recordings/{recordingId}/status/active.json\n      name: unarchiverecording\n      operations:\n      - method: PUT\n        name: unarchiverecording\n        description: Unarchive a recording\n        call: basecamp.unarchiverecording\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /message_boards/{messageBoardId}/messages.json\n      name: listmessages\n      operations:\n      - method: GET\n        name: listmessages\n        description: List messages\n        call: basecamp.listmessages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /message_boards/{messageBoardId}/messages.json\n      name: createmessage\n      operations:\n      - method: POST\n        name: createmessage\n        description:\
  \ Create a message\n        call: basecamp.createmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}.json\n      name: getmessage\n      operations:\n      - method: GET\n        name: getmessage\n        description: Get a message\n        call: basecamp.getmessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /messages/{messageId}.json\n      name: updatemessage\n      operations:\n      - method: PUT\n        name: updatemessage\n        description: Update a message\n        call: basecamp.updatemessage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recordings/{recordingId}/comments.json\n      name: listcomments\n      operations:\n      - method: GET\n        name: listcomments\n        description: List comments\n        call: basecamp.listcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /recordings/{recordingId}/comments.json\n      name: createcomment\n      operations:\n      - method: POST\n        name: createcomment\n        description: Create a comment\n        call: basecamp.createcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/{commentId}.json\n      name: getcomment\n      operations:\n      - method: GET\n        name: getcomment\n        description: Get a comment\n        call: basecamp.getcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments/{commentId}.json\n      name: updatecomment\n      operations:\n      - method: PUT\n        name: updatecomment\n        description: Update a comment\n        call: basecamp.updatecomment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todosets/{todosetId}/todolists.json\n      name: listtodolists\n      operations:\n      - method: GET\n        name: listtodolists\n\
  \        description: List to-do lists\n        call: basecamp.listtodolists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todosets/{todosetId}/todolists.json\n      name: createtodolist\n      operations:\n      - method: POST\n        name: createtodolist\n        description: Create a to-do list\n        call: basecamp.createtodolist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todolists/{todolistId}.json\n      name: gettodolist\n      operations:\n      - method: GET\n        name: gettodolist\n        description: Get a to-do list\n        call: basecamp.gettodolist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todolists/{todolistId}.json\n      name: updatetodolist\n      operations:\n      - method: PUT\n        name: updatetodolist\n        description: Update a to-do list\n        call: basecamp.updatetodolist\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /todolists/{todolistId}/todos.json\n      name: listtodos\n      operations:\n      - method: GET\n        name: listtodos\n        description: List to-dos\n        call: basecamp.listtodos\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todolists/{todolistId}/todos.json\n      name: createtodo\n      operations:\n      - method: POST\n        name: createtodo\n        description: Create a to-do\n        call: basecamp.createtodo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todos/{todoId}.json\n      name: gettodo\n      operations:\n      - method: GET\n        name: gettodo\n        description: Get a to-do\n        call: basecamp.gettodo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todos/{todoId}.json\n      name: updatetodo\n      operations:\n      - method: PUT\n        name: updatetodo\n        description: Update\
  \ a to-do\n        call: basecamp.updatetodo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todos/{todoId}/completion.json\n      name: completetodo\n      operations:\n      - method: POST\n        name: completetodo\n        description: Complete a to-do\n        call: basecamp.completetodo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todos/{todoId}/completion.json\n      name: uncompletetodo\n      operations:\n      - method: DELETE\n        name: uncompletetodo\n        description: Uncomplete a to-do\n        call: basecamp.uncompletetodo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /todos/{todoId}/position.json\n      name: repositiontodo\n      operations:\n      - method: PUT\n        name: repositiontodo\n        description: Reposition a to-do\n        call: basecamp.repositiontodo\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /schedules/{scheduleId}.json\n      name: getschedule\n      operations:\n      - method: GET\n        name: getschedule\n        description: Get a schedule\n        call: basecamp.getschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{scheduleId}.json\n      name: updateschedule\n      operations:\n      - method: PUT\n        name: updateschedule\n        description: Update a schedule\n        call: basecamp.updateschedule\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{scheduleId}/entries.json\n      name: listscheduleentries\n      operations:\n      - method: GET\n        name: listscheduleentries\n        description: List schedule entries\n        call: basecamp.listscheduleentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/{scheduleId}/entries.json\n      name: createscheduleentry\n      operations:\n\
  \      - method: POST\n        name: createscheduleentry\n        description: Create a schedule entry\n        call: basecamp.createscheduleentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule_entries/{entryId}.json\n      name: getscheduleentry\n      operations:\n      - method: GET\n        name: getscheduleentry\n        description: Get a schedule entry\n        call: basecamp.getscheduleentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedule_entries/{entryId}.json\n      name: updatescheduleentry\n      operations:\n      - method: PUT\n        name: updatescheduleentry\n        description: Update a schedule entry\n        call: basecamp.updatescheduleentry\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vaults/{vaultId}/documents.jso\n\n# --- truncated at 32 KB (51 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/basecamp/refs/heads/main/capabilities/basecamp-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/basecamp/refs/heads/main/capabilities/basecamp-capability.yaml
tags:
- Basecamp
- API
tools:
- description: List projects
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojects
- description: Create a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createproject
- description: Get a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproject
- description: Update a project
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateproject
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproject
- description: List all people
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpeople
- description: List people on a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listprojectpeople
- description: Update project access
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateprojectaccess
- description: List pingable people
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpingablepeople
- description: Get a person
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getperson
- description: Get my profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmyprofile
- description: Update my profile
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemyprofile
- description: List templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtemplates
- description: Create a template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtemplate
- description: Get a template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplate
- description: Update a template
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetemplate
- description: Delete a template
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetemplate
- description: Create project from template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createprojectfromtemplate
- description: Get project construction status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprojectconstruction
- description: List recordings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecordings
- description: Trash a recording
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: trashrecording
- description: Archive a recording
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: archiverecording
- description: Unarchive a recording
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unarchiverecording
- description: List messages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmessages
- description: Create a message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmessage
- description: Get a message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmessage
- description: Update a message
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatemessage
- description: List comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomments
- description: Create a comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcomment
- description: Get a comment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcomment
- description: Update a comment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecomment
- description: List to-do lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtodolists
- description: Create a to-do list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtodolist
- description: Get a to-do list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettodolist
- description: Update a to-do list
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetodolist
- description: List to-dos
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtodos
- description: Create a to-do
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtodo
- description: Get a to-do
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettodo
- description: Update a to-do
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetodo
- description: Complete a to-do
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: completetodo
- description: Uncomplete a to-do
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: uncompletetodo
- description: Reposition a to-do
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: repositiontodo
- description: Get a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getschedule
- description: Update a schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateschedule
- description: List schedule entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscheduleentries
- description: Create a schedule entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createscheduleentry
- description: Get a schedule entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getscheduleentry
- description: Update a schedule entry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatescheduleentry
- description: List documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocuments
- description: Create a document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocument
- description: Get a document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocument
- description: Update a document
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedocument
- description: List uploads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listuploads
- description: Create an upload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createupload
- description: Get an upload
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getupload
- description: Update an upload
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateupload
- description: List campfires
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampfires
- description: Get a campfire
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampfire
- description: List campfire lines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampfirelines
- description: Create a campfire line
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcampfireline
---
