---
categories: []
consumed_apis:
- flir-camera
description: Industrial thermal monitoring capability using Teledyne FLIR automation cameras. Enables continuous temperature monitoring, alarm management, and predictive maintenance workflows for manufacturing, electrical infrastructure, process plants, and building inspection applications. Combines real-time thermal imaging with ROI measurement and alarm monitoring via the FLIR Camera REST API.
layout: capability
name: Teledyne FLIR Industrial Thermal Monitoring
operations:
- description: Capture current thermal image in the specified format.
  method: GET
  name: get-current-image
  path: /v1/images/current
- description: Get spot temperature measurement.
  method: GET
  name: get-spot-measurement
  path: /v1/measurements/spots/{instance}
- description: Get box ROI temperature statistics.
  method: GET
  name: get-box-measurement
  path: /v1/measurements/boxes/{instance}
- description: Get line profile temperature measurements.
  method: GET
  name: get-line-measurement
  path: /v1/measurements/lines/{instance}
- description: Get all camera alarm states.
  method: GET
  name: get-all-alarms
  path: /v1/alarms
- description: Get a specific camera alarm state.
  method: GET
  name: get-alarm
  path: /v1/alarms/{instance}
personas: []
provider_name: Teledyne Technologies
provider_slug: teledyne-technologies
search_terms:
- get current image
- industrial automation
- current thermal camera image.
- get alarm
- spot temperature measurement.
- get line measurement
- get spot measurement
- get box measurement
- camera alarm states.
- read line temperature profile
- process monitoring
- test and measurement
- machine vision
- get spot temperature measurement.
- thermal imaging
- check whether a specific temperature alarm is triggered on the flir camera.
- capture a current thermal image from a flir automation camera. use imgformat=rjpeg for radiometric data.
- check the state of all configured temperature alarms on the flir camera.
- digital imaging
- box roi temperature statistics.
- line profile temperature measurements.
- get all camera alarm states.
- read min, max, and average temperature statistics for a box region of interest on the flir camera.
- capture thermal image
- fortune 500
- check alarm
- read the temperature profile across a line region of interest for thermal gradient analysis.
- capture current thermal image in the specified format.
- read spot temperature
- predictive maintenance
- get line profile temperature measurements.
- defense
- get a specific camera alarm state.
- read box temperature stats
- thermal monitoring
- specific alarm state.
- teledyne flir
- instrumentation
- aerospace
- read the current temperature at a specific spot measurement point on the flir camera.
- get all alarms
- get box roi temperature statistics.
- check all alarms
slug: industrial-thermal-monitoring
source_filename: industrial-thermal-monitoring.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Teledyne FLIR Industrial Thermal Monitoring\"\n  description: >-\n    Industrial thermal monitoring capability using Teledyne FLIR automation\n    cameras. Enables continuous temperature monitoring, alarm management,\n    and predictive maintenance workflows for manufacturing, electrical\n    infrastructure, process plants, and building inspection applications.\n    Combines real-time thermal imaging with ROI measurement and alarm\n    monitoring via the FLIR Camera REST API.\n  tags:\n    - Teledyne FLIR\n    - Thermal Monitoring\n    - Industrial Automation\n    - Predictive Maintenance\n    - Process Monitoring\n    - Machine Vision\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      FLIR_CAMERA_IP: FLIR_CAMERA_IP\n\ncapability:\n  consumes:\n    - import: flir-camera\n      location: ./shared/flir-camera-rest.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace:\
  \ thermal-monitoring-api\n      description: \"Unified REST API for Teledyne FLIR industrial thermal monitoring.\"\n      resources:\n        - path: /v1/images/current\n          name: current-image\n          description: \"Current thermal camera image.\"\n          operations:\n            - method: GET\n              name: get-current-image\n              description: \"Capture current thermal image in the specified format.\"\n              call: \"flir-camera.get-current-image\"\n              with:\n                imgformat: \"rest.imgformat\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/measurements/spots/{instance}\n          name: spot-measurement\n          description: \"Spot temperature measurement.\"\n          operations:\n            - method: GET\n              name: get-spot-measurement\n              description: \"Get spot temperature measurement.\"\n              call: \"flir-camera.get-spot-measurement\"\
  \n              with:\n                instance: \"rest.instance\"\n                tempUnit: \"rest.tempUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/measurements/boxes/{instance}\n          name: box-measurement\n          description: \"Box ROI temperature statistics.\"\n          operations:\n            - method: GET\n              name: get-box-measurement\n              description: \"Get box ROI temperature statistics.\"\n              call: \"flir-camera.get-box-measurement\"\n              with:\n                instance: \"rest.instance\"\n                tempUnit: \"rest.tempUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/measurements/lines/{instance}\n          name: line-measurement\n          description: \"Line profile temperature measurements.\"\n          operations:\n            - method: GET\n         \
  \     name: get-line-measurement\n              description: \"Get line profile temperature measurements.\"\n              call: \"flir-camera.get-line-measurement\"\n              with:\n                instance: \"rest.instance\"\n                tempUnit: \"rest.tempUnit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alarms\n          name: alarms\n          description: \"Camera alarm states.\"\n          operations:\n            - method: GET\n              name: get-all-alarms\n              description: \"Get all camera alarm states.\"\n              call: \"flir-camera.get-all-alarms\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/alarms/{instance}\n          name: alarm\n          description: \"Specific alarm state.\"\n          operations:\n            - method: GET\n              name: get-alarm\n              description:\
  \ \"Get a specific camera alarm state.\"\n              call: \"flir-camera.get-alarm\"\n              with:\n                instance: \"rest.instance\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: thermal-monitoring-mcp\n      transport: http\n      description: \"MCP server for AI-assisted FLIR industrial thermal monitoring.\"\n      tools:\n        - name: capture-thermal-image\n          description: \"Capture a current thermal image from a FLIR automation camera. Use imgformat=RJPEG for radiometric data.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"flir-camera.get-current-image\"\n          with:\n            imgformat: \"tools.imgformat\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: read-spot-temperature\n          description: \"Read the current temperature at\
  \ a specific spot measurement point on the FLIR camera.\"\n          hints:\n            readOnly: true\n          call: \"flir-camera.get-spot-measurement\"\n          with:\n            instance: \"tools.instance\"\n            tempUnit: \"tools.tempUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: read-box-temperature-stats\n          description: \"Read min, max, and average temperature statistics for a box region of interest on the FLIR camera.\"\n          hints:\n            readOnly: true\n          call: \"flir-camera.get-box-measurement\"\n          with:\n            instance: \"tools.instance\"\n            tempUnit: \"tools.tempUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: read-line-temperature-profile\n          description: \"Read the temperature profile across a line region of interest for thermal gradient analysis.\"\n          hints:\n  \
  \          readOnly: true\n          call: \"flir-camera.get-line-measurement\"\n          with:\n            instance: \"tools.instance\"\n            tempUnit: \"tools.tempUnit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-all-alarms\n          description: \"Check the state of all configured temperature alarms on the FLIR camera.\"\n          hints:\n            readOnly: true\n          call: \"flir-camera.get-all-alarms\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: check-alarm\n          description: \"Check whether a specific temperature alarm is triggered on the FLIR camera.\"\n          hints:\n            readOnly: true\n          call: \"flir-camera.get-alarm\"\n          with:\n            instance: \"tools.instance\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/teledyne-technologies/refs/heads/main/capabilities/industrial-thermal-monitoring.yaml
tags:
- Teledyne FLIR
- Thermal Monitoring
- Industrial Automation
- Predictive Maintenance
- Process Monitoring
- Machine Vision
tools:
- description: Capture a current thermal image from a FLIR automation camera. Use imgformat=RJPEG for radiometric data.
  hints:
    openWorld: true
    readOnly: true
  name: capture-thermal-image
- description: Read the current temperature at a specific spot measurement point on the FLIR camera.
  hints:
    readOnly: true
  name: read-spot-temperature
- description: Read min, max, and average temperature statistics for a box region of interest on the FLIR camera.
  hints:
    readOnly: true
  name: read-box-temperature-stats
- description: Read the temperature profile across a line region of interest for thermal gradient analysis.
  hints:
    readOnly: true
  name: read-line-temperature-profile
- description: Check the state of all configured temperature alarms on the FLIR camera.
  hints:
    readOnly: true
  name: check-all-alarms
- description: Check whether a specific temperature alarm is triggered on the FLIR camera.
  hints:
    readOnly: true
  name: check-alarm
---
