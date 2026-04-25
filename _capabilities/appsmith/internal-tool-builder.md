---
consumed_apis:
- appsmith
description: Workflow capability for building and managing internal tools using the Appsmith low-code platform. Supports developers creating workflow applications with connected datasources and team workspaces.
layout: capability
name: Appsmith Internal Tool Builder
operations: []
personas: []
provider_name: Appsmith
provider_slug: appsmith
search_terms:
- appsmith
- internal tools
- list internal tools
- list team workspaces
- lists datasources connected to appsmith for powering internal tools
- list connected datasources
- connecting databases and apis to power application data
- manages workspaces and application access for teams
- open source
- developer tools
- builds low-code internal tools and workflow applications
- build and deploy low-code internal tools with appsmith
- lists all low-code internal tool applications built in appsmith
- creating and managing low-code applications
- low-code
- workflow automation
- creates a new internal tool application in appsmith
- developer productivity
- create internal tool
- lists workspaces available for organizing internal tools
slug: internal-tool-builder
tags:
- Appsmith
- Low-Code
- Internal Tools
- Developer Productivity
tools:
- description: Lists all low-code internal tool applications built in Appsmith
  hints:
    idempotent: true
    readOnly: true
  name: list-internal-tools
- description: Creates a new internal tool application in Appsmith
  hints:
    destructive: false
    readOnly: false
  name: create-internal-tool
- description: Lists workspaces available for organizing internal tools
  hints:
    idempotent: true
    readOnly: true
  name: list-team-workspaces
- description: Lists datasources connected to Appsmith for powering internal tools
  hints:
    idempotent: true
    readOnly: true
  name: list-connected-datasources
---
