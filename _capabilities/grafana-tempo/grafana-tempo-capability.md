---
categories: []
consumed_apis: []
description: Grafana Tempo HTTP API for querying traces, searching with TraceQL, and retrieving trace metadata. Tempo is an open-source, high-scale distributed tracing backend.
layout: capability
name: Grafana Tempo HTTP API
operations:
- description: Get trace by ID
  method: GET
  name: gettracebyid
  path: /api/traces/{traceID}
- description: Search for traces
  method: GET
  name: searchtraces
  path: /api/search
- description: Get search tag names
  method: GET
  name: getsearchtags
  path: /api/search/tags
- description: Get values for a tag
  method: GET
  name: getsearchtagvalues
  path: /api/search/tag/{tagName}/values
- description: Get search tag names (v2)
  method: GET
  name: getsearchtagsv2
  path: /api/v2/search/tags
- description: Get values for a tag (v2)
  method: GET
  name: getsearchtagvaluesv2
  path: /api/v2/search/tag/{tagName}/values
- description: Echo endpoint
  method: GET
  name: echo
  path: /api/echo
- description: Readiness check
  method: GET
  name: ready
  path: /ready
- description: Get build information
  method: GET
  name: getbuildinfo
  path: /status/buildinfo
- description: Get metrics summary
  method: GET
  name: getmetricssummary
  path: /api/metrics/summary
personas: []
provider_name: Grafana Tempo
provider_slug: grafana-tempo
search_terms:
- getsearchtagsv2
- getmetricssummary
- getsearchtagvaluesv2
- ready
- getbuildinfo
- get values for a tag
- getsearchtagvalues
- gettracebyid
- searchtraces
- open source
- get search tag names (v2)
- get search tag names
- search for traces
- get build information
- grafana
- api
- tempo
- observability
- echo
- readiness check
- get trace by id
- getsearchtags
- get metrics summary
- echo endpoint
- distributed tracing
- microservices
- get values for a tag (v2)
slug: grafana-tempo-capability
source_filename: grafana-tempo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Grafana Tempo HTTP API\n  description: Grafana Tempo HTTP API for querying traces, searching with TraceQL, and retrieving trace metadata. Tempo is\n    an open-source, high-scale distributed tracing backend.\n  tags:\n  - Grafana\n  - Tempo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: grafana-tempo\n    baseUri: http://localhost:3200\n    description: Grafana Tempo HTTP API HTTP API.\n    resources:\n    - name: api-traces-traceid\n      path: /api/traces/{traceID}\n      operations:\n      - name: gettracebyid\n        method: GET\n        description: Get trace by ID\n        inputParameters:\n        - name: traceID\n          in: path\n          type: string\n          required: true\n          description: Trace ID in hex format\n        - name: start\n          in: query\n          type: integer\n          description: Start of time range in Unix epoch seconds\n\
  \        - name: end\n          in: query\n          type: integer\n          description: End of time range in Unix epoch seconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-search\n      path: /api/search\n      operations:\n      - name: searchtraces\n        method: GET\n        description: Search for traces\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: TraceQL query string\n        - name: tags\n          in: query\n          type: string\n          description: Tag-based search in logfmt format, e.g. \"service.name=myservice error=true\"\n        - name: minDuration\n          in: query\n          type: string\n          description: Minimum trace duration, e.g. \"1.5s\" or \"500ms\"\n        - name: maxDuration\n          in: query\n          type: string\n          description: Maximum trace duration\n        -\
  \ name: limit\n          in: query\n          type: integer\n          description: Maximum number of traces to return\n        - name: start\n          in: query\n          type: integer\n          description: Start of time range in Unix epoch seconds\n        - name: end\n          in: query\n          type: integer\n          description: End of time range in Unix epoch seconds\n        - name: spss\n          in: query\n          type: integer\n          description: Spans per span set, limits spans returned per set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-search-tags\n      path: /api/search/tags\n      operations:\n      - name: getsearchtags\n        method: GET\n        description: Get search tag names\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          description: Scope of tags to return (resource, span, or intrinsic)\n\
  \        - name: start\n          in: query\n          type: integer\n          description: Start of time range in Unix epoch seconds\n        - name: end\n          in: query\n          type: integer\n          description: End of time range in Unix epoch seconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-search-tag-tagname-values\n      path: /api/search/tag/{tagName}/values\n      operations:\n      - name: getsearchtagvalues\n        method: GET\n        description: Get values for a tag\n        inputParameters:\n        - name: tagName\n          in: path\n          type: string\n          required: true\n          description: The tag name to lookup values for\n        - name: q\n          in: query\n          type: string\n          description: TraceQL query to filter values by\n        - name: start\n          in: query\n          type: integer\n          description: Start of\
  \ time range in Unix epoch seconds\n        - name: end\n          in: query\n          type: integer\n          description: End of time range in Unix epoch seconds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-search-tags\n      path: /api/v2/search/tags\n      operations:\n      - name: getsearchtagsv2\n        method: GET\n        description: Get search tag names (v2)\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          description: Scope of tags to return\n        - name: start\n          in: query\n          type: integer\n        - name: end\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-search-tag-tagname-values\n      path: /api/v2/search/tag/{tagName}/values\n      operations:\n  \
  \    - name: getsearchtagvaluesv2\n        method: GET\n        description: Get values for a tag (v2)\n        inputParameters:\n        - name: tagName\n          in: path\n          type: string\n          required: true\n        - name: q\n          in: query\n          type: string\n          description: TraceQL query to filter values\n        - name: start\n          in: query\n          type: integer\n        - name: end\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-echo\n      path: /api/echo\n      operations:\n      - name: echo\n        method: GET\n        description: Echo endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ready\n      path: /ready\n      operations:\n      - name: ready\n        method: GET\n        description: Readiness\
  \ check\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: status-buildinfo\n      path: /status/buildinfo\n      operations:\n      - name: getbuildinfo\n        method: GET\n        description: Get build information\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-metrics-summary\n      path: /api/metrics/summary\n      operations:\n      - name: getmetricssummary\n        method: GET\n        description: Get metrics summary\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: TraceQL query to compute metrics from\n        - name: groupBy\n          in: query\n          type: string\n          description: Attribute to group metrics by\n        - name: start\n          in: query\n          type: integer\n        - name:\
  \ end\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: grafana-tempo-rest\n    description: REST adapter for Grafana Tempo HTTP API.\n    resources:\n    - path: /api/traces/{traceID}\n      name: gettracebyid\n      operations:\n      - method: GET\n        name: gettracebyid\n        description: Get trace by ID\n        call: grafana-tempo.gettracebyid\n        with:\n          traceID: rest.traceID\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/search\n      name: searchtraces\n      operations:\n      - method: GET\n        name: searchtraces\n        description: Search for traces\n        call: grafana-tempo.searchtraces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/search/tags\n      name: getsearchtags\n  \
  \    operations:\n      - method: GET\n        name: getsearchtags\n        description: Get search tag names\n        call: grafana-tempo.getsearchtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/search/tag/{tagName}/values\n      name: getsearchtagvalues\n      operations:\n      - method: GET\n        name: getsearchtagvalues\n        description: Get values for a tag\n        call: grafana-tempo.getsearchtagvalues\n        with:\n          tagName: rest.tagName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/search/tags\n      name: getsearchtagsv2\n      operations:\n      - method: GET\n        name: getsearchtagsv2\n        description: Get search tag names (v2)\n        call: grafana-tempo.getsearchtagsv2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/v2/search/tag/{tagName}/values\n      name: getsearchtagvaluesv2\n      operations:\n    \
  \  - method: GET\n        name: getsearchtagvaluesv2\n        description: Get values for a tag (v2)\n        call: grafana-tempo.getsearchtagvaluesv2\n        with:\n          tagName: rest.tagName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/echo\n      name: echo\n      operations:\n      - method: GET\n        name: echo\n        description: Echo endpoint\n        call: grafana-tempo.echo\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ready\n      name: ready\n      operations:\n      - method: GET\n        name: ready\n        description: Readiness check\n        call: grafana-tempo.ready\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /status/buildinfo\n      name: getbuildinfo\n      operations:\n      - method: GET\n        name: getbuildinfo\n        description: Get build information\n        call: grafana-tempo.getbuildinfo\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /api/metrics/summary\n      name: getmetricssummary\n      operations:\n      - method: GET\n        name: getmetricssummary\n        description: Get metrics summary\n        call: grafana-tempo.getmetricssummary\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: grafana-tempo-mcp\n    transport: http\n    description: MCP adapter for Grafana Tempo HTTP API for AI agent use.\n    tools:\n    - name: gettracebyid\n      description: Get trace by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.gettracebyid\n      with:\n        traceID: tools.traceID\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: traceID\n        type: string\n        description: Trace ID in hex format\n        required: true\n      - name: start\n        type: integer\n    \
  \    description: Start of time range in Unix epoch seconds\n      - name: end\n        type: integer\n        description: End of time range in Unix epoch seconds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchtraces\n      description: Search for traces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.searchtraces\n      with:\n        q: tools.q\n        tags: tools.tags\n        minDuration: tools.minDuration\n        maxDuration: tools.maxDuration\n        limit: tools.limit\n        start: tools.start\n        end: tools.end\n        spss: tools.spss\n      inputParameters:\n      - name: q\n        type: string\n        description: TraceQL query string\n      - name: tags\n        type: string\n        description: Tag-based search in logfmt format, e.g. \"service.name=myservice error=true\"\n      - name: minDuration\n        type: string\n        description: Minimum\
  \ trace duration, e.g. \"1.5s\" or \"500ms\"\n      - name: maxDuration\n        type: string\n        description: Maximum trace duration\n      - name: limit\n        type: integer\n        description: Maximum number of traces to return\n      - name: start\n        type: integer\n        description: Start of time range in Unix epoch seconds\n      - name: end\n        type: integer\n        description: End of time range in Unix epoch seconds\n      - name: spss\n        type: integer\n        description: Spans per span set, limits spans returned per set\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsearchtags\n      description: Get search tag names\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.getsearchtags\n      with:\n        scope: tools.scope\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: scope\n        type: string\n  \
  \      description: Scope of tags to return (resource, span, or intrinsic)\n      - name: start\n        type: integer\n        description: Start of time range in Unix epoch seconds\n      - name: end\n        type: integer\n        description: End of time range in Unix epoch seconds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsearchtagvalues\n      description: Get values for a tag\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.getsearchtagvalues\n      with:\n        tagName: tools.tagName\n        q: tools.q\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: tagName\n        type: string\n        description: The tag name to lookup values for\n        required: true\n      - name: q\n        type: string\n        description: TraceQL query to filter values by\n      - name: start\n        type: integer\n        description: Start of\
  \ time range in Unix epoch seconds\n      - name: end\n        type: integer\n        description: End of time range in Unix epoch seconds\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsearchtagsv2\n      description: Get search tag names (v2)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.getsearchtagsv2\n      with:\n        scope: tools.scope\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: scope\n        type: string\n        description: Scope of tags to return\n      - name: start\n        type: integer\n        description: start\n      - name: end\n        type: integer\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsearchtagvaluesv2\n      description: Get values for a tag (v2)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n\
  \      call: grafana-tempo.getsearchtagvaluesv2\n      with:\n        tagName: tools.tagName\n        q: tools.q\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: tagName\n        type: string\n        description: tagName\n        required: true\n      - name: q\n        type: string\n        description: TraceQL query to filter values\n      - name: start\n        type: integer\n        description: start\n      - name: end\n        type: integer\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: echo\n      description: Echo endpoint\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.echo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: ready\n      description: Readiness check\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.ready\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbuildinfo\n      description: Get build information\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.getbuildinfo\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmetricssummary\n      description: Get metrics summary\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: grafana-tempo.getmetricssummary\n      with:\n        q: tools.q\n        groupBy: tools.groupBy\n        start: tools.start\n        end: tools.end\n      inputParameters:\n      - name: q\n        type: string\n        description: TraceQL query to compute metrics from\n        required: true\n      - name: groupBy\n        type: string\n        description: Attribute to group metrics by\n      - name: start\n        type: integer\n        description: start\n      - name: end\n  \
  \      type: integer\n        description: end\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/grafana-tempo/refs/heads/main/capabilities/grafana-tempo-capability.yaml
tags:
- Grafana
- Tempo
- API
tools:
- description: Get trace by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettracebyid
- description: Search for traces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchtraces
- description: Get search tag names
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsearchtags
- description: Get values for a tag
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsearchtagvalues
- description: Get search tag names (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsearchtagsv2
- description: Get values for a tag (v2)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsearchtagvaluesv2
- description: Echo endpoint
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: echo
- description: Readiness check
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ready
- description: Get build information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuildinfo
- description: Get metrics summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmetricssummary
---
