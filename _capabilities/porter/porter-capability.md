---
categories: []
consumed_apis: []
description: The Porter Bundle API provides programmatic access to managing Cloud Native Application Bundles (CNAB) using Porter. It supports listing and inspecting bundles, managing installations, handling credential sets and parameter sets, and querying installation runs and outputs. Porter implements the CNAB spec for packaging applications with their dependencies into distributable installers.
layout: capability
name: Porter Bundle API
operations:
- description: Porter List bundles
  method: GET
  name: listbundles
  path: /v1/bundles
- description: Porter Get a bundle
  method: GET
  name: getbundle
  path: /v1/bundles/{namespace}/{name}
- description: Porter List installations
  method: GET
  name: listinstallations
  path: /v1/installations
- description: Porter Create an installation
  method: POST
  name: createinstallation
  path: /v1/installations
- description: Porter Get an installation
  method: GET
  name: getinstallation
  path: /v1/installations/{namespace}/{name}
- description: Porter Update an installation
  method: PATCH
  name: patchinstallation
  path: /v1/installations/{namespace}/{name}
- description: Porter Delete an installation
  method: DELETE
  name: deleteinstallation
  path: /v1/installations/{namespace}/{name}
- description: Porter List runs for an installation
  method: GET
  name: listinstallationruns
  path: /v1/installations/{namespace}/{name}/runs
- description: Porter Get a specific run
  method: GET
  name: getinstallationrun
  path: /v1/installations/{namespace}/{name}/runs/{run_id}
- description: Porter List outputs for a run
  method: GET
  name: listrunoutputs
  path: /v1/installations/{namespace}/{name}/runs/{run_id}/outputs
- description: Porter List credential sets
  method: GET
  name: listcredentialsets
  path: /v1/credentialsets
- description: Porter Create a credential set
  method: POST
  name: createcredentialset
  path: /v1/credentialsets
- description: Porter Get a credential set
  method: GET
  name: getcredentialset
  path: /v1/credentialsets/{namespace}/{name}
- description: Porter Update a credential set
  method: PUT
  name: updatecredentialset
  path: /v1/credentialsets/{namespace}/{name}
- description: Porter Delete a credential set
  method: DELETE
  name: deletecredentialset
  path: /v1/credentialsets/{namespace}/{name}
- description: Porter List parameter sets
  method: GET
  name: listparametersets
  path: /v1/parametersets
- description: Porter Create a parameter set
  method: POST
  name: createparameterset
  path: /v1/parametersets
- description: Porter Get a parameter set
  method: GET
  name: getparameterset
  path: /v1/parametersets/{namespace}/{name}
- description: Porter Delete a parameter set
  method: DELETE
  name: deleteparameterset
  path: /v1/parametersets/{namespace}/{name}
personas: []
provider_name: Porter
provider_slug: porter
search_terms:
- porter list parameter sets
- devops
- porter get a specific run
- porter delete a credential set
- deleteinstallation
- api
- porter delete an installation
- porter create a credential set
- porter get a credential set
- porter delete a parameter set
- cloud native
- package manager
- porter
- listrunoutputs
- listbundles
- createparameterset
- porter list runs for an installation
- deleteparameterset
- kubernetes
- porter get an installation
- porter create a parameter set
- updatecredentialset
- porter list installations
- deletecredentialset
- listinstallations
- listinstallationruns
- getcredentialset
- createcredentialset
- getinstallation
- porter get a bundle
- cnab
- porter update an installation
- porter list outputs for a run
- createinstallation
- porter list credential sets
- listparametersets
- listcredentialsets
- getinstallationrun
- porter update a credential set
- porter list bundles
- getparameterset
- porter get a parameter set
- porter create an installation
- getbundle
- patchinstallation
slug: porter-capability
source_filename: porter-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Porter Bundle API\n  description: The Porter Bundle API provides programmatic access to managing Cloud Native Application Bundles (CNAB) using\n    Porter. It supports listing and inspecting bundles, managing installations, handling credential sets and parameter sets,\n    and querying installation runs and outputs. Porter implements the CNAB spec for packaging applications with their dependencies\n    into distributable installers.\n  tags:\n  - Porter\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: porter\n    baseUri: http://localhost:3000\n    description: Porter Bundle API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{PORTER_TOKEN}}'\n    resources:\n    - name: v1-bundles\n      path: /v1/bundles\n      operations:\n      - name: listbundles\n        method: GET\n        description: Porter List bundles\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-bundles-namespace-name\n      path: /v1/bundles/{namespace}/{name}\n      operations:\n      - name: getbundle\n        method: GET\n        description: Porter Get a bundle\n        inputParameters:\n        - name: version\n          in: query\n          type: string\n          description: Specific version of the bundle to retrieve. Defaults to latest.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-installations\n      path: /v1/installations\n      operations:\n      - name: listinstallations\n        method: GET\n        description: Porter List installations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createinstallation\n        method: POST\n        description: Porter Create an installation\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-installations-namespace-name\n      path: /v1/installations/{namespace}/{name}\n      operations:\n      - name: getinstallation\n        method: GET\n        description: Porter Get an installation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchinstallation\n        method: PATCH\n        description: Porter Update an installation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteinstallation\n        method: DELETE\n        description: Porter Delete an installation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-installations-namespace-name-runs\n      path:\
  \ /v1/installations/{namespace}/{name}/runs\n      operations:\n      - name: listinstallationruns\n        method: GET\n        description: Porter List runs for an installation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-installations-namespace-name-runs-run-id\n      path: /v1/installations/{namespace}/{name}/runs/{run_id}\n      operations:\n      - name: getinstallationrun\n        method: GET\n        description: Porter Get a specific run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-installations-namespace-name-runs-run-id-outp\n      path: /v1/installations/{namespace}/{name}/runs/{run_id}/outputs\n      operations:\n      - name: listrunoutputs\n        method: GET\n        description: Porter List outputs for a run\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: v1-credentialsets\n      path: /v1/credentialsets\n      operations:\n      - name: listcredentialsets\n        method: GET\n        description: Porter List credential sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcredentialset\n        method: POST\n        description: Porter Create a credential set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-credentialsets-namespace-name\n      path: /v1/credentialsets/{namespace}/{name}\n      operations:\n      - name: getcredentialset\n        method: GET\n        description: Porter Get a credential set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecredentialset\n      \
  \  method: PUT\n        description: Porter Update a credential set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecredentialset\n        method: DELETE\n        description: Porter Delete a credential set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parametersets\n      path: /v1/parametersets\n      operations:\n      - name: listparametersets\n        method: GET\n        description: Porter List parameter sets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createparameterset\n        method: POST\n        description: Porter Create a parameter set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-parametersets-namespace-name\n\
  \      path: /v1/parametersets/{namespace}/{name}\n      operations:\n      - name: getparameterset\n        method: GET\n        description: Porter Get a parameter set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteparameterset\n        method: DELETE\n        description: Porter Delete a parameter set\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: porter-rest\n    description: REST adapter for Porter Bundle API.\n    resources:\n    - path: /v1/bundles\n      name: listbundles\n      operations:\n      - method: GET\n        name: listbundles\n        description: Porter List bundles\n        call: porter.listbundles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bundles/{namespace}/{name}\n      name:\
  \ getbundle\n      operations:\n      - method: GET\n        name: getbundle\n        description: Porter Get a bundle\n        call: porter.getbundle\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations\n      name: listinstallations\n      operations:\n      - method: GET\n        name: listinstallations\n        description: Porter List installations\n        call: porter.listinstallations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations\n      name: createinstallation\n      operations:\n      - method: POST\n        name: createinstallation\n        description: Porter Create an installation\n        call: porter.createinstallation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}\n      name: getinstallation\n      operations:\n      - method: GET\n        name: getinstallation\n        description: Porter\
  \ Get an installation\n        call: porter.getinstallation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}\n      name: patchinstallation\n      operations:\n      - method: PATCH\n        name: patchinstallation\n        description: Porter Update an installation\n        call: porter.patchinstallation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}\n      name: deleteinstallation\n      operations:\n      - method: DELETE\n        name: deleteinstallation\n        description: Porter Delete an installation\n        call: porter.deleteinstallation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}/runs\n      name: listinstallationruns\n      operations:\n      - method: GET\n        name: listinstallationruns\n        description: Porter List runs for an installation\n\
  \        call: porter.listinstallationruns\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}/runs/{run_id}\n      name: getinstallationrun\n      operations:\n      - method: GET\n        name: getinstallationrun\n        description: Porter Get a specific run\n        call: porter.getinstallationrun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/installations/{namespace}/{name}/runs/{run_id}/outputs\n      name: listrunoutputs\n      operations:\n      - method: GET\n        name: listrunoutputs\n        description: Porter List outputs for a run\n        call: porter.listrunoutputs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/credentialsets\n      name: listcredentialsets\n      operations:\n      - method: GET\n        name: listcredentialsets\n        description: Porter List credential sets\n        call: porter.listcredentialsets\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/credentialsets\n      name: createcredentialset\n      operations:\n      - method: POST\n        name: createcredentialset\n        description: Porter Create a credential set\n        call: porter.createcredentialset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/credentialsets/{namespace}/{name}\n      name: getcredentialset\n      operations:\n      - method: GET\n        name: getcredentialset\n        description: Porter Get a credential set\n        call: porter.getcredentialset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/credentialsets/{namespace}/{name}\n      name: updatecredentialset\n      operations:\n      - method: PUT\n        name: updatecredentialset\n        description: Porter Update a credential set\n        call: porter.updatecredentialset\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /v1/credentialsets/{namespace}/{name}\n      name: deletecredentialset\n      operations:\n      - method: DELETE\n        name: deletecredentialset\n        description: Porter Delete a credential set\n        call: porter.deletecredentialset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parametersets\n      name: listparametersets\n      operations:\n      - method: GET\n        name: listparametersets\n        description: Porter List parameter sets\n        call: porter.listparametersets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parametersets\n      name: createparameterset\n      operations:\n      - method: POST\n        name: createparameterset\n        description: Porter Create a parameter set\n        call: porter.createparameterset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parametersets/{namespace}/{name}\n\
  \      name: getparameterset\n      operations:\n      - method: GET\n        name: getparameterset\n        description: Porter Get a parameter set\n        call: porter.getparameterset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/parametersets/{namespace}/{name}\n      name: deleteparameterset\n      operations:\n      - method: DELETE\n        name: deleteparameterset\n        description: Porter Delete a parameter set\n        call: porter.deleteparameterset\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: porter-mcp\n    transport: http\n    description: MCP adapter for Porter Bundle API for AI agent use.\n    tools:\n    - name: listbundles\n      description: Porter List bundles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.listbundles\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: getbundle\n      description: Porter Get a bundle\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.getbundle\n      with:\n        version: tools.version\n      inputParameters:\n      - name: version\n        type: string\n        description: Specific version of the bundle to retrieve. Defaults to latest.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstallations\n      description: Porter List installations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.listinstallations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinstallation\n      description: Porter Create an installation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: porter.createinstallation\n      outputParameters:\n      - type: object\n   \
  \     mapping: $.\n    - name: getinstallation\n      description: Porter Get an installation\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.getinstallation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchinstallation\n      description: Porter Update an installation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: porter.patchinstallation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteinstallation\n      description: Porter Delete an installation\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: porter.deleteinstallation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listinstallationruns\n      description: Porter List runs for an installation\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: porter.listinstallationruns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinstallationrun\n      description: Porter Get a specific run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.getinstallationrun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrunoutputs\n      description: Porter List outputs for a run\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.listrunoutputs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcredentialsets\n      description: Porter List credential sets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.listcredentialsets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcredentialset\n\
  \      description: Porter Create a credential set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: porter.createcredentialset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcredentialset\n      description: Porter Get a credential set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.getcredentialset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecredentialset\n      description: Porter Update a credential set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: porter.updatecredentialset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletecredentialset\n      description: Porter Delete a credential set\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call:\
  \ porter.deletecredentialset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listparametersets\n      description: Porter List parameter sets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.listparametersets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createparameterset\n      description: Porter Create a parameter set\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: porter.createparameterset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getparameterset\n      description: Porter Get a parameter set\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: porter.getparameterset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteparameterset\n      description: Porter Delete a parameter\
  \ set\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: porter.deleteparameterset\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    PORTER_TOKEN: PORTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/porter/refs/heads/main/capabilities/porter-capability.yaml
tags:
- Porter
- API
tools:
- description: Porter List bundles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbundles
- description: Porter Get a bundle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbundle
- description: Porter List installations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstallations
- description: Porter Create an installation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinstallation
- description: Porter Get an installation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstallation
- description: Porter Update an installation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchinstallation
- description: Porter Delete an installation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteinstallation
- description: Porter List runs for an installation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listinstallationruns
- description: Porter Get a specific run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinstallationrun
- description: Porter List outputs for a run
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrunoutputs
- description: Porter List credential sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcredentialsets
- description: Porter Create a credential set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcredentialset
- description: Porter Get a credential set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcredentialset
- description: Porter Update a credential set
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecredentialset
- description: Porter Delete a credential set
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecredentialset
- description: Porter List parameter sets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listparametersets
- description: Porter Create a parameter set
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createparameterset
- description: Porter Get a parameter set
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparameterset
- description: Porter Delete a parameter set
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteparameterset
---
