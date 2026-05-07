---
categories: []
consumed_apis: []
description: Port API API capability.
layout: capability
name: Port API
operations:
- description: Get a blueprint's permissions
  method: GET
  name: get-v1-blueprints-blueprint-identifier-permissio
  path: /v1/blueprints/{blueprint_identifier}/permissions
- description: Update a blueprint's permissions
  method: PATCH
  name: patch-v1-blueprints-blueprint-identifier-permiss
  path: /v1/blueprints/{blueprint_identifier}/permissions
- description: Simulate permissions for a user
  method: POST
  name: post-v1-blueprints-blueprint-identifier-permissi
  path: /v1/blueprints/{blueprint_identifier}/permissions/simulate
- description: Get a page's permissions
  method: GET
  name: get-v1-pages-page-identifier-permissions
  path: /v1/pages/{page_identifier}/permissions
- description: Update a page's permissions
  method: PATCH
  name: patch-v1-pages-page-identifier-permissions
  path: /v1/pages/{page_identifier}/permissions
- description: Create an access token
  method: POST
  name: post-v1-auth-access-token
  path: /v1/auth/access_token
- description: Create an entity
  method: POST
  name: post-v1-blueprints-blueprint-identifier-entities
  path: /v1/blueprints/{blueprint_identifier}/entities
- description: Get all entities of a blueprint
  method: GET
  name: get-v1-blueprints-blueprint-identifier-entities
  path: /v1/blueprints/{blueprint_identifier}/entities
- description: Create multiple entities
  method: POST
  name: post-v1-blueprints-blueprint-identifier-entities
  path: /v1/blueprints/{blueprint_identifier}/entities/bulk
- description: Update an entity
  method: PATCH
  name: patch-v1-blueprints-blueprint-identifier-entitie
  path: /v1/blueprints/{blueprint_identifier}/entities/{entity_identifier}
- description: Change an entity
  method: PUT
  name: put-v1-blueprints-blueprint-identifier-entities-
  path: /v1/blueprints/{blueprint_identifier}/entities/{entity_identifier}
- description: Get an entity
  method: GET
  name: get-v1-blueprints-blueprint-identifier-entities-
  path: /v1/blueprints/{blueprint_identifier}/entities/{entity_identifier}
- description: Delete an entity
  method: DELETE
  name: delete-v1-blueprints-blueprint-identifier-entiti
  path: /v1/blueprints/{blueprint_identifier}/entities/{entity_identifier}
- description: Get a blueprint's entity count
  method: GET
  name: get-v1-blueprints-blueprint-identifier-entities-
  path: /v1/blueprints/{blueprint_identifier}/entities-count
- description: Delete all entities of a blueprint
  method: DELETE
  name: delete-v1-blueprints-blueprint-identifier-all-en
  path: /v1/blueprints/{blueprint_identifier}/all-entities
- description: Delete multiple entities
  method: POST
  name: post-v1-blueprints-blueprint-identifier-bulk-ent
  path: /v1/blueprints/{blueprint_identifier}/bulk/entities/delete
- description: Search entities
  method: POST
  name: post-v1-entities-search
  path: /v1/entities/search
- description: Search a blueprint's entities
  method: POST
  name: post-v1-blueprints-blueprint-identifier-entities
  path: /v1/blueprints/{blueprint_identifier}/entities/search
- description: Aggregate entities
  method: POST
  name: post-v1-entities-aggregate
  path: /v1/entities/aggregate
- description: Aggregate entities over time
  method: POST
  name: post-v1-entities-aggregate-over-time
  path: /v1/entities/aggregate-over-time
- description: Fetch the history of an entity's properties
  method: POST
  name: post-v1-entities-properties-history
  path: /v1/entities/properties-history
- description: Get all blueprints
  method: GET
  name: get-v1-blueprints
  path: /v1/blueprints
- description: Create a blueprint
  method: POST
  name: post-v1-blueprints
  path: /v1/blueprints
- description: Get a blueprint
  method: GET
  name: get-v1-blueprints-identifier
  path: /v1/blueprints/{identifier}
- description: Change a blueprint
  method: PUT
  name: put-v1-blueprints-identifier
  path: /v1/blueprints/{identifier}
- description: Update a blueprint
  method: PATCH
  name: patch-v1-blueprints-identifier
  path: /v1/blueprints/{identifier}
- description: Delete a blueprint
  method: DELETE
  name: delete-v1-blueprints-identifier
  path: /v1/blueprints/{identifier}
- description: Rename a property in a blueprint
  method: PATCH
  name: patch-v1-blueprints-blueprint-identifier-propert
  path: /v1/blueprints/{blueprint_identifier}/properties/{property_identifier}/rename
- description: Rename a blueprint's mirror property
  method: PATCH
  name: patch-v1-blueprints-blueprint-identifier-mirror-
  path: /v1/blueprints/{blueprint_identifier}/mirror/{property_identifier}/rename
- description: Rename a blueprint's relation
  method: PATCH
  name: patch-v1-blueprints-blueprint-identifier-relatio
  path: /v1/blueprints/{blueprint_identifier}/relations/{relation_identifier}/rename
- description: Create an action/automation
  method: POST
  name: post-v1-actions
  path: /v1/actions
- description: Get actions/automations
  method: GET
  name: get-v1-actions
  path: /v1/actions
- description: Change an action/automation
  method: PUT
  name: put-v1-actions-action-identifier
  path: /v1/actions/{action_identifier}
- description: Get an action/automation
  method: GET
  name: get-v1-actions-action-identifier
  path: /v1/actions/{action_identifier}
- description: Delete an action/automation
  method: DELETE
  name: delete-v1-actions-action-identifier
  path: /v1/actions/{action_identifier}
- description: This route is deprecated since November 20th 2024
  method: POST
  name: post-v1-blueprints-blueprint-identifier-actions
  path: /v1/blueprints/{blueprint_identifier}/actions
- description: This route is deprecated since November 20th 2024
  method: PUT
  name: put-v1-blueprints-blueprint-identifier-actions
  path: /v1/blueprints/{blueprint_identifier}/actions
- description: This route is deprecated since November 20th 2024
  method: GET
  name: get-v1-blueprints-blueprint-identifier-actions
  path: /v1/blueprints/{blueprint_identifier}/actions
- description: This route is deprecated since November 20th 2024
  method: PUT
  name: put-v1-blueprints-blueprint-identifier-actions-a
  path: /v1/blueprints/{blueprint_identifier}/actions/{action_identifier}
- description: This route is deprecated since November 20th 2024
  method: GET
  name: get-v1-blueprints-blueprint-identifier-actions-a
  path: /v1/blueprints/{blueprint_identifier}/actions/{action_identifier}
- description: This route is deprecated since November 20th 2024
  method: DELETE
  name: delete-v1-blueprints-blueprint-identifier-action
  path: /v1/blueprints/{blueprint_identifier}/actions/{action_identifier}
- description: Execute a self-service action
  method: POST
  name: post-v1-actions-action-identifier-runs
  path: /v1/actions/{action_identifier}/runs
- description: Update an action run
  method: PATCH
  name: patch-v1-actions-runs-run-id
  path: /v1/actions/runs/{run_id}
- description: Get an action run's details
  method: GET
  name: get-v1-actions-runs-run-id
  path: /v1/actions/runs/{run_id}
- description: Approve an action run
  method: PATCH
  name: patch-v1-actions-runs-run-id-approval
  path: /v1/actions/runs/{run_id}/approval
- description: Get all action runs
  method: GET
  name: get-v1-actions-runs
  path: /v1/actions/runs
- description: Add a log to an action run
  method: POST
  name: post-v1-actions-runs-run-id-logs
  path: /v1/actions/runs/{run_id}/logs
- description: Get an action's run logs
  method: GET
  name: get-v1-actions-runs-run-id-logs
  path: /v1/actions/runs/{run_id}/logs
- description: Get an action run's approvers
  method: GET
  name: get-v1-actions-runs-run-id-approvers
  path: /v1/actions/runs/{run_id}/approvers
- description: Get all pages in your portal
  method: GET
  name: get-v1-pages
  path: /v1/pages
- description: Create pages in your portal
  method: POST
  name: post-v1-pages
  path: /v1/pages
- description: Get a page
  method: GET
  name: get-v1-pages-identifier
  path: /v1/pages/{identifier}
- description: Patch a page
  method: PATCH
  name: patch-v1-pages-identifier
  path: /v1/pages/{identifier}
- description: Delete a page
  method: DELETE
  name: delete-v1-pages-identifier
  path: /v1/pages/{identifier}
- description: Duplicate a page
  method: POST
  name: post-v1-pages-identifier-duplicate
  path: /v1/pages/{identifier}/duplicate
- description: Create a widget
  method: POST
  name: post-v1-pages-page-identifier-widgets
  path: /v1/pages/{page_identifier}/widgets
- description: Update a widget
  method: PATCH
  name: patch-v1-pages-page-identifier-widgets-widget-id
  path: /v1/pages/{page_identifier}/widgets/{widget_id}
- description: Delete a widget
  method: DELETE
  name: delete-v1-pages-page-identifier-widgets-widget-i
  path: /v1/pages/{page_identifier}/widgets/{widget_id}
- description: Get organization details
  method: GET
  name: get-v1-organization
  path: /v1/organization
- description: Change organization details
  method: PUT
  name: put-v1-organization
  path: /v1/organization
personas: []
provider_name: Port
provider_slug: port
search_terms:
- post v1 pages page identifier widgets
- delete a widget
- create pages in your portal
- put v1 organization
- get v1 blueprints blueprint identifier permissio
- post v1 pages
- api
- patch a page
- change a blueprint
- post v1 entities search
- put v1 blueprints blueprint identifier actions a
- get an action/automation
- delete v1 actions action identifier
- port
- get v1 pages identifier
- patch v1 blueprints blueprint identifier propert
- get all entities of a blueprint
- fetch the history of an entity's properties
- execute a self-service action
- delete a page
- post v1 actions action identifier runs
- software catalog
- change an entity
- duplicate a page
- aggregate entities over time
- change an action/automation
- create an access token
- get v1 blueprints blueprint identifier entities
- patch v1 pages identifier
- get v1 blueprints blueprint identifier entities
- post v1 auth access token
- patch v1 actions runs run id approval
- post v1 blueprints blueprint identifier entities
- search a blueprint's entities
- search entities
- get an action run's approvers
- rename a blueprint's relation
- post v1 blueprints blueprint identifier bulk ent
- delete a blueprint
- get a blueprint's permissions
- patch v1 blueprints blueprint identifier relatio
- create an action/automation
- patch v1 blueprints blueprint identifier permiss
- get all blueprints
- create a blueprint
- delete v1 pages page identifier widgets widget i
- get v1 actions runs run id approvers
- get a page's permissions
- delete v1 pages identifier
- change organization details
- get organization details
- self-service
- get v1 organization
- update an entity
- delete v1 blueprints blueprint identifier all en
- get an entity
- post v1 actions
- patch v1 blueprints blueprint identifier mirror
- internal developer portal
- delete an entity
- get v1 blueprints blueprint identifier actions
- automations
- get v1 actions runs
- developer portals
- put v1 blueprints blueprint identifier entities
- get v1 actions runs run id logs
- this route is deprecated since november 20th 2024
- post v1 entities aggregate
- get actions/automations
- delete v1 blueprints blueprint identifier entiti
- create multiple entities
- rename a blueprint's mirror property
- get v1 pages page identifier permissions
- update a blueprint's permissions
- put v1 actions action identifier
- patch v1 blueprints blueprint identifier entitie
- delete v1 blueprints blueprint identifier action
- get v1 actions action identifier
- delete multiple entities
- post v1 entities aggregate over time
- delete all entities of a blueprint
- update a widget
- post v1 blueprints blueprint identifier permissi
- delete v1 blueprints identifier
- delete an action/automation
- post v1 blueprints
- get v1 actions
- post v1 blueprints blueprint identifier actions
- get all pages in your portal
- post v1 pages identifier duplicate
- get a blueprint's entity count
- get v1 pages
- simulate permissions for a user
- platform engineering
- get a blueprint
- update a page's permissions
- patch v1 blueprints identifier
- aggregate entities
- put v1 blueprints blueprint identifier actions
- post v1 entities properties history
- put v1 blueprints identifier
- patch v1 pages page identifier permissions
- update an action run
- get an action run's details
- scorecards
- get v1 blueprints identifier
- patch v1 actions runs run id
- get all action runs
- create an entity
- get v1 actions runs run id
- get an action's run logs
- rename a property in a blueprint
- get v1 blueprints blueprint identifier actions a
- approve an action run
- post v1 actions runs run id logs
- create a widget
- get a page
- update a blueprint
- patch v1 pages page identifier widgets widget id
- get v1 blueprints
- add a log to an action run
slug: port-capability
source_filename: port-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Port API\n  description: Port API API capability.\n  tags:\n  - Port\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: port\n    baseUri: https://api.example.com\n    description: Port API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PORT_TOKEN}}'\n    resources:\n    - name: v1-blueprints-blueprint-identifier-permissions\n      path: /v1/blueprints/{blueprint_identifier}/permissions\n      operations:\n      - name: get-v1-blueprints-blueprint-identifier-permissio\n        method: GET\n        description: Get a blueprint's permissions\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n      - name: patch-v1-blueprints-blueprint-identifier-permiss\n        method: PATCH\n        description: Update a blueprint's permissions\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-permissions-s\n      path: /v1/blueprints/{blueprint_identifier}/permissions/simulate\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-permissi\n        method: POST\n        description: Simulate permissions for a user\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier\
  \ of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-pages-page-identifier-permissions\n      path: /v1/pages/{page_identifier}/permissions\n      operations:\n      - name: get-v1-pages-page-identifier-permissions\n        method: GET\n        description: Get a page's permissions\n        inputParameters:\n        - name: page_identifier\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v1-pages-page-identifier-permissions\n        method: PATCH\n        description: Update a page's permissions\n        inputParameters:\n        - name: page_identifier\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: v1-auth-access-token\n      path: /v1/auth/access_token\n      operations:\n      - name: post-v1-auth-access-token\n        method: POST\n        description: Create an access token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-entities\n      path: /v1/blueprints/{blueprint_identifier}/entities\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-entities\n        method: POST\n        description: Create an entity\n        inputParameters:\n        - name: upsert\n          in: query\n          type: boolean\n          required: true\n          description: If `true`, this call will override the entire entity/ies, if it/they already exist/s.\n        - name: validation_only\n          in: query\n          type: boolean\n          description: If `true`, this call will only validate\
  \ the entity/ies and return the validation errors.\n        - name: create_missing_related_entities\n          in: query\n          type: boolean\n          description: If `true`, this call will also create missing related entities.<br/>This is useful when you want to\n            create an entity and its related entities in one call, or if\n        - name: merge\n          in: query\n          type: boolean\n          description: If `true` and `upsert` is also `true`, this call will update the entity/ies, if it/they already exist/s.\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n\
  \          in: query\n          type: string\n          description: How the operation was triggered.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-blueprints-blueprint-identifier-entities\n        method: GET\n        description: Get all entities of a blueprint\n        inputParameters:\n        - name: exclude_calculated_properties\n          in: query\n          type: boolean\n          description: If `true`, [calculated properties](https://docs.getport.io/build-your-software-catalog/customize-integrations/configure-data-model/setup-blueprint/properties/ca\n        - name: include\n          in: query\n          type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure).\n\
  \            Only these values will be retu\n        - name: exclude\n          in: query\n          type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure)\n            to be ommitted from the respons\n        - name: attach_title_to_relation\n          in: query\n          type: boolean\n        - name: attach_identifier_to_title_mirror_properties\n          in: query\n          type: boolean\n        - name: allow_partial_results\n          in: query\n          type: boolean\n          description: When enabled allows some of the blueprint searches to fail without failing the full request.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n    - name: v1-blueprints-blueprint-identifier-entities-bulk\n      path: /v1/blueprints/{blueprint_identifier}/entities/bulk\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-entities\n        method: POST\n        description: Create multiple entities\n        inputParameters:\n        - name: upsert\n          in: query\n          type: boolean\n          required: true\n          description: If `true`, this call will override the entire entity/ies, if it/they already exist/s.\n        - name: validation_only\n          in: query\n          type: boolean\n          description: If `true`, this call will only validate the entity/ies and return the validation errors.\n        - name: create_missing_related_entities\n          in: query\n          type: boolean\n          description: If `true`, this call will also create missing related entities.<br/>This is useful when you want to\n            create an entity and its related entities in one\
  \ call, or if\n        - name: merge\n          in: query\n          type: boolean\n          description: If `true` and `upsert` is also `true`, this call will update the entity/ies, if it/they already exist/s.\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n          description: How the operation was triggered.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-entities-enti\n      path: /v1/blueprints/{blueprint_identifier}/entities/{entity_identifier}\n      operations:\n      - name: patch-v1-blueprints-blueprint-identifier-entitie\n        method: PATCH\n        description: Update an entity\n        inputParameters:\n        - name: create_missing_related_entities\n          in: query\n          type: boolean\n          description: If `true`, this call will also create missing related entities.<br/>This is useful when you want to\n            create an entity and its related entities in one call, or if\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n    \
  \      in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n          description: How the operation was triggered.\n        - name: entity_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the entity to operate on.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-blueprints-blueprint-identifier-entities-\n        method: PUT\n        description: Change an entity\n        inputParameters:\n        - name: create_missing_related_entities\n          in: query\n          type: boolean\n\
  \          description: If `true`, this call will also create missing related entities.<br/>This is useful when you want to\n            create an entity and its related entities in one call, or if\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n          description: How the operation was triggered.\n        - name: entity_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the entity to operate on.\n        - name: blueprint_identifier\n          in:\
  \ path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-blueprints-blueprint-identifier-entities-\n        method: GET\n        description: Get an entity\n        inputParameters:\n        - name: exclude_calculated_properties\n          in: query\n          type: boolean\n          description: If `true`, [calculated properties](https://docs.getport.io/build-your-software-catalog/customize-integrations/configure-data-model/setup-blueprint/properties/ca\n        - name: include\n          in: query\n          type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure).\n            Only these values will be retu\n        - name: exclude\n          in: query\n     \
  \     type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure)\n            to be ommitted from the respons\n        - name: attach_title_to_relation\n          in: query\n          type: boolean\n        - name: attach_identifier_to_title_mirror_properties\n          in: query\n          type: boolean\n        - name: allow_partial_results\n          in: query\n          type: boolean\n          description: When enabled allows some of the blueprint searches to fail without failing the full request.\n        - name: entity_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the entity to operate on.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-blueprints-blueprint-identifier-entiti\n        method: DELETE\n        description: Delete an entity\n        inputParameters:\n        - name: delete_dependents\n          in: query\n          type: boolean\n          required: true\n          description: If `true`, this call will also delete all entities with a relation to the deleted entity.\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n        \
  \  description: How the operation was triggered.\n        - name: entity_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the entity to operate on.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-entities-coun\n      path: /v1/blueprints/{blueprint_identifier}/entities-count\n      operations:\n      - name: get-v1-blueprints-blueprint-identifier-entities-\n        method: GET\n        description: Get a blueprint's entity count\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint\
  \ to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-all-entities\n      path: /v1/blueprints/{blueprint_identifier}/all-entities\n      operations:\n      - name: delete-v1-blueprints-blueprint-identifier-all-en\n        method: DELETE\n        description: Delete all entities of a blueprint\n        inputParameters:\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the deleted entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n          description:\
  \ How the operation was triggered.\n        - name: delete_blueprint\n          in: query\n          type: boolean\n          description: If `true`, this call will also delete the blueprint itself.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-bulk-entities\n      path: /v1/blueprints/{blueprint_identifier}/bulk/entities/delete\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-bulk-ent\n        method: POST\n        description: Delete multiple entities\n        inputParameters:\n        - name: delete_dependents\n          in: query\n          type: boolean\n          required: true\n          description: If `true`, this call will also delete all entities with\
  \ a relation to the deleted entity.\n        - name: run_id\n          in: query\n          type: string\n          description: You can provide a `run_id` to associate the created entities with a specific [action run](https://docs.port.io/create-self-service-experiences/reflect-action-pr\n        - name: ocean_info_resync_id\n          in: query\n          type: string\n          description: Resync run identifier. Only valid when `ocean_info_event_type` is `resync`.\n        - name: ocean_info_event_type\n          in: query\n          type: string\n          description: How the operation was triggered.\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-entities-search\n      path: /v1/entities/search\n      operations:\n\
  \      - name: post-v1-entities-search\n        method: POST\n        description: Search entities\n        inputParameters:\n        - name: exclude_calculated_properties\n          in: query\n          type: boolean\n          description: If `true`, [calculated properties](https://docs.getport.io/build-your-software-catalog/customize-integrations/configure-data-model/setup-blueprint/properties/ca\n        - name: include\n          in: query\n          type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure).\n            Only these values will be retu\n        - name: exclude\n          in: query\n          type: array\n          description: An array of values from the [entity JSON](https://docs.port.io/build-your-software-catalog/sync-data-to-catalog/#json-structure)\n            to be ommitted from the respons\n        - name: attach_title_to_relation\n          in: query\n\
  \          type: boolean\n        - name: attach_identifier_to_title_mirror_properties\n          in: query\n          type: boolean\n        - name: allow_partial_results\n          in: query\n          type: boolean\n          description: When enabled allows some of the blueprint searches to fail without failing the full request.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-entities-sear\n      path: /v1/blueprints/{blueprint_identifier}/entities/search\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-entities\n        method: POST\n        description: Search a blueprint's entities\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint whose entities you want to search.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-entities-aggregate\n      path: /v1/entities/aggregate\n      operations:\n      - name: post-v1-entities-aggregate\n        method: POST\n        description: Aggregate entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-entities-aggregate-over-time\n      path: /v1/entities/aggregate-over-time\n      operations:\n      - name: post-v1-entities-aggregate-over-time\n        method: POST\n        description: Aggregate entities over time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-entities-properties-history\n      path: /v1/entities/properties-history\n      operations:\n      - name: post-v1-entities-properties-history\n        method: POST\n        description: Fetch the history\
  \ of an entity's properties\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints\n      path: /v1/blueprints\n      operations:\n      - name: get-v1-blueprints\n        method: GET\n        description: Get all blueprints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-blueprints\n        method: POST\n        description: Create a blueprint\n        inputParameters:\n        - name: create_catalog_page\n          in: query\n          type: boolean\n          description: If true, a catalog page will be created for this blueprint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-identifier\n      path: /v1/blueprints/{identifier}\n      operations:\n      - name: get-v1-blueprints-identifier\n\
  \        method: GET\n        description: Get a blueprint\n        inputParameters:\n        - name: identifier\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the resource you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-blueprints-identifier\n        method: PUT\n        description: Change a blueprint\n        inputParameters:\n        - name: identifier\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the resource you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v1-blueprints-identifier\n        method: PATCH\n        description: Update a blueprint\n        inputParameters:\n        - name: identifier\n\
  \          in: path\n          type: string\n          required: true\n          description: The unique identifier of the resource you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-blueprints-identifier\n        method: DELETE\n        description: Delete a blueprint\n        inputParameters:\n        - name: delete_actions\n          in: query\n          type: boolean\n          description: If `true`, all self-service actions associated with this blueprint will be deleted as well.\n        - name: identifier\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the resource you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-properties-pr\n      path:\
  \ /v1/blueprints/{blueprint_identifier}/properties/{property_identifier}/rename\n      operations:\n      - name: patch-v1-blueprints-blueprint-identifier-propert\n        method: PATCH\n        description: Rename a property in a blueprint\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint you want to change.\n        - name: property_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the property you want to rename.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-mirror-proper\n      path: /v1/blueprints/{blueprint_identifier}/mirror/{property_identifier}/rename\n      operations:\n      - name: patch-v1-blueprints-blueprint-identifier-mirror-\n      \
  \  method: PATCH\n        description: Rename a blueprint's mirror property\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the blueprint you want to change.\n        - name: property_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the property you want to rename.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-relations-rel\n      path: /v1/blueprints/{blueprint_identifier}/relations/{relation_identifier}/rename\n      operations:\n      - name: patch-v1-blueprints-blueprint-identifier-relatio\n        method: PATCH\n        description: Rename a blueprint's relation\n        inputParameters:\n        - name: blueprint_identifier\n          in: path\n         \
  \ type: string\n          required: true\n          description: The identifier of the blueprint you want to change.\n        - name: relation_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the relation you want to rename.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-actions\n      path: /v1/actions\n      operations:\n      - name: post-v1-actions\n        method: POST\n        description: Create an action/automation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-actions\n        method: GET\n        description: Get actions/automations\n        inputParameters:\n        - name: action_identifier\n          in: query\n          type: array\n          description: The identifier/s of the action/s and/or automation/s\
  \ you want to fetch.\n        - name: blueprint_identifier\n          in: query\n          type: array\n          description: The identifier/s of the blueprint/s whose actions/automations you wish to fetch.\n        - name: operation\n          in: query\n          type: array\n          description: The [operation type/s](https://docs.port.io/create-self-service-experiences/setup-ui-for-action/#basic-details)\n            of the action/s you want to fetch. Relevant only\n        - name: published\n          in: query\n          type: boolean\n          description: Only relevant for **automations**. If `true`, only published automations will be fetched.\n        - name: trigger_type\n          in: query\n          type: string\n        - name: trigger_event\n          in: query\n          type: array\n          description: The event/s that triggered the automation/s you want to fetch. Relevant only for automations.\n        - name: trigger_event_action_identifier\n          in: query\n\
  \          type: array\n        - name: version\n          in: query\n          type: string\n          description: Specifies the API version to use. Please use `v2` for the latest version of the API.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-actions-action-identifier\n      path: /v1/actions/{action_identifier}\n      operations:\n      - name: put-v1-actions-action-identifier\n        method: PUT\n        description: Change an action/automation\n        inputParameters:\n        - name: action_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the action/automation you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-actions-action-identifier\n        method: GET\n        description: Get an action/automation\n\
  \        inputParameters:\n        - name: action_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the action/automation you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-actions-action-identifier\n        method: DELETE\n        description: Delete an action/automation\n        inputParameters:\n        - name: action_identifier\n          in: path\n          type: string\n          required: true\n          description: The identifier of the action/automation you want to operate on.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-actions\n      path: /v1/blueprints/{blueprint_identifier}/actions\n      operations:\n      - name: post-v1-blueprints-blueprint-identifier-actions\n\
  \        method: POST\n        description: This route is deprecated since November 20th 2024\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: nullable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-v1-blueprints-blueprint-identifier-actions\n        method: PUT\n        description: This route is deprecated since November 20th 2024\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: nullable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-blueprints-blueprint-identifier-actions\n     \
  \   method: GET\n        description: This route is deprecated since November 20th 2024\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: nullable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-blueprints-blueprint-identifier-actions-actio\n      path: /v1/blueprints/{blueprint_identifier}/actions/{action_identifier}\n      operations:\n      - name: put-v1-blueprints-blueprint-identifier-actions-a\n        method: PUT\n        description: This route is deprecated since November 20th 2024\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: nullable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-blueprints-blueprint-identifier-actions-a\n        method: GET\n        description: This route is deprecated since November 20th 2024\n        inputParameters:\n        - name: type\n          in: path\n          type: string\n          required: true\n        - name: nullable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\n# --- truncated at 32 KB (115 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/port/refs/heads/main/capabilities/port-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/port/refs/heads/main/capabilities/port-capability.yaml
tags:
- Port
- API
tools:
- description: Get a blueprint's permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-permissio
- description: Update a blueprint's permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-blueprint-identifier-permiss
- description: Simulate permissions for a user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-permissi
- description: Get a page's permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-pages-page-identifier-permissions
- description: Update a page's permissions
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-pages-page-identifier-permissions
- description: Create an access token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-auth-access-token
- description: Create an entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-entities
- description: Get all entities of a blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-entities
- description: Create multiple entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-entities
- description: Update an entity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-blueprint-identifier-entitie
- description: Change an entity
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-blueprints-blueprint-identifier-entities-
- description: Get an entity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-entities-
- description: Delete an entity
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-blueprints-blueprint-identifier-entiti
- description: Get a blueprint's entity count
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-entities-
- description: Delete all entities of a blueprint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-blueprints-blueprint-identifier-all-en
- description: Delete multiple entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-bulk-ent
- description: Search entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-entities-search
- description: Search a blueprint's entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-entities
- description: Aggregate entities
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-entities-aggregate
- description: Aggregate entities over time
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-entities-aggregate-over-time
- description: Fetch the history of an entity's properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-entities-properties-history
- description: Get all blueprints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints
- description: Create a blueprint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints
- description: Get a blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-identifier
- description: Change a blueprint
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-blueprints-identifier
- description: Update a blueprint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-identifier
- description: Delete a blueprint
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-blueprints-identifier
- description: Rename a property in a blueprint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-blueprint-identifier-propert
- description: Rename a blueprint's mirror property
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-blueprint-identifier-mirror-
- description: Rename a blueprint's relation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-blueprints-blueprint-identifier-relatio
- description: Create an action/automation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-actions
- description: Get actions/automations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions
- description: Change an action/automation
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-actions-action-identifier
- description: Get an action/automation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions-action-identifier
- description: Delete an action/automation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-actions-action-identifier
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-blueprints-blueprint-identifier-actions
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-blueprints-blueprint-identifier-actions
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-actions
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-blueprints-blueprint-identifier-actions-a
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-blueprints-blueprint-identifier-actions-a
- description: This route is deprecated since November 20th 2024
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-blueprints-blueprint-identifier-action
- description: Execute a self-service action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-actions-action-identifier-runs
- description: Update an action run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-actions-runs-run-id
- description: Get an action run's details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions-runs-run-id
- description: Approve an action run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-actions-runs-run-id-approval
- description: Get all action runs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions-runs
- description: Add a log to an action run
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-actions-runs-run-id-logs
- description: Get an action's run logs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions-runs-run-id-logs
- description: Get an action run's approvers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-actions-runs-run-id-approvers
- description: Get all pages in your portal
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-pages
- description: Create pages in your portal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-pages
- description: Get a page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-pages-identifier
- description: Patch a page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-pages-identifier
- description: Delete a page
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-pages-identifier
- description: Duplicate a page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-pages-identifier-duplicate
- description: Create a widget
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-pages-page-identifier-widgets
- description: Update a widget
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-pages-page-identifier-widgets-widget-id
- description: Delete a widget
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-pages-page-identifier-widgets-widget-i
- description: Get organization details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-organization
- description: Change organization details
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-v1-organization
---
