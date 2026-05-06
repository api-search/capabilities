---
categories: []
consumed_apis: []
description: REST API for JupyterLab Server, the set of REST API services that JupyterLab depends on. Provides endpoints for managing user-defined settings, workspaces, themes, translations, third-party license reports, and extension listings. JupyterLab Server runs as a Jupyter Server extension.
layout: capability
name: JupyterLab Server REST API
operations:
- description: JupyterLab List all settings
  method: GET
  name: listsettings
  path: /settings
- description: JupyterLab Get setting
  method: GET
  name: getsetting
  path: /settings/{schema_name}
- description: JupyterLab Update setting
  method: PUT
  name: updatesetting
  path: /settings/{schema_name}
- description: JupyterLab List workspaces
  method: GET
  name: listworkspaces
  path: /workspaces
- description: JupyterLab Get workspace
  method: GET
  name: getworkspace
  path: /workspaces/{space_name}
- description: JupyterLab Update workspace
  method: PUT
  name: updateworkspace
  path: /workspaces/{space_name}
- description: JupyterLab Delete workspace
  method: DELETE
  name: deleteworkspace
  path: /workspaces/{space_name}
- description: JupyterLab Get theme asset
  method: GET
  name: getthemeasset
  path: /themes/{theme_file}
- description: JupyterLab List translations
  method: GET
  name: listtranslations
  path: /translations
- description: JupyterLab Get translation bundle
  method: GET
  name: gettranslation
  path: /translations/{locale}
- description: JupyterLab Get licenses report
  method: GET
  name: getlicenses
  path: /licenses
- description: JupyterLab Get extension listings
  method: GET
  name: getlistings
  path: /listings/@jupyterlab/extensionmanager-extension/listings.json
personas: []
provider_name: JupyterLab
provider_slug: jupyterlab
search_terms:
- getlistings
- jupyterlab update setting
- listworkspaces
- updatesetting
- jupyterlab get extension listings
- jupyterlab get setting
- getworkspace
- notebooks
- listsettings
- deleteworkspace
- ide
- listtranslations
- jupyterlab get translation bundle
- gettranslation
- jupyterlab delete workspace
- getsetting
- jupyterlab list workspaces
- api
- jupyterlab update workspace
- interactive computing
- jupyterlab get workspace
- python
- getthemeasset
- jupyterlab
- jupyterlab get theme asset
- jupyterlab list translations
- extensions
- jupyterlab list all settings
- jupyterlab get licenses report
- updateworkspace
- data science
- getlicenses
slug: jupyterlab-capability
source_filename: jupyterlab-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: JupyterLab Server REST API\n  description: REST API for JupyterLab Server, the set of REST API services that JupyterLab depends on. Provides endpoints\n    for managing user-defined settings, workspaces, themes, translations, third-party license reports, and extension listings.\n    JupyterLab Server runs as a Jupyter Server extension.\n  tags:\n  - Jupyterlab\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: jupyterlab\n    baseUri: http://localhost:8888/lab/api\n    description: JupyterLab Server REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{JUPYTERLAB_TOKEN}}'\n    resources:\n    - name: settings\n      path: /settings\n      operations:\n      - name: listsettings\n        method: GET\n        description: JupyterLab List all settings\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: settings-schema-name\n      path: /settings/{schema_name}\n      operations:\n      - name: getsetting\n        method: GET\n        description: JupyterLab Get setting\n        inputParameters:\n        - name: schema_name\n          in: path\n          type: string\n          required: true\n          description: Plugin schema identifier (for example @jupyterlab/apputils-extension:themes).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesetting\n        method: PUT\n        description: JupyterLab Update setting\n        inputParameters:\n        - name: schema_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n\
  \      operations:\n      - name: listworkspaces\n        method: GET\n        description: JupyterLab List workspaces\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces-space-name\n      path: /workspaces/{space_name}\n      operations:\n      - name: getworkspace\n        method: GET\n        description: JupyterLab Get workspace\n        inputParameters:\n        - name: space_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkspace\n        method: PUT\n        description: JupyterLab Update workspace\n        inputParameters:\n        - name: space_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n     \
  \     type: object\n          value: $.\n      - name: deleteworkspace\n        method: DELETE\n        description: JupyterLab Delete workspace\n        inputParameters:\n        - name: space_name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: themes-theme-file\n      path: /themes/{theme_file}\n      operations:\n      - name: getthemeasset\n        method: GET\n        description: JupyterLab Get theme asset\n        inputParameters:\n        - name: theme_file\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: translations\n      path: /translations\n      operations:\n      - name: listtranslations\n        method: GET\n        description: JupyterLab List translations\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: translations-locale\n      path: /translations/{locale}\n      operations:\n      - name: gettranslation\n        method: GET\n        description: JupyterLab Get translation bundle\n        inputParameters:\n        - name: locale\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: licenses\n      path: /licenses\n      operations:\n      - name: getlicenses\n        method: GET\n        description: JupyterLab Get licenses report\n        inputParameters:\n        - name: bundles\n          in: query\n          type: string\n          description: Comma-separated list of bundles to include in the report.\n        - name: full_text\n          in: query\n          type: boolean\n          description:\
  \ Whether to include the full text of each license.\n        - name: format\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: listings-jupyterlab-extensionmanager-extension-l\n      path: /listings/@jupyterlab/extensionmanager-extension/listings.json\n      operations:\n      - name: getlistings\n        method: GET\n        description: JupyterLab Get extension listings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: jupyterlab-rest\n    description: REST adapter for JupyterLab Server REST API.\n    resources:\n    - path: /settings\n      name: listsettings\n      operations:\n      - method: GET\n        name: listsettings\n        description: JupyterLab List all settings\n        call: jupyterlab.listsettings\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /settings/{schema_name}\n      name: getsetting\n      operations:\n      - method: GET\n        name: getsetting\n        description: JupyterLab Get setting\n        call: jupyterlab.getsetting\n        with:\n          schema_name: rest.schema_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /settings/{schema_name}\n      name: updatesetting\n      operations:\n      - method: PUT\n        name: updatesetting\n        description: JupyterLab Update setting\n        call: jupyterlab.updatesetting\n        with:\n          schema_name: rest.schema_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: JupyterLab List workspaces\n        call: jupyterlab.listworkspaces\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /workspaces/{space_name}\n      name: getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: JupyterLab Get workspace\n        call: jupyterlab.getworkspace\n        with:\n          space_name: rest.space_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{space_name}\n      name: updateworkspace\n      operations:\n      - method: PUT\n        name: updateworkspace\n        description: JupyterLab Update workspace\n        call: jupyterlab.updateworkspace\n        with:\n          space_name: rest.space_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workspaces/{space_name}\n      name: deleteworkspace\n      operations:\n      - method: DELETE\n        name: deleteworkspace\n        description: JupyterLab Delete workspace\n        call: jupyterlab.deleteworkspace\n        with:\n\
  \          space_name: rest.space_name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /themes/{theme_file}\n      name: getthemeasset\n      operations:\n      - method: GET\n        name: getthemeasset\n        description: JupyterLab Get theme asset\n        call: jupyterlab.getthemeasset\n        with:\n          theme_file: rest.theme_file\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /translations\n      name: listtranslations\n      operations:\n      - method: GET\n        name: listtranslations\n        description: JupyterLab List translations\n        call: jupyterlab.listtranslations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /translations/{locale}\n      name: gettranslation\n      operations:\n      - method: GET\n        name: gettranslation\n        description: JupyterLab Get translation bundle\n        call: jupyterlab.gettranslation\n        with:\n\
  \          locale: rest.locale\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /licenses\n      name: getlicenses\n      operations:\n      - method: GET\n        name: getlicenses\n        description: JupyterLab Get licenses report\n        call: jupyterlab.getlicenses\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /listings/@jupyterlab/extensionmanager-extension/listings.json\n      name: getlistings\n      operations:\n      - method: GET\n        name: getlistings\n        description: JupyterLab Get extension listings\n        call: jupyterlab.getlistings\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: jupyterlab-mcp\n    transport: http\n    description: MCP adapter for JupyterLab Server REST API for AI agent use.\n    tools:\n    - name: listsettings\n      description: JupyterLab List all settings\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.listsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsetting\n      description: JupyterLab Get setting\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.getsetting\n      with:\n        schema_name: tools.schema_name\n      inputParameters:\n      - name: schema_name\n        type: string\n        description: Plugin schema identifier (for example @jupyterlab/apputils-extension:themes).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesetting\n      description: JupyterLab Update setting\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: jupyterlab.updatesetting\n      with:\n        schema_name: tools.schema_name\n      inputParameters:\n      - name: schema_name\n        type:\
  \ string\n        description: schema_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkspaces\n      description: JupyterLab List workspaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.listworkspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkspace\n      description: JupyterLab Get workspace\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.getworkspace\n      with:\n        space_name: tools.space_name\n      inputParameters:\n      - name: space_name\n        type: string\n        description: space_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkspace\n      description: JupyterLab Update workspace\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: jupyterlab.updateworkspace\n      with:\n        space_name: tools.space_name\n      inputParameters:\n      - name: space_name\n        type: string\n        description: space_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteworkspace\n      description: JupyterLab Delete workspace\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: jupyterlab.deleteworkspace\n      with:\n        space_name: tools.space_name\n      inputParameters:\n      - name: space_name\n        type: string\n        description: space_name\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getthemeasset\n      description: JupyterLab Get theme asset\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.getthemeasset\n      with:\n        theme_file:\
  \ tools.theme_file\n      inputParameters:\n      - name: theme_file\n        type: string\n        description: theme_file\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtranslations\n      description: JupyterLab List translations\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.listtranslations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettranslation\n      description: JupyterLab Get translation bundle\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.gettranslation\n      with:\n        locale: tools.locale\n      inputParameters:\n      - name: locale\n        type: string\n        description: locale\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlicenses\n      description: JupyterLab Get\
  \ licenses report\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.getlicenses\n      with:\n        bundles: tools.bundles\n        full_text: tools.full_text\n        format: tools.format\n      inputParameters:\n      - name: bundles\n        type: string\n        description: Comma-separated list of bundles to include in the report.\n      - name: full_text\n        type: boolean\n        description: Whether to include the full text of each license.\n      - name: format\n        type: string\n        description: format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getlistings\n      description: JupyterLab Get extension listings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: jupyterlab.getlistings\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    JUPYTERLAB_TOKEN:\
  \ JUPYTERLAB_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/jupyterlab/refs/heads/main/capabilities/jupyterlab-capability.yaml
tags:
- Jupyterlab
- API
tools:
- description: JupyterLab List all settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsettings
- description: JupyterLab Get setting
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsetting
- description: JupyterLab Update setting
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesetting
- description: JupyterLab List workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: JupyterLab Get workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: JupyterLab Update workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateworkspace
- description: JupyterLab Delete workspace
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteworkspace
- description: JupyterLab Get theme asset
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getthemeasset
- description: JupyterLab List translations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtranslations
- description: JupyterLab Get translation bundle
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettranslation
- description: JupyterLab Get licenses report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlicenses
- description: JupyterLab Get extension listings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlistings
---
