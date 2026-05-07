---
categories: []
consumed_apis: []
description: The Doctave API provides programmatic access to manage documentation sites, deployments, pages, and search on the Doctave docs-as-code platform. It allows teams to automate documentation workflows, trigger deployments, manage site configurations, and integrate documentation search into their own applications and developer portals.
layout: capability
name: Doctave API
operations:
- description: Doctave List Sites
  method: GET
  name: listsites
  path: /sites
- description: Doctave Create Site
  method: POST
  name: createsite
  path: /sites
- description: Doctave Get Site
  method: GET
  name: getsite
  path: /sites/{siteId}
- description: Doctave Update Site
  method: PUT
  name: updatesite
  path: /sites/{siteId}
- description: Doctave Delete Site
  method: DELETE
  name: deletesite
  path: /sites/{siteId}
- description: Doctave List Deployments
  method: GET
  name: listdeployments
  path: /sites/{siteId}/deployments
- description: Doctave Create Deployment
  method: POST
  name: createdeployment
  path: /sites/{siteId}/deployments
- description: Doctave Get Deployment
  method: GET
  name: getdeployment
  path: /sites/{siteId}/deployments/{deploymentId}
- description: Doctave List Pages
  method: GET
  name: listpages
  path: /sites/{siteId}/pages
- description: Doctave Create Page
  method: POST
  name: createpage
  path: /sites/{siteId}/pages
- description: Doctave Get Page
  method: GET
  name: getpage
  path: /sites/{siteId}/pages/{pageId}
- description: Doctave Update Page
  method: PUT
  name: updatepage
  path: /sites/{siteId}/pages/{pageId}
- description: Doctave Delete Page
  method: DELETE
  name: deletepage
  path: /sites/{siteId}/pages/{pageId}
- description: Doctave Search Site
  method: GET
  name: searchsite
  path: /sites/{siteId}/search
personas: []
provider_name: Doctave
provider_slug: doctave
search_terms:
- doctave delete page
- doctave get page
- doctave list pages
- searchsite
- updatesite
- doctave update site
- api
- platform
- getsite
- listsites
- deletepage
- doctave
- openapi
- documentation
- portals
- deletesite
- listpages
- doctave search site
- createsite
- doctave list deployments
- doctave list sites
- doctave create page
- doctave create deployment
- getdeployment
- doctave delete site
- createpage
- updatepage
- createdeployment
- listdeployments
- doctave update page
- getpage
- doctave get deployment
- doctave create site
- doctave get site
slug: doctave-capability
source_filename: doctave-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Doctave API\n  description: The Doctave API provides programmatic access to manage documentation sites, deployments, pages, and search\n    on the Doctave docs-as-code platform. It allows teams to automate documentation workflows, trigger deployments, manage\n    site configurations, and integrate documentation search into their own applications and developer portals.\n  tags:\n  - Doctave\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: doctave\n    baseUri: https://api.doctave.com/v1\n    description: Doctave API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DOCTAVE_TOKEN}}'\n    resources:\n    - name: sites\n      path: /sites\n      operations:\n      - name: listsites\n        method: GET\n        description: Doctave List Sites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n      - name: createsite\n        method: POST\n        description: Doctave Create Site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid\n      path: /sites/{siteId}\n      operations:\n      - name: getsite\n        method: GET\n        description: Doctave Get Site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesite\n        method: PUT\n        description: Doctave Update Site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesite\n        method: DELETE\n        description: Doctave Delete Site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid-deployments\n      path:\
  \ /sites/{siteId}/deployments\n      operations:\n      - name: listdeployments\n        method: GET\n        description: Doctave List Deployments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeployment\n        method: POST\n        description: Doctave Create Deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid-deployments-deploymentid\n      path: /sites/{siteId}/deployments/{deploymentId}\n      operations:\n      - name: getdeployment\n        method: GET\n        description: Doctave Get Deployment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid-pages\n      path: /sites/{siteId}/pages\n      operations:\n      - name: listpages\n        method: GET\n        description:\
  \ Doctave List Pages\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpage\n        method: POST\n        description: Doctave Create Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid-pages-pageid\n      path: /sites/{siteId}/pages/{pageId}\n      operations:\n      - name: getpage\n        method: GET\n        description: Doctave Get Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepage\n        method: PUT\n        description: Doctave Update Page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepage\n        method: DELETE\n        description: Doctave Delete Page\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-siteid-search\n      path: /sites/{siteId}/search\n      operations:\n      - name: searchsite\n        method: GET\n        description: Doctave Search Site\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: true\n          description: The search query string.\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return.\n        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: doctave-rest\n    description: REST adapter for Doctave API.\n    resources:\n    - path: /sites\n   \
  \   name: listsites\n      operations:\n      - method: GET\n        name: listsites\n        description: Doctave List Sites\n        call: doctave.listsites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites\n      name: createsite\n      operations:\n      - method: POST\n        name: createsite\n        description: Doctave Create Site\n        call: doctave.createsite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}\n      name: getsite\n      operations:\n      - method: GET\n        name: getsite\n        description: Doctave Get Site\n        call: doctave.getsite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}\n      name: updatesite\n      operations:\n      - method: PUT\n        name: updatesite\n        description: Doctave Update Site\n        call: doctave.updatesite\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /sites/{siteId}\n      name: deletesite\n      operations:\n      - method: DELETE\n        name: deletesite\n        description: Doctave Delete Site\n        call: doctave.deletesite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/deployments\n      name: listdeployments\n      operations:\n      - method: GET\n        name: listdeployments\n        description: Doctave List Deployments\n        call: doctave.listdeployments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/deployments\n      name: createdeployment\n      operations:\n      - method: POST\n        name: createdeployment\n        description: Doctave Create Deployment\n        call: doctave.createdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/deployments/{deploymentId}\n      name: getdeployment\n      operations:\n\
  \      - method: GET\n        name: getdeployment\n        description: Doctave Get Deployment\n        call: doctave.getdeployment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/pages\n      name: listpages\n      operations:\n      - method: GET\n        name: listpages\n        description: Doctave List Pages\n        call: doctave.listpages\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/pages\n      name: createpage\n      operations:\n      - method: POST\n        name: createpage\n        description: Doctave Create Page\n        call: doctave.createpage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/pages/{pageId}\n      name: getpage\n      operations:\n      - method: GET\n        name: getpage\n        description: Doctave Get Page\n        call: doctave.getpage\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /sites/{siteId}/pages/{pageId}\n      name: updatepage\n      operations:\n      - method: PUT\n        name: updatepage\n        description: Doctave Update Page\n        call: doctave.updatepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/pages/{pageId}\n      name: deletepage\n      operations:\n      - method: DELETE\n        name: deletepage\n        description: Doctave Delete Page\n        call: doctave.deletepage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /sites/{siteId}/search\n      name: searchsite\n      operations:\n      - method: GET\n        name: searchsite\n        description: Doctave Search Site\n        call: doctave.searchsite\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: doctave-mcp\n    transport: http\n    description: MCP adapter for Doctave API for\
  \ AI agent use.\n    tools:\n    - name: listsites\n      description: Doctave List Sites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.listsites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsite\n      description: Doctave Create Site\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doctave.createsite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsite\n      description: Doctave Get Site\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.getsite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesite\n      description: Doctave Update Site\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: doctave.updatesite\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: deletesite\n      description: Doctave Delete Site\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: doctave.deletesite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdeployments\n      description: Doctave List Deployments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.listdeployments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdeployment\n      description: Doctave Create Deployment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doctave.createdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getdeployment\n      description: Doctave Get Deployment\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent:\
  \ true\n      call: doctave.getdeployment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpages\n      description: Doctave List Pages\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.listpages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createpage\n      description: Doctave Create Page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: doctave.createpage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getpage\n      description: Doctave Get Page\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.getpage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepage\n      description: Doctave Update Page\n      hints:\n        readOnly: false\n        destructive: false\n\
  \        idempotent: true\n      call: doctave.updatepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletepage\n      description: Doctave Delete Page\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: doctave.deletepage\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchsite\n      description: Doctave Search Site\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: doctave.searchsite\n      with:\n        q: tools.q\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: q\n        type: string\n        description: The search query string.\n        required: true\n      - name: limit\n        type: integer\n        description: Maximum number of results to return.\n      - name: offset\n        type: integer\n        description: Number of results to skip for pagination.\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DOCTAVE_TOKEN: DOCTAVE_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/doctave/refs/heads/main/capabilities/doctave-capability.yaml
tags:
- Doctave
- API
tools:
- description: Doctave List Sites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
- description: Doctave Create Site
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsite
- description: Doctave Get Site
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsite
- description: Doctave Update Site
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesite
- description: Doctave Delete Site
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesite
- description: Doctave List Deployments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdeployments
- description: Doctave Create Deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Doctave Get Deployment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: Doctave List Pages
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpages
- description: Doctave Create Page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpage
- description: Doctave Get Page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpage
- description: Doctave Update Page
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepage
- description: Doctave Delete Page
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepage
- description: Doctave Search Site
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsite
---
