---
categories: []
consumed_apis: []
description: The CourtListener REST API (operated by Free Law Project) provides programmatic access to case law, PACER data, the RECAP archive, oral arguments, judges, financial disclosures, citations, citation networks, alerts, tags, and visualizations.
layout: capability
name: Free Law Project / CourtListener REST API
operations:
- description: Search across CourtListener
  method: GET
  name: search
  path: /search/
- description: List opinions
  method: GET
  name: listopinions
  path: /opinions/
- description: Retrieve an opinion
  method: GET
  name: getopinion
  path: /opinions/{id}/
- description: List opinion clusters
  method: GET
  name: listclusters
  path: /clusters/
- description: List dockets
  method: GET
  name: listdockets
  path: /dockets/
- description: List docket entries
  method: GET
  name: listdocketentries
  path: /docket-entries/
- description: List RECAP documents
  method: GET
  name: listrecapdocuments
  path: /recap-documents/
- description: List oral arguments
  method: GET
  name: listoralarguments
  path: /audio/
- description: List judges and people
  method: GET
  name: listpeople
  path: /people/
- description: List judicial positions
  method: GET
  name: listpositions
  path: /positions/
- description: List financial disclosures
  method: GET
  name: listfinancialdisclosures
  path: /financial-disclosures/
- description: Lookup citations in text
  method: POST
  name: lookupcitations
  path: /citation-lookup/
- description: List alerts
  method: GET
  name: listalerts
  path: /alerts/
- description: Create an alert
  method: POST
  name: createalert
  path: /alerts/
- description: List tags
  method: GET
  name: listtags
  path: /tag/
personas: []
provider_name: Free Law Project
provider_slug: free-law-project
search_terms:
- list dockets
- free
- list tags
- lookupcitations
- create an alert
- search across courtlistener
- listdocketentries
- lookup citations in text
- transparency
- api
- listpositions
- courts
- listalerts
- listpeople
- getopinion
- listtags
- listclusters
- list recap documents
- law
- list judges and people
- list judicial positions
- createalert
- list oral arguments
- list opinion clusters
- list docket entries
- project
- list alerts
- list opinions
- retrieve an opinion
- listrecapdocuments
- search
- justice
- list financial disclosures
- listdockets
- listfinancialdisclosures
- legal
- listopinions
- listoralarguments
slug: free-law-project-capability
source_filename: free-law-project-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Free Law Project / CourtListener REST API\n  description: The CourtListener REST API (operated by Free Law Project) provides programmatic access to case law, PACER data,\n    the RECAP archive, oral arguments, judges, financial disclosures, citations, citation networks, alerts, tags, and visualizations.\n  tags:\n  - Free\n  - Law\n  - Project\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: free-law-project\n    baseUri: https://www.courtlistener.com/api/rest/v4\n    description: Free Law Project / CourtListener REST API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{FREE_LAW_PROJECT_TOKEN}}'\n    resources:\n    - name: search\n      path: /search/\n      operations:\n      - name: search\n        method: GET\n        description: Search across CourtListener\n        inputParameters:\n        - name:\
  \ q\n          in: query\n          type: string\n          description: Search query string.\n        - name: type\n          in: query\n          type: string\n          description: Result type (e.g., o for opinions, r for RECAP, oa for oral arguments, p for people).\n        - name: order_by\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: opinions\n      path: /opinions/\n      operations:\n      - name: listopinions\n        method: GET\n        description: List opinions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: opinions-id\n      path: /opinions/{id}/\n      operations:\n      - name: getopinion\n        method: GET\n        description: Retrieve an opinion\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clusters\n      path: /clusters/\n      operations:\n      - name: listclusters\n        method: GET\n        description: List opinion clusters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dockets\n      path: /dockets/\n      operations:\n      - name: listdockets\n        method: GET\n        description: List dockets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: docket-entries\n      path: /docket-entries/\n      operations:\n      - name: listdocketentries\n        method: GET\n        description: List docket entries\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: recap-documents\n      path: /recap-documents/\n      operations:\n      - name: listrecapdocuments\n        method: GET\n        description: List RECAP documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: audio\n      path: /audio/\n      operations:\n      - name: listoralarguments\n        method: GET\n        description: List oral arguments\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: people\n      path: /people/\n      operations:\n      - name: listpeople\n        method: GET\n        description: List judges and people\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: positions\n      path: /positions/\n      operations:\n\
  \      - name: listpositions\n        method: GET\n        description: List judicial positions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: financial-disclosures\n      path: /financial-disclosures/\n      operations:\n      - name: listfinancialdisclosures\n        method: GET\n        description: List financial disclosures\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: citation-lookup\n      path: /citation-lookup/\n      operations:\n      - name: lookupcitations\n        method: POST\n        description: Lookup citations in text\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alerts\n      path: /alerts/\n      operations:\n      - name: listalerts\n        method: GET\n        description: List alerts\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createalert\n        method: POST\n        description: Create an alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tag\n      path: /tag/\n      operations:\n      - name: listtags\n        method: GET\n        description: List tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: free-law-project-rest\n    description: REST adapter for Free Law Project / CourtListener REST API.\n    resources:\n    - path: /search/\n      name: search\n      operations:\n      - method: GET\n        name: search\n        description: Search across CourtListener\n        call: free-law-project.search\n        outputParameters:\n  \
  \      - type: object\n          mapping: $.\n    - path: /opinions/\n      name: listopinions\n      operations:\n      - method: GET\n        name: listopinions\n        description: List opinions\n        call: free-law-project.listopinions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /opinions/{id}/\n      name: getopinion\n      operations:\n      - method: GET\n        name: getopinion\n        description: Retrieve an opinion\n        call: free-law-project.getopinion\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /clusters/\n      name: listclusters\n      operations:\n      - method: GET\n        name: listclusters\n        description: List opinion clusters\n        call: free-law-project.listclusters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dockets/\n      name: listdockets\n      operations:\n      - method: GET\n\
  \        name: listdockets\n        description: List dockets\n        call: free-law-project.listdockets\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /docket-entries/\n      name: listdocketentries\n      operations:\n      - method: GET\n        name: listdocketentries\n        description: List docket entries\n        call: free-law-project.listdocketentries\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /recap-documents/\n      name: listrecapdocuments\n      operations:\n      - method: GET\n        name: listrecapdocuments\n        description: List RECAP documents\n        call: free-law-project.listrecapdocuments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /audio/\n      name: listoralarguments\n      operations:\n      - method: GET\n        name: listoralarguments\n        description: List oral arguments\n        call: free-law-project.listoralarguments\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /people/\n      name: listpeople\n      operations:\n      - method: GET\n        name: listpeople\n        description: List judges and people\n        call: free-law-project.listpeople\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /positions/\n      name: listpositions\n      operations:\n      - method: GET\n        name: listpositions\n        description: List judicial positions\n        call: free-law-project.listpositions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /financial-disclosures/\n      name: listfinancialdisclosures\n      operations:\n      - method: GET\n        name: listfinancialdisclosures\n        description: List financial disclosures\n        call: free-law-project.listfinancialdisclosures\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /citation-lookup/\n\
  \      name: lookupcitations\n      operations:\n      - method: POST\n        name: lookupcitations\n        description: Lookup citations in text\n        call: free-law-project.lookupcitations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerts/\n      name: listalerts\n      operations:\n      - method: GET\n        name: listalerts\n        description: List alerts\n        call: free-law-project.listalerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /alerts/\n      name: createalert\n      operations:\n      - method: POST\n        name: createalert\n        description: Create an alert\n        call: free-law-project.createalert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /tag/\n      name: listtags\n      operations:\n      - method: GET\n        name: listtags\n        description: List tags\n        call: free-law-project.listtags\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: free-law-project-mcp\n    transport: http\n    description: MCP adapter for Free Law Project / CourtListener REST API for AI agent use.\n    tools:\n    - name: search\n      description: Search across CourtListener\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.search\n      with:\n        q: tools.q\n        type: tools.type\n        order_by: tools.order_by\n        page: tools.page\n      inputParameters:\n      - name: q\n        type: string\n        description: Search query string.\n      - name: type\n        type: string\n        description: Result type (e.g., o for opinions, r for RECAP, oa for oral arguments, p for people).\n      - name: order_by\n        type: string\n        description: order_by\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: listopinions\n      description: List opinions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listopinions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getopinion\n      description: Retrieve an opinion\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.getopinion\n      with:\n        id: tools.id\n      inputParameters:\n      - name: id\n        type: integer\n        description: id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listclusters\n      description: List opinion clusters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listclusters\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdockets\n\
  \      description: List dockets\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listdockets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdocketentries\n      description: List docket entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listdocketentries\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listrecapdocuments\n      description: List RECAP documents\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listrecapdocuments\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listoralarguments\n      description: List oral arguments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listoralarguments\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpeople\n      description: List judges and people\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listpeople\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listpositions\n      description: List judicial positions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listpositions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfinancialdisclosures\n      description: List financial disclosures\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listfinancialdisclosures\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: lookupcitations\n      description: Lookup citations in text\n      hints:\n\
  \        readOnly: false\n        destructive: false\n        idempotent: false\n      call: free-law-project.lookupcitations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listalerts\n      description: List alerts\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listalerts\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createalert\n      description: Create an alert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: free-law-project.createalert\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtags\n      description: List tags\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: free-law-project.listtags\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n\
  \    FREE_LAW_PROJECT_TOKEN: FREE_LAW_PROJECT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/free-law-project/refs/heads/main/capabilities/free-law-project-capability.yaml
tags:
- Free
- Law
- Project
- API
tools:
- description: Search across CourtListener
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: search
- description: List opinions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listopinions
- description: Retrieve an opinion
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getopinion
- description: List opinion clusters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listclusters
- description: List dockets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdockets
- description: List docket entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listdocketentries
- description: List RECAP documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listrecapdocuments
- description: List oral arguments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listoralarguments
- description: List judges and people
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpeople
- description: List judicial positions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listpositions
- description: List financial disclosures
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfinancialdisclosures
- description: Lookup citations in text
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: lookupcitations
- description: List alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listalerts
- description: Create an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createalert
- description: List tags
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listtags
---
