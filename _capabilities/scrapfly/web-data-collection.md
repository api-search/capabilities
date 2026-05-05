---
api_specs:
- filename: scrapfly-scrape-openapi.yml
  format: yaml
  label: scrapfly-scrape
  slug: scrapfly-scrape
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/scrapfly/refs/heads/main/openapi/scrapfly-scrape-openapi.yml
categories: []
consumed_apis:
- scrapfly-scrape
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
- scrape any webpage and return its content. supports anti-bot bypass, javascript rendering for dynamic sites, proxy rotation across 190+ countries, and output in html, markdown, or plain text format.
- data extraction
- capture a full-page screenshot of any website. useful for visual verification, archiving, or accessibility testing.
- anti-bot
- scrape a webpage with session persistence, maintaining cookies and browser fingerprint across multiple requests to the same site.
- scrape url
- scrape a webpage and extract structured data using an ai prompt. returns structured json data extracted from the page content.
- browser automation
- proxies
- capture a screenshot of a specific html element using a css selector. useful for extracting visual data from specific page components.
- ai
- capture element screenshot
- extract structured data
- web scraping
- data collection
- scrape with session
- capture screenshot
- scrape with cache
- capture full page screenshot
- scrape webpage
- web page scraping with anti-bot bypass
- scrape a url with caching enabled to avoid redundant requests. ideal for repeatedly accessed urls that don't change frequently.
- scrape a url with configurable rendering and extraction
- web page screenshot capture
- screenshots
- capture a screenshot of a webpage or element
slug: web-data-collection
source_filename: web-data-collection.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Web Data Collection\"\n  description: >-\n    Unified capability for web data collection workflows using Scrapfly's\n    scraping, screenshot, and extraction APIs. Enables data engineers and\n    researchers to collect, extract, and transform web content at scale\n    with anti-bot bypass, proxy rotation, and AI-assisted extraction.\n  tags:\n    - Web Scraping\n    - Data Collection\n    - Data Extraction\n    - Screenshots\n    - Anti-Bot\n    - Proxies\n  created: \"2026-05-02\"\n  modified: \"2026-05-02\"\n\nbinds:\n  - namespace: env\n    keys:\n      SCRAPFLY_API_KEY: SCRAPFLY_API_KEY\n\ncapability:\n  consumes:\n    - import: scrapfly-scrape\n      location: ./shared/scrapfly-scrape.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: web-data-collection-api\n      description: \"Unified REST API for web data collection, scraping, and screenshot capture.\"\n      resources:\n        - path: /v1/scrape\n\
  \          name: scraping\n          description: Web page scraping with anti-bot bypass\n          operations:\n            - method: GET\n              name: scrape-url\n              description: Scrape a URL with configurable rendering and extraction\n              call: \"scrapfly-scrape.scrape-url\"\n              with:\n                url: \"rest.url\"\n                render_js: \"rest.render_js\"\n                asp: \"rest.asp\"\n                country: \"rest.country\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/screenshots\n          name: screenshots\n          description: Web page screenshot capture\n          operations:\n            - method: GET\n              name: capture-screenshot\n              description: Capture a screenshot of a webpage or element\n              call: \"scrapfly-scrape.capture-screenshot\"\n              with:\n         \
  \       url: \"rest.url\"\n                capture: \"rest.capture\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: web-data-collection-mcp\n      transport: http\n      description: \"MCP server for AI-assisted web data collection and extraction workflows.\"\n      tools:\n        - name: scrape-webpage\n          description: >-\n            Scrape any webpage and return its content. Supports anti-bot bypass,\n            JavaScript rendering for dynamic sites, proxy rotation across 190+\n            countries, and output in HTML, markdown, or plain text format.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scrapfly-scrape.scrape-url\"\n          with:\n            url: \"tools.url\"\n            render_js: \"tools.render_js\"\n            asp: \"tools.asp\"\n            country: \"tools.country\"\
  \n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: extract-structured-data\n          description: >-\n            Scrape a webpage and extract structured data using an AI prompt.\n            Returns structured JSON data extracted from the page content.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"scrapfly-scrape.scrape-url\"\n          with:\n            url: \"tools.url\"\n            extraction_prompt: \"tools.prompt\"\n            render_js: \"tools.render_js\"\n            asp: \"tools.asp\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: scrape-with-session\n          description: >-\n            Scrape a webpage with session persistence, maintaining cookies and\n            browser fingerprint across multiple requests to the same site.\n          hints:\n            readOnly: true\n\
  \          call: \"scrapfly-scrape.scrape-url\"\n          with:\n            url: \"tools.url\"\n            session: \"tools.session\"\n            render_js: \"tools.render_js\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: scrape-with-cache\n          description: >-\n            Scrape a URL with caching enabled to avoid redundant requests.\n            Ideal for repeatedly accessed URLs that don't change frequently.\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"scrapfly-scrape.scrape-url\"\n          with:\n            url: \"tools.url\"\n            cache: \"tools.cache\"\n            cache_ttl: \"tools.cache_ttl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: capture-full-page-screenshot\n          description: >-\n            Capture a full-page screenshot of any website. Useful for visual\n            verification,\
  \ archiving, or accessibility testing.\n          hints:\n            readOnly: true\n          call: \"scrapfly-scrape.capture-screenshot\"\n          with:\n            url: \"tools.url\"\n            capture: \"fullpage\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: capture-element-screenshot\n          description: >-\n            Capture a screenshot of a specific HTML element using a CSS selector.\n            Useful for extracting visual data from specific page components.\n          hints:\n            readOnly: true\n          call: \"scrapfly-scrape.capture-screenshot\"\n          with:\n            url: \"tools.url\"\n            capture: \"tools.css_selector\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
