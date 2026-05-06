---
categories: []
consumed_apis: []
description: Identity and access management workflow for security engineers to manage Gravitee AM security domains, OAuth2/OIDC applications, users, roles, identity providers, and authentication flows.
layout: capability
name: Gravitee Access Management
operations:
- description: List all security domains.
  method: GET
  name: list-domains
  path: /v1/domains
- description: Create a new security domain.
  method: POST
  name: create-domain
  path: /v1/domains
- description: Get a security domain by ID.
  method: GET
  name: get-domain
  path: /v1/domains/{domainId}
- description: Delete a security domain.
  method: DELETE
  name: delete-domain
  path: /v1/domains/{domainId}
- description: List OAuth2/OIDC applications within a domain.
  method: GET
  name: list-domain-applications
  path: /v1/domains/{domainId}/applications
- description: List users within a security domain.
  method: GET
  name: list-domain-users
  path: /v1/domains/{domainId}/users
- description: List roles within a security domain.
  method: GET
  name: list-domain-roles
  path: /v1/domains/{domainId}/roles
- description: List identity providers within a security domain.
  method: GET
  name: list-identity-providers
  path: /v1/domains/{domainId}/identities
- description: List authentication and authorization flows within a domain.
  method: GET
  name: list-domain-flows
  path: /v1/domains/{domainId}/flows
personas: []
provider_name: Gravitee
provider_slug: gravitee
search_terms:
- gravitee
- get a security domain by id.
- list roles within a security domain.
- delete domain
- list identity providers
- identity
- flows within a domain.
- oauth2
- list authentication and authorization flows within a domain.
- update domain
- list domain applications
- a single security domain.
- get a gravitee am security domain by id.
- create a new gravitee am security domain.
- graphql
- applications within a domain.
- create domain
- create a new security domain.
- get domain
- users within a domain.
- list identity providers within a security domain.
- list domain roles
- list domain flows
- list all gravitee am security domains within an environment.
- open source
- update a gravitee am security domain.
- create a new oauth2/oidc application within a domain.
- list all security domains.
- identity providers within a domain.
- delete a gravitee am security domain and its resources.
- create domain application
- create a user within a security domain.
- api gateway
- api management
- access management
- roles within a domain.
- list domain users
- list domains
- security domains.
- list oauth2/oidc applications within a domain.
- delete a security domain.
- list users within a security domain.
- create domain user
slug: access-management
source_filename: access-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Gravitee Access Management\n  description: Identity and access management workflow for security engineers to manage Gravitee AM security domains, OAuth2/OIDC\n    applications, users, roles, identity providers, and authentication flows.\n  tags:\n  - Gravitee\n  - Identity\n  - Access Management\n  - OAuth2\n  created: '2026-05-04'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    GRAVITEE_AM_URL: GRAVITEE_AM_URL\n    GRAVITEE_AM_TOKEN: GRAVITEE_AM_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: gravitee-am\n    baseUri: '{GRAVITEE_AM_URL}'\n    description: Gravitee Access Management administration API.\n    authentication:\n      type: bearer\n      value: '{{GRAVITEE_AM_TOKEN}}'\n      placement: header\n    resources:\n    - name: domains\n      path: /organizations/{organizationId}/environments/{environmentId}/domains\n      description: Security domain management.\n      operations:\n      - name:\
  \ list-domains\n        method: GET\n        description: List all security domains within an environment.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-domain\n        method: POST\n        description: Create a new security domain.\n        inputParameters:\n        - name: organizationId\n          in:\
  \ path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n            path: '{{tools.path}}'\n      - name: get-domain\n        method: GET\n        description: Get a security domain by ID.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n\
  \          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-domain\n        method: PUT\n        description: Update a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name:\
  \ '{{tools.name}}'\n            description: '{{tools.description}}'\n            enabled: '{{tools.enabled}}'\n      - name: delete-domain\n        method: DELETE\n        description: Delete a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domain-applications\n      path: /organizations/{organizationId}/environments/{environmentId}/domains/{domainId}/applications\n      description: OAuth2/OIDC application management within\
  \ a domain.\n      operations:\n      - name: list-domain-applications\n        method: GET\n        description: List applications within a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: create-domain-application\n        method: POST\n        description: Create a new OAuth2/OIDC application within a domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            type: '{{tools.type}}'\n            settings: '{{tools.settings}}'\n    - name: domain-users\n      path: /organizations/{organizationId}/environments/{environmentId}/domains/{domainId}/users\n\
  \      description: Users within a security domain.\n      operations:\n      - name: list-domain-users\n        method: GET\n        description: List users within a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        - name: page\n          in: query\n          type: integer\n          required: false\n          description: Page number.\n        - name: size\n          in: query\n          type: integer\n          required: false\n          description: Items per page.\n        - name: q\n          in: query\n          type: string\n          required:\
  \ false\n          description: Search query.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-domain-user\n        method: POST\n        description: Create a user within a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            username: '{{tools.username}}'\n            firstName:\
  \ '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n            password: '{{tools.password}}'\n    - name: domain-roles\n      path: /organizations/{organizationId}/environments/{environmentId}/domains/{domainId}/roles\n      description: Roles within a security domain.\n      operations:\n      - name: list-domain-roles\n        method: GET\n        description: List roles within a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: domain-identities\n      path: /organizations/{organizationId}/environments/{environmentId}/domains/{domainId}/identities\n      description: Identity providers within a security domain.\n      operations:\n      - name: list-identity-providers\n        method: GET\n        description: List identity providers within a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ domain-flows\n      path: /organizations/{organizationId}/environments/{environmentId}/domains/{domainId}/flows\n      description: Authentication and authorization flows within a domain.\n      operations:\n      - name: list-domain-flows\n        method: GET\n        description: List flows configured in a security domain.\n        inputParameters:\n        - name: organizationId\n          in: path\n          type: string\n          required: true\n          description: Organization identifier.\n        - name: environmentId\n          in: path\n          type: string\n          required: true\n          description: Environment identifier.\n        - name: domainId\n          in: path\n          type: string\n          required: true\n          description: Domain identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8081\n    namespace: gravitee-access-management-api\n\
  \    description: Unified REST API for Gravitee AM administration.\n    resources:\n    - path: /v1/domains\n      name: domains\n      description: Security domains.\n      operations:\n      - method: GET\n        name: list-domains\n        description: List all security domains.\n        call: gravitee-am.list-domains\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-domain\n        description: Create a new security domain.\n        call: gravitee-am.create-domain\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          name: rest.name\n          description: rest.description\n          path: rest.path\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}\n      name: domain\n      description:\
  \ A single security domain.\n      operations:\n      - method: GET\n        name: get-domain\n        description: Get a security domain by ID.\n        call: gravitee-am.get-domain\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-domain\n        description: Delete a security domain.\n        call: gravitee-am.delete-domain\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}/applications\n      name: domain-applications\n      description: Applications within a domain.\n      operations:\n      - method: GET\n        name: list-domain-applications\n        description: List OAuth2/OIDC\
  \ applications within a domain.\n        call: gravitee-am.list-domain-applications\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}/users\n      name: domain-users\n      description: Users within a domain.\n      operations:\n      - method: GET\n        name: list-domain-users\n        description: List users within a security domain.\n        call: gravitee-am.list-domain-users\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}/roles\n      name: domain-roles\n      description: Roles within a domain.\n      operations:\n      - method: GET\n        name: list-domain-roles\n        description:\
  \ List roles within a security domain.\n        call: gravitee-am.list-domain-roles\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}/identities\n      name: domain-identities\n      description: Identity providers within a domain.\n      operations:\n      - method: GET\n        name: list-identity-providers\n        description: List identity providers within a security domain.\n        call: gravitee-am.list-identity-providers\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/{domainId}/flows\n      name: domain-flows\n      description: Flows within a domain.\n      operations:\n      - method: GET\n\
  \        name: list-domain-flows\n        description: List authentication and authorization flows within a domain.\n        call: gravitee-am.list-domain-flows\n        with:\n          organizationId: rest.organizationId\n          environmentId: rest.environmentId\n          domainId: rest.domainId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: gravitee-access-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Gravitee AM administration.\n    tools:\n    - name: list-domains\n      description: List all Gravitee AM security domains within an environment.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-domains\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-domain\n      description: Get a Gravitee AM security domain by ID.\n\
  \      hints:\n        readOnly: true\n      call: gravitee-am.get-domain\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-domain\n      description: Create a new Gravitee AM security domain.\n      hints:\n        readOnly: false\n      call: gravitee-am.create-domain\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        name: tools.name\n        description: tools.description\n        path: tools.path\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-domain\n      description: Update a Gravitee AM security domain.\n      hints:\n        readOnly: false\n        idempotent: true\n      call: gravitee-am.update-domain\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n\
  \        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-domain\n      description: Delete a Gravitee AM security domain and its resources.\n      hints:\n        destructive: true\n      call: gravitee-am.delete-domain\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domain-applications\n      description: List OAuth2/OIDC applications within a domain.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-domain-applications\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-domain-application\n      description: Create a new OAuth2/OIDC application within a domain.\n\
  \      hints:\n        readOnly: false\n      call: gravitee-am.create-domain-application\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n        name: tools.name\n        type: tools.type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domain-users\n      description: List users within a security domain.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-domain-users\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-domain-user\n      description: Create a user within a security domain.\n      hints:\n        readOnly: false\n      call: gravitee-am.create-domain-user\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n\
  \        domainId: tools.domainId\n        username: tools.username\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domain-roles\n      description: List roles within a security domain.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-domain-roles\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-identity-providers\n      description: List identity providers within a security domain.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-identity-providers\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-domain-flows\n      description: List authentication\
  \ and authorization flows within a domain.\n      hints:\n        readOnly: true\n      call: gravitee-am.list-domain-flows\n      with:\n        organizationId: tools.organizationId\n        environmentId: tools.environmentId\n        domainId: tools.domainId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/gravitee/refs/heads/main/capabilities/access-management.yaml
tags:
- Gravitee
- Identity
- Access Management
- OAuth2
tools:
- description: List all Gravitee AM security domains within an environment.
  hints:
    readOnly: true
  name: list-domains
- description: Get a Gravitee AM security domain by ID.
  hints:
    readOnly: true
  name: get-domain
- description: Create a new Gravitee AM security domain.
  hints:
    readOnly: false
  name: create-domain
- description: Update a Gravitee AM security domain.
  hints:
    idempotent: true
    readOnly: false
  name: update-domain
- description: Delete a Gravitee AM security domain and its resources.
  hints:
    destructive: true
  name: delete-domain
- description: List OAuth2/OIDC applications within a domain.
  hints:
    readOnly: true
  name: list-domain-applications
- description: Create a new OAuth2/OIDC application within a domain.
  hints:
    readOnly: false
  name: create-domain-application
- description: List users within a security domain.
  hints:
    readOnly: true
  name: list-domain-users
- description: Create a user within a security domain.
  hints:
    readOnly: false
  name: create-domain-user
- description: List roles within a security domain.
  hints:
    readOnly: true
  name: list-domain-roles
- description: List identity providers within a security domain.
  hints:
    readOnly: true
  name: list-identity-providers
- description: List authentication and authorization flows within a domain.
  hints:
    readOnly: true
  name: list-domain-flows
---
