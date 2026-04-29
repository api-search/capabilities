---
categories: []
consumed_apis: []
description: 'Manage end-to-end time-series forecasting pipelines: datasets, predictors, and forecast generation.'
layout: capability
name: Amazon Forecast Time Series Prediction
operations: []
personas: []
provider_name: Amazon Forecast
provider_slug: amazon-forecast
search_terms:
- predictive analytics
- aws
- forecasting
- time series
- demand planning
- machine learning
slug: amazon-forecast-time-series-prediction
source_filename: amazon-forecast-time-series-prediction.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: Amazon Forecast Time Series Prediction\n  description: 'Manage end-to-end time-series forecasting pipelines: datasets, predictors, and forecast generation.'\n  tags:\n  - Forecasting\n  - Machine Learning\n  - Time Series\n  - Demand Planning\n  - AWS\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - namespace: forecast\n    ref: capabilities/shared/forecast.yaml\n  exposes:\n  - type: rest\n    port: 8080\n  - type: mcp\n    port: 9090\n  tools:\n  - name: createDataset\n    description: Create an Amazon Forecast dataset\n    inputSchema:\n      type: object\n      properties:\n        DatasetName:\n          type: string\n        Domain:\n          type: string\n        DatasetType:\n          type: string\n        DataFrequency:\n          type: string\n        Schema:\n          type: object\n    \
  \  required:\n      - DatasetName\n      - Domain\n      - DatasetType\n      - Schema\n  - name: listDatasets\n    description: List all Forecast datasets\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n  - name: describeDataset\n    description: Describe a Forecast dataset\n    inputSchema:\n      type: object\n      properties:\n        datasetArn:\n          type: string\n      required:\n      - datasetArn\n  - name: createDatasetGroup\n    description: Create a dataset group\n    inputSchema:\n      type: object\n      properties:\n        DatasetGroupName:\n          type: string\n        Domain:\n          type: string\n        DatasetArns:\n          type: array\n      required:\n      - DatasetGroupName\n      - Domain\n  - name: listDatasetGroups\n    description: List all dataset groups\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type:\
  \ integer\n        nextToken:\n          type: string\n  - name: createPredictor\n    description: Train a Forecast predictor on a dataset group\n    inputSchema:\n      type: object\n      properties:\n        PredictorName:\n          type: string\n        ForecastHorizon:\n          type: integer\n        InputDataConfig:\n          type: object\n        FeaturizationConfig:\n          type: object\n        PerformAutoML:\n          type: boolean\n      required:\n      - PredictorName\n      - ForecastHorizon\n      - InputDataConfig\n      - FeaturizationConfig\n  - name: listPredictors\n    description: List all Forecast predictors\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n  - name: createForecast\n    description: Generate a forecast from a trained predictor\n    inputSchema:\n      type: object\n      properties:\n        ForecastName:\n          type: string\n        PredictorArn:\n\
  \          type: string\n        ForecastTypes:\n          type: array\n      required:\n      - ForecastName\n      - PredictorArn\n  - name: listForecasts\n    description: List all Forecast forecasts\n    inputSchema:\n      type: object\n      properties:\n        maxResults:\n          type: integer\n        nextToken:\n          type: string\n  - name: createForecastExportJob\n    description: Export forecast data to S3\n    inputSchema:\n      type: object\n      properties:\n        ForecastExportJobName:\n          type: string\n        ForecastArn:\n          type: string\n        Destination:\n          type: object\n      required:\n      - ForecastExportJobName\n      - ForecastArn\n      - Destination\n  - name: listTagsForResource\n    description: List tags for a Forecast resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n      required:\n      - resourceArn\n  - name: tagResource\n    description: Tag a Forecast\
  \ resource\n    inputSchema:\n      type: object\n      properties:\n        resourceArn:\n          type: string\n        Tags:\n          type: array\n      required:\n      - resourceArn\n      - Tags\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-forecast/refs/heads/main/capabilities/amazon-forecast-time-series-prediction.yaml
tags:
- Forecasting
- Machine Learning
- Time Series
- Demand Planning
- AWS
tools: []
---
