---
categories: []
consumed_apis: []
description: The Finout API provides seamless access to powerful cloud cost management tools, enabling you to integrate, analyze, and optimize your cloud expenses. It includes endpoints for cost insights, tagging, forecasting, and more, empowering teams to automate workflows, track spending, and drive efficiency across cloud environments.
layout: capability
name: Finout API
operations:
- description: Finout Query costs for a view
  method: POST
  name: querycosts
  path: /view
- description: Finout Get all virtual tags
  method: GET
  name: listvirtualtags
  path: /virtual-tag
- description: Finout Create a virtual tag
  method: POST
  name: createvirtualtag
  path: /virtual-tag
- description: Finout Update a virtual tag
  method: PUT
  name: updatevirtualtag
  path: /virtual-tag
- description: Finout Get a virtual tag by ID
  method: GET
  name: getvirtualtagbyid
  path: /virtual-tag/{id}
- description: Finout Delete a virtual tag
  method: DELETE
  name: deletevirtualtag
  path: /virtual-tag/{id}
- description: Finout Get virtual tag metadata
  method: GET
  name: getvirtualtagmetadata
  path: /virtual-tags/{virtualTagId}/metadata
- description: Finout Update virtual tag metadata
  method: PUT
  name: updatevirtualtagmetadata
  path: /virtual-tags/{virtualTagId}/metadata
- description: Finout Get all MegaBill keys
  method: GET
  name: getmegabillkeys
  path: /megabill/query-language/keys
- description: Finout Get values for a MegaBill key
  method: GET
  name: getmegabillkeyvalues
  path: /megabill/query-language/values/{costCenter}/{key}
- description: Finout Get MegaBill virtual tags
  method: GET
  name: getmegabillvirtualtags
  path: /megabill/query-language/virtual-tags
- description: Finout Get all CostGuard scans
  method: GET
  name: listcostguardscans
  path: /cost-guard/scans
- description: Finout Get scan recommendations
  method: POST
  name: getcostguardscanrecommendations
  path: /cost-guard/scans-recommendations
- description: Finout Get all endpoints
  method: GET
  name: listendpoints
  path: /endpoints
- description: Finout Create an endpoint
  method: POST
  name: createendpoint
  path: /endpoints
personas: []
provider_name: Finout
provider_slug: finout
search_terms:
- createendpoint
- finout get scan recommendations
- updatevirtualtagmetadata
- finout
- finout create a virtual tag
- finout update virtual tag metadata
- listvirtualtags
- api
- finout get all megabill keys
- getvirtualtagmetadata
- finout get virtual tag metadata
- getmegabillkeyvalues
- createvirtualtag
- updatevirtualtag
- finout get values for a megabill key
- listendpoints
- getvirtualtagbyid
- getmegabillkeys
- getcostguardscanrecommendations
- finout get all endpoints
- finout get all costguard scans
- getmegabillvirtualtags
- listcostguardscans
- finout create an endpoint
- finout get a virtual tag by id
- finout query costs for a view
- finout delete a virtual tag
- querycosts
- deletevirtualtag
- budgets
- finout get all virtual tags
- finout get megabill virtual tags
- finout update a virtual tag
- costs
- finops
slug: finout-capability
source_filename: finout-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Finout API\n  description: The Finout API provides seamless access to powerful cloud cost management tools, enabling you to integrate,\n    analyze, and optimize your cloud expenses. It includes endpoints for cost insights, tagging, forecasting, and more, empowering\n    teams to automate workflows, track spending, and drive efficiency across cloud environments.\n  tags:\n  - Finout\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: finout\n    baseUri: https://app.finout.io/v1\n    description: Finout API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-finout-client-id\n      value: '{{FINOUT_TOKEN}}'\n    resources:\n    - name: view\n      path: /view\n      operations:\n      - name: querycosts\n        method: POST\n        description: Finout Query costs for a view\n        outputRawFormat: json\n        outputParameters:\n    \
  \    - name: result\n          type: object\n          value: $.\n    - name: virtual-tag\n      path: /virtual-tag\n      operations:\n      - name: listvirtualtags\n        method: GET\n        description: Finout Get all virtual tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createvirtualtag\n        method: POST\n        description: Finout Create a virtual tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevirtualtag\n        method: PUT\n        description: Finout Update a virtual tag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-tag-id\n      path: /virtual-tag/{id}\n      operations:\n      - name: getvirtualtagbyid\n        method: GET\n        description: Finout Get a virtual\
  \ tag by ID\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the virtual tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletevirtualtag\n        method: DELETE\n        description: Finout Delete a virtual tag\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the virtual tag to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: virtual-tags-virtualtagid-metadata\n      path: /virtual-tags/{virtualTagId}/metadata\n      operations:\n      - name: getvirtualtagmetadata\n        method: GET\n        description: Finout Get virtual tag metadata\n        inputParameters:\n\
  \        - name: virtualTagId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the virtual tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatevirtualtagmetadata\n        method: PUT\n        description: Finout Update virtual tag metadata\n        inputParameters:\n        - name: virtualTagId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the virtual tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: megabill-query-language-keys\n      path: /megabill/query-language/keys\n      operations:\n      - name: getmegabillkeys\n        method: GET\n        description: Finout Get all MegaBill keys\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n    - name: megabill-query-language-values-costcenter-key\n      path: /megabill/query-language/values/{costCenter}/{key}\n      operations:\n      - name: getmegabillkeyvalues\n        method: GET\n        description: Finout Get values for a MegaBill key\n        inputParameters:\n        - name: costCenter\n          in: path\n          type: string\n          required: true\n          description: The cost center to query (e.g., AWS, GCP, Azure).\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The MegaBill key to retrieve values for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: megabill-query-language-virtual-tags\n      path: /megabill/query-language/virtual-tags\n      operations:\n      - name: getmegabillvirtualtags\n        method: GET\n        description:\
  \ Finout Get MegaBill virtual tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-guard-scans\n      path: /cost-guard/scans\n      operations:\n      - name: listcostguardscans\n        method: GET\n        description: Finout Get all CostGuard scans\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-guard-scans-recommendations\n      path: /cost-guard/scans-recommendations\n      operations:\n      - name: getcostguardscanrecommendations\n        method: POST\n        description: Finout Get scan recommendations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: endpoints\n      path: /endpoints\n      operations:\n      - name: listendpoints\n        method: GET\n        description: Finout Get all endpoints\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createendpoint\n        method: POST\n        description: Finout Create an endpoint\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: finout-rest\n    description: REST adapter for Finout API.\n    resources:\n    - path: /view\n      name: querycosts\n      operations:\n      - method: POST\n        name: querycosts\n        description: Finout Query costs for a view\n        call: finout.querycosts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tag\n      name: listvirtualtags\n      operations:\n      - method: GET\n        name: listvirtualtags\n        description: Finout Get all virtual tags\n        call: finout.listvirtualtags\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /virtual-tag\n      name: createvirtualtag\n      operations:\n      - method: POST\n        name: createvirtualtag\n        description: Finout Create a virtual tag\n        call: finout.createvirtualtag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tag\n      name: updatevirtualtag\n      operations:\n      - method: PUT\n        name: updatevirtualtag\n        description: Finout Update a virtual tag\n        call: finout.updatevirtualtag\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tag/{id}\n      name: getvirtualtagbyid\n      operations:\n      - method: GET\n        name: getvirtualtagbyid\n        description: Finout Get a virtual tag by ID\n        call: finout.getvirtualtagbyid\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tag/{id}\n\
  \      name: deletevirtualtag\n      operations:\n      - method: DELETE\n        name: deletevirtualtag\n        description: Finout Delete a virtual tag\n        call: finout.deletevirtualtag\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tags/{virtualTagId}/metadata\n      name: getvirtualtagmetadata\n      operations:\n      - method: GET\n        name: getvirtualtagmetadata\n        description: Finout Get virtual tag metadata\n        call: finout.getvirtualtagmetadata\n        with:\n          virtualTagId: rest.virtualTagId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /virtual-tags/{virtualTagId}/metadata\n      name: updatevirtualtagmetadata\n      operations:\n      - method: PUT\n        name: updatevirtualtagmetadata\n        description: Finout Update virtual tag metadata\n        call: finout.updatevirtualtagmetadata\n        with:\n          virtualTagId:\
  \ rest.virtualTagId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /megabill/query-language/keys\n      name: getmegabillkeys\n      operations:\n      - method: GET\n        name: getmegabillkeys\n        description: Finout Get all MegaBill keys\n        call: finout.getmegabillkeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /megabill/query-language/values/{costCenter}/{key}\n      name: getmegabillkeyvalues\n      operations:\n      - method: GET\n        name: getmegabillkeyvalues\n        description: Finout Get values for a MegaBill key\n        call: finout.getmegabillkeyvalues\n        with:\n          costCenter: rest.costCenter\n          key: rest.key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /megabill/query-language/virtual-tags\n      name: getmegabillvirtualtags\n      operations:\n      - method: GET\n        name: getmegabillvirtualtags\n    \
  \    description: Finout Get MegaBill virtual tags\n        call: finout.getmegabillvirtualtags\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cost-guard/scans\n      name: listcostguardscans\n      operations:\n      - method: GET\n        name: listcostguardscans\n        description: Finout Get all CostGuard scans\n        call: finout.listcostguardscans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cost-guard/scans-recommendations\n      name: getcostguardscanrecommendations\n      operations:\n      - method: POST\n        name: getcostguardscanrecommendations\n        description: Finout Get scan recommendations\n        call: finout.getcostguardscanrecommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: listendpoints\n      operations:\n      - method: GET\n        name: listendpoints\n        description: Finout Get all endpoints\n\
  \        call: finout.listendpoints\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /endpoints\n      name: createendpoint\n      operations:\n      - method: POST\n        name: createendpoint\n        description: Finout Create an endpoint\n        call: finout.createendpoint\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: finout-mcp\n    transport: http\n    description: MCP adapter for Finout API for AI agent use.\n    tools:\n    - name: querycosts\n      description: Finout Query costs for a view\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finout.querycosts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listvirtualtags\n      description: Finout Get all virtual tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.listvirtualtags\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createvirtualtag\n      description: Finout Create a virtual tag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finout.createvirtualtag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatevirtualtag\n      description: Finout Update a virtual tag\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: finout.updatevirtualtag\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvirtualtagbyid\n      description: Finout Get a virtual tag by ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.getvirtualtagbyid\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: The unique identifier of the virtual tag.\n  \
  \      required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletevirtualtag\n      description: Finout Delete a virtual tag\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: finout.deletevirtualtag\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: string\n        description: The unique identifier of the virtual tag to delete.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getvirtualtagmetadata\n      description: Finout Get virtual tag metadata\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.getvirtualtagmetadata\n      with:\n        virtualTagId: tools.virtualTagId\n      inputParameters:\n      - name: virtualTagId\n        type: string\n        description: The unique identifier of the virtual tag.\n        required: true\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatevirtualtagmetadata\n      description: Finout Update virtual tag metadata\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: finout.updatevirtualtagmetadata\n      with:\n        virtualTagId: tools.virtualTagId\n      inputParameters:\n      - name: virtualTagId\n        type: string\n        description: The unique identifier of the virtual tag.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmegabillkeys\n      description: Finout Get all MegaBill keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.getmegabillkeys\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmegabillkeyvalues\n      description: Finout Get values for a MegaBill key\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: finout.getmegabillkeyvalues\n      with:\n        costCenter: tools.costCenter\n        key: tools.key\n      inputParameters:\n      - name: costCenter\n        type: string\n        description: The cost center to query (e.g., AWS, GCP, Azure).\n        required: true\n      - name: key\n        type: string\n        description: The MegaBill key to retrieve values for.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmegabillvirtualtags\n      description: Finout Get MegaBill virtual tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.getmegabillvirtualtags\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcostguardscans\n      description: Finout Get all CostGuard scans\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.listcostguardscans\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcostguardscanrecommendations\n      description: Finout Get scan recommendations\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finout.getcostguardscanrecommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listendpoints\n      description: Finout Get all endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: finout.listendpoints\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createendpoint\n      description: Finout Create an endpoint\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: finout.createendpoint\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FINOUT_TOKEN: FINOUT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/finout/refs/heads/main/capabilities/finout-capability.yaml
tags:
- Finout
- API
tools:
- description: Finout Query costs for a view
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querycosts
- description: Finout Get all virtual tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listvirtualtags
- description: Finout Create a virtual tag
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvirtualtag
- description: Finout Update a virtual tag
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevirtualtag
- description: Finout Get a virtual tag by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvirtualtagbyid
- description: Finout Delete a virtual tag
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletevirtualtag
- description: Finout Get virtual tag metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvirtualtagmetadata
- description: Finout Update virtual tag metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatevirtualtagmetadata
- description: Finout Get all MegaBill keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmegabillkeys
- description: Finout Get values for a MegaBill key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmegabillkeyvalues
- description: Finout Get MegaBill virtual tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmegabillvirtualtags
- description: Finout Get all CostGuard scans
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcostguardscans
- description: Finout Get scan recommendations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getcostguardscanrecommendations
- description: Finout Get all endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listendpoints
- description: Finout Create an endpoint
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createendpoint
---
