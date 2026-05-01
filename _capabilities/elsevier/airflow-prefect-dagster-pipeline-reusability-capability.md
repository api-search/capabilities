---
categories: []
consumed_apis:
- elsevier
description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack.
layout: capability
naftiko_layer: service-anchored
naftiko_partner: Joyce Stack
name: Elsevier Airflow Prefect Dagster Pipeline Reusability Capability
operations: []
personas: []
provider_name: Elsevier
provider_slug: elsevier
search_terms:
- capability
- composition
- over
- airflow
- prefect
slug: airflow-prefect-dagster-pipeline-reusability-capability
source_filename: airflow-prefect-dagster-pipeline-reusability-capability.yaml
source_heading: Capability Spec
source_yaml: |-
  naftiko: 1.0.0-alpha2
  info:
    title: Elsevier Airflow Prefect Dagster Pipeline Reusability Capability
    description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack.
    tags:
    - Elsevier
    created: '2026-04-30'
    modified: '2026-04-30'
  binds:
  - namespace: elsevier-env
    description: Elsevier credentials.
    keys:
      ELSEVIER_API_KEY: ELSEVIER_API_KEY
  capability:
    consumes:
    - namespace: elsevier
      type: http
      baseUri: https://api.elsevier.com
      authentication:
        type: bearer
        token: '{{ELSEVIER_API_KEY}}'
      resources:
      - name: example
        path: /example
        operations:
        - name: example-op
          method: GET
    exposes:
    - type: rest
      address: 0.0.0.0
      port: 8080
      namespace: airflow-prefect-dagster-pipeline-reusability-capability-rest
      description: REST API for Elsevier Airflow Prefect Dagster Pipeline Reusability Capability.
      resources:
      - name: example
        path: /example
        operations:
        - method: GET
          name: example-op
          call: elsevier.example-op
    - type: mcp
      address: 0.0.0.0
      port: 3010
      namespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp
      description: MCP server exposing Elsevier Airflow Prefect Dagster Pipeline Reusability Capability for AI agents.
      tools:
      - name: example
        description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack.
        hints:
          readOnly: true
        call: elsevier.example-op
    - type: skill
      address: 0.0.0.0
      port: 3011
      namespace: airflow-prefect-dagster-pipeline-reusability-capability-skills
      description: Agent Skill bundle for Elsevier Airflow Prefect Dagster Pipeline Reusability Capability.
      skills:
      - name: airflow-prefect-dagster-pipeline-reusability-capability
        description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack.
        location: file:///opt/naftiko/skills/airflow-prefect-dagster-pipeline-reusability-capability
        allowed-tools: example
        tools:
        - name: example
          description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack.
          from:
            sourceNamespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp
            action: example
---

A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on Elsevier's actual data stack. Reusability across three orchestrators on Elsevier's actual stack is the pattern her ask was reaching for.
