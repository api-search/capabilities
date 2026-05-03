---
categories: []
consumed_apis: []
description: A workflow capability for an Identity Administrator onboarding new organizations, projects, applications, and human users into Zitadel. Combines Zitadel Management operations to automate provisioning of tenant-isolated identity infrastructure.
layout: capability
name: Identity Onboarding
operations: []
personas: []
provider_name: Zitadel
provider_slug: zitadel
search_terms:
- operates zitadel and provisions identity resources.
- oauth 2.0
- identity management
- oidc
- authentication
- provision organizations, projects, applications, and users.
- integrates applications with zitadel for authentication.
- open source
- authorization
- configures policies, mfa, and audit controls.
slug: identity-onboarding
source_filename: identity-onboarding.yaml
source_heading: Capability Spec
source_yaml: "apiVersion: naftiko/v1\nkind: WorkflowCapability\nmetadata:\n  name: identity-onboarding\n  provider: zitadel\ninfo:\n  title: Identity Onboarding\n  description: >-\n    A workflow capability for an Identity Administrator onboarding new\n    organizations, projects, applications, and human users into Zitadel.\n    Combines Zitadel Management operations to automate provisioning of\n    tenant-isolated identity infrastructure.\n  persona: Identity Administrator\ncombines:\n  - api: zitadel-management-api\n    capability: capabilities/shared/zitadel-management-api.yaml\nmcp:\n  tools:\n    - name: create-organization\n      description: Create a new Zitadel organization (tenant).\n      operationId: createOrg\n    - name: create-project\n      description: Create a new project under an organization.\n      operationId: createProject\n    - name: create-oidc-application\n      description: Register a new OIDC application under a project.\n      operationId: createOidcApp\n   \
  \ - name: create-api-application\n      description: Register a new API application under a project.\n      operationId: createApiApp\n    - name: create-human-user\n      description: Onboard a new human end-user into the organization.\n      operationId: createHumanUser\n    - name: create-machine-user\n      description: Onboard a new machine user (service account).\n      operationId: createMachineUser\n    - name: list-users\n      description: Search for users in the organization.\n      operationId: listUsers\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zitadel/refs/heads/main/capabilities/identity-onboarding.yaml
tags: []
tools: []
---
