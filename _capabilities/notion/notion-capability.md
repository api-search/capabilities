---
categories: []
consumed_apis: []
description: The Notion API allows developers to integrate with Notion workspaces programmatically. Build integrations that connect Notion with other tools, automate workflows, and manage workspace content including pages, databases, blocks, users, comments, and search. Notion is an all-in-one workspace that combines notes, tasks, wikis, and databases into a flexible, collaborative platform.
layout: capability
name: Notion API
operations:
- description: Notion Create a page
  method: POST
  name: createpage
  path: /pages
- description: Notion Retrieve a page
  method: GET
  name: retrievepage
  path: /pages/{page_id}
- description: Notion Update page properties
  method: PATCH
  name: updatepage
  path: /pages/{page_id}
- description: Notion Retrieve a page property item
  method: GET
  name: retrievepageproperty
  path: /pages/{page_id}/properties/{property_id}
- description: Notion Create a database
  method: POST
  name: createdatabase
  path: /databases
- description: Notion Retrieve a database
  method: GET
  name: retrievedatabase
  path: /databases/{database_id}
- description: Notion Update a database
  method: PATCH
  name: updatedatabase
  path: /databases/{database_id}
- description: Notion Query a database
  method: POST
  name: querydatabase
  path: /databases/{database_id}/query
- description: Notion Retrieve a block
  method: GET
  name: retrieveblock
  path: /blocks/{block_id}
- description: Notion Update a block
  method: PATCH
  name: updateblock
  path: /blocks/{block_id}
- description: Notion Delete a block
  method: DELETE
  name: deleteblock
  path: /blocks/{block_id}
- description: Notion Retrieve block children
  method: GET
  name: retrieveblockchildren
  path: /blocks/{block_id}/children
- description: Notion Append block children
  method: PATCH
  name: appendblockchildren
  path: /blocks/{block_id}/children
- description: Notion List all users
  method: GET
  name: listusers
  path: /users
- description: Notion Retrieve a user
  method: GET
  name: retrieveuser
  path: /users/{user_id}
- description: Notion Retrieve the bot user
  method: GET
  name: retrievebotuser
  path: /users/me
- description: Notion Search by title
  method: POST
  name: search
  path: /search
- description: Notion Retrieve comments
  method: GET
  name: listcomments
  path: /comments
- description: Notion Create a comment
  method: POST
  name: createcomment
  path: /comments
personas: []
provider_name: Notion
provider_slug: notion
search_terms:
- deleteblock
- notion search by title
- ideas
- tasks
- wiki
- notes
- projects
- notion retrieve a page
- createpage
- notion list all users
- listcomments
- notion create a comment
- notion delete a block
- retrieveblockchildren
- notion update page properties
- retrievebotuser
- notion retrieve comments
- retrievedatabase
- notion update a database
- productivity
- notion retrieve a page property item
- notion create a database
- retrieveuser
- retrieveblock
- retrievepage
- notion retrieve block children
- database
- t1
- createdatabase
- api
- notion query a database
- updatedatabase
- search
- notion retrieve the bot user
- retrievepageproperty
- notion retrieve a block
- appendblockchildren
- notion retrieve a user
- querydatabase
- notion retrieve a database
- notion append block children
- notion create a page
- workspace
- notion update a block
- listusers
- notion
- collaboration
- updateblock
- createcomment
- updatepage
slug: notion-capability
source_filename: notion-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Notion API\n  description: The Notion API allows developers to integrate with Notion workspaces programmatically. Build integrations that\n    connect Notion with other tools, automate workflows, and manage workspace content including pages, databases, blocks,\n    users, comments, and search. Notion is an all-in-one workspace that combines notes, tasks, wikis, and databases into a\n    flexible, collaborative platform.\n  tags:\n  - Notion\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: notion\n    baseUri: https://api.notion.com/v1\n    description: Notion API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{NOTION_TOKEN}}'\n    resources:\n    - name: pages\n      path: /pages\n      operations:\n      - name: createpage\n        method: POST\n        description: Notion Create a page\n        outputRawFormat: json\n        outputParameters:\n \
  \       - name: result\n          type: object\n          value: $.\n    - name: pages-page-id\n      path: /pages/{page_id}\n      operations:\n      - name: retrievepage\n        method: GET\n        description: Notion Retrieve a page\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the page to retrieve.\n        - name: filter_properties\n          in: query\n          type: array\n          description: A list of page property value IDs to include in the response. If provided, only the specified properties\n            will be returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepage\n        method: PATCH\n        description: Notion Update page properties\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The ID of the page to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pages-page-id-properties-property-id\n      path: /pages/{page_id}/properties/{property_id}\n      operations:\n      - name: retrievepageproperty\n        method: GET\n        description: Notion Retrieve a page property item\n        inputParameters:\n        - name: page_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the page.\n        - name: property_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the property to retrieve.\n        - name: start_cursor\n          in: query\n          type: string\n          description: Pagination cursor for paginated property types. If supplied, returns results starting after the cursor.\n        - name: page_size\n          in: query\n  \
  \        type: integer\n          description: Maximum number of property items to return (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases\n      path: /databases\n      operations:\n      - name: createdatabase\n        method: POST\n        description: Notion Create a database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-database-id\n      path: /databases/{database_id}\n      operations:\n      - name: retrievedatabase\n        method: GET\n        description: Notion Retrieve a database\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the database to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: updatedatabase\n        method: PATCH\n        description: Notion Update a database\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the database to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: databases-database-id-query\n      path: /databases/{database_id}/query\n      operations:\n      - name: querydatabase\n        method: POST\n        description: Notion Query a database\n        inputParameters:\n        - name: database_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the database to query.\n        - name: filter_properties\n          in: query\n          type: array\n          description: A list of property IDs to include in the response. Only the specified properties will\
  \ be returned for\n            each page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks-block-id\n      path: /blocks/{block_id}\n      operations:\n      - name: retrieveblock\n        method: GET\n        description: Notion Retrieve a block\n        inputParameters:\n        - name: block_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the block to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateblock\n        method: PATCH\n        description: Notion Update a block\n        inputParameters:\n        - name: block_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the block to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deleteblock\n        method: DELETE\n        description: Notion Delete a block\n        inputParameters:\n        - name: block_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the block to delete (archive).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: blocks-block-id-children\n      path: /blocks/{block_id}/children\n      operations:\n      - name: retrieveblockchildren\n        method: GET\n        description: Notion Retrieve block children\n        inputParameters:\n        - name: block_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the block whose children to retrieve. This can be a page ID to retrieve page content.\n        - name: start_cursor\n          in: query\n          type: string\n          description:\
  \ Pagination cursor to continue fetching results.\n        - name: page_size\n          in: query\n          type: integer\n          description: Maximum number of blocks to return (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: appendblockchildren\n        method: PATCH\n        description: Notion Append block children\n        inputParameters:\n        - name: block_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the block to append children to. This can be a page ID to add content to a page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      operations:\n      - name: listusers\n        method: GET\n        description: Notion List all users\n        inputParameters:\n        - name: start_cursor\n \
  \         in: query\n          type: string\n          description: Pagination cursor to continue fetching results.\n        - name: page_size\n          in: query\n          type: integer\n          description: Maximum number of users to return (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-user-id\n      path: /users/{user_id}\n      operations:\n      - name: retrieveuser\n        method: GET\n        description: Notion Retrieve a user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the user to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users-me\n      path: /users/me\n      operations:\n      - name: retrievebotuser\n        method: GET\n        description: Notion\
  \ Retrieve the bot user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      operations:\n      - name: search\n        method: POST\n        description: Notion Search by title\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: comments\n      path: /comments\n      operations:\n      - name: listcomments\n        method: GET\n        description: Notion Retrieve comments\n        inputParameters:\n        - name: block_id\n          in: query\n          type: string\n          required: true\n          description: The ID of the block or page to retrieve comments for.\n        - name: start_cursor\n          in: query\n          type: string\n          description: Pagination cursor to continue fetching results.\n        - name: page_size\n          in: query\n          type:\
  \ integer\n          description: Maximum number of comments to return (max 100).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcomment\n        method: POST\n        description: Notion Create a comment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: notion-rest\n    description: REST adapter for Notion API.\n    resources:\n    - path: /pages\n      name: createpage\n      operations:\n      - method: POST\n        name: createpage\n        description: Notion Create a page\n        call: notion.createpage\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{page_id}\n      name: retrievepage\n      operations:\n      - method: GET\n        name: retrievepage\n        description: Notion Retrieve a page\n\
  \        call: notion.retrievepage\n        with:\n          page_id: rest.page_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{page_id}\n      name: updatepage\n      operations:\n      - method: PATCH\n        name: updatepage\n        description: Notion Update page properties\n        call: notion.updatepage\n        with:\n          page_id: rest.page_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pages/{page_id}/properties/{property_id}\n      name: retrievepageproperty\n      operations:\n      - method: GET\n        name: retrievepageproperty\n        description: Notion Retrieve a page property item\n        call: notion.retrievepageproperty\n        with:\n          page_id: rest.page_id\n          property_id: rest.property_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases\n      name: createdatabase\n      operations:\n      - method:\
  \ POST\n        name: createdatabase\n        description: Notion Create a database\n        call: notion.createdatabase\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{database_id}\n      name: retrievedatabase\n      operations:\n      - method: GET\n        name: retrievedatabase\n        description: Notion Retrieve a database\n        call: notion.retrievedatabase\n        with:\n          database_id: rest.database_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{database_id}\n      name: updatedatabase\n      operations:\n      - method: PATCH\n        name: updatedatabase\n        description: Notion Update a database\n        call: notion.updatedatabase\n        with:\n          database_id: rest.database_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /databases/{database_id}/query\n      name: querydatabase\n      operations:\n   \
  \   - method: POST\n        name: querydatabase\n        description: Notion Query a database\n        call: notion.querydatabase\n        with:\n          database_id: rest.database_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blocks/{block_id}\n      name: retrieveblock\n      operations:\n      - method: GET\n        name: retrieveblock\n        description: Notion Retrieve a block\n        call: notion.retrieveblock\n        with:\n          block_id: rest.block_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blocks/{block_id}\n      name: updateblock\n      operations:\n      - method: PATCH\n        name: updateblock\n        description: Notion Update a block\n        call: notion.updateblock\n        with:\n          block_id: rest.block_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blocks/{block_id}\n      name: deleteblock\n      operations:\n\
  \      - method: DELETE\n        name: deleteblock\n        description: Notion Delete a block\n        call: notion.deleteblock\n        with:\n          block_id: rest.block_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blocks/{block_id}/children\n      name: retrieveblockchildren\n      operations:\n      - method: GET\n        name: retrieveblockchildren\n        description: Notion Retrieve block children\n        call: notion.retrieveblockchildren\n        with:\n          block_id: rest.block_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /blocks/{block_id}/children\n      name: appendblockchildren\n      operations:\n      - method: PATCH\n        name: appendblockchildren\n        description: Notion Append block children\n        call: notion.appendblockchildren\n        with:\n          block_id: rest.block_id\n        outputParameters:\n        - type: object\n          mapping: $.\n   \
  \ - path: /users\n      name: listusers\n      operations:\n      - method: GET\n        name: listusers\n        description: Notion List all users\n        call: notion.listusers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/{user_id}\n      name: retrieveuser\n      operations:\n      - method: GET\n        name: retrieveuser\n        description: Notion Retrieve a user\n        call: notion.retrieveuser\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /users/me\n      name: retrievebotuser\n      operations:\n      - method: GET\n        name: retrievebotuser\n        description: Notion Retrieve the bot user\n        call: notion.retrievebotuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /search\n      name: search\n      operations:\n      - method: POST\n        name: search\n        description: Notion\
  \ Search by title\n        call: notion.search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments\n      name: listcomments\n      operations:\n      - method: GET\n        name: listcomments\n        description: Notion Retrieve comments\n        call: notion.listcomments\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /comments\n      name: createcomment\n      operations:\n      - method: POST\n        name: createcomment\n        description: Notion Create a comment\n        call: notion.createcomment\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: notion-mcp\n    transport: http\n    description: MCP adapter for Notion API for AI agent use.\n    tools:\n    - name: createpage\n      description: Notion Create a page\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.createpage\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievepage\n      description: Notion Retrieve a page\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrievepage\n      with:\n        page_id: tools.page_id\n        filter_properties: tools.filter_properties\n      inputParameters:\n      - name: page_id\n        type: string\n        description: The ID of the page to retrieve.\n        required: true\n      - name: filter_properties\n        type: array\n        description: A list of page property value IDs to include in the response. If provided, only the specified properties\n          will be returned.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatepage\n      description: Notion Update page properties\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.updatepage\n      with:\n  \
  \      page_id: tools.page_id\n      inputParameters:\n      - name: page_id\n        type: string\n        description: The ID of the page to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievepageproperty\n      description: Notion Retrieve a page property item\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrievepageproperty\n      with:\n        page_id: tools.page_id\n        property_id: tools.property_id\n        start_cursor: tools.start_cursor\n        page_size: tools.page_size\n      inputParameters:\n      - name: page_id\n        type: string\n        description: The ID of the page.\n        required: true\n      - name: property_id\n        type: string\n        description: The ID of the property to retrieve.\n        required: true\n      - name: start_cursor\n        type: string\n        description: Pagination cursor for paginated\
  \ property types. If supplied, returns results starting after the cursor.\n      - name: page_size\n        type: integer\n        description: Maximum number of property items to return (max 100).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createdatabase\n      description: Notion Create a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.createdatabase\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievedatabase\n      description: Notion Retrieve a database\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrievedatabase\n      with:\n        database_id: tools.database_id\n      inputParameters:\n      - name: database_id\n        type: string\n        description: The ID of the database to retrieve.\n        required: true\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: updatedatabase\n      description: Notion Update a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.updatedatabase\n      with:\n        database_id: tools.database_id\n      inputParameters:\n      - name: database_id\n        type: string\n        description: The ID of the database to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querydatabase\n      description: Notion Query a database\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.querydatabase\n      with:\n        database_id: tools.database_id\n        filter_properties: tools.filter_properties\n      inputParameters:\n      - name: database_id\n        type: string\n        description: The ID of the database to query.\n        required: true\n      - name: filter_properties\n        type:\
  \ array\n        description: A list of property IDs to include in the response. Only the specified properties will be returned for\n          each page.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveblock\n      description: Notion Retrieve a block\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrieveblock\n      with:\n        block_id: tools.block_id\n      inputParameters:\n      - name: block_id\n        type: string\n        description: The ID of the block to retrieve.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateblock\n      description: Notion Update a block\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.updateblock\n      with:\n        block_id: tools.block_id\n      inputParameters:\n      - name: block_id\n        type: string\n     \
  \   description: The ID of the block to update.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteblock\n      description: Notion Delete a block\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: notion.deleteblock\n      with:\n        block_id: tools.block_id\n      inputParameters:\n      - name: block_id\n        type: string\n        description: The ID of the block to delete (archive).\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveblockchildren\n      description: Notion Retrieve block children\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrieveblockchildren\n      with:\n        block_id: tools.block_id\n        start_cursor: tools.start_cursor\n        page_size: tools.page_size\n      inputParameters:\n      - name: block_id\n  \
  \      type: string\n        description: The ID of the block whose children to retrieve. This can be a page ID to retrieve page content.\n        required: true\n      - name: start_cursor\n        type: string\n        description: Pagination cursor to continue fetching results.\n      - name: page_size\n        type: integer\n        description: Maximum number of blocks to return (max 100).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: appendblockchildren\n      description: Notion Append block children\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.appendblockchildren\n      with:\n        block_id: tools.block_id\n      inputParameters:\n      - name: block_id\n        type: string\n        description: The ID of the block to append children to. This can be a page ID to add content to a page.\n        required: true\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: listusers\n      description: Notion List all users\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.listusers\n      with:\n        start_cursor: tools.start_cursor\n        page_size: tools.page_size\n      inputParameters:\n      - name: start_cursor\n        type: string\n        description: Pagination cursor to continue fetching results.\n      - name: page_size\n        type: integer\n        description: Maximum number of users to return (max 100).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveuser\n      description: Notion Retrieve a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrieveuser\n      with:\n        user_id: tools.user_id\n      inputParameters:\n      - name: user_id\n        type: string\n        description: The ID of the user to retrieve.\n        required: true\n  \
  \    outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievebotuser\n      description: Notion Retrieve the bot user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.retrievebotuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search\n      description: Notion Search by title\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.search\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcomments\n      description: Notion Retrieve comments\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: notion.listcomments\n      with:\n        block_id: tools.block_id\n        start_cursor: tools.start_cursor\n        page_size: tools.page_size\n      inputParameters:\n      - name: block_id\n        type: string\n        description:\
  \ The ID of the block or page to retrieve comments for.\n        required: true\n      - name: start_cursor\n        type: string\n        description: Pagination cursor to continue fetching results.\n      - name: page_size\n        type: integer\n        description: Maximum number of comments to return (max 100).\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcomment\n      description: Notion Create a comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: notion.createcomment\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    NOTION_TOKEN: NOTION_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/notion/refs/heads/main/capabilities/notion-capability.yaml
tags:
- Notion
- API
tools:
- description: Notion Create a page
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpage
- description: Notion Retrieve a page
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievepage
- description: Notion Update page properties
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatepage
- description: Notion Retrieve a page property item
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievepageproperty
- description: Notion Create a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdatabase
- description: Notion Retrieve a database
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievedatabase
- description: Notion Update a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedatabase
- description: Notion Query a database
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: querydatabase
- description: Notion Retrieve a block
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveblock
- description: Notion Update a block
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateblock
- description: Notion Delete a block
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteblock
- description: Notion Retrieve block children
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveblockchildren
- description: Notion Append block children
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: appendblockchildren
- description: Notion List all users
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusers
- description: Notion Retrieve a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveuser
- description: Notion Retrieve the bot user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievebotuser
- description: Notion Search by title
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: search
- description: Notion Retrieve comments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcomments
- description: Notion Create a comment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcomment
---
