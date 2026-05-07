---
categories: []
consumed_apis: []
description: Unified capability for managing laboratory data across Scispot's LIMS, ELN, sample tracking, sequence management, and container manifests. Enables computational biologists, lab automation engineers, and data scientists to programmatically access and manipulate all lab data in one unified workflow interface with REST and MCP adapters.
layout: capability
name: Scispot Lab Data Management
operations:
- description: List all LIMS labsheets in the workspace
  method: GET
  name: list-labsheets
  path: /v1/labsheets
- description: Retrieve all data rows from a labsheet
  method: GET
  name: get-labsheet-rows
  path: /v1/labsheets/{labsheetId}/rows
- description: Add a new row to a labsheet
  method: POST
  name: add-labsheet-row
  path: /v1/labsheets/{labsheetId}/rows
- description: Get a specific row by ID
  method: GET
  name: get-labsheet-row
  path: /v1/labsheets/{labsheetId}/rows/{rowId}
- description: Update an existing labsheet row
  method: PUT
  name: update-labsheet-row
  path: /v1/labsheets/{labsheetId}/rows/{rowId}
- description: Delete a labsheet row
  method: DELETE
  name: delete-labsheet-row
  path: /v1/labsheets/{labsheetId}/rows/{rowId}
- description: Find all records associated with a sample barcode
  method: GET
  name: search-by-barcode
  path: /v1/samples/search/{barcode}
- description: List all Electronic Lab Notebooks
  method: GET
  name: list-notebooks
  path: /v1/notebooks
- description: List entries in a notebook
  method: GET
  name: list-notebook-entries
  path: /v1/notebooks/{notebookId}/entries
- description: Create a new notebook entry
  method: POST
  name: create-notebook-entry
  path: /v1/notebooks/{notebookId}/entries
- description: List all physical container manifests
  method: GET
  name: list-manifests
  path: /v1/manifests
- description: Create a new physical container manifest
  method: POST
  name: create-manifest
  path: /v1/manifests
- description: Get a specific manifest with its contents
  method: GET
  name: get-manifest
  path: /v1/manifests/{manifestId}
- description: List all biological sequences
  method: GET
  name: list-sequences
  path: /v1/sequences
- description: Add a new biological sequence
  method: POST
  name: create-sequence
  path: /v1/sequences
- description: Get a specific sequence with annotations
  method: GET
  name: get-sequence
  path: /v1/sequences/{sequenceId}
- description: Update a biological sequence
  method: PUT
  name: update-sequence
  path: /v1/sequences/{sequenceId}
personas: []
provider_name: Scispot
provider_slug: scispot
search_terms:
- individual manifest operations
- add a new data row to a scispot labsheet. supports barcode assignment and custom column values. use for sample registration, assay result entry, and inventory updates.
- search all scispot data by sample barcode. returns all records across labsheets and experiments associated with the specified barcode.
- search by barcode
- list all electronic lab notebook (eln) notebooks in the scispot workspace. notebooks contain experimental protocols, observations, and research notes.
- laboratory
- add a new biological sequence to the scispot database. supports dna, rna, protein, and chemical structure sequences with full annotation support.
- add labsheet row
- automation
- eln notebook management
- get a specific sequence with annotations
- update a biological sequence
- lims
- list all biological sequences (dna, rna, protein, chemical) stored in the scispot workspace with their metadata and annotations.
- create a new physical container manifest
- individual sequence operations
- container manifest management (plates, boxes, racks)
- biotech
- list sequences
- scientific data
- sequences
- retrieve all data rows from a labsheet
- create manifest
- list labsheets
- biological sequence management
- update labsheet row
- update sequence
- get sequence
- delete a row from a scispot labsheet. use with caution as this permanently removes the record from the lims.
- sample lookup by barcode
- create notebook entry
- create a new entry in a scispot eln notebook. entries can be experiments, protocol executions, observations, or research notes.
- list entries in a notebook
- update an existing labsheet row
- life science
- list notebooks
- update an existing row in a scispot labsheet with new column values. used for updating sample status, adding results, or correcting data.
- healthcare
- retrieve a specific biological sequence by id including its full sequence string, annotations, features, and associated metadata.
- list all lims labsheets (data tables) in the scispot workspace. labsheets are used for sample registries, assay results, inventory tracking, and any structured lab data.
- list notebook entries
- lims labsheet management
- labsheet row data management
- add a new row to a labsheet
- list all lims labsheets in the workspace
- list all physical container manifests (plates, boxes, racks) in the scispot workspace. manifests track sample storage organization.
- list all biological sequences
- add a new biological sequence
- eln notebook entry management
- delete a labsheet row
- get manifest
- create a new notebook entry
- samples
- list all electronic lab notebooks
- get labsheet row
- delete labsheet row
- eln
- get labsheet rows
- get a specific manifest with its contents
- list all physical container manifests
- api first
- list manifests
- create sequence
- create a new physical container manifest (plate, box, or rack) in scispot for organizing and tracking sample storage.
- individual labsheet row operations
- find all records associated with a sample barcode
- retrieve all data rows from a specific scispot labsheet. returns the full dataset with all column values for each row in the specified lims table.
- get a specific row by id
slug: lab-data-management
source_filename: lab-data-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Scispot Lab Data Management\n  description: Unified capability for managing laboratory data across Scispot's LIMS, ELN, sample tracking, sequence management,\n    and container manifests. Enables computational biologists, lab automation engineers, and data scientists to programmatically\n    access and manipulate all lab data in one unified workflow interface with REST and MCP adapters.\n  tags:\n  - Laboratory\n  - LIMS\n  - ELN\n  - Life Science\n  - Biotech\n  - Samples\n  - Sequences\n  - Automation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCISPOT_API_KEY: SCISPOT_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scispot\n    baseUri: https://api.scispot.com/v1\n    description: Scispot laboratory data platform API\n    authentication:\n      type: apikey\n      key: apiKey\n      value: '{{SCISPOT_API_KEY}}'\n      placement: header\n    resources:\n    - name: labsheets\n\
  \      path: /labsheets\n      description: List all labsheets in the workspace\n      operations:\n      - name: list-labsheets\n        method: GET\n        description: Retrieve all LIMS-style data tables\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labsheet-rows\n      path: /labsheets/{labsheetId}/rows\n      description: Manage rows within a specific labsheet\n      operations:\n      - name: get-labsheet-rows\n        method: GET\n        description: Retrieve all rows from a labsheet\n        inputParameters:\n        - name: labsheetId\n          in: path\n          type: string\n          required:\
  \ true\n          description: Labsheet identifier\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Rows per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-labsheet-row\n        method: POST\n        description: Add a new data row to a labsheet\n        inputParameters:\n        - name: labsheetId\n          in: path\n          type: string\n          required: true\n          description: Labsheet identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            barcode: '{{tools.barcode}}'\n            data: '{{tools.data}}'\n    - name: labsheet-row\n\
  \      path: /labsheets/{labsheetId}/rows/{rowId}\n      description: Manage a specific labsheet row\n      operations:\n      - name: get-labsheet-row\n        method: GET\n        description: Get a specific row by ID\n        inputParameters:\n        - name: labsheetId\n          in: path\n          type: string\n          required: true\n          description: Labsheet identifier\n        - name: rowId\n          in: path\n          type: string\n          required: true\n          description: Row identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-labsheet-row\n        method: PUT\n        description: Update an existing labsheet row\n        inputParameters:\n        - name: labsheetId\n          in: path\n          type: string\n          required: true\n          description: Labsheet identifier\n        - name: rowId\n          in: path\n          type: string\n      \
  \    required: true\n          description: Row identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            data: '{{tools.data}}'\n      - name: delete-labsheet-row\n        method: DELETE\n        description: Delete a row from a labsheet\n        inputParameters:\n        - name: labsheetId\n          in: path\n          type: string\n          required: true\n          description: Labsheet identifier\n        - name: rowId\n          in: path\n          type: string\n          required: true\n          description: Row identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: barcode-search\n      path: /results/search/{barcode}\n      description: Search results by barcode\n      operations:\n      - name: search-by-barcode\n        method: GET\n\
  \        description: Find all records associated with a barcode\n        inputParameters:\n        - name: barcode\n          in: path\n          type: string\n          required: true\n          description: Barcode identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: eln-notebooks\n      path: /eln/notebooks\n      description: Manage ELN notebooks\n      operations:\n      - name: list-notebooks\n        method: GET\n        description: List all ELN notebooks\n        inputParameters:\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Results per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ notebook-entries\n      path: /eln/notebooks/{notebookId}/entries\n      description: Manage entries within an ELN notebook\n      operations:\n      - name: list-notebook-entries\n        method: GET\n        description: List all entries in a notebook\n        inputParameters:\n        - name: notebookId\n          in: path\n          type: string\n          required: true\n          description: Notebook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notebook-entry\n        method: POST\n        description: Create a new notebook entry (experiment, protocol, or observation)\n        inputParameters:\n        - name: notebookId\n          in: path\n          type: string\n          required: true\n          description: Notebook identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    \
  \    body:\n          type: json\n          data:\n            title: '{{tools.title}}'\n            type: '{{tools.entry_type}}'\n            content: '{{tools.content}}'\n    - name: manifests\n      path: /manifests\n      description: Manage physical container manifests\n      operations:\n      - name: list-manifests\n        method: GET\n        description: List all manifests (plates, boxes, racks)\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Container type filter (plate, box, rack)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-manifest\n        method: POST\n        description: Create a new physical container manifest\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            name: '{{tools.name}}'\n            type: '{{tools.container_type}}'\n            barcode: '{{tools.barcode}}'\n    - name: manifest-detail\n      path: /manifests/{manifestId}\n      description: Get a specific manifest by ID\n      operations:\n      - name: get-manifest\n        method: GET\n        description: Retrieve a single manifest with its contents\n        inputParameters:\n        - name: manifestId\n          in: path\n          type: string\n          required: true\n          description: Manifest identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sequences\n      path: /sequences\n      description: Manage biological sequences\n      operations:\n      - name: list-sequences\n        method: GET\n        description: List all biological sequences (DNA, RNA, protein, chemical)\n        inputParameters:\n        - name: type\n          in: query\n\
  \          type: string\n          required: false\n          description: Sequence type filter (dna, rna, protein, chemical)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-sequence\n        method: POST\n        description: Add a new biological sequence with annotations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.sequence_type}}'\n            sequence: '{{tools.sequence}}'\n    - name: sequence-detail\n      path: /sequences/{sequenceId}\n      description: Manage a specific sequence by ID\n      operations:\n      - name: get-sequence\n        method: GET\n        description: Retrieve a single sequence with annotations\n        inputParameters:\n        - name: sequenceId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Sequence identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-sequence\n        method: PUT\n        description: Update an existing biological sequence\n        inputParameters:\n        - name: sequenceId\n          in: path\n          type: string\n          required: true\n          description: Sequence identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            sequence: '{{tools.sequence}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: scispot-lab-management-api\n    description: Unified REST API for Scispot lab data management workflows.\n    resources:\n    - path: /v1/labsheets\n      name: labsheets\n\
  \      description: LIMS labsheet management\n      operations:\n      - method: GET\n        name: list-labsheets\n        description: List all LIMS labsheets in the workspace\n        call: scispot.list-labsheets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labsheets/{labsheetId}/rows\n      name: labsheet-rows\n      description: Labsheet row data management\n      operations:\n      - method: GET\n        name: get-labsheet-rows\n        description: Retrieve all data rows from a labsheet\n        call: scispot.get-labsheet-rows\n        with:\n          labsheetId: rest.labsheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: add-labsheet-row\n        description: Add a new row to a labsheet\n        call: scispot.add-labsheet-row\n        with:\n          labsheetId: rest.labsheetId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/labsheets/{labsheetId}/rows/{rowId}\n\
  \      name: labsheet-row\n      description: Individual labsheet row operations\n      operations:\n      - method: GET\n        name: get-labsheet-row\n        description: Get a specific row by ID\n        call: scispot.get-labsheet-row\n        with:\n          labsheetId: rest.labsheetId\n          rowId: rest.rowId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-labsheet-row\n        description: Update an existing labsheet row\n        call: scispot.update-labsheet-row\n        with:\n          labsheetId: rest.labsheetId\n          rowId: rest.rowId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-labsheet-row\n        description: Delete a labsheet row\n        call: scispot.delete-labsheet-row\n        with:\n          labsheetId: rest.labsheetId\n          rowId: rest.rowId\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /v1/samples/search/{barcode}\n      name: barcode-lookup\n      description: Sample lookup by barcode\n      operations:\n      - method: GET\n        name: search-by-barcode\n        description: Find all records associated with a sample barcode\n        call: scispot.search-by-barcode\n        with:\n          barcode: rest.barcode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notebooks\n      name: notebooks\n      description: ELN notebook management\n      operations:\n      - method: GET\n        name: list-notebooks\n        description: List all Electronic Lab Notebooks\n        call: scispot.list-notebooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notebooks/{notebookId}/entries\n      name: notebook-entries\n      description: ELN notebook entry management\n      operations:\n      - method: GET\n        name: list-notebook-entries\n        description: List entries\
  \ in a notebook\n        call: scispot.list-notebook-entries\n        with:\n          notebookId: rest.notebookId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-notebook-entry\n        description: Create a new notebook entry\n        call: scispot.create-notebook-entry\n        with:\n          notebookId: rest.notebookId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manifests\n      name: manifests\n      description: Container manifest management (plates, boxes, racks)\n      operations:\n      - method: GET\n        name: list-manifests\n        description: List all physical container manifests\n        call: scispot.list-manifests\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-manifest\n        description: Create a new physical container manifest\n        call: scispot.create-manifest\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/manifests/{manifestId}\n      name: manifest-detail\n      description: Individual manifest operations\n      operations:\n      - method: GET\n        name: get-manifest\n        description: Get a specific manifest with its contents\n        call: scispot.get-manifest\n        with:\n          manifestId: rest.manifestId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/sequences\n      name: sequences\n      description: Biological sequence management\n      operations:\n      - method: GET\n        name: list-sequences\n        description: List all biological sequences\n        call: scispot.list-sequences\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-sequence\n        description: Add a new biological sequence\n        call: scispot.create-sequence\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /v1/sequences/{sequenceId}\n      name: sequence-detail\n      description: Individual sequence operations\n      operations:\n      - method: GET\n        name: get-sequence\n        description: Get a specific sequence with annotations\n        call: scispot.get-sequence\n        with:\n          sequenceId: rest.sequenceId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-sequence\n        description: Update a biological sequence\n        call: scispot.update-sequence\n        with:\n          sequenceId: rest.sequenceId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: scispot-lab-management-mcp\n    transport: http\n    description: MCP server for AI-assisted lab data management using Scispot.\n    tools:\n    - name: list-labsheets\n      description: List all LIMS labsheets (data tables) in the\
  \ Scispot workspace. Labsheets are used for sample registries,\n        assay results, inventory tracking, and any structured lab data.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.list-labsheets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-labsheet-rows\n      description: Retrieve all data rows from a specific Scispot labsheet. Returns the full dataset with all column values\n        for each row in the specified LIMS table.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.get-labsheet-rows\n      with:\n        labsheetId: tools.labsheetId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-labsheet-row\n      description: Add a new data row to a Scispot labsheet. Supports barcode assignment and custom column values. Use for\n        sample registration, assay result entry, and inventory updates.\n      hints:\n        readOnly: false\n\
  \        destructive: false\n        idempotent: false\n      call: scispot.add-labsheet-row\n      with:\n        labsheetId: tools.labsheetId\n        barcode: tools.barcode\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-labsheet-row\n      description: Update an existing row in a Scispot labsheet with new column values. Used for updating sample status, adding\n        results, or correcting data.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: scispot.update-labsheet-row\n      with:\n        labsheetId: tools.labsheetId\n        rowId: tools.rowId\n        data: tools.data\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-labsheet-row\n      description: Delete a row from a Scispot labsheet. Use with caution as this permanently removes the record from the\n        LIMS.\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: scispot.delete-labsheet-row\n      with:\n        labsheetId: tools.labsheetId\n        rowId: tools.rowId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-by-barcode\n      description: Search all Scispot data by sample barcode. Returns all records across labsheets and experiments associated\n        with the specified barcode.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.search-by-barcode\n      with:\n        barcode: tools.barcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notebooks\n      description: List all Electronic Lab Notebook (ELN) notebooks in the Scispot workspace. Notebooks contain experimental\n        protocols, observations, and research notes.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.list-notebooks\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: create-notebook-entry\n      description: Create a new entry in a Scispot ELN notebook. Entries can be experiments, protocol executions, observations,\n        or research notes.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scispot.create-notebook-entry\n      with:\n        notebookId: tools.notebookId\n        title: tools.title\n        entry_type: tools.entry_type\n        content: tools.content\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-manifests\n      description: List all physical container manifests (plates, boxes, racks) in the Scispot workspace. Manifests track\n        sample storage organization.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.list-manifests\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-manifest\n      description: Create a new physical container manifest (plate,\
  \ box, or rack) in Scispot for organizing and tracking sample\n        storage.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: scispot.create-manifest\n      with:\n        name: tools.name\n        container_type: tools.container_type\n        barcode: tools.barcode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-sequences\n      description: List all biological sequences (DNA, RNA, protein, chemical) stored in the Scispot workspace with their\n        metadata and annotations.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.list-sequences\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-sequence\n      description: Add a new biological sequence to the Scispot database. Supports DNA, RNA, protein, and chemical structure\n        sequences with full annotation support.\n      hints:\n        readOnly: false\n     \
  \   destructive: false\n        idempotent: false\n      call: scispot.create-sequence\n      with:\n        name: tools.name\n        sequence_type: tools.sequence_type\n        sequence: tools.sequence\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-sequence\n      description: Retrieve a specific biological sequence by ID including its full sequence string, annotations, features,\n        and associated metadata.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scispot.get-sequence\n      with:\n        sequenceId: tools.sequenceId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scispot/refs/heads/main/capabilities/lab-data-management.yaml
tags:
- Laboratory
- LIMS
- ELN
- Life Science
- Biotech
- Samples
- Sequences
- Automation
tools:
- description: List all LIMS labsheets (data tables) in the Scispot workspace. Labsheets are used for sample registries, assay results, inventory tracking, and any structured lab data.
  hints:
    idempotent: true
    readOnly: true
  name: list-labsheets
- description: Retrieve all data rows from a specific Scispot labsheet. Returns the full dataset with all column values for each row in the specified LIMS table.
  hints:
    idempotent: true
    readOnly: true
  name: get-labsheet-rows
- description: Add a new data row to a Scispot labsheet. Supports barcode assignment and custom column values. Use for sample registration, assay result entry, and inventory updates.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-labsheet-row
- description: Update an existing row in a Scispot labsheet with new column values. Used for updating sample status, adding results, or correcting data.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-labsheet-row
- description: Delete a row from a Scispot labsheet. Use with caution as this permanently removes the record from the LIMS.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-labsheet-row
- description: Search all Scispot data by sample barcode. Returns all records across labsheets and experiments associated with the specified barcode.
  hints:
    idempotent: true
    readOnly: true
  name: search-by-barcode
- description: List all Electronic Lab Notebook (ELN) notebooks in the Scispot workspace. Notebooks contain experimental protocols, observations, and research notes.
  hints:
    idempotent: true
    readOnly: true
  name: list-notebooks
- description: Create a new entry in a Scispot ELN notebook. Entries can be experiments, protocol executions, observations, or research notes.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-notebook-entry
- description: List all physical container manifests (plates, boxes, racks) in the Scispot workspace. Manifests track sample storage organization.
  hints:
    idempotent: true
    readOnly: true
  name: list-manifests
- description: Create a new physical container manifest (plate, box, or rack) in Scispot for organizing and tracking sample storage.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-manifest
- description: List all biological sequences (DNA, RNA, protein, chemical) stored in the Scispot workspace with their metadata and annotations.
  hints:
    idempotent: true
    readOnly: true
  name: list-sequences
- description: Add a new biological sequence to the Scispot database. Supports DNA, RNA, protein, and chemical structure sequences with full annotation support.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-sequence
- description: Retrieve a specific biological sequence by ID including its full sequence string, annotations, features, and associated metadata.
  hints:
    idempotent: true
    readOnly: true
  name: get-sequence
---
