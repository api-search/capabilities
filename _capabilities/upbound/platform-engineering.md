---
api_specs:
- filename: upbound-openapi.yml
  format: yaml
  label: upbound
  slug: upbound
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/upbound/refs/heads/main/openapi/upbound-openapi.yml
categories: []
consumed_apis:
- upbound
description: Workflow capability for Upbound platform engineering, composing organization management, control plane lifecycle, package repositories, team access, and robot account automation into a unified internal developer platform workflow. Designed for platform engineers and DevOps teams managing cloud infrastructure through Crossplane-based control planes.
layout: capability
name: Upbound Platform Engineering
operations:
- description: List all organizations
  method: GET
  name: list-organizations
  path: /v1/organizations
- description: Create a new organization
  method: POST
  name: create-organization
  path: /v1/organizations
- description: Get organization details
  method: GET
  name: get-organization
  path: /v1/organizations/{orgName}
- description: Delete an organization
  method: DELETE
  name: delete-organization
  path: /v1/organizations/{orgName}
- description: List control planes in organization
  method: GET
  name: list-control-planes
  path: /v1/organizations/{orgName}/control-planes
- description: Create a new managed control plane
  method: POST
  name: create-control-plane
  path: /v1/organizations/{orgName}/control-planes
- description: Get control plane status and details
  method: GET
  name: get-control-plane
  path: /v1/organizations/{orgName}/control-planes/{cpName}
- description: Delete a managed control plane
  method: DELETE
  name: delete-control-plane
  path: /v1/organizations/{orgName}/control-planes/{cpName}
- description: List package repositories
  method: GET
  name: list-repositories
  path: /v1/organizations/{orgName}/repositories
- description: Create a package repository
  method: POST
  name: create-repository
  path: /v1/organizations/{orgName}/repositories
- description: List teams in organization
  method: GET
  name: list-teams
  path: /v1/organizations/{orgName}/teams
- description: Create a new team
  method: POST
  name: create-team
  path: /v1/organizations/{orgName}/teams
- description: List robot accounts
  method: GET
  name: list-robots
  path: /v1/organizations/{orgName}/robots
- description: Create a robot account
  method: POST
  name: create-robot
  path: /v1/organizations/{orgName}/robots
personas: []
provider_name: Upbound
provider_slug: upbound
search_terms:
- create team
- list organizations
- list teams in organization
- cloud infrastructure
- individual control plane operations
- list all upbound organizations the user belongs to
- get details for a specific upbound organization
- package repository management
- create robot
- get control plane status and details
- list control planes in organization
- get status and configuration of a managed control plane
- organization management
- delete organization
- crossplane
- delete control plane
- get control plane
- create a new crossplane package repository
- create repository
- list robot accounts
- create control plane
- create a new upbound organization
- platform engineering
- list crossplane package repositories in an organization
- delete a managed control plane
- create a robot account for ci/cd pipeline access
- create a new managed control plane
- list robot accounts for ci/cd automation
- create a robot account
- list managed crossplane control planes in an organization
- upbound
- create a new organization
- provision a new managed crossplane control plane
- individual organization
- create organization
- list repositories
- list robots
- create a package repository
- list teams in an upbound organization
- create a new team
- delete an organization
- robot account management for ci/cd automation
- control planes
- get organization details
- list teams
- developer experience
- team management
- list all organizations
- managed control plane lifecycle
- get organization
- list control planes
- list package repositories
- deprovision and delete a managed control plane
- internal developer platform
slug: platform-engineering
source_filename: platform-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Upbound Platform Engineering\"\n  description: >-\n    Workflow capability for Upbound platform engineering, composing organization\n    management, control plane lifecycle, package repositories, team access, and\n    robot account automation into a unified internal developer platform workflow.\n    Designed for platform engineers and DevOps teams managing cloud infrastructure\n    through Crossplane-based control planes.\n  tags:\n    - Upbound\n    - Crossplane\n    - Platform Engineering\n    - Internal Developer Platform\n    - Cloud Infrastructure\n    - Control Planes\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      UPBOUND_TOKEN: UPBOUND_TOKEN\n\ncapability:\n  consumes:\n    - import: upbound\n      location: ./shared/upbound.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: upbound-platform-api\n      description: \"Unified REST API for Upbound\
  \ platform engineering workflows.\"\n      resources:\n        - path: /v1/organizations\n          name: organizations\n          description: \"Organization management\"\n          operations:\n            - method: GET\n              name: list-organizations\n              description: \"List all organizations\"\n              call: \"upbound.list-organizations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-organization\n              description: \"Create a new organization\"\n              call: \"upbound.create-organization\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}\n          name: organization\n          description: \"Individual organization\"\n          operations:\n            - method: GET\n              name: get-organization\n              description: \"Get\
  \ organization details\"\n              call: \"upbound.get-organization\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-organization\n              description: \"Delete an organization\"\n              call: \"upbound.delete-organization\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}/control-planes\n          name: control-planes\n          description: \"Managed control plane lifecycle\"\n          operations:\n            - method: GET\n              name: list-control-planes\n              description: \"List control planes in organization\"\n              call: \"upbound.list-control-planes\"\n              with:\n                orgName: \"rest.orgName\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-control-plane\n              description: \"Create a new managed control plane\"\n              call: \"upbound.create-control-plane\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}/control-planes/{cpName}\n          name: control-plane\n          description: \"Individual control plane operations\"\n          operations:\n            - method: GET\n              name: get-control-plane\n              description: \"Get control plane status and details\"\n              call: \"upbound.get-control-plane\"\n              with:\n                orgName: \"rest.orgName\"\n                cpName: \"rest.cpName\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-control-plane\n              description: \"Delete a managed control plane\"\n              call: \"upbound.delete-control-plane\"\n              with:\n                orgName: \"rest.orgName\"\n                cpName: \"rest.cpName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}/repositories\n          name: repositories\n          description: \"Package repository management\"\n          operations:\n            - method: GET\n              name: list-repositories\n              description: \"List package repositories\"\n              call: \"upbound.list-repositories\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-repository\n\
  \              description: \"Create a package repository\"\n              call: \"upbound.create-repository\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}/teams\n          name: teams\n          description: \"Team management\"\n          operations:\n            - method: GET\n              name: list-teams\n              description: \"List teams in organization\"\n              call: \"upbound.list-teams\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-team\n              description: \"Create a new team\"\n              call: \"upbound.create-team\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n \
  \               - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/organizations/{orgName}/robots\n          name: robots\n          description: \"Robot account management for CI/CD automation\"\n          operations:\n            - method: GET\n              name: list-robots\n              description: \"List robot accounts\"\n              call: \"upbound.list-robots\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-robot\n              description: \"Create a robot account\"\n              call: \"upbound.create-robot\"\n              with:\n                orgName: \"rest.orgName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: upbound-platform-mcp\n      transport: http\n      description:\
  \ \"MCP server for AI-assisted Upbound platform engineering workflows.\"\n      tools:\n        - name: list-organizations\n          description: \"List all Upbound organizations the user belongs to\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.list-organizations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-organization\n          description: \"Get details for a specific Upbound organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.get-organization\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-organization\n          description: \"Create a new Upbound organization\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upbound.create-organization\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-control-planes\n          description: \"List managed Crossplane control planes in an organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.list-control-planes\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-control-plane\n          description: \"Get status and configuration of a managed control plane\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.get-control-plane\"\n          with:\n            orgName: \"tools.orgName\"\n            cpName: \"tools.cpName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-control-plane\n          description: \"Provision a new managed Crossplane\
  \ control plane\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upbound.create-control-plane\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-control-plane\n          description: \"Deprovision and delete a managed control plane\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n          call: \"upbound.delete-control-plane\"\n          with:\n            orgName: \"tools.orgName\"\n            cpName: \"tools.cpName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-repositories\n          description: \"List Crossplane package repositories in an organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.list-repositories\"\n          with:\n\
  \            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-repository\n          description: \"Create a new Crossplane package repository\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upbound.create-repository\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-teams\n          description: \"List teams in an Upbound organization\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"upbound.list-teams\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-robots\n          description: \"List robot accounts for CI/CD automation\"\n          hints:\n            readOnly: true\n\
  \            openWorld: false\n          call: \"upbound.list-robots\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-robot\n          description: \"Create a robot account for CI/CD pipeline access\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"upbound.create-robot\"\n          with:\n            orgName: \"tools.orgName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/upbound/refs/heads/main/capabilities/platform-engineering.yaml
tags:
- Upbound
- Crossplane
- Platform Engineering
- Internal Developer Platform
- Cloud Infrastructure
- Control Planes
tools:
- description: List all Upbound organizations the user belongs to
  hints:
    openWorld: false
    readOnly: true
  name: list-organizations
- description: Get details for a specific Upbound organization
  hints:
    openWorld: false
    readOnly: true
  name: get-organization
- description: Create a new Upbound organization
  hints:
    openWorld: false
    readOnly: false
  name: create-organization
- description: List managed Crossplane control planes in an organization
  hints:
    openWorld: false
    readOnly: true
  name: list-control-planes
- description: Get status and configuration of a managed control plane
  hints:
    openWorld: false
    readOnly: true
  name: get-control-plane
- description: Provision a new managed Crossplane control plane
  hints:
    openWorld: false
    readOnly: false
  name: create-control-plane
- description: Deprovision and delete a managed control plane
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-control-plane
- description: List Crossplane package repositories in an organization
  hints:
    openWorld: false
    readOnly: true
  name: list-repositories
- description: Create a new Crossplane package repository
  hints:
    openWorld: false
    readOnly: false
  name: create-repository
- description: List teams in an Upbound organization
  hints:
    openWorld: false
    readOnly: true
  name: list-teams
- description: List robot accounts for CI/CD automation
  hints:
    openWorld: false
    readOnly: true
  name: list-robots
- description: Create a robot account for CI/CD pipeline access
  hints:
    openWorld: false
    readOnly: false
  name: create-robot
---
