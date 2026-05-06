---
categories: []
consumed_apis: []
description: Unified workflow capability for bioinformatics and data science on the CyVerse Discovery Environment. Enables researchers, bioinformaticians, and data scientists to manage data in iRODS, discover and launch analysis applications, monitor jobs, annotate datasets with metadata, share data with collaborators, and request persistent identifiers for publication-ready datasets.
layout: capability
name: CyVerse Data Science Workflow
operations:
- description: List directory contents in iRODS
  method: GET
  name: list-directory
  path: /v1/filesystem
- description: Get user's root iRODS directory
  method: GET
  name: get-root-directory
  path: /v1/filesystem/root
- description: Search iRODS for files and directories
  method: GET
  name: search-filesystem
  path: /v1/filesystem/search
- description: Get AVU metadata for a path
  method: GET
  name: get-file-metadata
  path: /v1/filesystem/metadata
- description: Browse available bioinformatics apps
  method: GET
  name: list-apps
  path: /v1/apps
- description: List user's analysis jobs
  method: GET
  name: list-analyses
  path: /v1/analyses
- description: Submit a new analysis job
  method: POST
  name: submit-analysis
  path: /v1/analyses
- description: List user notifications
  method: GET
  name: list-notifications
  path: /v1/notifications
personas: []
provider_name: Terrain Discovery Environment API
provider_slug: terrain-discovery-environment-api
search_terms:
- open science
- list apps
- browse available bioinformatics apps
- get file stats
- get size, permissions, and modification dates for an irods file or directory
- search data store
- list user's analysis jobs
- user root directory
- file metadata (avus)
- get avu metadata for a path
- list notifications
- browse an irods directory in the cyverse data store
- irods data store browsing
- move files or directories to the user's irods trash
- search filesystem
- list directory
- research computing
- get root directory
- user notifications
- submit a new analysis job
- get file metadata
- search the cyverse irods data store for files and folders by name
- share data
- cloud computing
- open source
- move files
- submit a new bioinformatics analysis job using a discovery environment application
- irods
- list the user's analysis job history in the discovery environment
- list analyses
- analysis job management
- life sciences
- search irods for files and directories
- cyverse
- move files or directories to a new location in irods
- list user notifications
- delete files
- filesystem
- browse bioinformatics and data science apps in the discovery environment
- get the root directory structure for the cyverse user account
- share irods data (files/folders) with other cyverse users
- get user's root irods directory
- get irods avu metadata triples for a file or directory
- get recent notifications about completed analyses and system events
- application discovery
- data science
- list directory contents in irods
- bioinformatics
- submit analysis
slug: data-science-workflow
source_filename: data-science-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CyVerse Data Science Workflow\n  description: Unified workflow capability for bioinformatics and data science on the CyVerse Discovery Environment. Enables\n    researchers, bioinformaticians, and data scientists to manage data in iRODS, discover and launch analysis applications,\n    monitor jobs, annotate datasets with metadata, share data with collaborators, and request persistent identifiers for publication-ready\n    datasets.\n  tags:\n  - CyVerse\n  - Bioinformatics\n  - Data Science\n  - iRODS\n  - Life Sciences\n  - Research Computing\n  - Open Science\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TERRAIN_JWT_TOKEN: TERRAIN_JWT_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: terrain\n    baseUri: https://de.cyverse.org/terrain\n    description: Terrain Discovery Environment primary REST API\n    authentication:\n      type: bearer\n      token: '{{TERRAIN_JWT_TOKEN}}'\n\
  \    resources:\n    - name: filesystem-directory\n      path: /secured/filesystem/directory\n      description: Browse and create iRODS directories\n      operations:\n      - name: list-directory\n        method: GET\n        description: List contents of a directory in iRODS\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: iRODS path of the directory\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max entries to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-root\n      path: /secured/filesystem/root\n      description: Get root directory for the user\n      operations:\n  \
  \    - name: get-root-directory\n        method: GET\n        description: Get the root directory listing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-stat\n      path: /secured/filesystem/stat\n      description: Get file or directory statistics\n      operations:\n      - name: get-file-stats\n        method: GET\n        description: Get metadata and stats for a file or directory\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: iRODS path\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-search\n      path: /secured/filesystem/search\n      description: Search the iRODS filesystem\n      operations:\n      - name: search-filesystem\n        method: GET\n        description: Full-text search\
  \ across iRODS data store\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max results\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: 'Filter: file, folder, any'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-move\n      path: /secured/filesystem/move\n      description: Move files and directories\n      operations:\n      - name: move-files\n        method: POST\n        description: Move files or directories to a new location\n        body:\n          type: json\n          data:\n            sources: '{{tools.sources}}'\n            dest: '{{tools.dest}}'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-delete\n      path: /secured/filesystem/delete\n      description: Delete files and directories\n      operations:\n      - name: delete-files\n        method: POST\n        description: Move files or directories to the trash\n        body:\n          type: json\n          data:\n            paths: '{{tools.paths}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-metadata\n      path: /secured/filesystem/metadata\n      description: Manage iRODS metadata AVUs\n      operations:\n      - name: get-file-metadata\n        method: GET\n        description: Get metadata AVUs for a file or directory\n        inputParameters:\n        - name: path\n          in: query\n          type: string\n          required: true\n          description: iRODS path\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filesystem-share\n      path: /secured/filesystem/share\n      description: Share data with other users\n      operations:\n      - name: share-data\n        method: POST\n        description: Share files or directories with specified users\n        body:\n          type: json\n          data:\n            sharing: '{{tools.sharing}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apps\n      path: /secured/apps\n      description: Browse available applications\n      operations:\n      - name: list-apps\n        method: GET\n        description: List available applications in the Discovery Environment\n        inputParameters:\n        - name: search\n          in: query\n          type: string\n          required: false\n          description: Filter apps by name\n        - name:\
  \ limit\n          in: query\n          type: integer\n          required: false\n          description: Max apps to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: analyses\n      path: /secured/analyses\n      description: Submit and list analysis jobs\n      operations:\n      - name: list-analyses\n        method: GET\n        description: List analyses for the current user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max analyses to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: submit-analysis\n        method: POST\n        description: Submit a new\
  \ analysis job\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            app_id: '{{tools.app_id}}'\n            system_id: '{{tools.system_id}}'\n            config: '{{tools.config}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notifications\n      path: /secured/notifications\n      description: Manage user notifications\n      operations:\n      - name: list-notifications\n        method: GET\n        description: List notifications for the current user\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Max notifications\n        - name: seen\n          in: query\n          type: boolean\n          required: false\n          description: Filter by read/unread\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cyverse-data-science-api\n    description: Unified REST API for CyVerse Discovery Environment data science workflows.\n    resources:\n    - path: /v1/filesystem\n      name: filesystem\n      description: iRODS data store browsing\n      operations:\n      - method: GET\n        name: list-directory\n        description: List directory contents in iRODS\n        call: terrain.list-directory\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filesystem/root\n      name: filesystem-root\n      description: User root directory\n      operations:\n      - method: GET\n        name: get-root-directory\n        description: Get user's root iRODS directory\n        call: terrain.get-root-directory\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filesystem/search\n      name:\
  \ filesystem-search\n      description: Search data store\n      operations:\n      - method: GET\n        name: search-filesystem\n        description: Search iRODS for files and directories\n        call: terrain.search-filesystem\n        with:\n          search: rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/filesystem/metadata\n      name: metadata\n      description: File metadata (AVUs)\n      operations:\n      - method: GET\n        name: get-file-metadata\n        description: Get AVU metadata for a path\n        call: terrain.get-file-metadata\n        with:\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/apps\n      name: apps\n      description: Application discovery\n      operations:\n      - method: GET\n        name: list-apps\n        description: Browse available bioinformatics apps\n        call: terrain.list-apps\n        with:\n          search:\
  \ rest.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/analyses\n      name: analyses\n      description: Analysis job management\n      operations:\n      - method: GET\n        name: list-analyses\n        description: List user's analysis jobs\n        call: terrain.list-analyses\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: submit-analysis\n        description: Submit a new analysis job\n        call: terrain.submit-analysis\n        with:\n          name: rest.name\n          app_id: rest.app_id\n          system_id: rest.system_id\n          config: rest.config\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notifications\n      name: notifications\n      description: User notifications\n      operations:\n      - method: GET\n        name: list-notifications\n        description: List user notifications\n        call: terrain.list-notifications\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cyverse-data-science-mcp\n    transport: http\n    description: MCP server for AI-assisted CyVerse Discovery Environment data science workflows.\n    tools:\n    - name: list-directory\n      description: Browse an iRODS directory in the CyVerse data store\n      hints:\n        readOnly: true\n        openWorld: true\n      call: terrain.list-directory\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-root-directory\n      description: Get the root directory structure for the CyVerse user account\n      hints:\n        readOnly: true\n        openWorld: false\n      call: terrain.get-root-directory\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-stats\n      description: Get size, permissions, and modification dates for an iRODS file or directory\n   \
  \   hints:\n        readOnly: true\n        openWorld: false\n      call: terrain.get-file-stats\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-filesystem\n      description: Search the CyVerse iRODS data store for files and folders by name\n      hints:\n        readOnly: true\n        openWorld: true\n      call: terrain.search-filesystem\n      with:\n        search: tools.search\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: move-files\n      description: Move files or directories to a new location in iRODS\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: terrain.move-files\n      with:\n        sources: tools.sources\n        dest: tools.dest\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-files\n      description: Move files or directories to the\
  \ user's iRODS trash\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: false\n      call: terrain.delete-files\n      with:\n        paths: tools.paths\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-metadata\n      description: Get iRODS AVU metadata triples for a file or directory\n      hints:\n        readOnly: true\n        openWorld: false\n      call: terrain.get-file-metadata\n      with:\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: share-data\n      description: Share iRODS data (files/folders) with other CyVerse users\n      hints:\n        readOnly: false\n        destructive: false\n      call: terrain.share-data\n      with:\n        sharing: tools.sharing\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-apps\n      description: Browse bioinformatics and data science apps in the Discovery Environment\n\
  \      hints:\n        readOnly: true\n        openWorld: true\n      call: terrain.list-apps\n      with:\n        search: tools.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-analyses\n      description: List the user's analysis job history in the Discovery Environment\n      hints:\n        readOnly: true\n        openWorld: true\n      call: terrain.list-analyses\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: submit-analysis\n      description: Submit a new bioinformatics analysis job using a Discovery Environment application\n      hints:\n        readOnly: false\n        destructive: false\n      call: terrain.submit-analysis\n      with:\n        name: tools.name\n        app_id: tools.app_id\n        system_id: tools.system_id\n        config: tools.config\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notifications\n      description: Get recent notifications\
  \ about completed analyses and system events\n      hints:\n        readOnly: true\n        openWorld: true\n      call: terrain.list-notifications\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/terrain-discovery-environment-api/refs/heads/main/capabilities/data-science-workflow.yaml
tags:
- CyVerse
- Bioinformatics
- Data Science
- iRODS
- Life Sciences
- Research Computing
- Open Science
tools:
- description: Browse an iRODS directory in the CyVerse data store
  hints:
    openWorld: true
    readOnly: true
  name: list-directory
- description: Get the root directory structure for the CyVerse user account
  hints:
    openWorld: false
    readOnly: true
  name: get-root-directory
- description: Get size, permissions, and modification dates for an iRODS file or directory
  hints:
    openWorld: false
    readOnly: true
  name: get-file-stats
- description: Search the CyVerse iRODS data store for files and folders by name
  hints:
    openWorld: true
    readOnly: true
  name: search-filesystem
- description: Move files or directories to a new location in iRODS
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: move-files
- description: Move files or directories to the user's iRODS trash
  hints:
    destructive: true
    idempotent: false
    readOnly: false
  name: delete-files
- description: Get iRODS AVU metadata triples for a file or directory
  hints:
    openWorld: false
    readOnly: true
  name: get-file-metadata
- description: Share iRODS data (files/folders) with other CyVerse users
  hints:
    destructive: false
    readOnly: false
  name: share-data
- description: Browse bioinformatics and data science apps in the Discovery Environment
  hints:
    openWorld: true
    readOnly: true
  name: list-apps
- description: List the user's analysis job history in the Discovery Environment
  hints:
    openWorld: true
    readOnly: true
  name: list-analyses
- description: Submit a new bioinformatics analysis job using a Discovery Environment application
  hints:
    destructive: false
    readOnly: false
  name: submit-analysis
- description: Get recent notifications about completed analyses and system events
  hints:
    openWorld: true
    readOnly: true
  name: list-notifications
---
