---
categories: []
consumed_apis: []
description: The Astronomy Picture of the Day (APOD) API provides access to NASA's popular APOD service, returning the astronomy picture or video of the day along with a brief explanation written by a professional astronomer.
layout: capability
name: NASA Astronomy Picture of the Day (APOD) API
operations:
- description: NASA Get Astronomy Picture of the Day
  method: GET
  name: getapod
  path: /planetary/apod
personas: []
provider_name: NASA
provider_slug: nasa
search_terms:
- space
- getapod
- science
- nasa
- nasa get astronomy picture of the day
- api
- government
slug: nasa-capability
source_filename: nasa-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NASA Astronomy Picture of the Day (APOD) API\n  description: The Astronomy Picture of the Day (APOD) API provides access to NASA's popular APOD service, returning the astronomy\n    picture or video of the day along with a brief explanation written by a professional astronomer.\n  tags:\n  - Nasa\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nasa\n    baseUri: https://api.nasa.gov\n    description: NASA Astronomy Picture of the Day (APOD) API HTTP API.\n    resources:\n    - name: planetary-apod\n      path: /planetary/apod\n      operations:\n      - name: getapod\n        method: GET\n        description: NASA Get Astronomy Picture of the Day\n        inputParameters:\n        - name: api_key\n          in: query\n          type: string\n          required: true\n          description: API key for authentication. Use DEMO_KEY for testing.\n        - name: date\n\
  \          in: query\n          type: string\n          description: The date of the APOD image to retrieve (YYYY-MM-DD).\n        - name: start_date\n          in: query\n          type: string\n          description: The start of a date range for multiple APOD images.\n        - name: end_date\n          in: query\n          type: string\n          description: The end of a date range. Defaults to today.\n        - name: count\n          in: query\n          type: integer\n          description: Return a specified number of random APOD images.\n        - name: thumbs\n          in: query\n          type: boolean\n          description: Return URL of video thumbnail if media type is video.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: nasa-rest\n    description: REST adapter for NASA Astronomy Picture of the Day (APOD) API.\n    resources:\n    -\
  \ path: /planetary/apod\n      name: getapod\n      operations:\n      - method: GET\n        name: getapod\n        description: NASA Get Astronomy Picture of the Day\n        call: nasa.getapod\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: nasa-mcp\n    transport: http\n    description: MCP adapter for NASA Astronomy Picture of the Day (APOD) API for AI agent use.\n    tools:\n    - name: getapod\n      description: NASA Get Astronomy Picture of the Day\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: nasa.getapod\n      with:\n        api_key: tools.api_key\n        date: tools.date\n        start_date: tools.start_date\n        end_date: tools.end_date\n        count: tools.count\n        thumbs: tools.thumbs\n      inputParameters:\n      - name: api_key\n        type: string\n        description: API key for authentication. Use DEMO_KEY for testing.\n\
  \        required: true\n      - name: date\n        type: string\n        description: The date of the APOD image to retrieve (YYYY-MM-DD).\n      - name: start_date\n        type: string\n        description: The start of a date range for multiple APOD images.\n      - name: end_date\n        type: string\n        description: The end of a date range. Defaults to today.\n      - name: count\n        type: integer\n        description: Return a specified number of random APOD images.\n      - name: thumbs\n        type: boolean\n        description: Return URL of video thumbnail if media type is video.\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nasa/refs/heads/main/capabilities/nasa-capability.yaml
tags:
- Nasa
- API
tools:
- description: NASA Get Astronomy Picture of the Day
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapod
---
