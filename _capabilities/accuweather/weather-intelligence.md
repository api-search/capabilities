---
consumed_apis:
- accuweather
description: Unified workflow combining AccuWeather's location, conditions, forecasts, air quality, and storm tracking APIs into a single capability for weather-aware applications. Used by developers, IoT platforms, travel apps, and emergency management systems.
layout: capability
name: AccuWeather Weather Intelligence
operations:
- description: Search for weather locations by text query
  method: GET
  name: search-locations
  path: /v1/locations
- description: Get current weather conditions
  method: GET
  name: get-current-weather
  path: /v1/weather/current/{locationKey}
- description: Get hourly weather forecast
  method: GET
  name: get-hourly-forecast
  path: /v1/weather/forecast/hourly/{locationKey}
- description: Get daily weather forecast
  method: GET
  name: get-daily-forecast
  path: /v1/weather/forecast/daily/{locationKey}
- description: Get MinuteCast precipitation forecast
  method: GET
  name: get-minutecast
  path: /v1/weather/minutecast/{locationKey}
- description: Get current air quality
  method: GET
  name: get-air-quality
  path: /v1/air-quality/{locationKey}
- description: Get all active global storms
  method: GET
  name: get-active-storms
  path: /v1/storms/active/{locationKey}
personas: []
provider_name: AccuWeather
provider_slug: accuweather
search_terms:
- get daily weather forecast
- get hourly weather forecast for the next 12-120 hours
- search locations
- software developer building weather-aware applications
- get current weather conditions for a location key
- consumer weather app presenting conditions and forecasts
- current and historical weather observation data
- get current weather
- get daily forecast
- Emergency Management
- search for weather locations by partial name or query text
- get hourly air quality
- weather
- hourly weather forecast
- active and historical tropical cyclone monitoring
- get hourly forecast
- get all active global storms
- storms
- get air quality
- iot system using weather data for device automation
- get all currently active tropical storms globally
- unified weather data workflow for location search, conditions, forecasts, air quality, and storm tracking
- daily weather forecast
- meteorology
- search for weather locations
- aqi and pollutant measurement data
- get storm details
- emergency response team tracking storms and severe weather
- get minutecast
- get minutecast precipitation forecast
- get detailed tracking data for a specific tropical storm
- accuweather
- get accuweather minutecast minute-by-minute precipitation forecast
- location services
- get 1, 5, 7, 10, or 15 day weather forecast
- minute-by-minute precipitation forecast
- Mobile App
- air quality
- storm tracking
- get current air quality
- get active storms
- current weather conditions for a location
- active tropical storm tracking
- short and long-range weather prediction
- get current air quality index and pollutant data
- get hourly air quality forecast
- forecasts
- Developer
- get hourly weather forecast
- search for weather locations by text query
- air quality data
- IoT Platform
- geographic location search and resolution
- get current weather conditions
slug: weather-intelligence
tags:
- AccuWeather
- Weather
- Forecasts
- Air Quality
- Storm Tracking
- Location Services
tools:
- description: Search for weather locations by partial name or query text
  hints:
    openWorld: true
    readOnly: true
  name: search-locations
- description: Get current weather conditions for a location key
  hints:
    openWorld: true
    readOnly: true
  name: get-current-weather
- description: Get hourly weather forecast for the next 12-120 hours
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-forecast
- description: Get 1, 5, 7, 10, or 15 day weather forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-daily-forecast
- description: Get AccuWeather MinuteCast minute-by-minute precipitation forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-minutecast
- description: Get current air quality index and pollutant data
  hints:
    openWorld: true
    readOnly: true
  name: get-air-quality
- description: Get hourly air quality forecast
  hints:
    openWorld: true
    readOnly: true
  name: get-hourly-air-quality
- description: Get all currently active tropical storms globally
  hints:
    openWorld: true
    readOnly: true
  name: get-active-storms
- description: Get detailed tracking data for a specific tropical storm
  hints:
    openWorld: true
    readOnly: true
  name: get-storm-details
---
