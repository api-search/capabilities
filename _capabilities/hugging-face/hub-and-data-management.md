---
categories: []
consumed_apis: []
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
- list and search spaces on the hub.
- get dataset size
- get dataset rows
- datasets
- models
- list all available model tags grouped by type.
- create a new model, dataset, or space repository on the hub.
- get rows from a dataset split with pagination.
- list dataset tags
- manage spaces on the hub
- search dataset
- get dataset splits
- get authenticated user info
- list and search datasets on the hub.
- get detailed information about a specific space.
- update repo settings
- get dataset details
- list all available dataset tags grouped by type.
- get dataset statistics
- get rows
- list and search models
- get detailed information about a specific model.
- get dataset
- data management
- get dataset information
- manage datasets on the hub
- preview dataset rows
- search for rows matching a query in a dataset.
- manage models on the hub
- get space
- filter dataset rows using a condition.
- filter dataset
- search dataset rows
- create repo
- whoami
- list and search ml models on the hugging face hub.
- hub
- get information about the authenticated user.
- get the list of splits for a dataset.
- hugging face
- user information
- check dataset validity
- get the first rows of a dataset split for preview.
- search rows
- get statistical information about a dataset split.
- list models
- get rows from a dataset
- search rows in a dataset
- get model information
- get croissant metadata
- get parquet file urls for a dataset.
- create a new repository
- get size information for a dataset.
- get model revision
- get model details
- get detailed information about a specific dataset.
- delete a repository from the hub.
- update settings for a repository.
- list model tags
- list datasets
- list and search spaces
- create repositories
- get dataset parquet
- get model
- list spaces
- check if a dataset is valid and available on the hub.
- get croissant metadata for a dataset.
- get model information at a specific revision or branch.
- delete repo
- list and search datasets
slug: hub-and-data-management
source_filename: hub-and-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hugging Face Hub and Data Management\n  description: Unified workflow for managing models, datasets, and spaces on the Hugging Face Hub, and exploring dataset contents\n    via the Dataset Viewer. Used by ML engineers, data scientists, and platform administrators for model discovery, dataset\n    curation, and repository management.\n  tags:\n  - Hugging Face\n  - Hub\n  - Models\n  - Datasets\n  - Data Management\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HF_API_TOKEN: HF_API_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: hf-hub\n    baseUri: https://huggingface.co/api\n    description: Manage models, datasets, spaces, and repositories on the Hugging Face Hub.\n    authentication:\n      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: models\n      path: /models\n      description: List and search models\n      operations:\n      - name: list-models\n\
  \        method: GET\n        description: List models on the Hub with optional filtering.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: author\n          in: query\n          type: string\n          required: false\n          description: Filter by author/organization\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: direction\n          in: query\n          type: string\n          required: false\n          description: Sort direction\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: model-by-id\n      path: /models/{repo_id}\n      description: Get model details\n      operations:\n      - name: get-model\n        method: GET\n        description: Get detailed information about a specific model.\n        inputParameters:\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description: The model repository ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-revision\n      path: /models/{repo_id}/revision/{revision}\n      description: Get model at specific revision\n      operations:\n      - name: get-model-revision\n        method: GET\n        description: Get model information at a specific revision.\n        inputParameters:\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The model repository ID\n        - name: revision\n          in: path\n          type: string\n          required: true\n          description: The revision (branch, tag, or commit)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datasets\n      path: /datasets\n      description: List and search datasets\n      operations:\n      - name: list-datasets\n        method: GET\n        description: List datasets on the Hub with optional filtering.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: author\n          in: query\n          type: string\n          required: false\n          description: Filter by author/organization\n        - name: filter\n          in: query\n          type: string\n          required: false\n          description: Filter by tags\n     \
  \   - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataset-by-id\n      path: /datasets/{repo_id}\n      description: Get dataset details\n      operations:\n      - name: get-dataset\n        method: GET\n        description: Get detailed information about a specific dataset.\n        inputParameters:\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description: The dataset repository ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataset-parquet\n      path: /datasets/{repo_id}/parquet\n\
  \      description: Get dataset parquet files\n      operations:\n      - name: get-dataset-parquet\n        method: GET\n        description: Get parquet file URLs for a dataset.\n        inputParameters:\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description: The dataset repository ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: spaces\n      path: /spaces\n      description: List and search spaces\n      operations:\n      - name: list-spaces\n        method: GET\n        description: List Spaces on the Hub with optional filtering.\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: author\n          in: query\n          type: string\n          required: false\n          description: Filter by author/organization\n\
  \        - name: sort\n          in: query\n          type: string\n          required: false\n          description: Sort field\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: space-by-id\n      path: /spaces/{repo_id}\n      description: Get space details\n      operations:\n      - name: get-space\n        method: GET\n        description: Get detailed information about a specific Space.\n        inputParameters:\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description: The space repository ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repos-create\n      path: /repos/create\n      description:\
  \ Create repositories\n      operations:\n      - name: create-repo\n        method: POST\n        description: Create a new repository on the Hub.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            name: '{{tools.name}}'\n            organization: '{{tools.organization}}'\n            private: '{{tools.private}}'\n    - name: repos-delete\n      path: /repos/delete\n      description: Delete repositories\n      operations:\n      - name: delete-repo\n        method: DELETE\n        description: Delete a repository from the Hub.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n         \
  \   name: '{{tools.name}}'\n            organization: '{{tools.organization}}'\n    - name: repo-settings\n      path: /repos/{repo_type}/{repo_id}/settings\n      description: Update repository settings\n      operations:\n      - name: update-repo-settings\n        method: PUT\n        description: Update settings for a repository.\n        inputParameters:\n        - name: repo_type\n          in: path\n          type: string\n          required: true\n          description: Repository type (model, dataset, space)\n        - name: repo_id\n          in: path\n          type: string\n          required: true\n          description: The repository ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            private: '{{tools.private}}'\n    - name: whoami\n      path: /whoami-v2\n      description: Get current user info\n      operations:\n      - name:\
  \ whoami\n        method: GET\n        description: Get information about the authenticated user.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics\n      path: /metrics\n      description: List available metrics\n      operations:\n      - name: list-metrics\n        method: GET\n        description: List all available evaluation metrics.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: model-tags\n      path: /models-tags-by-type\n      description: List model tags\n      operations:\n      - name: list-model-tags\n        method: GET\n        description: List all model tags grouped by type.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: dataset-tags\n      path: /datasets-tags-by-type\n      description: List dataset tags\n      operations:\n      - name: list-dataset-tags\n        method: GET\n        description: List all dataset tags grouped by type.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: hf-dataset-viewer\n    baseUri: https://datasets-server.huggingface.co\n    description: Query and visualize datasets without downloading the entire dataset.\n    authentication:\n      type: bearer\n      token: '{{HF_API_TOKEN}}'\n    resources:\n    - name: validity\n      path: /is-valid\n      description: Check dataset validity\n      operations:\n      - name: is-valid\n        method: GET\n        description: Check if a dataset is valid and available.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required:\
  \ true\n          description: The dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: splits\n      path: /splits\n      description: Get dataset splits\n      operations:\n      - name: get-splits\n        method: GET\n        description: Get the list of splits for a dataset.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: first-rows\n      path: /first-rows\n      description: Get first rows preview\n      operations:\n      - name: get-first-rows\n        method: GET\n        description: Get the first rows of a dataset split.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n        \
  \  required: true\n          description: The dataset name\n        - name: config\n          in: query\n          type: string\n          required: true\n          description: The dataset configuration\n        - name: split\n          in: query\n          type: string\n          required: true\n          description: The dataset split\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rows\n      path: /rows\n      description: Get dataset rows\n      operations:\n      - name: get-rows\n        method: GET\n        description: Get rows from a dataset split with pagination.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        - name: config\n          in: query\n          type: string\n          required: true\n          description: The dataset configuration\n        - name: split\n\
  \          in: query\n          type: string\n          required: true\n          description: The dataset split\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Row offset\n        - name: length\n          in: query\n          type: integer\n          required: false\n          description: Number of rows\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: Search dataset rows\n      operations:\n      - name: search-rows\n        method: GET\n        description: Search for rows matching a query.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        - name: config\n          in: query\n          type: string\n          required: true\n          description: The dataset\
  \ configuration\n        - name: split\n          in: query\n          type: string\n          required: true\n          description: The dataset split\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filter\n      path: /filter\n      description: Filter dataset rows\n      operations:\n      - name: filter-rows\n        method: GET\n        description: Filter rows using a condition.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        - name: config\n          in: query\n          type: string\n          required: true\n          description: The dataset configuration\n        - name: split\n          in: query\n          type: string\n          required:\
  \ true\n          description: The dataset split\n        - name: where\n          in: query\n          type: string\n          required: true\n          description: Filter condition\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parquet\n      path: /parquet\n      description: Get parquet files\n      operations:\n      - name: get-parquet-files\n        method: GET\n        description: Get Parquet file URLs for a dataset.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: size\n      path: /size\n      description: Get dataset size\n      operations:\n      - name: get-dataset-size\n        method: GET\n        description: Get size information\
  \ for a dataset.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: statistics\n      path: /statistics\n      description: Get dataset statistics\n      operations:\n      - name: get-statistics\n        method: GET\n        description: Get statistical information about a dataset.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        - name: config\n          in: query\n          type: string\n          required: true\n          description: The dataset configuration\n        - name: split\n          in: query\n          type: string\n          required: true\n          description: The dataset split\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: croissant\n      path: /croissant\n      description: Get Croissant metadata\n      operations:\n      - name: get-croissant-metadata\n        method: GET\n        description: Get Croissant metadata for a dataset.\n        inputParameters:\n        - name: dataset\n          in: query\n          type: string\n          required: true\n          description: The dataset name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: hf-hub-data-api\n    description: Unified REST API for Hugging Face Hub resource management and dataset exploration.\n    resources:\n    - path: /v1/models\n      name: models\n      description: Manage models on the Hub\n      operations:\n      - method: GET\n        name: list-models\n        description: List and\
  \ search models\n        call: hf-hub.list-models\n        with:\n          search: rest.search\n          author: rest.author\n          filter: rest.filter\n          sort: rest.sort\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/models/{repo_id}\n      name: model-details\n      description: Get model details\n      operations:\n      - method: GET\n        name: get-model\n        description: Get model information\n        call: hf-hub.get-model\n        with:\n          repo_id: rest.repo_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets\n      name: datasets\n      description: Manage datasets on the Hub\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List and search datasets\n        call: hf-hub.list-datasets\n        with:\n          search: rest.search\n          author: rest.author\n          filter: rest.filter\n\
  \          sort: rest.sort\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets/{repo_id}\n      name: dataset-details\n      description: Get dataset details\n      operations:\n      - method: GET\n        name: get-dataset\n        description: Get dataset information\n        call: hf-hub.get-dataset\n        with:\n          repo_id: rest.repo_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/datasets/{dataset}/rows\n      name: dataset-rows\n      description: Get dataset rows\n      operations:\n      - method: GET\n        name: get-rows\n        description: Get rows from a dataset\n        call: hf-dataset-viewer.get-rows\n        with:\n          dataset: rest.dataset\n          config: rest.config\n          split: rest.split\n          offset: rest.offset\n          length: rest.length\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/datasets/{dataset}/search\n      name: dataset-search\n      description: Search dataset rows\n      operations:\n      - method: GET\n        name: search-rows\n        description: Search rows in a dataset\n        call: hf-dataset-viewer.search-rows\n        with:\n          dataset: rest.dataset\n          config: rest.config\n          split: rest.split\n          query: rest.query\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/spaces\n      name: spaces\n      description: Manage Spaces on the Hub\n      operations:\n      - method: GET\n        name: list-spaces\n        description: List and search Spaces\n        call: hf-hub.list-spaces\n        with:\n          search: rest.search\n          author: rest.author\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/repos\n      name: repos\n      description: Create repositories\n      operations:\n\
  \      - method: POST\n        name: create-repo\n        description: Create a new repository\n        call: hf-hub.create-repo\n        with:\n          type: rest.type\n          name: rest.name\n          organization: rest.organization\n          private: rest.private\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/user\n      name: user\n      description: User information\n      operations:\n      - method: GET\n        name: whoami\n        description: Get authenticated user info\n        call: hf-hub.whoami\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: hf-hub-data-mcp\n    transport: http\n    description: MCP server for AI-assisted Hugging Face Hub management and dataset exploration.\n    tools:\n    - name: list-models\n      description: List and search ML models on the Hugging Face Hub.\n      hints:\n        readOnly: true\n        openWorld: true\n     \
  \ call: hf-hub.list-models\n      with:\n        search: tools.search\n        author: tools.author\n        filter: tools.filter\n        sort: tools.sort\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model\n      description: Get detailed information about a specific model.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-hub.get-model\n      with:\n        repo_id: tools.repo_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-model-revision\n      description: Get model information at a specific revision or branch.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-hub.get-model-revision\n      with:\n        repo_id: tools.repo_id\n        revision: tools.revision\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-datasets\n      description: List and search datasets on the Hub.\n      hints:\n\
  \        readOnly: true\n        openWorld: true\n      call: hf-hub.list-datasets\n      with:\n        search: tools.search\n        author: tools.author\n        filter: tools.filter\n        sort: tools.sort\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset\n      description: Get detailed information about a specific dataset.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-hub.get-dataset\n      with:\n        repo_id: tools.repo_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset-parquet\n      description: Get parquet file URLs for a dataset.\n      hints:\n        readOnly: true\n      call: hf-hub.get-dataset-parquet\n      with:\n        repo_id: tools.repo_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-spaces\n      description: List and search Spaces on the Hub.\n      hints:\n        readOnly:\
  \ true\n        openWorld: true\n      call: hf-hub.list-spaces\n      with:\n        search: tools.search\n        author: tools.author\n        sort: tools.sort\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-space\n      description: Get detailed information about a specific Space.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: hf-hub.get-space\n      with:\n        repo_id: tools.repo_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repo\n      description: Create a new model, dataset, or Space repository on the Hub.\n      hints:\n        readOnly: false\n      call: hf-hub.create-repo\n      with:\n        type: tools.type\n        name: tools.name\n        organization: tools.organization\n        private: tools.private\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-repo\n      description: Delete a repository\
  \ from the Hub.\n      hints:\n        readOnly: false\n        destructive: true\n      call: hf-hub.delete-repo\n      with:\n        type: tools.type\n        name: tools.name\n        organization: tools.organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-repo-settings\n      description: Update settings for a repository.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: hf-hub.update-repo-settings\n      with:\n        repo_type: tools.repo_type\n        repo_id: tools.repo_id\n        private: tools.private\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: whoami\n      description: Get information about the authenticated user.\n      hints:\n        readOnly: true\n      call: hf-hub.whoami\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-model-tags\n      description: List all available model tags grouped by type.\n      hints:\n     \
  \   readOnly: true\n      call: hf-hub.list-model-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-dataset-tags\n      description: List all available dataset tags grouped by type.\n      hints:\n        readOnly: true\n      call: hf-hub.list-dataset-tags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-dataset-validity\n      description: Check if a dataset is valid and available on the Hub.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.is-valid\n      with:\n        dataset: tools.dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset-splits\n      description: Get the list of splits for a dataset.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-splits\n      with:\n        dataset: tools.dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: preview-dataset-rows\n      description:\
  \ Get the first rows of a dataset split for preview.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-first-rows\n      with:\n        dataset: tools.dataset\n        config: tools.config\n        split: tools.split\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset-rows\n      description: Get rows from a dataset split with pagination.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-rows\n      with:\n        dataset: tools.dataset\n        config: tools.config\n        split: tools.split\n        offset: tools.offset\n        length: tools.length\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-dataset\n      description: Search for rows matching a query in a dataset.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.search-rows\n      with:\n        dataset: tools.dataset\n        config: tools.config\n        split: tools.split\n     \
  \   query: tools.query\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: filter-dataset\n      description: Filter dataset rows using a condition.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.filter-rows\n      with:\n        dataset: tools.dataset\n        config: tools.config\n        split: tools.split\n        where: tools.where\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset-size\n      description: Get size information for a dataset.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-dataset-size\n      with:\n        dataset: tools.dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-dataset-statistics\n      description: Get statistical information about a dataset split.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-statistics\n      with:\n        dataset: tools.dataset\n        config: tools.config\n\
  \        split: tools.split\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-croissant-metadata\n      description: Get Croissant metadata for a dataset.\n      hints:\n        readOnly: true\n      call: hf-dataset-viewer.get-croissant-metadata\n      with:\n        dataset: tools.dataset\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
