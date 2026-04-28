---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Baker Hughes Industrial Platform
operations: []
personas: []
provider_name: Baker Hughes
provider_slug: baker-hughes
search_terms:
- oil and gas
- digital energy
- industrial iot
- energy technology
- asset performance management
slug: baker-hughes-industrial-platform
source_yaml: "name: Baker Hughes Industrial Platform Capability\ndescription: >-\n  Naftiko capability for Baker Hughes Cordant industrial software platform covering\n  asset performance management, process optimization, and emissions management workflows\n  for energy and industrial operations.\nversion: '1.0'\nprovider: baker-hughes\n\nworkflows:\n  - name: Asset Performance Monitoring\n    description: Monitor industrial asset health, sensor data, and maintenance alerts.\n    apis:\n      - baker-hughes:cordant-platform\n    tools:\n      - name: GetAssetStatus\n        description: Retrieve current health and operational status of an industrial asset.\n      - name: ListAlerts\n        description: List active alerts and anomalies for monitored assets.\n      - name: GetSensorReadings\n        description: Retrieve time-series sensor data for a specific asset.\n    persona: Plant Engineer\n\n  - name: Predictive Maintenance\n    description: AI-driven prediction of equipment failures\
  \ and maintenance scheduling.\n    apis:\n      - baker-hughes:bhc3-ai-suite\n    tools:\n      - name: GetMaintenancePredictions\n        description: Retrieve AI predictions for upcoming maintenance needs.\n      - name: CreateWorkOrder\n        description: Generate a maintenance work order from a prediction.\n      - name: GetRiskScore\n        description: Retrieve reliability risk score for an asset.\n    persona: Operations Manager\n\n  - name: Emissions Tracking\n    description: Track and report greenhouse gas emissions across industrial facilities.\n    apis:\n      - baker-hughes:cordant-platform\n    tools:\n      - name: GetEmissionsMeasurements\n        description: Retrieve emissions measurements for a facility or asset group.\n      - name: GenerateEmissionsReport\n        description: Generate ESG and emissions compliance report.\n    persona: Sustainability Officer\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/baker-hughes/refs/heads/main/capabilities/baker-hughes-industrial-platform.yaml
tags: []
tools: []
---
