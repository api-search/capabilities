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
- generate a chart.
- entity report
- generate digital card
- financial data
- report generation.
- report builder
- chart generation.
- generate chart
- generate capital structure report.
- build a custom report book.
- vermilion report
- estimates report
- generate estimates report.
- capital structure report
- build book
- generate ownership report.
- reporting
- generate entity report.
- research
- generate overview report.
- generate a digital card.
- generate fundamentals report.
- financial
- ownership report
- market data
- list available reports.
- fundamentals report
- investment analytics
- list reports
- factset
- visualization
- portfolio analytics
- overview report
- generate vermilion report.
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
