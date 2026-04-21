---
consumed_apis:
- active-directory-users
- active-directory-groups
- active-directory-applications
description: Unified workflow for managing Microsoft Entra ID (Active Directory) identity and access operations including user lifecycle management, group management, and application registration. Used by IT administrators, identity engineers, and security teams to automate identity governance and access management.
layout: capability
name: Microsoft Active Directory Identity Management Operations
operations:
- description: List users
  method: GET
  name: list-users
  path: /v1/users
- description: Create user
  method: POST
  name: create-user
  path: /v1/users
- description: Get user by ID or UPN
  method: GET
  name: get-user
  path: /v1/users/{userId}
- description: Get signed-in user profile
  method: GET
  name: get-me
  path: /v1/me
- description: List groups
  method: GET
  name: list-groups
  path: /v1/groups
- description: Create group
  method: POST
  name: create-group
  path: /v1/groups
- description: Get group
  method: GET
  name: get-group
  path: /v1/groups/{groupId}
- description: List group members
  method: GET
  name: list-group-members
  path: /v1/groups/{groupId}/members
- description: List applications
  method: GET
  name: list-applications
  path: /v1/applications
- description: List service principals
  method: GET
  name: list-service-principals
  path: /v1/servicePrincipals
personas: []
provider_name: Microsoft Active Directory
provider_slug: active-directory
search_terms:
- get group
- security professional monitoring identity risks, conditional access policies, and audit logs
- get details about a specific microsoft entra application registration
- registered and joined device management for compliant device access policies
- get user by id or upn
- periodic access reviews and identity risk remediation
- get application
- enterprise it admin managing user accounts, groups, device policies, and access management
- get me
- list users
- list application registrations in the microsoft entra tenant
- list groups
- group member management
- group management
- Security Analyst
- identity platform engineer managing application registrations, service principals, and oauth2 permission grants
- create group
- list microsoft entra id users with optional filtering by department, job title, or other attributes
- authorization
- list applications
- signed-in user profile
- list group members
- authentication
- list service principals in the microsoft entra tenant
- get signed-in user profile
- Identity Engineer
- list service principals
- zero trust
- group-based access control and app role assignment for resource permissions
- identity management
- get details about a specific microsoft entra user by object id or userprincipalname
- active directory
- get user
- get details about a specific microsoft entra group including type and membership settings
- create, update, and deactivate user accounts throughout the employee/guest lifecycle
- list direct members of a microsoft entra group
- list microsoft entra id groups — security groups and microsoft 365 groups
- service principals
- create user
- individual user operations
- microsoft entra
- create a new user account in microsoft entra id with required profile and password settings
- user management
- individual group operations
- directory services
- IT Administrator
- get the signed-in user's microsoft entra profile
- unified user, group, and application management for microsoft entra id
- conditional access policy automation for zero-trust enforcement
- application registration and service principal lifecycle for zero-trust app governance
- user lifecycle management
- application registrations
slug: identity-management-operations
tags:
- Active Directory
- Identity Management
- Microsoft Entra
- User Management
- Zero Trust
tools:
- description: List Microsoft Entra ID users with optional filtering by department, job title, or other attributes
  hints:
    openWorld: true
    readOnly: true
  name: list-users
- description: Get details about a specific Microsoft Entra user by object ID or userPrincipalName
  hints:
    idempotent: true
    readOnly: true
  name: get-user
- description: Create a new user account in Microsoft Entra ID with required profile and password settings
  hints:
    idempotent: false
    readOnly: false
  name: create-user
- description: Get the signed-in user's Microsoft Entra profile
  hints:
    idempotent: true
    readOnly: true
  name: get-me
- description: List Microsoft Entra ID groups — security groups and Microsoft 365 groups
  hints:
    openWorld: true
    readOnly: true
  name: list-groups
- description: Get details about a specific Microsoft Entra group including type and membership settings
  hints:
    idempotent: true
    readOnly: true
  name: get-group
- description: List direct members of a Microsoft Entra group
  hints:
    openWorld: true
    readOnly: true
  name: list-group-members
- description: List application registrations in the Microsoft Entra tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-applications
- description: Get details about a specific Microsoft Entra application registration
  hints:
    idempotent: true
    readOnly: true
  name: get-application
- description: List service principals in the Microsoft Entra tenant
  hints:
    openWorld: true
    readOnly: true
  name: list-service-principals
---
