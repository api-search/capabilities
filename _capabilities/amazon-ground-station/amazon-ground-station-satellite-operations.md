---
categories: []
consumed_apis: []
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
- list satellites
- create mission profile
- satellite contact scheduling
- amazon ground station
- space technology
- schedule a new satellite contact window at an aws ground station
- cancel satellite contact
- satellite tracking information
- satellite operations
- schedules and manages satellite contacts and data downlinks
- configures mission profiles and dataflow infrastructure
- list ground station locations
- cancel a previously scheduled satellite contact
- list available ground stations
- list all configured satellite mission profiles
- list all mission profiles
- create a new mission profile
- reserve satellite contact
- schedule a satellite contact
- list all scheduled and historical satellite contacts with status and timing
- get detailed information about a specific satellite contact
- list satellite contacts
- create a new mission profile defining satellite operations parameters
- list trackable satellites
- satellite communications
- list all satellites that can be tracked through aws ground station
- data processing
- create a dataflow endpoint group for satellite data delivery
- list all satellite contacts
- list all available aws ground station antenna locations worldwide
- list contacts
- iot
- Satellite Operator
- describe contact
- mission control
- Mission Control Engineer
- ground station locations
- list mission profiles
- list ground stations
- aws
- reserve contact
- satellite mission profiles
- list configs
- list all dataflow endpoint and antenna configurations
- create dataflow endpoint group
slug: amazon-ground-station-satellite-operations
source_filename: amazon-ground-station-satellite-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Ground Station Satellite Operations\n  description: Workflow capability for satellite operators and mission control teams using Amazon Ground Station. Covers contact\n    scheduling, mission profile management, satellite tracking, and dataflow configuration for satellite operations.\n  tags:\n  - Amazon Ground Station\n  - Satellite Operations\n  - Mission Control\n  - Space Technology\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-ground-station\n    baseUri: https://groundstation.amazonaws.com\n    description: Amazon Ground Station API\n    authentication:\n      type: bearer\n      token: '{{AWS_AUTH_HEADER}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      description: Satellite\
  \ contact management\n      operations:\n      - name: ListContacts\n        method: GET\n        description: List all satellite contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: ReserveContact\n        method: POST\n        description: Schedule a satellite contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CancelContact\n        method: DELETE\n        description: Cancel a scheduled contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeContact\n        method: GET\n        description: Get contact details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mission-profiles\n      path: /missionprofile\n\
  \      description: Mission profile management\n      operations:\n      - name: ListMissionProfiles\n        method: GET\n        description: List all mission profiles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateMissionProfile\n        method: POST\n        description: Create a mission profile\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: satellites\n      path: /satellite\n      description: Satellite tracking information\n      operations:\n      - name: ListSatellites\n        method: GET\n        description: List trackable satellites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ground-stations\n      path: /groundstation\n      description: Ground station location management\n      operations:\n\
  \      - name: ListGroundStations\n        method: GET\n        description: List all ground stations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8084\n    namespace: ground-station-ops-api\n    description: Unified REST API for Amazon Ground Station satellite operations.\n    resources:\n    - path: /v1/contacts\n      name: contacts\n      description: Satellite contact scheduling\n      operations:\n      - method: GET\n        name: list-contacts\n        description: List all satellite contacts\n        call: amazon-ground-station.ListContacts\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: reserve-contact\n        description: Schedule a satellite contact\n        call: amazon-ground-station.ReserveContact\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/satellites\n\
  \      name: satellites\n      description: Satellite tracking information\n      operations:\n      - method: GET\n        name: list-satellites\n        description: List trackable satellites\n        call: amazon-ground-station.ListSatellites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ground-stations\n      name: ground-stations\n      description: Ground station locations\n      operations:\n      - method: GET\n        name: list-ground-stations\n        description: List available ground stations\n        call: amazon-ground-station.ListGroundStations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/mission-profiles\n      name: mission-profiles\n      description: Satellite mission profiles\n      operations:\n      - method: GET\n        name: list-mission-profiles\n        description: List all mission profiles\n        call: amazon-ground-station.ListMissionProfiles\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n      - method: POST\n        name: create-mission-profile\n        description: Create a new mission profile\n        call: amazon-ground-station.CreateMissionProfile\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9094\n    namespace: ground-station-ops-mcp\n    transport: http\n    description: MCP server for AI-assisted Amazon Ground Station satellite operations.\n    tools:\n    - name: list-satellite-contacts\n      description: List all scheduled and historical satellite contacts with status and timing\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-ground-station.ListContacts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reserve-satellite-contact\n      description: Schedule a new satellite contact window at an AWS ground station\n      hints:\n        readOnly: false\n      call: amazon-ground-station.ReserveContact\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-satellite-contact\n      description: Cancel a previously scheduled satellite contact\n      hints:\n        readOnly: false\n        destructive: true\n      call: amazon-ground-station.CancelContact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-contact\n      description: Get detailed information about a specific satellite contact\n      hints:\n        readOnly: true\n      call: amazon-ground-station.DescribeContact\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-trackable-satellites\n      description: List all satellites that can be tracked through AWS Ground Station\n      hints:\n        readOnly: true\n      call: amazon-ground-station.ListSatellites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-ground-station-locations\n      description: List all available AWS Ground Station\
  \ antenna locations worldwide\n      hints:\n        readOnly: true\n      call: amazon-ground-station.ListGroundStations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-mission-profiles\n      description: List all configured satellite mission profiles\n      hints:\n        readOnly: true\n      call: amazon-ground-station.ListMissionProfiles\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-mission-profile\n      description: Create a new mission profile defining satellite operations parameters\n      hints:\n        readOnly: false\n      call: amazon-ground-station.CreateMissionProfile\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-configs\n      description: List all dataflow endpoint and antenna configurations\n      hints:\n        readOnly: true\n      call: amazon-ground-station.ListConfigs\n      outputParameters:\n      - type: object\n        mapping: $.\n   \
  \ - name: create-dataflow-endpoint-group\n      description: Create a dataflow endpoint group for satellite data delivery\n      hints:\n        readOnly: false\n      call: amazon-ground-station.CreateDataflowEndpointGroup\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-ground-station/refs/heads/main/capabilities/amazon-ground-station-satellite-operations.yaml
tags:
- Amazon Ground Station
- Satellite Operations
- Mission Control
- Space Technology
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
