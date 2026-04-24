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
- list internal tools
- lists all low-code internal tool applications built in appsmith
- manages workspaces and application access for teams
- low-code
- builds low-code internal tools and workflow applications
- developer tools
- internal tools
- open source
- developer productivity
- creates a new internal tool application in appsmith
- lists datasources connected to appsmith for powering internal tools
- appsmith
- list connected datasources
- workflow automation
- lists workspaces available for organizing internal tools
- list team workspaces
- creating and managing low-code applications
- connecting databases and apis to power application data
- create internal tool
- build and deploy low-code internal tools with appsmith
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
