---
categories: []
consumed_apis:
- ampersand-api
description: Workflow capability for product developers and platform engineers to manage SaaS integrations, connections, installations, and destinations programmatically through the Ampersand platform.
layout: capability
name: Ampersand Integration Management
operations:
- description: List all SaaS providers available for integration through Ampersand.
  method: GET
  name: list-providers
  path: /v1/providers
- description: List all integration definitions in an Ampersand project.
  method: GET
  name: list-integrations
  path: /v1/projects/{projectIdOrName}/integrations
- description: List all connections established for SaaS providers in a project.
  method: GET
  name: list-connections
  path: /v1/projects/{projectIdOrName}/connections
- description: List all integration installations for end-user connections.
  method: GET
  name: list-installations
  path: /v1/projects/{projectIdOrName}/installations
- description: Create a new integration installation for an end user.
  method: POST
  name: create-installation
  path: /v1/projects/{projectIdOrName}/installations
- description: List all destinations for integration data delivery.
  method: GET
  name: list-destinations
  path: /v1/projects/{projectIdOrName}/destinations
personas: []
provider_name: Ampersand
provider_slug: ampersand
search_terms:
- list all connections established for saas providers in a project.
- create a new integration installation for an end user.
- create a new ampersand integration installation to connect an end user's saas account with a configured integration.
- list all integration definitions in an ampersand project.
- infrastructure engineer automating integration deployment and managing connections at scale.
- oauth
- developer tools
- list integrations
- list providers
- list connections
- list all destinations for integration data delivery.
- list all oauth connections to third-party saas providers established by end users in an ampersand project.
- saas product developer building native integrations with third-party tools using ampersand.
- list all integration installations mapping end-user groups to integration configurations in ampersand.
- saas integrations
- create installation
- saas
- integration definitions for a project.
- integration installations for end-user connections.
- integration management
- list all integration installations for end-user connections.
- finops
- list destinations
- ampersand
- data destinations for integration output delivery.
- list all saas providers available for integration through ampersand.
- list all saas providers available for integration through ampersand, including salesforce, hubspot, marketo, zendesk, and hundreds more.
- Product Developer
- platform
- oauth connections to third-party saas providers.
- list all integration definitions configured in an ampersand project for a saas product.
- list all data destinations configured in an ampersand project for integration data delivery to webhooks, databases, or other targets.
- integrations
- native product integrations between saas applications using managed oauth, data sync, and field mapping.
- available saas provider connectors.
- webhooks
- list installations
- workflow for managing saas integrations, connections, and installations.
- Platform Engineer
- data sync
slug: integration-management
source_filename: integration-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Ampersand Integration Management\"\n  description: \"Workflow capability for product developers and platform engineers to manage SaaS integrations, connections, installations, and destinations programmatically through the Ampersand platform.\"\n  tags:\n    - Ampersand\n    - Integration Management\n    - SaaS Integrations\n    - Developer Tools\n    - FinOps\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AMPERSAND_API_KEY: AMPERSAND_API_KEY\n\ncapability:\n  consumes:\n    - import: ampersand-api\n      location: ./shared/ampersand-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: integration-management-api\n      description: \"Unified REST API for managing Ampersand SaaS integrations, connections, and installations.\"\n      resources:\n        - path: /v1/providers\n          name: providers\n          description: \"Available SaaS provider connectors.\"\
  \n          operations:\n            - method: GET\n              name: list-providers\n              description: \"List all SaaS providers available for integration through Ampersand.\"\n              call: \"ampersand-api.list-providers\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectIdOrName}/integrations\n          name: integrations\n          description: \"Integration definitions for a project.\"\n          operations:\n            - method: GET\n              name: list-integrations\n              description: \"List all integration definitions in an Ampersand project.\"\n              call: \"ampersand-api.list-integrations\"\n              with:\n                projectIdOrName: \"rest.projectIdOrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectIdOrName}/connections\n          name: connections\n\
  \          description: \"OAuth connections to third-party SaaS providers.\"\n          operations:\n            - method: GET\n              name: list-connections\n              description: \"List all connections established for SaaS providers in a project.\"\n              call: \"ampersand-api.list-connections\"\n              with:\n                projectIdOrName: \"rest.projectIdOrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectIdOrName}/installations\n          name: installations\n          description: \"Integration installations for end-user connections.\"\n          operations:\n            - method: GET\n              name: list-installations\n              description: \"List all integration installations for end-user connections.\"\n              call: \"ampersand-api.list-installations\"\n              with:\n                projectIdOrName: \"rest.projectIdOrName\"\n   \
  \             integrationId: \"rest.integrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-installation\n              description: \"Create a new integration installation for an end user.\"\n              call: \"ampersand-api.create-installation\"\n              with:\n                projectIdOrName: \"rest.projectIdOrName\"\n                integrationId: \"rest.integrationId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/projects/{projectIdOrName}/destinations\n          name: destinations\n          description: \"Data destinations for integration output delivery.\"\n          operations:\n            - method: GET\n              name: list-destinations\n              description: \"List all destinations for integration data delivery.\"\n              call: \"ampersand-api.list-destinations\"\
  \n              with:\n                projectIdOrName: \"rest.projectIdOrName\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: integration-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SaaS integration management and automation.\"\n      tools:\n        - name: list-providers\n          description: \"List all SaaS providers available for integration through Ampersand, including Salesforce, HubSpot, Marketo, Zendesk, and hundreds more.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ampersand-api.list-providers\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-integrations\n          description: \"List all integration definitions configured in an Ampersand project for a SaaS product.\"\n          hints:\n            readOnly: true\n\
  \            openWorld: true\n          call: \"ampersand-api.list-integrations\"\n          with:\n            projectIdOrName: \"tools.projectIdOrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-connections\n          description: \"List all OAuth connections to third-party SaaS providers established by end users in an Ampersand project.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ampersand-api.list-connections\"\n          with:\n            projectIdOrName: \"tools.projectIdOrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-installations\n          description: \"List all integration installations mapping end-user groups to integration configurations in Ampersand.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"ampersand-api.list-installations\"\n\
  \          with:\n            projectIdOrName: \"tools.projectIdOrName\"\n            integrationId: \"tools.integrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-installation\n          description: \"Create a new Ampersand integration installation to connect an end user's SaaS account with a configured integration.\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"ampersand-api.create-installation\"\n          with:\n            projectIdOrName: \"tools.projectIdOrName\"\n            integrationId: \"tools.integrationId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-destinations\n          description: \"List all data destinations configured in an Ampersand project for integration data delivery to webhooks, databases, or other targets.\"\n          hints:\n            readOnly: true\n           \
  \ openWorld: true\n          call: \"ampersand-api.list-destinations\"\n          with:\n            projectIdOrName: \"tools.projectIdOrName\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ampersand/refs/heads/main/capabilities/integration-management.yaml
tags:
- Ampersand
- Integration Management
- SaaS Integrations
- Developer Tools
- FinOps
tools:
- description: List all SaaS providers available for integration through Ampersand, including Salesforce, HubSpot, Marketo, Zendesk, and hundreds more.
  hints:
    openWorld: true
    readOnly: true
  name: list-providers
- description: List all integration definitions configured in an Ampersand project for a SaaS product.
  hints:
    openWorld: true
    readOnly: true
  name: list-integrations
- description: List all OAuth connections to third-party SaaS providers established by end users in an Ampersand project.
  hints:
    openWorld: true
    readOnly: true
  name: list-connections
- description: List all integration installations mapping end-user groups to integration configurations in Ampersand.
  hints:
    openWorld: true
    readOnly: true
  name: list-installations
- description: Create a new Ampersand integration installation to connect an end user's SaaS account with a configured integration.
  hints:
    openWorld: false
    readOnly: false
  name: create-installation
- description: List all data destinations configured in an Ampersand project for integration data delivery to webhooks, databases, or other targets.
  hints:
    openWorld: true
    readOnly: true
  name: list-destinations
---
