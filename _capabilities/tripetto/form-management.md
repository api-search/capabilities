---
categories: []
consumed_apis: []
description: Workflow capability for building, deploying, and collecting responses from Tripetto smart forms and surveys. Enables form lifecycle management including creation, updates, response retrieval, and webhook configuration for automation platform integrations.
layout: capability
name: Tripetto Form Management
operations:
- description: List all forms in the Tripetto account
  method: GET
  name: list-forms
  path: /v1/forms
- description: Create a new smart form with a JSON definition
  method: POST
  name: create-form
  path: /v1/forms
- description: Retrieve a specific form by ID
  method: GET
  name: get-form
  path: /v1/forms/{formId}
- description: Update form name or definition
  method: PUT
  name: update-form
  path: /v1/forms/{formId}
- description: Delete a form and all responses
  method: DELETE
  name: delete-form
  path: /v1/forms/{formId}
- description: List all responses for a specific form
  method: GET
  name: list-form-responses
  path: /v1/forms/{formId}/responses
- description: List all configured webhooks for a form
  method: GET
  name: list-form-webhooks
  path: /v1/forms/{formId}/webhooks
- description: Add a webhook endpoint to receive form responses
  method: POST
  name: create-form-webhook
  path: /v1/forms/{formId}/webhooks
personas: []
provider_name: Tripetto
provider_slug: tripetto
search_terms:
- webhooks
- no-code
- create and list tripetto forms
- delete a form and all responses
- create form
- list form responses
- create a new smart form with conditional logic
- list forms
- create form webhook
- manage webhook integrations for a form
- retrieve a specific form by id
- list webhook integrations configured for a form
- list all configured webhooks for a form
- sdk
- add a webhook endpoint to receive form responses
- manage a specific form
- update form
- create a new smart form with a json definition
- access collected form responses
- form builder
- list form webhooks
- retrieve a specific form definition by id
- update form name or definition
- delete a form and all its collected responses
- list all forms in the tripetto account
- update an existing form definition
- list responses collected for a specific form
- list all responses for a specific form
- add a webhook endpoint to deliver form responses to external services
- surveys
- forms
- get form
- delete form
- list all tripetto forms in the account
- automation
slug: form-management
source_filename: form-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tripetto Form Management\n  description: Workflow capability for building, deploying, and collecting responses from Tripetto smart forms and surveys.\n    Enables form lifecycle management including creation, updates, response retrieval, and webhook configuration for automation\n    platform integrations.\n  tags:\n  - Forms\n  - Surveys\n  - Form Builder\n  - Webhooks\n  - Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRIPETTO_API_TOKEN: TRIPETTO_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tripetto\n    baseUri: https://tripetto.com\n    description: Tripetto FormBuilder API for managing forms, responses, and webhooks\n    authentication:\n      type: bearer\n      token: '{{TRIPETTO_API_TOKEN}}'\n    resources:\n    - name: forms\n      path: /app/api/forms\n      description: Create and manage form definitions\n      operations:\n      - name: list-forms\n\
  \        method: GET\n        description: Retrieve a list of forms in the account\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of forms per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-form\n        method: POST\n        description: Create a new form with a definition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            definition: '{{tools.definition}}'\n    - name: form-by-id\n      path: /app/api/forms/{formId}\n\
  \      description: Manage a specific form by ID\n      operations:\n      - name: get-form\n        method: GET\n        description: Retrieve a specific form by its ID\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-form\n        method: PUT\n        description: Update an existing form definition\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            definition:\
  \ '{{tools.definition}}'\n      - name: delete-form\n        method: DELETE\n        description: Delete a form and all its responses\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: form-responses\n      path: /app/api/forms/{formId}/responses\n      description: Access form response data\n      operations:\n      - name: list-form-responses\n        method: GET\n        description: Retrieve all responses submitted for a specific form\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the form\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description:\
  \ Page number for pagination\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of responses per page\n        - name: from\n          in: query\n          type: string\n          required: false\n          description: Filter responses from this ISO 8601 date\n        - name: to\n          in: query\n          type: string\n          required: false\n          description: Filter responses to this ISO 8601 date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: form-webhooks\n      path: /app/api/forms/{formId}/webhooks\n      description: Manage webhooks for a form\n      operations:\n      - name: list-form-webhooks\n        method: GET\n        description: List all configured webhooks for a form\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n   \
  \       description: The unique identifier of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-form-webhook\n        method: POST\n        description: Configure a webhook to receive form responses\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            sendRawData: '{{tools.send_raw_data}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tripetto-form-management-api\n    description: Unified REST API for Tripetto form lifecycle management.\n    resources:\n    - path: /v1/forms\n      name: forms\n      description: Create\
  \ and list Tripetto forms\n      operations:\n      - method: GET\n        name: list-forms\n        description: List all forms in the Tripetto account\n        call: tripetto.list-forms\n        with:\n          page: rest.page\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-form\n        description: Create a new smart form with a JSON definition\n        call: tripetto.create-form\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forms/{formId}\n      name: form\n      description: Manage a specific form\n      operations:\n      - method: GET\n        name: get-form\n        description: Retrieve a specific form by ID\n        call: tripetto.get-form\n        with:\n          formId: rest.formId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-form\n        description: Update\
  \ form name or definition\n        call: tripetto.update-form\n        with:\n          formId: rest.formId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-form\n        description: Delete a form and all responses\n        call: tripetto.delete-form\n        with:\n          formId: rest.formId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forms/{formId}/responses\n      name: form-responses\n      description: Access collected form responses\n      operations:\n      - method: GET\n        name: list-form-responses\n        description: List all responses for a specific form\n        call: tripetto.list-form-responses\n        with:\n          formId: rest.formId\n          page: rest.page\n          limit: rest.limit\n          from: rest.from\n          to: rest.to\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/forms/{formId}/webhooks\n\
  \      name: form-webhooks\n      description: Manage webhook integrations for a form\n      operations:\n      - method: GET\n        name: list-form-webhooks\n        description: List all configured webhooks for a form\n        call: tripetto.list-form-webhooks\n        with:\n          formId: rest.formId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-form-webhook\n        description: Add a webhook endpoint to receive form responses\n        call: tripetto.create-form-webhook\n        with:\n          formId: rest.formId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tripetto-form-management-mcp\n    transport: http\n    description: MCP server for AI-assisted form building and survey data collection.\n    tools:\n    - name: list-forms\n      description: List all Tripetto forms in the account\n      hints:\n        readOnly: true\n    \
  \    openWorld: true\n      call: tripetto.list-forms\n      with:\n        page: tools.page\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-form\n      description: Retrieve a specific form definition by ID\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tripetto.get-form\n      with:\n        formId: tools.formId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-form\n      description: Create a new smart form with conditional logic\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tripetto.create-form\n      with:\n        name: tools.name\n        description: tools.description\n        definition: tools.definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-form\n      description: Update an existing form definition\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: true\n      call: tripetto.update-form\n      with:\n        formId: tools.formId\n        name: tools.name\n        definition: tools.definition\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-form\n      description: Delete a form and all its collected responses\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tripetto.delete-form\n      with:\n        formId: tools.formId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-form-responses\n      description: List responses collected for a specific form\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tripetto.list-form-responses\n      with:\n        formId: tools.formId\n        page: tools.page\n        limit: tools.limit\n        from: tools.from\n        to: tools.to\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: list-form-webhooks\n      description: List webhook integrations configured for a form\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tripetto.list-form-webhooks\n      with:\n        formId: tools.formId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-form-webhook\n      description: Add a webhook endpoint to deliver form responses to external services\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: tripetto.create-form-webhook\n      with:\n        formId: tools.formId\n        url: tools.url\n        sendRawData: tools.send_raw_data\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tripetto/refs/heads/main/capabilities/form-management.yaml
tags:
- Forms
- Surveys
- Form Builder
- Webhooks
- Automation
tools:
- description: List all Tripetto forms in the account
  hints:
    openWorld: true
    readOnly: true
  name: list-forms
- description: Retrieve a specific form definition by ID
  hints:
    openWorld: false
    readOnly: true
  name: get-form
- description: Create a new smart form with conditional logic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-form
- description: Update an existing form definition
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-form
- description: Delete a form and all its collected responses
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-form
- description: List responses collected for a specific form
  hints:
    openWorld: true
    readOnly: true
  name: list-form-responses
- description: List webhook integrations configured for a form
  hints:
    openWorld: false
    readOnly: true
  name: list-form-webhooks
- description: Add a webhook endpoint to deliver form responses to external services
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-form-webhook
---
