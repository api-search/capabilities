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
- google workspace
- list form responses
- create watch
- google
- notifications
- delete watch
- list all active watches for a form
- apply batch updates to a form (add/remove/modify items)
- get form details
- delete a watch
- form response operations
- google forms
- create a new form
- get a single form response by id
- list all responses for a form
- surveys
- Form Administrator
- watch notification operations
- create forms, collect responses, monitor changes
- Data Analyst
- analyzes form responses and collects data
- responses
- questionnaires
- list responses
- form crud operations
- get a google form's structure and settings
- get a single response
- get response
- batch update form
- update form publish settings
- forms
- managing surveys, questions, and notification watches
- set up a pub/sub watch for form changes or new responses
- extend a watch's expiration by seven days
- get form
- creates and manages forms, monitors responses
- delete a watch to stop notifications
- set publish settings
- creating and managing forms for data collection
- create a notification watch
- create form
- data collection
- renew watch
- create a new google form with a title
- list watches
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
