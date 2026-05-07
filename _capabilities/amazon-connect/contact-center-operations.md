---
categories: []
consumed_apis: []
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
- list all queues configured in an amazon connect instance
- get historical metrics for contacts handled, handle time, abandon rate, and service level
- operations
- list routing profiles in an amazon connect instance
- real-time metrics
- queue, routing profile, and contact flow configuration for intelligent routing
- create queue
- responsible for configuring and managing the amazon connect instance, including users, queues, routing profiles, and contact flows.
- contact search
- amazon connect
- get details and status of a specific amazon connect instance
- user/agent account management and workforce administration
- get current metrics
- ai
- list queues
- get historical metrics
- list all contact flows in an amazon connect instance
- create a new agent in an amazon connect instance
- get details of a specific agent including their routing profile and security profile
- single instance operations
- get agent
- initiation, management, and search of contact interactions
- list all amazon connect instances
- list queues in an amazon connect instance
- monitors agent activity, queue health, and contact center performance using real-time and historical metrics dashboards.
- describe instance
- list routing profiles
- create a new queue in an amazon connect instance
- start chat contact
- contact flow management
- search contacts in an amazon connect instance
- list instances
- Operations Team
- amazon connect instance management
- create a new amazon connect instance
- search for past contacts by time range, agent, queue, or channel
- agent/user management
- Contact Center Administrator
- get full details of a specific contact interaction
- list all amazon connect contact center instances in the aws account
- manages day-to-day contact center operations including agent status, contact handling, and performance reporting.
- list agents in an amazon connect instance
- get details of a specific agent
- list contact flows in an amazon connect instance
- historical metrics
- list all routing profiles configured in an amazon connect instance
- describe contact
- chat
- queue management
- place an outbound call from the contact center to a customer phone number
- Contact Center Supervisor
- create agent
- individual agent operations
- initiate a chat contact session with a customer
- configuration and lifecycle management of amazon connect instances
- real-time and historical performance metrics and reporting
- metrics
- get details of an amazon connect instance
- unified workflow for managing and monitoring the amazon connect contact center, combining instance administration, agent management, queue configuration, and real-time/historical metrics.
- create instance
- routing profile management
- search contacts
- aws
- voice
- omnichannel
- get real-time metrics showing agents online, contacts in queue, and queue health
- list agents
- list contact flows
- customer service
- get historical metrics for an amazon connect instance
- get real-time metrics for queues and agents
- start outbound voice contact
- contact center
- list all agents/users in an amazon connect instance
slug: contact-center-operations
source_filename: contact-center-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Connect Contact Center Operations\n  description: Unified workflow capability for contact center operations combining instance management, agent management,\n    queue management, contact handling, and real-time/historical metrics. Used by contact center administrators, supervisors,\n    and operations teams to manage and monitor the Amazon Connect contact center platform.\n  tags:\n  - Amazon Connect\n  - Contact Center\n  - AWS\n  - Operations\n  - Metrics\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_SESSION_TOKEN: AWS_SESSION_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: connect\n    baseUri: https://connect.amazonaws.com\n    description: Amazon Connect Service REST API\n    authentication:\n      type: bearer\n      token: '{{AWS_SESSION_TOKEN}}'\n    resources:\n  \
  \  - name: instances\n      path: /instance\n      description: Amazon Connect instance management\n      operations:\n      - name: list-instances\n        method: GET\n        description: List all Amazon Connect instances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-instance\n        method: POST\n        description: Create a new Amazon Connect instance\n        body:\n          type: json\n          data:\n            IdentityManagementType: '{{tools.identity_management_type}}'\n            InstanceAlias: '{{tools.instance_alias}}'\n            InboundCallsEnabled: '{{tools.inbound_calls_enabled}}'\n            OutboundCallsEnabled: '{{tools.outbound_calls_enabled}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance\n      path: /instance/{InstanceId}\n      description: Single Amazon\
  \ Connect instance operations\n      operations:\n      - name: describe-instance\n        method: GET\n        description: Get details of a specific Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-instance\n        method: DELETE\n        description: Delete an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users/{InstanceId}\n      description:\
  \ Amazon Connect user management\n      operations:\n      - name: list-users\n        method: GET\n        description: List all users in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        - name: nextToken\n          in: query\n          type: string\n          required: false\n          description: Token for pagination\n        - name: maxResults\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-user\n        method: POST\n        description: Create a user in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n   \
  \       required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n          data:\n            Username: '{{tools.username}}'\n            IdentityInfo: '{{tools.identity_info}}'\n            PhoneConfig: '{{tools.phone_config}}'\n            SecurityProfileIds: '{{tools.security_profile_ids}}'\n            RoutingProfileId: '{{tools.routing_profile_id}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /users/{InstanceId}/{UserId}\n      description: Individual user operations\n      operations:\n      - name: describe-user\n        method: GET\n        description: Get details of a specific user\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        - name: UserId\n \
  \         in: path\n          type: string\n          required: true\n          description: The identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-user\n        method: DELETE\n        description: Delete a user from an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        - name: UserId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: queues\n      path: /queues/{InstanceId}\n      description: Queue management\n      operations:\n      - name: list-queues\n        method: GET\n        description:\
  \ List all queues in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-queue\n        method: POST\n        description: Create a new queue in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            HoursOfOperationId: '{{tools.hours_of_operation_id}}'\n            MaxContacts: '{{tools.max_contacts}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: routing-profiles\n      path: /routing-profiles/{InstanceId}\n      description: Routing profile management\n      operations:\n      - name: list-routing-profiles\n        method: GET\n        description: List all routing profiles in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-routing-profile\n        method: POST\n        description: Create a new routing profile\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n\
  \            Description: '{{tools.description}}'\n            DefaultOutboundQueueId: '{{tools.default_outbound_queue_id}}'\n            MediaConcurrencies: '{{tools.media_concurrencies}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contact-flows\n      path: /contact-flows/{InstanceId}\n      description: Contact flow management\n      operations:\n      - name: list-contact-flows\n        method: GET\n        description: List all contact flows in an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-contact-flow\n        method: POST\n        description: Create a new contact flow\n\
  \        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n          data:\n            Name: '{{tools.name}}'\n            Type: '{{tools.type}}'\n            Content: '{{tools.content}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contacts\n      path: /contacts/{InstanceId}/{ContactId}\n      description: Contact operations\n      operations:\n      - name: describe-contact\n        method: GET\n        description: Get details of a specific contact\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        - name: ContactId\n          in: path\n          type: string\n       \
  \   required: true\n          description: The identifier of the contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search-contacts\n      path: /search-contacts\n      description: Contact search\n      operations:\n      - name: search-contacts\n        method: POST\n        description: Search contacts in an Amazon Connect instance\n        body:\n          type: json\n          data:\n            InstanceId: '{{tools.instance_id}}'\n            TimeRange: '{{tools.time_range}}'\n            MaxResults: '{{tools.max_results}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: current-metrics\n      path: /metrics/current/{InstanceId}\n      description: Real-time metrics\n      operations:\n      - name: get-current-metric-data\n        method: POST\n        description: Get real-time metric data from\
  \ an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n          data:\n            Filters: '{{tools.filters}}'\n            CurrentMetrics: '{{tools.current_metrics}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: historical-metrics\n      path: /metrics/historical/{InstanceId}\n      description: Historical metrics\n      operations:\n      - name: get-metric-data\n        method: POST\n        description: Get historical metric data from an Amazon Connect instance\n        inputParameters:\n        - name: InstanceId\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Amazon Connect instance\n        body:\n          type: json\n\
  \          data:\n            StartTime: '{{tools.start_time}}'\n            EndTime: '{{tools.end_time}}'\n            Filters: '{{tools.filters}}'\n            HistoricalMetrics: '{{tools.historical_metrics}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-chat\n      path: /contact/chat\n      description: Start chat contacts\n      operations:\n      - name: start-chat-contact\n        method: POST\n        description: Start a chat contact with a customer\n        body:\n          type: json\n          data:\n            InstanceId: '{{tools.instance_id}}'\n            ContactFlowId: '{{tools.contact_flow_id}}'\n            ParticipantDetails: '{{tools.participant_details}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: start-voice\n      path: /contact/outbound-voice\n      description: Start\
  \ outbound voice contacts\n      operations:\n      - name: start-outbound-voice-contact\n        method: POST\n        description: Place an outbound call to a contact\n        body:\n          type: json\n          data:\n            InstanceId: '{{tools.instance_id}}'\n            ContactFlowId: '{{tools.contact_flow_id}}'\n            DestinationPhoneNumber: '{{tools.destination_phone_number}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: contact-center-api\n    description: Unified REST API for Amazon Connect contact center operations.\n    resources:\n    - path: /v1/instances\n      name: instances\n      description: Amazon Connect instance management\n      operations:\n      - method: GET\n        name: list-instances\n        description: List all Amazon Connect instances\n        call: connect.list-instances\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-instance\n        description: Create a new Amazon Connect instance\n        call: connect.create-instance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}\n      name: instance\n      description: Single instance operations\n      operations:\n      - method: GET\n        name: describe-instance\n        description: Get details of an Amazon Connect instance\n        call: connect.describe-instance\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/agents\n      name: agents\n      description: Agent/user management\n      operations:\n      - method: GET\n        name: list-agents\n        description: List agents in an Amazon Connect instance\n        call: connect.list-users\n        with:\n          InstanceId:\
  \ rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-agent\n        description: Create a new agent in an Amazon Connect instance\n        call: connect.create-user\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/agents/{agent-id}\n      name: agent\n      description: Individual agent operations\n      operations:\n      - method: GET\n        name: get-agent\n        description: Get details of a specific agent\n        call: connect.describe-user\n        with:\n          InstanceId: rest.instance-id\n          UserId: rest.agent-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/queues\n      name: queues\n      description: Queue management\n      operations:\n      - method: GET\n        name: list-queues\n    \
  \    description: List queues in an Amazon Connect instance\n        call: connect.list-queues\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-queue\n        description: Create a new queue in an Amazon Connect instance\n        call: connect.create-queue\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/routing-profiles\n      name: routing-profiles\n      description: Routing profile management\n      operations:\n      - method: GET\n        name: list-routing-profiles\n        description: List routing profiles in an Amazon Connect instance\n        call: connect.list-routing-profiles\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/contact-flows\n\
  \      name: contact-flows\n      description: Contact flow management\n      operations:\n      - method: GET\n        name: list-contact-flows\n        description: List contact flows in an Amazon Connect instance\n        call: connect.list-contact-flows\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contacts/search\n      name: contact-search\n      description: Contact search\n      operations:\n      - method: POST\n        name: search-contacts\n        description: Search contacts in an Amazon Connect instance\n        call: connect.search-contacts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/metrics/current\n      name: current-metrics\n      description: Real-time metrics\n      operations:\n      - method: POST\n        name: get-current-metrics\n        description: Get real-time metrics for queues and agents\n\
  \        call: connect.get-current-metric-data\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/instances/{instance-id}/metrics/historical\n      name: historical-metrics\n      description: Historical metrics\n      operations:\n      - method: POST\n        name: get-historical-metrics\n        description: Get historical metrics for an Amazon Connect instance\n        call: connect.get-metric-data\n        with:\n          InstanceId: rest.instance-id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: contact-center-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Connect contact center management and monitoring.\n    tools:\n    - name: list-instances\n      description: List all Amazon Connect contact center instances in the AWS account\n      hints:\n        readOnly: true\n        openWorld:\
  \ true\n      call: connect.list-instances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-instance\n      description: Get details and status of a specific Amazon Connect instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.describe-instance\n      with:\n        InstanceId: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-agents\n      description: List all agents/users in an Amazon Connect instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.list-users\n      with:\n        InstanceId: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-agent\n      description: Get details of a specific agent including their routing profile and security profile\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.describe-user\n      with:\n  \
  \      InstanceId: tools.instance_id\n        UserId: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-queues\n      description: List all queues configured in an Amazon Connect instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.list-queues\n      with:\n        InstanceId: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-routing-profiles\n      description: List all routing profiles configured in an Amazon Connect instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.list-routing-profiles\n      with:\n        InstanceId: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contact-flows\n      description: List all contact flows in an Amazon Connect instance\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.list-contact-flows\n\
  \      with:\n        InstanceId: tools.instance_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-current-metrics\n      description: Get real-time metrics showing agents online, contacts in queue, and queue health\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.get-current-metric-data\n      with:\n        InstanceId: tools.instance_id\n        Filters: tools.filters\n        CurrentMetrics: tools.current_metrics\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-historical-metrics\n      description: Get historical metrics for contacts handled, handle time, abandon rate, and service level\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.get-metric-data\n      with:\n        InstanceId: tools.instance_id\n        StartTime: tools.start_time\n        EndTime: tools.end_time\n        Filters: tools.filters\n        HistoricalMetrics: tools.historical_metrics\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-contacts\n      description: Search for past contacts by time range, agent, queue, or channel\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.search-contacts\n      with:\n        InstanceId: tools.instance_id\n        TimeRange: tools.time_range\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-contact\n      description: Get full details of a specific contact interaction\n      hints:\n        readOnly: true\n        openWorld: true\n      call: connect.describe-contact\n      with:\n        InstanceId: tools.instance_id\n        ContactId: tools.contact_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-outbound-voice-contact\n      description: Place an outbound call from the contact center to a customer phone number\n      hints:\n        readOnly: false\n        openWorld: false\n\
  \      call: connect.start-outbound-voice-contact\n      with:\n        InstanceId: tools.instance_id\n        ContactFlowId: tools.contact_flow_id\n        DestinationPhoneNumber: tools.destination_phone_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-chat-contact\n      description: Initiate a chat contact session with a customer\n      hints:\n        readOnly: false\n        openWorld: false\n      call: connect.start-chat-contact\n      with:\n        InstanceId: tools.instance_id\n        ContactFlowId: tools.contact_flow_id\n        ParticipantDetails: tools.participant_details\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
