---
categories: []
consumed_apis:
- forms-api
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
- Form Administrator
- create a notification watch
- get form details
- watch notification operations
- set publish settings
- managing surveys, questions, and notification watches
- renew watch
- delete a watch to stop notifications
- list responses
- delete watch
- list all responses for a form
- get form
- update form publish settings
- create forms, collect responses, monitor changes
- apply batch updates to a form (add/remove/modify items)
- form crud operations
- batch update form
- responses
- google
- questionnaires
- google workspace
- google forms
- get a single form response by id
- Data Analyst
- data collection
- list watches
- get response
- list form responses
- create watch
- notifications
- set up a pub/sub watch for form changes or new responses
- surveys
- delete a watch
- create form
- creating and managing forms for data collection
- forms
- create a new google form with a title
- get a google form's structure and settings
- creates and manages forms, monitors responses
- form response operations
- analyzes form responses and collects data
- extend a watch's expiration by seven days
- create a new form
- list all active watches for a form
- get a single response
slug: form-management
source_filename: form-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Forms Form Management\"\n  description: \"Workflow capability for managing Google Forms - creating forms, collecting responses, and monitoring changes via watches. Used by form administrators and data analysts.\"\n  tags:\n    - Google Forms\n    - Surveys\n    - Data Collection\n    - Notifications\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_FORMS_API_KEY: GOOGLE_FORMS_API_KEY\n\ncapability:\n  consumes:\n    - import: forms-api\n      location: ./shared/forms-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: form-management-api\n      description: \"Unified REST API for Google Forms management workflows.\"\n      resources:\n        - path: /v1/forms\n          name: forms\n          description: \"Form CRUD operations\"\n          operations:\n            - method: POST\n              name: create-form\n              description:\
  \ \"Create a new form\"\n              call: \"forms-api.create-form\"\n            - method: GET\n              name: get-form\n              description: \"Get form details\"\n              call: \"forms-api.get-form\"\n        - path: /v1/responses\n          name: responses\n          description: \"Form response operations\"\n          operations:\n            - method: GET\n              name: list-responses\n              description: \"List form responses\"\n              call: \"forms-api.list-responses\"\n            - method: GET\n              name: get-response\n              description: \"Get a single response\"\n              call: \"forms-api.get-response\"\n        - path: /v1/watches\n          name: watches\n          description: \"Watch notification operations\"\n          operations:\n            - method: POST\n              name: create-watch\n              description: \"Create a notification watch\"\n              call: \"forms-api.create-watch\"\n          \
  \  - method: GET\n              name: list-watches\n              description: \"List watches\"\n              call: \"forms-api.list-watches\"\n            - method: DELETE\n              name: delete-watch\n              description: \"Delete a watch\"\n              call: \"forms-api.delete-watch\"\n\n    - type: mcp\n      port: 9090\n      namespace: form-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Google Forms management.\"\n      tools:\n        - name: create-form\n          description: \"Create a new Google Form with a title\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"forms-api.create-form\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-form\n          description: \"Get a Google Form's structure and settings\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"forms-api.get-form\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: batch-update-form\n          description: \"Apply batch updates to a form (add/remove/modify items)\"\n          hints:\n            readOnly: false\n          call: \"forms-api.batch-update-form\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: set-publish-settings\n          description: \"Update form publish settings\"\n          hints:\n            readOnly: false\n          call: \"forms-api.set-publish-settings\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-responses\n          description: \"List all responses for a form\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"forms-api.list-responses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-response\n\
  \          description: \"Get a single form response by ID\"\n          hints:\n            readOnly: true\n          call: \"forms-api.get-response\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-watch\n          description: \"Set up a Pub/Sub watch for form changes or new responses\"\n          hints:\n            readOnly: false\n          call: \"forms-api.create-watch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-watches\n          description: \"List all active watches for a form\"\n          hints:\n            readOnly: true\n          call: \"forms-api.list-watches\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-watch\n          description: \"Delete a watch to stop notifications\"\n          hints:\n            destructive: true\n          call: \"forms-api.delete-watch\"\n      \
  \    outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: renew-watch\n          description: \"Extend a watch's expiration by seven days\"\n          hints:\n            readOnly: false\n          call: \"forms-api.renew-watch\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
