---
categories: []
consumed_apis: []
description: OpenF1 is a free and open-source API providing real-time and historical Formula 1 data including car telemetry, lap timing, race control, weather, pit stops, team radio, and championship standings.
layout: capability
name: OpenF1 API
operations:
- description: List F1 sessions
  method: GET
  name: listsessions
  path: /sessions
- description: List Grand Prix meetings
  method: GET
  name: listmeetings
  path: /meetings
- description: List drivers for a session
  method: GET
  name: listdrivers
  path: /drivers
- description: List laps with sector and speed-trap times
  method: GET
  name: listlaps
  path: /laps
- description: High-frequency car telemetry (RPM, throttle, brake, gear, speed, DRS)
  method: GET
  name: getcardata
  path: /car_data
- description: Three-dimensional car location on track
  method: GET
  name: getlocation
  path: /location
- description: Driver running order during a session
  method: GET
  name: getposition
  path: /position
- description: Real-time intervals between drivers (race only)
  method: GET
  name: getintervals
  path: /intervals
- description: List pit-lane events
  method: GET
  name: listpitstops
  path: /pit
- description: List tyre stints with compound and age
  method: GET
  name: liststints
  path: /stints
- description: Track weather conditions during a session
  method: GET
  name: getweather
  path: /weather
- description: Race control messages, flags, and incidents
  method: GET
  name: listracecontrol
  path: /race_control
- description: List team radio recordings
  method: GET
  name: listteamradio
  path: /team_radio
personas: []
provider_name: OpenF1
provider_slug: openf1
search_terms:
- real-time
- sports
- list drivers for a session
- list grand prix meetings
- real-time intervals between drivers (race only)
- getintervals
- motorsport
- list team radio recordings
- telemetry
- track weather conditions during a session
- getweather
- listdrivers
- listteamradio
- high-frequency car telemetry (rpm, throttle, brake, gear, speed, drs)
- list pit-lane events
- driver running order during a session
- getlocation
- getcardata
- race control messages, flags, and incidents
- list laps with sector and speed-trap times
- list f1 sessions
- openf1
- api
- listpitstops
- formula 1
- listsessions
- liststints
- listracecontrol
- getposition
- listlaps
- listmeetings
- three-dimensional car location on track
- list tyre stints with compound and age
slug: openf1-capability
source_filename: openf1-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenF1 API\n  description: OpenF1 is a free and open-source API providing real-time and historical Formula 1 data including car telemetry,\n    lap timing, race control, weather, pit stops, team radio, and championship standings.\n  tags:\n  - Openf1\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: openf1\n    baseUri: https://api.openf1.org/v1\n    description: OpenF1 API HTTP API.\n    resources:\n    - name: sessions\n      path: /sessions\n      operations:\n      - name: listsessions\n        method: GET\n        description: List F1 sessions\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: meeting_key\n          in: query\n          type: integer\n        - name: year\n          in: query\n          type: integer\n        - name: country_name\n          in: query\n          type: string\n     \
  \   - name: session_type\n          in: query\n          type: string\n        - name: session_name\n          in: query\n          type: string\n        - name: circuit_short_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: meetings\n      path: /meetings\n      operations:\n      - name: listmeetings\n        method: GET\n        description: List Grand Prix meetings\n        inputParameters:\n        - name: meeting_key\n          in: query\n          type: integer\n        - name: year\n          in: query\n          type: integer\n        - name: country_name\n          in: query\n          type: string\n        - name: circuit_short_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: drivers\n      path: /drivers\n\
  \      operations:\n      - name: listdrivers\n        method: GET\n        description: List drivers for a session\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: meeting_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        - name: team_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: laps\n      path: /laps\n      operations:\n      - name: listlaps\n        method: GET\n        description: List laps with sector and speed-trap times\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        - name: lap_number\n          in: query\n          type: integer\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: car-data\n      path: /car_data\n      operations:\n      - name: getcardata\n        method: GET\n        description: High-frequency car telemetry (RPM, throttle, brake, gear, speed, DRS)\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        - name: speed\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: location\n      path: /location\n      operations:\n      - name: getlocation\n        method: GET\n        description: Three-dimensional car location on track\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in:\
  \ query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: position\n      path: /position\n      operations:\n      - name: getposition\n        method: GET\n        description: Driver running order during a session\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        - name: position\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: intervals\n      path: /intervals\n      operations:\n      - name: getintervals\n        method: GET\n        description: Real-time intervals between drivers (race only)\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n   \
  \     - name: driver_number\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pit\n      path: /pit\n      operations:\n      - name: listpitstops\n        method: GET\n        description: List pit-lane events\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stints\n      path: /stints\n      operations:\n      - name: liststints\n        method: GET\n        description: List tyre stints with compound and age\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: weather\n      path: /weather\n      operations:\n      - name: getweather\n        method: GET\n        description: Track weather conditions during a session\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: race-control\n      path: /race_control\n      operations:\n      - name: listracecontrol\n        method: GET\n        description: Race control messages, flags, and incidents\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        - name: category\n          in: query\n          type: string\n        - name: flag\n         \
  \ in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: team-radio\n      path: /team_radio\n      operations:\n      - name: listteamradio\n        method: GET\n        description: List team radio recordings\n        inputParameters:\n        - name: session_key\n          in: query\n          type: integer\n        - name: driver_number\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: openf1-rest\n    description: REST adapter for OpenF1 API.\n    resources:\n    - path: /sessions\n      name: listsessions\n      operations:\n      - method: GET\n        name: listsessions\n        description: List F1 sessions\n        call: openf1.listsessions\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /meetings\n      name: listmeetings\n      operations:\n      - method: GET\n        name: listmeetings\n        description: List Grand Prix meetings\n        call: openf1.listmeetings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /drivers\n      name: listdrivers\n      operations:\n      - method: GET\n        name: listdrivers\n        description: List drivers for a session\n        call: openf1.listdrivers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /laps\n      name: listlaps\n      operations:\n      - method: GET\n        name: listlaps\n        description: List laps with sector and speed-trap times\n        call: openf1.listlaps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /car_data\n      name: getcardata\n      operations:\n      - method: GET\n        name: getcardata\n        description: High-frequency\
  \ car telemetry (RPM, throttle, brake, gear, speed, DRS)\n        call: openf1.getcardata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /location\n      name: getlocation\n      operations:\n      - method: GET\n        name: getlocation\n        description: Three-dimensional car location on track\n        call: openf1.getlocation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /position\n      name: getposition\n      operations:\n      - method: GET\n        name: getposition\n        description: Driver running order during a session\n        call: openf1.getposition\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /intervals\n      name: getintervals\n      operations:\n      - method: GET\n        name: getintervals\n        description: Real-time intervals between drivers (race only)\n        call: openf1.getintervals\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /pit\n      name: listpitstops\n      operations:\n      - method: GET\n        name: listpitstops\n        description: List pit-lane events\n        call: openf1.listpitstops\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stints\n      name: liststints\n      operations:\n      - method: GET\n        name: liststints\n        description: List tyre stints with compound and age\n        call: openf1.liststints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /weather\n      name: getweather\n      operations:\n      - method: GET\n        name: getweather\n        description: Track weather conditions during a session\n        call: openf1.getweather\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /race_control\n      name: listracecontrol\n      operations:\n      - method: GET\n        name: listracecontrol\n        description: Race\
  \ control messages, flags, and incidents\n        call: openf1.listracecontrol\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /team_radio\n      name: listteamradio\n      operations:\n      - method: GET\n        name: listteamradio\n        description: List team radio recordings\n        call: openf1.listteamradio\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: openf1-mcp\n    transport: http\n    description: MCP adapter for OpenF1 API for AI agent use.\n    tools:\n    - name: listsessions\n      description: List F1 sessions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listsessions\n      with:\n        session_key: tools.session_key\n        meeting_key: tools.meeting_key\n        year: tools.year\n        country_name: tools.country_name\n        session_type: tools.session_type\n        session_name:\
  \ tools.session_name\n        circuit_short_name: tools.circuit_short_name\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: meeting_key\n        type: integer\n        description: meeting_key\n      - name: year\n        type: integer\n        description: year\n      - name: country_name\n        type: string\n        description: country_name\n      - name: session_type\n        type: string\n        description: session_type\n      - name: session_name\n        type: string\n        description: session_name\n      - name: circuit_short_name\n        type: string\n        description: circuit_short_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmeetings\n      description: List Grand Prix meetings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listmeetings\n      with:\n        meeting_key: tools.meeting_key\n\
  \        year: tools.year\n        country_name: tools.country_name\n        circuit_short_name: tools.circuit_short_name\n      inputParameters:\n      - name: meeting_key\n        type: integer\n        description: meeting_key\n      - name: year\n        type: integer\n        description: year\n      - name: country_name\n        type: string\n        description: country_name\n      - name: circuit_short_name\n        type: string\n        description: circuit_short_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdrivers\n      description: List drivers for a session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listdrivers\n      with:\n        session_key: tools.session_key\n        meeting_key: tools.meeting_key\n        driver_number: tools.driver_number\n        team_name: tools.team_name\n      inputParameters:\n      - name: session_key\n        type: integer\n     \
  \   description: session_key\n      - name: meeting_key\n        type: integer\n        description: meeting_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      - name: team_name\n        type: string\n        description: team_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlaps\n      description: List laps with sector and speed-trap times\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listlaps\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n        lap_number: tools.lap_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      - name: lap_number\n        type: integer\n        description: lap_number\n      outputParameters:\n      -\
  \ type: object\n        mapping: $.\n    - name: getcardata\n      description: High-frequency car telemetry (RPM, throttle, brake, gear, speed, DRS)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.getcardata\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n        speed: tools.speed\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      - name: speed\n        type: integer\n        description: speed\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlocation\n      description: Three-dimensional car location on track\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.getlocation\n      with:\n        session_key: tools.session_key\n  \
  \      driver_number: tools.driver_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getposition\n      description: Driver running order during a session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.getposition\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n        position: tools.position\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      - name: position\n        type: integer\n        description: position\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getintervals\n\
  \      description: Real-time intervals between drivers (race only)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.getintervals\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpitstops\n      description: List pit-lane events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listpitstops\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n\
  \        description: driver_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststints\n      description: List tyre stints with compound and age\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.liststints\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getweather\n      description: Track weather conditions during a session\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.getweather\n      with:\n        session_key: tools.session_key\n      inputParameters:\n      - name: session_key\n        type: integer\n\
  \        description: session_key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listracecontrol\n      description: Race control messages, flags, and incidents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: openf1.listracecontrol\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n        category: tools.category\n        flag: tools.flag\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      - name: category\n        type: string\n        description: category\n      - name: flag\n        type: string\n        description: flag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listteamradio\n      description: List team radio recordings\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: openf1.listteamradio\n      with:\n        session_key: tools.session_key\n        driver_number: tools.driver_number\n      inputParameters:\n      - name: session_key\n        type: integer\n        description: session_key\n      - name: driver_number\n        type: integer\n        description: driver_number\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/openf1/refs/heads/main/capabilities/openf1-capability.yaml
tags:
- Openf1
- API
tools:
- description: List F1 sessions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsessions
- description: List Grand Prix meetings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmeetings
- description: List drivers for a session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdrivers
- description: List laps with sector and speed-trap times
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlaps
- description: High-frequency car telemetry (RPM, throttle, brake, gear, speed, DRS)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcardata
- description: Three-dimensional car location on track
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlocation
- description: Driver running order during a session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getposition
- description: Real-time intervals between drivers (race only)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getintervals
- description: List pit-lane events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpitstops
- description: List tyre stints with compound and age
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststints
- description: Track weather conditions during a session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getweather
- description: Race control messages, flags, and incidents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listracecontrol
- description: List team radio recordings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listteamradio
---
