---
categories: []
consumed_apis:
- figma-rest
description: Unified workflow for managing design files, components, styles, projects, comments, and asset export. Combines the Figma REST API endpoints into a cohesive design system management experience. Used by design system engineers, developers, and design ops teams.
layout: capability
name: Figma Design System Management
operations:
- description: Get a Figma file.
  method: GET
  name: get-file
  path: /v1/files/{file_key}
- description: Get specific nodes from a file.
  method: GET
  name: get-file-nodes
  path: /v1/files/{file_key}/nodes
- description: Render images from a file.
  method: GET
  name: get-images
  path: /v1/images/{file_key}
- description: Get a component by key.
  method: GET
  name: get-component
  path: /v1/components/{key}
- description: List team components.
  method: GET
  name: get-team-components
  path: /v1/teams/{team_id}/components
- description: List team projects.
  method: GET
  name: get-team-projects
  path: /v1/teams/{team_id}/projects
- description: List files in a project.
  method: GET
  name: get-project-files
  path: /v1/projects/{project_id}/files
personas: []
provider_name: Figma
provider_slug: figma
search_terms:
- get file nodes
- render images from a file.
- list published component sets for a team.
- ui/ux
- design systems
- graphics
- get team component sets
- get team styles
- get team projects
- image rendering.
- get team components
- get information about the authenticated user.
- list comments on a figma file.
- get component
- get me
- interfaces
- file node access.
- get images
- team project access.
- get specific nodes from a figma file by ids.
- render and export images from a figma file.
- get a specific component by key.
- team component access.
- project file access.
- get a component by key.
- list team projects.
- get specific nodes from a file.
- prototypes
- post comment
- prototyping
- list components in a figma file.
- get project files
- design file access.
- list published components for a team.
- collaboration
- list files in a project.
- list projects for a team.
- files
- get download links for images used as fills in a file.
- get file
- list published styles for a team.
- get a figma file document tree.
- design
- post a comment on a figma file.
- get a figma file.
- list team components.
- components
- get image fills
- get comments
- figma
- get file versions
- get file components
- list version history of a figma file.
- component access.
- asset export
slug: design-system-management
source_filename: design-system-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Figma Design System Management\"\n  description: \"Unified workflow for managing design files, components, styles, projects, comments, and asset export. Combines the Figma REST API endpoints into a cohesive design system management experience. Used by design system engineers, developers, and design ops teams.\"\n  tags:\n    - Figma\n    - Design Systems\n    - Components\n    - Files\n    - Asset Export\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FIGMA_ACCESS_TOKEN: FIGMA_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: figma-rest\n      location: ./shared/rest-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: figma-design-api\n      description: \"Unified REST API for Figma design system management.\"\n      resources:\n        - path: /v1/files/{file_key}\n          name: files\n          description: \"Design file access.\"\n      \
  \    operations:\n            - method: GET\n              name: get-file\n              description: \"Get a Figma file.\"\n              call: \"figma-rest.get-file\"\n              with:\n                file_key: \"rest.file_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/files/{file_key}/nodes\n          name: file-nodes\n          description: \"File node access.\"\n          operations:\n            - method: GET\n              name: get-file-nodes\n              description: \"Get specific nodes from a file.\"\n              call: \"figma-rest.get-file-nodes\"\n              with:\n                file_key: \"rest.file_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/images/{file_key}\n          name: images\n          description: \"Image rendering.\"\n          operations:\n            - method: GET\n              name: get-images\n\
  \              description: \"Render images from a file.\"\n              call: \"figma-rest.get-images\"\n              with:\n                file_key: \"rest.file_key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/components/{key}\n          name: components\n          description: \"Component access.\"\n          operations:\n            - method: GET\n              name: get-component\n              description: \"Get a component by key.\"\n              call: \"figma-rest.get-component\"\n              with:\n                key: \"rest.key\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams/{team_id}/components\n          name: team-components\n          description: \"Team component access.\"\n          operations:\n            - method: GET\n              name: get-team-components\n              description: \"List team components.\"\
  \n              call: \"figma-rest.get-team-components\"\n              with:\n                team_id: \"rest.team_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/teams/{team_id}/projects\n          name: team-projects\n          description: \"Team project access.\"\n          operations:\n            - method: GET\n              name: get-team-projects\n              description: \"List team projects.\"\n              call: \"figma-rest.get-team-projects\"\n              with:\n                team_id: \"rest.team_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/projects/{project_id}/files\n          name: project-files\n          description: \"Project file access.\"\n          operations:\n            - method: GET\n              name: get-project-files\n              description: \"List files in a project.\"\n              call:\
  \ \"figma-rest.get-project-files\"\n              with:\n                project_id: \"rest.project_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: figma-design-mcp\n      transport: http\n      description: \"MCP server for AI-assisted Figma design system management.\"\n      tools:\n        - name: get-file\n          description: \"Get a Figma file document tree.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"figma-rest.get-file\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-nodes\n          description: \"Get specific nodes from a Figma file by IDs.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-file-nodes\"\n          with:\n            file_key: \"tools.file_key\"\
  \n            ids: \"tools.ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-images\n          description: \"Render and export images from a Figma file.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-images\"\n          with:\n            file_key: \"tools.file_key\"\n            ids: \"tools.ids\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-image-fills\n          description: \"Get download links for images used as fills in a file.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-image-fills\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-versions\n          description: \"List version history of a Figma file.\"\n          hints:\n            readOnly: true\n     \
  \     call: \"figma-rest.get-file-versions\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-comments\n          description: \"List comments on a Figma file.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-comments\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: post-comment\n          description: \"Post a comment on a Figma file.\"\n          hints:\n            readOnly: false\n          call: \"figma-rest.post-comment\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-components\n          description: \"List published components for a team.\"\n          hints:\n            readOnly: true\n \
  \         call: \"figma-rest.get-team-components\"\n          with:\n            team_id: \"tools.team_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-file-components\n          description: \"List components in a Figma file.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-file-components\"\n          with:\n            file_key: \"tools.file_key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-component\n          description: \"Get a specific component by key.\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"figma-rest.get-component\"\n          with:\n            key: \"tools.key\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-component-sets\n          description: \"List published component sets for a team.\"\
  \n          hints:\n            readOnly: true\n          call: \"figma-rest.get-team-component-sets\"\n          with:\n            team_id: \"tools.team_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-styles\n          description: \"List published styles for a team.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-team-styles\"\n          with:\n            team_id: \"tools.team_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-team-projects\n          description: \"List projects for a team.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-team-projects\"\n          with:\n            team_id: \"tools.team_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-project-files\n          description: \"List files in a project.\"\n\
  \          hints:\n            readOnly: true\n          call: \"figma-rest.get-project-files\"\n          with:\n            project_id: \"tools.project_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-me\n          description: \"Get information about the authenticated user.\"\n          hints:\n            readOnly: true\n          call: \"figma-rest.get-me\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/figma/refs/heads/main/capabilities/design-system-management.yaml
tags:
- Figma
- Design Systems
- Components
- Files
- Asset Export
tools:
- description: Get a Figma file document tree.
  hints:
    openWorld: true
    readOnly: true
  name: get-file
- description: Get specific nodes from a Figma file by IDs.
  hints:
    readOnly: true
  name: get-file-nodes
- description: Render and export images from a Figma file.
  hints:
    readOnly: true
  name: get-images
- description: Get download links for images used as fills in a file.
  hints:
    readOnly: true
  name: get-image-fills
- description: List version history of a Figma file.
  hints:
    readOnly: true
  name: get-file-versions
- description: List comments on a Figma file.
  hints:
    readOnly: true
  name: get-comments
- description: Post a comment on a Figma file.
  hints:
    readOnly: false
  name: post-comment
- description: List published components for a team.
  hints:
    readOnly: true
  name: get-team-components
- description: List components in a Figma file.
  hints:
    readOnly: true
  name: get-file-components
- description: Get a specific component by key.
  hints:
    idempotent: true
    readOnly: true
  name: get-component
- description: List published component sets for a team.
  hints:
    readOnly: true
  name: get-team-component-sets
- description: List published styles for a team.
  hints:
    readOnly: true
  name: get-team-styles
- description: List projects for a team.
  hints:
    readOnly: true
  name: get-team-projects
- description: List files in a project.
  hints:
    readOnly: true
  name: get-project-files
- description: Get information about the authenticated user.
  hints:
    readOnly: true
  name: get-me
---
