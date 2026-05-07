---
categories: []
consumed_apis: []
description: 'You''re looking at the current **stable** documentation of the OpenProject APIv3. If you''re interested in the current development version, please go to [github.com/opf](https://github.com/opf/openproject/tree/dev/docs/api/apiv3). ## Introduction The documentation for the APIv3 is written according to the [OpenAPI 3.1 Specification](https://swagger.io/specification/). You can either view the static version of this documentation on the [website](https://www.openproject.org/docs/api/introduction/) or the interactive version, rendered with [OpenAPI Explorer](https://github.com/Rhosys/openapi-explor'
layout: capability
name: OpenProject API V3 (Stable)
operations:
- description: View root
  method: GET
  name: view-root
  path: /api/v3
- description: List actions
  method: GET
  name: list-actions
  path: /api/v3/actions
- description: View action
  method: GET
  name: view-action
  path: /api/v3/actions/{id}
- description: Get an activity
  method: GET
  name: get-activity
  path: /api/v3/activities/{id}
- description: Update activity
  method: PATCH
  name: update-activity
  path: /api/v3/activities/{id}
- description: List attachments by activity
  method: GET
  name: list-activity-attachments
  path: /api/v3/activities/{id}/attachments
- description: Add attachment to activity
  method: POST
  name: create-activity-attachment
  path: /api/v3/activities/{id}/attachments
- description: List emoji reactions by activity
  method: GET
  name: list-activity-emoji-reactions
  path: /api/v3/activities/{id}/emoji_reactions
- description: Toggle emoji reaction for an activity
  method: PATCH
  name: toggle-activity-emoji-reaction
  path: /api/v3/activities/{id}/emoji_reactions
- description: Create Attachment
  method: POST
  name: create-attachment
  path: /api/v3/attachments
- description: Delete attachment
  method: DELETE
  name: delete-attachment
  path: /api/v3/attachments/{id}
- description: View attachment
  method: GET
  name: view-attachment
  path: /api/v3/attachments/{id}
- description: view Budget
  method: GET
  name: view-budget
  path: /api/v3/budgets/{id}
- description: List capabilities
  method: GET
  name: list-capabilities
  path: /api/v3/capabilities
- description: View global context
  method: GET
  name: view-global-context
  path: /api/v3/capabilities/context/global
- description: View capabilities
  method: GET
  name: view-capabilities
  path: /api/v3/capabilities/{id}
- description: View Category
  method: GET
  name: view-category
  path: /api/v3/categories/{id}
- description: View configuration
  method: GET
  name: view-configuration
  path: /api/v3/configuration
- description: Get a custom action
  method: GET
  name: get-custom-action
  path: /api/v3/custom_actions/{id}
- description: Execute custom action
  method: POST
  name: execute-custom-action
  path: /api/v3/custom_actions/{id}/execute
- description: Get the custom field hierarchy items
  method: GET
  name: get-custom-field-items
  path: /api/v3/custom_fields/{id}/items
- description: Get a custom field hierarchy item
  method: GET
  name: get-custom-field-item
  path: /api/v3/custom_field_items/{id}
- description: Get a custom field hierarchy item's branch
  method: GET
  name: get-custom-field-item-branch
  path: /api/v3/custom_field_items/{id}/branch
- description: View Custom Option
  method: GET
  name: view-custom-option
  path: /api/v3/custom_options/{id}
- description: Lists all non working days
  method: GET
  name: list-non-working-days
  path: /api/v3/days/non_working
- description: Creates a non-working day (NOT IMPLEMENTED)
  method: POST
  name: create-non-working-day
  path: /api/v3/days/non_working
- description: View a non-working day
  method: GET
  name: view-non-working-day
  path: /api/v3/days/non_working/{date}
- description: Update a non-working day attributes (NOT IMPLEMENTED)
  method: PATCH
  name: update-non-working-day
  path: /api/v3/days/non_working/{date}
- description: Removes a non-working day (NOT IMPLEMENTED)
  method: DELETE
  name: delete-non-working-day
  path: /api/v3/days/non_working/{date}
- description: Lists week days
  method: GET
  name: list-week-days
  path: /api/v3/days/week
- description: Update week days (NOT IMPLEMENTED)
  method: PATCH
  name: update-week-days
  path: /api/v3/days/week
- description: View a week day
  method: GET
  name: view-week-day
  path: /api/v3/days/week/{day}
- description: Update a week day attributes (NOT IMPLEMENTED)
  method: PATCH
  name: update-week-day
  path: /api/v3/days/week/{day}
- description: Lists days
  method: GET
  name: list-days
  path: /api/v3/days
- description: View day
  method: GET
  name: view-day
  path: /api/v3/days/{date}
- description: List Documents
  method: GET
  name: list-documents
  path: /api/v3/documents
- description: View document
  method: GET
  name: view-document
  path: /api/v3/documents/{id}
- description: Update document
  method: PATCH
  name: update-document
  path: /api/v3/documents/{id}
- description: show or validate form
  method: POST
  name: show-or-validate-form
  path: /api/v3/example/form
- description: view the schema
  method: GET
  name: view-the-schema
  path: /api/v3/example/schema
- description: view aggregated result
  method: GET
  name: view-aggregated-result
  path: /api/v3/examples
- description: Gets a file link.
  method: GET
  name: view-file-link
  path: /api/v3/file_links/{id}
- description: Removes a file link.
  method: DELETE
  name: delete-file-link
  path: /api/v3/file_links/{id}
- description: Creates an opening uri of the linked file.
  method: GET
  name: open-file-link
  path: /api/v3/file_links/{id}/open
- description: Creates a download uri of the linked file.
  method: GET
  name: download-file-link
  path: /api/v3/file_links/{id}/download
- description: List grids
  method: GET
  name: list-grids
  path: /api/v3/grids
- description: Create a grid
  method: POST
  name: create-grid
  path: /api/v3/grids
- description: Grid Create Form
  method: POST
  name: grid-create-form
  path: /api/v3/grids/form
- description: Get a grid
  method: GET
  name: get-grid
  path: /api/v3/grids/{id}
- description: Update a grid
  method: PATCH
  name: update-grid
  path: /api/v3/grids/{id}
- description: Grid Update Form
  method: POST
  name: grid-update-form
  path: /api/v3/grids/{id}/form
- description: List groups
  method: GET
  name: list-groups
  path: /api/v3/groups
- description: Create group
  method: POST
  name: create-group
  path: /api/v3/groups
- description: Delete group
  method: DELETE
  name: delete-group
  path: /api/v3/groups/{id}
- description: Get group
  method: GET
  name: get-group
  path: /api/v3/groups/{id}
- description: Update group
  method: PATCH
  name: update-group
  path: /api/v3/groups/{id}
- description: List help texts
  method: GET
  name: list-help-texts
  path: /api/v3/help_texts
- description: Get help text
  method: GET
  name: get-help-text
  path: /api/v3/help_texts/{id}
- description: List all visible meetings
  method: GET
  name: list-meetings
  path: /api/v3/meetings
- description: Get a meeting
  method: GET
  name: get-meeting
  path: /api/v3/meetings/{id}
personas: []
provider_name: OpenProject
provider_slug: openproject
search_terms:
- add attachment to activity
- list attachments by activity
- list non working days
- api
- lists days
- get custom field item
- get custom field items
- update document
- update a week day attributes (not implemented)
- list actions
- get group
- removes a non-working day (not implemented)
- get the custom field hierarchy items
- view capabilities
- view the schema
- get meeting
- create attachment
- view root
- create a grid
- get a custom action
- list documents
- delete group
- create activity attachment
- get a grid
- create grid
- removes a file link.
- list groups
- create non working day
- delete attachment
- list week days
- delete file link
- list meetings
- view custom option
- view action
- open file link
- update activity
- agile
- view category
- view day
- creates an opening uri of the linked file.
- view file link
- view configuration
- update grid
- update a non-working day attributes (not implemented)
- download file link
- get a custom field hierarchy item's branch
- list help texts
- view document
- time tracking
- update week days
- list activity emoji reactions
- gets a file link.
- view a week day
- grid create form
- execute custom action
- update week days (not implemented)
- view global context
- project management
- update a grid
- delete non working day
- toggle activity emoji reaction
- get an activity
- openproject
- show or validate form
- list all visible meetings
- list activity attachments
- grid update form
- update group
- create group
- get a meeting
- get activity
- list days
- view budget
- list emoji reactions by activity
- view attachment
- open source
- gantt
- get a custom field hierarchy item
- lists all non working days
- view non working day
- view week day
- toggle emoji reaction for an activity
- list grids
- work packages
- update week day
- get custom field item branch
- update non working day
- creates a non-working day (not implemented)
- get custom action
- get help text
- view aggregated result
- creates a download uri of the linked file.
- list capabilities
- lists week days
- get grid
- view a non-working day
slug: openproject-capability
source_filename: openproject-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenProject API V3 (Stable)\n  description: 'You''re looking at the current **stable** documentation of the OpenProject APIv3. If you''re interested in\n    the current development version, please go to [github.com/opf](https://github.com/opf/openproject/tree/dev/docs/api/apiv3).\n    ## Introduction The documentation for the APIv3 is written according to the [OpenAPI 3.1 Specification](https://swagger.io/specification/).\n    You can either view the static version of this documentation on the [website](https://www.openproject.org/docs/api/introduction/)\n    or the interactive version, rendered with [OpenAPI Explorer](https://github.com/Rhosys/openapi-explor'\n  tags:\n  - Openproject\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openproject\n    baseUri: https://qa.openproject-edge.com\n    description: OpenProject API V3 (Stable) HTTP API.\n    authentication:\n\
  \      type: basic\n      username: '{{OPENPROJECT_USERNAME}}'\n      password: '{{OPENPROJECT_PASSWORD}}'\n    resources:\n    - name: api-v3\n      path: /api/v3\n      operations:\n      - name: view-root\n        method: GET\n        description: View root\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-actions\n      path: /api/v3/actions\n      operations:\n      - name: list-actions\n        method: GET\n        description: List actions\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description: JSON specifying filter conditions. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Curre\n        - name: sortBy\n          in: query\n          type: string\n          description: JSON specifying sort criteria. Accepts the same format as returned\
  \ by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Currently\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-actions-id\n      path: /api/v3/actions/{id}\n      operations:\n      - name: view-action\n        method: GET\n        description: View action\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: action id which is the name of the action\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-activities-id\n      path: /api/v3/activities/{id}\n      operations:\n      - name: get-activity\n        method: GET\n        description: Get an activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required:\
  \ true\n          description: Activity id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-activity\n        method: PATCH\n        description: Update activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Activity id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-activities-id-attachments\n      path: /api/v3/activities/{id}/attachments\n      operations:\n      - name: list-activity-attachments\n        method: GET\n        description: List attachments by activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the activity whose attachments will be listed\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-activity-attachment\n        method: POST\n        description: Add attachment to activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the activity to receive the attachment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-activities-id-emoji-reactions\n      path: /api/v3/activities/{id}/emoji_reactions\n      operations:\n      - name: list-activity-emoji-reactions\n        method: GET\n        description: List emoji reactions by activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the activity whose emoji reactions will be listed\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: toggle-activity-emoji-reaction\n        method: PATCH\n        description: Toggle emoji reaction for an activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the activity to toggle emoji reaction for\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-attachments\n      path: /api/v3/attachments\n      operations:\n      - name: create-attachment\n        method: POST\n        description: Create Attachment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-attachments-id\n      path: /api/v3/attachments/{id}\n      operations:\n      - name: delete-attachment\n        method: DELETE\n        description: Delete attachment\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Attachment id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: view-attachment\n        method: GET\n        description: View attachment\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Attachment id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-budgets-id\n      path: /api/v3/budgets/{id}\n      operations:\n      - name: view-budget\n        method: GET\n        description: view Budget\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Budget id\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-capabilities\n      path: /api/v3/capabilities\n      operations:\n      - name: list-capabilities\n        method: GET\n        description: List capabilities\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description: JSON specifying filter conditions. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. + act\n        - name: sortBy\n          in: query\n          type: string\n          description: JSON specifying sort criteria. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Currently\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-capabilities-context-global\n\
  \      path: /api/v3/capabilities/context/global\n      operations:\n      - name: view-global-context\n        method: GET\n        description: View global context\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-capabilities-id\n      path: /api/v3/capabilities/{id}\n      operations:\n      - name: view-capabilities\n        method: GET\n        description: View capabilities\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: capability id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-categories-id\n      path: /api/v3/categories/{id}\n      operations:\n      - name: view-category\n        method: GET\n        description: View Category\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: integer\n          required: true\n          description: Category id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-configuration\n      path: /api/v3/configuration\n      operations:\n      - name: view-configuration\n        method: GET\n        description: View configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-custom-actions-id\n      path: /api/v3/custom_actions/{id}\n      operations:\n      - name: get-custom-action\n        method: GET\n        description: Get a custom action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The id of the custom action to fetch\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-v3-custom-actions-id-execute\n      path: /api/v3/custom_actions/{id}/execute\n      operations:\n      - name: execute-custom-action\n        method: POST\n        description: Execute custom action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The id of the custom action to execute\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-custom-fields-id-items\n      path: /api/v3/custom_fields/{id}/items\n      operations:\n      - name: get-custom-field-items\n        method: GET\n        description: Get the custom field hierarchy items\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The custom field's unique identifier\n        - name: parent\n          in: query\n    \
  \      type: integer\n          description: The identifier of the parent hierarchy item\n        - name: depth\n          in: query\n          type: integer\n          description: The level of hierarchy depth\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-custom-field-items-id\n      path: /api/v3/custom_field_items/{id}\n      operations:\n      - name: get-custom-field-item\n        method: GET\n        description: Get a custom field hierarchy item\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The custom field item's unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-custom-field-items-id-branch\n      path: /api/v3/custom_field_items/{id}/branch\n      operations:\n      - name:\
  \ get-custom-field-item-branch\n        method: GET\n        description: Get a custom field hierarchy item's branch\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The custom field item's unique identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-custom-options-id\n      path: /api/v3/custom_options/{id}\n      operations:\n      - name: view-custom-option\n        method: GET\n        description: View Custom Option\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: The custom option's identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days-non-working\n      path: /api/v3/days/non_working\n   \
  \   operations:\n      - name: list-non-working-days\n        method: GET\n        description: Lists all non working days\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description: JSON specifying filter conditions. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Curre\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-non-working-day\n        method: POST\n        description: Creates a non-working day (NOT IMPLEMENTED)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days-non-working-date\n      path: /api/v3/days/non_working/{date}\n      operations:\n      - name: view-non-working-day\n        method: GET\n        description: View a non-working\
  \ day\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: The date of the non-working day to view in ISO 8601 format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-non-working-day\n        method: PATCH\n        description: Update a non-working day attributes (NOT IMPLEMENTED)\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: The date of the non-working day to view in ISO 8601 format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-non-working-day\n        method: DELETE\n        description: Removes a non-working day (NOT IMPLEMENTED)\n        inputParameters:\n        - name: date\n          in: path\n \
  \         type: string\n          required: true\n          description: The date of the non-working day to view in ISO 8601 format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days-week\n      path: /api/v3/days/week\n      operations:\n      - name: list-week-days\n        method: GET\n        description: Lists week days\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-week-days\n        method: PATCH\n        description: Update week days (NOT IMPLEMENTED)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days-week-day\n      path: /api/v3/days/week/{day}\n      operations:\n      - name: view-week-day\n        method: GET\n        description: View a week day\n        inputParameters:\n\
  \        - name: day\n          in: path\n          type: integer\n          required: true\n          description: The week day from 1 to 7. 1 is Monday. 7 is Sunday.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-week-day\n        method: PATCH\n        description: Update a week day attributes (NOT IMPLEMENTED)\n        inputParameters:\n        - name: day\n          in: path\n          type: integer\n          required: true\n          description: The week day from 1 to 7. 1 is Monday. 7 is Sunday.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days\n      path: /api/v3/days\n      operations:\n      - name: list-days\n        method: GET\n        description: Lists days\n        inputParameters:\n        - name: filters\n          in: query\n          type: string\n          description:\
  \ JSON specifying filter conditions. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Curre\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-days-date\n      path: /api/v3/days/{date}\n      operations:\n      - name: view-day\n        method: GET\n        description: View day\n        inputParameters:\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: The date of the non-working day to view in ISO 8601 format.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-documents\n      path: /api/v3/documents\n      operations:\n      - name: list-documents\n        method: GET\n        description: List Documents\n        inputParameters:\n        - name:\
  \ offset\n          in: query\n          type: integer\n          description: Page number inside the requested collection.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of elements to display per page.\n        - name: sortBy\n          in: query\n          type: string\n          description: JSON specifying sort criteria. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Currently\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-documents-id\n      path: /api/v3/documents/{id}\n      operations:\n      - name: view-document\n        method: GET\n        description: View document\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Document id\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-document\n        method: PATCH\n        description: Update document\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Document id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-example-form\n      path: /api/v3/example/form\n      operations:\n      - name: show-or-validate-form\n        method: POST\n        description: show or validate form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-example-schema\n      path: /api/v3/example/schema\n      operations:\n      - name: view-the-schema\n        method: GET\n        description: view the schema\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-examples\n      path: /api/v3/examples\n      operations:\n      - name: view-aggregated-result\n        method: GET\n        description: view aggregated result\n        inputParameters:\n        - name: groupBy\n          in: query\n          type: string\n          description: 'The column to group by. Note: Aggregation is as of now only supported by the work package collection.\n            You can pass any column name as returned by the [queries]('\n        - name: showSums\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-file-links-id\n      path: /api/v3/file_links/{id}\n      operations:\n      - name: view-file-link\n        method: GET\n        description: Gets a file link.\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: integer\n          required: true\n          description: File link id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-file-link\n        method: DELETE\n        description: Removes a file link.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: File link id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-file-links-id-open\n      path: /api/v3/file_links/{id}/open\n      operations:\n      - name: open-file-link\n        method: GET\n        description: Creates an opening uri of the linked file.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: File link id\n        - name:\
  \ location\n          in: query\n          type: boolean\n          description: Boolean flag indicating, if the file should be opened directly or rather the directory location.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-file-links-id-download\n      path: /api/v3/file_links/{id}/download\n      operations:\n      - name: download-file-link\n        method: GET\n        description: Creates a download uri of the linked file.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: File link id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-grids\n      path: /api/v3/grids\n      operations:\n      - name: list-grids\n        method: GET\n        description: List grids\n        inputParameters:\n      \
  \  - name: offset\n          in: query\n          type: integer\n          description: Page number inside the requested collection.\n        - name: pageSize\n          in: query\n          type: integer\n          description: Number of elements to display per page.\n        - name: filters\n          in: query\n          type: string\n          description: JSON specifying filter conditions. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Curre\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-grid\n        method: POST\n        description: Create a grid\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-grids-form\n      path: /api/v3/grids/form\n      operations:\n      - name: grid-create-form\n        method:\
  \ POST\n        description: Grid Create Form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-grids-id\n      path: /api/v3/grids/{id}\n      operations:\n      - name: get-grid\n        method: GET\n        description: Get a grid\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Grid id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-grid\n        method: PATCH\n        description: Update a grid\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Grid id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-grids-id-form\n\
  \      path: /api/v3/grids/{id}/form\n      operations:\n      - name: grid-update-form\n        method: POST\n        description: Grid Update Form\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the grid being modified\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-groups\n      path: /api/v3/groups\n      operations:\n      - name: list-groups\n        method: GET\n        description: List groups\n        inputParameters:\n        - name: sortBy\n          in: query\n          type: string\n          description: JSON specifying sort criteria. Accepts the same format as returned by the [queries](https://www.openproject.org/docs/api/endpoints/queries/)\n            endpoint. Currently\n        - name: select\n          in: query\n          type: string\n          description: Comma separated\
  \ list of properties to include.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-group\n        method: POST\n        description: Create group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-groups-id\n      path: /api/v3/groups/{id}\n      operations:\n      - name: delete-group\n        method: DELETE\n        description: Delete group\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Group id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-group\n        method: GET\n        description: Get group\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required:\
  \ true\n          description: Group id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-group\n        method: PATCH\n        description: Update group\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Group id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-help-texts\n      path: /api/v3/help_texts\n      operations:\n      - name: list-help-texts\n        method: GET\n        description: List help texts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-help-texts-id\n      path: /api/v3/help_texts/{id}\n      operations:\n      - name: get-help-text\n        method: GET\n        description: Get help\
  \ text\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Help text id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-meetings\n      path: /api/v3/meetings\n      operations:\n      - name: list-meetings\n        method: GET\n        description: List all visible meetings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v3-meetings-id\n      path: /api/v3/meetings/{id}\n      operations:\n      - name: get-meeting\n        method: GET\n        description: Get a meeting\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Meeting identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openproject-rest\n    description: REST adapter for OpenProject API V3 (Stable).\n    resources:\n    - path: /api/v3\n      name: view-root\n      operations:\n      - method: GET\n        name: view-root\n        description: View root\n        call: openproject.view-root\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/actions\n      name: list-actions\n      operations:\n      - method: GET\n        name: list-actions\n        description: List actions\n        call: openproject.list-actions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/actions/{id}\n      name: view-action\n      operations:\n      - method: GET\n        name: view-action\n        description: View action\n        call: openproject.view-action\n        with:\n          id: rest.id\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}\n      name: get-activity\n      operations:\n      - method: GET\n        name: get-activity\n        description: Get an activity\n        call: openproject.get-activity\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}\n      name: update-activity\n      operations:\n      - method: PATCH\n        name: update-activity\n        description: Update activity\n        call: openproject.update-activity\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}/attachments\n      name: list-activity-attachments\n      operations:\n      - method: GET\n        name: list-activity-attachments\n        description: List attachments by activity\n        call: openproject.list-activity-attachments\n        with:\n          id: rest.id\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}/attachments\n      name: create-activity-attachment\n      operations:\n      - method: POST\n        name: create-activity-attachment\n        description: Add attachment to activity\n        call: openproject.create-activity-attachment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}/emoji_reactions\n      name: list-activity-emoji-reactions\n      operations:\n      - method: GET\n        name: list-activity-emoji-reactions\n        description: List emoji reactions by activity\n        call: openproject.list-activity-emoji-reactions\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/activities/{id}/emoji_reactions\n      name: toggle-activity-emoji-reaction\n      operations:\n      - method: PATCH\n\
  \        name: toggle-activity-emoji-reaction\n        description: Toggle emoji reaction for an activity\n        call: openproject.toggle-activity-emoji-reaction\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/attachments\n      name: create-attachment\n      operations:\n      - method: POST\n        name: create-attachment\n        description: Create Attachment\n        call: openproject.create-attachment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/attachments/{id}\n      name: delete-attachment\n      operations:\n      - method: DELETE\n        name: delete-attachment\n        description: Delete attachment\n        call: openproject.delete-attachment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/attachments/{id}\n      name: view-attachment\n      operations:\n\
  \      - method: GET\n        name: view-attachment\n        description: View attachment\n        call: openproject.view-attachment\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/budgets/{id}\n      name: view-budget\n      operations:\n      - method: GET\n        name: view-budget\n        description: view Budget\n        call: openproject.view-budget\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v3/capabilities\n      name: list-capabilities\n      operations:\n      - method: GET\n        name: list-capabilities\n        description: List capabilities\n        call: openproject.list-capabilities\n        outputParameters:\n        - type: object\n   \n\n# --- truncated at 32 KB (72 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/openproject/refs/heads/main/capabilities/openproject-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openproject/refs/heads/main/capabilities/openproject-capability.yaml
tags:
- Openproject
- API
tools:
- description: View root
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-root
- description: List actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-actions
- description: View action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-action
- description: Get an activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-activity
- description: Update activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-activity
- description: List attachments by activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-activity-attachments
- description: Add attachment to activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-activity-attachment
- description: List emoji reactions by activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-activity-emoji-reactions
- description: Toggle emoji reaction for an activity
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: toggle-activity-emoji-reaction
- description: Create Attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-attachment
- description: Delete attachment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-attachment
- description: View attachment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-attachment
- description: view Budget
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-budget
- description: List capabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-capabilities
- description: View global context
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-global-context
- description: View capabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-capabilities
- description: View Category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-category
- description: View configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-configuration
- description: Get a custom action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-custom-action
- description: Execute custom action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: execute-custom-action
- description: Get the custom field hierarchy items
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-custom-field-items
- description: Get a custom field hierarchy item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-custom-field-item
- description: Get a custom field hierarchy item's branch
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-custom-field-item-branch
- description: View Custom Option
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-custom-option
- description: Lists all non working days
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-non-working-days
- description: Creates a non-working day (NOT IMPLEMENTED)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-non-working-day
- description: View a non-working day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-non-working-day
- description: Update a non-working day attributes (NOT IMPLEMENTED)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-non-working-day
- description: Removes a non-working day (NOT IMPLEMENTED)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-non-working-day
- description: Lists week days
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-week-days
- description: Update week days (NOT IMPLEMENTED)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-week-days
- description: View a week day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-week-day
- description: Update a week day attributes (NOT IMPLEMENTED)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-week-day
- description: Lists days
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-days
- description: View day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-day
- description: List Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-documents
- description: View document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-document
- description: Update document
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-document
- description: show or validate form
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: show-or-validate-form
- description: view the schema
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-the-schema
- description: view aggregated result
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-aggregated-result
- description: Gets a file link.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: view-file-link
- description: Removes a file link.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-file-link
- description: Creates an opening uri of the linked file.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: open-file-link
- description: Creates a download uri of the linked file.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: download-file-link
- description: List grids
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-grids
- description: Create a grid
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-grid
- description: Grid Create Form
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: grid-create-form
- description: Get a grid
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-grid
- description: Update a grid
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-grid
- description: Grid Update Form
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: grid-update-form
- description: List groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-groups
- description: Create group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-group
- description: Delete group
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-group
- description: Get group
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-group
- description: Update group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-group
- description: List help texts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-help-texts
- description: Get help text
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-help-text
- description: List all visible meetings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-meetings
- description: Get a meeting
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-meeting
---
