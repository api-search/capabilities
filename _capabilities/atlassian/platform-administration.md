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
- policy management
- list audit events
- list organization domains
- list groups in an organization
- administration
- list organization users
- list domains
- list organization policies
- list organization audit events
- get organization
- list users
- list groups
- user management
- group management
- collaboration
- platform
- get organization details
- list organizations
- organization management
- identity
- list organization groups
- productivity
- software development
- list users in an organization
- list all atlassian organizations
- atlassian
- list atlassian organizations
- list policies
- domain management
- audit events
- list events
- list domains in an organization
- code
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
