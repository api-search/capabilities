---
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
- generate estimates report.
- market data
- factset
- portfolio analytics
- generate chart
- build a custom report book.
- generate a chart.
- estimates report
- report builder
- generate capital structure report.
- generate ownership report.
- vermilion report
- generate vermilion report.
- capital structure report
- investment analytics
- visualization
- generate fundamentals report.
- research
- reporting
- list available reports.
- fundamentals report
- list reports
- ownership report
- generate a digital card.
- financial data
- chart generation.
- generate overview report.
- generate digital card
- financial
- build book
- generate entity report.
- report generation.
- overview report
slug: reporting
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
