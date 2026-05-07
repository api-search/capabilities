---
categories: []
consumed_apis: []
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
- crossplane
- list all organizations
- create a new organization
- developer experience
- list teams in organization
- create organization
- list robot accounts
- list managed crossplane control planes in an organization
- create team
- robot account management for ci/cd automation
- individual control plane operations
- create robot
- create control plane
- create a new upbound organization
- team management
- managed control plane lifecycle
- list robots
- control planes
- package repository management
- list teams
- get control plane
- list all upbound organizations the user belongs to
- deprovision and delete a managed control plane
- create a package repository
- create a new crossplane package repository
- get details for a specific upbound organization
- create a new managed control plane
- get organization details
- create repository
- list crossplane package repositories in an organization
- provision a new managed crossplane control plane
- list organizations
- internal developer platform
- individual organization
- cloud infrastructure
- list control planes
- organization management
- upbound
- get status and configuration of a managed control plane
- list teams in an upbound organization
- delete control plane
- list package repositories
- create a robot account for ci/cd pipeline access
- create a robot account
- list control planes in organization
- list robot accounts for ci/cd automation
- get control plane status and details
- delete a managed control plane
- create a new team
- delete organization
- get organization
- list repositories
- delete an organization
- platform engineering
slug: platform-engineering
source_filename: platform-engineering.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Upbound Platform Engineering\n  description: Workflow capability for Upbound platform engineering, composing organization management, control plane lifecycle,\n    package repositories, team access, and robot account automation into a unified internal developer platform workflow. Designed\n    for platform engineers and DevOps teams managing cloud infrastructure through Crossplane-based control planes.\n  tags:\n  - Upbound\n  - Crossplane\n  - Platform Engineering\n  - Internal Developer Platform\n  - Cloud Infrastructure\n  - Control Planes\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPBOUND_TOKEN: UPBOUND_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: upbound\n    baseUri: https://api.upbound.io/v1\n    description: Upbound Cloud REST API\n    authentication:\n      type: bearer\n      token: '{{UPBOUND_TOKEN}}'\n    resources:\n    - name: organizations\n      path: /organizations\n\
  \      description: Organization management\n      operations:\n      - name: list-organizations\n        method: GET\n        description: List all organizations the authenticated user belongs to\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-organization\n        method: POST\n        description: Create a new organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            displayName: '{{tools.displayName}}'\n            description: '{{tools.description}}'\n    - name: organization\n      path: /organizations/{orgName}\n      description: Individual organization operations\n      operations:\n      - name: get-organization\n        method: GET\n        description: Get organization details\n        inputParameters:\n\
  \        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-organization\n        method: DELETE\n        description: Delete an organization\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: control-planes\n      path: /organizations/{orgName}/controlplanes\n      description: Managed control plane management\n      operations:\n      - name: list-control-planes\n        method: GET\n        description: List managed control planes in an organization\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        - name: page\n    \
  \      in: query\n          type: integer\n          required: false\n        - name: size\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-control-plane\n        method: POST\n        description: Create a new managed control plane\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            configuration: '{{tools.configuration}}'\n            region: '{{tools.region}}'\n            description: '{{tools.description}}'\n    - name: control-plane\n      path: /organizations/{orgName}/controlplanes/{cpName}\n      description: Individual\
  \ control plane operations\n      operations:\n      - name: get-control-plane\n        method: GET\n        description: Get control plane details and status\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        - name: cpName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-control-plane\n        method: DELETE\n        description: Delete a managed control plane\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        - name: cpName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: repositories\n      path: /organizations/{orgName}/repositories\n\
  \      description: Package repository management\n      operations:\n      - name: list-repositories\n        method: GET\n        description: List package repositories in an organization\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-repository\n        method: POST\n        description: Create a new package repository\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            public: '{{tools.public}}'\n    - name: robots\n   \
  \   path: /organizations/{orgName}/robots\n      description: Robot account management\n      operations:\n      - name: list-robots\n        method: GET\n        description: List robot accounts in an organization\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-robot\n        method: POST\n        description: Create a robot account for CI/CD\n        inputParameters:\n        - name: orgName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n  exposes:\n  - type: rest\n    port: 8080\n\
  \    namespace: upbound-platform-api\n    description: Unified REST API for Upbound platform engineering workflows.\n    resources:\n    - path: /v1/organizations\n      name: organizations\n      description: Organization management\n      operations:\n      - method: GET\n        name: list-organizations\n        description: List all organizations\n        call: upbound.list-organizations\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-organization\n        description: Create a new organization\n        call: upbound.create-organization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}\n      name: organization\n      description: Individual organization\n      operations:\n      - method: GET\n        name: get-organization\n        description: Get organization details\n        call: upbound.get-organization\n        with:\n          orgName: rest.orgName\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-organization\n        description: Delete an organization\n        call: upbound.delete-organization\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}/control-planes\n      name: control-planes\n      description: Managed control plane lifecycle\n      operations:\n      - method: GET\n        name: list-control-planes\n        description: List control planes in organization\n        call: upbound.list-control-planes\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-control-plane\n        description: Create a new managed control plane\n        call: upbound.create-control-plane\n        with:\n          orgName: rest.orgName\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}/control-planes/{cpName}\n      name: control-plane\n      description: Individual control plane operations\n      operations:\n      - method: GET\n        name: get-control-plane\n        description: Get control plane status and details\n        call: upbound.get-control-plane\n        with:\n          orgName: rest.orgName\n          cpName: rest.cpName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-control-plane\n        description: Delete a managed control plane\n        call: upbound.delete-control-plane\n        with:\n          orgName: rest.orgName\n          cpName: rest.cpName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}/repositories\n      name: repositories\n      description: Package repository management\n      operations:\n      - method: GET\n\
  \        name: list-repositories\n        description: List package repositories\n        call: upbound.list-repositories\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-repository\n        description: Create a package repository\n        call: upbound.create-repository\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}/teams\n      name: teams\n      description: Team management\n      operations:\n      - method: GET\n        name: list-teams\n        description: List teams in organization\n        call: upbound.list-teams\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-team\n        description: Create a new team\n        call: upbound.create-team\n\
  \        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/organizations/{orgName}/robots\n      name: robots\n      description: Robot account management for CI/CD automation\n      operations:\n      - method: GET\n        name: list-robots\n        description: List robot accounts\n        call: upbound.list-robots\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-robot\n        description: Create a robot account\n        call: upbound.create-robot\n        with:\n          orgName: rest.orgName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: upbound-platform-mcp\n    transport: http\n    description: MCP server for AI-assisted Upbound platform engineering workflows.\n    tools:\n    - name: list-organizations\n     \
  \ description: List all Upbound organizations the user belongs to\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.list-organizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-organization\n      description: Get details for a specific Upbound organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.get-organization\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-organization\n      description: Create a new Upbound organization\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upbound.create-organization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-control-planes\n      description: List managed Crossplane control planes in an organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ upbound.list-control-planes\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-control-plane\n      description: Get status and configuration of a managed control plane\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.get-control-plane\n      with:\n        orgName: tools.orgName\n        cpName: tools.cpName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-control-plane\n      description: Provision a new managed Crossplane control plane\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upbound.create-control-plane\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-control-plane\n      description: Deprovision and delete a managed control plane\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent:\
  \ true\n      call: upbound.delete-control-plane\n      with:\n        orgName: tools.orgName\n        cpName: tools.cpName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-repositories\n      description: List Crossplane package repositories in an organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.list-repositories\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-repository\n      description: Create a new Crossplane package repository\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upbound.create-repository\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-teams\n      description: List teams in an Upbound organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.list-teams\n\
  \      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-robots\n      description: List robot accounts for CI/CD automation\n      hints:\n        readOnly: true\n        openWorld: false\n      call: upbound.list-robots\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-robot\n      description: Create a robot account for CI/CD pipeline access\n      hints:\n        readOnly: false\n        openWorld: false\n      call: upbound.create-robot\n      with:\n        orgName: tools.orgName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
