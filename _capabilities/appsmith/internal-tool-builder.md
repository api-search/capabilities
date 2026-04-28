---
categories: []
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
- developer productivity
- list internal tools
- connecting databases and apis to power application data
- low-code
- lists all low-code internal tool applications built in appsmith
- creating and managing low-code applications
- list connected datasources
- builds low-code internal tools and workflow applications
- workflow automation
- build and deploy low-code internal tools with appsmith
- lists datasources connected to appsmith for powering internal tools
- developer tools
- appsmith
- internal tools
- lists workspaces available for organizing internal tools
- open source
- manages workspaces and application access for teams
- create internal tool
- list team workspaces
- creates a new internal tool application in appsmith
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
