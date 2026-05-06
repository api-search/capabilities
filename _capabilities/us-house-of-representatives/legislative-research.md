---
categories: []
consumed_apis: []
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
- list current and historical members of congress
- get details for a member of congress
- get bill
- look up a member of congress by bioguide id. returns name, state, party, chamber, district, contact info, and service history.
- list house of representatives committees for a specific congress. returns committee names, system codes, and types for the house chamber.
- list committees
- get committee details
- get bills sponsored by a member
- legislative data
- bills
- members of congress
- congressional committees
- single congressional bill
- 'list all bills introduced in a specific congress (e.g., 118 or 119). filter by bill type: hr (house bills), s (senate bills), hjres, sjres, hconres, sconres, hres, sres.'
- single member of congress
- committees
- get bill actions
- list current members
- list congressional bills with optional date filters
- list bills
- list current members of the us house of representatives and senate. returns each member's name, state, party, chamber, and district.
- congressional bills and resolutions
- get comprehensive details for a specific congressional bill including title, sponsors, cosponsors, committees, subjects, and current status. specify congress number (e.g., 119), type (hr, s), and bill number.
- track bill progress
- get details for a specific bill
- get legislative action history for a bill
- get member legislation
- get member
- 'get the complete legislative action history for a congressional bill. shows all actions taken: introduction, committee referrals, markups, floor votes, and presidential action.'
- legislation sponsored by a member
- civic tech
- get committee
- get member sponsored legislation
- list recent congressional bills from congress.gov. filter by date range to find bills introduced or updated within a specific window. returns bill number, title, sponsor, and latest action.
- congress
- list bills by congress
- get bill details
- federal government
- legislation
- get detailed information for a specific congressional committee including subcommittees, bill count, and recent reports.
- search recent bills
- list house committees
- members
- single congressional committee
- legislative actions on a bill
- list members
- list congressional committees
- find member of congress
- get all bills sponsored by a specific member of congress. useful for analyzing a legislator's legislative priorities and activity.
slug: legislative-research
source_filename: legislative-research.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: US Congressional Legislative Research\n  description: Workflow capability for legislative research and congressional monitoring. Provides access to congressional\n    bills, member information, committee activities, and legislative actions via the Congress.gov API. Supports policy analysts,\n    journalists, civic tech applications, and advocacy organizations monitoring legislation.\n  tags:\n  - Legislation\n  - Congress\n  - Bills\n  - Members\n  - Committees\n  - Federal Government\n  - Civic Tech\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    CONGRESS_API_KEY: CONGRESS_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: congress\n    baseUri: https://api.congress.gov/v3\n    description: Congress.gov API v3\n    authentication:\n      type: apikey\n      key: api_key\n      value: '{{CONGRESS_API_KEY}}'\n      placement: query\n    resources:\n    - name: bills\n      path:\
  \ /bill\n      description: Congressional bills and resolutions\n      operations:\n      - name: list-bills\n        method: GET\n        description: List congressional bills\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results (max 250)\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: format\n          in: query\n          type: string\n          required: false\n          description: Response format (json or xml)\n        - name: fromDateTime\n          in: query\n          type: string\n          required: false\n          description: Filter from date/time\n        - name: toDateTime\n          in: query\n          type: string\n          required: false\n          description: Filter to date/time\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n      - name: list-bills-by-congress\n        method: GET\n        description: List bills for a specific Congress\n        inputParameters:\n        - name: congress\n          in: path\n          type: integer\n          required: true\n          description: Congress number\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bill\n        method: GET\n        description: Get details for a specific bill\n        inputParameters:\n        - name: congress\n          in: path\n          type: integer\n          required: true\n          description: Congress number\n\
  \        - name: type\n          in: path\n          type: string\n          required: true\n          description: Bill type (hr, s, hjres, etc.)\n        - name: number\n          in: path\n          type: integer\n          required: true\n          description: Bill number\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-bill-actions\n        method: GET\n        description: Get legislative actions for a bill\n        inputParameters:\n        - name: congress\n          in: path\n          type: integer\n          required: true\n          description: Congress number\n        - name: type\n          in: path\n          type: string\n          required: true\n          description: Bill type\n        - name: number\n          in: path\n          type: integer\n          required: true\n          description: Bill number\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /member\n      description: Members of Congress\n      operations:\n      - name: list-members\n        method: GET\n        description: List members of Congress\n        inputParameters:\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Number of results\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        - name: currentMember\n          in: query\n          type: boolean\n          required: false\n          description: Filter for current members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-member\n        method: GET\n        description: Get details for a specific member\n        inputParameters:\n        - name: bioguideId\n\
  \          in: path\n          type: string\n          required: true\n          description: Member Bioguide ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-member-sponsored-legislation\n        method: GET\n        description: Get legislation sponsored by a member\n        inputParameters:\n        - name: bioguideId\n          in: path\n          type: string\n          required: true\n          description: Member Bioguide ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: committees\n      path: /committee\n      description: Congressional committees\n      operations:\n      - name: list-committees\n        method: GET\n        description: List congressional committees\n        inputParameters:\n        - name: congress\n          in: path\n          type: integer\n          required: true\n\
  \          description: Congress number\n        - name: chamber\n          in: path\n          type: string\n          required: true\n          description: Chamber (house, senate, joint)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-committee\n        method: GET\n        description: Get details for a specific committee\n        inputParameters:\n        - name: chamber\n          in: path\n          type: string\n          required: true\n          description: Chamber\n        - name: systemCode\n          in: path\n          type: string\n          required: true\n          description: Committee system code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: legislative-research-api\n    description: Unified REST API for US Congressional legislative\
  \ research and monitoring.\n    resources:\n    - path: /v1/bills\n      name: bills\n      description: Congressional bills and resolutions\n      operations:\n      - method: GET\n        name: list-bills\n        description: List congressional bills with optional date filters\n        call: congress.list-bills\n        with:\n          limit: rest.limit\n          offset: rest.offset\n          fromDateTime: rest.from_date\n          toDateTime: rest.to_date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/bills/{congress}/{type}/{number}\n      name: bill\n      description: Single congressional bill\n      operations:\n      - method: GET\n        name: get-bill\n        description: Get details for a specific bill\n        call: congress.get-bill\n        with:\n          congress: rest.congress\n          type: rest.type\n          number: rest.number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /v1/bills/{congress}/{type}/{number}/actions\n      name: bill-actions\n      description: Legislative actions on a bill\n      operations:\n      - method: GET\n        name: get-bill-actions\n        description: Get legislative action history for a bill\n        call: congress.get-bill-actions\n        with:\n          congress: rest.congress\n          type: rest.type\n          number: rest.number\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members\n      name: members\n      description: Members of Congress\n      operations:\n      - method: GET\n        name: list-members\n        description: List current and historical members of Congress\n        call: congress.list-members\n        with:\n          currentMember: rest.current_member\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{bioguideId}\n      name: member\n      description: Single member of\
  \ Congress\n      operations:\n      - method: GET\n        name: get-member\n        description: Get details for a member of Congress\n        call: congress.get-member\n        with:\n          bioguideId: rest.bioguide_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{bioguideId}/sponsored-legislation\n      name: member-sponsored\n      description: Legislation sponsored by a member\n      operations:\n      - method: GET\n        name: get-member-sponsored-legislation\n        description: Get bills sponsored by a member\n        call: congress.get-member-sponsored-legislation\n        with:\n          bioguideId: rest.bioguide_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/committees\n      name: committees\n      description: Congressional committees\n      operations:\n      - method: GET\n        name: list-committees\n        description: List congressional committees\n      \
  \  call: congress.list-committees\n        with:\n          congress: rest.congress\n          chamber: rest.chamber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/committees/{chamber}/{systemCode}\n      name: committee\n      description: Single congressional committee\n      operations:\n      - method: GET\n        name: get-committee\n        description: Get committee details\n        call: congress.get-committee\n        with:\n          chamber: rest.chamber\n          systemCode: rest.system_code\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: legislative-research-mcp\n    transport: http\n    description: MCP server for AI-assisted US Congressional legislative research, bill tracking, and member activity monitoring.\n    tools:\n    - name: search-recent-bills\n      description: List recent congressional bills from Congress.gov. Filter by date range to find bills\
  \ introduced or updated\n        within a specific window. Returns bill number, title, sponsor, and latest action.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: congress.list-bills\n      with:\n        limit: tools.limit\n        offset: tools.offset\n        fromDateTime: tools.from_date\n        toDateTime: tools.to_date\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-bills-by-congress\n      description: 'List all bills introduced in a specific Congress (e.g., 118 or 119). Filter by bill type: hr (House bills),\n        s (Senate bills), hjres, sjres, hconres, sconres, hres, sres.'\n      hints:\n        readOnly: true\n        openWorld: true\n      call: congress.list-bills-by-congress\n      with:\n        congress: tools.congress\n        limit: tools.limit\n        offset: tools.offset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-bill-details\n      description: Get comprehensive\
  \ details for a specific congressional bill including title, sponsors, cosponsors, committees,\n        subjects, and current status. Specify congress number (e.g., 119), type (hr, s), and bill number.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: congress.get-bill\n      with:\n        congress: tools.congress\n        type: tools.bill_type\n        number: tools.bill_number\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: track-bill-progress\n      description: 'Get the complete legislative action history for a congressional bill. Shows all actions taken: introduction,\n        committee referrals, markups, floor votes, and presidential action.'\n      hints:\n        readOnly: true\n        openWorld: false\n      call: congress.get-bill-actions\n      with:\n        congress: tools.congress\n        type: tools.bill_type\n        number: tools.bill_number\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: find-member-of-congress\n      description: Look up a member of Congress by Bioguide ID. Returns name, state, party, chamber, district, contact info,\n        and service history.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: congress.get-member\n      with:\n        bioguideId: tools.bioguide_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-current-members\n      description: List current members of the US House of Representatives and Senate. Returns each member's name, state,\n        party, chamber, and district.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: congress.list-members\n      with:\n        currentMember: tools.current_member\n        limit: tools.limit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-member-legislation\n      description: Get all bills sponsored by a specific member of Congress. Useful for analyzing a\
  \ legislator's legislative\n        priorities and activity.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: congress.get-member-sponsored-legislation\n      with:\n        bioguideId: tools.bioguide_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-house-committees\n      description: List House of Representatives committees for a specific Congress. Returns committee names, system codes,\n        and types for the House chamber.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: congress.list-committees\n      with:\n        congress: tools.congress\n        chamber: house\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-committee-details\n      description: Get detailed information for a specific congressional committee including subcommittees, bill count, and\n        recent reports.\n      hints:\n        readOnly: true\n        openWorld: false\n      call:\
  \ congress.get-committee\n      with:\n        chamber: tools.chamber\n        systemCode: tools.system_code\n      outputParameters:\n      - type: object\n        mapping: $.\n"
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
