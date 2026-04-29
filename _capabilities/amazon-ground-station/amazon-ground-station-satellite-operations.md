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
- list all satellites that can be tracked through aws ground station
- list satellite contacts
- list ground stations
- satellite communications
- schedule a satellite contact
- list contacts
- mission control
- schedule a new satellite contact window at an aws ground station
- get detailed information about a specific satellite contact
- describe contact
- list all available aws ground station antenna locations worldwide
- aws
- cancel satellite contact
- create a dataflow endpoint group for satellite data delivery
- space technology
- schedules and manages satellite contacts and data downlinks
- list all configured satellite mission profiles
- list available ground stations
- list all mission profiles
- reserve satellite contact
- satellite operations
- create dataflow endpoint group
- list ground station locations
- iot
- configures mission profiles and dataflow infrastructure
- Satellite Operator
- satellite tracking information
- list satellites
- list all satellite contacts
- amazon ground station
- data processing
- create a new mission profile
- list trackable satellites
- reserve contact
- cancel a previously scheduled satellite contact
- list all dataflow endpoint and antenna configurations
- satellite mission profiles
- list mission profiles
- list all scheduled and historical satellite contacts with status and timing
- create a new mission profile defining satellite operations parameters
- Mission Control Engineer
- satellite contact scheduling
- list configs
- ground station locations
- create mission profile
slug: amazon-ground-station-satellite-operations
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Ground Station Satellite Operations\n  description: >-\n    Workflow capability for satellite operators and mission control teams using\n    Amazon Ground Station. Covers contact scheduling, mission profile management,\n    satellite tracking, and dataflow configuration for satellite operations.\n  tags:\n    - Amazon Ground Station\n    - Satellite Operations\n    - Mission Control\n    - Space Technology\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-ground-station\n      location: ./shared/amazon-ground-station.yaml\n\n  exposes:\n    - type: rest\n      port: 8084\n      namespace: ground-station-ops-api\n      description: Unified REST API for Amazon Ground Station satellite operations.\n\
  \      resources:\n        - path: /v1/contacts\n          name: contacts\n          description: Satellite contact scheduling\n          operations:\n            - method: GET\n              name: list-contacts\n              description: List all satellite contacts\n              call: amazon-ground-station.ListContacts\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: reserve-contact\n              description: Schedule a satellite contact\n              call: amazon-ground-station.ReserveContact\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/satellites\n          name: satellites\n          description: Satellite tracking information\n          operations:\n            - method: GET\n              name: list-satellites\n              description: List trackable satellites\n              call: amazon-ground-station.ListSatellites\n\
  \              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/ground-stations\n          name: ground-stations\n          description: Ground station locations\n          operations:\n            - method: GET\n              name: list-ground-stations\n              description: List available ground stations\n              call: amazon-ground-station.ListGroundStations\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/mission-profiles\n          name: mission-profiles\n          description: Satellite mission profiles\n          operations:\n            - method: GET\n              name: list-mission-profiles\n              description: List all mission profiles\n              call: amazon-ground-station.ListMissionProfiles\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n     \
  \         name: create-mission-profile\n              description: Create a new mission profile\n              call: amazon-ground-station.CreateMissionProfile\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9094\n      namespace: ground-station-ops-mcp\n      transport: http\n      description: MCP server for AI-assisted Amazon Ground Station satellite operations.\n      tools:\n        - name: list-satellite-contacts\n          description: List all scheduled and historical satellite contacts with status and timing\n          hints:\n            readOnly: true\n            openWorld: true\n          call: amazon-ground-station.ListContacts\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: reserve-satellite-contact\n          description: Schedule a new satellite contact window at an AWS ground station\n          hints:\n            readOnly: false\n\
  \          call: amazon-ground-station.ReserveContact\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: cancel-satellite-contact\n          description: Cancel a previously scheduled satellite contact\n          hints:\n            readOnly: false\n            destructive: true\n          call: amazon-ground-station.CancelContact\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-contact\n          description: Get detailed information about a specific satellite contact\n          hints:\n            readOnly: true\n          call: amazon-ground-station.DescribeContact\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-trackable-satellites\n          description: List all satellites that can be tracked through AWS Ground Station\n          hints:\n            readOnly: true\n          call: amazon-ground-station.ListSatellites\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-ground-station-locations\n          description: List all available AWS Ground Station antenna locations worldwide\n          hints:\n            readOnly: true\n          call: amazon-ground-station.ListGroundStations\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-mission-profiles\n          description: List all configured satellite mission profiles\n          hints:\n            readOnly: true\n          call: amazon-ground-station.ListMissionProfiles\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-mission-profile\n          description: Create a new mission profile defining satellite operations parameters\n          hints:\n            readOnly: false\n          call: amazon-ground-station.CreateMissionProfile\n          outputParameters:\n        \
  \    - type: object\n              mapping: \"$.\"\n        - name: list-configs\n          description: List all dataflow endpoint and antenna configurations\n          hints:\n            readOnly: true\n          call: amazon-ground-station.ListConfigs\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dataflow-endpoint-group\n          description: Create a dataflow endpoint group for satellite data delivery\n          hints:\n            readOnly: false\n          call: amazon-ground-station.CreateDataflowEndpointGroup\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ground-station/refs/heads/main/capabilities/amazon-ground-station-satellite-operations.yaml
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
