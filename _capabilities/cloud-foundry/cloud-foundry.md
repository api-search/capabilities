---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Cloud Foundry
operations: []
personas: []
provider_name: Cloud Foundry
provider_slug: cloud-foundry
search_terms:
- cloud foundry foundation
- open source
- platform
- containers
- paas
- multi-cloud
slug: cloud-foundry
source_filename: cloud-foundry.yaml
source_heading: Capability Spec
source_yaml: "# Naftiko capabilities profile for Cloud Foundry.\n# Capabilities map verbs against the high-value operations in the\n# Cloud Controller API v3 (https://v3-apidocs.cloudfoundry.org/).\nprovider: cloud-foundry\nname: Cloud Foundry\ndescription: >-\n  Cloud Foundry is an open-source Platform as a Service. These\n  capabilities cover the core lifecycle of organizations, spaces,\n  applications, builds, droplets, routes, and service instances\n  through the Cloud Controller API v3.\ncapabilities:\n  - id: cloud-foundry.orgs.list\n    name: List organizations\n    description: Return organizations visible to the authenticated user.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1organizations/get\n    inputs:\n      - page\n      - per_page\n      - names\n    outputs:\n      - resources\n      - pagination\n\n  - id: cloud-foundry.spaces.list\n    name: List spaces\n    description: Return spaces\
  \ in an organization.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1spaces/get\n    inputs:\n      - organization_guids\n      - page\n      - per_page\n    outputs:\n      - resources\n      - pagination\n\n  - id: cloud-foundry.apps.create\n    name: Create application\n    description: Register a new application in a space.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1apps/post\n    inputs:\n      - name\n      - relationships\n      - lifecycle\n      - environment_variables\n    outputs:\n      - guid\n\n  - id: cloud-foundry.apps.start\n    name: Start application\n    description: Start an existing application's web process.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1apps~1{guid}~1actions~1start/post\n    inputs:\n\
  \      - guid\n    outputs:\n      - state\n\n  - id: cloud-foundry.apps.stop\n    name: Stop application\n    description: Stop a running application.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1apps~1{guid}~1actions~1stop/post\n    inputs:\n      - guid\n    outputs:\n      - state\n\n  - id: cloud-foundry.packages.upload\n    name: Upload package\n    description: Upload application source bits or a docker reference as a package.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1packages/post\n    inputs:\n      - type\n      - relationships\n      - data\n    outputs:\n      - guid\n\n  - id: cloud-foundry.builds.create\n    name: Create build\n    description: Stage a build (droplet) from an uploaded package.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1builds/post\n\
  \    inputs:\n      - package\n      - lifecycle\n    outputs:\n      - guid\n      - state\n\n  - id: cloud-foundry.routes.create\n    name: Create route\n    description: Reserve a route in a space and domain for an application.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1routes/post\n    inputs:\n      - host\n      - path\n      - relationships\n    outputs:\n      - guid\n      - url\n\n  - id: cloud-foundry.service-instances.create\n    name: Create service instance\n    description: Provision a service instance from a marketplace plan.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1service_instances/post\n    inputs:\n      - name\n      - type\n      - relationships\n      - parameters\n    outputs:\n      - guid\n\n  - id: cloud-foundry.tasks.run\n    name: Run task\n    description: Run a one-off task\
  \ against an application's droplet.\n    api: cloud-foundry:cloud-controller-api-v3\n    operationRef: openapi/cloud-foundry-cloud-controller-api-v3-openapi.yml#/paths/~1apps~1{guid}~1tasks/post\n    inputs:\n      - guid\n      - command\n      - name\n      - memory_in_mb\n    outputs:\n      - guid\n      - state\n\n  - id: cloud-foundry.logs.stream\n    name: Stream application logs\n    description: Stream Loggregator log and metric envelopes for an app.\n    api: cloud-foundry:loggregator\n    operationRef: asyncapi/cloud-foundry-loggregator-asyncapi.yml#/channels/firehose\n    inputs:\n      - source-id\n    outputs:\n      - envelopes\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cloud-foundry/refs/heads/main/capabilities/cloud-foundry.yaml
tags: []
tools: []
---
