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
- oauth
- developer tools
- list connections
- list all saas providers available for integration through ampersand, including salesforce, hubspot, marketo, zendesk, and hundreds more.
- list all data destinations configured in an ampersand project for integration data delivery to webhooks, databases, or other targets.
- list all integration definitions in an ampersand project.
- data destinations for integration output delivery.
- list destinations
- available saas provider connectors.
- list all oauth connections to third-party saas providers established by end users in an ampersand project.
- Product Developer
- ampersand
- create a new ampersand integration installation to connect an end user's saas account with a configured integration.
- list all integration installations mapping end-user groups to integration configurations in ampersand.
- list all connections established for saas providers in a project.
- list providers
- platform
- infrastructure engineer automating integration deployment and managing connections at scale.
- list all integration definitions configured in an ampersand project for a saas product.
- integrations
- list all integration installations for end-user connections.
- integration definitions for a project.
- saas
- list integrations
- webhooks
- list all saas providers available for integration through ampersand.
- list installations
- finops
- data sync
- list all destinations for integration data delivery.
- workflow for managing saas integrations, connections, and installations.
- create installation
- integration management
- create a new integration installation for an end user.
- native product integrations between saas applications using managed oauth, data sync, and field mapping.
- saas product developer building native integrations with third-party tools using ampersand.
- saas integrations
- integration installations for end-user connections.
- oauth connections to third-party saas providers.
- Platform Engineer
slug: integration-management
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
