---
api_specs:
- filename: terrain-openapi.yml
  format: yaml
  label: terrain
  slug: terrain
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/terrain-discovery-environment-api/refs/heads/main/openapi/terrain-openapi.yml
categories: []
consumed_apis:
- terrain
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
- list apps
- list user's analysis jobs
- filesystem
- share data
- open source
- bioinformatics
- get file metadata
- user notifications
- search filesystem
- submit analysis
- cyverse
- irods
- list user notifications
- get avu metadata for a path
- get root directory
- browse bioinformatics and data science apps in the discovery environment
- list the user's analysis job history in the discovery environment
- move files or directories to a new location in irods
- user root directory
- get user's root irods directory
- get file stats
- browse an irods directory in the cyverse data store
- get irods avu metadata triples for a file or directory
- browse available bioinformatics apps
- open science
- analysis job management
- list notifications
- get the root directory structure for the cyverse user account
- search the cyverse irods data store for files and folders by name
- submit a new bioinformatics analysis job using a discovery environment application
- list directory contents in irods
- application discovery
- list directory
- life sciences
- irods data store browsing
- search data store
- delete files
- research computing
- file metadata (avus)
- share irods data (files/folders) with other cyverse users
- get size, permissions, and modification dates for an irods file or directory
- data science
- search irods for files and directories
- get recent notifications about completed analyses and system events
- move files or directories to the user's irods trash
- move files
- submit a new analysis job
- cloud computing
- list analyses
slug: data-science-workflow
source_filename: data-science-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"CyVerse Data Science Workflow\"\n  description: >-\n    Unified workflow capability for bioinformatics and data science on the CyVerse\n    Discovery Environment. Enables researchers, bioinformaticians, and data scientists\n    to manage data in iRODS, discover and launch analysis applications, monitor jobs,\n    annotate datasets with metadata, share data with collaborators, and request\n    persistent identifiers for publication-ready datasets.\n  tags:\n    - CyVerse\n    - Bioinformatics\n    - Data Science\n    - iRODS\n    - Life Sciences\n    - Research Computing\n    - Open Science\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TERRAIN_JWT_TOKEN: TERRAIN_JWT_TOKEN\n\ncapability:\n  consumes:\n    - import: terrain\n      location: ./shared/terrain.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: cyverse-data-science-api\n      description: \"\
  Unified REST API for CyVerse Discovery Environment data science workflows.\"\n      resources:\n        - path: /v1/filesystem\n          name: filesystem\n          description: \"iRODS data store browsing\"\n          operations:\n            - method: GET\n              name: list-directory\n              description: \"List directory contents in iRODS\"\n              call: \"terrain.list-directory\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/filesystem/root\n          name: filesystem-root\n          description: \"User root directory\"\n          operations:\n            - method: GET\n              name: get-root-directory\n              description: \"Get user's root iRODS directory\"\n              call: \"terrain.get-root-directory\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        -\
  \ path: /v1/filesystem/search\n          name: filesystem-search\n          description: \"Search data store\"\n          operations:\n            - method: GET\n              name: search-filesystem\n              description: \"Search iRODS for files and directories\"\n              call: \"terrain.search-filesystem\"\n              with:\n                search: \"rest.search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/filesystem/metadata\n          name: metadata\n          description: \"File metadata (AVUs)\"\n          operations:\n            - method: GET\n              name: get-file-metadata\n              description: \"Get AVU metadata for a path\"\n              call: \"terrain.get-file-metadata\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/apps\n          name:\
  \ apps\n          description: \"Application discovery\"\n          operations:\n            - method: GET\n              name: list-apps\n              description: \"Browse available bioinformatics apps\"\n              call: \"terrain.list-apps\"\n              with:\n                search: \"rest.search\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/analyses\n          name: analyses\n          description: \"Analysis job management\"\n          operations:\n            - method: GET\n              name: list-analyses\n              description: \"List user's analysis jobs\"\n              call: \"terrain.list-analyses\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: submit-analysis\n              description: \"Submit a new analysis job\"\n              call: \"terrain.submit-analysis\"\n              with:\n\
  \                name: \"rest.name\"\n                app_id: \"rest.app_id\"\n                system_id: \"rest.system_id\"\n                config: \"rest.config\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/notifications\n          name: notifications\n          description: \"User notifications\"\n          operations:\n            - method: GET\n              name: list-notifications\n              description: \"List user notifications\"\n              call: \"terrain.list-notifications\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: cyverse-data-science-mcp\n      transport: http\n      description: \"MCP server for AI-assisted CyVerse Discovery Environment data science workflows.\"\n      tools:\n        - name: list-directory\n          description: \"Browse an iRODS directory in the CyVerse data\
  \ store\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terrain.list-directory\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-root-directory\n          description: \"Get the root directory structure for the CyVerse user account\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terrain.get-root-directory\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-stats\n          description: \"Get size, permissions, and modification dates for an iRODS file or directory\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terrain.get-file-stats\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\
  \n        - name: search-filesystem\n          description: \"Search the CyVerse iRODS data store for files and folders by name\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terrain.search-filesystem\"\n          with:\n            search: \"tools.search\"\n            type: \"tools.type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: move-files\n          description: \"Move files or directories to a new location in iRODS\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n          call: \"terrain.move-files\"\n          with:\n            sources: \"tools.sources\"\n            dest: \"tools.dest\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-files\n          description: \"Move files or directories to the user's iRODS trash\"\n          hints:\n   \
  \         readOnly: false\n            destructive: true\n            idempotent: false\n          call: \"terrain.delete-files\"\n          with:\n            paths: \"tools.paths\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-metadata\n          description: \"Get iRODS AVU metadata triples for a file or directory\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"terrain.get-file-metadata\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: share-data\n          description: \"Share iRODS data (files/folders) with other CyVerse users\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"terrain.share-data\"\n          with:\n            sharing: \"tools.sharing\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-apps\n          description: \"Browse bioinformatics and data science apps in the Discovery Environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terrain.list-apps\"\n          with:\n            search: \"tools.search\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-analyses\n          description: \"List the user's analysis job history in the Discovery Environment\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terrain.list-analyses\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-analysis\n          description: \"Submit a new bioinformatics analysis job using a Discovery Environment application\"\n          hints:\n            readOnly: false\n            destructive: false\n          call: \"terrain.submit-analysis\"\
  \n          with:\n            name: \"tools.name\"\n            app_id: \"tools.app_id\"\n            system_id: \"tools.system_id\"\n            config: \"tools.config\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-notifications\n          description: \"Get recent notifications about completed analyses and system events\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"terrain.list-notifications\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
