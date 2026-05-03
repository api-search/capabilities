---
categories:
- analytics
consumed_apis:
- search-console
description: Unified SEO management workflow combining search analytics, sitemap management, URL inspection, and site management for SEO specialists and webmasters.
layout: capability
name: Google Search Console SEO Management
operations:
- description: List all Search Console sites.
  method: GET
  name: list-sites
  path: /v1/sites
- description: Get details for a specific site.
  method: GET
  name: get-site
  path: /v1/sites
- description: Add a site to Search Console.
  method: PUT
  name: add-site
  path: /v1/sites
- description: Remove a site from Search Console.
  method: DELETE
  name: delete-site
  path: /v1/sites
- description: Query search analytics data with filters.
  method: POST
  name: query-search-analytics
  path: /v1/search-analytics
- description: List sitemaps for a site.
  method: GET
  name: list-sitemaps
  path: /v1/sitemaps
- description: Get sitemap details.
  method: GET
  name: get-sitemap
  path: /v1/sitemaps
- description: Submit a sitemap.
  method: PUT
  name: submit-sitemap
  path: /v1/sitemaps
- description: Delete a sitemap.
  method: DELETE
  name: delete-sitemap
  path: /v1/sitemaps
- description: Inspect a URL for index status and rich results.
  method: POST
  name: inspect-url
  path: /v1/url-inspection
personas: []
provider_name: Google Search Console
provider_slug: google-search-console
search_terms:
- get details for a specific search console site.
- inspect a url for index status, crawl info, mobile usability, and rich results.
- get details for a specific sitemap.
- list sitemaps for a site.
- submit sitemap
- list sites
- delete a previously submitted sitemap.
- submit a sitemap for crawling.
- analytics
- inspect a url for index status and rich results.
- get sitemap details.
- add a site to search console.
- add site
- webmaster tools
- manage sitemaps.
- get details for a specific site.
- delete sitemap
- inspect url
- search
- list sitemaps submitted for a site.
- google
- manage search console sites.
- query search analytics
- query search traffic data.
- list sitemaps
- inspect urls for indexing status.
- delete a sitemap.
- submit a sitemap.
- list all search console sites.
- search console
- list all search console sites for the authenticated user.
- query search traffic data with filters and dimensions.
- query search analytics data with filters.
- seo
- delete site
- get sitemap
- remove a site from search console.
- webmaster
- get site
slug: seo-management
source_filename: seo-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Google Search Console SEO Management\"\n  description: \"Unified SEO management workflow combining search analytics, sitemap management, URL inspection, and site management for SEO specialists and webmasters.\"\n  tags:\n    - Google\n    - Search Console\n    - SEO\n    - Analytics\n    - Webmaster\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      GOOGLE_OAUTH_TOKEN: GOOGLE_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: search-console\n      location: ./shared/search-console.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: seo-management-api\n      description: \"Unified REST API for SEO management combining search analytics, sitemaps, URL inspection, and site management.\"\n      resources:\n        - path: /v1/sites\n          name: sites\n          description: \"Manage Search Console sites.\"\n          operations:\n            - method: GET\n\
  \              name: list-sites\n              description: \"List all Search Console sites.\"\n              call: \"search-console.list-sites\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-site\n              description: \"Get details for a specific site.\"\n              call: \"search-console.get-site\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-site\n              description: \"Add a site to Search Console.\"\n              call: \"search-console.add-site\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-site\n              description:\
  \ \"Remove a site from Search Console.\"\n              call: \"search-console.delete-site\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/search-analytics\n          name: search-analytics\n          description: \"Query search traffic data.\"\n          operations:\n            - method: POST\n              name: query-search-analytics\n              description: \"Query search analytics data with filters.\"\n              call: \"search-console.query-search-analytics\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n                startDate: \"rest.startDate\"\n                endDate: \"rest.endDate\"\n                dimensions: \"rest.dimensions\"\n                type: \"rest.type\"\n                rowLimit: \"rest.rowLimit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\
  \n        - path: /v1/sitemaps\n          name: sitemaps\n          description: \"Manage sitemaps.\"\n          operations:\n            - method: GET\n              name: list-sitemaps\n              description: \"List sitemaps for a site.\"\n              call: \"search-console.list-sitemaps\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: GET\n              name: get-sitemap\n              description: \"Get sitemap details.\"\n              call: \"search-console.get-sitemap\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n                feedpath: \"rest.feedpath\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: submit-sitemap\n              description: \"Submit a sitemap.\"\n              call: \"search-console.submit-sitemap\"\
  \n              with:\n                siteUrl: \"rest.siteUrl\"\n                feedpath: \"rest.feedpath\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-sitemap\n              description: \"Delete a sitemap.\"\n              call: \"search-console.delete-sitemap\"\n              with:\n                siteUrl: \"rest.siteUrl\"\n                feedpath: \"rest.feedpath\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/url-inspection\n          name: url-inspection\n          description: \"Inspect URLs for indexing status.\"\n          operations:\n            - method: POST\n              name: inspect-url\n              description: \"Inspect a URL for index status and rich results.\"\n              call: \"search-console.inspect-url\"\n              with:\n                inspectionUrl: \"rest.inspectionUrl\"\
  \n                siteUrl: \"rest.siteUrl\"\n                languageCode: \"rest.languageCode\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: seo-management-mcp\n      transport: http\n      description: \"MCP server for AI-assisted SEO management with search analytics, sitemaps, URL inspection, and site management.\"\n      tools:\n        - name: list-sites\n          description: \"List all Search Console sites for the authenticated user.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-console.list-sites\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-site\n          description: \"Get details for a specific Search Console site.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-console.get-site\"\n        \
  \  with:\n            siteUrl: \"tools.siteUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: add-site\n          description: \"Add a site to Search Console.\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"search-console.add-site\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-site\n          description: \"Remove a site from Search Console.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"search-console.delete-site\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: query-search-analytics\n          description: \"Query search traffic data with filters and dimensions.\"\n          hints:\n       \
  \     readOnly: true\n            openWorld: true\n          call: \"search-console.query-search-analytics\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n            startDate: \"tools.startDate\"\n            endDate: \"tools.endDate\"\n            dimensions: \"tools.dimensions\"\n            type: \"tools.type\"\n            rowLimit: \"tools.rowLimit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-sitemaps\n          description: \"List sitemaps submitted for a site.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-console.list-sitemaps\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-sitemap\n          description: \"Get details for a specific sitemap.\"\n          hints:\n            readOnly: true\n            openWorld: true\n     \
  \     call: \"search-console.get-sitemap\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n            feedpath: \"tools.feedpath\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: submit-sitemap\n          description: \"Submit a sitemap for crawling.\"\n          hints:\n            readOnly: false\n            openWorld: true\n          call: \"search-console.submit-sitemap\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n            feedpath: \"tools.feedpath\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: delete-sitemap\n          description: \"Delete a previously submitted sitemap.\"\n          hints:\n            readOnly: false\n            destructive: true\n          call: \"search-console.delete-sitemap\"\n          with:\n            siteUrl: \"tools.siteUrl\"\n            feedpath: \"tools.feedpath\"\n          outputParameters:\n       \
  \     - type: object\n              mapping: \"$.\"\n        - name: inspect-url\n          description: \"Inspect a URL for index status, crawl info, mobile usability, and rich results.\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"search-console.inspect-url\"\n          with:\n            inspectionUrl: \"tools.inspectionUrl\"\n            siteUrl: \"tools.siteUrl\"\n            languageCode: \"tools.languageCode\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-search-console/refs/heads/main/capabilities/seo-management.yaml
tags:
- Google
- Search Console
- SEO
- Analytics
- Webmaster
tools:
- description: List all Search Console sites for the authenticated user.
  hints:
    openWorld: true
    readOnly: true
  name: list-sites
- description: Get details for a specific Search Console site.
  hints:
    openWorld: true
    readOnly: true
  name: get-site
- description: Add a site to Search Console.
  hints:
    openWorld: true
    readOnly: false
  name: add-site
- description: Remove a site from Search Console.
  hints:
    destructive: true
    readOnly: false
  name: delete-site
- description: Query search traffic data with filters and dimensions.
  hints:
    openWorld: true
    readOnly: true
  name: query-search-analytics
- description: List sitemaps submitted for a site.
  hints:
    openWorld: true
    readOnly: true
  name: list-sitemaps
- description: Get details for a specific sitemap.
  hints:
    openWorld: true
    readOnly: true
  name: get-sitemap
- description: Submit a sitemap for crawling.
  hints:
    openWorld: true
    readOnly: false
  name: submit-sitemap
- description: Delete a previously submitted sitemap.
  hints:
    destructive: true
    readOnly: false
  name: delete-sitemap
- description: Inspect a URL for index status, crawl info, mobile usability, and rich results.
  hints:
    openWorld: true
    readOnly: true
  name: inspect-url
---
