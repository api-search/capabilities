---
categories: []
consumed_apis: []
description: Unified capability for teams to manage projects, tasks, and workflows using Trello's kanban-style boards. Provides board management, card tracking, list organization, team collaboration, and search for project managers, developers, and team leads.
layout: capability
name: Trello Project Management
operations:
- description: Create a new project board
  method: POST
  name: create-board
  path: /v1/boards
- description: Get board details
  method: GET
  name: get-board
  path: /v1/boards/{id}
- description: Update board settings
  method: PUT
  name: update-board
  path: /v1/boards/{id}
- description: Delete a board
  method: DELETE
  name: delete-board
  path: /v1/boards/{id}
- description: Get all cards on a board
  method: GET
  name: get-board-cards
  path: /v1/boards/{id}/cards
- description: Get board lists
  method: GET
  name: get-board-lists
  path: /v1/boards/{id}/lists
- description: Get board members
  method: GET
  name: get-board-members
  path: /v1/boards/{id}/members
- description: Create a task card
  method: POST
  name: create-card
  path: /v1/cards
- description: Get card
  method: GET
  name: get-card
  path: /v1/cards/{id}
- description: Update card
  method: PUT
  name: update-card
  path: /v1/cards/{id}
- description: Delete card
  method: DELETE
  name: delete-card
  path: /v1/cards/{id}
- description: Create a list
  method: POST
  name: create-list
  path: /v1/lists
- description: Get list
  method: GET
  name: get-list
  path: /v1/lists/{id}
- description: Update list
  method: PUT
  name: update-list
  path: /v1/lists/{id}
- description: Get cards in list
  method: GET
  name: get-list-cards
  path: /v1/lists/{id}/cards
- description: Get member
  method: GET
  name: get-member
  path: /v1/members/{id}
- description: Get member boards
  method: GET
  name: get-member-boards
  path: /v1/members/{id}/boards
- description: Search Trello
  method: GET
  name: search
  path: /v1/search
- description: Create webhook
  method: POST
  name: create-webhook
  path: /v1/webhooks
- description: Get webhook
  method: GET
  name: get-webhook
  path: /v1/webhooks/{id}
- description: Delete webhook
  method: DELETE
  name: delete-webhook
  path: /v1/webhooks/{id}
personas: []
provider_name: trello
provider_slug: trello
search_terms:
- permanently delete a trello card.
- update board
- update card
- member's boards
- delete webhook
- update list
- get webhook
- trello boards for project organization
- task management
- atlassian
- create a webhook to receive real-time notifications when trello resources change.
- get board lists
- create list
- create a new project board
- get a trello board by id including metadata and settings.
- create card
- delete board
- get card
- webhook detail
- get member boards
- search across trello for boards, cards, or members matching a query.
- get all cards on a board
- project board detail
- task cards
- list detail
- get list cards
- get all team members with access to a board.
- search trello
- create a list
- create webhook
- get list
- get board details
- create a new task card on a trello list with name, description, and due date.
- project management
- get a specific trello card including description, labels, due date, and members.
- collaboration
- all cards on a board
- workflow lists (columns)
- get all lists on a board (workflow columns like to do, in progress, done).
- get cards in list
- create a task card
- get board members
- get all cards on a board to review the full task backlog or sprint.
- get all cards in a specific trello list (workflow column).
- boards
- delete card
- cards
- update board settings
- team member
- lists on a board
- kanban
- task card detail
- get member
- cards in a list
- create a new workflow column (list) on a trello board.
- board team members
- get board cards
- create a new trello board for a project or team workflow.
- update a trello card to change name, description, due date, or move to another list.
- delete a board
- search
- create board
- trello webhooks
- search all trello resources
- get board
- get all trello boards accessible to a specific member.
slug: project-management
source_filename: project-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Trello Project Management\n  description: Unified capability for teams to manage projects, tasks, and workflows using Trello's kanban-style boards. Provides\n    board management, card tracking, list organization, team collaboration, and search for project managers, developers, and\n    team leads.\n  tags:\n  - Atlassian\n  - Boards\n  - Cards\n  - Collaboration\n  - Kanban\n  - Project Management\n  - Task Management\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRELLO_API_KEY: TRELLO_API_KEY\n    TRELLO_TOKEN: TRELLO_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: trello\n    baseUri: https://api.trello.com\n    description: Trello project management REST API\n    authentication:\n      type: apikey\n      key: key\n      value: '{{TRELLO_API_KEY}}'\n      placement: query\n    resources:\n    - name: boards\n      path: /1/boards\n      description: Trello boards\n      operations:\n\
  \      - name: create-board\n        method: POST\n        description: Create a Board\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            desc: '{{tools.desc}}'\n    - name: board-detail\n      path: /1/boards/{id}\n      description: Single Trello board\n      operations:\n      - name: get-board\n        method: GET\n        description: Get a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Board ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-board\n        method: PUT\n        description: Update a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n          description: Board ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            desc: '{{tools.desc}}'\n      - name: delete-board\n        method: DELETE\n        description: Delete a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Board ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: board-cards\n      path: /1/boards/{id}/cards\n      description: Cards on a board\n      operations:\n      - name: get-board-cards\n        method: GET\n        description: Get Cards on a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description:\
  \ Board ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: board-lists\n      path: /1/boards/{id}/lists\n      description: Lists on a board\n      operations:\n      - name: get-board-lists\n        method: GET\n        description: Get Lists on a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Board ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: board-members\n      path: /1/boards/{id}/members\n      description: Members of a board\n      operations:\n      - name: get-board-members\n        method: GET\n        description: Get Members of a Board\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Board ID\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cards\n      path: /1/cards\n      description: Trello cards\n      operations:\n      - name: create-card\n        method: POST\n        description: Create a new Card\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            idList: '{{tools.idList}}'\n            desc: '{{tools.desc}}'\n            due: '{{tools.due}}'\n    - name: card-detail\n      path: /1/cards/{id}\n      description: Single Trello card\n      operations:\n      - name: get-card\n        method: GET\n        description: Get a Card\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Card ID\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-card\n        method: PUT\n        description: Update a Card\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Card ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            desc: '{{tools.desc}}'\n            due: '{{tools.due}}'\n            closed: '{{tools.closed}}'\n            idList: '{{tools.idList}}'\n      - name: delete-card\n        method: DELETE\n        description: Delete a Card\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Card ID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: lists\n      path: /1/lists\n      description: Trello lists\n      operations:\n      - name: create-list\n        method: POST\n        description: Create a new List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            idBoard: '{{tools.idBoard}}'\n    - name: list-detail\n      path: /1/lists/{id}\n      description: Single Trello list\n      operations:\n      - name: get-list\n        method: GET\n        description: Get a List\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-list\n        method:\
  \ PUT\n        description: Update a List\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            closed: '{{tools.closed}}'\n    - name: list-cards\n      path: /1/lists/{id}/cards\n      description: Cards in a list\n      operations:\n      - name: get-list-cards\n        method: GET\n        description: Get the Cards in a List\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: List ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: members\n      path: /1/members/{id}\n      description:\
  \ Trello member details\n      operations:\n      - name: get-member\n        method: GET\n        description: Get a Member\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Member ID or username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: member-boards\n      path: /1/members/{id}/boards\n      description: Boards for a member\n      operations:\n      - name: get-member-boards\n        method: GET\n        description: Get Member's Boards\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Member ID or username\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /1/search\n      description: Search Trello resources\n\
  \      operations:\n      - name: search\n        method: GET\n        description: Search across Trello\n        inputParameters:\n        - name: query\n          in: query\n          type: string\n          required: true\n          description: Search query\n        - name: modelTypes\n          in: query\n          type: string\n          required: false\n          description: Types to search (boards, cards, members)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks\n      path: /1/webhooks\n      description: Trello webhooks\n      operations:\n      - name: create-webhook\n        method: POST\n        description: Create a Webhook\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n            callbackURL:\
  \ '{{tools.callbackURL}}'\n            idModel: '{{tools.idModel}}'\n    - name: webhook-detail\n      path: /1/webhooks/{id}\n      description: Single webhook\n      operations:\n      - name: get-webhook\n        method: GET\n        description: Get a Webhook\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Webhook ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-webhook\n        method: PUT\n        description: Update a Webhook\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Webhook ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            description: '{{tools.description}}'\n\
  \            callbackURL: '{{tools.callbackURL}}'\n            active: '{{tools.active}}'\n      - name: delete-webhook\n        method: DELETE\n        description: Delete a Webhook\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: Webhook ID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: trello-project-mgmt-api\n    description: Unified REST API for Trello project and task management.\n    resources:\n    - path: /v1/boards\n      name: boards\n      description: Trello boards for project organization\n      operations:\n      - method: POST\n        name: create-board\n        description: Create a new project board\n        call: trello.create-board\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boards/{id}\n   \
  \   name: board-detail\n      description: Project board detail\n      operations:\n      - method: GET\n        name: get-board\n        description: Get board details\n        call: trello.get-board\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-board\n        description: Update board settings\n        call: trello.update-board\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-board\n        description: Delete a board\n        call: trello.delete-board\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boards/{id}/cards\n      name: board-cards\n      description: All cards on a board\n      operations:\n      - method: GET\n        name: get-board-cards\n        description: Get all cards on\
  \ a board\n        call: trello.get-board-cards\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boards/{id}/lists\n      name: board-lists\n      description: Lists on a board\n      operations:\n      - method: GET\n        name: get-board-lists\n        description: Get board lists\n        call: trello.get-board-lists\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/boards/{id}/members\n      name: board-members\n      description: Board team members\n      operations:\n      - method: GET\n        name: get-board-members\n        description: Get board members\n        call: trello.get-board-members\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cards\n      name: cards\n      description: Task cards\n      operations:\n      - method: POST\n\
  \        name: create-card\n        description: Create a task card\n        call: trello.create-card\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/cards/{id}\n      name: card-detail\n      description: Task card detail\n      operations:\n      - method: GET\n        name: get-card\n        description: Get card\n        call: trello.get-card\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-card\n        description: Update card\n        call: trello.update-card\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-card\n        description: Delete card\n        call: trello.delete-card\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists\n      name: lists\n\
  \      description: Workflow lists (columns)\n      operations:\n      - method: POST\n        name: create-list\n        description: Create a list\n        call: trello.create-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists/{id}\n      name: list-detail\n      description: List detail\n      operations:\n      - method: GET\n        name: get-list\n        description: Get list\n        call: trello.get-list\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: update-list\n        description: Update list\n        call: trello.update-list\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/lists/{id}/cards\n      name: list-cards\n      description: Cards in a list\n      operations:\n      - method: GET\n        name: get-list-cards\n        description: Get cards\
  \ in list\n        call: trello.get-list-cards\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}\n      name: member-detail\n      description: Team member\n      operations:\n      - method: GET\n        name: get-member\n        description: Get member\n        call: trello.get-member\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/members/{id}/boards\n      name: member-boards\n      description: Member's boards\n      operations:\n      - method: GET\n        name: get-member-boards\n        description: Get member boards\n        call: trello.get-member-boards\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/search\n      name: search\n      description: Search all Trello resources\n      operations:\n      - method: GET\n        name:\
  \ search\n        description: Search Trello\n        call: trello.search\n        with:\n          query: rest.query\n          modelTypes: rest.modelTypes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks\n      name: webhooks\n      description: Trello webhooks\n      operations:\n      - method: POST\n        name: create-webhook\n        description: Create webhook\n        call: trello.create-webhook\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/webhooks/{id}\n      name: webhook-detail\n      description: Webhook detail\n      operations:\n      - method: GET\n        name: get-webhook\n        description: Get webhook\n        call: trello.get-webhook\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-webhook\n        description: Delete webhook\n        call: trello.delete-webhook\n\
  \        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: trello-project-mgmt-mcp\n    transport: http\n    description: MCP server for AI-assisted project management using Trello boards, lists, and cards.\n    tools:\n    - name: get-board\n      description: Get a Trello board by ID including metadata and settings.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trello.get-board\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-board\n      description: Create a new Trello board for a project or team workflow.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trello.create-board\n      with:\n        name: tools.name\n        desc: tools.desc\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-board-cards\n\
  \      description: Get all cards on a board to review the full task backlog or sprint.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.get-board-cards\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-board-lists\n      description: Get all lists on a board (workflow columns like To Do, In Progress, Done).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.get-board-lists\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-board-members\n      description: Get all team members with access to a board.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.get-board-members\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-card\n      description: Create a new task card on a Trello list\
  \ with name, description, and due date.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trello.create-card\n      with:\n        name: tools.name\n        idList: tools.idList\n        desc: tools.desc\n        due: tools.due\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-card\n      description: Get a specific Trello card including description, labels, due date, and members.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: trello.get-card\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-card\n      description: Update a Trello card to change name, description, due date, or move to another list.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: trello.update-card\n      with:\n        id: tools.id\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: delete-card\n      description: Permanently delete a Trello card.\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: trello.delete-card\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-list\n      description: Create a new workflow column (list) on a Trello board.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trello.create-list\n      with:\n        name: tools.name\n        idBoard: tools.idBoard\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-list-cards\n      description: Get all cards in a specific Trello list (workflow column).\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.get-list-cards\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: get-member-boards\n      description: Get all Trello boards accessible to a specific member.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.get-member-boards\n      with:\n        id: tools.id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Search across Trello for boards, cards, or members matching a query.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: trello.search\n      with:\n        query: tools.query\n        modelTypes: tools.modelTypes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-webhook\n      description: Create a webhook to receive real-time notifications when Trello resources change.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: trello.create-webhook\n      with:\n        description: tools.description\n        callbackURL: tools.callbackURL\n\
  \        idModel: tools.idModel\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/trello/refs/heads/main/capabilities/project-management.yaml
tags:
- Atlassian
- Boards
- Cards
- Collaboration
- Kanban
- Project Management
- Task Management
tools:
- description: Get a Trello board by ID including metadata and settings.
  hints:
    openWorld: false
    readOnly: true
  name: get-board
- description: Create a new Trello board for a project or team workflow.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-board
- description: Get all cards on a board to review the full task backlog or sprint.
  hints:
    openWorld: true
    readOnly: true
  name: get-board-cards
- description: Get all lists on a board (workflow columns like To Do, In Progress, Done).
  hints:
    openWorld: true
    readOnly: true
  name: get-board-lists
- description: Get all team members with access to a board.
  hints:
    openWorld: true
    readOnly: true
  name: get-board-members
- description: Create a new task card on a Trello list with name, description, and due date.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-card
- description: Get a specific Trello card including description, labels, due date, and members.
  hints:
    openWorld: false
    readOnly: true
  name: get-card
- description: Update a Trello card to change name, description, due date, or move to another list.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-card
- description: Permanently delete a Trello card.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-card
- description: Create a new workflow column (list) on a Trello board.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-list
- description: Get all cards in a specific Trello list (workflow column).
  hints:
    openWorld: true
    readOnly: true
  name: get-list-cards
- description: Get all Trello boards accessible to a specific member.
  hints:
    openWorld: true
    readOnly: true
  name: get-member-boards
- description: Search across Trello for boards, cards, or members matching a query.
  hints:
    openWorld: true
    readOnly: true
  name: search
- description: Create a webhook to receive real-time notifications when Trello resources change.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-webhook
---
