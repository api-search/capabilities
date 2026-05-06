---
categories: []
consumed_apis: []
description: The Google Indexing API allows site owners to notify Google when pages are added or removed. It enables direct notification to Google to crawl pages, leading to fresher content in search results. It is primarily intended for websites with job postings or livestream structured data.
layout: capability
name: Google Indexing API
operations:
- description: Google Indexing Publish URL Notification
  method: POST
  name: publishurlnotification
  path: /urlNotifications:publish
- description: Google Indexing Get URL Notification Metadata
  method: GET
  name: geturlnotificationmetadata
  path: /urlNotifications/metadata
personas: []
provider_name: Google Indexing
provider_slug: google-indexing
search_terms:
- urls
- google
- api
- google indexing get url notification metadata
- crawling
- seo
- search
- geturlnotificationmetadata
- google indexing publish url notification
- indexing
- publishurlnotification
slug: google-indexing-capability
source_filename: google-indexing-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Indexing API\n  description: The Google Indexing API allows site owners to notify Google when pages are added or removed. It enables direct\n    notification to Google to crawl pages, leading to fresher content in search results. It is primarily intended for websites\n    with job postings or livestream structured data.\n  tags:\n  - Google\n  - Indexing\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-indexing\n    baseUri: https://indexing.googleapis.com/v3\n    description: Google Indexing API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_INDEXING_TOKEN}}'\n    resources:\n    - name: urlnotifications-publish\n      path: /urlNotifications:publish\n      operations:\n      - name: publishurlnotification\n        method: POST\n        description: Google Indexing Publish URL Notification\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: urlnotifications-metadata\n      path: /urlNotifications/metadata\n      operations:\n      - name: geturlnotificationmetadata\n        method: GET\n        description: Google Indexing Get URL Notification Metadata\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description: The URL to get notification metadata for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-indexing-rest\n    description: REST adapter for Google Indexing API.\n    resources:\n    - path: /urlNotifications:publish\n      name: publishurlnotification\n      operations:\n      - method: POST\n        name: publishurlnotification\n        description: Google Indexing Publish URL Notification\n\
  \        call: google-indexing.publishurlnotification\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /urlNotifications/metadata\n      name: geturlnotificationmetadata\n      operations:\n      - method: GET\n        name: geturlnotificationmetadata\n        description: Google Indexing Get URL Notification Metadata\n        call: google-indexing.geturlnotificationmetadata\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-indexing-mcp\n    transport: http\n    description: MCP adapter for Google Indexing API for AI agent use.\n    tools:\n    - name: publishurlnotification\n      description: Google Indexing Publish URL Notification\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-indexing.publishurlnotification\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: geturlnotificationmetadata\n\
  \      description: Google Indexing Get URL Notification Metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-indexing.geturlnotificationmetadata\n      with:\n        url: tools.url\n      inputParameters:\n      - name: url\n        type: string\n        description: The URL to get notification metadata for.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_INDEXING_TOKEN: GOOGLE_INDEXING_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-indexing/refs/heads/main/capabilities/google-indexing-capability.yaml
tags:
- Google
- Indexing
- API
tools:
- description: Google Indexing Publish URL Notification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publishurlnotification
- description: Google Indexing Get URL Notification Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: geturlnotificationmetadata
---
