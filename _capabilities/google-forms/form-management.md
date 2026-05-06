---
categories: []
consumed_apis: []
description: Workflow capability for managing Google Forms - creating forms, collecting responses, and monitoring changes via watches. Used by form administrators and data analysts.
layout: capability
name: Google Forms Form Management
operations:
- description: Create a new form
  method: POST
  name: create-form
  path: /v1/forms
- description: Get form details
  method: GET
  name: get-form
  path: /v1/forms
- description: List form responses
  method: GET
  name: list-responses
  path: /v1/responses
- description: Get a single response
  method: GET
  name: get-response
  path: /v1/responses
- description: Create a notification watch
  method: POST
  name: create-watch
  path: /v1/watches
- description: List watches
  method: GET
  name: list-watches
  path: /v1/watches
- description: Delete a watch
  method: DELETE
  name: delete-watch
  path: /v1/watches
personas: []
provider_name: Google Forms
provider_slug: google-forms
search_terms:
- update form publish settings
- form crud operations
- get a google form's structure and settings
- google workspace
- create a new google form with a title
- get a single form response by id
- apply batch updates to a form (add/remove/modify items)
- list responses
- create form
- list form responses
- responses
- set publish settings
- set up a pub/sub watch for form changes or new responses
- data collection
- google forms
- questionnaires
- google
- managing surveys, questions, and notification watches
- create forms, collect responses, monitor changes
- create a notification watch
- delete a watch to stop notifications
- list watches
- renew watch
- get a single response
- delete watch
- create a new form
- list all responses for a form
- Data Analyst
- Form Administrator
- create watch
- surveys
- notifications
- creates and manages forms, monitors responses
- form response operations
- extend a watch's expiration by seven days
- creating and managing forms for data collection
- delete a watch
- forms
- get form
- get form details
- batch update form
- get response
- list all active watches for a form
- watch notification operations
- analyzes form responses and collects data
slug: form-management
source_filename: form-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Forms Form Management\n  description: Workflow capability for managing Google Forms - creating forms, collecting responses, and monitoring changes\n    via watches. Used by form administrators and data analysts.\n  tags:\n  - Google Forms\n  - Surveys\n  - Data Collection\n  - Notifications\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_FORMS_API_KEY: GOOGLE_FORMS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: forms-api\n    baseUri: https://forms.googleapis.com\n    description: Google Forms API v1 for managing forms, responses, and watches.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_FORMS_API_KEY}}'\n    resources:\n    - name: forms\n      path: /v1/forms\n      description: Form management operations\n      operations:\n      - name: create-form\n        method: POST\n        description: Create a new form\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            info:\n              title: '{{tools.title}}'\n      - name: get-form\n        method: GET\n        description: Get a form by ID\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: batch-update-form\n        method: POST\n        description: Batch update a form with multiple changes\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      \
  \  body:\n          type: json\n          data:\n            requests: '{{tools.requests}}'\n      - name: set-publish-settings\n        method: POST\n        description: Update publish settings for a form\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            publishSettings: '{{tools.publishSettings}}'\n    - name: responses\n      path: /v1/forms/{formId}/responses\n      description: Form response operations\n      operations:\n      - name: list-responses\n        method: GET\n        description: List form responses\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n    \
  \    - name: pageSize\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of responses\n        - name: pageToken\n          in: query\n          type: string\n          required: false\n          description: Pagination token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-response\n        method: GET\n        description: Get a single form response\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        - name: responseId\n          in: path\n          type: string\n          required: true\n          description: The response ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: watches\n      path: /v1/forms/{formId}/watches\n\
  \      description: Watch management operations\n      operations:\n      - name: create-watch\n        method: POST\n        description: Create a new watch for notifications\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            watch: '{{tools.watch}}'\n      - name: list-watches\n        method: GET\n        description: List watches for a form\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-watch\n        method: DELETE\n   \
  \     description: Delete a watch\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        - name: watchId\n          in: path\n          type: string\n          required: true\n          description: The watch ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: renew-watch\n        method: POST\n        description: Renew a watch for seven more days\n        inputParameters:\n        - name: formId\n          in: path\n          type: string\n          required: true\n          description: The ID of the form\n        - name: watchId\n          in: path\n          type: string\n          required: true\n          description: The watch ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  -\
  \ type: rest\n    port: 8080\n    namespace: form-management-api\n    description: Unified REST API for Google Forms management workflows.\n    resources:\n    - path: /v1/forms\n      name: forms\n      description: Form CRUD operations\n      operations:\n      - method: POST\n        name: create-form\n        description: Create a new form\n        call: forms-api.create-form\n      - method: GET\n        name: get-form\n        description: Get form details\n        call: forms-api.get-form\n    - path: /v1/responses\n      name: responses\n      description: Form response operations\n      operations:\n      - method: GET\n        name: list-responses\n        description: List form responses\n        call: forms-api.list-responses\n      - method: GET\n        name: get-response\n        description: Get a single response\n        call: forms-api.get-response\n    - path: /v1/watches\n      name: watches\n      description: Watch notification operations\n      operations:\n    \
  \  - method: POST\n        name: create-watch\n        description: Create a notification watch\n        call: forms-api.create-watch\n      - method: GET\n        name: list-watches\n        description: List watches\n        call: forms-api.list-watches\n      - method: DELETE\n        name: delete-watch\n        description: Delete a watch\n        call: forms-api.delete-watch\n  - type: mcp\n    port: 9090\n    namespace: form-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Google Forms management.\n    tools:\n    - name: create-form\n      description: Create a new Google Form with a title\n      hints:\n        readOnly: false\n        openWorld: true\n      call: forms-api.create-form\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-form\n      description: Get a Google Form's structure and settings\n      hints:\n        readOnly: true\n        openWorld: true\n      call: forms-api.get-form\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: batch-update-form\n      description: Apply batch updates to a form (add/remove/modify items)\n      hints:\n        readOnly: false\n      call: forms-api.batch-update-form\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-publish-settings\n      description: Update form publish settings\n      hints:\n        readOnly: false\n      call: forms-api.set-publish-settings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-responses\n      description: List all responses for a form\n      hints:\n        readOnly: true\n        openWorld: true\n      call: forms-api.list-responses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-response\n      description: Get a single form response by ID\n      hints:\n        readOnly: true\n      call: forms-api.get-response\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: create-watch\n      description: Set up a Pub/Sub watch for form changes or new responses\n      hints:\n        readOnly: false\n      call: forms-api.create-watch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-watches\n      description: List all active watches for a form\n      hints:\n        readOnly: true\n      call: forms-api.list-watches\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-watch\n      description: Delete a watch to stop notifications\n      hints:\n        destructive: true\n      call: forms-api.delete-watch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: renew-watch\n      description: Extend a watch's expiration by seven days\n      hints:\n        readOnly: false\n      call: forms-api.renew-watch\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-forms/refs/heads/main/capabilities/form-management.yaml
tags:
- Google Forms
- Surveys
- Data Collection
- Notifications
tools:
- description: Create a new Google Form with a title
  hints:
    openWorld: true
    readOnly: false
  name: create-form
- description: Get a Google Form's structure and settings
  hints:
    openWorld: true
    readOnly: true
  name: get-form
- description: Apply batch updates to a form (add/remove/modify items)
  hints:
    readOnly: false
  name: batch-update-form
- description: Update form publish settings
  hints:
    readOnly: false
  name: set-publish-settings
- description: List all responses for a form
  hints:
    openWorld: true
    readOnly: true
  name: list-responses
- description: Get a single form response by ID
  hints:
    readOnly: true
  name: get-response
- description: Set up a Pub/Sub watch for form changes or new responses
  hints:
    readOnly: false
  name: create-watch
- description: List all active watches for a form
  hints:
    readOnly: true
  name: list-watches
- description: Delete a watch to stop notifications
  hints:
    destructive: true
  name: delete-watch
- description: Extend a watch's expiration by seven days
  hints:
    readOnly: false
  name: renew-watch
---
