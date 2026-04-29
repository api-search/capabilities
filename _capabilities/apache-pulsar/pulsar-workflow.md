---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Pulsar Workflow
operations: []
personas: []
provider_name: Apache Pulsar
provider_slug: apache-pulsar
search_terms:
- apache
- engineer managing pulsar clusters and multi-tenancy
- developer producing and consuming messages with pulsar
- engineer building real-time streaming pipelines with pulsar
- cloud native
- multi-tenant
- messaging
- pub-sub
- end-to-end workflow for producing and consuming pulsar messages
- open source
- real-time message delivery between producers and consumers
- streaming
- workflow for managing pulsar cluster resources
- processing message streams with pulsar functions
slug: pulsar-workflow
source_filename: pulsar-workflow.yaml
source_heading: Capability Spec
source_yaml: "name: Apache Pulsar Messaging Workflow\ndescription: Workflow capability for managing topics, subscriptions, and message streaming with Apache Pulsar.\nversion: 1.0.0-alpha1\napis:\n  - name: Apache Pulsar Admin REST API\n    url: https://raw.githubusercontent.com/api-evangelist/apache-pulsar/refs/heads/main/apis.yml\nshared:\n  - url: capabilities/shared/pulsar-api.yaml\nworkflow:\n  name: pulsar-workflow\n  description: Manage Pulsar tenants, namespaces, topics, and message producers/consumers.\n  steps:\n    - name: create-tenant\n      description: Create a new Pulsar tenant\n      api: Apache Pulsar Admin REST API\n      operation: createTenant\n    - name: create-namespace\n      description: Create a namespace within a tenant\n      api: Apache Pulsar Admin REST API\n      operation: createNamespace\n    - name: create-topic\n      description: Create a Pulsar topic\n      api: Apache Pulsar Admin REST API\n      operation: createTopic\n    - name: get-topic-stats\n\
  \      description: Get statistics for a Pulsar topic\n      api: Apache Pulsar Admin REST API\n      operation: getTopicStats\n    - name: publish-message\n      description: Publish a message to a topic\n      api: Apache Pulsar Messaging API\n      operation: publishMessage\n    - name: consume-message\n      description: Consume messages from a subscription\n      api: Apache Pulsar Messaging API\n      operation: consumeMessage\nexposes:\n  - type: rest\n    port: 8080\n    paths:\n      - /admin/v2/clusters\n      - /admin/v2/tenants\n      - /admin/v2/namespaces/{tenant}\n      - /admin/v2/persistent/{tenant}/{namespace}\n      - /admin/v2/functions\n  - type: mcp\n    port: 9090\n    tools:\n      - name: list-clusters\n        description: List Pulsar clusters\n        operation: listClusters\n      - name: create-tenant\n        description: Create a Pulsar tenant\n        operation: createTenant\n      - name: create-namespace\n        description: Create a namespace\n     \
  \   operation: createNamespace\n      - name: create-topic\n        description: Create a Pulsar topic\n        operation: createTopic\n      - name: get-topic-stats\n        description: Get topic statistics\n        operation: getTopicStats\n      - name: list-subscriptions\n        description: List topic subscriptions\n        operation: listSubscriptions\n      - name: create-function\n        description: Deploy a Pulsar function\n        operation: createFunction\n      - name: get-function-status\n        description: Get Pulsar function status\n        operation: getFunctionStatus\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apache-pulsar/refs/heads/main/capabilities/pulsar-workflow.yaml
tags: []
tools: []
---
