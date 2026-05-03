---
categories: []
consumed_apis:
- connect
description: Unified workflow capability for contact center operations combining instance management, agent management, queue management, contact handling, and real-time/historical metrics. Used by contact center administrators, supervisors, and operations teams to manage and monitor the Amazon Connect contact center platform.
layout: capability
name: Amazon Connect Contact Center Operations
operations:
- description: List all Amazon Connect instances
  method: GET
  name: list-instances
  path: /v1/instances
- description: Create a new Amazon Connect instance
  method: POST
  name: create-instance
  path: /v1/instances
- description: Get details of an Amazon Connect instance
  method: GET
  name: describe-instance
  path: /v1/instances/{instance-id}
- description: List agents in an Amazon Connect instance
  method: GET
  name: list-agents
  path: /v1/instances/{instance-id}/agents
- description: Create a new agent in an Amazon Connect instance
  method: POST
  name: create-agent
  path: /v1/instances/{instance-id}/agents
- description: Get details of a specific agent
  method: GET
  name: get-agent
  path: /v1/instances/{instance-id}/agents/{agent-id}
- description: List queues in an Amazon Connect instance
  method: GET
  name: list-queues
  path: /v1/instances/{instance-id}/queues
- description: Create a new queue in an Amazon Connect instance
  method: POST
  name: create-queue
  path: /v1/instances/{instance-id}/queues
- description: List routing profiles in an Amazon Connect instance
  method: GET
  name: list-routing-profiles
  path: /v1/instances/{instance-id}/routing-profiles
- description: List contact flows in an Amazon Connect instance
  method: GET
  name: list-contact-flows
  path: /v1/instances/{instance-id}/contact-flows
- description: Search contacts in an Amazon Connect instance
  method: POST
  name: search-contacts
  path: /v1/contacts/search
- description: Get real-time metrics for queues and agents
  method: POST
  name: get-current-metrics
  path: /v1/instances/{instance-id}/metrics/current
- description: Get historical metrics for an Amazon Connect instance
  method: POST
  name: get-historical-metrics
  path: /v1/instances/{instance-id}/metrics/historical
personas: []
provider_name: Amazon Connect
provider_slug: amazon-connect
search_terms:
- describe instance
- search contacts in an amazon connect instance
- list all agents/users in an amazon connect instance
- get details of a specific agent including their routing profile and security profile
- real-time and historical performance metrics and reporting
- get full details of a specific contact interaction
- monitors agent activity, queue health, and contact center performance using real-time and historical metrics dashboards.
- start chat contact
- omnichannel
- list all amazon connect instances
- create instance
- list routing profiles in an amazon connect instance
- list queues in an amazon connect instance
- configuration and lifecycle management of amazon connect instances
- get agent
- routing profile management
- list contact flows in an amazon connect instance
- operations
- get details and status of a specific amazon connect instance
- place an outbound call from the contact center to a customer phone number
- unified workflow for managing and monitoring the amazon connect contact center, combining instance administration, agent management, queue configuration, and real-time/historical metrics.
- responsible for configuring and managing the amazon connect instance, including users, queues, routing profiles, and contact flows.
- create a new agent in an amazon connect instance
- voice
- initiation, management, and search of contact interactions
- contact center
- create agent
- create queue
- contact flow management
- aws
- agent/user management
- amazon connect instance management
- list agents
- real-time metrics
- get current metrics
- list all amazon connect contact center instances in the aws account
- list all contact flows in an amazon connect instance
- get historical metrics
- get real-time metrics showing agents online, contacts in queue, and queue health
- list agents in an amazon connect instance
- queue management
- amazon connect
- user/agent account management and workforce administration
- chat
- list routing profiles
- ai
- search for past contacts by time range, agent, queue, or channel
- metrics
- Contact Center Supervisor
- single instance operations
- initiate a chat contact session with a customer
- customer service
- create a new amazon connect instance
- get real-time metrics for queues and agents
- list all queues configured in an amazon connect instance
- create a new queue in an amazon connect instance
- list contact flows
- historical metrics
- list queues
- describe contact
- get historical metrics for an amazon connect instance
- start outbound voice contact
- list all routing profiles configured in an amazon connect instance
- Operations Team
- get details of a specific agent
- list instances
- Contact Center Administrator
- contact search
- get historical metrics for contacts handled, handle time, abandon rate, and service level
- manages day-to-day contact center operations including agent status, contact handling, and performance reporting.
- get details of an amazon connect instance
- queue, routing profile, and contact flow configuration for intelligent routing
- search contacts
- individual agent operations
slug: contact-center-operations
source_filename: contact-center-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Connect Contact Center Operations\n  description: >-\n    Unified workflow capability for contact center operations combining instance management,\n    agent management, queue management, contact handling, and real-time/historical metrics.\n    Used by contact center administrators, supervisors, and operations teams to manage\n    and monitor the Amazon Connect contact center platform.\n  tags:\n    - Amazon Connect\n    - Contact Center\n    - AWS\n    - Operations\n    - Metrics\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_SESSION_TOKEN: AWS_SESSION_TOKEN\n\ncapability:\n  consumes:\n    - import: connect\n      location: ./shared/connect-service.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: contact-center-api\n      description: Unified REST\
  \ API for Amazon Connect contact center operations.\n      resources:\n        - path: /v1/instances\n          name: instances\n          description: Amazon Connect instance management\n          operations:\n            - method: GET\n              name: list-instances\n              description: List all Amazon Connect instances\n              call: \"connect.list-instances\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-instance\n              description: Create a new Amazon Connect instance\n              call: \"connect.create-instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}\n          name: instance\n          description: Single instance operations\n          operations:\n            - method: GET\n              name: describe-instance\n              description:\
  \ Get details of an Amazon Connect instance\n              call: \"connect.describe-instance\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/agents\n          name: agents\n          description: Agent/user management\n          operations:\n            - method: GET\n              name: list-agents\n              description: List agents in an Amazon Connect instance\n              call: \"connect.list-users\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-agent\n              description: Create a new agent in an Amazon Connect instance\n              call: \"connect.create-user\"\n              with:\n                InstanceId: \"rest.instance-id\"\
  \n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/agents/{agent-id}\n          name: agent\n          description: Individual agent operations\n          operations:\n            - method: GET\n              name: get-agent\n              description: Get details of a specific agent\n              call: \"connect.describe-user\"\n              with:\n                InstanceId: \"rest.instance-id\"\n                UserId: \"rest.agent-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/queues\n          name: queues\n          description: Queue management\n          operations:\n            - method: GET\n              name: list-queues\n              description: List queues in an Amazon Connect instance\n              call: \"connect.list-queues\"\n              with:\n                InstanceId:\
  \ \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-queue\n              description: Create a new queue in an Amazon Connect instance\n              call: \"connect.create-queue\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/routing-profiles\n          name: routing-profiles\n          description: Routing profile management\n          operations:\n            - method: GET\n              name: list-routing-profiles\n              description: List routing profiles in an Amazon Connect instance\n              call: \"connect.list-routing-profiles\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n        \
  \          mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/contact-flows\n          name: contact-flows\n          description: Contact flow management\n          operations:\n            - method: GET\n              name: list-contact-flows\n              description: List contact flows in an Amazon Connect instance\n              call: \"connect.list-contact-flows\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/contacts/search\n          name: contact-search\n          description: Contact search\n          operations:\n            - method: POST\n              name: search-contacts\n              description: Search contacts in an Amazon Connect instance\n              call: \"connect.search-contacts\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/metrics/current\n\
  \          name: current-metrics\n          description: Real-time metrics\n          operations:\n            - method: POST\n              name: get-current-metrics\n              description: Get real-time metrics for queues and agents\n              call: \"connect.get-current-metric-data\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/instances/{instance-id}/metrics/historical\n          name: historical-metrics\n          description: Historical metrics\n          operations:\n            - method: POST\n              name: get-historical-metrics\n              description: Get historical metrics for an Amazon Connect instance\n              call: \"connect.get-metric-data\"\n              with:\n                InstanceId: \"rest.instance-id\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: contact-center-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon Connect contact center management and monitoring.\n      tools:\n        - name: list-instances\n          description: List all Amazon Connect contact center instances in the AWS account\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.list-instances\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-instance\n          description: Get details and status of a specific Amazon Connect instance\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.describe-instance\"\n          with:\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-agents\n          description:\
  \ List all agents/users in an Amazon Connect instance\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.list-users\"\n          with:\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-agent\n          description: Get details of a specific agent including their routing profile and security profile\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.describe-user\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            UserId: \"tools.user_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-queues\n          description: List all queues configured in an Amazon Connect instance\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.list-queues\"\n      \
  \    with:\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-routing-profiles\n          description: List all routing profiles configured in an Amazon Connect instance\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.list-routing-profiles\"\n          with:\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-contact-flows\n          description: List all contact flows in an Amazon Connect instance\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.list-contact-flows\"\n          with:\n            InstanceId: \"tools.instance_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-current-metrics\n          description:\
  \ Get real-time metrics showing agents online, contacts in queue, and queue health\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.get-current-metric-data\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            Filters: \"tools.filters\"\n            CurrentMetrics: \"tools.current_metrics\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-historical-metrics\n          description: Get historical metrics for contacts handled, handle time, abandon rate, and service level\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.get-metric-data\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            StartTime: \"tools.start_time\"\n            EndTime: \"tools.end_time\"\n            Filters: \"tools.filters\"\n            HistoricalMetrics: \"tools.historical_metrics\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n        - name: search-contacts\n          description: Search for past contacts by time range, agent, queue, or channel\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.search-contacts\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            TimeRange: \"tools.time_range\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-contact\n          description: Get full details of a specific contact interaction\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"connect.describe-contact\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            ContactId: \"tools.contact_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-outbound-voice-contact\n          description: Place\
  \ an outbound call from the contact center to a customer phone number\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"connect.start-outbound-voice-contact\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            ContactFlowId: \"tools.contact_flow_id\"\n            DestinationPhoneNumber: \"tools.destination_phone_number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-chat-contact\n          description: Initiate a chat contact session with a customer\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"connect.start-chat-contact\"\n          with:\n            InstanceId: \"tools.instance_id\"\n            ContactFlowId: \"tools.contact_flow_id\"\n            ParticipantDetails: \"tools.participant_details\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-connect/refs/heads/main/capabilities/contact-center-operations.yaml
tags:
- Amazon Connect
- Contact Center
- Operations
- Metrics
tools:
- description: List all Amazon Connect contact center instances in the AWS account
  hints:
    openWorld: true
    readOnly: true
  name: list-instances
- description: Get details and status of a specific Amazon Connect instance
  hints:
    openWorld: true
    readOnly: true
  name: describe-instance
- description: List all agents/users in an Amazon Connect instance
  hints:
    openWorld: true
    readOnly: true
  name: list-agents
- description: Get details of a specific agent including their routing profile and security profile
  hints:
    openWorld: true
    readOnly: true
  name: get-agent
- description: List all queues configured in an Amazon Connect instance
  hints:
    openWorld: true
    readOnly: true
  name: list-queues
- description: List all routing profiles configured in an Amazon Connect instance
  hints:
    openWorld: true
    readOnly: true
  name: list-routing-profiles
- description: List all contact flows in an Amazon Connect instance
  hints:
    openWorld: true
    readOnly: true
  name: list-contact-flows
- description: Get real-time metrics showing agents online, contacts in queue, and queue health
  hints:
    openWorld: true
    readOnly: true
  name: get-current-metrics
- description: Get historical metrics for contacts handled, handle time, abandon rate, and service level
  hints:
    openWorld: true
    readOnly: true
  name: get-historical-metrics
- description: Search for past contacts by time range, agent, queue, or channel
  hints:
    openWorld: true
    readOnly: true
  name: search-contacts
- description: Get full details of a specific contact interaction
  hints:
    openWorld: true
    readOnly: true
  name: describe-contact
- description: Place an outbound call from the contact center to a customer phone number
  hints:
    openWorld: false
    readOnly: false
  name: start-outbound-voice-contact
- description: Initiate a chat contact session with a customer
  hints:
    openWorld: false
    readOnly: false
  name: start-chat-contact
---
