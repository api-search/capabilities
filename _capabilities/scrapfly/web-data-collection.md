---
categories: []
consumed_apis: []
description: Unified capability for web data collection workflows using Scrapfly's scraping, screenshot, and extraction APIs. Enables data engineers and researchers to collect, extract, and transform web content at scale with anti-bot bypass, proxy rotation, and AI-assisted extraction.
layout: capability
name: Web Data Collection
operations:
- description: Scrape a URL with configurable rendering and extraction
  method: GET
  name: scrape-url
  path: /v1/scrape
- description: Capture a screenshot of a webpage or element
  method: GET
  name: capture-screenshot
  path: /v1/screenshots
personas: []
provider_name: Scrapfly
provider_slug: scrapfly
search_terms:
- capture a screenshot of a specific html element using a css selector. useful for extracting visual data from specific page components.
- capture element screenshot
- scrape with session
- web page scraping with anti-bot bypass
- proxies
- anti-bot
- extract structured data
- data collection
- data extraction
- scrape with cache
- web page screenshot capture
- ai
- web scraping
- capture screenshot
- scrape a url with configurable rendering and extraction
- scrape a webpage with session persistence, maintaining cookies and browser fingerprint across multiple requests to the same site.
- screenshots
- browser automation
- scrape webpage
- capture a screenshot of a webpage or element
- capture full page screenshot
- scrape a webpage and extract structured data using an ai prompt. returns structured json data extracted from the page content.
- scrape url
- scrape any webpage and return its content. supports anti-bot bypass, javascript rendering for dynamic sites, proxy rotation across 190+ countries, and output in html, markdown, or plain text format.
- capture a full-page screenshot of any website. useful for visual verification, archiving, or accessibility testing.
- scrape a url with caching enabled to avoid redundant requests. ideal for repeatedly accessed urls that don't change frequently.
slug: web-data-collection
source_filename: web-data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Web Data Collection\n  description: Unified capability for web data collection workflows using Scrapfly's scraping, screenshot, and extraction\n    APIs. Enables data engineers and researchers to collect, extract, and transform web content at scale with anti-bot bypass,\n    proxy rotation, and AI-assisted extraction.\n  tags:\n  - Web Scraping\n  - Data Collection\n  - Data Extraction\n  - Screenshots\n  - Anti-Bot\n  - Proxies\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SCRAPFLY_API_KEY: SCRAPFLY_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: scrapfly-scrape\n    baseUri: https://api.scrapfly.io\n    description: Scrapfly Web Scraping API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{SCRAPFLY_API_KEY}}'\n      placement: query\n    resources:\n    - name: scraping\n      path: /scrape\n      description: Core web scraping endpoint\n      operations:\n\
  \      - name: scrape-url\n        method: GET\n        description: Scrape any URL with anti-bot bypass and optional JS rendering\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description: Target URL to scrape\n        - name: render_js\n          in: query\n          type: boolean\n          required: false\n          description: Enable JavaScript rendering\n        - name: asp\n          in: query\n          type: boolean\n          required: false\n          description: Enable Anti Scraping Protection bypass\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Proxy country (ISO alpha-2)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Output format (raw, clean_html, markdown, text)\n        - name: extraction_prompt\n          in: query\n          type: string\n\
  \          required: false\n          description: LLM prompt for structured data extraction\n        - name: session\n          in: query\n          type: string\n          required: false\n          description: Session name for persistent cookies\n        - name: cache\n          in: query\n          type: boolean\n          required: false\n          description: Enable response caching\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: screenshot\n      path: /screenshot\n      description: Screenshot capture endpoint\n      operations:\n      - name: capture-screenshot\n        method: GET\n        description: Capture a screenshot of a web page or element\n        inputParameters:\n        - name: url\n          in: query\n          type: string\n          required: true\n          description: Target URL to screenshot\n        - name: capture\n          in: query\n          type: string\n \
  \         required: false\n          description: Capture scope (fullpage or CSS selector)\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Image format (png, jpeg, webp)\n        - name: country\n          in: query\n          type: string\n          required: false\n          description: Proxy country for geo-specific capture\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: web-data-collection-api\n    description: Unified REST API for web data collection, scraping, and screenshot capture.\n    resources:\n    - path: /v1/scrape\n      name: scraping\n      description: Web page scraping with anti-bot bypass\n      operations:\n      - method: GET\n        name: scrape-url\n        description: Scrape a URL with configurable rendering and extraction\n        call: scrapfly-scrape.scrape-url\n\
  \        with:\n          url: rest.url\n          render_js: rest.render_js\n          asp: rest.asp\n          country: rest.country\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/screenshots\n      name: screenshots\n      description: Web page screenshot capture\n      operations:\n      - method: GET\n        name: capture-screenshot\n        description: Capture a screenshot of a webpage or element\n        call: scrapfly-scrape.capture-screenshot\n        with:\n          url: rest.url\n          capture: rest.capture\n          format: rest.format\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: web-data-collection-mcp\n    transport: http\n    description: MCP server for AI-assisted web data collection and extraction workflows.\n    tools:\n    - name: scrape-webpage\n      description: Scrape any webpage and return its content. Supports\
  \ anti-bot bypass, JavaScript rendering for dynamic sites,\n        proxy rotation across 190+ countries, and output in HTML, markdown, or plain text format.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scrapfly-scrape.scrape-url\n      with:\n        url: tools.url\n        render_js: tools.render_js\n        asp: tools.asp\n        country: tools.country\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: extract-structured-data\n      description: Scrape a webpage and extract structured data using an AI prompt. Returns structured JSON data extracted\n        from the page content.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: scrapfly-scrape.scrape-url\n      with:\n        url: tools.url\n        extraction_prompt: tools.prompt\n        render_js: tools.render_js\n        asp: tools.asp\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ scrape-with-session\n      description: Scrape a webpage with session persistence, maintaining cookies and browser fingerprint across multiple\n        requests to the same site.\n      hints:\n        readOnly: true\n      call: scrapfly-scrape.scrape-url\n      with:\n        url: tools.url\n        session: tools.session\n        render_js: tools.render_js\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: scrape-with-cache\n      description: Scrape a URL with caching enabled to avoid redundant requests. Ideal for repeatedly accessed URLs that\n        don't change frequently.\n      hints:\n        readOnly: true\n        idempotent: true\n      call: scrapfly-scrape.scrape-url\n      with:\n        url: tools.url\n        cache: tools.cache\n        cache_ttl: tools.cache_ttl\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-full-page-screenshot\n      description: Capture a full-page screenshot of any website.\
  \ Useful for visual verification, archiving, or accessibility\n        testing.\n      hints:\n        readOnly: true\n      call: scrapfly-scrape.capture-screenshot\n      with:\n        url: tools.url\n        capture: fullpage\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: capture-element-screenshot\n      description: Capture a screenshot of a specific HTML element using a CSS selector. Useful for extracting visual data\n        from specific page components.\n      hints:\n        readOnly: true\n      call: scrapfly-scrape.capture-screenshot\n      with:\n        url: tools.url\n        capture: tools.css_selector\n        format: tools.format\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/scrapfly/refs/heads/main/capabilities/web-data-collection.yaml
tags:
- Web Scraping
- Data Collection
- Data Extraction
- Screenshots
- Anti-Bot
- Proxies
tools:
- description: Scrape any webpage and return its content. Supports anti-bot bypass, JavaScript rendering for dynamic sites, proxy rotation across 190+ countries, and output in HTML, markdown, or plain text format.
  hints:
    openWorld: true
    readOnly: true
  name: scrape-webpage
- description: Scrape a webpage and extract structured data using an AI prompt. Returns structured JSON data extracted from the page content.
  hints:
    openWorld: true
    readOnly: true
  name: extract-structured-data
- description: Scrape a webpage with session persistence, maintaining cookies and browser fingerprint across multiple requests to the same site.
  hints:
    readOnly: true
  name: scrape-with-session
- description: Scrape a URL with caching enabled to avoid redundant requests. Ideal for repeatedly accessed URLs that don't change frequently.
  hints:
    idempotent: true
    readOnly: true
  name: scrape-with-cache
- description: Capture a full-page screenshot of any website. Useful for visual verification, archiving, or accessibility testing.
  hints:
    readOnly: true
  name: capture-full-page-screenshot
- description: Capture a screenshot of a specific HTML element using a CSS selector. Useful for extracting visual data from specific page components.
  hints:
    readOnly: true
  name: capture-element-screenshot
---
