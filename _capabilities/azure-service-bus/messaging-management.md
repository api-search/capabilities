---
categories:
- messaging
consumed_apis: []
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
- delete a service bus namespace
- namespace details
- list queues
- get namespace
- message queues
- get namespace details
- pub/sub topics
- service bus
- list azure service bus namespaces in a subscription
- create or update namespace
- get details of a specific service bus namespace
- message broker
- service bus namespaces
- create or update a service bus namespace
- enterprise
- list topics
- pub/sub
- list queues within a service bus namespace
- list namespaces
- cloud infrastructure
- delete namespace
- cloud
- azure
- list all namespaces
- queues
- list topics within a service bus namespace
- messaging
slug: messaging-management
source_filename: messaging-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Azure Service Bus Messaging Management\n  description: Unified workflow for managing Azure Service Bus messaging infrastructure including namespaces, queues, topics,\n    and subscriptions. Designed for cloud architects and platform engineers managing enterprise messaging.\n  tags:\n  - Azure\n  - Service Bus\n  - Messaging\n  - Cloud Infrastructure\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AZURE_BEARER_TOKEN: AZURE_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: service-bus\n    baseUri: https://management.azure.com\n    description: Azure Service Bus Management API\n    authentication:\n      type: bearer\n      token: '{{AZURE_BEARER_TOKEN}}'\n    resources:\n    - name: namespaces\n      path: /subscriptions/{subscriptionId}/providers/Microsoft.ServiceBus/namespaces\n      description: Service Bus namespaces\n      operations:\n      - name: list-namespaces\n \
  \       method: GET\n        description: List all namespaces in a subscription\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: namespace-details\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ServiceBus/namespaces/{namespaceName}\n      description: Manage a specific namespace\n      operations:\n      - name: get-namespace\n        method: GET\n        description: Get namespace details\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure\
  \ subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        - name: api-version\n          in: query\n          type: string\n          required: true\n          description: API version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-or-update-namespace\n        method: PUT\n        description: Create or update a namespace\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group\
  \ name\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-namespace\n        method: DELETE\n        description: Delete a namespace\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ServiceBus/namespaces/{namespaceName}/queues\n\
  \      description: Service Bus queues\n      operations:\n      - name: list-queues\n        method: GET\n        description: List queues in a namespace\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: topics\n      path: /subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ServiceBus/namespaces/{namespaceName}/topics\n      description: Service Bus topics\n      operations:\n      - name: list-topics\n   \
  \     method: GET\n        description: List topics in a namespace\n        inputParameters:\n        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: Azure subscription ID\n        - name: resourceGroupName\n          in: path\n          type: string\n          required: true\n          description: Resource group name\n        - name: namespaceName\n          in: path\n          type: string\n          required: true\n          description: Namespace name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: messaging-api\n    description: Unified REST API for Azure Service Bus messaging management.\n    resources:\n    - path: /v1/namespaces\n      name: namespaces\n      description: Service Bus namespaces\n      operations:\n      - method: GET\n        name: list-namespaces\n      \
  \  description: List all namespaces\n        call: service-bus.list-namespaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/namespaces/{namespaceName}\n      name: namespace-details\n      description: Namespace details\n      operations:\n      - method: GET\n        name: get-namespace\n        description: Get namespace details\n        call: service-bus.get-namespace\n        with:\n          namespaceName: rest.namespaceName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/queues\n      name: queues\n      description: Message queues\n      operations:\n      - method: GET\n        name: list-queues\n        description: List queues\n        call: service-bus.list-queues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/topics\n      name: topics\n      description: Pub/sub topics\n      operations:\n      - method: GET\n        name: list-topics\n     \
  \   description: List topics\n        call: service-bus.list-topics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: messaging-mcp\n    transport: http\n    description: MCP server for AI-assisted Azure Service Bus messaging management.\n    tools:\n    - name: list-namespaces\n      description: List Azure Service Bus namespaces in a subscription\n      hints:\n        readOnly: true\n        openWorld: true\n      call: service-bus.list-namespaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-namespace\n      description: Get details of a specific Service Bus namespace\n      hints:\n        readOnly: true\n      call: service-bus.get-namespace\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        namespaceName: tools.namespaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ create-or-update-namespace\n      description: Create or update a Service Bus namespace\n      hints:\n        readOnly: false\n        idempotent: true\n      call: service-bus.create-or-update-namespace\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        namespaceName: tools.namespaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-namespace\n      description: Delete a Service Bus namespace\n      hints:\n        destructive: true\n        idempotent: true\n      call: service-bus.delete-namespace\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        namespaceName: tools.namespaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List queues within a Service Bus namespace\n      hints:\n        readOnly: true\n      call: service-bus.list-queues\n\
  \      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        namespaceName: tools.namespaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-topics\n      description: List topics within a Service Bus namespace\n      hints:\n        readOnly: true\n      call: service-bus.list-topics\n      with:\n        subscriptionId: tools.subscriptionId\n        resourceGroupName: tools.resourceGroupName\n        namespaceName: tools.namespaceName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/azure-service-bus/refs/heads/main/capabilities/messaging-management.yaml
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
