---
categories: []
consumed_apis: []
description: API Reference API capability.
layout: capability
name: API Reference
operations:
- description: ✨ Get activity logs
  method: GET
  name: list
  path: /api/activity-logs/
- description: ✨ List all annotation history items for annotation
  method: GET
  name: list
  path: /api/annotation-history/
- description: ✨ Delete annotation history items
  method: DELETE
  name: delete
  path: /api/annotation-history/
- description: ✨ Retrieve a single annotation history item (full result for hydration)
  method: GET
  name: retrieve
  path: /api/annotation-history/{id}/
- description: ✨ List annotation history items for project
  method: GET
  name: list-for-project
  path: /api/projects/{id}/annotation-history/
- description: ✨ List reviews
  method: GET
  name: list
  path: /api/annotation-reviews/
- description: ✨ Create review
  method: POST
  name: create
  path: /api/annotation-reviews/
- description: ✨ Get review
  method: GET
  name: get
  path: /api/annotation-reviews/{id}/
- description: ✨ Delete review
  method: DELETE
  name: delete
  path: /api/annotation-reviews/{id}/
- description: ✨ Update review
  method: PATCH
  name: update
  path: /api/annotation-reviews/{id}/
- description: Bulk delete annotations by IDs
  method: POST
  name: delete-bulk
  path: /api/annotations/bulk-delete/
- description: Bulk create annotations
  method: POST
  name: create-bulk
  path: /api/annotations/bulk/
- description: Get annotation by its ID
  method: GET
  name: get
  path: /api/annotations/{id}/
- description: Delete annotation
  method: DELETE
  name: delete
  path: /api/annotations/{id}/
- description: Update annotation
  method: PATCH
  name: update
  path: /api/annotations/{id}/
- description: Get all task annotations
  method: GET
  name: list
  path: /api/tasks/{id}/annotations/
- description: Create annotation
  method: POST
  name: create
  path: /api/tasks/{id}/annotations/
- description: ✨ Get billing info
  method: GET
  name: info
  path: /api/billing/info
- description: ✨ List comments
  method: GET
  name: list
  path: /api/comments/
- description: ✨ Create comment
  method: POST
  name: create
  path: /api/comments/
- description: ✨ Export comments to CSV
  method: GET
  name: export
  path: /api/comments/export/
- description: ✨ Get comment
  method: GET
  name: get
  path: /api/comments/{id}/
- description: ✨ Delete comment
  method: DELETE
  name: delete
  path: /api/comments/{id}/
- description: ✨ Update comment
  method: PATCH
  name: update
  path: /api/comments/{id}/
- description: ✨ Get current user info
  method: GET
  name: get-current-user
  path: /api/current-user
- description: ✨ Update current user
  method: PATCH
  name: update-current-user
  path: /api/current-user
- description: Get user hotkeys
  method: GET
  name: get-hotkeys
  path: /api/current-user/hotkeys/
- description: Update user hotkeys
  method: PATCH
  name: update-hotkeys
  path: /api/current-user/hotkeys/
- description: Reset user token
  method: POST
  name: reset-token
  path: /api/current-user/reset-token/
- description: Get user token
  method: GET
  name: get-token
  path: /api/current-user/token
- description: Retrieve my user
  method: GET
  name: whoami
  path: /api/current-user/whoami
- description: List users
  method: GET
  name: list
  path: /api/users/
- description: Create new user
  method: POST
  name: create
  path: /api/users/
- description: Get user info
  method: GET
  name: get
  path: /api/users/{id}/
- description: Delete user
  method: DELETE
  name: delete
  path: /api/users/{id}/
- description: Update user details
  method: PATCH
  name: update
  path: /api/users/{id}/
- description: ✨ Trigger Agreement V2 backfill
  method: POST
  name: trigger-backfill
  path: /api/dimensions/backfill/
- description: ✨ Cancel Agreement V2 backfill jobs
  method: DELETE
  name: cancel-backfill
  path: /api/dimensions/backfill/
- description: ✨ List Agreement V2 backfill jobs
  method: GET
  name: list-backfills
  path: /api/dimensions/backfill/jobs/
- description: ✨ Get Agreement V2 backfill status
  method: GET
  name: get-backfill-status
  path: /api/dimensions/backfill/status/
- description: ✨ List dimensions
  method: GET
  name: list
  path: /api/projects/{project_pk}/dimensions/
- description: ✨ Get dimension
  method: GET
  name: get
  path: /api/projects/{project_pk}/dimensions/{id}/
- description: Get actions
  method: GET
  name: list
  path: /api/dm/actions/
- description: Post actions
  method: POST
  name: create
  path: /api/dm/actions/
- description: List views
  method: GET
  name: list
  path: /api/dm/views/
- description: Create view
  method: POST
  name: create
  path: /api/dm/views/
- description: Update order of views
  method: POST
  name: update-order
  path: /api/dm/views/order/
- description: Delete all project views
  method: DELETE
  name: delete-all
  path: /api/dm/views/reset/
- description: Get view details
  method: GET
  name: get
  path: /api/dm/views/{id}/
- description: Delete view
  method: DELETE
  name: delete
  path: /api/dm/views/{id}/
- description: Update view
  method: PATCH
  name: update
  path: /api/dm/views/{id}/
- description: ✨ Trigger state backfill for organization
  method: POST
  name: trigger-backfill
  path: /api/fsm/backfill/
- description: ✨ Cancel state backfill jobs
  method: DELETE
  name: cancel-backfill
  path: /api/fsm/backfill/
- description: ✨ List state backfill jobs
  method: GET
  name: list-backfills
  path: /api/fsm/backfill/jobs/
- description: ✨ Get state backfill status
  method: GET
  name: get-backfill-status
  path: /api/fsm/backfill/status/
- description: ✨ Get entity state history
  method: GET
  name: state-history
  path: /api/fsm/entities/{entity_name}/{entity_id}/history
- description: ✨ Execute manual state transition
  method: POST
  name: execute-transition
  path: /api/fsm/entities/{entity_name}/{entity_id}/transition/
- description: Get file upload
  method: GET
  name: get
  path: /api/import/file-upload/{id}
- description: Delete file upload
  method: DELETE
  name: delete
  path: /api/import/file-upload/{id}
- description: Update file upload
  method: PATCH
  name: update
  path: /api/import/file-upload/{id}
personas: []
provider_name: Label Studio
provider_slug: label-studio
search_terms:
- reset user token
- bulk delete annotations by ids
- create new user
- delete annotation
- api
- get actions
- update user hotkeys
- update order
- retrieve
- machine learning
- state history
- ✨ create review
- ✨ get review
- ✨ get comment
- ✨ get activity logs
- delete all
- get view details
- update view
- get token
- create bulk
- delete bulk
- ✨ export comments to csv
- ✨ delete review
- ✨ delete comment
- ai
- ✨ cancel state backfill jobs
- delete
- ✨ update current user
- ✨ trigger state backfill for organization
- ✨ list reviews
- ✨ trigger agreement v2 backfill
- ✨ get billing info
- artificial intelligence
- delete user
- list for project
- info
- get user hotkeys
- list users
- ✨ execute manual state transition
- delete all project views
- ✨ update comment
- execute transition
- export
- get current user
- ✨ list comments
- get hotkeys
- ✨ get dimension
- update user details
- bulk create annotations
- ✨ update review
- ✨ create comment
- llm
- create view
- ✨ retrieve a single annotation history item (full result for hydration)
- trigger backfill
- ✨ delete annotation history items
- ✨ cancel agreement v2 backfill jobs
- get file upload
- ✨ list annotation history items for project
- whoami
- cancel backfill
- ✨ list dimensions
- update annotation
- update hotkeys
- data labeling
- retrieve my user
- studio
- list backfills
- post actions
- update file upload
- list views
- ✨ get entity state history
- get
- list
- delete file upload
- update
- ✨ list state backfill jobs
- ✨ get state backfill status
- ✨ list agreement v2 backfill jobs
- label
- create
- open source
- ✨ get current user info
- get user info
- annotation
- get user token
- get backfill status
- get all task annotations
- reset token
- ✨ get agreement v2 backfill status
- ✨ list all annotation history items for annotation
- get annotation by its id
- delete view
- update order of views
- create annotation
- update current user
slug: label-studio-capability
source_filename: label-studio-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: API Reference\n  description: API Reference API capability.\n  tags:\n  - Label\n  - Studio\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: label-studio\n    baseUri: http://localhost:8000\n    description: API Reference HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{LABEL_STUDIO_TOKEN}}'\n    resources:\n    - name: api-activity-logs\n      path: /api/activity-logs/\n      operations:\n      - name: list\n        method: GET\n        description: ✨ Get activity logs\n        inputParameters:\n        - name: end_date\n          in: query\n          type: string\n          description: End date/time (ISO-8601) for log filtering.\n        - name: method\n          in: query\n          type: string\n          description: HTTP request method used in the log.\n        - name: ordering\n          in: query\n\
  \          type: string\n          description: Which field to use when ordering the results.\n        - name: page\n          in: query\n          type: integer\n          description: '[or \"start\"] Current page index.'\n        - name: page_size\n          in: query\n          type: integer\n          description: '[or \"length\"] Logs per page, use -1 to obtain all logs (might be slow).'\n        - name: project\n          in: query\n          type: integer\n          description: Project ID to filter logs.\n        - name: search\n          in: query\n          type: string\n          description: Search expression using \"AND\"/\"OR\" to filter by request URL.\n        - name: start_date\n          in: query\n          type: string\n          description: Start date/time (ISO-8601) for log filtering.\n        - name: user\n          in: query\n          type: integer\n          description: User ID to filter logs.\n        - name: workspace\n          in: query\n          type:\
  \ integer\n          description: Workspace owner ID to filter logs.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotation-history\n      path: /api/annotation-history/\n      operations:\n      - name: list\n        method: GET\n        description: ✨ List all annotation history items for annotation\n        inputParameters:\n        - name: annotation\n          in: query\n          type: integer\n          description: Annotation ID to get annotation history items for.\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when\
  \ ordering the results.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: ✨ Delete annotation history items\n        inputParameters:\n        - name: annotation\n          in: query\n          type: integer\n          description: Annotation ID to delete annotation history items for.\n        - name: project\n          in: query\n          type: integer\n          description: Project ID to delete annotation history items for.\n        - name: task\n          in: query\n          type: integer\n          description: Task ID to delete annotation\
  \ history items for.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotation-history-id\n      path: /api/annotation-history/{id}/\n      operations:\n      - name: retrieve\n        method: GET\n        description: ✨ Retrieve a single annotation history item (full result for hydration)\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can\
  \ find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-projects-id-annotation-history\n      path: /api/projects/{id}/annotation-history/\n      operations:\n      - name: list-for-project\n        method: GET\n        description: ✨ List annotation history items for project\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: page\n          in: query\n          type: integer\n          description: A page number within the paginated result set.\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token\
  \ (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotation-reviews\n      path: /api/annotation-reviews/\n      operations:\n      - name: list\n        method: GET\n        description: ✨ List reviews\n        inputParameters:\n        - name: annotation\n          in: query\n          type: integer\n        - name: annotation__task__project\n          in: query\n          type: integer\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your\
  \ user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: ✨ Create review\n        inputParameters:\n        - name: async_postprocess\n          in: query\n          type: boolean\n          description: Whether to postprocess the review asynchronously.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotation-reviews-id\n      path: /api/annotation-reviews/{id}/\n\
  \      operations:\n      - name: get\n        method: GET\n        description: ✨ Get review\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this annotation review.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: ✨ Delete review\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this annotation\
  \ review.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: ✨ Update review\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this annotation review.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example:\
  \ <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotations-bulk-delete\n      path: /api/annotations/bulk-delete/\n      operations:\n      - name: delete-bulk\n        method: POST\n        description: Bulk delete annotations by IDs\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotations-bulk\n      path: /api/annotations/bulk/\n      operations:\n      - name: create-bulk\n        method: POST\n        description: Bulk create annotations\n \
  \       inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-annotations-id\n      path: /api/annotations/{id}/\n      operations:\n      - name: get\n        method: GET\n        description: Get annotation by its ID\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page\
  \ in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete annotation\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: Update annotation\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required:\
  \ true\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-tasks-id-annotations\n      path: /api/tasks/{id}/annotations/\n      operations:\n      - name: list\n        method: GET\n        description: Get all task annotations\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Task ID\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: Authorization\n          in: header\n          type: string\n       \
  \   required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: Create annotation\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Task ID\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: api-billing-info\n      path: /api/billing/info\n      operations:\n      - name: info\n        method: GET\n        description: ✨ Get billing info\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-comments\n      path: /api/comments/\n      operations:\n      - name: list\n        method: GET\n        description: ✨ List comments\n        inputParameters:\n        - name: annotation\n          in: query\n          type: integer\n        - name: annotators\n          in: query\n          type: string\n        - name: draft\n          in: query\n      \
  \    type: integer\n        - name: expand_created_by\n          in: query\n          type: boolean\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: projects\n          in: query\n          type: string\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create\n        method: POST\n        description: ✨ Create comment\n        inputParameters:\n        - name: expand_created_by\n          in: query\n          type: boolean\n          description: Expand the created_by field\n        - name:\
  \ Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-comments-export\n      path: /api/comments/export/\n      operations:\n      - name: export\n        method: GET\n        description: ✨ Export comments to CSV\n        inputParameters:\n        - name: annotation\n          in: query\n          type: integer\n        - name: annotators\n          in: query\n          type: string\n        - name: draft\n          in: query\n          type: integer\n        - name: expand_created_by\n          in: query\n          type: boolean\n        - name: projects\n          in: query\n          type: string\n        - name:\
  \ tz\n          in: query\n          type: string\n          description: Timezone in which to export the data. Format IANA timezone name, e.g. \"America/New_York\"\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-comments-id\n      path: /api/comments/{id}/\n      operations:\n      - name: get\n        method: GET\n        description: ✨ Get comment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: expand_created_by\n          in: query\n          type: boolean\n          description: Expand the created_by field\n\
  \        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: ✨ Delete comment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: expand_created_by\n          in: query\n          type: boolean\n          description: Expand the created_by field\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n      \
  \      Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: ✨ Update comment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: expand_created_by\n          in: query\n          type: boolean\n          description: Expand the created_by field\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-current-user\n      path:\
  \ /api/current-user\n      operations:\n      - name: get-current-user\n        method: GET\n        description: ✨ Get current user info\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-current-user\n        method: PATCH\n        description: ✨ Update current user\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example:\
  \ <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-current-user-hotkeys\n      path: /api/current-user/hotkeys/\n      operations:\n      - name: get-hotkeys\n        method: GET\n        description: Get user hotkeys\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-hotkeys\n        method: PATCH\n        description: Update user hotkeys\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n        \
  \  required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-current-user-reset-token\n      path: /api/current-user/reset-token/\n      operations:\n      - name: reset-token\n        method: POST\n        description: Reset user token\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: api-current-user-token\n      path: /api/current-user/token\n      operations:\n      - name: get-token\n        method: GET\n        description: Get user token\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-current-user-whoami\n      path: /api/current-user/whoami\n      operations:\n      - name: whoami\n        method: GET\n        description: Retrieve my user\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request\
  \ header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users\n      path: /api/users/\n      operations:\n      - name: list\n        method: GET\n        description: List users\n        inputParameters:\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      -\
  \ name: create\n        method: POST\n        description: Create new user\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-users-id\n      path: /api/users/{id}/\n      operations:\n      - name: get\n        method: GET\n        description: Get user info\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: User ID\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as\
  \ a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete\n        method: DELETE\n        description: Delete user\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: User ID\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update\n        method: PATCH\n        description: Update user\
  \ details\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: User ID\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-dimensions-backfill\n      path: /api/dimensions/backfill/\n      operations:\n      - name: trigger-backfill\n        method: POST\n        description: ✨ Trigger Agreement V2 backfill\n        inputParameters:\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header.\
  \ You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: cancel-backfill\n        method: DELETE\n        description: ✨ Cancel Agreement V2 backfill jobs\n        inputParameters:\n        - name: job_id\n          in: query\n          type: integer\n          description: Optional specific job ID to cancel\n        - name: project_id\n          in: query\n          type: integer\n          description: Optional project ID to cancel its active backfill jobs\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-dimensions-backfill-jobs\n      path: /api/dimensions/backfill/jobs/\n      operations:\n      - name: list-backfills\n        method: GET\n        description: ✨ List Agreement V2 backfill jobs\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: 'Filter by job status: PENDING, QUEUED, RUNNING, COMPLETED, or FAILED.'\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-dimensions-backfill-status\n      path: /api/dimensions/backfill/status/\n\
  \      operations:\n      - name: get-backfill-status\n        method: GET\n        description: ✨ Get Agreement V2 backfill status\n        inputParameters:\n        - name: job_id\n          in: query\n          type: integer\n          description: Optional job ID to retrieve specific job status\n        - name: project_id\n          in: query\n          type: integer\n          description: Optional project ID to retrieve the latest backfill status for that project. If omitted, returns aggregated\n            organization status.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-projects-project-pk-dimensions\n\
  \      path: /api/projects/{project_pk}/dimensions/\n      operations:\n      - name: list\n        method: GET\n        description: ✨ List dimensions\n        inputParameters:\n        - name: project_pk\n          in: path\n          type: integer\n          required: true\n          description: Project ID\n        - name: agreement_methodology\n          in: query\n          type: string\n          description: 'Agreement methodology to use for computing allowed_metrics_with_params. If not provided, uses the\n            methodology stored in the project settings. Valid values: \"pai'\n        - name: is_active\n          in: query\n          type: boolean\n          description: Filter by active status\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: Authorization\n          in: header\n          type: string\n          required: true\n          description: 'The token (or\
  \ API key) must be passed as a request header. You can find your user token on the User\n            Account page in Label Studio. Example: <br><pre><code class='\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-projects-project-pk-dimensions-id\n      path: /api/projects/{project_pk}/dimensions/{id}/\n      operations:\n      - name: get\n        method: GET\n        description: ✨ Get dimension\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Dimension ID\n        - name: project_pk\n        \n\n# --- truncated at 32 KB (93 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/label-studio/refs/heads/main/capabilities/label-studio-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/label-studio/refs/heads/main/capabilities/label-studio-capability.yaml
tags:
- Label
- Studio
- API
tools:
- description: ✨ Get activity logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: ✨ List all annotation history items for annotation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: ✨ Delete annotation history items
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: ✨ Retrieve a single annotation history item (full result for hydration)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieve
- description: ✨ List annotation history items for project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-for-project
- description: ✨ List reviews
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: ✨ Create review
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: ✨ Get review
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: ✨ Delete review
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: ✨ Update review
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Bulk delete annotations by IDs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: delete-bulk
- description: Bulk create annotations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-bulk
- description: Get annotation by its ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete annotation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Update annotation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: Get all task annotations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create annotation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: ✨ Get billing info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: info
- description: ✨ List comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: ✨ Create comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: ✨ Export comments to CSV
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: export
- description: ✨ Get comment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: ✨ Delete comment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: ✨ Update comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: ✨ Get current user info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-current-user
- description: ✨ Update current user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-current-user
- description: Get user hotkeys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-hotkeys
- description: Update user hotkeys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-hotkeys
- description: Reset user token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: reset-token
- description: Get user token
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-token
- description: Retrieve my user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: whoami
- description: List users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create new user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Get user info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Update user details
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: ✨ Trigger Agreement V2 backfill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-backfill
- description: ✨ Cancel Agreement V2 backfill jobs
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-backfill
- description: ✨ List Agreement V2 backfill jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-backfills
- description: ✨ Get Agreement V2 backfill status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-backfill-status
- description: ✨ List dimensions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: ✨ Get dimension
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Get actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Post actions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: List views
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list
- description: Create view
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create
- description: Update order of views
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-order
- description: Delete all project views
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-all
- description: Get view details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete view
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Update view
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
- description: ✨ Trigger state backfill for organization
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: trigger-backfill
- description: ✨ Cancel state backfill jobs
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-backfill
- description: ✨ List state backfill jobs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-backfills
- description: ✨ Get state backfill status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-backfill-status
- description: ✨ Get entity state history
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: state-history
- description: ✨ Execute manual state transition
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-transition
- description: Get file upload
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get
- description: Delete file upload
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete
- description: Update file upload
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update
---
