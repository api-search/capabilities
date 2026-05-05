---
api_specs:
- filename: congress-gov-api-openapi.yml
  format: yaml
  label: congress
  slug: congress
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/us-house-of-representatives/refs/heads/main/openapi/congress-gov-api-openapi.yml
categories: []
consumed_apis:
- congress
description: Workflow capability for legislative research and congressional monitoring. Provides access to congressional bills, member information, committee activities, and legislative actions via the Congress.gov API. Supports policy analysts, journalists, civic tech applications, and advocacy organizations monitoring legislation.
layout: capability
name: US Congressional Legislative Research
operations:
- description: List congressional bills with optional date filters
  method: GET
  name: list-bills
  path: /v1/bills
- description: Get details for a specific bill
  method: GET
  name: get-bill
  path: /v1/bills/{congress}/{type}/{number}
- description: Get legislative action history for a bill
  method: GET
  name: get-bill-actions
  path: /v1/bills/{congress}/{type}/{number}/actions
- description: List current and historical members of Congress
  method: GET
  name: list-members
  path: /v1/members
- description: Get details for a member of Congress
  method: GET
  name: get-member
  path: /v1/members/{bioguideId}
- description: Get bills sponsored by a member
  method: GET
  name: get-member-sponsored-legislation
  path: /v1/members/{bioguideId}/sponsored-legislation
- description: List congressional committees
  method: GET
  name: list-committees
  path: /v1/committees
- description: Get committee details
  method: GET
  name: get-committee
  path: /v1/committees/{chamber}/{systemCode}
personas: []
provider_name: US House of Representatives
provider_slug: us-house-of-representatives
search_terms:
- congress
- get all bills sponsored by a specific member of congress. useful for analyzing a legislator's legislative priorities and activity.
- list house committees
- committees
- federal government
- legislation sponsored by a member
- get committee details
- list bills
- members of congress
- get committee
- get member legislation
- search recent bills
- civic tech
- look up a member of congress by bioguide id. returns name, state, party, chamber, district, contact info, and service history.
- list recent congressional bills from congress.gov. filter by date range to find bills introduced or updated within a specific window. returns bill number, title, sponsor, and latest action.
- list congressional bills with optional date filters
- single congressional bill
- list members
- legislative data
- congressional committees
- list bills by congress
- list current members
- get details for a member of congress
- get bill actions
- track bill progress
- single congressional committee
- list current and historical members of congress
- get bill details
- find member of congress
- get bills sponsored by a member
- get comprehensive details for a specific congressional bill including title, sponsors, cosponsors, committees, subjects, and current status. specify congress number (e.g., 119), type (hr, s), and bill number.
- congressional bills and resolutions
- list current members of the us house of representatives and senate. returns each member's name, state, party, chamber, and district.
- legislative actions on a bill
- bills
- legislation
- get legislative action history for a bill
- get details for a specific bill
- get member sponsored legislation
- list committees
- members
- get detailed information for a specific congressional committee including subcommittees, bill count, and recent reports.
- list congressional committees
- list house of representatives committees for a specific congress. returns committee names, system codes, and types for the house chamber.
- get bill
- 'list all bills introduced in a specific congress (e.g., 118 or 119). filter by bill type: hr (house bills), s (senate bills), hjres, sjres, hconres, sconres, hres, sres.'
- 'get the complete legislative action history for a congressional bill. shows all actions taken: introduction, committee referrals, markups, floor votes, and presidential action.'
- single member of congress
- get member
slug: legislative-research
source_filename: legislative-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"US Congressional Legislative Research\"\n  description: >-\n    Workflow capability for legislative research and congressional monitoring.\n    Provides access to congressional bills, member information, committee\n    activities, and legislative actions via the Congress.gov API. Supports\n    policy analysts, journalists, civic tech applications, and advocacy\n    organizations monitoring legislation.\n  tags:\n    - Legislation\n    - Congress\n    - Bills\n    - Members\n    - Committees\n    - Federal Government\n    - Civic Tech\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      CONGRESS_API_KEY: CONGRESS_API_KEY\n\ncapability:\n  consumes:\n    - import: congress\n      location: ./shared/congress-gov-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: legislative-research-api\n      description: \"Unified REST API for US Congressional legislative\
  \ research and monitoring.\"\n      resources:\n        - path: /v1/bills\n          name: bills\n          description: \"Congressional bills and resolutions\"\n          operations:\n            - method: GET\n              name: list-bills\n              description: \"List congressional bills with optional date filters\"\n              call: \"congress.list-bills\"\n              with:\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n                fromDateTime: \"rest.from_date\"\n                toDateTime: \"rest.to_date\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bills/{congress}/{type}/{number}\n          name: bill\n          description: \"Single congressional bill\"\n          operations:\n            - method: GET\n              name: get-bill\n              description: \"Get details for a specific bill\"\n              call: \"congress.get-bill\"\n            \
  \  with:\n                congress: \"rest.congress\"\n                type: \"rest.type\"\n                number: \"rest.number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/bills/{congress}/{type}/{number}/actions\n          name: bill-actions\n          description: \"Legislative actions on a bill\"\n          operations:\n            - method: GET\n              name: get-bill-actions\n              description: \"Get legislative action history for a bill\"\n              call: \"congress.get-bill-actions\"\n              with:\n                congress: \"rest.congress\"\n                type: \"rest.type\"\n                number: \"rest.number\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members\n          name: members\n          description: \"Members of Congress\"\n          operations:\n            - method: GET\n       \
  \       name: list-members\n              description: \"List current and historical members of Congress\"\n              call: \"congress.list-members\"\n              with:\n                currentMember: \"rest.current_member\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members/{bioguideId}\n          name: member\n          description: \"Single member of Congress\"\n          operations:\n            - method: GET\n              name: get-member\n              description: \"Get details for a member of Congress\"\n              call: \"congress.get-member\"\n              with:\n                bioguideId: \"rest.bioguide_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/members/{bioguideId}/sponsored-legislation\n          name: member-sponsored\n          description: \"Legislation sponsored\
  \ by a member\"\n          operations:\n            - method: GET\n              name: get-member-sponsored-legislation\n              description: \"Get bills sponsored by a member\"\n              call: \"congress.get-member-sponsored-legislation\"\n              with:\n                bioguideId: \"rest.bioguide_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/committees\n          name: committees\n          description: \"Congressional committees\"\n          operations:\n            - method: GET\n              name: list-committees\n              description: \"List congressional committees\"\n              call: \"congress.list-committees\"\n              with:\n                congress: \"rest.congress\"\n                chamber: \"rest.chamber\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/committees/{chamber}/{systemCode}\n\
  \          name: committee\n          description: \"Single congressional committee\"\n          operations:\n            - method: GET\n              name: get-committee\n              description: \"Get committee details\"\n              call: \"congress.get-committee\"\n              with:\n                chamber: \"rest.chamber\"\n                systemCode: \"rest.system_code\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: legislative-research-mcp\n      transport: http\n      description: \"MCP server for AI-assisted US Congressional legislative research, bill tracking, and member activity monitoring.\"\n      tools:\n        - name: search-recent-bills\n          description: >-\n            List recent congressional bills from Congress.gov. Filter by date range\n            to find bills introduced or updated within a specific window.\n            Returns bill number, title,\
  \ sponsor, and latest action.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"congress.list-bills\"\n          with:\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n            fromDateTime: \"tools.from_date\"\n            toDateTime: \"tools.to_date\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-bills-by-congress\n          description: >-\n            List all bills introduced in a specific Congress (e.g., 118 or 119).\n            Filter by bill type: hr (House bills), s (Senate bills), hjres, sjres,\n            hconres, sconres, hres, sres.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"congress.list-bills-by-congress\"\n          with:\n            congress: \"tools.congress\"\n            limit: \"tools.limit\"\n            offset: \"tools.offset\"\n          outputParameters:\n            - type:\
  \ object\n              mapping: \"$.\"\n        - name: get-bill-details\n          description: >-\n            Get comprehensive details for a specific congressional bill including\n            title, sponsors, cosponsors, committees, subjects, and current status.\n            Specify congress number (e.g., 119), type (hr, s), and bill number.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"congress.get-bill\"\n          with:\n            congress: \"tools.congress\"\n            type: \"tools.bill_type\"\n            number: \"tools.bill_number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: track-bill-progress\n          description: >-\n            Get the complete legislative action history for a congressional bill.\n            Shows all actions taken: introduction, committee referrals, markups,\n            floor votes, and presidential action.\n          hints:\n       \
  \     readOnly: true\n            openWorld: false\n          call: \"congress.get-bill-actions\"\n          with:\n            congress: \"tools.congress\"\n            type: \"tools.bill_type\"\n            number: \"tools.bill_number\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: find-member-of-congress\n          description: >-\n            Look up a member of Congress by Bioguide ID. Returns name, state,\n            party, chamber, district, contact info, and service history.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"congress.get-member\"\n          with:\n            bioguideId: \"tools.bioguide_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-current-members\n          description: >-\n            List current members of the US House of Representatives and Senate.\n            Returns each member's name,\
  \ state, party, chamber, and district.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"congress.list-members\"\n          with:\n            currentMember: \"tools.current_member\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-member-legislation\n          description: >-\n            Get all bills sponsored by a specific member of Congress.\n            Useful for analyzing a legislator's legislative priorities and activity.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"congress.get-member-sponsored-legislation\"\n          with:\n            bioguideId: \"tools.bioguide_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-house-committees\n          description: >-\n            List House of Representatives committees for a specific\
  \ Congress.\n            Returns committee names, system codes, and types for the House chamber.\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"congress.list-committees\"\n          with:\n            congress: \"tools.congress\"\n            chamber: \"house\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: get-committee-details\n          description: >-\n            Get detailed information for a specific congressional committee\n            including subcommittees, bill count, and recent reports.\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"congress.get-committee\"\n          with:\n            chamber: \"tools.chamber\"\n            systemCode: \"tools.system_code\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/us-house-of-representatives/refs/heads/main/capabilities/legislative-research.yaml
tags:
- Legislation
- Congress
- Bills
- Members
- Committees
- Federal Government
- Civic Tech
tools:
- description: List recent congressional bills from Congress.gov. Filter by date range to find bills introduced or updated within a specific window. Returns bill number, title, sponsor, and latest action.
  hints:
    openWorld: true
    readOnly: true
  name: search-recent-bills
- description: 'List all bills introduced in a specific Congress (e.g., 118 or 119). Filter by bill type: hr (House bills), s (Senate bills), hjres, sjres, hconres, sconres, hres, sres.'
  hints:
    openWorld: true
    readOnly: true
  name: list-bills-by-congress
- description: Get comprehensive details for a specific congressional bill including title, sponsors, cosponsors, committees, subjects, and current status. Specify congress number (e.g., 119), type (hr, s), and bill number.
  hints:
    openWorld: false
    readOnly: true
  name: get-bill-details
- description: 'Get the complete legislative action history for a congressional bill. Shows all actions taken: introduction, committee referrals, markups, floor votes, and presidential action.'
  hints:
    openWorld: false
    readOnly: true
  name: track-bill-progress
- description: Look up a member of Congress by Bioguide ID. Returns name, state, party, chamber, district, contact info, and service history.
  hints:
    openWorld: false
    readOnly: true
  name: find-member-of-congress
- description: List current members of the US House of Representatives and Senate. Returns each member's name, state, party, chamber, and district.
  hints:
    openWorld: true
    readOnly: true
  name: list-current-members
- description: Get all bills sponsored by a specific member of Congress. Useful for analyzing a legislator's legislative priorities and activity.
  hints:
    openWorld: false
    readOnly: true
  name: get-member-legislation
- description: List House of Representatives committees for a specific Congress. Returns committee names, system codes, and types for the House chamber.
  hints:
    openWorld: true
    readOnly: true
  name: list-house-committees
- description: Get detailed information for a specific congressional committee including subcommittees, bill count, and recent reports.
  hints:
    openWorld: false
    readOnly: true
  name: get-committee-details
---
