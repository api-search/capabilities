---
categories: []
consumed_apis: []
description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.
layout: capability
name: Airflow Prefect Dagster Pipeline Reusability Capability
operations:
- description: ''
  method: GET
  name: example-op
  path: /example
personas: []
provider_name: Naftiko
provider_slug: naftiko
search_terms:
- a capability composition over the airflow + prefect + dagster pipeline trio that exposes shared steps as reusable capabilities — the api-reusability ask, made concrete on actual data stack.
- spec-driven integration
- example op
- example
- api integration
- naftiko
- governance
- mcp
- capabilities
- ai
slug: airflow-prefect-dagster-pipeline-reusability-capability
source_filename: airflow-prefect-dagster-pipeline-reusability-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  title: Airflow Prefect Dagster Pipeline Reusability Capability\n  description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.\n  tags:\n  - Naftiko\n  created: '2026-05-01'\n  modified: '2026-05-01'\nbinds:\n- namespace: naftiko-env\n  description: Naftiko credentials.\n  keys:\n    NAFTIKO_API_KEY: NAFTIKO_API_KEY\ncapability:\n  consumes:\n  - namespace: naftiko\n    type: http\n    baseUri: https://api.naftiko.com\n    authentication:\n      type: bearer\n      token: '{{NAFTIKO_API_KEY}}'\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - name: example-op\n        method: GET\n  exposes:\n  - type: rest\n    address: 0.0.0.0\n    port: 8080\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-rest\n    description: REST API for Airflow Prefect\
  \ Dagster Pipeline Reusability Capability.\n    resources:\n    - name: example\n      path: /example\n      operations:\n      - method: GET\n        name: example-op\n        call: naftiko.example-op\n  - type: mcp\n    address: 0.0.0.0\n    port: 3010\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp\n    description: MCP server exposing Airflow Prefect Dagster Pipeline Reusability Capability for AI agents.\n    tools:\n    - name: example\n      description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.\n      hints:\n        readOnly: true\n      call: naftiko.example-op\n  - type: skill\n    address: 0.0.0.0\n    port: 3011\n    namespace: airflow-prefect-dagster-pipeline-reusability-capability-skills\n    description: Agent Skill bundle for Airflow Prefect Dagster Pipeline Reusability Capability.\n    skills:\n\
  \    - name: airflow-prefect-dagster-pipeline-reusability-capability\n      description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.\n      location: file:///opt/naftiko/skills/airflow-prefect-dagster-pipeline-reusability-capability\n      allowed-tools: example\n      tools:\n      - name: example\n        description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.\n        from:\n          sourceNamespace: airflow-prefect-dagster-pipeline-reusability-capability-mcp\n          action: example\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/naftiko/refs/heads/main/capabilities/airflow-prefect-dagster-pipeline-reusability-capability.yaml
tags:
- Naftiko
tools:
- description: A Capability Composition over the Airflow + Prefect + Dagster pipeline trio that exposes shared steps as reusable capabilities — the API-reusability ask, made concrete on actual data stack.
  hints:
    readOnly: true
  name: example
---
