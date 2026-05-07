---
categories: []
consumed_apis: []
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
- list published components for a team.
- get specific nodes from a file.
- design file access.
- get file nodes
- files
- get image fills
- get component
- list projects for a team.
- get file versions
- list team projects.
- list team components.
- render images from a file.
- get specific nodes from a figma file by ids.
- post comment
- components
- image rendering.
- post a comment on a figma file.
- interfaces
- get team styles
- design
- graphics
- get a figma file document tree.
- collaboration
- component access.
- get file components
- file node access.
- asset export
- get images
- get a figma file.
- team component access.
- get team projects
- figma
- get information about the authenticated user.
- get team components
- list published styles for a team.
- get team component sets
- get download links for images used as fills in a file.
- get me
- list comments on a figma file.
- get file
- get a component by key.
- ui/ux
- design systems
- get project files
- list published component sets for a team.
- get comments
- project file access.
- get a specific component by key.
- list version history of a figma file.
- render and export images from a figma file.
- team project access.
- prototypes
- list components in a figma file.
- prototyping
- list files in a project.
slug: design-system-management
source_filename: design-system-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Figma Design System Management\n  description: Unified workflow for managing design files, components, styles, projects, comments, and asset export. Combines\n    the Figma REST API endpoints into a cohesive design system management experience. Used by design system engineers, developers,\n    and design ops teams.\n  tags:\n  - Figma\n  - Design Systems\n  - Components\n  - Files\n  - Asset Export\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FIGMA_ACCESS_TOKEN: FIGMA_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: figma-rest\n    baseUri: https://api.figma.com\n    description: Figma REST API for design file and team management.\n    authentication:\n      type: bearer\n      token: '{{FIGMA_ACCESS_TOKEN}}'\n    resources:\n    - name: files\n      path: /v1/files/{file_key}\n      description: Access Figma file data.\n      operations:\n      - name: get-file\n    \
  \    method: GET\n        description: Returns the document tree for a given Figma file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        - name: version\n          in: query\n          type: string\n          required: false\n          description: A specific version ID.\n        - name: ids\n          in: query\n          type: string\n          required: false\n          description: Comma-separated list of node IDs.\n        - name: depth\n          in: query\n          type: integer\n          required: false\n          description: Document tree depth.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: file-nodes\n      path: /v1/files/{file_key}/nodes\n      description: Access specific nodes in a file.\n      operations:\n      - name: get-file-nodes\n        method: GET\n\
  \        description: Returns nodes referenced by IDs.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of node IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /v1/images/{file_key}\n      description: Export images from a file.\n      operations:\n      - name: get-images\n        method: GET\n        description: Render images from a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        - name: ids\n          in: query\n          type: string\n          required: true\n          description: Comma-separated\
  \ list of node IDs to render.\n        - name: scale\n          in: query\n          type: integer\n          required: false\n          description: Image scale factor.\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Image format (jpg, png, svg, pdf).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: image-fills\n      path: /v1/files/{file_key}/images\n      description: Get image fill URLs.\n      operations:\n      - name: get-image-fills\n        method: GET\n        description: Returns download links for images in a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: file-versions\n\
  \      path: /v1/files/{file_key}/versions\n      description: Access file version history.\n      operations:\n      - name: get-file-versions\n        method: GET\n        description: List version history of a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /v1/files/{file_key}/comments\n      description: Manage file comments.\n      operations:\n      - name: get-comments\n        method: GET\n        description: List comments on a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n      - name: post-comment\n        method: POST\n        description: Post a comment on a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n    - name: team-components\n      path: /v1/teams/{team_id}/components\n      description: Access team components.\n      operations:\n      - name: get-team-components\n        method: GET\n        description: List published components for a team.\n        inputParameters:\n        - name: team_id\n          in: path\n          type: string\n          required: true\n          description: The team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: file-components\n      path: /v1/files/{file_key}/components\n      description: Access file components.\n      operations:\n      - name: get-file-components\n        method: GET\n        description: List components in a file.\n        inputParameters:\n        - name: file_key\n          in: path\n          type: string\n          required: true\n          description: The file key.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: component-details\n      path: /v1/components/{key}\n      description: Access component details.\n      operations:\n      - name: get-component\n        method: GET\n        description: Get a component by key.\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The component key.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: team-component-sets\n      path: /v1/teams/{team_id}/component_sets\n      description: Access team component sets.\n      operations:\n      - name: get-team-component-sets\n        method: GET\n        description: List published component sets for a team.\n        inputParameters:\n        - name: team_id\n          in: path\n          type: string\n          required: true\n          description: The team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-styles\n      path: /v1/teams/{team_id}/styles\n      description: Access team styles.\n      operations:\n      - name: get-team-styles\n        method: GET\n        description: List published styles for a team.\n        inputParameters:\n        - name: team_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-projects\n      path: /v1/teams/{team_id}/projects\n      description: Access team projects.\n      operations:\n      - name: get-team-projects\n        method: GET\n        description: List projects for a team.\n        inputParameters:\n        - name: team_id\n          in: path\n          type: string\n          required: true\n          description: The team ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: project-files\n      path: /v1/projects/{project_id}/files\n      description: Access project files.\n      operations:\n      - name: get-project-files\n        method: GET\n        description: List files in a project.\n        inputParameters:\n        - name: project_id\n          in: path\n          type: string\n       \
  \   required: true\n          description: The project ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me\n      path: /v1/me\n      description: Current user info.\n      operations:\n      - name: get-me\n        method: GET\n        description: Get the authenticated user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: figma-design-api\n    description: Unified REST API for Figma design system management.\n    resources:\n    - path: /v1/files/{file_key}\n      name: files\n      description: Design file access.\n      operations:\n      - method: GET\n        name: get-file\n        description: Get a Figma file.\n        call: figma-rest.get-file\n        with:\n          file_key: rest.file_key\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /v1/files/{file_key}/nodes\n      name: file-nodes\n      description: File node access.\n      operations:\n      - method: GET\n        name: get-file-nodes\n        description: Get specific nodes from a file.\n        call: figma-rest.get-file-nodes\n        with:\n          file_key: rest.file_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/images/{file_key}\n      name: images\n      description: Image rendering.\n      operations:\n      - method: GET\n        name: get-images\n        description: Render images from a file.\n        call: figma-rest.get-images\n        with:\n          file_key: rest.file_key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/components/{key}\n      name: components\n      description: Component access.\n      operations:\n      - method: GET\n        name: get-component\n        description: Get a component by key.\n      \
  \  call: figma-rest.get-component\n        with:\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{team_id}/components\n      name: team-components\n      description: Team component access.\n      operations:\n      - method: GET\n        name: get-team-components\n        description: List team components.\n        call: figma-rest.get-team-components\n        with:\n          team_id: rest.team_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/teams/{team_id}/projects\n      name: team-projects\n      description: Team project access.\n      operations:\n      - method: GET\n        name: get-team-projects\n        description: List team projects.\n        call: figma-rest.get-team-projects\n        with:\n          team_id: rest.team_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects/{project_id}/files\n      name:\
  \ project-files\n      description: Project file access.\n      operations:\n      - method: GET\n        name: get-project-files\n        description: List files in a project.\n        call: figma-rest.get-project-files\n        with:\n          project_id: rest.project_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: figma-design-mcp\n    transport: http\n    description: MCP server for AI-assisted Figma design system management.\n    tools:\n    - name: get-file\n      description: Get a Figma file document tree.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: figma-rest.get-file\n      with:\n        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-nodes\n      description: Get specific nodes from a Figma file by IDs.\n      hints:\n        readOnly: true\n      call: figma-rest.get-file-nodes\n      with:\n       \
  \ file_key: tools.file_key\n        ids: tools.ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-images\n      description: Render and export images from a Figma file.\n      hints:\n        readOnly: true\n      call: figma-rest.get-images\n      with:\n        file_key: tools.file_key\n        ids: tools.ids\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-image-fills\n      description: Get download links for images used as fills in a file.\n      hints:\n        readOnly: true\n      call: figma-rest.get-image-fills\n      with:\n        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-versions\n      description: List version history of a Figma file.\n      hints:\n        readOnly: true\n      call: figma-rest.get-file-versions\n      with:\n        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: get-comments\n      description: List comments on a Figma file.\n      hints:\n        readOnly: true\n      call: figma-rest.get-comments\n      with:\n        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-comment\n      description: Post a comment on a Figma file.\n      hints:\n        readOnly: false\n      call: figma-rest.post-comment\n      with:\n        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-components\n      description: List published components for a team.\n      hints:\n        readOnly: true\n      call: figma-rest.get-team-components\n      with:\n        team_id: tools.team_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-file-components\n      description: List components in a Figma file.\n      hints:\n        readOnly: true\n      call: figma-rest.get-file-components\n      with:\n\
  \        file_key: tools.file_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-component\n      description: Get a specific component by key.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: figma-rest.get-component\n      with:\n        key: tools.key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-component-sets\n      description: List published component sets for a team.\n      hints:\n        readOnly: true\n      call: figma-rest.get-team-component-sets\n      with:\n        team_id: tools.team_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-styles\n      description: List published styles for a team.\n      hints:\n        readOnly: true\n      call: figma-rest.get-team-styles\n      with:\n        team_id: tools.team_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-team-projects\n      description:\
  \ List projects for a team.\n      hints:\n        readOnly: true\n      call: figma-rest.get-team-projects\n      with:\n        team_id: tools.team_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-project-files\n      description: List files in a project.\n      hints:\n        readOnly: true\n      call: figma-rest.get-project-files\n      with:\n        project_id: tools.project_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-me\n      description: Get information about the authenticated user.\n      hints:\n        readOnly: true\n      call: figma-rest.get-me\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
