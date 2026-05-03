---
categories:
- analytics
consumed_apis:
- factset-ent-rb
- factset-fund-rb
- factset-est-rb
- factset-cap-rb
- factset-ovw-rb
- factset-own-rb
- factset-charts
- factset-cards
- factset-bookbuilder
- factset-vermilion
description: Unified workflow for generating reports including entity, fundamentals, estimates, capital structure, overview, ownership reports, charts, and digital cards. Used by report builders.
layout: capability
name: FactSet Reporting
operations:
- description: List available reports.
  method: GET
  name: list-reports
  path: /v1/reports
- description: Generate a chart.
  method: GET
  name: generate-chart
  path: /v1/charts
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- entity report
- generate fundamentals report.
- generate estimates report.
- chart generation.
- generate a chart.
- report builder
- financial
- factset
- fundamentals report
- build a custom report book.
- generate chart
- report generation.
- generate capital structure report.
- estimates report
- research
- market data
- visualization
- build book
- generate entity report.
- list available reports.
- generate a digital card.
- ownership report
- generate digital card
- overview report
- vermilion report
- financial data
- generate vermilion report.
- portfolio analytics
- list reports
- capital structure report
- investment analytics
- reporting
- generate overview report.
- generate ownership report.
slug: reporting
source_filename: reporting.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"FactSet Reporting\"\n  description: \"Unified workflow for generating reports including entity, fundamentals, estimates, capital structure, overview, ownership reports, charts, and digital cards. Used by report builders.\"\n  tags:\n    - FactSet\n    - Reporting\n    - Report Builder\n    - Visualization\n  created: \"2026-04-18\"\n  modified: \"2026-04-18\"\n\nbinds:\n  - namespace: env\n    keys:\n      FACTSET_USERNAME: FACTSET_USERNAME\n      FACTSET_PASSWORD: FACTSET_PASSWORD\n\ncapability:\n  consumes:\n    - import: factset-ent-rb\n      location: ./shared/entity-report-builder.yaml\n    - import: factset-fund-rb\n      location: ./shared/fundamentals-report-builder.yaml\n    - import: factset-est-rb\n      location: ./shared/estimates-report-builder.yaml\n    - import: factset-cap-rb\n      location: ./shared/capital-structure-report-builder.yaml\n    - import: factset-ovw-rb\n      location: ./shared/overview-report-builder.yaml\n\
  \    - import: factset-own-rb\n      location: ./shared/ownership-report-builder.yaml\n    - import: factset-charts\n      location: ./shared/chart-generation-service.yaml\n    - import: factset-cards\n      location: ./shared/digital-cards.yaml\n    - import: factset-bookbuilder\n      location: ./shared/bookbuilder.yaml\n    - import: factset-vermilion\n      location: ./shared/vermilion.yaml\n\n  exposes:\n    - type: rest\n      port: 8089\n      namespace: reporting-api\n      description: \"Unified REST API for reporting.\"\n      resources:\n        - path: /v1/reports\n          name: reports\n          description: \"Report generation.\"\n          operations:\n            - method: GET\n              name: list-reports\n              description: \"List available reports.\"\n              call: \"factset-fund-rb.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/charts\n          name: charts\n     \
  \     description: \"Chart generation.\"\n          operations:\n            - method: GET\n              name: generate-chart\n              description: \"Generate a chart.\"\n              call: \"factset-charts.list\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9089\n      namespace: reporting-mcp\n      transport: http\n      description: \"MCP server for AI-assisted reporting.\"\n      tools:\n        - name: entity-report\n          description: \"Generate entity report.\"\n          hints:\n            readOnly: true\n          call: \"factset-ent-rb.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: fundamentals-report\n          description: \"Generate fundamentals report.\"\n          hints:\n            readOnly: true\n          call: \"factset-fund-rb.list\"\n          outputParameters:\n            - type: object\n          \
  \    mapping: \"$.\"\n        - name: estimates-report\n          description: \"Generate estimates report.\"\n          hints:\n            readOnly: true\n          call: \"factset-est-rb.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: capital-structure-report\n          description: \"Generate capital structure report.\"\n          hints:\n            readOnly: true\n          call: \"factset-cap-rb.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: overview-report\n          description: \"Generate overview report.\"\n          hints:\n            readOnly: true\n          call: \"factset-ovw-rb.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: ownership-report\n          description: \"Generate ownership report.\"\n          hints:\n            readOnly: true\n          call: \"factset-own-rb.list\"\
  \n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-chart\n          description: \"Generate a chart.\"\n          hints:\n            readOnly: true\n          call: \"factset-charts.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: generate-digital-card\n          description: \"Generate a digital card.\"\n          hints:\n            readOnly: true\n          call: \"factset-cards.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: build-book\n          description: \"Build a custom report book.\"\n          hints:\n            readOnly: true\n          call: \"factset-bookbuilder.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: vermilion-report\n          description: \"Generate Vermilion report.\"\n          hints:\n            readOnly:\
  \ true\n          call: \"factset-vermilion.list\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/factset/refs/heads/main/capabilities/reporting.yaml
tags:
- FactSet
- Reporting
- Report Builder
- Visualization
tools:
- description: Generate entity report.
  hints:
    readOnly: true
  name: entity-report
- description: Generate fundamentals report.
  hints:
    readOnly: true
  name: fundamentals-report
- description: Generate estimates report.
  hints:
    readOnly: true
  name: estimates-report
- description: Generate capital structure report.
  hints:
    readOnly: true
  name: capital-structure-report
- description: Generate overview report.
  hints:
    readOnly: true
  name: overview-report
- description: Generate ownership report.
  hints:
    readOnly: true
  name: ownership-report
- description: Generate a chart.
  hints:
    readOnly: true
  name: generate-chart
- description: Generate a digital card.
  hints:
    readOnly: true
  name: generate-digital-card
- description: Build a custom report book.
  hints:
    readOnly: true
  name: build-book
- description: Generate Vermilion report.
  hints:
    readOnly: true
  name: vermilion-report
---
