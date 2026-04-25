---
consumed_apis:
- cloud-resource-manager
description: Workflow for managing the Google Cloud resource hierarchy including projects, folders, organizations, and tags. Used by cloud administrators and platform engineers.
layout: capability
name: Google Cloud Platform Resource Hierarchy Management
operations:
- description: List projects
  method: GET
  name: list-projects
  path: /v1/projects
- description: Create a project
  method: POST
  name: create-project
  path: /v1/projects
- description: Get project details
  method: GET
  name: get-project
  path: /v1/projects/{name}
- description: Update a project
  method: PATCH
  name: update-project
  path: /v1/projects/{name}
- description: Delete a project
  method: DELETE
  name: delete-project
  path: /v1/projects/{name}
- description: List folders
  method: GET
  name: list-folders
  path: /v1/folders
- description: Create a folder
  method: POST
  name: create-folder
  path: /v1/folders
- description: Get organization details
  method: GET
  name: get-organization
  path: /v1/organizations/{name}
personas: []
provider_name: Google Cloud Platform
provider_slug: google-cloud-platform
search_terms:
- organization operations
- get organization
- delete a google cloud project
- create project
- search projects
- create a project
- create folder
- create a new google cloud project
- get project details
- get organization details
- delete project
- list folders
- search for organizations
- update project
- get folder
- update a project
- search organizations
- platform as a service
- create tag key
- governance
- folder management
- delete a folder
- google cloud
- list projects
- list tag keys
- resource management
- single project operations
- create a folder
- search for projects matching a query
- create a new tag key
- delete a project
- list google cloud projects under a parent
- get folder details
- delete folder
- list tag keys for resource tagging
- api management
- list folders under a parent
- project management
- cloud computing
- infrastructure
- get project
slug: resource-hierarchy-management
tags:
- Google Cloud
- Resource Management
- Governance
- Infrastructure
tools:
- description: List Google Cloud projects under a parent
  hints:
    idempotent: true
    readOnly: true
  name: list-projects
- description: Create a new Google Cloud project
  hints:
    idempotent: false
    readOnly: false
  name: create-project
- description: Get project details
  hints:
    idempotent: true
    readOnly: true
  name: get-project
- description: Update a project
  hints:
    idempotent: true
    readOnly: false
  name: update-project
- description: Delete a Google Cloud project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-project
- description: Search for projects matching a query
  hints:
    idempotent: true
    readOnly: true
  name: search-projects
- description: List folders under a parent
  hints:
    idempotent: true
    readOnly: true
  name: list-folders
- description: Create a folder
  hints:
    idempotent: false
    readOnly: false
  name: create-folder
- description: Get folder details
  hints:
    idempotent: true
    readOnly: true
  name: get-folder
- description: Delete a folder
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-folder
- description: Get organization details
  hints:
    idempotent: true
    readOnly: true
  name: get-organization
- description: Search for organizations
  hints:
    idempotent: true
    readOnly: true
  name: search-organizations
- description: List tag keys for resource tagging
  hints:
    idempotent: true
    readOnly: true
  name: list-tag-keys
- description: Create a new tag key
  hints:
    idempotent: false
    readOnly: false
  name: create-tag-key
---
