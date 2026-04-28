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
- start outbound voice contact
- create agent
- real-time and historical performance metrics and reporting
- get historical metrics for contacts handled, handle time, abandon rate, and service level
- start chat contact
- list routing profiles in an amazon connect instance
- get real-time metrics showing agents online, contacts in queue, and queue health
- Contact Center Supervisor
- list all agents/users in an amazon connect instance
- place an outbound call from the contact center to a customer phone number
- routing profile management
- amazon connect
- amazon connect instance management
- search contacts in an amazon connect instance
- list instances
- contact search
- contact center
- unified workflow for managing and monitoring the amazon connect contact center, combining instance administration, agent management, queue configuration, and real-time/historical metrics.
- aws
- single instance operations
- get details and status of a specific amazon connect instance
- get details of an amazon connect instance
- Contact Center Administrator
- queue management
- list agents
- list all queues configured in an amazon connect instance
- list queues
- list routing profiles
- search contacts
- get historical metrics for an amazon connect instance
- search for past contacts by time range, agent, queue, or channel
- operations
- ai
- responsible for configuring and managing the amazon connect instance, including users, queues, routing profiles, and contact flows.
- voice
- individual agent operations
- list queues in an amazon connect instance
- list agents in an amazon connect instance
- list all contact flows in an amazon connect instance
- initiate a chat contact session with a customer
- monitors agent activity, queue health, and contact center performance using real-time and historical metrics dashboards.
- list all amazon connect instances
- configuration and lifecycle management of amazon connect instances
- create a new amazon connect instance
- list all routing profiles configured in an amazon connect instance
- customer service
- initiation, management, and search of contact interactions
- metrics
- create a new queue in an amazon connect instance
- Operations Team
- describe contact
- get historical metrics
- describe instance
- queue, routing profile, and contact flow configuration for intelligent routing
- create instance
- create queue
- agent/user management
- contact flow management
- manages day-to-day contact center operations including agent status, contact handling, and performance reporting.
- omnichannel
- user/agent account management and workforce administration
- list all amazon connect contact center instances in the aws account
- get details of a specific agent including their routing profile and security profile
- real-time metrics
- historical metrics
- get real-time metrics for queues and agents
- get full details of a specific contact interaction
- chat
- get details of a specific agent
- get current metrics
- create a new agent in an amazon connect instance
- get agent
- list contact flows
- list contact flows in an amazon connect instance
slug: contact-center-operations
tags:
- Amazon Connect
- Contact Center
- AWS
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
