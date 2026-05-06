---
categories: []
consumed_apis: []
description: PostHog API API capability.
layout: capability
name: PostHog API
operations:
- description: Check access
  method: GET
  name: code-invites-check-access-retrieve
  path: /api/code/invites/check-access/
- description: Redeem invite code
  method: POST
  name: code-invites-redeem-create
  path: /api/code/invites/redeem/
- description: GET /api/environments/{environment_id}/alerts/
  method: GET
  name: environments-alerts-list
  path: /api/environments/{environment_id}/alerts/
- description: POST /api/environments/{environment_id}/alerts/
  method: POST
  name: environments-alerts-create
  path: /api/environments/{environment_id}/alerts/
- description: GET /api/environments/{environment_id}/alerts/{id}/
  method: GET
  name: environments-alerts-retrieve
  path: /api/environments/{environment_id}/alerts/{id}/
- description: PUT /api/environments/{environment_id}/alerts/{id}/
  method: PUT
  name: environments-alerts-update
  path: /api/environments/{environment_id}/alerts/{id}/
- description: PATCH /api/environments/{environment_id}/alerts/{id}/
  method: PATCH
  name: environments-alerts-partial-update
  path: /api/environments/{environment_id}/alerts/{id}/
- description: DELETE /api/environments/{environment_id}/alerts/{id}/
  method: DELETE
  name: environments-alerts-destroy
  path: /api/environments/{environment_id}/alerts/{id}/
- description: Simulate a detector on an insight's historical data. Read-only — no AlertCheck records are created.
  method: POST
  name: environments-alerts-simulate-create
  path: /api/environments/{environment_id}/alerts/simulate/
- description: GET /api/environments/{environment_id}/batch_exports/
  method: GET
  name: environments-batch-exports-list
  path: /api/environments/{environment_id}/batch_exports/
- description: POST /api/environments/{environment_id}/batch_exports/
  method: POST
  name: environments-batch-exports-create
  path: /api/environments/{environment_id}/batch_exports/
- description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills, but not updating or deleting them.
  method: GET
  name: environments-batch-exports-backfills-list
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/
- description: Create a new backfill for a BatchExport.
  method: POST
  name: environments-batch-exports-backfills-create
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/
- description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills, but not updating or deleting them.
  method: GET
  name: environments-batch-exports-backfills-retrieve
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/{id}/
- description: Cancel a batch export backfill.
  method: POST
  name: environments-batch-exports-backfills-cancel-crea
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/{id}/cancel/
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/
  method: GET
  name: environments-batch-exports-runs-list
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/
  method: GET
  name: environments-batch-exports-runs-retrieve
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/
- description: Cancel a batch export run.
  method: POST
  name: environments-batch-exports-runs-cancel-create
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/cancel/
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/
  method: GET
  name: environments-batch-exports-runs-logs-retrieve
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/
- description: Retry a batch export run. We use the same underlying mechanism as when backfilling a batch export, as retrying a run is the same as backfilling one run.
  method: POST
  name: environments-batch-exports-runs-retry-create
  path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/retry/
- description: GET /api/environments/{environment_id}/batch_exports/{id}/
  method: GET
  name: environments-batch-exports-retrieve
  path: /api/environments/{environment_id}/batch_exports/{id}/
- description: PUT /api/environments/{environment_id}/batch_exports/{id}/
  method: PUT
  name: environments-batch-exports-update
  path: /api/environments/{environment_id}/batch_exports/{id}/
- description: PATCH /api/environments/{environment_id}/batch_exports/{id}/
  method: PATCH
  name: environments-batch-exports-partial-update
  path: /api/environments/{environment_id}/batch_exports/{id}/
- description: DELETE /api/environments/{environment_id}/batch_exports/{id}/
  method: DELETE
  name: environments-batch-exports-destroy
  path: /api/environments/{environment_id}/batch_exports/{id}/
- description: GET /api/environments/{environment_id}/batch_exports/{id}/logs/
  method: GET
  name: environments-batch-exports-logs-retrieve
  path: /api/environments/{environment_id}/batch_exports/{id}/logs/
- description: Pause a BatchExport.
  method: POST
  name: environments-batch-exports-pause-create
  path: /api/environments/{environment_id}/batch_exports/{id}/pause/
- description: POST /api/environments/{environment_id}/batch_exports/{id}/run_test_step/
  method: POST
  name: environments-batch-exports-run-test-step-create
  path: /api/environments/{environment_id}/batch_exports/{id}/run_test_step/
- description: Unpause a BatchExport.
  method: POST
  name: environments-batch-exports-unpause-create
  path: /api/environments/{environment_id}/batch_exports/{id}/unpause/
- description: POST /api/environments/{environment_id}/batch_exports/run_test_step_new/
  method: POST
  name: environments-batch-exports-run-test-step-new-cre
  path: /api/environments/{environment_id}/batch_exports/run_test_step_new/
- description: GET /api/environments/{environment_id}/batch_exports/test/
  method: GET
  name: environments-batch-exports-test-retrieve
  path: /api/environments/{environment_id}/batch_exports/test/
- description: GET /api/environments/{environment_id}/dashboards/
  method: GET
  name: environments-dashboards-list
  path: /api/environments/{environment_id}/dashboards/
- description: POST /api/environments/{environment_id}/dashboards/
  method: POST
  name: environments-dashboards-create
  path: /api/environments/{environment_id}/dashboards/
- description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
  method: GET
  name: environments-dashboards-collaborators-list
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
- description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
  method: POST
  name: environments-dashboards-collaborators-create
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
- description: DELETE /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/
  method: DELETE
  name: environments-dashboards-collaborators-destroy
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/
- description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/
  method: GET
  name: environments-dashboards-sharing-list
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/
- description: Create a new password for the sharing configuration.
  method: POST
  name: environments-dashboards-sharing-passwords-create
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/passwords/
- description: Delete a password from the sharing configuration.
  method: DELETE
  name: environments-dashboards-sharing-passwords-destro
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/passwords/{password_id}/
- description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/
  method: POST
  name: environments-dashboards-sharing-refresh-create
  path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/
- description: GET /api/environments/{environment_id}/dashboards/{id}/
  method: GET
  name: environments-dashboards-retrieve
  path: /api/environments/{environment_id}/dashboards/{id}/
- description: PUT /api/environments/{environment_id}/dashboards/{id}/
  method: PUT
  name: environments-dashboards-update
  path: /api/environments/{environment_id}/dashboards/{id}/
- description: PATCH /api/environments/{environment_id}/dashboards/{id}/
  method: PATCH
  name: environments-dashboards-partial-update
  path: /api/environments/{environment_id}/dashboards/{id}/
- description: Hard delete of this model is not allowed. Use a patch API call to set "deleted" to true
  method: DELETE
  name: environments-dashboards-destroy
  path: /api/environments/{environment_id}/dashboards/{id}/
- description: Generate AI analysis comparing before/after dashboard refresh. Expects cache_key in request body pointing to the stored 'before' state.
  method: POST
  name: environments-dashboards-analyze-refresh-result-c
  path: /api/environments/{environment_id}/dashboards/{id}/analyze_refresh_result/
- description: Copy an existing dashboard tile to another dashboard (insight or text card; new tile row).
  method: POST
  name: environments-dashboards-copy-tile-create
  path: /api/environments/{environment_id}/dashboards/{id}/copy_tile/
- description: PATCH /api/environments/{environment_id}/dashboards/{id}/move_tile/
  method: PATCH
  name: environments-dashboards-move-tile-partial-update
  path: /api/environments/{environment_id}/dashboards/{id}/move_tile/
- description: POST /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/
  method: POST
  name: environments-dashboards-reorder-tiles-create
  path: /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/
- description: Run all insights on a dashboard and return their results.
  method: GET
  name: environments-dashboards-run-insights-retrieve
  path: /api/environments/{environment_id}/dashboards/{id}/run_insights/
- description: Snapshot the current dashboard state (from cache) for AI analysis. Returns a cache_key representing the 'before' state, to be used with analyze_refresh_result.
  method: POST
  name: environments-dashboards-snapshot-create
  path: /api/environments/{environment_id}/dashboards/{id}/snapshot/
- description: Stream dashboard metadata and tiles via Server-Sent Events. Sends metadata first, then tiles as they are rendered.
  method: GET
  name: environments-dashboards-stream-tiles-retrieve
  path: /api/environments/{environment_id}/dashboards/{id}/stream_tiles/
- description: 'Bulk update tags on multiple objects. Accepts: - {"ids": [...], "action": "add"|"remove"|"set", "tags": ["tag1", "tag2"]} Actions: - "add": Add tags to existing tags on each object - "remove": Remove specific tags from each object - "set":'
  method: POST
  name: environments-dashboards-bulk-update-tags-create
  path: /api/environments/{environment_id}/dashboards/bulk_update_tags/
- description: POST /api/environments/{environment_id}/dashboards/create_from_template_json/
  method: POST
  name: environments-dashboards-create-from-template-jso
  path: /api/environments/{environment_id}/dashboards/create_from_template_json/
- description: Creates an unlisted dashboard from template by tag. Enforces uniqueness (one per tag per team). Returns 409 if unlisted dashboard with this tag already exists.
  method: POST
  name: environments-dashboards-create-unlisted-dashboar
  path: /api/environments/{environment_id}/dashboards/create_unlisted_dashboard/
- description: GET /api/environments/{environment_id}/data_color_themes/
  method: GET
  name: environments-data-color-themes-list
  path: /api/environments/{environment_id}/data_color_themes/
- description: POST /api/environments/{environment_id}/data_color_themes/
  method: POST
  name: environments-data-color-themes-create
  path: /api/environments/{environment_id}/data_color_themes/
- description: GET /api/environments/{environment_id}/data_color_themes/{id}/
  method: GET
  name: environments-data-color-themes-retrieve
  path: /api/environments/{environment_id}/data_color_themes/{id}/
- description: PUT /api/environments/{environment_id}/data_color_themes/{id}/
  method: PUT
  name: environments-data-color-themes-update
  path: /api/environments/{environment_id}/data_color_themes/{id}/
- description: PATCH /api/environments/{environment_id}/data_color_themes/{id}/
  method: PATCH
  name: environments-data-color-themes-partial-update
  path: /api/environments/{environment_id}/data_color_themes/{id}/
- description: DELETE /api/environments/{environment_id}/data_color_themes/{id}/
  method: DELETE
  name: environments-data-color-themes-destroy
  path: /api/environments/{environment_id}/data_color_themes/{id}/
- description: List data modeling jobs which are "runs" for our saved queries.
  method: GET
  name: environments-data-modeling-jobs-list
  path: /api/environments/{environment_id}/data_modeling_jobs/
personas: []
provider_name: PostHog
provider_slug: posthog
search_terms:
- post /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/
- environments batch exports backfills list
- get /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/
- environments alerts create
- environments dashboards destroy
- environments dashboards copy tile create
- retry a batch export run. we use the same underlying mechanism as when backfilling a batch export, as retrying a run is the same as backfilling one run.
- environments alerts update
- analytics
- environments batch exports runs logs retrieve
- environments batch exports runs retry create
- hard delete of this model is not allowed. use a patch api call to set "deleted" to true
- get /api/environments/{environment_id}/dashboards/{id}/
- session recording
- get /api/environments/{environment_id}/batch_exports/{id}/
- environments dashboards partial update
- post /api/environments/{environment_id}/alerts/
- put /api/environments/{environment_id}/dashboards/{id}/
- api
- creates an unlisted dashboard from template by tag. enforces uniqueness (one per tag per team). returns 409 if unlisted dashboard with this tag already exists.
- environments dashboards sharing passwords destro
- environments batch exports retrieve
- 'bulk update tags on multiple objects. accepts: - {"ids": [...], "action": "add"|"remove"|"set", "tags": ["tag1", "tag2"]} actions: - "add": add tags to existing tags on each object - "remove": remove specific tags from each object - "set":'
- environments data color themes list
- environments batch exports run test step new cre
- delete /api/environments/{environment_id}/alerts/{id}/
- list data modeling jobs which are "runs" for our saved queries.
- delete /api/environments/{environment_id}/data_color_themes/{id}/
- environments dashboards update
- environments batch exports partial update
- redeem invite code
- put /api/environments/{environment_id}/batch_exports/{id}/
- get /api/environments/{environment_id}/data_color_themes/{id}/
- patch /api/environments/{environment_id}/dashboards/{id}/
- environments dashboards collaborators destroy
- environments dashboards collaborators create
- environments dashboards sharing refresh create
- check access
- patch /api/environments/{environment_id}/data_color_themes/{id}/
- run all insights on a dashboard and return their results.
- open source
- environments data color themes retrieve
- environments batch exports backfills cancel crea
- environments batch exports create
- get /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/
- environments batch exports test retrieve
- generate ai analysis comparing before/after dashboard refresh. expects cache_key in request body pointing to the stored 'before' state.
- environments data color themes create
- environments dashboards create from template jso
- environments dashboards collaborators list
- feature flags
- environments dashboards sharing passwords create
- post /api/environments/{environment_id}/data_color_themes/
- environments dashboards list
- environments dashboards create
- environments data modeling jobs list
- post /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
- get /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/
- patch /api/environments/{environment_id}/alerts/{id}/
- post /api/environments/{environment_id}/batch_exports/
- environments dashboards move tile partial update
- simulate a detector on an insight's historical data. read-only — no alertcheck records are created.
- patch /api/environments/{environment_id}/batch_exports/{id}/
- environments data color themes partial update
- a/b testing
- get /api/environments/{environment_id}/alerts/
- environments dashboards bulk update tags create
- get /api/environments/{environment_id}/alerts/{id}/
- patch /api/environments/{environment_id}/dashboards/{id}/move_tile/
- environments dashboards create unlisted dashboar
- environments batch exports run test step create
- stream dashboard metadata and tiles via server-sent events. sends metadata first, then tiles as they are rendered.
- viewset for batchexportbackfill models. allows creating and reading backfills, but not updating or deleting them.
- environments alerts list
- environments dashboards snapshot create
- delete /api/environments/{environment_id}/batch_exports/{id}/
- unpause a batchexport.
- delete /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/
- put /api/environments/{environment_id}/alerts/{id}/
- create a new backfill for a batchexport.
- environments batch exports logs retrieve
- environments data color themes update
- copy an existing dashboard tile to another dashboard (insight or text card; new tile row).
- environments batch exports destroy
- environments batch exports backfills retrieve
- environments batch exports list
- environments batch exports backfills create
- post /api/environments/{environment_id}/batch_exports/run_test_step_new/
- environments batch exports unpause create
- environments alerts simulate create
- environments batch exports runs cancel create
- get /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
- post /api/environments/{environment_id}/batch_exports/{id}/run_test_step/
- environments batch exports runs retrieve
- cancel a batch export run.
- post /api/environments/{environment_id}/dashboards/create_from_template_json/
- get /api/environments/{environment_id}/dashboards/
- environments dashboards run insights retrieve
- delete a password from the sharing configuration.
- create a new password for the sharing configuration.
- get /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/
- posthog
- pause a batchexport.
- environments alerts partial update
- get /api/environments/{environment_id}/batch_exports/{id}/logs/
- post /api/environments/{environment_id}/dashboards/
- get /api/environments/{environment_id}/data_color_themes/
- environments batch exports pause create
- environments dashboards sharing list
- post /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/
- environments data color themes destroy
- get /api/environments/{environment_id}/batch_exports/test/
- environments dashboards retrieve
- environments alerts destroy
- cancel a batch export backfill.
- environments dashboards stream tiles retrieve
- environments alerts retrieve
- environments batch exports update
- product analytics
- code invites check access retrieve
- environments dashboards reorder tiles create
- code invites redeem create
- put /api/environments/{environment_id}/data_color_themes/{id}/
- environments dashboards analyze refresh result c
- snapshot the current dashboard state (from cache) for ai analysis. returns a cache_key representing the 'before' state, to be used with analyze_refresh_result.
- environments batch exports runs list
- get /api/environments/{environment_id}/batch_exports/
slug: posthog-capability
source_filename: posthog-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PostHog API\n  description: PostHog API API capability.\n  tags:\n  - Posthog\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: posthog\n    baseUri: https://api.example.com\n    description: PostHog API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{POSTHOG_TOKEN}}'\n    resources:\n    - name: api-code-invites-check-access\n      path: /api/code/invites/check-access/\n      operations:\n      - name: code-invites-check-access-retrieve\n        method: GET\n        description: Check access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-code-invites-redeem\n      path: /api/code/invites/redeem/\n      operations:\n      - name: code-invites-redeem-create\n        method: POST\n        description: Redeem invite code\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-alerts\n      path: /api/environments/{environment_id}/alerts/\n      operations:\n      - name: environments-alerts-list\n        method: GET\n        description: GET /api/environments/{environment_id}/alerts/\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-alerts-create\n        method: POST\n        description: POST /api/environments/{environment_id}/alerts/\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: api-environments-environment-id-alerts-id\n      path: /api/environments/{environment_id}/alerts/{id}/\n      operations:\n      - name: environments-alerts-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/alerts/{id}/\n        inputParameters:\n        - name: checks_date_from\n          in: query\n          type: string\n          description: Relative date string for the start of the check history window (e.g. '-24h', '-7d', '-14d'). Returns\n            checks created after this time. Max retention is 14 days.\n        - name: checks_date_to\n          in: query\n          type: string\n          description: Relative date string for the end of the check history window (e.g. '-1h', '-1d'). Defaults to now if\n            not specified.\n        - name: checks_limit\n          in: query\n          type: integer\n          description: Maximum number of check results to return (default 5,\
  \ max 500). Applied after date filtering.\n        - name: checks_offset\n          in: query\n          type: integer\n          description: Number of newest checks to skip (0-based). Use with checks_limit for pagination. Default 0.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-alerts-update\n        method: PUT\n        description: PUT /api/environments/{environment_id}/alerts/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-alerts-partial-update\n\
  \        method: PATCH\n        description: PATCH /api/environments/{environment_id}/alerts/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-alerts-destroy\n        method: DELETE\n        description: DELETE /api/environments/{environment_id}/alerts/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this alert configuration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-alerts-simulate\n      path: /api/environments/{environment_id}/alerts/simulate/\n\
  \      operations:\n      - name: environments-alerts-simulate-create\n        method: POST\n        description: Simulate a detector on an insight's historical data. Read-only — no AlertCheck records are created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports\n      path: /api/environments/{environment_id}/batch_exports/\n      operations:\n      - name: environments-batch-exports-list\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: environments-batch-exports-create\n        method: POST\n        description: POST /api/environments/{environment_id}/batch_exports/\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/\n      operations:\n      - name: environments-batch-exports-backfills-list\n        method: GET\n        description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills, but not updating or deleting\n          them.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          description: The pagination cursor value.\n        - name: ordering\n\
  \          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-batch-exports-backfills-create\n        method: POST\n        description: Create a new backfill for a BatchExport.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/{id}/\n      operations:\n      - name: environments-batch-exports-backfills-retrieve\n        method: GET\n        description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills,\
  \ but not updating or deleting\n          them.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export backfill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/backfills/{id}/cancel/\n      operations:\n      - name: environments-batch-exports-backfills-cancel-crea\n        method: POST\n        description: Cancel a batch export backfill.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n         \
  \ required: true\n          description: A UUID string identifying this batch export backfill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/\n      operations:\n      - name: environments-batch-exports-runs-list\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          description: The pagination cursor value.\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/\n      operations:\n      - name: environments-batch-exports-runs-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/cancel/\n\
  \      operations:\n      - name: environments-batch-exports-runs-cancel-create\n        method: POST\n        description: Cancel a batch export run.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/\n      operations:\n      - name: environments-batch-exports-runs-logs-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/\n        inputParameters:\n        - name: after\n          in:\
  \ query\n          type: string\n          description: Only return entries after this ISO 8601 timestamp.\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: before\n          in: query\n          type: string\n          description: Only return entries before this ISO 8601 timestamp.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export run.\n        - name: instance_id\n          in: query\n          type: string\n          description: Filter logs to a specific execution instance.\n        - name: level\n          in: query\n          type: string\n          description: 'Comma-separated log levels to include, e.g. ''WARN,ERROR''. Valid levels: DEBUG, LOG, INFO, WARN,\n            ERROR.'\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of log entries to\
  \ return (1-500, default 50).\n        - name: search\n          in: query\n          type: string\n          description: Case-insensitive substring search across log messages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ba\n      path: /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/retry/\n      operations:\n      - name: environments-batch-exports-runs-retry-create\n        method: POST\n        description: Retry a batch export run. We use the same underlying mechanism as when backfilling a batch export, as\n          retrying a run is the same as backfilling one run.\n        inputParameters:\n        - name: batch_export_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID\
  \ string identifying this batch export run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-id\n      path: /api/environments/{environment_id}/batch_exports/{id}/\n      operations:\n      - name: environments-batch-exports-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-batch-exports-update\n        method: PUT\n        description: PUT /api/environments/{environment_id}/batch_exports/{id}/\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-batch-exports-partial-update\n        method: PATCH\n        description: PATCH /api/environments/{environment_id}/batch_exports/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-batch-exports-destroy\n        method: DELETE\n        description: DELETE /api/environments/{environment_id}/batch_exports/{id}/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n   \
  \       description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-id\n      path: /api/environments/{environment_id}/batch_exports/{id}/logs/\n      operations:\n      - name: environments-batch-exports-logs-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/{id}/logs/\n        inputParameters:\n        - name: after\n          in: query\n          type: string\n          description: Only return entries after this ISO 8601 timestamp.\n        - name: before\n          in: query\n          type: string\n          description: Only return entries before this ISO 8601 timestamp.\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        - name:\
  \ instance_id\n          in: query\n          type: string\n          description: Filter logs to a specific execution instance.\n        - name: level\n          in: query\n          type: string\n          description: 'Comma-separated log levels to include, e.g. ''WARN,ERROR''. Valid levels: DEBUG, LOG, INFO, WARN,\n            ERROR.'\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of log entries to return (1-500, default 50).\n        - name: search\n          in: query\n          type: string\n          description: Case-insensitive substring search across log messages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-id\n      path: /api/environments/{environment_id}/batch_exports/{id}/pause/\n      operations:\n      - name: environments-batch-exports-pause-create\n        method: POST\n\
  \        description: Pause a BatchExport.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-id\n      path: /api/environments/{environment_id}/batch_exports/{id}/run_test_step/\n      operations:\n      - name: environments-batch-exports-run-test-step-create\n        method: POST\n        description: POST /api/environments/{environment_id}/batch_exports/{id}/run_test_step/\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: api-environments-environment-id-batch-exports-id\n      path: /api/environments/{environment_id}/batch_exports/{id}/unpause/\n      operations:\n      - name: environments-batch-exports-unpause-create\n        method: POST\n        description: Unpause a BatchExport.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: A UUID string identifying this batch export.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-ru\n      path: /api/environments/{environment_id}/batch_exports/run_test_step_new/\n      operations:\n      - name: environments-batch-exports-run-test-step-new-cre\n        method: POST\n        description: POST /api/environments/{environment_id}/batch_exports/run_test_step_new/\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-batch-exports-te\n      path: /api/environments/{environment_id}/batch_exports/test/\n      operations:\n      - name: environments-batch-exports-test-retrieve\n        method: GET\n        description: GET /api/environments/{environment_id}/batch_exports/test/\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards\n      path: /api/environments/{environment_id}/dashboards/\n      operations:\n      - name: environments-dashboards-list\n        method: GET\n        description: GET /api/environments/{environment_id}/dashboards/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n\
  \        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-dashboards-create\n        method: POST\n        description: POST /api/environments/{environment_id}/dashboards/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/\n      operations:\n      - name: environments-dashboards-collaborators-list\n        method: GET\n        description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/\n        inputParameters:\n\
  \        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-dashboards-collaborators-create\n        method: POST\n        description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/\n      operations:\n      - name: environments-dashboards-collaborators-destroy\n        method: DELETE\n        description: DELETE /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/\n\
  \        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        - name: user__uuid\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/\n      operations:\n      - name: environments-dashboards-sharing-list\n        method: GET\n        description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n\
  \      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/passwords/\n      operations:\n      - name: environments-dashboards-sharing-passwords-create\n        method: POST\n        description: Create a new password for the sharing configuration.\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/passwords/{password_id}/\n      operations:\n      - name: environments-dashboards-sharing-passwords-destro\n        method: DELETE\n        description: Delete a password from the sharing configuration.\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n\
  \        - name: password_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-dashb\n      path: /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/\n      operations:\n      - name: environments-dashboards-sharing-refresh-create\n        method: POST\n        description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/\n        inputParameters:\n        - name: dashboard_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id\n      path: /api/environments/{environment_id}/dashboards/{id}/\n      operations:\n      - name: environments-dashboards-retrieve\n\
  \        method: GET\n        description: GET /api/environments/{environment_id}/dashboards/{id}/\n        inputParameters:\n        - name: filters_override\n          in: query\n          type: string\n          description: JSON object to override dashboard filters for this request only (not persisted). Top-level keys replace;\n            nested values are not deep-merged — pass the complete v\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        - name: variables_override\n          in: query\n          type: string\n          description: 'JSON object to override dashboard variables for this request only (not persisted). Format: {\"<variable_id>\":\n            {\"code_name\": \"<code_name>\", \"variableId\": \"<variab'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: environments-dashboards-update\n        method: PUT\n        description: PUT /api/environments/{environment_id}/dashboards/{id}/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-dashboards-partial-update\n        method: PATCH\n        description: PATCH /api/environments/{environment_id}/dashboards/{id}/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: environments-dashboards-destroy\n        method: DELETE\n        description: Hard delete of this model is not allowed. Use a patch API call to set \"deleted\" to true\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-an\n      path: /api/environments/{environment_id}/dashboards/{id}/analyze_refresh_result/\n      operations:\n      - name: environments-dashboards-analyze-refresh-result-c\n        method: POST\n        description: Generate AI analysis comparing\
  \ before/after dashboard refresh. Expects cache_key in request body pointing\n          to the stored 'before' state.\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-co\n      path: /api/environments/{environment_id}/dashboards/{id}/copy_tile/\n      operations:\n      - name: environments-dashboards-copy-tile-create\n        method: POST\n        description: Copy an existing dashboard tile to another dashboard (insight or text card; new tile row).\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type:\
  \ integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-mo\n      path: /api/environments/{environment_id}/dashboards/{id}/move_tile/\n      operations:\n      - name: environments-dashboards-move-tile-partial-update\n        method: PATCH\n        description: PATCH /api/environments/{environment_id}/dashboards/{id}/move_tile/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-re\n\
  \      path: /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/\n      operations:\n      - name: environments-dashboards-reorder-tiles-create\n        method: POST\n        description: POST /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-ru\n      path: /api/environments/{environment_id}/dashboards/{id}/run_insights/\n      operations:\n      - name: environments-dashboards-run-insights-retrieve\n        method: GET\n        description: Run all insights on a dashboard and return their results.\n        inputParameters:\n\
  \        - name: filters_override\n          in: query\n          type: string\n          description: JSON object to override dashboard filters for this request only (not persisted). Top-level keys replace;\n            nested values are not deep-merged — pass the complete v\n        - name: format\n          in: query\n          type: string\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this dashboard.\n        - name: output_format\n          in: query\n          type: string\n          description: '''optimized'' (default) returns LLM-friendly formatted text per insight. ''json'' returns the raw\n            query result objects.'\n        - name: refresh\n          in: query\n          type: string\n          description: Cache behavior. 'force_cache' (default) serves from cache even if stale. 'blocking' uses cache if fresh,\n            otherwise recalculates. 'force_blocking'\
  \ always recalcu\n        - name: variables_override\n          in: query\n          type: string\n          description: 'JSON object to override dashboard variables for this request only (not persisted). Format: {\"<variable_id>\":\n            {\"code_name\": \"<code_name>\", \"variableId\": \"<variab'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-environments-environment-id-dashboards-id-sn\n      path: /api/environments\n\n# --- truncated at 32 KB (107 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/posthog/refs/heads/main/capabilities/posthog-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/posthog/refs/heads/main/capabilities/posthog-capability.yaml
tags:
- Posthog
- API
tools:
- description: Check access
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: code-invites-check-access-retrieve
- description: Redeem invite code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: code-invites-redeem-create
- description: GET /api/environments/{environment_id}/alerts/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-alerts-list
- description: POST /api/environments/{environment_id}/alerts/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-alerts-create
- description: GET /api/environments/{environment_id}/alerts/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-alerts-retrieve
- description: PUT /api/environments/{environment_id}/alerts/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: environments-alerts-update
- description: PATCH /api/environments/{environment_id}/alerts/{id}/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-alerts-partial-update
- description: DELETE /api/environments/{environment_id}/alerts/{id}/
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-alerts-destroy
- description: Simulate a detector on an insight's historical data. Read-only — no AlertCheck records are created.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-alerts-simulate-create
- description: GET /api/environments/{environment_id}/batch_exports/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-list
- description: POST /api/environments/{environment_id}/batch_exports/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-create
- description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills, but not updating or deleting them.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-backfills-list
- description: Create a new backfill for a BatchExport.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-backfills-create
- description: ViewSet for BatchExportBackfill models. Allows creating and reading backfills, but not updating or deleting them.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-backfills-retrieve
- description: Cancel a batch export backfill.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-backfills-cancel-crea
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-runs-list
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-runs-retrieve
- description: Cancel a batch export run.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-runs-cancel-create
- description: GET /api/environments/{environment_id}/batch_exports/{batch_export_id}/runs/{id}/logs/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-runs-logs-retrieve
- description: Retry a batch export run. We use the same underlying mechanism as when backfilling a batch export, as retrying a run is the same as backfilling one run.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-runs-retry-create
- description: GET /api/environments/{environment_id}/batch_exports/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-retrieve
- description: PUT /api/environments/{environment_id}/batch_exports/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: environments-batch-exports-update
- description: PATCH /api/environments/{environment_id}/batch_exports/{id}/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-partial-update
- description: DELETE /api/environments/{environment_id}/batch_exports/{id}/
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-batch-exports-destroy
- description: GET /api/environments/{environment_id}/batch_exports/{id}/logs/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-logs-retrieve
- description: Pause a BatchExport.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-pause-create
- description: POST /api/environments/{environment_id}/batch_exports/{id}/run_test_step/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-run-test-step-create
- description: Unpause a BatchExport.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-unpause-create
- description: POST /api/environments/{environment_id}/batch_exports/run_test_step_new/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-batch-exports-run-test-step-new-cre
- description: GET /api/environments/{environment_id}/batch_exports/test/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-batch-exports-test-retrieve
- description: GET /api/environments/{environment_id}/dashboards/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-list
- description: POST /api/environments/{environment_id}/dashboards/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-create
- description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-collaborators-list
- description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-collaborators-create
- description: DELETE /api/environments/{environment_id}/dashboards/{dashboard_id}/collaborators/{user__uuid}/
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-dashboards-collaborators-destroy
- description: GET /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-sharing-list
- description: Create a new password for the sharing configuration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-sharing-passwords-create
- description: Delete a password from the sharing configuration.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-dashboards-sharing-passwords-destro
- description: POST /api/environments/{environment_id}/dashboards/{dashboard_id}/sharing/refresh/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-sharing-refresh-create
- description: GET /api/environments/{environment_id}/dashboards/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-retrieve
- description: PUT /api/environments/{environment_id}/dashboards/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: environments-dashboards-update
- description: PATCH /api/environments/{environment_id}/dashboards/{id}/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-partial-update
- description: Hard delete of this model is not allowed. Use a patch API call to set "deleted" to true
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-dashboards-destroy
- description: Generate AI analysis comparing before/after dashboard refresh. Expects cache_key in request body pointing to the stored 'before' state.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-analyze-refresh-result-c
- description: Copy an existing dashboard tile to another dashboard (insight or text card; new tile row).
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-copy-tile-create
- description: PATCH /api/environments/{environment_id}/dashboards/{id}/move_tile/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-move-tile-partial-update
- description: POST /api/environments/{environment_id}/dashboards/{id}/reorder_tiles/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-reorder-tiles-create
- description: Run all insights on a dashboard and return their results.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-run-insights-retrieve
- description: Snapshot the current dashboard state (from cache) for AI analysis. Returns a cache_key representing the 'before' state, to be used with analyze_refresh_result.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-snapshot-create
- description: Stream dashboard metadata and tiles via Server-Sent Events. Sends metadata first, then tiles as they are rendered.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-dashboards-stream-tiles-retrieve
- description: 'Bulk update tags on multiple objects. Accepts: - {"ids": [...], "action": "add"|"remove"|"set", "tags": ["tag1", "tag2"]} Actions: - "add": Add tags to existing tags on each object - "remove": Remove specific tags from each object - "set":'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-bulk-update-tags-create
- description: POST /api/environments/{environment_id}/dashboards/create_from_template_json/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-create-from-template-jso
- description: Creates an unlisted dashboard from template by tag. Enforces uniqueness (one per tag per team). Returns 409 if unlisted dashboard with this tag already exists.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-dashboards-create-unlisted-dashboar
- description: GET /api/environments/{environment_id}/data_color_themes/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-data-color-themes-list
- description: POST /api/environments/{environment_id}/data_color_themes/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-data-color-themes-create
- description: GET /api/environments/{environment_id}/data_color_themes/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-data-color-themes-retrieve
- description: PUT /api/environments/{environment_id}/data_color_themes/{id}/
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: environments-data-color-themes-update
- description: PATCH /api/environments/{environment_id}/data_color_themes/{id}/
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: environments-data-color-themes-partial-update
- description: DELETE /api/environments/{environment_id}/data_color_themes/{id}/
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: environments-data-color-themes-destroy
- description: List data modeling jobs which are "runs" for our saved queries.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: environments-data-modeling-jobs-list
---
