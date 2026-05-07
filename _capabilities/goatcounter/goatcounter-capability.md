---
categories: []
consumed_apis: []
description: The GoatCounter API can be used to manage sites, users, count pageviews, export raw data, retrieve statistics, and build custom dashboards on top of GoatCounter web analytics.
layout: capability
name: GoatCounter API
operations:
- description: Count pageviews
  method: POST
  name: count
  path: /count
- description: Create CSV export
  method: POST
  name: createexport
  path: /export
- description: Get export info
  method: GET
  name: getexport
  path: /export/{id}
- description: Download export
  method: GET
  name: downloadexport
  path: /export/{id}/download
- description: List total pageview counts
  method: GET
  name: statstotal
  path: /stats/total
- description: View/visitor stats per path
  method: GET
  name: statshits
  path: /stats/hits
- description: Referral stats for a path
  method: GET
  name: statshitsrefs
  path: /stats/hits/{path_id}
- description: Stats for a category (browser, system, location, etc.)
  method: GET
  name: statsbypage
  path: /stats/{page}
- description: Detailed stats within a category
  method: GET
  name: statsbypagedetail
  path: /stats/{page}/{id}
- description: List sites
  method: GET
  name: listsites
  path: /sites
- description: Create a new site
  method: PUT
  name: createsite
  path: /sites
- description: Get site detail
  method: GET
  name: getsite
  path: /sites/{id}
- description: Update a site
  method: POST
  name: updatesitepost
  path: /sites/{id}
- description: Patch a site
  method: PATCH
  name: patchsite
  path: /sites/{id}
- description: Get current user
  method: GET
  name: getme
  path: /me
- description: List paths
  method: GET
  name: listpaths
  path: /paths
personas: []
provider_name: GoatCounter
provider_slug: goatcounter
search_terms:
- list paths
- create a new site
- analytics
- get site detail
- patchsite
- web analytics
- api
- getsite
- statsbypagedetail
- listsites
- statshitsrefs
- statshits
- privacy
- count pageviews
- patch a site
- create csv export
- updatesitepost
- list sites
- get export info
- statsbypage
- createsite
- count
- getme
- pageviews
- update a site
- goatcounter
- downloadexport
- download export
- statstotal
- list total pageview counts
- stats for a category (browser, system, location, etc.)
- view/visitor stats per path
- referral stats for a path
- getexport
- get current user
- listpaths
- statistics
- detailed stats within a category
- createexport
slug: goatcounter-capability
source_filename: goatcounter-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: GoatCounter API\n  description: The GoatCounter API can be used to manage sites, users, count pageviews, export raw data, retrieve statistics,\n    and build custom dashboards on top of GoatCounter web analytics.\n  tags:\n  - Goatcounter\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: goatcounter\n    baseUri: https://goatcounter.com/api/v0\n    description: GoatCounter API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOATCOUNTER_TOKEN}}'\n    resources:\n    - name: count\n      path: /count\n      operations:\n      - name: count\n        method: POST\n        description: Count pageviews\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export\n      path: /export\n      operations:\n      - name: createexport\n        method: POST\n        description:\
  \ Create CSV export\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-id\n      path: /export/{id}\n      operations:\n      - name: getexport\n        method: GET\n        description: Get export info\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: export-id-download\n      path: /export/{id}/download\n      operations:\n      - name: downloadexport\n        method: GET\n        description: Download export\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-total\n      path:\
  \ /stats/total\n      operations:\n      - name: statstotal\n        method: GET\n        description: List total pageview counts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-hits\n      path: /stats/hits\n      operations:\n      - name: statshits\n        method: GET\n        description: View/visitor stats per path\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: include_paths\n          in: query\n          type: array\n        - name: exclude_paths\n          in: query\n          type: array\n        - name: daily\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-hits-path-id\n      path: /stats/hits/{path_id}\n      operations:\n      - name: statshitsrefs\n        method: GET\n\
  \        description: Referral stats for a path\n        inputParameters:\n        - name: path_id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-page\n      path: /stats/{page}\n      operations:\n      - name: statsbypage\n        method: GET\n        description: Stats for a category (browser, system, location, etc.)\n        inputParameters:\n        - name: page\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: stats-page-id\n      path: /stats/{page}/{id}\n      operations:\n      - name: statsbypagedetail\n        method: GET\n        description: Detailed stats within a category\n        inputParameters:\n        - name: page\n          in: path\n      \
  \    type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites\n      path: /sites\n      operations:\n      - name: listsites\n        method: GET\n        description: List sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsite\n        method: PUT\n        description: Create a new site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-id\n      path: /sites/{id}\n      operations:\n      - name: getsite\n        method: GET\n        description: Get site detail\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitepost\n        method: POST\n        description: Update a site\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchsite\n        method: PATCH\n        description: Patch a site\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: me\n      path: /me\n      operations:\n      - name: getme\n        method: GET\n        description: Get current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: paths\n      path: /paths\n      operations:\n      - name: listpaths\n        method: GET\n        description: List paths\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n        - name: after\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: goatcounter-rest\n    description: REST adapter for GoatCounter API.\n    resources:\n    - path: /count\n      name: count\n      operations:\n      - method: POST\n        name: count\n        description: Count pageviews\n        call: goatcounter.count\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /export\n      name: createexport\n      operations:\n      - method: POST\n        name: createexport\n        description:\
  \ Create CSV export\n        call: goatcounter.createexport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /export/{id}\n      name: getexport\n      operations:\n      - method: GET\n        name: getexport\n        description: Get export info\n        call: goatcounter.getexport\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /export/{id}/download\n      name: downloadexport\n      operations:\n      - method: GET\n        name: downloadexport\n        description: Download export\n        call: goatcounter.downloadexport\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/total\n      name: statstotal\n      operations:\n      - method: GET\n        name: statstotal\n        description: List total pageview counts\n        call: goatcounter.statstotal\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /stats/hits\n      name: statshits\n      operations:\n      - method: GET\n        name: statshits\n        description: View/visitor stats per path\n        call: goatcounter.statshits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/hits/{path_id}\n      name: statshitsrefs\n      operations:\n      - method: GET\n        name: statshitsrefs\n        description: Referral stats for a path\n        call: goatcounter.statshitsrefs\n        with:\n          path_id: rest.path_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /stats/{page}\n      name: statsbypage\n      operations:\n      - method: GET\n        name: statsbypage\n        description: Stats for a category (browser, system, location, etc.)\n        call: goatcounter.statsbypage\n        with:\n          page: rest.page\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /stats/{page}/{id}\n      name: statsbypagedetail\n      operations:\n      - method: GET\n        name: statsbypagedetail\n        description: Detailed stats within a category\n        call: goatcounter.statsbypagedetail\n        with:\n          page: rest.page\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites\n      name: listsites\n      operations:\n      - method: GET\n        name: listsites\n        description: List sites\n        call: goatcounter.listsites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites\n      name: createsite\n      operations:\n      - method: PUT\n        name: createsite\n        description: Create a new site\n        call: goatcounter.createsite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{id}\n      name: getsite\n      operations:\n      - method: GET\n        name: getsite\n\
  \        description: Get site detail\n        call: goatcounter.getsite\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{id}\n      name: updatesitepost\n      operations:\n      - method: POST\n        name: updatesitepost\n        description: Update a site\n        call: goatcounter.updatesitepost\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{id}\n      name: patchsite\n      operations:\n      - method: PATCH\n        name: patchsite\n        description: Patch a site\n        call: goatcounter.patchsite\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /me\n      name: getme\n      operations:\n      - method: GET\n        name: getme\n        description: Get current user\n        call: goatcounter.getme\n        outputParameters:\n    \
  \    - type: object\n          mapping: $.\n    - path: /paths\n      name: listpaths\n      operations:\n      - method: GET\n        name: listpaths\n        description: List paths\n        call: goatcounter.listpaths\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: goatcounter-mcp\n    transport: http\n    description: MCP adapter for GoatCounter API for AI agent use.\n    tools:\n    - name: count\n      description: Count pageviews\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goatcounter.count\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createexport\n      description: Create CSV export\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goatcounter.createexport\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getexport\n    \
  \  description: Get export info\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.getexport\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: downloadexport\n      description: Download export\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.downloadexport\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: statstotal\n      description: List total pageview counts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.statstotal\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: statshits\n      description: View/visitor stats per path\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.statshits\n      with:\n        limit: tools.limit\n        include_paths: tools.include_paths\n        exclude_paths: tools.exclude_paths\n        daily: tools.daily\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: include_paths\n        type: array\n        description: include_paths\n      - name: exclude_paths\n        type: array\n        description: exclude_paths\n      - name: daily\n        type: boolean\n        description: daily\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: statshitsrefs\n      description: Referral stats for a path\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.statshitsrefs\n\
  \      with:\n        path_id: tools.path_id\n      inputParameters:\n      - name: path_id\n        type: integer\n        description: path_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: statsbypage\n      description: Stats for a category (browser, system, location, etc.)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.statsbypage\n      with:\n        page: tools.page\n      inputParameters:\n      - name: page\n        type: string\n        description: page\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: statsbypagedetail\n      description: Detailed stats within a category\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.statsbypagedetail\n      with:\n        page: tools.page\n        id: tools.id\n      inputParameters:\n    \
  \  - name: page\n        type: string\n        description: page\n        required: true\n      - name: id\n        type: string\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsites\n      description: List sites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.listsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsite\n      description: Create a new site\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: goatcounter.createsite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsite\n      description: Get site detail\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.getsite\n      with:\n        id: tools.id\n      inputParameters:\n   \
  \   - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesitepost\n      description: Update a site\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goatcounter.updatesitepost\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: patchsite\n      description: Patch a site\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: goatcounter.patchsite\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getme\n      description:\
  \ Get current user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.getme\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpaths\n      description: List paths\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: goatcounter.listpaths\n      with:\n        limit: tools.limit\n        after: tools.after\n      inputParameters:\n      - name: limit\n        type: integer\n        description: limit\n      - name: after\n        type: integer\n        description: after\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOATCOUNTER_TOKEN: GOATCOUNTER_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/goatcounter/refs/heads/main/capabilities/goatcounter-capability.yaml
tags:
- Goatcounter
- API
tools:
- description: Count pageviews
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: count
- description: Create CSV export
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createexport
- description: Get export info
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getexport
- description: Download export
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloadexport
- description: List total pageview counts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: statstotal
- description: View/visitor stats per path
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: statshits
- description: Referral stats for a path
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: statshitsrefs
- description: Stats for a category (browser, system, location, etc.)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: statsbypage
- description: Detailed stats within a category
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: statsbypagedetail
- description: List sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
- description: Create a new site
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createsite
- description: Get site detail
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsite
- description: Update a site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesitepost
- description: Patch a site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchsite
- description: Get current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getme
- description: List paths
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpaths
---
