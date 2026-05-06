---
categories: []
consumed_apis: []
description: Workflow capability for economists, researchers, policy analysts, and data engineers to access U.S. Bureau of Labor Statistics time series data covering employment, unemployment, inflation, wages, and productivity. Combines the BLS Public Data API into a unified labor market data service.
layout: capability
name: BLS Labor Market Intelligence
operations:
- description: Retrieve historical economic indicator data for a BLS series.
  method: GET
  name: get-time-series
  path: /v1/timeseries/{seriesId}
- description: Retrieve data for multiple economic indicators simultaneously.
  method: POST
  name: get-multiple-indicators
  path: /v1/timeseries
- description: List the 25 most popular BLS economic time series.
  method: GET
  name: get-popular-indicators
  path: /v1/timeseries/popular
- description: List all available BLS survey programs and their abbreviations.
  method: GET
  name: list-surveys
  path: /v1/surveys
- description: Retrieve metadata and description for a specific BLS survey.
  method: GET
  name: get-survey
  path: /v1/surveys/{surveyId}
personas: []
provider_name: U.S. Bureau of Labor Statistics
provider_slug: u-s-bureau-of-labor-statistics
search_terms:
- list all available bls survey programs with their abbreviations. use this to discover which surveys are available before querying specific series ids.
- unified workflow for economists, researchers, and policy analysts to access bls labor market data for employment analysis, inflation monitoring, and economic research.
- economic data
- retrieve u.s. unemployment rate time series data. use series id lns14000000 for the national seasonally adjusted unemployment rate, or specify a different series id for demographic breakdowns.
- get unemployment rate
- get survey details
- discover available bls survey programs.
- get cpi inflation
- access bls time series data by series id.
- query multiple bls time series in a single request.
- labor market
- employment
- get employment statistics
- policy analysis
- access the most widely used bls economic indicator series.
- Data Engineer
- get multiple indicators
- retrieve current employment statistics (ces) data including total nonfarm employment, industry employment, and average hourly earnings.
- list bls surveys
- academic and policy research using government economic data
- Policy Analyst
- retrieve metadata and description for a specific bls survey.
- government or think tank analyst using bls indicators to inform employment policy, inflation monitoring, and economic forecasting.
- employment, unemployment, wages, and workforce statistics
- get multiple economic indicators
- get survey
- get the 25 most popular bls economic time series, optionally filtered by survey type (cps, ces, ap, etc.) to discover commonly used economic benchmark series.
- reporter using bls data to contextualize economic news stories about unemployment, inflation, wages, and job market trends.
- list the 25 most popular bls economic time series.
- bureau of labor statistics
- Economist
- academic or government economist analyzing labor market trends, wages, employment, and economic cycles using bls time series data.
- developer or data engineer integrating bls data into dashboards, data pipelines, and economic applications.
- federal government
- retrieve multiple bls economic indicators in a single api call. supports up to 50 series for comparative analysis across employment, wages, prices, and productivity metrics.
- data-driven analysis of labor and economic policy
- retrieve consumer price index (cpi) data for measuring inflation. use cuur0000sa0 for cpi-u all items, or specify a different cpi series for category-specific inflation (food, energy, housing).
- list all available bls survey programs and their abbreviations.
- economic research
- inflation
- list surveys
- get time series
- get detailed metadata for a specific bls survey program using its abbreviation (e.g., cps for current population survey, ces for current employment statistics, ap for average price data).
- get popular indicators
- labor
- retrieve data for multiple economic indicators simultaneously.
- statistics
- get details for a specific bls survey program.
- retrieve historical economic indicator data for a bls series.
slug: labor-market-intelligence
source_filename: labor-market-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: BLS Labor Market Intelligence\n  description: Workflow capability for economists, researchers, policy analysts, and data engineers to access U.S. Bureau\n    of Labor Statistics time series data covering employment, unemployment, inflation, wages, and productivity. Combines the\n    BLS Public Data API into a unified labor market data service.\n  tags:\n  - Bureau of Labor Statistics\n  - Labor Market\n  - Economic Research\n  - Policy Analysis\n  - Employment\n  - Inflation\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    BLS_API_KEY: BLS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: bls-public-data\n    baseUri: https://api.bls.gov/publicAPI/v2\n    description: BLS Public Data API v2 for time series labor statistics.\n    authentication:\n      type: apikey\n      key: registrationkey\n      value: '{{BLS_API_KEY}}'\n      placement: query\n    resources:\n\
  \    - name: time-series\n      path: /timeseries/data\n      description: Time series data for BLS economic indicators.\n      operations:\n      - name: get-single-series\n        method: GET\n        description: Retrieve time series data for a single BLS series ID.\n        inputParameters:\n        - name: seriesId\n          in: path\n          type: string\n          required: true\n          description: BLS series ID (e.g., CUUR0000SA0 for CPI).\n        - name: startyear\n          in: query\n          type: string\n          required: false\n          description: First year of data in YYYY format.\n        - name: endyear\n          in: query\n          type: string\n          required: false\n          description: Last year of data in YYYY format.\n        - name: catalog\n          in: query\n          type: boolean\n          required: false\n          description: Include catalog metadata.\n        - name: calculations\n          in: query\n          type: boolean\n  \
  \        required: false\n          description: Include net and percent change calculations.\n        - name: annualaverage\n          in: query\n          type: boolean\n          required: false\n          description: Include annual averages.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-multiple-series\n        method: POST\n        description: Retrieve data for multiple BLS series IDs in one request.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            seriesid: '{{tools.series_ids}}'\n            startyear: '{{tools.start_year}}'\n            endyear: '{{tools.end_year}}'\n            catalog: '{{tools.catalog}}'\n            calculations: '{{tools.calculations}}'\n            annualaverage: '{{tools.annual_average}}'\n\
  \    - name: popular-series\n      path: /timeseries/popular\n      description: Access to the most popular BLS time series.\n      operations:\n      - name: get-popular-series\n        method: GET\n        description: Retrieve the 25 most popular BLS series IDs.\n        inputParameters:\n        - name: survey\n          in: query\n          type: string\n          required: false\n          description: Survey abbreviation to filter popular series.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: surveys\n      path: /surveys\n      description: BLS survey metadata and catalog.\n      operations:\n      - name: get-all-surveys\n        method: GET\n        description: Retrieve metadata for all available BLS surveys.\n        inputParameters: []\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-survey-metadata\n\
  \        method: GET\n        description: Retrieve metadata for a specific BLS survey.\n        inputParameters:\n        - name: surveyId\n          in: path\n          type: string\n          required: true\n          description: Survey abbreviation (e.g., CPS, CES, AP).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: labor-market-intelligence-api\n    description: Unified REST API for BLS labor market data and economic indicators.\n    resources:\n    - path: /v1/timeseries/{seriesId}\n      name: time-series\n      description: Access BLS time series data by series ID.\n      operations:\n      - method: GET\n        name: get-time-series\n        description: Retrieve historical economic indicator data for a BLS series.\n        call: bls-public-data.get-single-series\n        with:\n          seriesId: rest.seriesId\n          startyear: rest.startyear\n\
  \          endyear: rest.endyear\n          calculations: rest.calculations\n          annualaverage: rest.annualaverage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries\n      name: multi-series\n      description: Query multiple BLS time series in a single request.\n      operations:\n      - method: POST\n        name: get-multiple-indicators\n        description: Retrieve data for multiple economic indicators simultaneously.\n        call: bls-public-data.get-multiple-series\n        with:\n          series_ids: rest.seriesid\n          start_year: rest.startyear\n          end_year: rest.endyear\n          calculations: rest.calculations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/timeseries/popular\n      name: popular-indicators\n      description: Access the most widely used BLS economic indicator series.\n      operations:\n      - method: GET\n        name: get-popular-indicators\n\
  \        description: List the 25 most popular BLS economic time series.\n        call: bls-public-data.get-popular-series\n        with:\n          survey: rest.survey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/surveys\n      name: surveys\n      description: Discover available BLS survey programs.\n      operations:\n      - method: GET\n        name: list-surveys\n        description: List all available BLS survey programs and their abbreviations.\n        call: bls-public-data.get-all-surveys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/surveys/{surveyId}\n      name: survey-detail\n      description: Get details for a specific BLS survey program.\n      operations:\n      - method: GET\n        name: get-survey\n        description: Retrieve metadata and description for a specific BLS survey.\n        call: bls-public-data.get-survey-metadata\n        with:\n          surveyId: rest.surveyId\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: labor-market-intelligence-mcp\n    transport: http\n    description: MCP server for AI-assisted labor market analysis using BLS data.\n    tools:\n    - name: get-unemployment-rate\n      description: Retrieve U.S. unemployment rate time series data. Use series ID LNS14000000 for the national seasonally\n        adjusted unemployment rate, or specify a different series ID for demographic breakdowns.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bls-public-data.get-single-series\n      with:\n        seriesId: tools.series_id\n        startyear: tools.start_year\n        endyear: tools.end_year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cpi-inflation\n      description: Retrieve Consumer Price Index (CPI) data for measuring inflation. Use CUUR0000SA0 for CPI-U All Items,\n        or specify a different\
  \ CPI series for category-specific inflation (food, energy, housing).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bls-public-data.get-single-series\n      with:\n        seriesId: tools.series_id\n        startyear: tools.start_year\n        endyear: tools.end_year\n        calculations: tools.calculations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-employment-statistics\n      description: Retrieve Current Employment Statistics (CES) data including total nonfarm employment, industry employment,\n        and average hourly earnings.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bls-public-data.get-single-series\n      with:\n        seriesId: tools.series_id\n        startyear: tools.start_year\n        endyear: tools.end_year\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-multiple-economic-indicators\n      description: Retrieve multiple BLS economic\
  \ indicators in a single API call. Supports up to 50 series for comparative\n        analysis across employment, wages, prices, and productivity metrics.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: bls-public-data.get-multiple-series\n      with:\n        series_ids: tools.series_ids\n        start_year: tools.start_year\n        end_year: tools.end_year\n        calculations: tools.calculations\n        annualaverage: tools.annual_average\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-popular-indicators\n      description: Get the 25 most popular BLS economic time series, optionally filtered by survey type (CPS, CES, AP, etc.)\n        to discover commonly used economic benchmark series.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: bls-public-data.get-popular-series\n      with:\n        survey: tools.survey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ list-bls-surveys\n      description: List all available BLS survey programs with their abbreviations. Use this to discover which surveys are\n        available before querying specific series IDs.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: bls-public-data.get-all-surveys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-survey-details\n      description: Get detailed metadata for a specific BLS survey program using its abbreviation (e.g., CPS for Current Population\n        Survey, CES for Current Employment Statistics, AP for Average Price Data).\n      hints:\n        readOnly: true\n        openWorld: false\n      call: bls-public-data.get-survey-metadata\n      with:\n        surveyId: tools.survey_id\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/u-s-bureau-of-labor-statistics/refs/heads/main/capabilities/labor-market-intelligence.yaml
tags:
- Bureau of Labor Statistics
- Labor Market
- Economic Research
- Policy Analysis
- Employment
- Inflation
- Federal Government
tools:
- description: Retrieve U.S. unemployment rate time series data. Use series ID LNS14000000 for the national seasonally adjusted unemployment rate, or specify a different series ID for demographic breakdowns.
  hints:
    openWorld: true
    readOnly: true
  name: get-unemployment-rate
- description: Retrieve Consumer Price Index (CPI) data for measuring inflation. Use CUUR0000SA0 for CPI-U All Items, or specify a different CPI series for category-specific inflation (food, energy, housing).
  hints:
    openWorld: true
    readOnly: true
  name: get-cpi-inflation
- description: Retrieve Current Employment Statistics (CES) data including total nonfarm employment, industry employment, and average hourly earnings.
  hints:
    openWorld: true
    readOnly: true
  name: get-employment-statistics
- description: Retrieve multiple BLS economic indicators in a single API call. Supports up to 50 series for comparative analysis across employment, wages, prices, and productivity metrics.
  hints:
    openWorld: true
    readOnly: true
  name: get-multiple-economic-indicators
- description: Get the 25 most popular BLS economic time series, optionally filtered by survey type (CPS, CES, AP, etc.) to discover commonly used economic benchmark series.
  hints:
    openWorld: false
    readOnly: true
  name: get-popular-indicators
- description: List all available BLS survey programs with their abbreviations. Use this to discover which surveys are available before querying specific series IDs.
  hints:
    openWorld: false
    readOnly: true
  name: list-bls-surveys
- description: Get detailed metadata for a specific BLS survey program using its abbreviation (e.g., CPS for Current Population Survey, CES for Current Employment Statistics, AP for Average Price Data).
  hints:
    openWorld: false
    readOnly: true
  name: get-survey-details
---
