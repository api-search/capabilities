---
categories: []
consumed_apis:
- amazon-ground-station
description: Workflow capability for satellite operators and mission control teams using Amazon Ground Station. Covers contact scheduling, mission profile management, satellite tracking, and dataflow configuration for satellite operations.
layout: capability
name: Amazon Ground Station Satellite Operations
operations:
- description: List all satellite contacts
  method: GET
  name: list-contacts
  path: /v1/contacts
- description: Schedule a satellite contact
  method: POST
  name: reserve-contact
  path: /v1/contacts
- description: List trackable satellites
  method: GET
  name: list-satellites
  path: /v1/satellites
- description: List available ground stations
  method: GET
  name: list-ground-stations
  path: /v1/ground-stations
- description: List all mission profiles
  method: GET
  name: list-mission-profiles
  path: /v1/mission-profiles
- description: Create a new mission profile
  method: POST
  name: create-mission-profile
  path: /v1/mission-profiles
personas: []
provider_name: Amazon Ground Station
provider_slug: amazon-ground-station
search_terms:
- Mission Control Engineer
- list satellite contacts
- reserve satellite contact
- list all mission profiles
- ground station locations
- Satellite Operator
- iot
- schedule a satellite contact
- space technology
- schedule a new satellite contact window at an aws ground station
- list all satellite contacts
- cancel a previously scheduled satellite contact
- list all satellites that can be tracked through aws ground station
- configures mission profiles and dataflow infrastructure
- create a dataflow endpoint group for satellite data delivery
- mission control
- list contacts
- list mission profiles
- data processing
- list configs
- schedules and manages satellite contacts and data downlinks
- list all available aws ground station antenna locations worldwide
- list all scheduled and historical satellite contacts with status and timing
- list all dataflow endpoint and antenna configurations
- create dataflow endpoint group
- list ground stations
- create a new mission profile defining satellite operations parameters
- satellite contact scheduling
- list trackable satellites
- list all configured satellite mission profiles
- amazon ground station
- describe contact
- cancel satellite contact
- aws
- list ground station locations
- satellite communications
- create mission profile
- satellite operations
- satellite tracking information
- create a new mission profile
- list satellites
- get detailed information about a specific satellite contact
- reserve contact
- list available ground stations
- satellite mission profiles
slug: amazon-ground-station-satellite-operations
tags:
- Amazon Ground Station
- Satellite Operations
- Mission Control
- Space Technology
- AWS
tools:
- description: List all scheduled and historical satellite contacts with status and timing
  hints:
    openWorld: true
    readOnly: true
  name: list-satellite-contacts
- description: Schedule a new satellite contact window at an AWS ground station
  hints:
    readOnly: false
  name: reserve-satellite-contact
- description: Cancel a previously scheduled satellite contact
  hints:
    destructive: true
    readOnly: false
  name: cancel-satellite-contact
- description: Get detailed information about a specific satellite contact
  hints:
    readOnly: true
  name: describe-contact
- description: List all satellites that can be tracked through AWS Ground Station
  hints:
    readOnly: true
  name: list-trackable-satellites
- description: List all available AWS Ground Station antenna locations worldwide
  hints:
    readOnly: true
  name: list-ground-station-locations
- description: List all configured satellite mission profiles
  hints:
    readOnly: true
  name: list-mission-profiles
- description: Create a new mission profile defining satellite operations parameters
  hints:
    readOnly: false
  name: create-mission-profile
- description: List all dataflow endpoint and antenna configurations
  hints:
    readOnly: true
  name: list-configs
- description: Create a dataflow endpoint group for satellite data delivery
  hints:
    readOnly: false
  name: create-dataflow-endpoint-group
---
