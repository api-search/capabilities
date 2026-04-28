---
categories:
- design
- developer-experience
consumed_apis:
- figma-rest
description: In-IDE Figma design context — pull component definitions, file contents, and rendered images so developers can implement against the live design without context-switching to a browser. Exposes a governed MCP-served Figma connector that platform teams can roll out across enterprise developer fleets with security-team-ready operations metadata.
layout: capability
name: Figma MCP Developer Connector
operations:
- description: Get the full document tree and metadata for a Figma file
  method: GET
  name: get-file-contents
  path: /v1/files/{file_key}
- description: List all files in a Figma project for design discovery from the IDE
  method: GET
  name: list-project-files
  path: /v1/projects/{project_id}/files
- description: Get component definitions for a Figma file so developers can see token and component shape
  method: GET
  name: get-component-definitions
  path: /v1/files/{file_key}/components
- description: Render images for specific nodes in a Figma file for in-IDE visual reference
  method: GET
  name: get-node-image-renders
  path: /v1/images/{file_key}
- description: List comments on a Figma file so developers can see designer feedback inline
  method: GET
  name: list-file-comments
  path: /v1/files/{file_key}/comments
- description: Get published styles for a file to mirror design tokens in code
  method: GET
  name: get-file-styles
  path: /v1/files/{file_key}/styles
personas:
- Developer
provider_name: Figma
provider_slug: figma
search_terms:
- get figma file contents from the ide
- list files in a figma project
- pull component definitions for in-ide implementation
- render images for specific figma nodes
- list comments on a design file
- in-ide figma design context
- mcp server for figma inside vs code and copilot
- design-to-code workflow
- ford-style governed figma connector
- enterprise design system access
- read figma published styles
- design tokens to code
- copilot figma integration
- security-reviewed figma mcp
- developer experience
- Developer
- node renders
- component shape
- live design context
- design system in the ide
- figma rest api
- mcp connector for design
slug: mcp-developer-connector
tags:
- Figma
- MCP
- Design
- Developer Experience
- IDE Integration
tools:
- description: Get the full document tree and metadata for a Figma file so the IDE can ground code on the live design
  hints:
    openWorld: false
    readOnly: true
  name: get-file-contents
- description: List all files in a Figma project to help developers discover the right design source
  hints:
    openWorld: false
    readOnly: true
  name: list-project-files
- description: Get component definitions for a Figma file to expose component shape and tokens to the IDE
  hints:
    openWorld: false
    readOnly: true
  name: get-component-definitions
- description: Render images for specific nodes in a Figma file for in-IDE visual reference
  hints:
    openWorld: false
    readOnly: true
  name: get-node-image-renders
- description: List comments on a Figma file so developers can see designer feedback inline
  hints:
    openWorld: false
    readOnly: true
  name: list-file-comments
- description: Get the published styles for a Figma file so developers can mirror design tokens in code
  hints:
    openWorld: false
    readOnly: true
  name: get-file-styles
---
