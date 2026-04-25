---
consumed_apis:
- atlassian-admin
description: Platform administration workflow combining Admin Organizations, User Management, User Provisioning, and Jira Configuration APIs for IT administrators to manage users, groups, organizations, and platform settings.
layout: capability
name: Atlassian Platform Administration
operations:
- description: List Atlassian organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: List organization users
  method: GET
  name: list-users
  path: /v1/users
- description: List organization groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: List organization domains
  method: GET
  name: list-domains
  path: /v1/domains
- description: List organization policies
  method: GET
  name: list-policies
  path: /v1/policies
- description: List audit events
  method: GET
  name: list-events
  path: /v1/events
personas: []
provider_name: Atlassian
provider_slug: atlassian
search_terms:
- software development
- list organization policies
- list organization domains
- list domains
- organization management
- list organization audit events
- platform
- administration
- list audit events
- get organization
- list groups
- identity
- productivity
- code
- collaboration
- list organizations
- user management
- list users
- atlassian
- group management
- list organization users
- list groups in an organization
- list atlassian organizations
- list policies
- list events
- policy management
- list organization groups
- domain management
- list all atlassian organizations
- list users in an organization
- list domains in an organization
- get organization details
- audit events
slug: platform-administration
tags:
- Administration
- Atlassian
- Identity
- Platform
tools:
- description: List all Atlassian organizations
  hints:
    openWorld: true
    readOnly: true
  name: list-organizations
- description: Get organization details
  hints:
    readOnly: true
  name: get-organization
- description: List users in an organization
  hints:
    readOnly: true
  name: list-users
- description: List groups in an organization
  hints:
    readOnly: true
  name: list-groups
- description: List domains in an organization
  hints:
    readOnly: true
  name: list-domains
- description: List organization policies
  hints:
    readOnly: true
  name: list-policies
- description: List organization audit events
  hints:
    readOnly: true
  name: list-events
---
