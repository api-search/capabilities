---
categories: []
consumed_apis: []
description: The OpenFEC API is a RESTful web service from the Federal Election Commission supporting full-text and field-specific searches on FEC data including candidates, committees, filings, financial summaries, and transaction schedules. Data are updated nightly.
layout: capability
name: OpenFEC API
operations:
- description: List candidates
  method: GET
  name: listcandidates
  path: /candidates/
- description: Search candidates with principal committees
  method: GET
  name: searchcandidates
  path: /candidates/search/
- description: Retrieve a single candidate
  method: GET
  name: getcandidate
  path: /candidate/{candidate_id}
- description: Candidate financial totals
  method: GET
  name: getcandidatetotals
  path: /candidate/{candidate_id}/totals/
- description: Committees associated with a candidate
  method: GET
  name: getcandidatecommittees
  path: /candidate/{candidate_id}/committees/
- description: List committees
  method: GET
  name: listcommittees
  path: /committees/
- description: Retrieve a single committee
  method: GET
  name: getcommittee
  path: /committee/{committee_id}
- description: Committee financial totals
  method: GET
  name: getcommitteetotals
  path: /committee/{committee_id}/totals/
- description: List filings
  method: GET
  name: listfilings
  path: /filings/
- description: Itemized individual contributions (Schedule A)
  method: GET
  name: listschedulea
  path: /schedules/schedule_a/
- description: Itemized disbursements (Schedule B)
  method: GET
  name: listscheduleb
  path: /schedules/schedule_b/
- description: Independent expenditures (Schedule E)
  method: GET
  name: listschedulee
  path: /schedules/schedule_e/
- description: Election summaries by office, cycle, and district
  method: GET
  name: listelections
  path: /elections/
- description: Candidate name typeahead
  method: GET
  name: candidatenames
  path: /names/candidates/
- description: Committee name typeahead
  method: GET
  name: committeenames
  path: /names/committees/
personas: []
provider_name: OpenFEC
provider_slug: open-fec
search_terms:
- list candidates
- federal
- list filings
- searchcandidates
- api
- getcandidatetotals
- listschedulea
- retrieve a single candidate
- listfilings
- search candidates with principal committees
- candidate financial totals
- retrieve a single committee
- election summaries by office, cycle, and district
- itemized disbursements (schedule b)
- candidatenames
- candidate name typeahead
- committeenames
- campaign finance
- independent expenditures (schedule e)
- committee financial totals
- fec
- listscheduleb
- list committees
- listelections
- getcandidatecommittees
- listcandidates
- open
- government
- listschedulee
- getcommittee
- getcandidate
- elections
- committee name typeahead
- committees associated with a candidate
- getcommitteetotals
- itemized individual contributions (schedule a)
- listcommittees
slug: open-fec-capability
source_filename: open-fec-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OpenFEC API\n  description: The OpenFEC API is a RESTful web service from the Federal Election Commission supporting full-text and field-specific\n    searches on FEC data including candidates, committees, filings, financial summaries, and transaction schedules. Data are\n    updated nightly.\n  tags:\n  - Open\n  - Fec\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: open-fec\n    baseUri: https://api.open.fec.gov/v1\n    description: OpenFEC API HTTP API.\n    authentication:\n      type: apikey\n      in: query\n      name: api_key\n      value: '{{OPEN_FEC_TOKEN}}'\n    resources:\n    - name: candidates\n      path: /candidates/\n      operations:\n      - name: listcandidates\n        method: GET\n        description: List candidates\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Full-text search.\n\
  \        - name: candidate_id\n          in: query\n          type: array\n        - name: cycle\n          in: query\n          type: array\n        - name: office\n          in: query\n          type: array\n        - name: state\n          in: query\n          type: string\n        - name: party\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidates-search\n      path: /candidates/search/\n      operations:\n      - name: searchcandidates\n        method: GET\n        description: Search candidates with principal committees\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-candidate-id\n      path: /candidate/{candidate_id}\n      operations:\n      - name:\
  \ getcandidate\n        method: GET\n        description: Retrieve a single candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-candidate-id-totals\n      path: /candidate/{candidate_id}/totals/\n      operations:\n      - name: getcandidatetotals\n        method: GET\n        description: Candidate financial totals\n        inputParameters:\n        - name: cycle\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: candidate-candidate-id-committees\n      path: /candidate/{candidate_id}/committees/\n      operations:\n      - name: getcandidatecommittees\n        method: GET\n        description: Committees associated with a candidate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n         \
  \ value: $.\n    - name: committees\n      path: /committees/\n      operations:\n      - name: listcommittees\n        method: GET\n        description: List committees\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        - name: committee_id\n          in: query\n          type: array\n        - name: committee_type\n          in: query\n          type: string\n        - name: cycle\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: committee-committee-id\n      path: /committee/{committee_id}\n      operations:\n      - name: getcommittee\n        method: GET\n        description: Retrieve a single committee\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: committee-committee-id-totals\n      path: /committee/{committee_id}/totals/\n\
  \      operations:\n      - name: getcommitteetotals\n        method: GET\n        description: Committee financial totals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: filings\n      path: /filings/\n      operations:\n      - name: listfilings\n        method: GET\n        description: List filings\n        inputParameters:\n        - name: candidate_id\n          in: query\n          type: array\n        - name: committee_id\n          in: query\n          type: array\n        - name: form_type\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-schedule-a\n      path: /schedules/schedule_a/\n      operations:\n      - name: listschedulea\n        method: GET\n        description: Itemized individual contributions (Schedule A)\n        inputParameters:\n\
  \        - name: contributor_name\n          in: query\n          type: string\n        - name: committee_id\n          in: query\n          type: array\n        - name: two_year_transaction_period\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-schedule-b\n      path: /schedules/schedule_b/\n      operations:\n      - name: listscheduleb\n        method: GET\n        description: Itemized disbursements (Schedule B)\n        inputParameters:\n        - name: committee_id\n          in: query\n          type: array\n        - name: recipient_name\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: schedules-schedule-e\n      path: /schedules/schedule_e/\n      operations:\n      - name: listschedulee\n        method:\
  \ GET\n        description: Independent expenditures (Schedule E)\n        inputParameters:\n        - name: candidate_id\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elections\n      path: /elections/\n      operations:\n      - name: listelections\n        method: GET\n        description: Election summaries by office, cycle, and district\n        inputParameters:\n        - name: cycle\n          in: query\n          type: integer\n        - name: office\n          in: query\n          type: string\n        - name: state\n          in: query\n          type: string\n        - name: district\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: names-candidates\n      path: /names/candidates/\n      operations:\n     \
  \ - name: candidatenames\n        method: GET\n        description: Candidate name typeahead\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: names-committees\n      path: /names/committees/\n      operations:\n      - name: committeenames\n        method: GET\n        description: Committee name typeahead\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: open-fec-rest\n    description: REST adapter for OpenFEC API.\n    resources:\n    - path: /candidates/\n      name: listcandidates\n      operations:\n      - method: GET\n        name: listcandidates\n        description: List candidates\n\
  \        call: open-fec.listcandidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidates/search/\n      name: searchcandidates\n      operations:\n      - method: GET\n        name: searchcandidates\n        description: Search candidates with principal committees\n        call: open-fec.searchcandidates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidate/{candidate_id}\n      name: getcandidate\n      operations:\n      - method: GET\n        name: getcandidate\n        description: Retrieve a single candidate\n        call: open-fec.getcandidate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /candidate/{candidate_id}/totals/\n      name: getcandidatetotals\n      operations:\n      - method: GET\n        name: getcandidatetotals\n        description: Candidate financial totals\n        call: open-fec.getcandidatetotals\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /candidate/{candidate_id}/committees/\n      name: getcandidatecommittees\n      operations:\n      - method: GET\n        name: getcandidatecommittees\n        description: Committees associated with a candidate\n        call: open-fec.getcandidatecommittees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /committees/\n      name: listcommittees\n      operations:\n      - method: GET\n        name: listcommittees\n        description: List committees\n        call: open-fec.listcommittees\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /committee/{committee_id}\n      name: getcommittee\n      operations:\n      - method: GET\n        name: getcommittee\n        description: Retrieve a single committee\n        call: open-fec.getcommittee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /committee/{committee_id}/totals/\n\
  \      name: getcommitteetotals\n      operations:\n      - method: GET\n        name: getcommitteetotals\n        description: Committee financial totals\n        call: open-fec.getcommitteetotals\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /filings/\n      name: listfilings\n      operations:\n      - method: GET\n        name: listfilings\n        description: List filings\n        call: open-fec.listfilings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/schedule_a/\n      name: listschedulea\n      operations:\n      - method: GET\n        name: listschedulea\n        description: Itemized individual contributions (Schedule A)\n        call: open-fec.listschedulea\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/schedule_b/\n      name: listscheduleb\n      operations:\n      - method: GET\n        name: listscheduleb\n        description: Itemized\
  \ disbursements (Schedule B)\n        call: open-fec.listscheduleb\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /schedules/schedule_e/\n      name: listschedulee\n      operations:\n      - method: GET\n        name: listschedulee\n        description: Independent expenditures (Schedule E)\n        call: open-fec.listschedulee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /elections/\n      name: listelections\n      operations:\n      - method: GET\n        name: listelections\n        description: Election summaries by office, cycle, and district\n        call: open-fec.listelections\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /names/candidates/\n      name: candidatenames\n      operations:\n      - method: GET\n        name: candidatenames\n        description: Candidate name typeahead\n        call: open-fec.candidatenames\n        outputParameters:\n     \
  \   - type: object\n          mapping: $.\n    - path: /names/committees/\n      name: committeenames\n      operations:\n      - method: GET\n        name: committeenames\n        description: Committee name typeahead\n        call: open-fec.committeenames\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: open-fec-mcp\n    transport: http\n    description: MCP adapter for OpenFEC API for AI agent use.\n    tools:\n    - name: listcandidates\n      description: List candidates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listcandidates\n      with:\n        q: tools.q\n        candidate_id: tools.candidate_id\n        cycle: tools.cycle\n        office: tools.office\n        state: tools.state\n        party: tools.party\n      inputParameters:\n      - name: q\n        type: string\n        description: Full-text search.\n      - name: candidate_id\n\
  \        type: array\n        description: candidate_id\n      - name: cycle\n        type: array\n        description: cycle\n      - name: office\n        type: array\n        description: office\n      - name: state\n        type: string\n        description: state\n      - name: party\n        type: string\n        description: party\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: searchcandidates\n      description: Search candidates with principal committees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.searchcandidates\n      with:\n        q: tools.q\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcandidate\n      description: Retrieve a single candidate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ open-fec.getcandidate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcandidatetotals\n      description: Candidate financial totals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.getcandidatetotals\n      with:\n        cycle: tools.cycle\n      inputParameters:\n      - name: cycle\n        type: array\n        description: cycle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcandidatecommittees\n      description: Committees associated with a candidate\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.getcandidatecommittees\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcommittees\n      description: List committees\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listcommittees\n\
  \      with:\n        q: tools.q\n        committee_id: tools.committee_id\n        committee_type: tools.committee_type\n        cycle: tools.cycle\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n      - name: committee_id\n        type: array\n        description: committee_id\n      - name: committee_type\n        type: string\n        description: committee_type\n      - name: cycle\n        type: array\n        description: cycle\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommittee\n      description: Retrieve a single committee\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.getcommittee\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcommitteetotals\n      description: Committee financial totals\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ open-fec.getcommitteetotals\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listfilings\n      description: List filings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listfilings\n      with:\n        candidate_id: tools.candidate_id\n        committee_id: tools.committee_id\n        form_type: tools.form_type\n      inputParameters:\n      - name: candidate_id\n        type: array\n        description: candidate_id\n      - name: committee_id\n        type: array\n        description: committee_id\n      - name: form_type\n        type: array\n        description: form_type\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedulea\n      description: Itemized individual contributions (Schedule A)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listschedulea\n      with:\n        contributor_name:\
  \ tools.contributor_name\n        committee_id: tools.committee_id\n        two_year_transaction_period: tools.two_year_transaction_period\n      inputParameters:\n      - name: contributor_name\n        type: string\n        description: contributor_name\n      - name: committee_id\n        type: array\n        description: committee_id\n      - name: two_year_transaction_period\n        type: integer\n        description: two_year_transaction_period\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listscheduleb\n      description: Itemized disbursements (Schedule B)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listscheduleb\n      with:\n        committee_id: tools.committee_id\n        recipient_name: tools.recipient_name\n      inputParameters:\n      - name: committee_id\n        type: array\n        description: committee_id\n      - name: recipient_name\n        type: string\n  \
  \      description: recipient_name\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschedulee\n      description: Independent expenditures (Schedule E)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listschedulee\n      with:\n        candidate_id: tools.candidate_id\n      inputParameters:\n      - name: candidate_id\n        type: array\n        description: candidate_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listelections\n      description: Election summaries by office, cycle, and district\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.listelections\n      with:\n        cycle: tools.cycle\n        office: tools.office\n        state: tools.state\n        district: tools.district\n      inputParameters:\n      - name: cycle\n        type: integer\n        description: cycle\n\
  \      - name: office\n        type: string\n        description: office\n      - name: state\n        type: string\n        description: state\n      - name: district\n        type: string\n        description: district\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: candidatenames\n      description: Candidate name typeahead\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.candidatenames\n      with:\n        q: tools.q\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: committeenames\n      description: Committee name typeahead\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: open-fec.committeenames\n      with:\n        q: tools.q\n      inputParameters:\n      - name: q\n        type: string\n        description: q\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    OPEN_FEC_TOKEN: OPEN_FEC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/open-fec/refs/heads/main/capabilities/open-fec-capability.yaml
tags:
- Open
- Fec
- API
tools:
- description: List candidates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcandidates
- description: Search candidates with principal committees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcandidates
- description: Retrieve a single candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidate
- description: Candidate financial totals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidatetotals
- description: Committees associated with a candidate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcandidatecommittees
- description: List committees
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcommittees
- description: Retrieve a single committee
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommittee
- description: Committee financial totals
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcommitteetotals
- description: List filings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listfilings
- description: Itemized individual contributions (Schedule A)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedulea
- description: Itemized disbursements (Schedule B)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listscheduleb
- description: Independent expenditures (Schedule E)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listschedulee
- description: Election summaries by office, cycle, and district
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listelections
- description: Candidate name typeahead
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: candidatenames
- description: Committee name typeahead
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: committeenames
---
