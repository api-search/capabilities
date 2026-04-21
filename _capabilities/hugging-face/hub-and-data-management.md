---
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
- get rows from a dataset split with pagination.
- list and search spaces
- user information
- search dataset
- get croissant metadata
- create repositories
- get model details
- get model revision
- get dataset statistics
- list all available model tags grouped by type.
- list model tags
- get authenticated user info
- list models
- models
- manage models on the hub
- hugging face
- data management
- list and search models
- get dataset details
- list and search ml models on the hugging face hub.
- delete a repository from the hub.
- get the list of splits for a dataset.
- get model information at a specific revision or branch.
- get detailed information about a specific model.
- get detailed information about a specific dataset.
- get information about the authenticated user.
- get dataset parquet
- search for rows matching a query in a dataset.
- search rows in a dataset
- get model information
- manage spaces on the hub
- get the first rows of a dataset split for preview.
- get detailed information about a specific space.
- get dataset rows
- get rows
- create a new model, dataset, or space repository on the hub.
- filter dataset rows using a condition.
- get statistical information about a dataset split.
- get parquet file urls for a dataset.
- preview dataset rows
- get dataset splits
- check if a dataset is valid and available on the hub.
- update repo settings
- search dataset rows
- get croissant metadata for a dataset.
- get space
- update settings for a repository.
- create a new repository
- create repo
- datasets
- search rows
- list and search datasets on the hub.
- list datasets
- list dataset tags
- check dataset validity
- manage datasets on the hub
- list all available dataset tags grouped by type.
- hub
- list and search datasets
- get dataset size
- get dataset
- delete repo
- list spaces
- get model
- get size information for a dataset.
- list and search spaces on the hub.
- whoami
- get rows from a dataset
- filter dataset
- get dataset information
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
