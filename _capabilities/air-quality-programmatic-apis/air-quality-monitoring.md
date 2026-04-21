---
consumed_apis:
- aqicn
description: Unified workflow for querying real-time air quality data, monitoring station health, and spatial air quality analysis. Used by environmental monitoring applications and public health systems.
layout: capability
name: Air Quality Monitoring Workflow
operations:
- description: Get current AQI for a city
  method: GET
  name: get-aqi-by-city
  path: /v1/air-quality/city/{city}
- description: Get AQI for coordinates
  method: GET
  name: get-aqi-by-coordinates
  path: /v1/air-quality/coordinates
- description: Search stations by keyword
  method: GET
  name: search-stations
  path: /v1/stations/search
personas: []
provider_name: Air Quality Programmatic APIs
provider_slug: air-quality-programmatic-apis
search_terms:
- real-time data
- open data
- air quality
- get current aqi for a city
- monitoring
- iot
- get aqi by city
- government data
- query real-time aqi and search monitoring stations
- epa
- search for air quality monitoring stations by city or station name
- search stations
- search monitoring stations
- get real-time air quality index (aqi) and pollutant data for a city
- app developer integrating air quality data into mobile or web applications
- search stations by keyword
- researcher or analyst studying air quality trends and patterns
- air quality by coordinates
- search air quality stations
- get aqi for coordinates
- get real-time aqi for a geographic location using latitude and longitude
- air quality by city name
- Developer
- public health
- environment
- Environmental Analyst
- get aqi by coordinates
slug: air-quality-monitoring
tags:
- Air Quality
- Environment
- Public Health
- Open Data
- Monitoring
tools:
- description: Get real-time air quality index (AQI) and pollutant data for a city
  hints:
    openWorld: true
    readOnly: true
  name: get-aqi-by-city
- description: Get real-time AQI for a geographic location using latitude and longitude
  hints:
    openWorld: true
    readOnly: true
  name: get-aqi-by-coordinates
- description: Search for air quality monitoring stations by city or station name
  hints:
    openWorld: true
    readOnly: true
  name: search-air-quality-stations
---
