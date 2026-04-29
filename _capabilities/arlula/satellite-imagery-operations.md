---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Satellite Imagery Operations
operations: []
personas: []
provider_name: Arlula
provider_slug: arlula
search_terms:
- satellites
- geospatial
- imagery
- remote sensing
- earth observation
slug: satellite-imagery-operations
source_yaml: "name: Satellite Imagery Operations\nversion: 1.0.0-alpha1\ndescription: >-\n  Workflow capability for discovering, ordering, and downloading satellite imagery\n  through the Arlula API. Covers archive search, tasking for future captures,\n  and retrieval of completed order datasets.\nnaftiko:\n  version: 1.0.0-alpha1\napis:\n  - name: Arlula API\n    shared: capabilities/shared/arlula-api.yaml\ntools:\n  - name: test-connection\n    description: Test API credentials and verify connectivity to the Arlula platform.\n    operation: test-connection\n  - name: search-archive\n    description: Search the satellite archive for available scenes within an area of interest and date range.\n    operation: search-archive\n  - name: order-archive-scene\n    description: Place an order for an available archive satellite scene.\n    operation: order-archive-scene\n  - name: search-tasking\n    description: Search for future satellite tasking opportunities for a given area of interest.\n \
  \   operation: search-tasking\n  - name: order-tasking\n    description: Place a tasking order for future satellite image capture.\n    operation: order-tasking\n  - name: cancel-tasking\n    description: Cancel an existing tasking order before capture occurs.\n    operation: cancel-tasking\n  - name: list-orders\n    description: List all orders for the authenticated account.\n    operation: list-orders\n  - name: get-order\n    description: Retrieve detailed information for a specific order including campaigns and datasets.\n    operation: get-order\n  - name: list-datasets\n    description: List all datasets produced from capture campaigns.\n    operation: list-datasets\n  - name: get-dataset\n    description: Retrieve details for a specific dataset including available downloadable resources.\n    operation: get-dataset\n  - name: download-resource\n    description: Download a specific resource such as a GeoTIFF, preview image, or metadata file.\n    operation: download-resource\npersonas:\n\
  \  - name: Geospatial Analyst\n    description: Analyst who searches the archive and orders imagery for analysis workflows.\n  - name: Remote Sensing Engineer\n    description: Engineer who manages tasking orders and processes downloaded datasets.\nports:\n  rest: 8080\n  mcp: 9090\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/arlula/refs/heads/main/capabilities/satellite-imagery-operations.yaml
tags: []
tools: []
---
