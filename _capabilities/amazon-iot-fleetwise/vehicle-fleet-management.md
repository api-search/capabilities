---
categories:
- iot
consumed_apis: []
description: Unified capability for Automotive Engineer, IoT Developer to manage collect, transform, and transfer vehicle data to the cloud operations.
layout: capability
name: Amazon IoT FleetWise - Vehicle Fleet Management
operations:
- description: List Vehicles
  method: GET
  name: list-vehicles
  path: /v1/resources
personas: []
provider_name: Amazon IoT FleetWise
provider_slug: amazon-iot-fleetwise
search_terms:
- amazon iot fleetwise list fleets
- collect, transform, and transfer vehicle data to the cloud.
- aws
- amazon iot fleetwise create signal catalog
- telematics
- amazon iot fleetwise create fleet
- amazon iot fleetwise list vehicles
- create signal catalog
- list fleets
- connected vehicles
- iot
- amazon iot fleetwise create campaign
- vehicle data
- manages amazon iot fleetwise resources and operations
- amazon iot fleetwise list signal catalogs
- IoT Developer
- list campaigns
- automotive
- vehicle telematics
- amazon iot fleetwise create vehicle
- Automotive Engineer
- list signal catalogs
- create vehicle
- amazon iot fleetwise list campaigns
- list vehicles
- create fleet
- create campaign
- amazon iot fleetwise resources
slug: vehicle-fleet-management
source_filename: vehicle-fleet-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon IoT FleetWise - Vehicle Fleet Management\n  description: Unified capability for Automotive Engineer, IoT Developer to manage collect, transform, and transfer vehicle\n    data to the cloud operations.\n  tags:\n  - IoT\n  - AWS\n  - Automotive\n  - Vehicle Telematics\n  - Connected Vehicles\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: iot-fleetwise\n    baseUri: https://iotfleetwise.amazonaws.com\n    description: Amazon IoT FleetWise REST API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n      placement: header\n    resources:\n    - name: resources\n      path: /\n      description: Amazon IoT FleetWise resources\n      operations:\n      - name: list-vehicles\n        method: GET\n\
  \        description: List Vehicles\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: vehicle-fleet-management-api\n    description: Unified REST API for vehicle fleet management.\n    resources:\n    - path: /v1/resources\n      name: resources\n      description: Amazon IoT FleetWise resources\n      operations:\n      - method: GET\n        name: list-vehicles\n        description: List Vehicles\n        call: iot-fleetwise.list-vehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: vehicle-fleet-management-mcp\n    transport: http\n    description: MCP server for AI-assisted vehicle fleet management.\n    tools:\n    - name: list-vehicles\n      description: Amazon IoT FleetWise List Vehicles\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iot-fleetwise.list-vehicles\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-vehicle\n      description: Amazon IoT FleetWise Create Vehicle\n      hints:\n        readOnly: false\n      call: iot-fleetwise.create-vehicle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-fleets\n      description: Amazon IoT FleetWise List Fleets\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iot-fleetwise.list-fleets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-fleet\n      description: Amazon IoT FleetWise Create Fleet\n      hints:\n        readOnly: false\n      call: iot-fleetwise.create-fleet\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-signal-catalogs\n      description: Amazon IoT FleetWise List Signal Catalogs\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iot-fleetwise.list-signal-catalogs\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-signal-catalog\n      description: Amazon IoT FleetWise Create Signal Catalog\n      hints:\n        readOnly: false\n      call: iot-fleetwise.create-signal-catalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-campaigns\n      description: Amazon IoT FleetWise List Campaigns\n      hints:\n        readOnly: true\n        openWorld: true\n      call: iot-fleetwise.list-campaigns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-campaign\n      description: Amazon IoT FleetWise Create Campaign\n      hints:\n        readOnly: false\n      call: iot-fleetwise.create-campaign\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-iot-fleetwise/refs/heads/main/capabilities/vehicle-fleet-management.yaml
tags:
- IoT
- Automotive
- Vehicle Telematics
- Connected Vehicles
tools:
- description: Amazon IoT FleetWise List Vehicles
  hints:
    openWorld: true
    readOnly: true
  name: list-vehicles
- description: Amazon IoT FleetWise Create Vehicle
  hints:
    readOnly: false
  name: create-vehicle
- description: Amazon IoT FleetWise List Fleets
  hints:
    openWorld: true
    readOnly: true
  name: list-fleets
- description: Amazon IoT FleetWise Create Fleet
  hints:
    readOnly: false
  name: create-fleet
- description: Amazon IoT FleetWise List Signal Catalogs
  hints:
    openWorld: true
    readOnly: true
  name: list-signal-catalogs
- description: Amazon IoT FleetWise Create Signal Catalog
  hints:
    readOnly: false
  name: create-signal-catalog
- description: Amazon IoT FleetWise List Campaigns
  hints:
    openWorld: true
    readOnly: true
  name: list-campaigns
- description: Amazon IoT FleetWise Create Campaign
  hints:
    readOnly: false
  name: create-campaign
---
