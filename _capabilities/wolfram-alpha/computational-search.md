---
categories: []
consumed_apis: []
description: Comprehensive computational search capability combining the Full Results API (complete pod-based results) and LLM API (AI-optimized results) for applications requiring deep computational intelligence. Used by search platforms, educational tools, and research applications needing rich multi-format results.
layout: capability
name: Wolfram|Alpha Computational Search
operations:
- description: Get complete Wolfram|Alpha results with all pods and formats.
  method: GET
  name: compute-full
  path: /v1/compute
- description: Get Wolfram|Alpha results formatted for LLM processing.
  method: GET
  name: compute-for-llm
  path: /v1/compute/llm
personas: []
provider_name: Wolfram|Alpha
provider_slug: wolfram-alpha
search_terms:
- full and llm apis for search platforms and educational tools
- education
- natural language processing
- research
- llm-optimized computational results.
- AI Developer
- augmenting search platforms with computational intelligence
- query wolfram|alpha and receive computational results formatted for llm consumption. includes structured text with interpretation and result data.
- building chatbots and voice assistants with factual answer capabilities
- full results
- Platform Developer
- compute for llm
- Search Engineer
- get complete wolfram|alpha computational results with all data pods. returns structured json with math, science, geography, and more.
- computational knowledge
- compute full
- ai
- artificial intelligence
- get wolfram|alpha results formatted for llm processing.
- full computational results with pod-based output.
- get complete wolfram|alpha results with all pods and formats.
- search
- computation
- building ai applications and llm integrations using wolfram knowledge
- science
- wolfram alpha
- integrating wolfram computational capabilities into educational platforms
- combines llm api, short answers, and spoken results for ai applications
- math
- Chatbot Engineer
- compute full results
slug: computational-search
source_filename: computational-search.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Wolfram|Alpha Computational Search\n  description: Comprehensive computational search capability combining the Full Results API (complete pod-based results) and\n    LLM API (AI-optimized results) for applications requiring deep computational intelligence. Used by search platforms, educational\n    tools, and research applications needing rich multi-format results.\n  tags:\n  - Computation\n  - Education\n  - Full Results\n  - Math\n  - Research\n  - Science\n  - Search\n  - Wolfram Alpha\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WOLFRAM_ALPHA_APP_ID: WOLFRAM_ALPHA_APP_ID\ncapability:\n  consumes:\n  - type: http\n    namespace: wolfram-full\n    baseUri: https://api.wolframalpha.com/v2\n    description: Wolfram|Alpha Full Results API with complete pod data.\n    authentication:\n      type: apikey\n      key: appid\n      value: '{{WOLFRAM_ALPHA_APP_ID}}'\n      placement: query\n    resources:\n\
  \    - name: queries\n      path: /query\n      description: Submit queries for full pod-based computational results.\n      operations:\n      - name: query-full-results\n        method: GET\n        description: Submit a natural language query for full results with disambiguation and drilldown.\n        inputParameters:\n        - name: input\n          in: query\n          type: string\n          required: true\n          description: URL-encoded query string.\n        - name: output\n          in: query\n          type: string\n          required: false\n          description: 'Response format: xml or json.'\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: 'Content formats: image, plaintext, mathml, etc.'\n        - name: includepodid\n          in: query\n          type: string\n          required: false\n          description: Include only pods with these IDs.\n        - name: units\n          in: query\n    \
  \      type: string\n          required: false\n          description: 'Measurement system: metric or imperial.'\n        - name: timeout\n          in: query\n          type: integer\n          required: false\n          description: Maximum processing time in seconds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: wolfram-llm\n    baseUri: https://www.wolframalpha.com/api/v1\n    description: Wolfram|Alpha LLM API for computational knowledge results.\n    authentication:\n      type: apikey\n      key: appid\n      value: '{{WOLFRAM_ALPHA_APP_ID}}'\n      placement: query\n    resources:\n    - name: queries\n      path: /llm-api\n      description: Submit natural language queries for LLM-optimized computational results.\n      operations:\n      - name: query-llm-api\n        method: GET\n        description: Submit a natural language query and receive computational results\
  \ formatted for LLM consumption.\n        inputParameters:\n        - name: input\n          in: query\n          type: string\n          required: true\n          description: URL-encoded natural language query string.\n        - name: maxchars\n          in: query\n          type: integer\n          required: false\n          description: Maximum characters in response. Default 6800.\n        - name: units\n          in: query\n          type: string\n          required: false\n          description: 'Measurement system: metric or imperial.'\n        - name: timezone\n          in: query\n          type: string\n          required: false\n          description: IANA timezone name for context.\n        - name: latlong\n          in: query\n          type: string\n          required: false\n          description: Latitude,longitude for location-aware results.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \  exposes:\n  - type: rest\n    port: 8081\n    namespace: wolfram-search-api\n    description: Unified REST API for Wolfram|Alpha computational search.\n    resources:\n    - path: /v1/compute\n      name: computations\n      description: Full computational results with pod-based output.\n      operations:\n      - method: GET\n        name: compute-full\n        description: Get complete Wolfram|Alpha results with all pods and formats.\n        call: wolfram-full.query-full-results\n        with:\n          input: rest.input\n          output: rest.output\n          format: rest.format\n          includepodid: rest.includepodid\n          units: rest.units\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/compute/llm\n      name: llm-computations\n      description: LLM-optimized computational results.\n      operations:\n      - method: GET\n        name: compute-for-llm\n        description: Get Wolfram|Alpha results formatted for LLM processing.\n\
  \        call: wolfram-llm.query-llm-api\n        with:\n          input: rest.input\n          maxchars: rest.maxchars\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9091\n    namespace: wolfram-search-mcp\n    transport: http\n    description: MCP server for AI-assisted computational search and scientific queries.\n    tools:\n    - name: compute-full-results\n      description: Get complete Wolfram|Alpha computational results with all data pods. Returns structured JSON with math,\n        science, geography, and more.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wolfram-full.query-full-results\n      with:\n        input: tools.input\n        output: tools.output\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: compute-for-llm\n      description: Query Wolfram|Alpha and receive computational results formatted for LLM consumption. Includes\
  \ structured\n        text with interpretation and result data.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: wolfram-llm.query-llm-api\n      with:\n        input: tools.input\n        maxchars: tools.maxchars\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/wolfram-alpha/refs/heads/main/capabilities/computational-search.yaml
tags:
- Computation
- Education
- Full Results
- Math
- Research
- Science
- Search
- Wolfram Alpha
tools:
- description: Get complete Wolfram|Alpha computational results with all data pods. Returns structured JSON with math, science, geography, and more.
  hints:
    openWorld: true
    readOnly: true
  name: compute-full-results
- description: Query Wolfram|Alpha and receive computational results formatted for LLM consumption. Includes structured text with interpretation and result data.
  hints:
    openWorld: true
    readOnly: true
  name: compute-for-llm
---
