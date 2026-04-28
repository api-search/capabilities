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
- list all available model tags grouped by type.
- list and search spaces
- get parquet file urls for a dataset.
- get rows
- update settings for a repository.
- get the first rows of a dataset split for preview.
- list and search datasets on the hub.
- manage datasets on the hub
- search dataset rows
- manage spaces on the hub
- create a new model, dataset, or space repository on the hub.
- list models
- list and search models
- preview dataset rows
- delete a repository from the hub.
- get size information for a dataset.
- get croissant metadata
- list and search spaces on the hub.
- update repo settings
- get dataset rows
- get model revision
- get information about the authenticated user.
- get dataset details
- search rows
- search rows in a dataset
- get rows from a dataset
- get model information
- datasets
- hub
- whoami
- get dataset statistics
- get authenticated user info
- check dataset validity
- search dataset
- create repo
- create a new repository
- list dataset tags
- user information
- delete repo
- get dataset
- get croissant metadata for a dataset.
- get detailed information about a specific model.
- list and search ml models on the hugging face hub.
- manage models on the hub
- get model information at a specific revision or branch.
- list all available dataset tags grouped by type.
- check if a dataset is valid and available on the hub.
- search for rows matching a query in a dataset.
- get space
- get model details
- create repositories
- get dataset splits
- hugging face
- get dataset information
- get statistical information about a dataset split.
- list datasets
- get dataset parquet
- models
- data management
- get model
- list spaces
- get dataset size
- filter dataset rows using a condition.
- filter dataset
- get the list of splits for a dataset.
- list and search datasets
- get detailed information about a specific dataset.
- get rows from a dataset split with pagination.
- list model tags
- get detailed information about a specific space.
slug: hub-and-data-management
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Hugging Face Hub and Data Management\"\n  description: \"Unified workflow for managing models, datasets, and spaces on the Hugging Face Hub, and exploring dataset contents via the Dataset Viewer. Used by ML engineers, data scientists, and platform administrators for model discovery, dataset curation, and repository management.\"\n  tags:\n    - Hugging Face\n    - Hub\n    - Models\n    - Datasets\n    - Data Management\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      HF_API_TOKEN: HF_API_TOKEN\n\ncapability:\n  consumes:\n    - import: hf-hub\n      location: ./shared/hub.yaml\n    - import: hf-dataset-viewer\n      location: ./shared/dataset-viewer.yaml\n\n  exposes:\n    - type: rest\n      port: 8081\n      namespace: hf-hub-data-api\n      description: \"Unified REST API for Hugging Face Hub resource management and dataset exploration.\"\n      resources:\n        - path:\
  \ /v1/models\n          name: models\n          description: \"Manage models on the Hub\"\n          operations:\n            - method: GET\n              name: list-models\n              description: \"List and search models\"\n              call: \"hf-hub.list-models\"\n              with:\n                search: \"rest.search\"\n                author: \"rest.author\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/models/{repo_id}\n          name: model-details\n          description: \"Get model details\"\n          operations:\n            - method: GET\n              name: get-model\n              description: \"Get model information\"\n              call: \"hf-hub.get-model\"\n              with:\n                repo_id: \"rest.repo_id\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets\n          name: datasets\n          description: \"Manage datasets on the Hub\"\n          operations:\n            - method: GET\n              name: list-datasets\n              description: \"List and search datasets\"\n              call: \"hf-hub.list-datasets\"\n              with:\n                search: \"rest.search\"\n                author: \"rest.author\"\n                filter: \"rest.filter\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets/{repo_id}\n          name: dataset-details\n          description: \"Get dataset details\"\n          operations:\n            - method: GET\n              name: get-dataset\n              description: \"Get dataset information\"\n              call: \"hf-hub.get-dataset\"\n              with:\n    \
  \            repo_id: \"rest.repo_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets/{dataset}/rows\n          name: dataset-rows\n          description: \"Get dataset rows\"\n          operations:\n            - method: GET\n              name: get-rows\n              description: \"Get rows from a dataset\"\n              call: \"hf-dataset-viewer.get-rows\"\n              with:\n                dataset: \"rest.dataset\"\n                config: \"rest.config\"\n                split: \"rest.split\"\n                offset: \"rest.offset\"\n                length: \"rest.length\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/datasets/{dataset}/search\n          name: dataset-search\n          description: \"Search dataset rows\"\n          operations:\n            - method: GET\n              name: search-rows\n              description:\
  \ \"Search rows in a dataset\"\n              call: \"hf-dataset-viewer.search-rows\"\n              with:\n                dataset: \"rest.dataset\"\n                config: \"rest.config\"\n                split: \"rest.split\"\n                query: \"rest.query\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/spaces\n          name: spaces\n          description: \"Manage Spaces on the Hub\"\n          operations:\n            - method: GET\n              name: list-spaces\n              description: \"List and search Spaces\"\n              call: \"hf-hub.list-spaces\"\n              with:\n                search: \"rest.search\"\n                author: \"rest.author\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/repos\n          name: repos\n          description: \"Create repositories\"\n  \
  \        operations:\n            - method: POST\n              name: create-repo\n              description: \"Create a new repository\"\n              call: \"hf-hub.create-repo\"\n              with:\n                type: \"rest.type\"\n                name: \"rest.name\"\n                organization: \"rest.organization\"\n                private: \"rest.private\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/user\n          name: user\n          description: \"User information\"\n          operations:\n            - method: GET\n              name: whoami\n              description: \"Get authenticated user info\"\n              call: \"hf-hub.whoami\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: hf-hub-data-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Hugging Face Hub\
  \ management and dataset exploration.\"\n      tools:\n        - name: list-models\n          description: \"List and search ML models on the Hugging Face Hub.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.list-models\"\n          with:\n            search: \"tools.search\"\n            author: \"tools.author\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model\n          description: \"Get detailed information about a specific model.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.get-model\"\n          with:\n            repo_id: \"tools.repo_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-model-revision\n          description: \"Get model\
  \ information at a specific revision or branch.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.get-model-revision\"\n          with:\n            repo_id: \"tools.repo_id\"\n            revision: \"tools.revision\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-datasets\n          description: \"List and search datasets on the Hub.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.list-datasets\"\n          with:\n            search: \"tools.search\"\n            author: \"tools.author\"\n            filter: \"tools.filter\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset\n          description: \"Get detailed information about a specific dataset.\"\n          hints:\n           \
  \ readOnly: true\n            openWorld: true\n          call: \"hf-hub.get-dataset\"\n          with:\n            repo_id: \"tools.repo_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset-parquet\n          description: \"Get parquet file URLs for a dataset.\"\n          hints:\n            readOnly: true\n          call: \"hf-hub.get-dataset-parquet\"\n          with:\n            repo_id: \"tools.repo_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-spaces\n          description: \"List and search Spaces on the Hub.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.list-spaces\"\n          with:\n            search: \"tools.search\"\n            author: \"tools.author\"\n            sort: \"tools.sort\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: get-space\n          description: \"Get detailed information about a specific Space.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"hf-hub.get-space\"\n          with:\n            repo_id: \"tools.repo_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-repo\n          description: \"Create a new model, dataset, or Space repository on the Hub.\"\n          hints:\n            readOnly: false\n          call: \"hf-hub.create-repo\"\n          with:\n            type: \"tools.type\"\n            name: \"tools.name\"\n            organization: \"tools.organization\"\n            private: \"tools.private\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-repo\n          description: \"Delete a repository from the Hub.\"\n          hints:\n            readOnly: false\n\
  \            destructive: true\n          call: \"hf-hub.delete-repo\"\n          with:\n            type: \"tools.type\"\n            name: \"tools.name\"\n            organization: \"tools.organization\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: update-repo-settings\n          description: \"Update settings for a repository.\"\n          hints:\n            readOnly: false\n            idempotent: true\n          call: \"hf-hub.update-repo-settings\"\n          with:\n            repo_type: \"tools.repo_type\"\n            repo_id: \"tools.repo_id\"\n            private: \"tools.private\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: whoami\n          description: \"Get information about the authenticated user.\"\n          hints:\n            readOnly: true\n          call: \"hf-hub.whoami\"\n          outputParameters:\n            - type: object\n             \
  \ mapping: \"$.\"\n        - name: list-model-tags\n          description: \"List all available model tags grouped by type.\"\n          hints:\n            readOnly: true\n          call: \"hf-hub.list-model-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-dataset-tags\n          description: \"List all available dataset tags grouped by type.\"\n          hints:\n            readOnly: true\n          call: \"hf-hub.list-dataset-tags\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: check-dataset-validity\n          description: \"Check if a dataset is valid and available on the Hub.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.is-valid\"\n          with:\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset-splits\n     \
  \     description: \"Get the list of splits for a dataset.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-splits\"\n          with:\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: preview-dataset-rows\n          description: \"Get the first rows of a dataset split for preview.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-first-rows\"\n          with:\n            dataset: \"tools.dataset\"\n            config: \"tools.config\"\n            split: \"tools.split\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset-rows\n          description: \"Get rows from a dataset split with pagination.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-rows\"\n          with:\n            dataset: \"tools.dataset\"\n\
  \            config: \"tools.config\"\n            split: \"tools.split\"\n            offset: \"tools.offset\"\n            length: \"tools.length\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: search-dataset\n          description: \"Search for rows matching a query in a dataset.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.search-rows\"\n          with:\n            dataset: \"tools.dataset\"\n            config: \"tools.config\"\n            split: \"tools.split\"\n            query: \"tools.query\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: filter-dataset\n          description: \"Filter dataset rows using a condition.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.filter-rows\"\n          with:\n            dataset: \"tools.dataset\"\n            config: \"tools.config\"\n          \
  \  split: \"tools.split\"\n            where: \"tools.where\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset-size\n          description: \"Get size information for a dataset.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-dataset-size\"\n          with:\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-dataset-statistics\n          description: \"Get statistical information about a dataset split.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-statistics\"\n          with:\n            dataset: \"tools.dataset\"\n            config: \"tools.config\"\n            split: \"tools.split\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-croissant-metadata\n          description: \"\
  Get Croissant metadata for a dataset.\"\n          hints:\n            readOnly: true\n          call: \"hf-dataset-viewer.get-croissant-metadata\"\n          with:\n            dataset: \"tools.dataset\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hugging-face/refs/heads/main/capabilities/hub-and-data-management.yaml
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
