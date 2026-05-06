---
categories: []
consumed_apis: []
description: Colab notebooks are stored as Google Drive files with the MIME type application/vnd.google.colaboratory. This API specification covers the Google Drive v3 endpoints commonly used to manage Colab notebooks, including listing, creating, updating, and sharing notebooks.
layout: capability
name: Google Colab Notebooks via Drive API
operations:
- description: Google Colab List Colab notebooks
  method: GET
  name: listnotebooks
  path: /files
- description: Google Colab Create a Colab notebook
  method: POST
  name: createnotebook
  path: /files
- description: Google Colab Get notebook metadata
  method: GET
  name: getnotebook
  path: /files/{fileId}
- description: Google Colab Update notebook metadata
  method: PATCH
  name: updatenotebook
  path: /files/{fileId}
- description: Google Colab Delete a notebook
  method: DELETE
  name: deletenotebook
  path: /files/{fileId}
- description: Google Colab Copy a notebook
  method: POST
  name: copynotebook
  path: /files/{fileId}/copy
- description: Google Colab List notebook permissions
  method: GET
  name: listpermissions
  path: /files/{fileId}/permissions
- description: Google Colab Share a notebook
  method: POST
  name: createpermission
  path: /files/{fileId}/permissions
personas: []
provider_name: Google Colab
provider_slug: google-colab
search_terms:
- google colab create a colab notebook
- google colab update notebook metadata
- colab
- google colab delete a notebook
- notebooks
- listnotebooks
- createpermission
- google colab share a notebook
- google colab list notebook permissions
- jupyter
- deletenotebook
- google colab get notebook metadata
- google
- updatenotebook
- copynotebook
- getnotebook
- google cloud
- google colab copy a notebook
- machine learning
- api
- python
- createnotebook
- collaboration
- data science
- google colab list colab notebooks
- listpermissions
slug: google-colab-capability
source_filename: google-colab-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Colab Notebooks via Drive API\n  description: Colab notebooks are stored as Google Drive files with the MIME type application/vnd.google.colaboratory. This\n    API specification covers the Google Drive v3 endpoints commonly used to manage Colab notebooks, including listing, creating,\n    updating, and sharing notebooks.\n  tags:\n  - Google\n  - Colab\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-colab\n    baseUri: https://www.googleapis.com/drive/v3\n    description: Google Colab Notebooks via Drive API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_COLAB_TOKEN}}'\n    resources:\n    - name: files\n      path: /files\n      operations:\n      - name: listnotebooks\n        method: GET\n        description: Google Colab List Colab notebooks\n        inputParameters:\n        - name: q\n          in: query\n          type:\
  \ string\n          description: Query string for filtering (e.g. mimeType filter for Colab files)\n        - name: pageSize\n          in: query\n          type: integer\n          description: Maximum number of files to return\n        - name: pageToken\n          in: query\n          type: string\n          description: Token for next page of results\n        - name: fields\n          in: query\n          type: string\n          description: Fields to include in the response\n        - name: orderBy\n          in: query\n          type: string\n          description: Sort order (e.g. modifiedTime desc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createnotebook\n        method: POST\n        description: Google Colab Create a Colab notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid\n\
  \      path: /files/{fileId}\n      operations:\n      - name: getnotebook\n        method: GET\n        description: Google Colab Get notebook metadata\n        inputParameters:\n        - name: fields\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatenotebook\n        method: PATCH\n        description: Google Colab Update notebook metadata\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletenotebook\n        method: DELETE\n        description: Google Colab Delete a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid-copy\n      path: /files/{fileId}/copy\n      operations:\n      - name: copynotebook\n        method: POST\n        description:\
  \ Google Colab Copy a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: files-fileid-permissions\n      path: /files/{fileId}/permissions\n      operations:\n      - name: listpermissions\n        method: GET\n        description: Google Colab List notebook permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpermission\n        method: POST\n        description: Google Colab Share a notebook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-colab-rest\n    description: REST adapter for Google Colab Notebooks via Drive API.\n    resources:\n    - path: /files\n      name: listnotebooks\n      operations:\n      - method: GET\n        name: listnotebooks\n\
  \        description: Google Colab List Colab notebooks\n        call: google-colab.listnotebooks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files\n      name: createnotebook\n      operations:\n      - method: POST\n        name: createnotebook\n        description: Google Colab Create a Colab notebook\n        call: google-colab.createnotebook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: getnotebook\n      operations:\n      - method: GET\n        name: getnotebook\n        description: Google Colab Get notebook metadata\n        call: google-colab.getnotebook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: updatenotebook\n      operations:\n      - method: PATCH\n        name: updatenotebook\n        description: Google Colab Update notebook metadata\n        call: google-colab.updatenotebook\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}\n      name: deletenotebook\n      operations:\n      - method: DELETE\n        name: deletenotebook\n        description: Google Colab Delete a notebook\n        call: google-colab.deletenotebook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/copy\n      name: copynotebook\n      operations:\n      - method: POST\n        name: copynotebook\n        description: Google Colab Copy a notebook\n        call: google-colab.copynotebook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/permissions\n      name: listpermissions\n      operations:\n      - method: GET\n        name: listpermissions\n        description: Google Colab List notebook permissions\n        call: google-colab.listpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /files/{fileId}/permissions\n\
  \      name: createpermission\n      operations:\n      - method: POST\n        name: createpermission\n        description: Google Colab Share a notebook\n        call: google-colab.createpermission\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-colab-mcp\n    transport: http\n    description: MCP adapter for Google Colab Notebooks via Drive API for AI agent use.\n    tools:\n    - name: listnotebooks\n      description: Google Colab List Colab notebooks\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-colab.listnotebooks\n      with:\n        q: tools.q\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        fields: tools.fields\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: q\n        type: string\n        description: Query string for filtering (e.g. mimeType filter for Colab files)\n      - name:\
  \ pageSize\n        type: integer\n        description: Maximum number of files to return\n      - name: pageToken\n        type: string\n        description: Token for next page of results\n      - name: fields\n        type: string\n        description: Fields to include in the response\n      - name: orderBy\n        type: string\n        description: Sort order (e.g. modifiedTime desc)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createnotebook\n      description: Google Colab Create a Colab notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-colab.createnotebook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getnotebook\n      description: Google Colab Get notebook metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-colab.getnotebook\n      with:\n        fields: tools.fields\n\
  \      inputParameters:\n      - name: fields\n        type: string\n        description: fields\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatenotebook\n      description: Google Colab Update notebook metadata\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-colab.updatenotebook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletenotebook\n      description: Google Colab Delete a notebook\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-colab.deletenotebook\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: copynotebook\n      description: Google Colab Copy a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-colab.copynotebook\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listpermissions\n      description: Google Colab List notebook permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-colab.listpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpermission\n      description: Google Colab Share a notebook\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-colab.createpermission\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_COLAB_TOKEN: GOOGLE_COLAB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-colab/refs/heads/main/capabilities/google-colab-capability.yaml
tags:
- Google
- Colab
- API
tools:
- description: Google Colab List Colab notebooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listnotebooks
- description: Google Colab Create a Colab notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createnotebook
- description: Google Colab Get notebook metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnotebook
- description: Google Colab Update notebook metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatenotebook
- description: Google Colab Delete a notebook
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletenotebook
- description: Google Colab Copy a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: copynotebook
- description: Google Colab List notebook permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermissions
- description: Google Colab Share a notebook
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpermission
---
