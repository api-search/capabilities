---
consumed_apis:
- service-bus
description: Unified workflow for managing Azure Service Bus messaging infrastructure including namespaces, queues, topics, and subscriptions. Designed for cloud architects and platform engineers managing enterprise messaging.
layout: capability
name: Azure Service Bus Messaging Management
operations:
- description: List all namespaces
  method: GET
  name: list-namespaces
  path: /v1/namespaces
- description: Get namespace details
  method: GET
  name: get-namespace
  path: /v1/namespaces/{namespaceName}
- description: List queues
  method: GET
  name: list-queues
  path: /v1/queues
- description: List topics
  method: GET
  name: list-topics
  path: /v1/topics
personas: []
provider_name: Azure Service Bus
provider_slug: azure-service-bus
search_terms:
- get namespace
- create or update a service bus namespace
- queues
- list all namespaces
- list queues within a service bus namespace
- cloud
- list queues
- pub/sub topics
- service bus
- delete a service bus namespace
- list topics
- list namespaces
- create or update namespace
- delete namespace
- message queues
- pub/sub
- service bus namespaces
- cloud infrastructure
- namespace details
- message broker
- get namespace details
- messaging
- get details of a specific service bus namespace
- list azure service bus namespaces in a subscription
- list topics within a service bus namespace
- azure
- enterprise
slug: messaging-management
tags:
- Azure
- Service Bus
- Messaging
- Cloud Infrastructure
tools:
- description: List Azure Service Bus namespaces in a subscription
  hints:
    openWorld: true
    readOnly: true
  name: list-namespaces
- description: Get details of a specific Service Bus namespace
  hints:
    readOnly: true
  name: get-namespace
- description: Create or update a Service Bus namespace
  hints:
    idempotent: true
    readOnly: false
  name: create-or-update-namespace
- description: Delete a Service Bus namespace
  hints:
    destructive: true
    idempotent: true
  name: delete-namespace
- description: List queues within a Service Bus namespace
  hints:
    readOnly: true
  name: list-queues
- description: List topics within a Service Bus namespace
  hints:
    readOnly: true
  name: list-topics
---
