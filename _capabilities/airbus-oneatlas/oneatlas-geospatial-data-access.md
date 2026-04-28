---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Oneatlas Geospatial Data Access
operations: []
personas: []
provider_name: Airbus OneAtlas
provider_slug: airbus-oneatlas
search_terms:
- imagery
- satellites
slug: oneatlas-geospatial-data-access
source_yaml: "name: Airbus OneAtlas Geospatial Data Access\ndescription: Workflow capability for searching, ordering, and downloading satellite imagery from OneAtlas\nversion: 1.0.0\ntype: workflow\nmcp_tools:\n- name: search_satellite_imagery\n  description: Search the OneAtlas catalog for satellite imagery by area of interest, date range, and cloud cover\n  inputs:\n    bbox: array\n    start_date: string\n    end_date: string\n    max_cloud_cover: number\n  outputs:\n    items: array\n    total_count: integer\n  rest_adapter:\n    ref: oneatlas-api\n    operations:\n    - searchCatalog\n- name: order_satellite_image\n  description: Place a pay-per-order request to purchase and download a specific satellite image\n  inputs:\n    item_id: string\n    delivery_format: string\n  outputs:\n    order_id: string\n    status: string\n    download_url: string\n  rest_adapter:\n    ref: oneatlas-api\n    operations:\n    - getItem\n    - downloadItem\n- name: create_tasking_order\n  description:\
  \ Request new satellite imagery acquisition of a specific area at a future date\n  inputs:\n    area_of_interest: object\n    acquisition_start: string\n    acquisition_end: string\n    priority: string\n  outputs:\n    order_id: string\n    estimated_date: string\n    status: string\n  rest_adapter:\n    ref: oneatlas-api\n    operations:\n    - createTasking\n- name: get_elevation_data\n  description: Retrieve WorldDEM elevation data for a given location or bounding box\n  inputs:\n    latitude: number\n    longitude: number\n    bbox: array\n  outputs:\n    elevation_meters: number\n    data: object\n  rest_adapter:\n    ref: oneatlas-api\n    operations:\n    - getElevation\n- name: search_radar_imagery\n  description: Search for SAR (synthetic aperture radar) satellite imagery from Airbus Radar\n  inputs:\n    bbox: array\n    start_date: string\n    end_date: string\n    polarization: string\n  outputs:\n    items: array\n    total: integer\n  rest_adapter:\n    ref: oneatlas-api\n\
  \    operations:\n    - searchRadar\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/airbus-oneatlas/refs/heads/main/capabilities/oneatlas-geospatial-data-access.yaml
tags: []
tools: []
---
