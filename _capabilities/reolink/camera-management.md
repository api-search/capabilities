---
categories: []
consumed_apis: []
description: Unified workflow for managing and monitoring Reolink IP cameras and NVRs. Combines device system management, PTZ control, recording search and playback, AI-powered object detection, motion alarm configuration, and LED/lighting control into a single interface for security operators, smart home integrators, and IoT automation platforms.
layout: capability
name: Reolink Camera Management
operations:
- description: Get camera device information and firmware details
  method: GET
  name: get-device-info
  path: /v1/device/info
- description: Get device date and time settings
  method: GET
  name: get-time
  path: /v1/device/time
- description: Set device date and time
  method: POST
  name: set-time
  path: /v1/device/time
- description: Get status of all camera channels
  method: GET
  name: get-channel-status
  path: /v1/device/channels
- description: Get hard drive storage information
  method: GET
  name: get-hdd-info
  path: /v1/device/storage
- description: Control camera pan, tilt, and zoom
  method: POST
  name: ptz-control
  path: /v1/ptz/control
- description: Get saved PTZ preset positions
  method: GET
  name: get-ptz-presets
  path: /v1/ptz/presets
- description: Get recording schedule and settings
  method: GET
  name: get-recording-settings
  path: /v1/recordings/settings
- description: Search recordings by date and time range
  method: POST
  name: search-recordings
  path: /v1/recordings/search
- description: Get motion detection configuration
  method: GET
  name: get-motion-alarm
  path: /v1/alarms/motion
- description: Configure motion detection settings
  method: POST
  name: set-motion-alarm
  path: /v1/alarms/motion
- description: Get current AI detection state (person, vehicle, animal)
  method: GET
  name: get-ai-state
  path: /v1/ai/state
- description: Capture a snapshot image from the camera
  method: POST
  name: capture-snapshot
  path: /v1/video/snapshot
- description: Get infrared LED settings
  method: GET
  name: get-ir-lights
  path: /v1/led/ir
- description: Configure infrared LED mode
  method: POST
  name: set-ir-lights
  path: /v1/led/ir
personas: []
provider_name: Reolink
provider_slug: reolink
search_terms:
- control camera pan, tilt, and zoom
- reboot the reolink camera or nvr device
- ptz
- get status of all camera channels
- storage drive information
- search recorded footage
- capture snapshots
- get storage drive capacity and status for the camera or nvr
- ptz move
- get infrared led settings
- ptz control
- get recording settings
- search camera recordings by date/time range and channel
- get infrared led settings for night vision on a camera channel
- set ir lights
- reboot camera
- configure motion detection settings
- get ai detection configuration and sensitivity settings for a channel
- get hard drive storage information
- security cameras
- set motion alarm
- surveillance
- search recordings by date and time range
- capture a jpeg snapshot from a specific camera channel
- get camera device information and firmware details
- set ai config
- get time
- get reolink camera device information including model, firmware, and hardware details
- search recordings
- configure ai object detection parameters (person/vehicle/animal sensitivity) for a channel
- configure infrared led mode
- get current ai detection state (person, vehicle, animal)
- set device date and time
- get recording schedule and configuration settings for a channel
- get ai config
- configure infrared led mode (auto/on/off) for night vision
- iot
- set time
- get ai state
- smart home
- get channel status
- get the online/offline status of all camera channels on the nvr
- get saved ptz preset positions for a camera channel
- configure motion detection sensitivity, zones, and schedule for a channel
- get motion detection configuration
- get device date and time settings
- ptz movement control
- motion detection alarm settings
- ptz preset positions
- get recording schedule and settings
- get ptz presets
- infrared led control
- get ir lights
- get motion detection alarm configuration for a camera channel
- get motion alarm
- device system information
- camera channel status
- recording configuration
- ai detection
- get hdd info
- get saved ptz preset positions
- capture a snapshot image from the camera
- get current ai object detection state (person, vehicle, animal) for a channel
- ai object detection state
- 'control ptz camera movement: pan left/right, tilt up/down, zoom in/out, or go to preset'
- device time configuration
- get device info
- capture snapshot
slug: camera-management
source_filename: camera-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Reolink Camera Management\n  description: Unified workflow for managing and monitoring Reolink IP cameras and NVRs. Combines device system management,\n    PTZ control, recording search and playback, AI-powered object detection, motion alarm configuration, and LED/lighting\n    control into a single interface for security operators, smart home integrators, and IoT automation platforms.\n  tags:\n  - IoT\n  - Security Cameras\n  - Surveillance\n  - Smart Home\n  - PTZ\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    REOLINK_USERNAME: REOLINK_USERNAME\n    REOLINK_PASSWORD: REOLINK_PASSWORD\n    REOLINK_CAMERA_IP: REOLINK_CAMERA_IP\ncapability:\n  consumes:\n  - type: http\n    namespace: reolink\n    baseUri: https://{REOLINK_CAMERA_IP}\n    description: Reolink camera local HTTP API\n    authentication:\n      type: apikey\n      key: token\n      value: '{{REOLINK_TOKEN}}'\n      placement: query\n\
  \    resources:\n    - name: authentication\n      path: /cgi-bin/api.cgi\n      description: Camera authentication and session management\n      operations:\n      - name: login\n        method: POST\n        description: Authenticate and obtain a session token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: Login\n            action: 0\n            param:\n              User:\n                userName: '{{REOLINK_USERNAME}}'\n                password: '{{REOLINK_PASSWORD}}'\n      - name: logout\n        method: POST\n        description: End session and invalidate token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system\n      path: /cgi-bin/api.cgi\n      description: Device information and system management\n      operations:\n      - name:\
  \ get-device-info\n        method: POST\n        description: Get device information including model and firmware version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetDevInfo\n            action: 0\n            param: {}\n      - name: get-time\n        method: POST\n        description: Get device date and time settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetTime\n            action: 0\n            param: {}\n      - name: set-time\n        method: POST\n        description: Set device date and time\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n        \
  \  data:\n            cmd: SetTime\n            action: 0\n            param: '{{tools.timeParam}}'\n      - name: reboot\n        method: POST\n        description: Reboot the camera device\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: Reboot\n            action: 0\n            param: {}\n      - name: get-hdd-info\n        method: POST\n        description: Get storage drive information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetHddInfo\n            action: 0\n            param: {}\n      - name: get-channel-status\n        method: POST\n        description: Get status of all camera channels\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n   \
  \       type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetChannelStatus\n            action: 0\n            param: {}\n    - name: ptz\n      path: /cgi-bin/api.cgi\n      description: Pan-tilt-zoom control and presets\n      operations:\n      - name: ptz-control\n        method: POST\n        description: Control PTZ movement (pan, tilt, zoom)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: PtzCtrl\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n              op: '{{tools.op}}'\n              speed: '{{tools.speed}}'\n      - name: get-ptz-presets\n        method: POST\n        description: Get configured PTZ preset positions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n        body:\n          type: json\n          data:\n            cmd: GetPtzPreset\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: set-ptz-preset\n        method: POST\n        description: Save current position as a named PTZ preset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: SetPtzPreset\n            action: 0\n            param: '{{tools.presetParam}}'\n    - name: recording\n      path: /cgi-bin/api.cgi\n      description: Recording configuration and search\n      operations:\n      - name: get-recording-settings\n        method: POST\n        description: Get recording schedule and settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n     \
  \     data:\n            cmd: GetRec\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: search-recordings\n        method: POST\n        description: Search recordings by date, time range, and channel\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: Search\n            action: 0\n            param:\n              Search:\n                channel: '{{tools.channel}}'\n                onlyStatus: 0\n                streamType: main\n                StartTime: '{{tools.startTime}}'\n                EndTime: '{{tools.endTime}}'\n    - name: alarm\n      path: /cgi-bin/api.cgi\n      description: Motion detection and alarm configuration\n      operations:\n      - name: get-motion-alarm\n        method: POST\n        description: Get motion detection alarm settings\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetMdAlarm\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: set-motion-alarm\n        method: POST\n        description: Configure motion detection alarm settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: SetMdAlarm\n            action: 0\n            param: '{{tools.alarmParam}}'\n    - name: ai-detection\n      path: /cgi-bin/api.cgi\n      description: AI-powered object detection\n      operations:\n      - name: get-ai-state\n        method: POST\n        description: Get AI detection state (person, vehicle, animal)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetAiState\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: get-ai-config\n        method: POST\n        description: Get AI detection configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetAiCfg\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: set-ai-config\n        method: POST\n        description: Configure AI detection parameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: SetAiCfg\n            action: 0\n            param: '{{tools.aiParam}}'\n      - name: get-ai-alarm\n\
  \        method: POST\n        description: Get AI alarm settings for object detection\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetAiAlarm\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n    - name: video\n      path: /cgi-bin/api.cgi\n      description: Video and image settings\n      operations:\n      - name: get-image-settings\n        method: POST\n        description: Get image quality settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetImage\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: capture-snapshot\n        method: POST\n        description: Capture a JPEG snapshot from\
  \ the camera\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: Snap\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n    - name: led\n      path: /cgi-bin/api.cgi\n      description: IR and white light LED control\n      operations:\n      - name: get-ir-lights\n        method: POST\n        description: Get infrared LED settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: GetIrLights\n            action: 0\n            param:\n              channel: '{{tools.channel}}'\n      - name: set-ir-lights\n        method: POST\n        description: Configure infrared LED for night vision\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            cmd: SetIrLights\n            action: 0\n            param: '{{tools.irParam}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: reolink-management-api\n    description: Unified REST API for Reolink camera management and surveillance.\n    resources:\n    - path: /v1/device/info\n      name: device-info\n      description: Device system information\n      operations:\n      - method: GET\n        name: get-device-info\n        description: Get camera device information and firmware details\n        call: reolink.get-device-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/device/time\n      name: device-time\n      description: Device time configuration\n      operations:\n      - method: GET\n        name: get-time\n        description: Get device date and time settings\n        call: reolink.get-time\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-time\n        description: Set device date and time\n        call: reolink.set-time\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/device/channels\n      name: channels\n      description: Camera channel status\n      operations:\n      - method: GET\n        name: get-channel-status\n        description: Get status of all camera channels\n        call: reolink.get-channel-status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/device/storage\n      name: storage\n      description: Storage drive information\n      operations:\n      - method: GET\n        name: get-hdd-info\n        description: Get hard drive storage information\n        call: reolink.get-hdd-info\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptz/control\n      name: ptz-control\n\
  \      description: PTZ movement control\n      operations:\n      - method: POST\n        name: ptz-control\n        description: Control camera pan, tilt, and zoom\n        call: reolink.ptz-control\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ptz/presets\n      name: ptz-presets\n      description: PTZ preset positions\n      operations:\n      - method: GET\n        name: get-ptz-presets\n        description: Get saved PTZ preset positions\n        call: reolink.get-ptz-presets\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings/settings\n      name: recording-settings\n      description: Recording configuration\n      operations:\n      - method: GET\n        name: get-recording-settings\n        description: Get recording schedule and settings\n        call: reolink.get-recording-settings\n\
  \        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recordings/search\n      name: recordings-search\n      description: Search recorded footage\n      operations:\n      - method: POST\n        name: search-recordings\n        description: Search recordings by date and time range\n        call: reolink.search-recordings\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alarms/motion\n      name: motion-alarm\n      description: Motion detection alarm settings\n      operations:\n      - method: GET\n        name: get-motion-alarm\n        description: Get motion detection configuration\n        call: reolink.get-motion-alarm\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-motion-alarm\n        description:\
  \ Configure motion detection settings\n        call: reolink.set-motion-alarm\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ai/state\n      name: ai-state\n      description: AI object detection state\n      operations:\n      - method: GET\n        name: get-ai-state\n        description: Get current AI detection state (person, vehicle, animal)\n        call: reolink.get-ai-state\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/video/snapshot\n      name: snapshot\n      description: Capture snapshots\n      operations:\n      - method: POST\n        name: capture-snapshot\n        description: Capture a snapshot image from the camera\n        call: reolink.capture-snapshot\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/led/ir\n      name: ir-lights\n      description: Infrared LED control\n      operations:\n      - method: GET\n        name: get-ir-lights\n        description: Get infrared LED settings\n        call: reolink.get-ir-lights\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: set-ir-lights\n        description: Configure infrared LED mode\n        call: reolink.set-ir-lights\n        with:\n          channel: rest.channel\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: reolink-management-mcp\n    transport: http\n    description: MCP server for AI-assisted Reolink camera management and surveillance monitoring.\n    tools:\n    - name: get-device-info\n      description: Get Reolink camera device information including model, firmware, and hardware details\n      hints:\n        readOnly: true\n        openWorld:\
  \ false\n      call: reolink.get-device-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-channel-status\n      description: Get the online/offline status of all camera channels on the NVR\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-channel-status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-hdd-info\n      description: Get storage drive capacity and status for the camera or NVR\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-hdd-info\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: reboot-camera\n      description: Reboot the Reolink camera or NVR device\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: reolink.reboot\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ptz-move\n      description: 'Control\
  \ PTZ camera movement: pan left/right, tilt up/down, zoom in/out, or go to preset'\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: reolink.ptz-control\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ptz-presets\n      description: Get saved PTZ preset positions for a camera channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-ptz-presets\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-recordings\n      description: Search camera recordings by date/time range and channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.search-recordings\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-recording-settings\n \
  \     description: Get recording schedule and configuration settings for a channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-recording-settings\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ai-state\n      description: Get current AI object detection state (person, vehicle, animal) for a channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-ai-state\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ai-config\n      description: Get AI detection configuration and sensitivity settings for a channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-ai-config\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-ai-config\n   \
  \   description: Configure AI object detection parameters (person/vehicle/animal sensitivity) for a channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: reolink.set-ai-config\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-motion-alarm\n      description: Get motion detection alarm configuration for a camera channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-motion-alarm\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-motion-alarm\n      description: Configure motion detection sensitivity, zones, and schedule for a channel\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: reolink.set-motion-alarm\n      with:\n        channel: tools.channel\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: capture-snapshot\n      description: Capture a JPEG snapshot from a specific camera channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.capture-snapshot\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-ir-lights\n      description: Get infrared LED settings for night vision on a camera channel\n      hints:\n        readOnly: true\n        openWorld: false\n      call: reolink.get-ir-lights\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: set-ir-lights\n      description: Configure infrared LED mode (auto/on/off) for night vision\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: reolink.set-ir-lights\n      with:\n        channel: tools.channel\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/reolink/refs/heads/main/capabilities/camera-management.yaml
tags:
- IoT
- Security Cameras
- Surveillance
- Smart Home
- PTZ
tools:
- description: Get Reolink camera device information including model, firmware, and hardware details
  hints:
    openWorld: false
    readOnly: true
  name: get-device-info
- description: Get the online/offline status of all camera channels on the NVR
  hints:
    openWorld: false
    readOnly: true
  name: get-channel-status
- description: Get storage drive capacity and status for the camera or NVR
  hints:
    openWorld: false
    readOnly: true
  name: get-hdd-info
- description: Reboot the Reolink camera or NVR device
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reboot-camera
- description: 'Control PTZ camera movement: pan left/right, tilt up/down, zoom in/out, or go to preset'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: ptz-move
- description: Get saved PTZ preset positions for a camera channel
  hints:
    openWorld: false
    readOnly: true
  name: get-ptz-presets
- description: Search camera recordings by date/time range and channel
  hints:
    openWorld: false
    readOnly: true
  name: search-recordings
- description: Get recording schedule and configuration settings for a channel
  hints:
    openWorld: false
    readOnly: true
  name: get-recording-settings
- description: Get current AI object detection state (person, vehicle, animal) for a channel
  hints:
    openWorld: false
    readOnly: true
  name: get-ai-state
- description: Get AI detection configuration and sensitivity settings for a channel
  hints:
    openWorld: false
    readOnly: true
  name: get-ai-config
- description: Configure AI object detection parameters (person/vehicle/animal sensitivity) for a channel
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-ai-config
- description: Get motion detection alarm configuration for a camera channel
  hints:
    openWorld: false
    readOnly: true
  name: get-motion-alarm
- description: Configure motion detection sensitivity, zones, and schedule for a channel
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-motion-alarm
- description: Capture a JPEG snapshot from a specific camera channel
  hints:
    openWorld: false
    readOnly: true
  name: capture-snapshot
- description: Get infrared LED settings for night vision on a camera channel
  hints:
    openWorld: false
    readOnly: true
  name: get-ir-lights
- description: Configure infrared LED mode (auto/on/off) for night vision
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: set-ir-lights
---
