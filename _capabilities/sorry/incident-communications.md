---
categories: []
consumed_apis: []
description: Unified capability for automated incident communication workflows using the Sorry™ API. Enables DevOps and support teams to programmatically manage status pages, publish incident notices, post updates as incidents evolve, and manage subscriber notifications during service disruptions and maintenance windows.
layout: capability
name: Sorry Incident Communications
operations:
- description: List all status pages in the account
  method: GET
  name: list-pages
  path: /v1/pages
- description: Create a new status page
  method: POST
  name: create-page
  path: /v1/pages
- description: List components for a status page
  method: GET
  name: list-components
  path: /v1/pages/{page_id}/components
- description: Add a component to a status page
  method: POST
  name: create-component
  path: /v1/pages/{page_id}/components
- description: List all notices for a status page
  method: GET
  name: list-notices
  path: /v1/pages/{page_id}/notices
- description: Create an incident or maintenance notice
  method: POST
  name: create-notice
  path: /v1/pages/{page_id}/notices
- description: List all updates for a notice
  method: GET
  name: list-notice-updates
  path: /v1/pages/{page_id}/notices/{notice_id}/updates
- description: Publish an update to an active incident notice
  method: POST
  name: create-notice-update
  path: /v1/pages/{page_id}/notices/{notice_id}/updates
- description: List all subscribers for a status page
  method: GET
  name: list-subscribers
  path: /v1/pages/{page_id}/subscribers
- description: Add a subscriber to a status page
  method: POST
  name: create-subscriber
  path: /v1/pages/{page_id}/subscribers
personas: []
provider_name: Sorry
provider_slug: sorry
search_terms:
- create subscriber
- notifications
- devops
- create an incident or maintenance notice
- list notice updates
- publish incident update
- create notice update
- update incident state
- list all status pages in the sorry account. use to find page ids for subsequent operations during incident response.
- add a new subscriber to receive status page notifications via email or sms.
- status page management
- publish an update to an active incident notice
- list components for a status page
- create incident notice
- create a new status page
- monitoring
- create notice
- list all status pages in the account
- incident and maintenance notices
- list all notices for a status page. use to find active incidents or review recent maintenance windows.
- update the state or details of an existing incident notice. use to progress an incident through monitoring, resolved, or completed states.
- customer communication
- list subscribers
- subscriber management
- add subscriber
- create component
- list all subscribers for a status page
- list all components for a status page. use to identify affected components before creating incident notices.
- create an incident notice on a status page to notify customers of an unplanned outage or service degradation. use for incident declaration.
- developer tools
- list all notices for a status page
- list status pages
- incident management
- status pages
- publish a new status update to an existing incident notice. use to keep customers informed as the incident investigation progresses.
- add a subscriber to a status page
- list pages
- component management
- list all updates for a notice
- incident status updates
- add a component to a status page
- create page
- list notices
- sorry
- list subscribers for a status page. use to understand notification reach before publishing a major incident notice.
- list components
slug: incident-communications
source_filename: incident-communications.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Sorry Incident Communications\n  description: Unified capability for automated incident communication workflows using the Sorry™ API. Enables DevOps and\n    support teams to programmatically manage status pages, publish incident notices, post updates as incidents evolve, and\n    manage subscriber notifications during service disruptions and maintenance windows.\n  tags:\n  - Sorry\n  - Status Pages\n  - Incident Management\n  - Notifications\n  - Customer Communication\n  - DevOps\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    SORRY_BEARER_TOKEN: SORRY_BEARER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: sorry-api\n    baseUri: https://api.sorryapp.com/v1\n    description: Sorry™ REST API for status page and incident management\n    authentication:\n      type: bearer\n      token: '{{SORRY_BEARER_TOKEN}}'\n    resources:\n    - name: pages\n      path: /pages\n      description:\
  \ Status page management\n      operations:\n      - name: list-pages\n        method: GET\n        description: List all status pages in the account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-page\n        method: POST\n        description: Create a new status page\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            timezone: '{{tools.timezone}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-page\n        method: GET\n        description: Retrieve a single status page by ID\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: update-page\n        method: PATCH\n        description: Update status page settings\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            support_email: '{{tools.support_email}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-page\n        method: DELETE\n        description: Delete a status page and all its content\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: components\n\
  \      path: /pages/{page_id}/components\n      description: Component management for status pages\n      operations:\n      - name: list-components\n        method: GET\n        description: List all components for a status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-component\n        method: POST\n        description: Add a new component to a status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            description: '{{tools.description}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: get-component\n        method: GET\n        description: Retrieve a component including its current operational state\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: Status page identifier\n        - name: component_id\n          in: path\n          type: string\n          required: true\n          description: Component identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-component\n        method: PATCH\n        description: Update component properties\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: component_id\n          in: path\n          type: string\n          required: true\n        body:\n          type:\
  \ json\n          data:\n            name: '{{tools.name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-component\n        method: DELETE\n        description: Delete a component from a status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: component_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notices\n      path: /pages/{page_id}/notices\n      description: Incident and maintenance notice management\n      operations:\n      - name: list-notices\n        method: GET\n        description: List all notices for a status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n     \
  \     required: true\n        - name: include\n          in: query\n          type: string\n          required: false\n          description: Related resources to include (components,updates)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notice\n        method: POST\n        description: Create an incident or maintenance notice\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            type: '{{tools.type}}'\n            subject: '{{tools.subject}}'\n            initial_comment: '{{tools.initial_comment}}'\n            should_publish: '{{tools.should_publish}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-notice\n        method: GET\n        description: Retrieve\
  \ a single notice\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: notice_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-notice\n        method: PATCH\n        description: Update notice details or state\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: notice_id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            state: '{{tools.state}}'\n            additional_comment: '{{tools.additional_comment}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-notice\n\
  \        method: DELETE\n        description: Delete a notice from the status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: notice_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notice-updates\n      path: /pages/{page_id}/notices/{notice_id}/updates\n      description: Notice update publishing\n      operations:\n      - name: list-notice-updates\n        method: GET\n        description: List all updates for a notice\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: notice_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: create-notice-update\n        method: POST\n        description: Publish a new update to an existing notice\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: notice_id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            content: '{{tools.content}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscribers\n      path: /pages/{page_id}/subscribers\n      description: Subscriber list management\n      operations:\n      - name: list-subscribers\n        method: GET\n        description: List all subscribers for a status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n\
  \          type: integer\n          required: false\n          description: Pagination page (500 per page)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscriber\n        method: POST\n        description: Add a new subscriber to the status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            first_name: '{{tools.first_name}}'\n            last_name: '{{tools.last_name}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscriber\n        method: DELETE\n        description: Remove a subscriber from the status page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n\
  \          required: true\n        - name: subscriber_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: sorry-incident-comms-api\n    description: Unified REST API for automated incident communication workflows via Sorry.\n    resources:\n    - path: /v1/pages\n      name: pages\n      description: Status page management\n      operations:\n      - method: GET\n        name: list-pages\n        description: List all status pages in the account\n        call: sorry-api.list-pages\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-page\n        description: Create a new status page\n        call: sorry-api.create-page\n        with:\n          name: rest.name\n          timezone: rest.timezone\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/pages/{page_id}/components\n      name: components\n      description: Component management\n      operations:\n      - method: GET\n        name: list-components\n        description: List components for a status page\n        call: sorry-api.list-components\n        with:\n          page_id: rest.page_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-component\n        description: Add a component to a status page\n        call: sorry-api.create-component\n        with:\n          page_id: rest.page_id\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{page_id}/notices\n      name: notices\n      description: Incident and maintenance notices\n      operations:\n      - method: GET\n        name: list-notices\n        description: List all notices for a status page\n        call:\
  \ sorry-api.list-notices\n        with:\n          page_id: rest.page_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-notice\n        description: Create an incident or maintenance notice\n        call: sorry-api.create-notice\n        with:\n          page_id: rest.page_id\n          type: rest.type\n          subject: rest.subject\n          initial_comment: rest.initial_comment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{page_id}/notices/{notice_id}/updates\n      name: notice-updates\n      description: Incident status updates\n      operations:\n      - method: GET\n        name: list-notice-updates\n        description: List all updates for a notice\n        call: sorry-api.list-notice-updates\n        with:\n          page_id: rest.page_id\n          notice_id: rest.notice_id\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \   - method: POST\n        name: create-notice-update\n        description: Publish an update to an active incident notice\n        call: sorry-api.create-notice-update\n        with:\n          page_id: rest.page_id\n          notice_id: rest.notice_id\n          content: rest.content\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/pages/{page_id}/subscribers\n      name: subscribers\n      description: Subscriber management\n      operations:\n      - method: GET\n        name: list-subscribers\n        description: List all subscribers for a status page\n        call: sorry-api.list-subscribers\n        with:\n          page_id: rest.page_id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-subscriber\n        description: Add a subscriber to a status page\n        call: sorry-api.create-subscriber\n        with:\n          page_id: rest.page_id\n          email: rest.email\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: sorry-incident-comms-mcp\n    transport: http\n    description: MCP server for AI-assisted incident communication using Sorry status pages.\n    tools:\n    - name: list-status-pages\n      description: List all status pages in the Sorry account. Use to find page IDs for subsequent operations during incident\n        response.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sorry-api.list-pages\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-components\n      description: List all components for a status page. Use to identify affected components before creating incident notices.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sorry-api.list-components\n      with:\n        page_id: tools.page_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ create-incident-notice\n      description: Create an incident notice on a status page to notify customers of an unplanned outage or service degradation.\n        Use for incident declaration.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sorry-api.create-notice\n      with:\n        page_id: tools.page_id\n        type: tools.type\n        subject: tools.subject\n        initial_comment: tools.initial_comment\n        should_publish: tools.should_publish\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notices\n      description: List all notices for a status page. Use to find active incidents or review recent maintenance windows.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sorry-api.list-notices\n      with:\n        page_id: tools.page_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-incident-state\n      description:\
  \ Update the state or details of an existing incident notice. Use to progress an incident through monitoring,\n        resolved, or completed states.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: sorry-api.update-notice\n      with:\n        page_id: tools.page_id\n        notice_id: tools.notice_id\n        state: tools.state\n        additional_comment: tools.additional_comment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-incident-update\n      description: Publish a new status update to an existing incident notice. Use to keep customers informed as the incident\n        investigation progresses.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sorry-api.create-notice-update\n      with:\n        page_id: tools.page_id\n        notice_id: tools.notice_id\n        content: tools.content\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: list-subscribers\n      description: List subscribers for a status page. Use to understand notification reach before publishing a major incident\n        notice.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: sorry-api.list-subscribers\n      with:\n        page_id: tools.page_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-subscriber\n      description: Add a new subscriber to receive status page notifications via email or SMS.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: sorry-api.create-subscriber\n      with:\n        page_id: tools.page_id\n        email: tools.email\n        first_name: tools.first_name\n        last_name: tools.last_name\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/sorry/refs/heads/main/capabilities/incident-communications.yaml
tags:
- Sorry
- Status Pages
- Incident Management
- Notifications
- Customer Communication
- DevOps
tools:
- description: List all status pages in the Sorry account. Use to find page IDs for subsequent operations during incident response.
  hints:
    openWorld: false
    readOnly: true
  name: list-status-pages
- description: List all components for a status page. Use to identify affected components before creating incident notices.
  hints:
    openWorld: false
    readOnly: true
  name: list-components
- description: Create an incident notice on a status page to notify customers of an unplanned outage or service degradation. Use for incident declaration.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-incident-notice
- description: List all notices for a status page. Use to find active incidents or review recent maintenance windows.
  hints:
    openWorld: false
    readOnly: true
  name: list-notices
- description: Update the state or details of an existing incident notice. Use to progress an incident through monitoring, resolved, or completed states.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-incident-state
- description: Publish a new status update to an existing incident notice. Use to keep customers informed as the incident investigation progresses.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: publish-incident-update
- description: List subscribers for a status page. Use to understand notification reach before publishing a major incident notice.
  hints:
    openWorld: false
    readOnly: true
  name: list-subscribers
- description: Add a new subscriber to receive status page notifications via email or SMS.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-subscriber
---
