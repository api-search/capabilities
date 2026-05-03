---
api_specs:
- filename: soax-web-data-api-openapi.yml
  format: yaml
  label: soax-web-data
  slug: soax-web-data
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/soax/refs/heads/main/openapi/soax-web-data-api-openapi.yml
- filename: soax-proxy-management-api-openapi.yml
  format: yaml
  label: soax-proxy-mgmt
  slug: soax-proxy-mgmt
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/soax/refs/heads/main/openapi/soax-proxy-management-api-openapi.yml
categories: []
consumed_apis:
- soax-web-data
- soax-proxy-mgmt
description: Unified web data collection workflow combining SOAX's Web Data API and Proxy Management API. Enables data engineers, analysts, and developers to scrape public web data at scale with automatic CAPTCHA bypass, JavaScript rendering, geo-targeted proxy selection, and structured data extraction from SERP and e-commerce sites.
layout: capability
name: SOAX Data Collection
operations:
- description: Fetch fully rendered HTML, screenshots, or Markdown from any public web page
  method: POST
  name: fetch-content
  path: /v1/fetch
- description: Extract structured search results from Google, Bing, or other search engines
  method: POST
  name: fetch-serp
  path: /v1/serp
- description: Extract real-time price, stock, and product details from e-commerce pages
  method: POST
  name: fetch-product
  path: /v1/ecommerce
- description: List all whitelisted IPs in proxy package slots
  method: GET
  name: list-whitelisted-ips
  path: /v1/proxy/whitelist
- description: List all cities available for proxy geo-targeting
  method: GET
  name: list-cities
  path: /v1/proxy/cities
- description: List mobile carriers available for mobile proxy selection
  method: GET
  name: list-carriers
  path: /v1/proxy/carriers
personas: []
provider_name: SOAX
provider_slug: soax
search_terms:
- web scraping
- available mobile carriers for mobile proxy targeting
- extract real-time price, stock, and product details from e-commerce pages
- available cities for geo-targeted proxy selection
- list proxy cities
- proxy management
- list wifi isps
- list all cities available for proxy geo-targeting
- list cities
- extract structured search results from google, bing, or other search engines
- list proxy regions
- fetch web content
- anti-bot bypass
- serp
- datacenter proxies
- fetch product
- data collection
- extract structured search engine results from google, bing, or other search engines with geo-targeting
- fetch ecommerce data
- list whitelisted ips
- fetch serp data
- e-commerce product pricing and inventory data
- geo targeting
- extract real-time pricing, stock levels, and product details from e-commerce websites
- fetch serp
- list all ip addresses whitelisted in soax proxy package slots
- residential proxies
- data extraction
- extract rendered web content from any public url
- extract fully rendered html, screenshots, or markdown from any public web page with automatic captcha bypass and anti-bot protection
- soax
- fetch content
- list mobile carriers
- mobile proxies
- fetch fully rendered html, screenshots, or markdown from any public web page
- search engine result page data
- list all cities available for soax geo-targeted proxy selection
- list mobile carriers available for soax mobile proxy targeting
- list all regions/states available for soax geo-targeted proxy selection
- ecommerce
- list wifi isps available for soax residential proxy targeting
- proxy
- manage ip whitelist for proxy authentication
- list carriers
- list all whitelisted ips in proxy package slots
- list mobile carriers available for mobile proxy selection
slug: data-collection
source_filename: data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"SOAX Data Collection\"\n  description: >-\n    Unified web data collection workflow combining SOAX's Web Data API and Proxy Management API. Enables data engineers, analysts, and developers to scrape public web data at scale with automatic CAPTCHA bypass, JavaScript rendering, geo-targeted proxy selection, and structured data extraction from SERP and e-commerce sites.\n  tags:\n    - SOAX\n    - Web Scraping\n    - Data Collection\n    - Proxy Management\n    - Anti-Bot Bypass\n    - SERP\n    - Ecommerce\n    - Geo Targeting\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SOAX_API_SECRET: SOAX_API_SECRET\n      SOAX_API_KEY: SOAX_API_KEY\n      SOAX_PACKAGE_KEY: SOAX_PACKAGE_KEY\n\ncapability:\n  consumes:\n    - import: soax-web-data\n      location: ./shared/soax-web-data-api.yaml\n    - import: soax-proxy-mgmt\n      location: ./shared/soax-proxy-management-api.yaml\n\n\
  \  exposes:\n    - type: rest\n      port: 8080\n      namespace: soax-data-collection-api\n      description: \"Unified REST API for SOAX web data collection, SERP extraction, e-commerce data, and proxy management.\"\n      resources:\n        - path: /v1/fetch\n          name: web-content\n          description: \"Extract rendered web content from any public URL\"\n          operations:\n            - method: POST\n              name: fetch-content\n              description: \"Fetch fully rendered HTML, screenshots, or Markdown from any public web page\"\n              call: \"soax-web-data.fetch-web-content\"\n              with:\n                url: \"rest.url\"\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/serp\n          name: search-results\n          description: \"Search engine result page data\"\n          operations:\n            - method: POST\n        \
  \      name: fetch-serp\n              description: \"Extract structured search results from Google, Bing, or other search engines\"\n              call: \"soax-web-data.fetch-serp-data\"\n              with:\n                query: \"rest.query\"\n                search_engine: \"rest.search_engine\"\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/ecommerce\n          name: product-data\n          description: \"E-commerce product pricing and inventory data\"\n          operations:\n            - method: POST\n              name: fetch-product\n              description: \"Extract real-time price, stock, and product details from e-commerce pages\"\n              call: \"soax-web-data.fetch-ecommerce-data\"\n              with:\n                url: \"rest.url\"\n                extract: \"rest.extract\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/proxy/whitelist\n          name: ip-whitelist\n          description: \"Manage IP whitelist for proxy authentication\"\n          operations:\n            - method: GET\n              name: list-whitelisted-ips\n              description: \"List all whitelisted IPs in proxy package slots\"\n              call: \"soax-proxy-mgmt.list-whitelisted-ips\"\n              with:\n                package_key: \"{{SOAX_PACKAGE_KEY}}\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.slots\"\n\n        - path: /v1/proxy/cities\n          name: proxy-cities\n          description: \"Available cities for geo-targeted proxy selection\"\n          operations:\n            - method: GET\n              name: list-cities\n              description: \"List all cities available for proxy geo-targeting\"\n              call: \"soax-proxy-mgmt.list-cities\"\n              with:\n                country:\
  \ \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.cities\"\n\n        - path: /v1/proxy/carriers\n          name: mobile-carriers\n          description: \"Available mobile carriers for mobile proxy targeting\"\n          operations:\n            - method: GET\n              name: list-carriers\n              description: \"List mobile carriers available for mobile proxy selection\"\n              call: \"soax-proxy-mgmt.list-carriers\"\n              with:\n                country: \"rest.country\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.carriers\"\n\n    - type: mcp\n      port: 9090\n      namespace: soax-data-collection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted web data collection, competitive intelligence, and market research using SOAX proxies.\"\n      tools:\n        - name: fetch-web-content\n          description: \"Extract\
  \ fully rendered HTML, screenshots, or Markdown from any public web page with automatic CAPTCHA bypass and anti-bot protection\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"soax-web-data.fetch-web-content\"\n          with:\n            url: \"tools.url\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-serp-data\n          description: \"Extract structured search engine results from Google, Bing, or other search engines with geo-targeting\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"soax-web-data.fetch-serp-data\"\n          with:\n            query: \"tools.query\"\n            search_engine: \"tools.search_engine\"\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: fetch-ecommerce-data\n\
  \          description: \"Extract real-time pricing, stock levels, and product details from e-commerce websites\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"soax-web-data.fetch-ecommerce-data\"\n          with:\n            url: \"tools.url\"\n            extract: \"tools.extract\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-whitelisted-ips\n          description: \"List all IP addresses whitelisted in SOAX proxy package slots\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"soax-proxy-mgmt.list-whitelisted-ips\"\n          with:\n            package_key: \"{{SOAX_PACKAGE_KEY}}\"\n          outputParameters:\n            - type: object\n              mapping: \"$.slots\"\n\n        - name: list-proxy-cities\n          description: \"List all cities available for SOAX geo-targeted proxy selection\"\n          hints:\n    \
  \        readOnly: true\n            openWorld: false\n          call: \"soax-proxy-mgmt.list-cities\"\n          with:\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.cities\"\n\n        - name: list-proxy-regions\n          description: \"List all regions/states available for SOAX geo-targeted proxy selection\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"soax-proxy-mgmt.list-regions\"\n          with:\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.regions\"\n\n        - name: list-mobile-carriers\n          description: \"List mobile carriers available for SOAX mobile proxy targeting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"soax-proxy-mgmt.list-carriers\"\n          with:\n            country: \"tools.country\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.carriers\"\n\n        - name: list-wifi-isps\n          description: \"List WiFi ISPs available for SOAX residential proxy targeting\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"soax-proxy-mgmt.list-wifi-isps\"\n          with:\n            country: \"tools.country\"\n          outputParameters:\n            - type: object\n              mapping: \"$.isps\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/soax/refs/heads/main/capabilities/data-collection.yaml
tags:
- SOAX
- Web Scraping
- Data Collection
- Proxy Management
- Anti-Bot Bypass
- SERP
- Ecommerce
- Geo Targeting
tools:
- description: Extract fully rendered HTML, screenshots, or Markdown from any public web page with automatic CAPTCHA bypass and anti-bot protection
  hints:
    openWorld: true
    readOnly: true
  name: fetch-web-content
- description: Extract structured search engine results from Google, Bing, or other search engines with geo-targeting
  hints:
    openWorld: true
    readOnly: true
  name: fetch-serp-data
- description: Extract real-time pricing, stock levels, and product details from e-commerce websites
  hints:
    openWorld: true
    readOnly: true
  name: fetch-ecommerce-data
- description: List all IP addresses whitelisted in SOAX proxy package slots
  hints:
    openWorld: false
    readOnly: true
  name: list-whitelisted-ips
- description: List all cities available for SOAX geo-targeted proxy selection
  hints:
    openWorld: false
    readOnly: true
  name: list-proxy-cities
- description: List all regions/states available for SOAX geo-targeted proxy selection
  hints:
    openWorld: false
    readOnly: true
  name: list-proxy-regions
- description: List mobile carriers available for SOAX mobile proxy targeting
  hints:
    openWorld: false
    readOnly: true
  name: list-mobile-carriers
- description: List WiFi ISPs available for SOAX residential proxy targeting
  hints:
    openWorld: false
    readOnly: true
  name: list-wifi-isps
---
