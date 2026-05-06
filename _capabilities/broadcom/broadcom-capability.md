---
categories: []
consumed_apis: []
description: The VMware Aria Operations for Applications REST API (formerly Tanzu Observability by Wavefront) enables programmatic interaction with the observability service. It supports querying metrics, managing dashboards, alerts, events, sources, user accounts, API tokens, and ingesting data directly. The API uses JSON payloads over HTTPS and supports both API token and session-based authentication.
layout: capability
name: Broadcom Operations for Applications REST API
operations:
- description: Broadcom Execute a query
  method: GET
  name: querymetrics
  path: /query
- description: Broadcom List dashboards
  method: GET
  name: listdashboards
  path: /dashboard
- description: Broadcom Create a dashboard
  method: POST
  name: createdashboard
  path: /dashboard
- description: Broadcom Get a dashboard
  method: GET
  name: getdashboard
  path: /dashboard/{id}
- description: Broadcom Update a dashboard
  method: PUT
  name: updatedashboard
  path: /dashboard/{id}
- description: Broadcom Delete a dashboard
  method: DELETE
  name: deletedashboard
  path: /dashboard/{id}
- description: Broadcom List alerts
  method: GET
  name: listalerts
  path: /alert
- description: Broadcom Create an alert
  method: POST
  name: createalert
  path: /alert
- description: Broadcom Get an alert
  method: GET
  name: getalert
  path: /alert/{id}
- description: Broadcom Update an alert
  method: PUT
  name: updatealert
  path: /alert/{id}
- description: Broadcom Delete an alert
  method: DELETE
  name: deletealert
  path: /alert/{id}
- description: Broadcom List events
  method: GET
  name: listevents
  path: /event
- description: Broadcom Create an event
  method: POST
  name: createevent
  path: /event
- description: Broadcom List sources
  method: GET
  name: listsources
  path: /source
- description: Broadcom Get a source
  method: GET
  name: getsource
  path: /source/{id}
- description: Broadcom List proxies
  method: GET
  name: listproxies
  path: /proxy
- description: Broadcom Get a proxy
  method: GET
  name: getproxy
  path: /proxy/{id}
- description: Broadcom Delete a proxy
  method: DELETE
  name: deleteproxy
  path: /proxy/{id}
- description: Broadcom List API tokens
  method: GET
  name: listapitokens
  path: /api-token
- description: Broadcom Create an API token
  method: POST
  name: createapitoken
  path: /api-token
personas: []
provider_name: Broadcom
provider_slug: broadcom
search_terms:
- updatealert
- deleteproxy
- broadcom list api tokens
- gateways
- listevents
- querymetrics
- broadcom list events
- broadcom execute a query
- getdashboard
- virtualization
- broadcom delete an alert
- broadcom
- cloud infrastructure
- broadcom create a dashboard
- broadcom get a dashboard
- broadcom get an alert
- broadcom delete a dashboard
- listsources
- getsource
- updatedashboard
- getproxy
- createalert
- createevent
- broadcom update an alert
- listapitokens
- api
- deletedashboard
- broadcom delete a proxy
- observability
- broadcom list dashboards
- broadcom create an event
- broadcom list sources
- networks
- createdashboard
- listalerts
- broadcom update a dashboard
- broadcom list alerts
- deletealert
- broadcom list proxies
- management
- listproxies
- getalert
- broadcom create an alert
- broadcom get a proxy
- createapitoken
- listdashboards
- broadcom get a source
- broadcom create an api token
slug: broadcom-capability
source_filename: broadcom-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Broadcom Operations for Applications REST API\n  description: The VMware Aria Operations for Applications REST API (formerly Tanzu Observability by Wavefront) enables programmatic\n    interaction with the observability service. It supports querying metrics, managing dashboards, alerts, events, sources,\n    user accounts, API tokens, and ingesting data directly. The API uses JSON payloads over HTTPS and supports both API token\n    and session-based authentication.\n  tags:\n  - Broadcom\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: broadcom\n    baseUri: https://example.wavefront.com/api/v2\n    description: Broadcom Operations for Applications REST API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{BROADCOM_TOKEN}}'\n    resources:\n    - name: query\n      path: /query\n      operations:\n      - name: querymetrics\n        method: GET\n  \
  \      description: Broadcom Execute a query\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The query expression\n        - name: s\n          in: query\n          type: string\n          required: true\n          description: Start time in epoch seconds or ms\n        - name: e\n          in: query\n          type: string\n          description: End time in epoch seconds or ms\n        - name: g\n          in: query\n          type: string\n          description: Granularity (s, m, h, d)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard\n      path: /dashboard\n      operations:\n      - name: listdashboards\n        method: GET\n        description: Broadcom List dashboards\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n \
  \         in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdashboard\n        method: POST\n        description: Broadcom Create a dashboard\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dashboard-id\n      path: /dashboard/{id}\n      operations:\n      - name: getdashboard\n        method: GET\n        description: Broadcom Get a dashboard\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedashboard\n        method: PUT\n        description: Broadcom Update a dashboard\n        inputParameters:\n        - name: id\n          in: path\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedashboard\n        method: DELETE\n        description: Broadcom Delete a dashboard\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert\n      path: /alert\n      operations:\n      - name: listalerts\n        method: GET\n        description: Broadcom List alerts\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalert\n        method: POST\n\
  \        description: Broadcom Create an alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alert-id\n      path: /alert/{id}\n      operations:\n      - name: getalert\n        method: GET\n        description: Broadcom Get an alert\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatealert\n        method: PUT\n        description: Broadcom Update an alert\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletealert\n        method: DELETE\n        description: Broadcom Delete an\
  \ alert\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event\n      path: /event\n      operations:\n      - name: listevents\n        method: GET\n        description: Broadcom List events\n        inputParameters:\n        - name: earliestStartTimeEpochMillis\n          in: query\n          type: integer\n        - name: latestStartTimeEpochMillis\n          in: query\n          type: integer\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createevent\n        method: POST\n        description: Broadcom Create an event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: source\n      path: /source\n      operations:\n      - name: listsources\n        method: GET\n        description: Broadcom List sources\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: source-id\n      path: /source/{id}\n      operations:\n      - name: getsource\n        method: GET\n        description: Broadcom Get a source\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: proxy\n      path: /proxy\n      operations:\n      - name: listproxies\n        method: GET\n        description: Broadcom List proxies\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: proxy-id\n      path: /proxy/{id}\n      operations:\n      - name: getproxy\n        method: GET\n        description: Broadcom Get a proxy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteproxy\n        method: DELETE\n        description: Broadcom Delete a proxy\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-token\n      path: /api-token\n      operations:\n      - name: listapitokens\n        method: GET\n        description: Broadcom List API tokens\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createapitoken\n        method: POST\n        description: Broadcom Create an API token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: broadcom-rest\n    description: REST adapter for Broadcom Operations for Applications REST API.\n    resources:\n    - path: /query\n      name: querymetrics\n      operations:\n      - method: GET\n        name: querymetrics\n        description: Broadcom Execute a query\n        call: broadcom.querymetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard\n      name: listdashboards\n      operations:\n      - method: GET\n        name: listdashboards\n        description: Broadcom List dashboards\n        call: broadcom.listdashboards\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /dashboard\n      name: createdashboard\n      operations:\n      - method: POST\n        name: createdashboard\n        description: Broadcom Create a dashboard\n        call: broadcom.createdashboard\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n      name: getdashboard\n      operations:\n      - method: GET\n        name: getdashboard\n        description: Broadcom Get a dashboard\n        call: broadcom.getdashboard\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n      name: updatedashboard\n      operations:\n      - method: PUT\n        name: updatedashboard\n        description: Broadcom Update a dashboard\n        call: broadcom.updatedashboard\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dashboard/{id}\n\
  \      name: deletedashboard\n      operations:\n      - method: DELETE\n        name: deletedashboard\n        description: Broadcom Delete a dashboard\n        call: broadcom.deletedashboard\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert\n      name: listalerts\n      operations:\n      - method: GET\n        name: listalerts\n        description: Broadcom List alerts\n        call: broadcom.listalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert\n      name: createalert\n      operations:\n      - method: POST\n        name: createalert\n        description: Broadcom Create an alert\n        call: broadcom.createalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert/{id}\n      name: getalert\n      operations:\n      - method: GET\n        name: getalert\n        description: Broadcom Get an alert\n      \
  \  call: broadcom.getalert\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert/{id}\n      name: updatealert\n      operations:\n      - method: PUT\n        name: updatealert\n        description: Broadcom Update an alert\n        call: broadcom.updatealert\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alert/{id}\n      name: deletealert\n      operations:\n      - method: DELETE\n        name: deletealert\n        description: Broadcom Delete an alert\n        call: broadcom.deletealert\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event\n      name: listevents\n      operations:\n      - method: GET\n        name: listevents\n        description: Broadcom List events\n        call: broadcom.listevents\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /event\n      name: createevent\n      operations:\n      - method: POST\n        name: createevent\n        description: Broadcom Create an event\n        call: broadcom.createevent\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /source\n      name: listsources\n      operations:\n      - method: GET\n        name: listsources\n        description: Broadcom List sources\n        call: broadcom.listsources\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /source/{id}\n      name: getsource\n      operations:\n      - method: GET\n        name: getsource\n        description: Broadcom Get a source\n        call: broadcom.getsource\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy\n      name: listproxies\n      operations:\n      - method: GET\n        name: listproxies\n        description: Broadcom\
  \ List proxies\n        call: broadcom.listproxies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy/{id}\n      name: getproxy\n      operations:\n      - method: GET\n        name: getproxy\n        description: Broadcom Get a proxy\n        call: broadcom.getproxy\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /proxy/{id}\n      name: deleteproxy\n      operations:\n      - method: DELETE\n        name: deleteproxy\n        description: Broadcom Delete a proxy\n        call: broadcom.deleteproxy\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api-token\n      name: listapitokens\n      operations:\n      - method: GET\n        name: listapitokens\n        description: Broadcom List API tokens\n        call: broadcom.listapitokens\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /api-token\n      name: createapitoken\n      operations:\n      - method: POST\n        name: createapitoken\n        description: Broadcom Create an API token\n        call: broadcom.createapitoken\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: broadcom-mcp\n    transport: http\n    description: MCP adapter for Broadcom Operations for Applications REST API for AI agent use.\n    tools:\n    - name: querymetrics\n      description: Broadcom Execute a query\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.querymetrics\n      with:\n        q: tools.q\n        s: tools.s\n        e: tools.e\n        g: tools.g\n      inputParameters:\n      - name: q\n        type: string\n        description: The query expression\n        required: true\n      - name: s\n        type: string\n        description: Start time in epoch seconds\
  \ or ms\n        required: true\n      - name: e\n        type: string\n        description: End time in epoch seconds or ms\n      - name: g\n        type: string\n        description: Granularity (s, m, h, d)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdashboards\n      description: Broadcom List dashboards\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listdashboards\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdashboard\n      description: Broadcom Create a dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: broadcom.createdashboard\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdashboard\n      description: Broadcom Get a dashboard\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.getdashboard\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatedashboard\n      description: Broadcom Update a dashboard\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: broadcom.updatedashboard\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletedashboard\n      description: Broadcom Delete a dashboard\n      hints:\n \
  \       readOnly: false\n        destructive: true\n        idempotent: true\n      call: broadcom.deletedashboard\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalerts\n      description: Broadcom List alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listalerts\n      with:\n        offset: tools.offset\n        limit: tools.limit\n      inputParameters:\n      - name: offset\n        type: integer\n        description: offset\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalert\n      description: Broadcom Create an alert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n    \
  \  call: broadcom.createalert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getalert\n      description: Broadcom Get an alert\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.getalert\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatealert\n      description: Broadcom Update an alert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: broadcom.updatealert\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletealert\n      description: Broadcom Delete an alert\n      hints:\n\
  \        readOnly: false\n        destructive: true\n        idempotent: true\n      call: broadcom.deletealert\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listevents\n      description: Broadcom List events\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listevents\n      with:\n        earliestStartTimeEpochMillis: tools.earliestStartTimeEpochMillis\n        latestStartTimeEpochMillis: tools.latestStartTimeEpochMillis\n        limit: tools.limit\n      inputParameters:\n      - name: earliestStartTimeEpochMillis\n        type: integer\n        description: earliestStartTimeEpochMillis\n      - name: latestStartTimeEpochMillis\n        type: integer\n        description: latestStartTimeEpochMillis\n      - name: limit\n        type: integer\n\
  \        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createevent\n      description: Broadcom Create an event\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: broadcom.createevent\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsources\n      description: Broadcom List sources\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listsources\n      with:\n        limit: tools.limit\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsource\n      description: Broadcom Get a source\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.getsource\n      with:\n        id: tools.id\n      inputParameters:\n\
  \      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listproxies\n      description: Broadcom List proxies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listproxies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getproxy\n      description: Broadcom Get a proxy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.getproxy\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteproxy\n      description: Broadcom Delete a proxy\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: broadcom.deleteproxy\n\
  \      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapitokens\n      description: Broadcom List API tokens\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: broadcom.listapitokens\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createapitoken\n      description: Broadcom Create an API token\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: broadcom.createapitoken\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    BROADCOM_TOKEN: BROADCOM_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/broadcom/refs/heads/main/capabilities/broadcom-capability.yaml
tags:
- Broadcom
- API
tools:
- description: Broadcom Execute a query
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querymetrics
- description: Broadcom List dashboards
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdashboards
- description: Broadcom Create a dashboard
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdashboard
- description: Broadcom Get a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdashboard
- description: Broadcom Update a dashboard
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedashboard
- description: Broadcom Delete a dashboard
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedashboard
- description: Broadcom List alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalerts
- description: Broadcom Create an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalert
- description: Broadcom Get an alert
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalert
- description: Broadcom Update an alert
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatealert
- description: Broadcom Delete an alert
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletealert
- description: Broadcom List events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listevents
- description: Broadcom Create an event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createevent
- description: Broadcom List sources
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsources
- description: Broadcom Get a source
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsource
- description: Broadcom List proxies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listproxies
- description: Broadcom Get a proxy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproxy
- description: Broadcom Delete a proxy
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteproxy
- description: Broadcom List API tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapitokens
- description: Broadcom Create an API token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapitoken
---
