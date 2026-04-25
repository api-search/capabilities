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
- low-code
- lists datasources connected to appsmith for powering internal tools
- creates a new internal tool application in appsmith
- build and deploy low-code internal tools with appsmith
- list team workspaces
- developer tools
- connecting databases and apis to power application data
- list connected datasources
- create internal tool
- manages workspaces and application access for teams
- lists all low-code internal tool applications built in appsmith
- workflow automation
- builds low-code internal tools and workflow applications
- creating and managing low-code applications
- list internal tools
- internal tools
- appsmith
- open source
- lists workspaces available for organizing internal tools
- developer productivity
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
