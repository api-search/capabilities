---
categories: []
consumed_apis: []
description: The PageSpeed Insights API runs Lighthouse audits on web pages and returns performance scores, Core Web Vitals metrics, Chrome User Experience Report field data, and detailed optimization opportunities and diagnostics.
layout: capability
name: Google PageSpeed PageSpeed Insights API
operations:
- description: Google PageSpeed Analyze page performance
  method: GET
  name: runpagespeed
  path: /runPagespeed
personas: []
provider_name: Google PageSpeed
provider_slug: google-pagespeed
search_terms:
- page speed
- lighthouse
- runpagespeed
- google pagespeed analyze page performance
- google
- api
- seo
- pagespeed
- web performance
- core web vitals
slug: google-pagespeed-capability
source_filename: google-pagespeed-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google PageSpeed PageSpeed Insights API\n  description: The PageSpeed Insights API runs Lighthouse audits on web pages and returns performance scores, Core Web Vitals\n    metrics, Chrome User Experience Report field data, and detailed optimization opportunities and diagnostics.\n  tags:\n  - Google\n  - Pagespeed\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-pagespeed\n    baseUri: https://www.googleapis.com/pagespeedonline/v5\n    description: Google PageSpeed PageSpeed Insights API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: key\n      value: '{{GOOGLE_PAGESPEED_TOKEN}}'\n    resources:\n    - name: runpagespeed\n      path: /runPagespeed\n      operations:\n      - name: runpagespeed\n        method: GET\n        description: Google PageSpeed Analyze page performance\n        inputParameters:\n        - name: url\n  \
  \        in: query\n          type: string\n          required: true\n          description: The URL to analyze\n        - name: strategy\n          in: query\n          type: string\n          description: The analysis strategy (desktop or mobile)\n        - name: category\n          in: query\n          type: array\n          description: Lighthouse categories to run\n        - name: locale\n          in: query\n          type: string\n          description: The locale for results (e.g. en_US)\n        - name: utm_campaign\n          in: query\n          type: string\n          description: Campaign name for analytics\n        - name: utm_source\n          in: query\n          type: string\n          description: Campaign source for analytics\n        - name: captchaToken\n          in: query\n          type: string\n          description: The captcha token for the request\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-pagespeed-rest\n    description: REST adapter for Google PageSpeed PageSpeed Insights API.\n    resources:\n    - path: /runPagespeed\n      name: runpagespeed\n      operations:\n      - method: GET\n        name: runpagespeed\n        description: Google PageSpeed Analyze page performance\n        call: google-pagespeed.runpagespeed\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-pagespeed-mcp\n    transport: http\n    description: MCP adapter for Google PageSpeed PageSpeed Insights API for AI agent use.\n    tools:\n    - name: runpagespeed\n      description: Google PageSpeed Analyze page performance\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-pagespeed.runpagespeed\n      with:\n        url: tools.url\n        strategy: tools.strategy\n        category:\
  \ tools.category\n        locale: tools.locale\n        utm_campaign: tools.utm_campaign\n        utm_source: tools.utm_source\n        captchaToken: tools.captchaToken\n      inputParameters:\n      - name: url\n        type: string\n        description: The URL to analyze\n        required: true\n      - name: strategy\n        type: string\n        description: The analysis strategy (desktop or mobile)\n      - name: category\n        type: array\n        description: Lighthouse categories to run\n      - name: locale\n        type: string\n        description: The locale for results (e.g. en_US)\n      - name: utm_campaign\n        type: string\n        description: Campaign name for analytics\n      - name: utm_source\n        type: string\n        description: Campaign source for analytics\n      - name: captchaToken\n        type: string\n        description: The captcha token for the request\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace:\
  \ env\n  keys:\n    GOOGLE_PAGESPEED_TOKEN: GOOGLE_PAGESPEED_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-pagespeed/refs/heads/main/capabilities/google-pagespeed-capability.yaml
tags:
- Google
- Pagespeed
- API
tools:
- description: Google PageSpeed Analyze page performance
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: runpagespeed
---
