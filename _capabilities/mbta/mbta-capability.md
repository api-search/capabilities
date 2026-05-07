---
categories: []
consumed_apis: []
description: The MBTA V3 API provides fast, easy access to Massachusetts Bay Transportation Authority schedules, alerts, and real-time information. Returns JSON:API formatted responses (application/vnd.api+json) for routes, stops, trips, schedules, predictions, vehicles, alerts, lines, facilities, services, shapes, and route patterns. Free API keys are available via the developer portal for higher rate limits.
layout: capability
name: MBTA V3 API
operations:
- description: List alerts
  method: GET
  name: listalerts
  path: /alerts
- description: Get alert
  method: GET
  name: getalert
  path: /alerts/{id}
- description: List facilities
  method: GET
  name: listfacilities
  path: /facilities
- description: Get facility
  method: GET
  name: getfacility
  path: /facilities/{id}
- description: List lines
  method: GET
  name: listlines
  path: /lines
- description: Get line
  method: GET
  name: getline
  path: /lines/{id}
- description: List predictions
  method: GET
  name: listpredictions
  path: /predictions
- description: List routes
  method: GET
  name: listroutes
  path: /routes
- description: Get route
  method: GET
  name: getroute
  path: /routes/{id}
- description: List route patterns
  method: GET
  name: listroutepatterns
  path: /route_patterns
- description: Get route pattern
  method: GET
  name: getroutepattern
  path: /route_patterns/{id}
- description: List schedules
  method: GET
  name: listschedules
  path: /schedules
- description: List services
  method: GET
  name: listservices
  path: /services
- description: Get service
  method: GET
  name: getservice
  path: /services/{id}
- description: List shapes
  method: GET
  name: listshapes
  path: /shapes
- description: Get shape
  method: GET
  name: getshape
  path: /shapes/{id}
- description: List stops
  method: GET
  name: liststops
  path: /stops
- description: Get stop
  method: GET
  name: getstop
  path: /stops/{id}
- description: List trips
  method: GET
  name: listtrips
  path: /trips
- description: Get trip
  method: GET
  name: gettrip
  path: /trips/{id}
- description: List vehicles
  method: GET
  name: listvehicles
  path: /vehicles
- description: Get vehicle
  method: GET
  name: getvehicle
  path: /vehicles/{id}
personas: []
provider_name: MBTA
provider_slug: mbta
search_terms:
- get vehicle
- list services
- getfacility
- listroutepatterns
- get route pattern
- listlines
- getshape
- getstop
- list trips
- liststops
- getservice
- get line
- get route
- list route patterns
- api
- listschedules
- listalerts
- public transportation
- getalert
- getline
- list shapes
- get shape
- list vehicles
- listvehicles
- listshapes
- getroutepattern
- list lines
- listtrips
- list routes
- list schedules
- get service
- listpredictions
- list alerts
- getvehicle
- get alert
- mbta
- massachusetts
- getroute
- list predictions
- get stop
- list stops
- get trip
- list facilities
- boston
- transit
- get facility
- real-time
- listfacilities
- gettrip
- listroutes
- listservices
slug: mbta-capability
source_filename: mbta-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: MBTA V3 API\n  description: The MBTA V3 API provides fast, easy access to Massachusetts Bay Transportation Authority schedules, alerts,\n    and real-time information. Returns JSON:API formatted responses (application/vnd.api+json) for routes, stops, trips, schedules,\n    predictions, vehicles, alerts, lines, facilities, services, shapes, and route patterns. Free API keys are available via\n    the developer portal for higher rate limits.\n  tags:\n  - Mbta\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: mbta\n    baseUri: https://api-v3.mbta.com\n    description: MBTA V3 API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{MBTA_TOKEN}}'\n    resources:\n    - name: alerts\n      path: /alerts\n      operations:\n      - name: listalerts\n        method: GET\n        description: List alerts\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts-id\n      path: /alerts/{id}\n      operations:\n      - name: getalert\n        method: GET\n        description: Get alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities\n      path: /facilities\n      operations:\n      - name: listfacilities\n        method: GET\n        description: List facilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities-id\n      path: /facilities/{id}\n      operations:\n      - name: getfacility\n        method: GET\n        description: Get facility\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lines\n      path: /lines\n      operations:\n\
  \      - name: listlines\n        method: GET\n        description: List lines\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: lines-id\n      path: /lines/{id}\n      operations:\n      - name: getline\n        method: GET\n        description: Get line\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: predictions\n      path: /predictions\n      operations:\n      - name: listpredictions\n        method: GET\n        description: List predictions\n        inputParameters:\n        - name: filter[stop]\n          in: query\n          type: string\n        - name: filter[route]\n          in: query\n          type: string\n        - name: filter[trip]\n          in: query\n          type: string\n        - name: filter[direction_id]\n          in: query\n          type: integer\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes\n      path: /routes\n      operations:\n      - name: listroutes\n        method: GET\n        description: List routes\n        inputParameters:\n        - name: filter[stop]\n          in: query\n          type: string\n        - name: filter[type]\n          in: query\n          type: string\n        - name: filter[direction_id]\n          in: query\n          type: integer\n        - name: filter[date]\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: routes-id\n      path: /routes/{id}\n      operations:\n      - name: getroute\n        method: GET\n        description: Get route\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-patterns\n\
  \      path: /route_patterns\n      operations:\n      - name: listroutepatterns\n        method: GET\n        description: List route patterns\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: route-patterns-id\n      path: /route_patterns/{id}\n      operations:\n      - name: getroutepattern\n        method: GET\n        description: Get route pattern\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules\n      path: /schedules\n      operations:\n      - name: listschedules\n        method: GET\n        description: List schedules\n        inputParameters:\n        - name: filter[date]\n          in: query\n          type: string\n        - name: filter[direction_id]\n          in: query\n          type: integer\n        - name: filter[route]\n          in: query\n          type: string\n        - name:\
  \ filter[stop]\n          in: query\n          type: string\n        - name: filter[trip]\n          in: query\n          type: string\n        - name: filter[min_time]\n          in: query\n          type: string\n        - name: filter[max_time]\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services\n      path: /services\n      operations:\n      - name: listservices\n        method: GET\n        description: List services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: services-id\n      path: /services/{id}\n      operations:\n      - name: getservice\n        method: GET\n        description: Get service\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shapes\n  \
  \    path: /shapes\n      operations:\n      - name: listshapes\n        method: GET\n        description: List shapes\n        inputParameters:\n        - name: filter[route]\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: shapes-id\n      path: /shapes/{id}\n      operations:\n      - name: getshape\n        method: GET\n        description: Get shape\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stops\n      path: /stops\n      operations:\n      - name: liststops\n        method: GET\n        description: List stops\n        inputParameters:\n        - name: filter[latitude]\n          in: query\n          type: number\n        - name: filter[longitude]\n          in: query\n          type: number\n        - name: filter[radius]\n\
  \          in: query\n          type: number\n        - name: filter[route]\n          in: query\n          type: string\n        - name: filter[route_type]\n          in: query\n          type: string\n        - name: filter[location_type]\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stops-id\n      path: /stops/{id}\n      operations:\n      - name: getstop\n        method: GET\n        description: Get stop\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trips\n      path: /trips\n      operations:\n      - name: listtrips\n        method: GET\n        description: List trips\n        inputParameters:\n        - name: filter[date]\n          in: query\n          type: string\n        - name: filter[direction_id]\n          in: query\n          type: integer\n\
  \        - name: filter[route]\n          in: query\n          type: string\n        - name: filter[route_pattern]\n          in: query\n          type: string\n        - name: filter[name]\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trips-id\n      path: /trips/{id}\n      operations:\n      - name: gettrip\n        method: GET\n        description: Get trip\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles\n      path: /vehicles\n      operations:\n      - name: listvehicles\n        method: GET\n        description: List vehicles\n        inputParameters:\n        - name: filter[trip]\n          in: query\n          type: string\n        - name: filter[label]\n          in: query\n          type: string\n        - name: filter[route]\n          in:\
  \ query\n          type: string\n        - name: filter[direction_id]\n          in: query\n          type: integer\n        - name: filter[route_type]\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vehicles-id\n      path: /vehicles/{id}\n      operations:\n      - name: getvehicle\n        method: GET\n        description: Get vehicle\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: mbta-rest\n    description: REST adapter for MBTA V3 API.\n    resources:\n    - path: /alerts\n      name: listalerts\n      operations:\n      - method: GET\n        name: listalerts\n        description: List alerts\n        call: mbta.listalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /alerts/{id}\n      name: getalert\n      operations:\n      - method: GET\n        name: getalert\n        description: Get alert\n        call: mbta.getalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities\n      name: listfacilities\n      operations:\n      - method: GET\n        name: listfacilities\n        description: List facilities\n        call: mbta.listfacilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities/{id}\n      name: getfacility\n      operations:\n      - method: GET\n        name: getfacility\n        description: Get facility\n        call: mbta.getfacility\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /lines\n      name: listlines\n      operations:\n      - method: GET\n        name: listlines\n        description: List lines\n        call: mbta.listlines\n        outputParameters:\n        - type: object\n       \
  \   mapping: $.\n    - path: /lines/{id}\n      name: getline\n      operations:\n      - method: GET\n        name: getline\n        description: Get line\n        call: mbta.getline\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /predictions\n      name: listpredictions\n      operations:\n      - method: GET\n        name: listpredictions\n        description: List predictions\n        call: mbta.listpredictions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes\n      name: listroutes\n      operations:\n      - method: GET\n        name: listroutes\n        description: List routes\n        call: mbta.listroutes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /routes/{id}\n      name: getroute\n      operations:\n      - method: GET\n        name: getroute\n        description: Get route\n        call: mbta.getroute\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /route_patterns\n      name: listroutepatterns\n      operations:\n      - method: GET\n        name: listroutepatterns\n        description: List route patterns\n        call: mbta.listroutepatterns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /route_patterns/{id}\n      name: getroutepattern\n      operations:\n      - method: GET\n        name: getroutepattern\n        description: Get route pattern\n        call: mbta.getroutepattern\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules\n      name: listschedules\n      operations:\n      - method: GET\n        name: listschedules\n        description: List schedules\n        call: mbta.listschedules\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services\n      name: listservices\n      operations:\n      - method: GET\n        name: listservices\n        description:\
  \ List services\n        call: mbta.listservices\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /services/{id}\n      name: getservice\n      operations:\n      - method: GET\n        name: getservice\n        description: Get service\n        call: mbta.getservice\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shapes\n      name: listshapes\n      operations:\n      - method: GET\n        name: listshapes\n        description: List shapes\n        call: mbta.listshapes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /shapes/{id}\n      name: getshape\n      operations:\n      - method: GET\n        name: getshape\n        description: Get shape\n        call: mbta.getshape\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stops\n      name: liststops\n      operations:\n      - method: GET\n        name: liststops\n        description:\
  \ List stops\n        call: mbta.liststops\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stops/{id}\n      name: getstop\n      operations:\n      - method: GET\n        name: getstop\n        description: Get stop\n        call: mbta.getstop\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /trips\n      name: listtrips\n      operations:\n      - method: GET\n        name: listtrips\n        description: List trips\n        call: mbta.listtrips\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /trips/{id}\n      name: gettrip\n      operations:\n      - method: GET\n        name: gettrip\n        description: Get trip\n        call: mbta.gettrip\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vehicles\n      name: listvehicles\n      operations:\n      - method: GET\n        name: listvehicles\n        description: List vehicles\n\
  \        call: mbta.listvehicles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /vehicles/{id}\n      name: getvehicle\n      operations:\n      - method: GET\n        name: getvehicle\n        description: Get vehicle\n        call: mbta.getvehicle\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: mbta-mcp\n    transport: http\n    description: MCP adapter for MBTA V3 API for AI agent use.\n    tools:\n    - name: listalerts\n      description: List alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listalerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalert\n      description: Get alert\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getalert\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: listfacilities\n      description: List facilities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listfacilities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfacility\n      description: Get facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getfacility\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listlines\n      description: List lines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listlines\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getline\n      description: Get line\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getline\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpredictions\n\
  \      description: List predictions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listpredictions\n      with:\n        filter[stop]: tools.filter[stop]\n        filter[route]: tools.filter[route]\n        filter[trip]: tools.filter[trip]\n        filter[direction_id]: tools.filter[direction_id]\n      inputParameters:\n      - name: filter[stop]\n        type: string\n        description: filter[stop]\n      - name: filter[route]\n        type: string\n        description: filter[route]\n      - name: filter[trip]\n        type: string\n        description: filter[trip]\n      - name: filter[direction_id]\n        type: integer\n        description: filter[direction_id]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroutes\n      description: List routes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listroutes\n      with:\n\
  \        filter[stop]: tools.filter[stop]\n        filter[type]: tools.filter[type]\n        filter[direction_id]: tools.filter[direction_id]\n        filter[date]: tools.filter[date]\n      inputParameters:\n      - name: filter[stop]\n        type: string\n        description: filter[stop]\n      - name: filter[type]\n        type: string\n        description: filter[type]\n      - name: filter[direction_id]\n        type: integer\n        description: filter[direction_id]\n      - name: filter[date]\n        type: string\n        description: filter[date]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroute\n      description: Get route\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getroute\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroutepatterns\n      description: List route patterns\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: mbta.listroutepatterns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getroutepattern\n      description: Get route pattern\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getroutepattern\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedules\n      description: List schedules\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listschedules\n      with:\n        filter[date]: tools.filter[date]\n        filter[direction_id]: tools.filter[direction_id]\n        filter[route]: tools.filter[route]\n        filter[stop]: tools.filter[stop]\n        filter[trip]: tools.filter[trip]\n        filter[min_time]: tools.filter[min_time]\n        filter[max_time]: tools.filter[max_time]\n      inputParameters:\n      - name: filter[date]\n        type: string\n\
  \        description: filter[date]\n      - name: filter[direction_id]\n        type: integer\n        description: filter[direction_id]\n      - name: filter[route]\n        type: string\n        description: filter[route]\n      - name: filter[stop]\n        type: string\n        description: filter[stop]\n      - name: filter[trip]\n        type: string\n        description: filter[trip]\n      - name: filter[min_time]\n        type: string\n        description: filter[min_time]\n      - name: filter[max_time]\n        type: string\n        description: filter[max_time]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservices\n      description: List services\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listservices\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getservice\n      description: Get service\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: mbta.getservice\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listshapes\n      description: List shapes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listshapes\n      with:\n        filter[route]: tools.filter[route]\n      inputParameters:\n      - name: filter[route]\n        type: string\n        description: filter[route]\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getshape\n      description: Get shape\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getshape\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststops\n      description: List stops\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.liststops\n  \
  \    with:\n        filter[latitude]: tools.filter[latitude]\n        filter[longitude]: tools.filter[longitude]\n        filter[radius]: tools.filter[radius]\n        filter[route]: tools.filter[route]\n        filter[route_type]: tools.filter[route_type]\n        filter[location_type]: tools.filter[location_type]\n      inputParameters:\n      - name: filter[latitude]\n        type: number\n        description: filter[latitude]\n      - name: filter[longitude]\n        type: number\n        description: filter[longitude]\n      - name: filter[radius]\n        type: number\n        description: filter[radius]\n      - name: filter[route]\n        type: string\n        description: filter[route]\n      - name: filter[route_type]\n        type: string\n        description: filter[route_type]\n      - name: filter[location_type]\n        type: string\n        description: filter[location_type]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstop\n    \
  \  description: Get stop\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getstop\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtrips\n      description: List trips\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listtrips\n      with:\n        filter[date]: tools.filter[date]\n        filter[direction_id]: tools.filter[direction_id]\n        filter[route]: tools.filter[route]\n        filter[route_pattern]: tools.filter[route_pattern]\n        filter[name]: tools.filter[name]\n      inputParameters:\n      - name: filter[date]\n        type: string\n        description: filter[date]\n      - name: filter[direction_id]\n        type: integer\n        description: filter[direction_id]\n      - name: filter[route]\n        type: string\n        description: filter[route]\n      - name: filter[route_pattern]\n        type: string\n\
  \        description: filter[route_pattern]\n      - name: filter[name]\n        type: string\n        description: filter[name]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettrip\n      description: Get trip\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.gettrip\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvehicles\n      description: List vehicles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.listvehicles\n      with:\n        filter[trip]: tools.filter[trip]\n        filter[label]: tools.filter[label]\n        filter[route]: tools.filter[route]\n        filter[direction_id]: tools.filter[direction_id]\n        filter[route_type]: tools.filter[route_type]\n      inputParameters:\n      - name: filter[trip]\n        type: string\n        description: filter[trip]\n      - name: filter[label]\n\
  \        type: string\n        description: filter[label]\n      - name: filter[route]\n        type: string\n        description: filter[route]\n      - name: filter[direction_id]\n        type: integer\n        description: filter[direction_id]\n      - name: filter[route_type]\n        type: string\n        description: filter[route_type]\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvehicle\n      description: Get vehicle\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: mbta.getvehicle\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    MBTA_TOKEN: MBTA_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/mbta/refs/heads/main/capabilities/mbta-capability.yaml
tags:
- Mbta
- API
tools:
- description: List alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalerts
- description: Get alert
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalert
- description: List facilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilities
- description: Get facility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfacility
- description: List lines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlines
- description: Get line
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getline
- description: List predictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpredictions
- description: List routes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutes
- description: Get route
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroute
- description: List route patterns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroutepatterns
- description: Get route pattern
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getroutepattern
- description: List schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedules
- description: List services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservices
- description: Get service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getservice
- description: List shapes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listshapes
- description: Get shape
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getshape
- description: List stops
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: liststops
- description: Get stop
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstop
- description: List trips
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtrips
- description: Get trip
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettrip
- description: List vehicles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvehicles
- description: Get vehicle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvehicle
---
