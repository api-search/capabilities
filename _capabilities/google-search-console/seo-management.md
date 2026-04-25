---
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
- submit sitemap
- list all search console sites for the authenticated user.
- google
- get details for a specific site.
- analytics
- query search analytics data with filters.
- query search analytics
- webmaster tools
- delete sitemap
- list sitemaps
- delete a sitemap.
- query search traffic data with filters and dimensions.
- search console
- delete site
- get site
- submit a sitemap.
- inspect url
- manage search console sites.
- webmaster
- inspect a url for index status and rich results.
- submit a sitemap for crawling.
- remove a site from search console.
- add a site to search console.
- get sitemap details.
- inspect urls for indexing status.
- get sitemap
- inspect a url for index status, crawl info, mobile usability, and rich results.
- delete a previously submitted sitemap.
- query search traffic data.
- seo
- get details for a specific search console site.
- search
- list sitemaps submitted for a site.
- get details for a specific sitemap.
- list sites
- list sitemaps for a site.
- add site
- list all search console sites.
- manage sitemaps.
slug: seo-management
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
