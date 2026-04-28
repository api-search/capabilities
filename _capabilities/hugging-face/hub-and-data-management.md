---
categories: []
consumed_apis:
- hf-hub
- hf-dataset-viewer
description: Unified workflow for managing models, datasets, and spaces on the Hugging Face Hub, and exploring dataset contents via the Dataset Viewer. Used by ML engineers, data scientists, and platform administrators for model discovery, dataset curation, and repository management.
layout: capability
name: Hugging Face Hub and Data Management
operations:
- description: List and search models
  method: GET
  name: list-models
  path: /v1/models
- description: Get model information
  method: GET
  name: get-model
  path: /v1/models/{repo_id}
- description: List and search datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Get dataset information
  method: GET
  name: get-dataset
  path: /v1/datasets/{repo_id}
- description: Get rows from a dataset
  method: GET
  name: get-rows
  path: /v1/datasets/{dataset}/rows
- description: Search rows in a dataset
  method: GET
  name: search-rows
  path: /v1/datasets/{dataset}/search
- description: List and search Spaces
  method: GET
  name: list-spaces
  path: /v1/spaces
- description: Create a new repository
  method: POST
  name: create-repo
  path: /v1/repos
- description: Get authenticated user info
  method: GET
  name: whoami
  path: /v1/user
personas: []
provider_name: Hugging Face
provider_slug: hugging-face
search_terms:
- get croissant metadata for a dataset.
- list and search datasets on the hub.
- hugging face
- get dataset details
- get detailed information about a specific dataset.
- get size information for a dataset.
- search dataset rows
- manage models on the hub
- get parquet file urls for a dataset.
- get rows from a dataset split with pagination.
- list and search spaces on the hub.
- check if a dataset is valid and available on the hub.
- update settings for a repository.
- user information
- get the first rows of a dataset split for preview.
- get information about the authenticated user.
- get model
- get dataset rows
- get model revision
- update repo settings
- models
- search rows in a dataset
- list datasets
- get model details
- filter dataset rows using a condition.
- get croissant metadata
- get dataset
- get dataset splits
- get model information at a specific revision or branch.
- get space
- delete repo
- list spaces
- create a new model, dataset, or space repository on the hub.
- check dataset validity
- create repositories
- list all available model tags grouped by type.
- search rows
- filter dataset
- datasets
- list and search datasets
- whoami
- manage datasets on the hub
- get detailed information about a specific space.
- get dataset parquet
- get dataset information
- get rows from a dataset
- delete a repository from the hub.
- create repo
- preview dataset rows
- get dataset statistics
- list models
- get the list of splits for a dataset.
- list and search spaces
- list dataset tags
- list and search ml models on the hugging face hub.
- search dataset
- get dataset size
- data management
- create a new repository
- get authenticated user info
- get statistical information about a dataset split.
- list and search models
- get model information
- get rows
- manage spaces on the hub
- list model tags
- search for rows matching a query in a dataset.
- list all available dataset tags grouped by type.
- hub
- get detailed information about a specific model.
slug: hub-and-data-management
tags:
- Hugging Face
- Hub
- Models
- Datasets
- Data Management
tools:
- description: List and search ML models on the Hugging Face Hub.
  hints:
    openWorld: true
    readOnly: true
  name: list-models
- description: Get detailed information about a specific model.
  hints:
    openWorld: true
    readOnly: true
  name: get-model
- description: Get model information at a specific revision or branch.
  hints:
    openWorld: true
    readOnly: true
  name: get-model-revision
- description: List and search datasets on the Hub.
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Get detailed information about a specific dataset.
  hints:
    openWorld: true
    readOnly: true
  name: get-dataset
- description: Get parquet file URLs for a dataset.
  hints:
    readOnly: true
  name: get-dataset-parquet
- description: List and search Spaces on the Hub.
  hints:
    openWorld: true
    readOnly: true
  name: list-spaces
- description: Get detailed information about a specific Space.
  hints:
    openWorld: true
    readOnly: true
  name: get-space
- description: Create a new model, dataset, or Space repository on the Hub.
  hints:
    readOnly: false
  name: create-repo
- description: Delete a repository from the Hub.
  hints:
    destructive: true
    readOnly: false
  name: delete-repo
- description: Update settings for a repository.
  hints:
    idempotent: true
    readOnly: false
  name: update-repo-settings
- description: Get information about the authenticated user.
  hints:
    readOnly: true
  name: whoami
- description: List all available model tags grouped by type.
  hints:
    readOnly: true
  name: list-model-tags
- description: List all available dataset tags grouped by type.
  hints:
    readOnly: true
  name: list-dataset-tags
- description: Check if a dataset is valid and available on the Hub.
  hints:
    readOnly: true
  name: check-dataset-validity
- description: Get the list of splits for a dataset.
  hints:
    readOnly: true
  name: get-dataset-splits
- description: Get the first rows of a dataset split for preview.
  hints:
    readOnly: true
  name: preview-dataset-rows
- description: Get rows from a dataset split with pagination.
  hints:
    readOnly: true
  name: get-dataset-rows
- description: Search for rows matching a query in a dataset.
  hints:
    readOnly: true
  name: search-dataset
- description: Filter dataset rows using a condition.
  hints:
    readOnly: true
  name: filter-dataset
- description: Get size information for a dataset.
  hints:
    readOnly: true
  name: get-dataset-size
- description: Get statistical information about a dataset split.
  hints:
    readOnly: true
  name: get-dataset-statistics
- description: Get Croissant metadata for a dataset.
  hints:
    readOnly: true
  name: get-croissant-metadata
---
