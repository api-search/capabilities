---
categories: []
consumed_apis: []
description: Unified workflow capability for finding, evaluating, and engaging freelancers on Upwork. Combines job search, freelancer profile access, contract management, and messaging into a single talent acquisition workflow. Designed for hiring managers, agencies, and developer platforms integrating Upwork talent data.
layout: capability
name: Upwork Talent Marketplace
operations:
- description: Search for job postings
  method: GET
  name: search-jobs
  path: /v1/jobs
- description: Get job details
  method: GET
  name: get-job
  path: /v1/jobs/{job_id}
- description: Search for freelancers
  method: GET
  name: search-freelancers
  path: /v1/freelancers
- description: Get freelancer profile
  method: GET
  name: get-freelancer
  path: /v1/freelancers/{user_id}
- description: List contracts
  method: GET
  name: list-contracts
  path: /v1/contracts
- description: Get contract details
  method: GET
  name: get-contract
  path: /v1/contracts/{contract_id}
- description: List messages in a room
  method: GET
  name: list-messages
  path: /v1/rooms/{room_id}/messages
- description: Send a message
  method: POST
  name: send-message
  path: /v1/rooms/{room_id}/messages
personas: []
provider_name: Upwork
provider_slug: upwork
search_terms:
- list messages in a room
- marketplace
- get job
- upwork
- contract communication
- list messages
- search for job postings
- search freelancers
- Developer
- manager overseeing multiple freelancer contracts
- freelancer search
- get contract
- search jobs
- freelancing
- get contract details
- execute a custom graphql query against the upwork api
- contracts
- search upwork job postings by keywords, skills, and budget
- get detailed information for a specific upwork job posting
- search for freelancers on upwork by skills, rate, and availability
- contract management
- list contracts
- execute graphql
- Hiring Manager
- business professional finding and hiring freelancers
- individual job operations
- get job details
- individual contract
- talent acquisition and freelancer management workflow
- send message
- talent
- hiring
- freelancer profile
- contract messaging
- get detailed information for a specific upwork contract
- Agency Manager
- send a message in a contract messaging room
- job search and management
- developer integrating upwork data into custom applications
- send a message
- talent acquisition
- list messages in a contract messaging room
- search for freelancers
- managing active and completed contracts
- jobs
- get freelancer profile
- finding and evaluating freelancers and jobs
- list all upwork contracts with optional status filtering
- retrieve the full profile for a specific upwork freelancer
- get freelancer
slug: talent-marketplace
source_filename: talent-marketplace.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Upwork Talent Marketplace\n  description: Unified workflow capability for finding, evaluating, and engaging freelancers on Upwork. Combines job search,\n    freelancer profile access, contract management, and messaging into a single talent acquisition workflow. Designed for\n    hiring managers, agencies, and developer platforms integrating Upwork talent data.\n  tags:\n  - Upwork\n  - Freelancing\n  - Talent Acquisition\n  - Hiring\n  - Contracts\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    UPWORK_ACCESS_TOKEN: UPWORK_ACCESS_TOKEN\n    UPWORK_CLIENT_ID: UPWORK_CLIENT_ID\n    UPWORK_CLIENT_SECRET: UPWORK_CLIENT_SECRET\ncapability:\n  consumes:\n  - type: http\n    namespace: upwork-graphql\n    baseUri: https://api.upwork.com\n    description: Upwork GraphQL API for marketplace data access\n    authentication:\n      type: bearer\n      token: '{{UPWORK_ACCESS_TOKEN}}'\n    resources:\n   \
  \ - name: graphql\n      path: /graphql\n      description: GraphQL endpoint for all queries and mutations\n      operations:\n      - name: execute-graphql\n        method: POST\n        description: Execute any GraphQL query, mutation, or subscription\n        inputParameters:\n        - name: query\n          in: body\n          type: string\n          required: true\n          description: GraphQL query string\n        - name: variables\n          in: body\n          type: object\n          required: false\n          description: Query variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n            variables: '{{tools.variables}}'\n    - name: jobs\n      path: /api/v3/jobs/search\n      description: Job search and retrieval\n      operations:\n      - name: search-jobs\n        method: GET\n        description:\
  \ Search for job postings on Upwork\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query string\n        - name: paging\n          in: query\n          type: string\n          required: false\n          description: Pagination as offset;count\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-job\n        method: GET\n        description: Get job details by ID\n        inputParameters:\n        - name: job_id\n          in: path\n          type: string\n          required: true\n          description: Job identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: contracts\n      path: /api/v3/hr/v2/contracts\n      description: Contract management\n      operations:\n      - name: list-contracts\n    \
  \    method: GET\n        description: List all contracts for the authenticated user\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by status\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-contract\n        method: GET\n        description: Get contract details\n        inputParameters:\n        - name: contract_id\n          in: path\n          type: string\n          required: true\n          description: Contract identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: profiles\n      path: /api/v3/profiles/v2/search/providers\n      description: Freelancer profile search\n      operations:\n      - name: search-freelancers\n        method: GET\n        description: Search for freelancers\
  \ by skills and criteria\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          required: false\n          description: Search query\n        - name: paging\n          in: query\n          type: string\n          required: false\n          description: Pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-freelancer-profile\n        method: GET\n        description: Get a freelancer's profile\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: User identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: messages\n      path: /api/v3/messages/v3/rooms\n      description: Contract messaging\n      operations:\n      - name: list-messages\n        method: GET\n\
  \        description: List messages in a contract room\n        inputParameters:\n        - name: room_id\n          in: path\n          type: string\n          required: true\n          description: Room identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: send-message\n        method: POST\n        description: Send a message to a contract room\n        inputParameters:\n        - name: room_id\n          in: path\n          type: string\n          required: true\n          description: Room identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            message: '{{tools.message}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: upwork-talent-api\n    description: Unified REST API for Upwork talent marketplace operations.\n    resources:\n\
  \    - path: /v1/jobs\n      name: jobs\n      description: Job search and management\n      operations:\n      - method: GET\n        name: search-jobs\n        description: Search for job postings\n        call: upwork-graphql.search-jobs\n        with:\n          q: rest.q\n          paging: rest.paging\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs/{job_id}\n      name: job\n      description: Individual job operations\n      operations:\n      - method: GET\n        name: get-job\n        description: Get job details\n        call: upwork-graphql.get-job\n        with:\n          job_id: rest.job_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/freelancers\n      name: freelancers\n      description: Freelancer search\n      operations:\n      - method: GET\n        name: search-freelancers\n        description: Search for freelancers\n        call: upwork-graphql.search-freelancers\n   \
  \     with:\n          q: rest.q\n          paging: rest.paging\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/freelancers/{user_id}\n      name: freelancer\n      description: Freelancer profile\n      operations:\n      - method: GET\n        name: get-freelancer\n        description: Get freelancer profile\n        call: upwork-graphql.get-freelancer-profile\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts\n      name: contracts\n      description: Contract management\n      operations:\n      - method: GET\n        name: list-contracts\n        description: List contracts\n        call: upwork-graphql.list-contracts\n        with:\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/contracts/{contract_id}\n      name: contract\n      description: Individual contract\n   \
  \   operations:\n      - method: GET\n        name: get-contract\n        description: Get contract details\n        call: upwork-graphql.get-contract\n        with:\n          contract_id: rest.contract_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/rooms/{room_id}/messages\n      name: messages\n      description: Contract messaging\n      operations:\n      - method: GET\n        name: list-messages\n        description: List messages in a room\n        call: upwork-graphql.list-messages\n        with:\n          room_id: rest.room_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: send-message\n        description: Send a message\n        call: upwork-graphql.send-message\n        with:\n          room_id: rest.room_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: upwork-talent-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted talent acquisition and freelancer management on Upwork.\n    tools:\n    - name: search-jobs\n      description: Search Upwork job postings by keywords, skills, and budget\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upwork-graphql.search-jobs\n      with:\n        q: tools.q\n        paging: tools.paging\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-job\n      description: Get detailed information for a specific Upwork job posting\n      hints:\n        readOnly: true\n      call: upwork-graphql.get-job\n      with:\n        job_id: tools.job_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-freelancers\n      description: Search for freelancers on Upwork by skills, rate, and availability\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upwork-graphql.search-freelancers\n      with:\n        q: tools.q\n\
  \        paging: tools.paging\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-freelancer-profile\n      description: Retrieve the full profile for a specific Upwork freelancer\n      hints:\n        readOnly: true\n      call: upwork-graphql.get-freelancer-profile\n      with:\n        user_id: tools.user_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-contracts\n      description: List all Upwork contracts with optional status filtering\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upwork-graphql.list-contracts\n      with:\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-contract\n      description: Get detailed information for a specific Upwork contract\n      hints:\n        readOnly: true\n      call: upwork-graphql.get-contract\n      with:\n        contract_id: tools.contract_id\n      outputParameters:\n  \
  \    - type: object\n        mapping: $.\n    - name: list-messages\n      description: List messages in a contract messaging room\n      hints:\n        readOnly: true\n      call: upwork-graphql.list-messages\n      with:\n        room_id: tools.room_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: send-message\n      description: Send a message in a contract messaging room\n      hints:\n        readOnly: false\n      call: upwork-graphql.send-message\n      with:\n        room_id: tools.room_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: execute-graphql\n      description: Execute a custom GraphQL query against the Upwork API\n      hints:\n        readOnly: true\n        openWorld: true\n      call: upwork-graphql.execute-graphql\n      with:\n        query: tools.query\n        variables: tools.variables\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/upwork/refs/heads/main/capabilities/talent-marketplace.yaml
tags:
- Upwork
- Freelancing
- Talent Acquisition
- Hiring
- Contracts
tools:
- description: Search Upwork job postings by keywords, skills, and budget
  hints:
    openWorld: true
    readOnly: true
  name: search-jobs
- description: Get detailed information for a specific Upwork job posting
  hints:
    readOnly: true
  name: get-job
- description: Search for freelancers on Upwork by skills, rate, and availability
  hints:
    openWorld: true
    readOnly: true
  name: search-freelancers
- description: Retrieve the full profile for a specific Upwork freelancer
  hints:
    readOnly: true
  name: get-freelancer-profile
- description: List all Upwork contracts with optional status filtering
  hints:
    openWorld: true
    readOnly: true
  name: list-contracts
- description: Get detailed information for a specific Upwork contract
  hints:
    readOnly: true
  name: get-contract
- description: List messages in a contract messaging room
  hints:
    readOnly: true
  name: list-messages
- description: Send a message in a contract messaging room
  hints:
    readOnly: false
  name: send-message
- description: Execute a custom GraphQL query against the Upwork API
  hints:
    openWorld: true
    readOnly: true
  name: execute-graphql
---
