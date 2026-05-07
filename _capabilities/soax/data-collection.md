---
categories: []
consumed_apis: []
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
- extract structured search results from google, bing, or other search engines
- extract real-time pricing, stock levels, and product details from e-commerce websites
- list mobile carriers available for soax mobile proxy targeting
- fetch content
- fetch serp
- extract rendered web content from any public url
- search engine result page data
- extract real-time price, stock, and product details from e-commerce pages
- list whitelisted ips
- list all cities available for proxy geo-targeting
- anti-bot bypass
- extract fully rendered html, screenshots, or markdown from any public web page with automatic captcha bypass and anti-bot protection
- ecommerce
- list proxy cities
- data collection
- serp
- list mobile carriers available for mobile proxy selection
- list all cities available for soax geo-targeted proxy selection
- available cities for geo-targeted proxy selection
- list mobile carriers
- data extraction
- fetch product
- list proxy regions
- list cities
- list carriers
- datacenter proxies
- manage ip whitelist for proxy authentication
- fetch serp data
- extract structured search engine results from google, bing, or other search engines with geo-targeting
- list all whitelisted ips in proxy package slots
- fetch ecommerce data
- list wifi isps available for soax residential proxy targeting
- fetch web content
- mobile proxies
- list all ip addresses whitelisted in soax proxy package slots
- available mobile carriers for mobile proxy targeting
- fetch fully rendered html, screenshots, or markdown from any public web page
- residential proxies
- e-commerce product pricing and inventory data
- list wifi isps
- proxy management
- list all regions/states available for soax geo-targeted proxy selection
- geo targeting
- web scraping
- soax
- proxy
slug: data-collection
source_filename: data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: SOAX Data Collection\n  description: Unified web data collection workflow combining SOAX's Web Data API and Proxy Management API. Enables data engineers,\n    analysts, and developers to scrape public web data at scale with automatic CAPTCHA bypass, JavaScript rendering, geo-targeted\n    proxy selection, and structured data extraction from SERP and e-commerce sites.\n  tags:\n  - SOAX\n  - Web Scraping\n  - Data Collection\n  - Proxy Management\n  - Anti-Bot Bypass\n  - SERP\n  - Ecommerce\n  - Geo Targeting\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SOAX_API_SECRET: SOAX_API_SECRET\n    SOAX_API_KEY: SOAX_API_KEY\n    SOAX_PACKAGE_KEY: SOAX_PACKAGE_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: soax-web-data\n    baseUri: https://scraping.soax.com\n    description: SOAX Web Data API for extracting content from any public website.\n    authentication:\n      type: apikey\n\
  \      key: X-SOAX-API-Secret\n      value: '{{SOAX_API_SECRET}}'\n      placement: header\n    resources:\n    - name: web-content\n      path: /v2/webdata/fetch-content\n      description: Fetch fully rendered content from any URL\n      operations:\n      - name: fetch-web-content\n        method: POST\n        description: Extract fully rendered HTML, screenshots, XHR, or Markdown from any public web page\n        inputParameters:\n        - name: url\n          in: body\n          type: string\n          required: true\n          description: Target URL to fetch\n        - name: country\n          in: body\n          type: string\n          required: false\n          description: Country code for proxy geo-targeting\n        - name: proxy_type\n          in: body\n          type: integer\n          required: false\n          description: Proxy type (1=residential, 2=mobile, 3=datacenter)\n        - name: return_body\n          in: body\n          type: boolean\n          required:\
  \ false\n          description: Return rendered HTML body\n        - name: return_screenshot\n          in: body\n          type: boolean\n          required: false\n          description: Return PNG screenshot\n        - name: return_xhr\n          in: body\n          type: boolean\n          required: false\n          description: Return XHR background responses\n        - name: return_markdown\n          in: body\n          type: boolean\n          required: false\n          description: Return Markdown version of content\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            proxy_settings:\n              country: '{{tools.country}}'\n              type: '{{tools.proxy_type}}'\n            response:\n              body: '{{tools.return_body}}'\n              screenshot: '{{tools.return_screenshot}}'\n          \
  \    xhr: '{{tools.return_xhr}}'\n              markdown: '{{tools.return_markdown}}'\n    - name: serp\n      path: /v2/webdata/serp\n      description: Search engine result page extraction\n      operations:\n      - name: fetch-serp-data\n        method: POST\n        description: Extract search results from Google, Bing, and other search engines\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: Search query\n        - name: search_engine\n          in: body\n          type: string\n          required: true\n          description: Target search engine (google, bing, yahoo)\n        - name: country\n          in: body\n          type: string\n          required: false\n          description: Country for localized results\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: object\n          value: $.\n        body:\n          type: json\n       \
  \   data:\n            query: '{{tools.query}}'\n            search_engine: '{{tools.search_engine}}'\n            country: '{{tools.country}}'\n    - name: ecommerce\n      path: /v2/webdata/ecommerce\n      description: E-commerce product data extraction\n      operations:\n      - name: fetch-ecommerce-data\n        method: POST\n        description: Extract real-time pricing, stock, and product details from e-commerce sites\n        inputParameters:\n        - name: url\n          in: body\n          type: string\n          required: true\n          description: Product page URL\n        - name: extract\n          in: body\n          type: array\n          required: false\n          description: Fields to extract (price, title, stock, rating, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: product\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            url: '{{tools.url}}'\n            extract:\
  \ '{{tools.extract}}'\n  - type: http\n    namespace: soax-proxy-mgmt\n    baseUri: https://partner.api.soax.com\n    description: SOAX Partner API for proxy package management.\n    authentication:\n      type: apikey\n      key: api-key\n      value: '{{SOAX_API_KEY}}'\n      placement: header\n    resources:\n    - name: ip-list\n      path: /v1/account/package/{package_key}/ip-list\n      description: Retrieve whitelisted IPs for a package\n      operations:\n      - name: list-whitelisted-ips\n        method: GET\n        description: Get all whitelisted IP slots for a proxy package\n        inputParameters:\n        - name: package_key\n          in: path\n          type: string\n          required: true\n          description: Proxy package key\n        outputRawFormat: json\n        outputParameters:\n        - name: slots\n          type: object\n          value: $.slots\n    - name: update-ip\n      path: /v1/account/package/{package_key}/update-ip\n      description: Update\
  \ whitelisted IP in a slot\n      operations:\n      - name: update-whitelisted-ip\n        method: POST\n        description: Add or update an IP address in a proxy whitelist slot\n        inputParameters:\n        - name: package_key\n          in: path\n          type: string\n          required: true\n          description: Proxy package key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n          - ip: '{{tools.ip}}'\n            slot: '{{tools.slot}}'\n            comment: '{{tools.comment}}'\n    - name: detach-ip\n      path: /v1/account/package/{package_key}/detach-ip\n      description: Remove whitelisted IP from a slot\n      operations:\n      - name: detach-whitelisted-ip\n        method: POST\n        description: Remove an IP address from a proxy whitelist slot\n        inputParameters:\n        - name: package_key\n          in: path\n \
  \         type: string\n          required: true\n          description: Proxy package key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n          - slot: '{{tools.slot}}'\n    - name: cities\n      path: /v1/geo/cities\n      description: Available cities for geo-targeting\n      operations:\n      - name: list-cities\n        method: GET\n        description: Get list of cities available for proxy geo-targeting\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by country code\n        outputRawFormat: json\n        outputParameters:\n        - name: cities\n          type: object\n          value: $.cities\n    - name: regions\n      path: /v1/geo/regions\n      description: Available regions for geo-targeting\n      operations:\n      - name: list-regions\n\
  \        method: GET\n        description: Get list of regions/states available for proxy geo-targeting\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by country code\n        outputRawFormat: json\n        outputParameters:\n        - name: regions\n          type: object\n          value: $.regions\n    - name: carriers\n      path: /v1/geo/carriers\n      description: Available mobile carriers for proxy targeting\n      operations:\n      - name: list-carriers\n        method: GET\n        description: Get list of mobile carriers available for mobile proxy targeting\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by country code\n        outputRawFormat: json\n        outputParameters:\n        - name: carriers\n          type: object\n          value: $.carriers\n    - name:\
  \ isps\n      path: /v1/geo/isps\n      description: Available WiFi ISPs for residential proxy targeting\n      operations:\n      - name: list-wifi-isps\n        method: GET\n        description: Get list of WiFi ISPs available for residential proxy targeting\n        inputParameters:\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Filter by country code\n        outputRawFormat: json\n        outputParameters:\n        - name: isps\n          type: object\n          value: $.isps\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: soax-data-collection-api\n    description: Unified REST API for SOAX web data collection, SERP extraction, e-commerce data, and proxy management.\n    resources:\n    - path: /v1/fetch\n      name: web-content\n      description: Extract rendered web content from any public URL\n      operations:\n      - method: POST\n        name: fetch-content\n        description: Fetch fully\
  \ rendered HTML, screenshots, or Markdown from any public web page\n        call: soax-web-data.fetch-web-content\n        with:\n          url: rest.url\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/serp\n      name: search-results\n      description: Search engine result page data\n      operations:\n      - method: POST\n        name: fetch-serp\n        description: Extract structured search results from Google, Bing, or other search engines\n        call: soax-web-data.fetch-serp-data\n        with:\n          query: rest.query\n          search_engine: rest.search_engine\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/ecommerce\n      name: product-data\n      description: E-commerce product pricing and inventory data\n      operations:\n      - method: POST\n        name: fetch-product\n        description: Extract real-time price,\
  \ stock, and product details from e-commerce pages\n        call: soax-web-data.fetch-ecommerce-data\n        with:\n          url: rest.url\n          extract: rest.extract\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/proxy/whitelist\n      name: ip-whitelist\n      description: Manage IP whitelist for proxy authentication\n      operations:\n      - method: GET\n        name: list-whitelisted-ips\n        description: List all whitelisted IPs in proxy package slots\n        call: soax-proxy-mgmt.list-whitelisted-ips\n        with:\n          package_key: '{{SOAX_PACKAGE_KEY}}'\n        outputParameters:\n        - type: object\n          mapping: $.slots\n    - path: /v1/proxy/cities\n      name: proxy-cities\n      description: Available cities for geo-targeted proxy selection\n      operations:\n      - method: GET\n        name: list-cities\n        description: List all cities available for proxy geo-targeting\n        call: soax-proxy-mgmt.list-cities\n\
  \        with:\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.cities\n    - path: /v1/proxy/carriers\n      name: mobile-carriers\n      description: Available mobile carriers for mobile proxy targeting\n      operations:\n      - method: GET\n        name: list-carriers\n        description: List mobile carriers available for mobile proxy selection\n        call: soax-proxy-mgmt.list-carriers\n        with:\n          country: rest.country\n        outputParameters:\n        - type: object\n          mapping: $.carriers\n  - type: mcp\n    port: 9090\n    namespace: soax-data-collection-mcp\n    transport: http\n    description: MCP server for AI-assisted web data collection, competitive intelligence, and market research using SOAX\n      proxies.\n    tools:\n    - name: fetch-web-content\n      description: Extract fully rendered HTML, screenshots, or Markdown from any public web page with automatic CAPTCHA bypass\n        and\
  \ anti-bot protection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: soax-web-data.fetch-web-content\n      with:\n        url: tools.url\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-serp-data\n      description: Extract structured search engine results from Google, Bing, or other search engines with geo-targeting\n      hints:\n        readOnly: true\n        openWorld: true\n      call: soax-web-data.fetch-serp-data\n      with:\n        query: tools.query\n        search_engine: tools.search_engine\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: fetch-ecommerce-data\n      description: Extract real-time pricing, stock levels, and product details from e-commerce websites\n      hints:\n        readOnly: true\n        openWorld: true\n      call: soax-web-data.fetch-ecommerce-data\n      with:\n        url: tools.url\n\
  \        extract: tools.extract\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-whitelisted-ips\n      description: List all IP addresses whitelisted in SOAX proxy package slots\n      hints:\n        readOnly: true\n        openWorld: false\n      call: soax-proxy-mgmt.list-whitelisted-ips\n      with:\n        package_key: '{{SOAX_PACKAGE_KEY}}'\n      outputParameters:\n      - type: object\n        mapping: $.slots\n    - name: list-proxy-cities\n      description: List all cities available for SOAX geo-targeted proxy selection\n      hints:\n        readOnly: true\n        openWorld: false\n      call: soax-proxy-mgmt.list-cities\n      with:\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.cities\n    - name: list-proxy-regions\n      description: List all regions/states available for SOAX geo-targeted proxy selection\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ soax-proxy-mgmt.list-regions\n      with:\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.regions\n    - name: list-mobile-carriers\n      description: List mobile carriers available for SOAX mobile proxy targeting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: soax-proxy-mgmt.list-carriers\n      with:\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.carriers\n    - name: list-wifi-isps\n      description: List WiFi ISPs available for SOAX residential proxy targeting\n      hints:\n        readOnly: true\n        openWorld: false\n      call: soax-proxy-mgmt.list-wifi-isps\n      with:\n        country: tools.country\n      outputParameters:\n      - type: object\n        mapping: $.isps\n"
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
