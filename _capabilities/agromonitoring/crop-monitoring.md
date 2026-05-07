---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Crop Monitoring
operations: []
personas: []
provider_name: Agromonitoring
provider_slug: agromonitoring
search_terms:
- agriculture
- weather
- satellite imagery
- vegetation indices
- precision agriculture
- remote sensing
slug: crop-monitoring
source_filename: crop-monitoring.yaml
source_heading: Capability Spec
source_yaml: "name: Crop Monitoring\ndescription: Workflow-oriented capability composition for monitoring crop health, vegetation indices, and environmental conditions using Agromonitoring satellite and sensor data.\nversion: \"1.0\"\ntags:\n  - Agriculture\n  - Crop Monitoring\n  - Satellite Imagery\n  - Remote Sensing\n\ntools:\n  - name: register_field\n    description: Register a new agricultural field polygon using GeoJSON coordinates\n    capability: agromonitoring-api.createPolygon\n    inputs:\n      - name: name\n        type: string\n        description: Human-readable name for the field\n      - name: geo_json\n        type: object\n        description: GeoJSON geometry defining the field boundary\n    outputs:\n      - name: polygon_id\n        type: string\n        description: Unique identifier for the registered polygon\n\n  - name: list_fields\n    description: List all registered field polygons for the account\n    capability: agromonitoring-api.listPolygons\n    outputs:\n\
  \      - name: polygons\n        type: array\n        description: Array of registered polygon objects\n\n  - name: get_satellite_imagery\n    description: Search for available satellite imagery for a field within a time window\n    capability: agromonitoring-api.searchSatelliteImages\n    inputs:\n      - name: polygon_id\n        type: string\n        description: Field polygon identifier\n      - name: start_date\n        type: integer\n        description: Start of search period as Unix timestamp\n      - name: end_date\n        type: integer\n        description: End of search period as Unix timestamp\n    outputs:\n      - name: images\n        type: array\n        description: List of available satellite images with cloud coverage and resolution\n\n  - name: get_vegetation_indices\n    description: Retrieve NDVI, EVI, and other vegetation index time series for a field\n    capability: agromonitoring-api.getNdviHistory\n    inputs:\n      - name: polygon_id\n        type: string\n\
  \        description: Field polygon identifier\n      - name: start_date\n        type: integer\n        description: Start date as Unix timestamp\n      - name: end_date\n        type: integer\n        description: End date as Unix timestamp\n    outputs:\n      - name: ndvi_history\n        type: array\n        description: Time series of vegetation index measurements (NDVI, EVI, EVI2, NRI, DSWI, LSWI)\n\n  - name: get_current_weather\n    description: Get current weather conditions including temperature, humidity, and wind for a field\n    capability: agromonitoring-api.getCurrentWeather\n    inputs:\n      - name: polygon_id\n        type: string\n        description: Field polygon identifier\n    outputs:\n      - name: weather\n        type: object\n        description: Current weather data including temperature, pressure, humidity, wind, and clouds\n\n  - name: get_weather_forecast\n    description: Get multi-day weather forecast for planning field operations\n    capability: agromonitoring-api.getWeatherForecast\n\
  \    inputs:\n      - name: polygon_id\n        type: string\n        description: Field polygon identifier\n    outputs:\n      - name: forecast\n        type: array\n        description: Daily weather forecast records\n\n  - name: get_soil_conditions\n    description: Get soil temperature (surface and 10cm depth) and moisture content for a field\n    capability: agromonitoring-api.getSoilData\n    inputs:\n      - name: polygon_id\n        type: string\n        description: Field polygon identifier\n    outputs:\n      - name: soil_data\n        type: object\n        description: Soil temperature at surface and 10cm depth, plus moisture level\n\n  - name: get_uv_index\n    description: Get UV index data for assessing sun exposure and radiation levels\n    capability: agromonitoring-api.getUvIndex\n    inputs:\n      - name: polygon_id\n        type: string\n        description: Field polygon identifier\n    outputs:\n      - name: uv_data\n        type: object\n        description: UV\
  \ index value with timestamp\n\nworkflows:\n  - name: Field Health Assessment\n    description: Complete crop health assessment combining satellite imagery, vegetation indices, weather, and soil data for a registered field\n    steps:\n      - tool: get_satellite_imagery\n        description: Find recent cloud-free satellite passes\n      - tool: get_vegetation_indices\n        description: Analyze NDVI trends to detect stress or disease\n      - tool: get_soil_conditions\n        description: Check soil moisture and temperature for irrigation decisions\n      - tool: get_current_weather\n        description: Assess current growing conditions\n\n  - name: Field Registration and Baseline\n    description: Register a new field and establish baseline monitoring data\n    steps:\n      - tool: register_field\n        description: Create polygon boundary for the field\n      - tool: get_vegetation_indices\n        description: Establish NDVI baseline\n      - tool: get_soil_conditions\n   \
  \     description: Record initial soil conditions\n      - tool: get_weather_forecast\n        description: Plan initial management activities\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/agromonitoring/refs/heads/main/capabilities/crop-monitoring.yaml
tags: []
tools: []
---
