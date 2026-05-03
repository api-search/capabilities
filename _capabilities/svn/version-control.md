---
api_specs:
- filename: svn-webdav-openapi.yml
  format: yaml
  label: svn-webdav
  slug: svn-webdav
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/svn/refs/heads/main/openapi/svn-webdav-openapi.yml
categories: []
consumed_apis:
- svn-webdav
description: Unified version control workflow capability for Apache Subversion. Combines repository browsing, file operations, commit lifecycle management, and historical revision access into a single workflow-oriented interface for developers and automation tools.
layout: capability
name: SVN Version Control
operations:
- description: Get repository root listing and metadata
  method: GET
  name: get-repository-root
  path: /v1/repository
- description: Get file content or directory listing at HEAD
  method: GET
  name: get-file
  path: /v1/files/{path}
- description: Upload file content as part of an active commit
  method: PUT
  name: upload-file
  path: /v1/files/{path}
- description: Delete a file or directory in an active commit
  method: DELETE
  name: delete-file
  path: /v1/files/{path}
- description: Create a new commit transaction
  method: POST
  name: create-commit
  path: /v1/commits
- description: Retrieve file content at a specific historical revision
  method: GET
  name: get-file-at-revision
  path: /v1/history/{revision}/files/{path}
personas: []
provider_name: Subversion
provider_slug: svn
search_terms:
- retrieve the content of a file or directory listing from svn
- subversion
- open source
- delete a file or directory in an active commit
- upload file
- svn
- create commit
- file and directory access
- create a new commit transaction
- browse the svn repository root and see available projects
- schedule a file or directory for deletion in an active svn commit
- start a new svn commit transaction to stage file changes
- version control
- browse repository
- get file content or directory listing at head
- get repository root
- retrieve the historical content of a file at a specific svn revision number
- commit transaction lifecycle
- historical file access by revision
- apache
- get file
- retrieve file content at a specific historical revision
- repository root information and metadata
- get repository root listing and metadata
- upload file content as part of an active commit
- webdav
- get file at revision
- source control
- upload a file to an active svn commit transaction
- repository
- delete file
slug: version-control
source_filename: version-control.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SVN Version Control\"\n  description: >-\n    Unified version control workflow capability for Apache Subversion. Combines\n    repository browsing, file operations, commit lifecycle management, and\n    historical revision access into a single workflow-oriented interface for\n    developers and automation tools.\n  tags:\n    - Apache\n    - Repository\n    - Source Control\n    - Subversion\n    - Version Control\n    - Webdav\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SVN_USERNAME: SVN_USERNAME\n      SVN_PASSWORD: SVN_PASSWORD\n\ncapability:\n  consumes:\n    - import: svn-webdav\n      location: ./shared/svn-webdav.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: svn-version-control-api\n      description: \"Unified REST API for Apache Subversion version control operations.\"\n      resources:\n        - path: /v1/repository\n          name:\
  \ repository\n          description: \"Repository root information and metadata\"\n          operations:\n            - method: GET\n              name: get-repository-root\n              description: \"Get repository root listing and metadata\"\n              call: \"svn-webdav.get-repository-root\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/files/{path}\n          name: files\n          description: \"File and directory access\"\n          operations:\n            - method: GET\n              name: get-file\n              description: \"Get file content or directory listing at HEAD\"\n              call: \"svn-webdav.get-file-or-directory\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: upload-file\n              description: \"Upload file content as\
  \ part of an active commit\"\n              call: \"svn-webdav.put-file\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-file\n              description: \"Delete a file or directory in an active commit\"\n              call: \"svn-webdav.delete-file-or-directory\"\n              with:\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/commits\n          name: commits\n          description: \"Commit transaction lifecycle\"\n          operations:\n            - method: POST\n              name: create-commit\n              description: \"Create a new commit transaction\"\n              call: \"svn-webdav.create-commit-transaction\"\n              outputParameters:\n                - type: object\n               \
  \   mapping: \"$.\"\n\n        - path: /v1/history/{revision}/files/{path}\n          name: history\n          description: \"Historical file access by revision\"\n          operations:\n            - method: GET\n              name: get-file-at-revision\n              description: \"Retrieve file content at a specific historical revision\"\n              call: \"svn-webdav.get-revision-versioned-resource\"\n              with:\n                revision: \"rest.revision\"\n                path: \"rest.path\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: svn-version-control-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Subversion version control operations.\"\n      tools:\n        - name: browse-repository\n          description: \"Browse the SVN repository root and see available projects\"\n          hints:\n            readOnly: true\n           \
  \ idempotent: true\n          call: \"svn-webdav.get-repository-root\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-file\n          description: \"Retrieve the content of a file or directory listing from SVN\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"svn-webdav.get-file-or-directory\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: upload-file\n          description: \"Upload a file to an active SVN commit transaction\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"svn-webdav.put-file\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: delete-file\n          description: \"Schedule a file or directory for\
  \ deletion in an active SVN commit\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"svn-webdav.delete-file-or-directory\"\n          with:\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-commit\n          description: \"Start a new SVN commit transaction to stage file changes\"\n          hints:\n            readOnly: false\n            idempotent: false\n          call: \"svn-webdav.create-commit-transaction\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-file-at-revision\n          description: \"Retrieve the historical content of a file at a specific SVN revision number\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"svn-webdav.get-revision-versioned-resource\"\n          with:\n            revision:\
  \ \"tools.revision\"\n            path: \"tools.path\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/svn/refs/heads/main/capabilities/version-control.yaml
tags:
- Apache
- Repository
- Source Control
- Subversion
- Version Control
- Webdav
tools:
- description: Browse the SVN repository root and see available projects
  hints:
    idempotent: true
    readOnly: true
  name: browse-repository
- description: Retrieve the content of a file or directory listing from SVN
  hints:
    idempotent: true
    readOnly: true
  name: get-file
- description: Upload a file to an active SVN commit transaction
  hints:
    idempotent: false
    readOnly: false
  name: upload-file
- description: Schedule a file or directory for deletion in an active SVN commit
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-file
- description: Start a new SVN commit transaction to stage file changes
  hints:
    idempotent: false
    readOnly: false
  name: create-commit
- description: Retrieve the historical content of a file at a specific SVN revision number
  hints:
    idempotent: true
    readOnly: true
  name: get-file-at-revision
---
