---
categories: []
consumed_apis: []
description: Workflow capability for automotive connected cockpit applications built on the Visteon Phoenix platform. Combines audio, phone, media, navigation, vehicle data, and screen management APIs into a unified interface for in-vehicle infotainment experience. Used by automotive app developers and OEM integration teams to build context-aware, multi-domain cockpit applications.
layout: capability
name: Visteon Connected Cockpit
operations:
- description: Get current vehicle speed, fuel, odometer, and HVAC data
  method: GET
  name: get-vehicle-data
  path: /v1/vehicle/data
- description: Get current audio playback status
  method: GET
  name: get-audio-status
  path: /v1/audio/status
- description: Get current volume level
  method: GET
  name: get-volume
  path: /v1/audio/volume
- description: Set master volume level
  method: PUT
  name: set-volume
  path: /v1/audio/volume
- description: List all available audio input sources
  method: GET
  name: list-audio-sources
  path: /v1/audio/sources
- description: Get Bluetooth phone connection and call status
  method: GET
  name: get-phone-status
  path: /v1/phone/status
- description: List active phone calls
  method: GET
  name: list-calls
  path: /v1/phone/calls
- description: Initiate an outgoing phone call
  method: POST
  name: make-call
  path: /v1/phone/calls
- description: Browse media library from connected devices
  method: GET
  name: browse-media-library
  path: /v1/media/library
- description: Get currently playing media track
  method: GET
  name: get-now-playing
  path: /v1/media/now-playing
- description: Get active navigation route with ETA
  method: GET
  name: get-active-route
  path: /v1/navigation/route
- description: Start navigation to a destination
  method: POST
  name: start-navigation
  path: /v1/navigation/route
- description: Cancel the active navigation route
  method: DELETE
  name: cancel-navigation
  path: /v1/navigation/route
- description: Search points of interest near vehicle
  method: GET
  name: search-poi
  path: /v1/navigation/search
- description: List all cockpit display screens
  method: GET
  name: list-displays
  path: /v1/screen/displays
personas: []
provider_name: Visteon
provider_slug: visteon
search_terms:
- volume control
- search poi
- vehicle telemetry and status
- get the active navigation route with eta and remaining distance
- get current audio system playback status and active source
- get currently playing media track
- cockpit display management
- connected car
- set master volume level
- get current vehicle speed, fuel, odometer, and hvac data
- get current audio playback status
- hmi
- phone call management
- cancel the active navigation route
- list active and on-hold phone calls
- navigation
- media content library
- list active phone calls
- get now playing
- navigation route management
- get active route
- list audio sources
- list all available audio input sources
- audio system state
- get active navigation route with eta
- set the master audio volume level
- initiate an outgoing phone call from the vehicle
- get bluetooth phone connection and call status
- list all available audio input sources (fm, am, bluetooth, usb, aux)
- get real-time vehicle telemetry including speed, fuel level, odometer, and hvac settings
- browse music, video, and photo media from connected devices
- iot
- audio
- vehicle data
- currently playing media
- get vehicle data
- browse media library
- automotive
- get bluetooth phone connection status and active call information
- make call
- list displays
- get current volume level and mute state
- get volume
- get phone status
- browse media library from connected devices
- list all cockpit display screens
- search points of interest near vehicle
- cancel the currently active navigation route
- infotainment
- list calls
- search for points of interest near the vehicle location
- available audio sources
- set volume
- cancel navigation
- list all cockpit display screens and their configuration
- get current volume level
- initiate an outgoing phone call
- start navigation
- get currently playing media track with artist, album, and duration
- start navigation to a destination
- visteon
- points of interest search
- get audio status
- start turn-by-turn navigation to a specified destination
- phone connection status
slug: connected-cockpit
source_filename: connected-cockpit.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Visteon Connected Cockpit\n  description: Workflow capability for automotive connected cockpit applications built on the Visteon Phoenix platform. Combines\n    audio, phone, media, navigation, vehicle data, and screen management APIs into a unified interface for in-vehicle infotainment\n    experience. Used by automotive app developers and OEM integration teams to build context-aware, multi-domain cockpit applications.\n  tags:\n  - Audio\n  - Automotive\n  - Connected Car\n  - HMI\n  - Infotainment\n  - Navigation\n  - Vehicle Data\n  - Visteon\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    VISTEON_PHOENIX_API_KEY: VISTEON_PHOENIX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: visteon-phoenix\n    baseUri: https://developer.visteon.com/phoenix/api\n    description: Visteon Phoenix automotive infotainment API\n    authentication:\n      type: apikey\n      key: X-Phoenix-API-Key\n\
  \      value: '{{VISTEON_PHOENIX_API_KEY}}'\n      placement: header\n    resources:\n    - name: audio\n      path: /audio/status\n      description: Audio system status\n      operations:\n      - name: get-audio-status\n        method: GET\n        description: Get current audio system status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: volume\n      path: /audio/volume\n      description: Volume control\n      operations:\n      - name: get-volume\n        method: GET\n        description: Get current volume level\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: set-volume\n        method: PUT\n        description: Set master volume level\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n\
  \          data:\n            level: '{{tools.level}}'\n            mute: '{{tools.mute}}'\n    - name: audio-sources\n      path: /audio/sources\n      description: Audio source management\n      operations:\n      - name: list-audio-sources\n        method: GET\n        description: List all available audio sources\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: phone\n      path: /phone/status\n      description: Phone connection status\n      operations:\n      - name: get-phone-status\n        method: GET\n        description: Get phone connection and call status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: calls\n      path: /phone/calls\n      description: Phone call management\n      operations:\n      - name: list-calls\n        method: GET\n        description: List active phone calls\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: make-call\n        method: POST\n        description: Initiate an outgoing call\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            number: '{{tools.number}}'\n    - name: media\n      path: /media/library\n      description: Media library browsing\n      operations:\n      - name: browse-media-library\n        method: GET\n        description: Browse the media library\n        inputParameters:\n        - name: type\n          in: query\n          type: string\n          required: false\n          description: Filter by media type\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: limit\n          in: query\n\
  \          type: integer\n          required: false\n          description: Items per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: now-playing\n      path: /media/nowplaying\n      description: Currently playing media\n      operations:\n      - name: get-now-playing\n        method: GET\n        description: Get currently playing track\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: navigation\n      path: /navigation/route\n      description: Navigation route management\n      operations:\n      - name: get-active-route\n        method: GET\n        description: Get the active navigation route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-navigation\n        method: POST\n        description: Start\
  \ navigation to a destination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            destination: '{{tools.destination}}'\n            avoidTolls: '{{tools.avoidTolls}}'\n      - name: cancel-navigation\n        method: DELETE\n        description: Cancel the active navigation route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: poi-search\n      path: /navigation/search\n      description: Points of interest search\n      operations:\n      - name: search-poi\n        method: GET\n        description: Search for points of interest\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: lat\n          in: query\n          type: number\n     \
  \     required: false\n          description: Search latitude\n        - name: lon\n          in: query\n          type: number\n          required: false\n          description: Search longitude\n        - name: radius\n          in: query\n          type: integer\n          required: false\n          description: Search radius in meters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicle-data\n      path: /vehicle/data\n      description: Vehicle telemetry data\n      operations:\n      - name: get-vehicle-data\n        method: GET\n        description: Get current vehicle telemetry data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: displays\n      path: /screen/displays\n      description: Display screen management\n      operations:\n      - name: list-displays\n        method: GET\n        description:\
  \ List all cockpit display screens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: visteon-cockpit-api\n    description: Unified REST API for Visteon connected cockpit applications.\n    resources:\n    - path: /v1/vehicle/data\n      name: vehicle-data\n      description: Vehicle telemetry and status\n      operations:\n      - method: GET\n        name: get-vehicle-data\n        description: Get current vehicle speed, fuel, odometer, and HVAC data\n        call: visteon-phoenix.get-vehicle-data\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audio/status\n      name: audio-status\n      description: Audio system state\n      operations:\n      - method: GET\n        name: get-audio-status\n        description: Get current audio playback status\n        call: visteon-phoenix.get-audio-status\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/audio/volume\n      name: volume\n      description: Volume control\n      operations:\n      - method: GET\n        name: get-volume\n        description: Get current volume level\n        call: visteon-phoenix.get-volume\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: set-volume\n        description: Set master volume level\n        call: visteon-phoenix.set-volume\n        with:\n          level: rest.level\n          mute: rest.mute\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/audio/sources\n      name: audio-sources\n      description: Available audio sources\n      operations:\n      - method: GET\n        name: list-audio-sources\n        description: List all available audio input sources\n        call: visteon-phoenix.list-audio-sources\n        outputParameters:\n        - type: object\n          mapping: $.\n\
  \    - path: /v1/phone/status\n      name: phone-status\n      description: Phone connection status\n      operations:\n      - method: GET\n        name: get-phone-status\n        description: Get Bluetooth phone connection and call status\n        call: visteon-phoenix.get-phone-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/phone/calls\n      name: calls\n      description: Phone call management\n      operations:\n      - method: GET\n        name: list-calls\n        description: List active phone calls\n        call: visteon-phoenix.list-calls\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: make-call\n        description: Initiate an outgoing phone call\n        call: visteon-phoenix.make-call\n        with:\n          number: rest.number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media/library\n      name: media-library\n\
  \      description: Media content library\n      operations:\n      - method: GET\n        name: browse-media-library\n        description: Browse media library from connected devices\n        call: visteon-phoenix.browse-media-library\n        with:\n          type: rest.type\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/media/now-playing\n      name: now-playing\n      description: Currently playing media\n      operations:\n      - method: GET\n        name: get-now-playing\n        description: Get currently playing media track\n        call: visteon-phoenix.get-now-playing\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/navigation/route\n      name: navigation-route\n      description: Navigation route management\n      operations:\n      - method: GET\n        name: get-active-route\n        description: Get active navigation route with\
  \ ETA\n        call: visteon-phoenix.get-active-route\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-navigation\n        description: Start navigation to a destination\n        call: visteon-phoenix.start-navigation\n        with:\n          destination: rest.destination\n          avoidTolls: rest.avoidTolls\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: cancel-navigation\n        description: Cancel the active navigation route\n        call: visteon-phoenix.cancel-navigation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/navigation/search\n      name: poi-search\n      description: Points of interest search\n      operations:\n      - method: GET\n        name: search-poi\n        description: Search points of interest near vehicle\n        call: visteon-phoenix.search-poi\n        with:\n          query: rest.query\n\
  \          lat: rest.lat\n          lon: rest.lon\n          radius: rest.radius\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screen/displays\n      name: displays\n      description: Cockpit display management\n      operations:\n      - method: GET\n        name: list-displays\n        description: List all cockpit display screens\n        call: visteon-phoenix.list-displays\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: visteon-cockpit-mcp\n    transport: http\n    description: MCP server for AI-assisted automotive cockpit control and telemetry.\n    tools:\n    - name: get-vehicle-data\n      description: Get real-time vehicle telemetry including speed, fuel level, odometer, and HVAC settings\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-vehicle-data\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-audio-status\n      description: Get current audio system playback status and active source\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-audio-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-volume\n      description: Get current volume level and mute state\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-volume\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-volume\n      description: Set the master audio volume level\n      hints:\n        readOnly: false\n        idempotent: true\n      call: visteon-phoenix.set-volume\n      with:\n        level: tools.level\n        mute: tools.mute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-audio-sources\n      description: List all available audio input sources (FM, AM, Bluetooth, USB, aux)\n      hints:\n\
  \        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.list-audio-sources\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-phone-status\n      description: Get Bluetooth phone connection status and active call information\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-phone-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-calls\n      description: List active and on-hold phone calls\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.list-calls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: make-call\n      description: Initiate an outgoing phone call from the vehicle\n      hints:\n        readOnly: false\n        idempotent: false\n      call: visteon-phoenix.make-call\n      with:\n        number: tools.number\n      outputParameters:\n      - type: object\n\
  \        mapping: $.\n    - name: browse-media-library\n      description: Browse music, video, and photo media from connected devices\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.browse-media-library\n      with:\n        type: tools.type\n        offset: tools.offset\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-now-playing\n      description: Get currently playing media track with artist, album, and duration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-now-playing\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-active-route\n      description: Get the active navigation route with ETA and remaining distance\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.get-active-route\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: start-navigation\n      description: Start turn-by-turn navigation to a specified destination\n      hints:\n        readOnly: false\n        idempotent: false\n      call: visteon-phoenix.start-navigation\n      with:\n        destination: tools.destination\n        avoidTolls: tools.avoidTolls\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancel-navigation\n      description: Cancel the currently active navigation route\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: visteon-phoenix.cancel-navigation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-poi\n      description: Search for points of interest near the vehicle location\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.search-poi\n      with:\n        query: tools.query\n        lat: tools.lat\n        lon: tools.lon\n        radius: tools.radius\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-displays\n      description: List all cockpit display screens and their configuration\n      hints:\n        readOnly: true\n        idempotent: true\n      call: visteon-phoenix.list-displays\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/visteon/refs/heads/main/capabilities/connected-cockpit.yaml
tags:
- Audio
- Automotive
- Connected Car
- HMI
- Infotainment
- Navigation
- Vehicle Data
- Visteon
tools:
- description: Get real-time vehicle telemetry including speed, fuel level, odometer, and HVAC settings
  hints:
    idempotent: true
    readOnly: true
  name: get-vehicle-data
- description: Get current audio system playback status and active source
  hints:
    idempotent: true
    readOnly: true
  name: get-audio-status
- description: Get current volume level and mute state
  hints:
    idempotent: true
    readOnly: true
  name: get-volume
- description: Set the master audio volume level
  hints:
    idempotent: true
    readOnly: false
  name: set-volume
- description: List all available audio input sources (FM, AM, Bluetooth, USB, aux)
  hints:
    idempotent: true
    readOnly: true
  name: list-audio-sources
- description: Get Bluetooth phone connection status and active call information
  hints:
    idempotent: true
    readOnly: true
  name: get-phone-status
- description: List active and on-hold phone calls
  hints:
    idempotent: true
    readOnly: true
  name: list-calls
- description: Initiate an outgoing phone call from the vehicle
  hints:
    idempotent: false
    readOnly: false
  name: make-call
- description: Browse music, video, and photo media from connected devices
  hints:
    idempotent: true
    readOnly: true
  name: browse-media-library
- description: Get currently playing media track with artist, album, and duration
  hints:
    idempotent: true
    readOnly: true
  name: get-now-playing
- description: Get the active navigation route with ETA and remaining distance
  hints:
    idempotent: true
    readOnly: true
  name: get-active-route
- description: Start turn-by-turn navigation to a specified destination
  hints:
    idempotent: false
    readOnly: false
  name: start-navigation
- description: Cancel the currently active navigation route
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: cancel-navigation
- description: Search for points of interest near the vehicle location
  hints:
    idempotent: true
    readOnly: true
  name: search-poi
- description: List all cockpit display screens and their configuration
  hints:
    idempotent: true
    readOnly: true
  name: list-displays
---
