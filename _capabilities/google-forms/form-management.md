---
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
- google forms
- renew watch
- surveys
- create a new google form with a title
- set publish settings
- form response operations
- watch notification operations
- create forms, collect responses, monitor changes
- list all active watches for a form
- creating and managing forms for data collection
- list watches
- forms
- list responses
- delete a watch to stop notifications
- delete watch
- responses
- create form
- form crud operations
- update form publish settings
- list form responses
- delete a watch
- create watch
- notifications
- create a notification watch
- creates and manages forms, monitors responses
- google
- google workspace
- questionnaires
- apply batch updates to a form (add/remove/modify items)
- Form Administrator
- data collection
- get form
- batch update form
- set up a pub/sub watch for form changes or new responses
- managing surveys, questions, and notification watches
- create a new form
- get a single response
- get form details
- get response
- list all responses for a form
- get a single form response by id
- extend a watch's expiration by seven days
- Data Analyst
- analyzes form responses and collects data
- get a google form's structure and settings
slug: form-management
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
