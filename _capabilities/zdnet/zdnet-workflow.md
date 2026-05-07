---
categories: []
consumed_apis: []
description: Unified workflow capability composing ZDNet APIs.
layout: capability
name: ZDNet Workflow
operations:
- description: ZDNet Get News RSS Feed
  method: GET
  name: get-news-rss-feed
  path: /v1/rss
- description: ZDNet Get Security RSS Feed
  method: GET
  name: get-security-rss-feed
  path: /v1/rss
- description: ZDNet Get Cloud RSS Feed
  method: GET
  name: get-cloud-rss-feed
  path: /v1/rss
- description: ZDNet Get AI RSS Feed
  method: GET
  name: get-ai-rss-feed
  path: /v1/rss
- description: ZDNet Get Developer RSS Feed
  method: GET
  name: get-developer-rss-feed
  path: /v1/rss
- description: ZDNet Get Innovation RSS Feed
  method: GET
  name: get-innovation-rss-feed
  path: /v1/rss
personas: []
provider_name: ZDNet
provider_slug: zdnet
search_terms:
- get innovation rss feed
- zdnet
- enterprise it
- rss get cloud rss feed
- rss get innovation rss feed
- get security rss feed
- get news rss feed
- zdnet get innovation rss feed
- technology news
- operations for rss
- rss get ai rss feed
- get ai rss feed
- rss get news rss feed
- get cloud rss feed
- zdnet get ai rss feed
- zdnet get security rss feed
- zdnet get cloud rss feed
- get developer rss feed
- media
- rss get developer rss feed
- zdnet get developer rss feed
- rss get security rss feed
- zdnet get news rss feed
slug: zdnet-workflow
source_filename: zdnet-workflow.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ZDNet Workflow\n  description: Unified workflow capability composing ZDNet APIs.\n  tags:\n  - ZDNet\n  created: '2026-05-03'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: rss\n    baseUri: https://www.zdnet.com\n    description: RSS feed endpoints from ZDNet covering enterprise IT, security, cloud, AI, development, and innovation news.\n      Each feed returns RSS 2.0 XML content.\n    resources:\n    - name: rss\n      path: /\n      description: RSS feed endpoints from ZDNet covering enterprise IT, security, cloud, AI, development, and innovation\n        news. Each feed returns RSS 2.0 XML content.\n      operations:\n      - name: get-news-rss-feed\n        method: GET\n        path: /news/rss.xml\n        description: ZDNet Get News RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n      - name: get-security-rss-feed\n        method: GET\n        path: /topic/security/rss.xml\n\
  \        description: ZDNet Get Security RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n      - name: get-cloud-rss-feed\n        method: GET\n        path: /topic/cloud/rss.xml\n        description: ZDNet Get Cloud RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n      - name: get-ai-rss-feed\n        method: GET\n        path: /topic/artificial-intelligence/rss.xml\n        description: ZDNet Get AI RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n      - name: get-developer-rss-feed\n        method: GET\n        path: /topic/developer/rss.xml\n        description: ZDNet Get Developer RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n      - name: get-innovation-rss-feed\n        method: GET\n        path: /topic/innovation/rss.xml\n        description: ZDNet Get Innovation RSS Feed\n        inputParameters: []\n        outputRawFormat: json\n  exposes:\n  - type: rest\n    port: 8080\n    namespace:\
  \ zdnet-api\n    description: Unified REST API for ZDNet\n    resources:\n    - path: /v1/rss\n      name: rss\n      description: Operations for rss\n      operations:\n      - method: GET\n        name: get-news-rss-feed\n        description: ZDNet Get News RSS Feed\n        call: rss.get-news-rss-feed\n      - method: GET\n        name: get-security-rss-feed\n        description: ZDNet Get Security RSS Feed\n        call: rss.get-security-rss-feed\n      - method: GET\n        name: get-cloud-rss-feed\n        description: ZDNet Get Cloud RSS Feed\n        call: rss.get-cloud-rss-feed\n      - method: GET\n        name: get-ai-rss-feed\n        description: ZDNet Get AI RSS Feed\n        call: rss.get-ai-rss-feed\n      - method: GET\n        name: get-developer-rss-feed\n        description: ZDNet Get Developer RSS Feed\n        call: rss.get-developer-rss-feed\n      - method: GET\n        name: get-innovation-rss-feed\n        description: ZDNet Get Innovation RSS Feed\n        call:\
  \ rss.get-innovation-rss-feed\n  - type: mcp\n    port: 9090\n    namespace: zdnet-mcp\n    transport: http\n    description: MCP server for ZDNet\n    tools:\n    - name: rss-get-news-rss-feed\n      description: ZDNet Get News RSS Feed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rss.get-news-rss-feed\n    - name: rss-get-security-rss-feed\n      description: ZDNet Get Security RSS Feed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rss.get-security-rss-feed\n    - name: rss-get-cloud-rss-feed\n      description: ZDNet Get Cloud RSS Feed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rss.get-cloud-rss-feed\n    - name: rss-get-ai-rss-feed\n      description: ZDNet Get AI RSS Feed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rss.get-ai-rss-feed\n    - name: rss-get-developer-rss-feed\n      description: ZDNet Get Developer RSS Feed\n      hints:\n        readOnly: true\n\
  \        openWorld: true\n      call: rss.get-developer-rss-feed\n    - name: rss-get-innovation-rss-feed\n      description: ZDNet Get Innovation RSS Feed\n      hints:\n        readOnly: true\n        openWorld: true\n      call: rss.get-innovation-rss-feed\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/zdnet/refs/heads/main/capabilities/zdnet-workflow.yaml
tags:
- ZDNet
tools:
- description: ZDNet Get News RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-news-rss-feed
- description: ZDNet Get Security RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-security-rss-feed
- description: ZDNet Get Cloud RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-cloud-rss-feed
- description: ZDNet Get AI RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-ai-rss-feed
- description: ZDNet Get Developer RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-developer-rss-feed
- description: ZDNet Get Innovation RSS Feed
  hints:
    openWorld: true
    readOnly: true
  name: rss-get-innovation-rss-feed
---
