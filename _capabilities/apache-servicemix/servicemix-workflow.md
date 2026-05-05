---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Servicemix Workflow
operations: []
personas: []
provider_name: Apache ServiceMix
provider_slug: apache-servicemix
search_terms:
- messaging
- enterprise integration
- esb
- developer building and deploying camel/cxf integration routes
- open source
- integration
- engineer managing servicemix esb infrastructure
- apache
- esb-based enterprise application integration
- jms/activemq message routing and transformation
- osgi
- deploy and manage esb integration routes and endpoints
slug: servicemix-workflow
source_filename: servicemix-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache ServiceMix Integration Workflow\ndescription: Workflow capability for managing ESB bundles, Camel routes, and message queues in Apache ServiceMix.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache ServiceMix REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-servicemix/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/servicemix-api.yaml\nworkflow:\n  name: servicemix-workflow\n  description: Deploy and manage integration routes, web service endpoints, and message queues.\n  steps:\n    - name: list-bundles\n      description: List deployed OSGi bundles\n      api: Apache ServiceMix REST API\n      operation: listBundles\n    - name: list-routes\n      description: List Camel integration routes\n      api: Apache ServiceMix REST API\n      operation: listRoutes\n    - name: start-route\n      description: Start an integration route\n      api: Apache ServiceMix REST API\n      operation: startRoute\n    - name: list-queues\n\
  \      description: Monitor message queues\n      api: Apache ServiceMix REST API\n      operation: listQueues\nexposes:\n  - type: rest\n    port: 8181\n    paths:\n      - /bundles\n      - /bundles/{bundleId}\n      - /routes\n      - /routes/{routeId}\n      - /routes/{routeId}/start\n      - /routes/{routeId}/stop\n      - /endpoints\n      - /queues\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-bundles\n        description: List OSGi bundles\n        operation: listBundles\n      - name: get-bundle\n        description: Get bundle details\n        operation: getBundle\n      - name: update-bundle-state\n        description: Start or stop a bundle\n        operation: updateBundleState\n      - name: list-routes\n        description: List Camel routes\n        operation: listRoutes\n      - name: start-route\n        description: Start a Camel route\n        operation: startRoute\n      - name: stop-route\n        description: Stop a Camel route\n        operation:\
  \ stopRoute\n      - name: list-endpoints\n        description: List web service endpoints\n        operation: listEndpoints\n      - name: list-queues\n        description: List ActiveMQ queues\n        operation: listQueues\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-servicemix/refs/heads/main/capabilities/servicemix-workflow.yaml
tags: []
tools: []
---
