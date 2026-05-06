---
categories: []
consumed_apis: []
description: The Recreation Information Database (RIDB) API provides programmatic access to information about federal recreation areas, facilities, campsites, tours, permits, events, and activities across the United States. RIDB is the authoritative federal source for recreation data managed by Recreation.gov.
layout: capability
name: Recreation Information Database (RIDB) API
operations:
- description: List activities
  method: GET
  name: listactivities
  path: /activities
- description: Get activity
  method: GET
  name: getactivity
  path: /activities/{id}
- description: List facilities
  method: GET
  name: listfacilities
  path: /facilities
- description: Get facility
  method: GET
  name: getfacility
  path: /facilities/{id}
- description: List activities for a facility
  method: GET
  name: listfacilityactivities
  path: /facilities/{id}/activities
- description: List campsites for a facility
  method: GET
  name: listfacilitycampsites
  path: /facilities/{id}/campsites
- description: List media for a facility
  method: GET
  name: listfacilitymedia
  path: /facilities/{id}/media
- description: List links for a facility
  method: GET
  name: listfacilitylinks
  path: /facilities/{id}/links
- description: List campsites
  method: GET
  name: listcampsites
  path: /campsites
- description: Get campsite
  method: GET
  name: getcampsite
  path: /campsites/{id}
- description: List recreation areas
  method: GET
  name: listrecareas
  path: /recareas
- description: Get recreation area
  method: GET
  name: getrecarea
  path: /recareas/{id}
- description: List activities for a recreation area
  method: GET
  name: listrecareaactivities
  path: /recareas/{id}/activities
- description: List facilities for a recreation area
  method: GET
  name: listrecareafacilities
  path: /recareas/{id}/facilities
- description: List media for a recreation area
  method: GET
  name: listrecareamedia
  path: /recareas/{id}/media
- description: List tours
  method: GET
  name: listtours
  path: /tours
- description: Get tour
  method: GET
  name: gettour
  path: /tours/{id}
- description: List permit entrances
  method: GET
  name: listpermitentrances
  path: /permitentrances
- description: Get permit entrance
  method: GET
  name: getpermitentrance
  path: /permitentrances/{id}
- description: List events
  method: GET
  name: listevents
  path: /events
- description: Get event
  method: GET
  name: getevent
  path: /events/{id}
- description: List media
  method: GET
  name: listmedia
  path: /media
- description: List links
  method: GET
  name: listlinks
  path: /links
- description: List organizations
  method: GET
  name: listorganizations
  path: /organizations
- description: Get organization
  method: GET
  name: getorganization
  path: /organizations/{id}
personas: []
provider_name: Recreation.gov
provider_slug: recreation-gov
search_terms:
- list events
- listrecareamedia
- list links
- listtours
- listfacilities
- get activity
- listevents
- list media
- get campsite
- listlinks
- list organizations
- list media for a facility
- listmedia
- list facilities for a recreation area
- camping
- list activities for a recreation area
- get event
- list campsites
- listcampsites
- get permit entrance
- getpermitentrance
- list tours
- listfacilitylinks
- getorganization
- public lands
- listfacilitymedia
- listactivities
- list facilities
- recreation
- getfacility
- list links for a facility
- listrecareas
- get recreation area
- get tour
- get organization
- listorganizations
- listfacilitycampsites
- list activities for a facility
- outdoors
- getcampsite
- gettour
- api
- listfacilityactivities
- getrecarea
- gov
- list media for a recreation area
- getactivity
- listrecareafacilities
- list campsites for a facility
- list activities
- list recreation areas
- listrecareaactivities
- getevent
- get facility
- federal
- list permit entrances
- listpermitentrances
slug: recreation-gov-capability
source_filename: recreation-gov-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Recreation Information Database (RIDB) API\n  description: The Recreation Information Database (RIDB) API provides programmatic access to information about federal recreation\n    areas, facilities, campsites, tours, permits, events, and activities across the United States. RIDB is the authoritative\n    federal source for recreation data managed by Recreation.gov.\n  tags:\n  - Recreation\n  - Gov\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: recreation-gov\n    baseUri: https://ridb.recreation.gov/api/v1\n    description: Recreation Information Database (RIDB) API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: apikey\n      value: '{{RECREATION_GOV_TOKEN}}'\n    resources:\n    - name: activities\n      path: /activities\n      operations:\n      - name: listactivities\n        method: GET\n        description: List activities\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: activities-id\n      path: /activities/{id}\n      operations:\n      - name: getactivity\n        method: GET\n        description: Get activity\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities\n      path: /facilities\n      operations:\n      - name: listfacilities\n        method: GET\n        description: List facilities\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        - name: activity\n          in: query\n          type: string\n        - name: lastupdated\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: facilities-id\n      path: /facilities/{id}\n      operations:\n      - name: getfacility\n        method: GET\n        description: Get facility\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities-id-activities\n      path: /facilities/{id}/activities\n      operations:\n      - name: listfacilityactivities\n        method: GET\n        description: List activities for a facility\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities-id-campsites\n      path: /facilities/{id}/campsites\n      operations:\n\
  \      - name: listfacilitycampsites\n        method: GET\n        description: List campsites for a facility\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities-id-media\n      path: /facilities/{id}/media\n      operations:\n      - name: listfacilitymedia\n        method: GET\n        description: List media for a facility\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: facilities-id-links\n      path: /facilities/{id}/links\n      operations:\n      - name: listfacilitylinks\n        method: GET\n        description: List links for a facility\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campsites\n      path: /campsites\n      operations:\n      - name: listcampsites\n        method: GET\n        description: List campsites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: campsites-id\n      path: /campsites/{id}\n      operations:\n      - name: getcampsite\n        method: GET\n        description: Get campsite\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recareas\n      path: /recareas\n      operations:\n      - name: listrecareas\n       \
  \ method: GET\n        description: List recreation areas\n        inputParameters:\n        - name: state\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recareas-id\n      path: /recareas/{id}\n      operations:\n      - name: getrecarea\n        method: GET\n        description: Get recreation area\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recareas-id-activities\n      path: /recareas/{id}/activities\n      operations:\n      - name: listrecareaactivities\n        method: GET\n        description: List activities for a recreation area\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recareas-id-facilities\n      path: /recareas/{id}/facilities\n      operations:\n      - name: listrecareafacilities\n        method: GET\n        description: List facilities for a recreation area\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recareas-id-media\n      path: /recareas/{id}/media\n      operations:\n      - name: listrecareamedia\n        method: GET\n        description: List media for a recreation area\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: tours\n      path: /tours\n      operations:\n      - name: listtours\n        method: GET\n        description: List tours\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tours-id\n      path: /tours/{id}\n      operations:\n      - name: gettour\n        method: GET\n        description: Get tour\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permitentrances\n      path: /permitentrances\n      operations:\n      - name: listpermitentrances\n        method: GET\n        description: List permit entrances\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: permitentrances-id\n\
  \      path: /permitentrances/{id}\n      operations:\n      - name: getpermitentrance\n        method: GET\n        description: Get permit entrance\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      operations:\n      - name: listevents\n        method: GET\n        description: List events\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events-id\n      path: /events/{id}\n      operations:\n      - name: getevent\n        method: GET\n        description: Get event\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: media\n      path: /media\n      operations:\n      - name: listmedia\n        method: GET\n        description: List media\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: links\n      path: /links\n      operations:\n      - name: listlinks\n        method: GET\n        description: List links\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations\n      path: /organizations\n      operations:\n      - name: listorganizations\n        method: GET\n        description: List organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-id\n      path: /organizations/{id}\n      operations:\n      - name: getorganization\n        method: GET\n\
  \        description: Get organization\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: recreation-gov-rest\n    description: REST adapter for Recreation Information Database (RIDB) API.\n    resources:\n    - path: /activities\n      name: listactivities\n      operations:\n      - method: GET\n        name: listactivities\n        description: List activities\n        call: recreation-gov.listactivities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /activities/{id}\n      name: getactivity\n      operations:\n      - method: GET\n        name: getactivity\n        description: Get activity\n        call: recreation-gov.getactivity\n        with:\n          id: rest.id\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /facilities\n      name: listfacilities\n      operations:\n      - method: GET\n        name: listfacilities\n        description: List facilities\n        call: recreation-gov.listfacilities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities/{id}\n      name: getfacility\n      operations:\n      - method: GET\n        name: getfacility\n        description: Get facility\n        call: recreation-gov.getfacility\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities/{id}/activities\n      name: listfacilityactivities\n      operations:\n      - method: GET\n        name: listfacilityactivities\n        description: List activities for a facility\n        call: recreation-gov.listfacilityactivities\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /facilities/{id}/campsites\n      name: listfacilitycampsites\n      operations:\n      - method: GET\n        name: listfacilitycampsites\n        description: List campsites for a facility\n        call: recreation-gov.listfacilitycampsites\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities/{id}/media\n      name: listfacilitymedia\n      operations:\n      - method: GET\n        name: listfacilitymedia\n        description: List media for a facility\n        call: recreation-gov.listfacilitymedia\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /facilities/{id}/links\n      name: listfacilitylinks\n      operations:\n      - method: GET\n        name: listfacilitylinks\n        description: List links for a facility\n        call: recreation-gov.listfacilitylinks\n        with:\n          id: rest.id\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campsites\n      name: listcampsites\n      operations:\n      - method: GET\n        name: listcampsites\n        description: List campsites\n        call: recreation-gov.listcampsites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /campsites/{id}\n      name: getcampsite\n      operations:\n      - method: GET\n        name: getcampsite\n        description: Get campsite\n        call: recreation-gov.getcampsite\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recareas\n      name: listrecareas\n      operations:\n      - method: GET\n        name: listrecareas\n        description: List recreation areas\n        call: recreation-gov.listrecareas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recareas/{id}\n      name: getrecarea\n      operations:\n\
  \      - method: GET\n        name: getrecarea\n        description: Get recreation area\n        call: recreation-gov.getrecarea\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recareas/{id}/activities\n      name: listrecareaactivities\n      operations:\n      - method: GET\n        name: listrecareaactivities\n        description: List activities for a recreation area\n        call: recreation-gov.listrecareaactivities\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recareas/{id}/facilities\n      name: listrecareafacilities\n      operations:\n      - method: GET\n        name: listrecareafacilities\n        description: List facilities for a recreation area\n        call: recreation-gov.listrecareafacilities\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /recareas/{id}/media\n      name: listrecareamedia\n      operations:\n      - method: GET\n        name: listrecareamedia\n        description: List media for a recreation area\n        call: recreation-gov.listrecareamedia\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tours\n      name: listtours\n      operations:\n      - method: GET\n        name: listtours\n        description: List tours\n        call: recreation-gov.listtours\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tours/{id}\n      name: gettour\n      operations:\n      - method: GET\n        name: gettour\n        description: Get tour\n        call: recreation-gov.gettour\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permitentrances\n      name: listpermitentrances\n      operations:\n      - method: GET\n        name:\
  \ listpermitentrances\n        description: List permit entrances\n        call: recreation-gov.listpermitentrances\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /permitentrances/{id}\n      name: getpermitentrance\n      operations:\n      - method: GET\n        name: getpermitentrance\n        description: Get permit entrance\n        call: recreation-gov.getpermitentrance\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: List events\n        call: recreation-gov.listevents\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /events/{id}\n      name: getevent\n      operations:\n      - method: GET\n        name: getevent\n        description: Get event\n        call: recreation-gov.getevent\n        with:\n         \
  \ id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /media\n      name: listmedia\n      operations:\n      - method: GET\n        name: listmedia\n        description: List media\n        call: recreation-gov.listmedia\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /links\n      name: listlinks\n      operations:\n      - method: GET\n        name: listlinks\n        description: List links\n        call: recreation-gov.listlinks\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations\n      name: listorganizations\n      operations:\n      - method: GET\n        name: listorganizations\n        description: List organizations\n        call: recreation-gov.listorganizations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/{id}\n      name: getorganization\n      operations:\n      - method: GET\n   \
  \     name: getorganization\n        description: Get organization\n        call: recreation-gov.getorganization\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: recreation-gov-mcp\n    transport: http\n    description: MCP adapter for Recreation Information Database (RIDB) API for AI agent use.\n    tools:\n    - name: listactivities\n      description: List activities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listactivities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getactivity\n      description: Get activity\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getactivity\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfacilities\n      description: List facilities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listfacilities\n      with:\n        state: tools.state\n        activity: tools.activity\n        lastupdated: tools.lastupdated\n      inputParameters:\n      - name: state\n        type: string\n        description: state\n      - name: activity\n        type: string\n        description: activity\n      - name: lastupdated\n        type: string\n        description: lastupdated\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfacility\n      description: Get facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getfacility\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n  \
  \      type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfacilityactivities\n      description: List activities for a facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listfacilityactivities\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfacilitycampsites\n      description: List campsites for a facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listfacilitycampsites\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listfacilitymedia\n      description: List media for a facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listfacilitymedia\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfacilitylinks\n      description: List links for a facility\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listfacilitylinks\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcampsites\n      description: List campsites\n      hints:\n        readOnly: true\n    \
  \    destructive: false\n        idempotent: true\n      call: recreation-gov.listcampsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcampsite\n      description: Get campsite\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getcampsite\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecareas\n      description: List recreation areas\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listrecareas\n      with:\n        state: tools.state\n      inputParameters:\n      - name: state\n        type: string\n        description: state\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrecarea\n  \
  \    description: Get recreation area\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getrecarea\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecareaactivities\n      description: List activities for a recreation area\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listrecareaactivities\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecareafacilities\n      description: List facilities for a recreation area\n      hints:\n        readOnly: true\n        destructive: false\n \
  \       idempotent: true\n      call: recreation-gov.listrecareafacilities\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecareamedia\n      description: List media for a recreation area\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listrecareamedia\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtours\n      description: List tours\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listtours\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettour\n\
  \      description: Get tour\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.gettour\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpermitentrances\n      description: List permit entrances\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listpermitentrances\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpermitentrance\n      description: Get permit entrance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getpermitentrance\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n       \
  \ required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: List events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listevents\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getevent\n      description: Get event\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getevent\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listmedia\n      description: List media\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listmedia\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ listlinks\n      description: List links\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listlinks\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganizations\n      description: List organizations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.listorganizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganization\n      description: Get organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: recreation-gov.getorganization\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    RECREATION_GOV_TOKEN: RECREATION_GOV_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/recreation-gov/refs/heads/main/capabilities/recreation-gov-capability.yaml
tags:
- Recreation
- Gov
- API
tools:
- description: List activities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listactivities
- description: Get activity
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getactivity
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
- description: List activities for a facility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilityactivities
- description: List campsites for a facility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilitycampsites
- description: List media for a facility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilitymedia
- description: List links for a facility
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfacilitylinks
- description: List campsites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcampsites
- description: Get campsite
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcampsite
- description: List recreation areas
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecareas
- description: Get recreation area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrecarea
- description: List activities for a recreation area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecareaactivities
- description: List facilities for a recreation area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecareafacilities
- description: List media for a recreation area
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecareamedia
- description: List tours
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtours
- description: Get tour
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettour
- description: List permit entrances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpermitentrances
- description: Get permit entrance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpermitentrance
- description: List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Get event
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getevent
- description: List media
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listmedia
- description: List links
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listlinks
- description: List organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizations
- description: Get organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganization
---
