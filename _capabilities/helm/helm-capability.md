---
categories: []
consumed_apis: []
description: The Helm Chart Repository API defines the HTTP endpoints used by Helm clients to discover and download charts from a repository server. A chart repository is an HTTP server that houses an index.yaml file listing all available charts and optionally packaged chart archives (.tgz files). ChartMuseum and compatible implementations extend this with a JSON-based management API for listing, uploading, and deleting charts programmatically.
layout: capability
name: Helm Chart Repository API
operations:
- description: Helm Get repository index
  method: GET
  name: getrepositoryindex
  path: /index.yaml
- description: Helm Download chart package
  method: GET
  name: downloadchartpackage
  path: /charts/{chartName}-{version}.tgz
- description: Helm Download chart provenance file
  method: GET
  name: downloadchartprovenance
  path: /charts/{chartName}-{version}.tgz.prov
- description: Helm List all charts
  method: GET
  name: listallcharts
  path: /api/charts
- description: Helm Upload chart package
  method: POST
  name: uploadchart
  path: /api/charts
- description: Helm Get chart versions
  method: GET
  name: getchartversions
  path: /api/charts/{chartName}
- description: Helm Get specific chart version
  method: GET
  name: getchartversion
  path: /api/charts/{chartName}/{version}
- description: Helm Delete chart version
  method: DELETE
  name: deletechartversion
  path: /api/charts/{chartName}/{version}
- description: Helm Upload provenance file
  method: POST
  name: uploadprovenance
  path: /api/prov
- description: Helm Get repository health
  method: GET
  name: gethealth
  path: /health
personas: []
provider_name: Helm
provider_slug: helm
search_terms:
- container orchestration
- listallcharts
- uploadchart
- helm download chart package
- helm delete chart version
- downloadchartpackage
- devops
- deletechartversion
- helm download chart provenance file
- helm get specific chart version
- getchartversion
- helm get repository index
- cloud native
- kubernetes
- helm get chart versions
- package manager
- helm upload provenance file
- gethealth
- api
- helm list all charts
- uploadprovenance
- helm get repository health
- helm
- charts
- downloadchartprovenance
- getchartversions
- helm upload chart package
- getrepositoryindex
slug: helm-capability
source_filename: helm-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Helm Chart Repository API\n  description: The Helm Chart Repository API defines the HTTP endpoints used by Helm clients to discover and download charts\n    from a repository server. A chart repository is an HTTP server that houses an index.yaml file listing all available charts\n    and optionally packaged chart archives (.tgz files). ChartMuseum and compatible implementations extend this with a JSON-based\n    management API for listing, uploading, and deleting charts programmatically.\n  tags:\n  - Helm\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: helm\n    baseUri: https://charts.example.com\n    description: Helm Chart Repository API HTTP API.\n    resources:\n    - name: index-yaml\n      path: /index.yaml\n      operations:\n      - name: getrepositoryindex\n        method: GET\n        description: Helm Get repository index\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charts-chartname-version-tgz\n      path: /charts/{chartName}-{version}.tgz\n      operations:\n      - name: downloadchartpackage\n        method: GET\n        description: Helm Download chart package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: charts-chartname-version-tgz-prov\n      path: /charts/{chartName}-{version}.tgz.prov\n      operations:\n      - name: downloadchartprovenance\n        method: GET\n        description: Helm Download chart provenance file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-charts\n      path: /api/charts\n      operations:\n      - name: listallcharts\n        method: GET\n        description: Helm List all charts\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: uploadchart\n        method: POST\n        description: Helm Upload chart package\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-charts-chartname\n      path: /api/charts/{chartName}\n      operations:\n      - name: getchartversions\n        method: GET\n        description: Helm Get chart versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-charts-chartname-version\n      path: /api/charts/{chartName}/{version}\n      operations:\n      - name: getchartversion\n        method: GET\n        description: Helm Get specific chart version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechartversion\n\
  \        method: DELETE\n        description: Helm Delete chart version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-prov\n      path: /api/prov\n      operations:\n      - name: uploadprovenance\n        method: POST\n        description: Helm Upload provenance file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: health\n      path: /health\n      operations:\n      - name: gethealth\n        method: GET\n        description: Helm Get repository health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: helm-rest\n    description: REST adapter for Helm Chart Repository API.\n    resources:\n    - path: /index.yaml\n      name: getrepositoryindex\n      operations:\n\
  \      - method: GET\n        name: getrepositoryindex\n        description: Helm Get repository index\n        call: helm.getrepositoryindex\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charts/{chartName}-{version}.tgz\n      name: downloadchartpackage\n      operations:\n      - method: GET\n        name: downloadchartpackage\n        description: Helm Download chart package\n        call: helm.downloadchartpackage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /charts/{chartName}-{version}.tgz.prov\n      name: downloadchartprovenance\n      operations:\n      - method: GET\n        name: downloadchartprovenance\n        description: Helm Download chart provenance file\n        call: helm.downloadchartprovenance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/charts\n      name: listallcharts\n      operations:\n      - method: GET\n        name: listallcharts\n\
  \        description: Helm List all charts\n        call: helm.listallcharts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/charts\n      name: uploadchart\n      operations:\n      - method: POST\n        name: uploadchart\n        description: Helm Upload chart package\n        call: helm.uploadchart\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/charts/{chartName}\n      name: getchartversions\n      operations:\n      - method: GET\n        name: getchartversions\n        description: Helm Get chart versions\n        call: helm.getchartversions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/charts/{chartName}/{version}\n      name: getchartversion\n      operations:\n      - method: GET\n        name: getchartversion\n        description: Helm Get specific chart version\n        call: helm.getchartversion\n        outputParameters:\n        - type:\
  \ object\n          mapping: $.\n    - path: /api/charts/{chartName}/{version}\n      name: deletechartversion\n      operations:\n      - method: DELETE\n        name: deletechartversion\n        description: Helm Delete chart version\n        call: helm.deletechartversion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /api/prov\n      name: uploadprovenance\n      operations:\n      - method: POST\n        name: uploadprovenance\n        description: Helm Upload provenance file\n        call: helm.uploadprovenance\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /health\n      name: gethealth\n      operations:\n      - method: GET\n        name: gethealth\n        description: Helm Get repository health\n        call: helm.gethealth\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: helm-mcp\n    transport: http\n    description: MCP adapter\
  \ for Helm Chart Repository API for AI agent use.\n    tools:\n    - name: getrepositoryindex\n      description: Helm Get repository index\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.getrepositoryindex\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadchartpackage\n      description: Helm Download chart package\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.downloadchartpackage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadchartprovenance\n      description: Helm Download chart provenance file\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.downloadchartprovenance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listallcharts\n      description: Helm List all charts\n      hints:\n   \
  \     readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.listallcharts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadchart\n      description: Helm Upload chart package\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: helm.uploadchart\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchartversions\n      description: Helm Get chart versions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.getchartversions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getchartversion\n      description: Helm Get specific chart version\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.getchartversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletechartversion\n\
  \      description: Helm Delete chart version\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: helm.deletechartversion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: uploadprovenance\n      description: Helm Upload provenance file\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: helm.uploadprovenance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gethealth\n      description: Helm Get repository health\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: helm.gethealth\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/helm/refs/heads/main/capabilities/helm-capability.yaml
tags:
- Helm
- API
tools:
- description: Helm Get repository index
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrepositoryindex
- description: Helm Download chart package
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadchartpackage
- description: Helm Download chart provenance file
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadchartprovenance
- description: Helm List all charts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listallcharts
- description: Helm Upload chart package
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadchart
- description: Helm Get chart versions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchartversions
- description: Helm Get specific chart version
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchartversion
- description: Helm Delete chart version
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechartversion
- description: Helm Upload provenance file
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: uploadprovenance
- description: Helm Get repository health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethealth
---
