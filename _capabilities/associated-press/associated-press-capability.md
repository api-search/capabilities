---
categories: []
consumed_apis: []
description: AP's next generation content API.
layout: capability
name: Associated Press AP Media API
operations:
- description: Associated Press Single item metadata lookup
  method: GET
  name: get-content-item-id
  path: /content/{item_id}
- description: Associated Press Search for AP content
  method: GET
  name: get-content-search
  path: /content/search
- description: Associated Press Receive a feed of incoming AP content
  method: GET
  name: get-content-feed
  path: /content/feed
- description: Associated Press Retrieve a list of available RSS XML feeds entitled to your plan.
  method: GET
  name: get-content-rss
  path: /content/rss
- description: Associated Press Receive a RSS feed of latest AP content
  method: GET
  name: get-content-rss-rss-id
  path: /content/rss/{rss_id}
- description: Associated Press Receive a feed of AP content items which have been sent to your organization's OnDemand queue.
  method: GET
  name: get-content-ondemand
  path: /content/ondemand
- description: Associated Press View available account endpoints
  method: GET
  name: get-account
  path: /account
- description: Associated Press View your Followed Topics
  method: GET
  name: get-account-followedtopics
  path: /account/followedtopics
- description: Associated Press View your plans and meters
  method: GET
  name: get-account-plans
  path: /account/plans
- description: Associated Press View your order history.
  method: GET
  name: get-account-downloads
  path: /account/downloads
- description: Associated Press View your API request limits.
  method: GET
  name: get-account-quotas
  path: /account/quotas
- description: Associated Press Create a new Monitor
  method: POST
  name: post-account-monitors-create
  path: /account/monitors/create
- description: Associated Press Update a Monitor
  method: POST
  name: post-account-monitors-monitorid-update
  path: /account/monitors/{monitorId}/update
- description: Associated Press Delete a Monitor
  method: DELETE
  name: delete-account-monitors-monitorid-delete
  path: /account/monitors/{monitorId}/delete
- description: Associated Press List your Monitors. (formerly /account/monitors/get)
  method: GET
  name: get-account-monitors
  path: /account/monitors
- description: Associated Press View one Monitor
  method: GET
  name: get-account-monitors-monitorid
  path: /account/monitors/{monitorId}
- description: Associated Press View recent Alerts
  method: GET
  name: get-account-monitors-alerts
  path: /account/monitors/alerts
- description: Associated Press View recent Sessions that have Monitors.
  method: GET
  name: get-account-monitors-sessions
  path: /account/monitors/sessions
- description: Associated Press View one Session
  method: GET
  name: get-account-monitors-sessions-session-id
  path: /account/monitors/sessions/{session_id}
- description: Associated Press Disable a Monitor on a Session
  method: GET
  name: get-account-monitors-sessions-session-id-disable
  path: /account/monitors/sessions/{session_id}/disable
- description: Associated Press Enable a Monitor on a Session
  method: GET
  name: get-account-monitors-sessions-session-id-enable
  path: /account/monitors/sessions/{session_id}/enable
personas: []
provider_name: Associated Press
provider_slug: associated-press
search_terms:
- get account monitors alerts
- get account monitors sessions session id enable
- get account downloads
- associated
- associated press list your monitors. (formerly /account/monitors/get)
- associated press view recent sessions that have monitors.
- get account monitors sessions session id disable
- associated press single item metadata lookup
- get content rss
- associated press view your followed topics
- get account quotas
- content
- get account monitors sessions session id
- associated press receive a feed of ap content items which have been sent to your organization's ondemand queue.
- associated press view recent alerts
- press
- associated press view one session
- associated press delete a monitor
- post account monitors monitorid update
- elections
- get account monitors sessions
- get account monitors monitorid
- associated press enable a monitor on a session
- news
- associated press view your api request limits.
- post account monitors create
- api
- associated press receive a feed of incoming ap content
- get content ondemand
- get content item id
- get account plans
- associated press create a new monitor
- associated press retrieve a list of available rss xml feeds entitled to your plan.
- journalism
- media
- associated press view your order history.
- associated press disable a monitor on a session
- get content feed
- associated press search for ap content
- get account monitors
- get account followedtopics
- associated press view one monitor
- associated press view your plans and meters
- associated press receive a rss feed of latest ap content
- get account
- delete account monitors monitorid delete
- get content search
- get content rss rss id
- associated press update a monitor
- associated press view available account endpoints
slug: associated-press-capability
source_filename: associated-press-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Associated Press AP Media API\n  description: AP's next generation content API.\n  tags:\n  - Associated\n  - Press\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: associated-press\n    baseUri: //api.ap.org/media/v\n    description: Associated Press AP Media API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{ASSOCIATED_PRESS_TOKEN}}'\n    resources:\n    - name: content-item-id\n      path: /content/{item_id}\n      operations:\n      - name: get-content-item-id\n        method: GET\n        description: Associated Press Single item metadata lookup\n        inputParameters:\n        - name: item_id\n          in: path\n          type: string\n          required: true\n          description: The itemid of the desired piece of content\n        - name: include\n          in: query\n          type: array\n  \
  \        description: Comma separated list of fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: pricing\n          in: query\n          type: boolean\n          description: Whether to include pricing information with the results\n        - name: in_my_plan\n          in: query\n          type: boolean\n          description: Specifying in_my_plan=true in the request returns only those associations of the content item that\n            do not incur any additional cost to download.\n        - name: format\n          in: query\n          type: string\n          description: The desired response format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-search\n      path: /content/search\n      operations:\n      - name: get-content-search\n\
  \        method: GET\n        description: Associated Press Search for AP content\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Your query\n        - name: include\n          in: query\n          type: array\n          description: Comma separated list of fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: sort\n          in: query\n          type: string\n          description: Your desired sorting criteria\n        - name: page\n          in: query\n          type: string\n          description: The desired page number. Page numbers begin at 1\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items to return per page\n        - name: pricing\n          in: query\n          type: boolean\n          description:\
  \ Whether to include pricing information with the results\n        - name: in_my_plan\n          in: query\n          type: boolean\n          description: Specifying in_my_plan=true in the request returns only those items that do not incur additional cost\n            to download. Additionally, items returned include only thos\n        - name: session_label\n          in: query\n          type: string\n          description: Attach an informational label to this session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-feed\n      path: /content/feed\n      operations:\n      - name: get-content-feed\n        method: GET\n        description: Associated Press Receive a feed of incoming AP content\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: Your query\n        - name: include\n          in: query\n          type: array\n\
  \          description: Comma separated list of fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items to return per page\n        - name: pricing\n          in: query\n          type: boolean\n          description: Whether to include pricing information with the results\n        - name: in_my_plan\n          in: query\n          type: boolean\n          description: Specifying in_my_plan=true in the request returns only those items that do not incur additional cost\n            to download. Additionally, items returned include only thos\n        - name: with_monitor\n          in: query\n          type: string\n          description: Apply the named Monitor to subsequent calls for this session\n        - name: session_label\n          in: query\n\
  \          type: string\n          description: Attach an informational label to this session\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-rss\n      path: /content/rss\n      operations:\n      - name: get-content-rss\n        method: GET\n        description: Associated Press Retrieve a list of available RSS XML feeds entitled to your plan.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-rss-rss-id\n      path: /content/rss/{rss_id}\n      operations:\n      - name: get-content-rss-rss-id\n        method: GET\n        description: Associated Press Receive a RSS feed of latest AP content\n        inputParameters:\n        - name: rss_id\n          in: path\n          type: integer\n          required: true\n          description: The product ID for the desired RSS feed (see /content/rss)\n\
  \        - name: include\n          in: query\n          type: array\n          description: Comma separated list of fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items to return per page\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: content-ondemand\n      path: /content/ondemand\n      operations:\n      - name: get-content-ondemand\n        method: GET\n        description: Associated Press Receive a feed of AP content items which have been sent to your organization's OnDemand\n          queue.\n        inputParameters:\n        - name: consumer_id\n          in: query\n          type: string\n          description: A user defined identifier for\
  \ the consumer of this feed. Each unique consumer ID will receive every\n            item in your organization's OnDemand queue once. If not spec\n        - name: queue\n          in: query\n          type: string\n          description: The ID of the desired queue.\n        - name: include\n          in: query\n          type: array\n          description: Comma separated list of fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: page_size\n          in: query\n          type: integer\n          description: Number of items to return per page\n        - name: pricing\n          in: query\n          type: boolean\n          description: Whether to include pricing information with the results\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account\n\
  \      path: /account\n      operations:\n      - name: get-account\n        method: GET\n        description: Associated Press View available account endpoints\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-followedtopics\n      path: /account/followedtopics\n      operations:\n      - name: get-account-followedtopics\n        method: GET\n        description: Associated Press View your Followed Topics\n        inputParameters:\n        - name: format\n          in: query\n          type: string\n          description: '''json'' is the default. Use ''csv'' for simplified CSV output/download.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-plans\n      path: /account/plans\n      operations:\n      - name: get-account-plans\n        method: GET\n        description: Associated Press View\
  \ your plans and meters\n        inputParameters:\n        - name: include\n          in: query\n          type: array\n          description: Comma separated list of fields to include from the response.\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response.\n        - name: format\n          in: query\n          type: string\n          description: '''json'' is the default. Use ''csv'' for simplified CSV output/download.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-downloads\n      path: /account/downloads\n      operations:\n      - name: get-account-downloads\n        method: GET\n        description: Associated Press View your order history.\n        inputParameters:\n        - name: include\n          in: query\n          type: array\n          description: Comma separated list of\
  \ fields to include from the response\n        - name: exclude\n          in: query\n          type: array\n          description: Comma separated list of fields to exclude from the response\n        - name: min_date\n          in: query\n          type: string\n          description: The date and time after which the content items were downloaded, in the format YYYY-MM-DD(THH:mm:ss)\n            or YYYY-MM. The default is 30 days prior to the time of the\n        - name: max_date\n          in: query\n          type: string\n          description: The date and time before which the content items were downloaded, in the format YYYY-MM-DD(THH:mm:ss)\n            or YYYY-MM. The default is the time of the request.\n        - name: order\n          in: query\n          type: integer\n          description: The ID of the desired order to return. The correct date-range must be provided.\n        - name: format\n          in: query\n          type: string\n          description: '''json'' is\
  \ the default. Use ''csv'' for simplified CSV output/download'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-quotas\n      path: /account/quotas\n      operations:\n      - name: get-account-quotas\n        method: GET\n        description: Associated Press View your API request limits.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-create\n      path: /account/monitors/create\n      operations:\n      - name: post-account-monitors-create\n        method: POST\n        description: Associated Press Create a new Monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-monitorid-update\n      path: /account/monitors/{monitorId}/update\n      operations:\n      - name: post-account-monitors-monitorid-update\n\
  \        method: POST\n        description: Associated Press Update a Monitor\n        inputParameters:\n        - name: monitorId\n          in: path\n          type: string\n          required: true\n          description: The unique name or ID of the Monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-monitorid-delete\n      path: /account/monitors/{monitorId}/delete\n      operations:\n      - name: delete-account-monitors-monitorid-delete\n        method: DELETE\n        description: Associated Press Delete a Monitor\n        inputParameters:\n        - name: monitorId\n          in: path\n          type: string\n          required: true\n          description: The unique name or ID of the Monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors\n      path: /account/monitors\n\
  \      operations:\n      - name: get-account-monitors\n        method: GET\n        description: Associated Press List your Monitors. (formerly /account/monitors/get)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-monitorid\n      path: /account/monitors/{monitorId}\n      operations:\n      - name: get-account-monitors-monitorid\n        method: GET\n        description: Associated Press View one Monitor\n        inputParameters:\n        - name: monitorId\n          in: path\n          type: string\n          required: true\n          description: The unique name or ID of the desired Monitor\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-alerts\n      path: /account/monitors/alerts\n      operations:\n      - name: get-account-monitors-alerts\n        method: GET\n \
  \       description: Associated Press View recent Alerts\n        inputParameters:\n        - name: show_detail\n          in: query\n          type: boolean\n          description: Return full details of Monitors and latest Alert\n        - name: agentid\n          in: query\n          type: string\n          description: Constrain operation to one Agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-sessions\n      path: /account/monitors/sessions\n      operations:\n      - name: get-account-monitors-sessions\n        method: GET\n        description: Associated Press View recent Sessions that have Monitors.\n        inputParameters:\n        - name: show_detail\n          in: query\n          type: boolean\n          description: Return full details of Monitors and latest Alert\n        - name: agentid\n          in: query\n          type: string\n          description: Constrain\
  \ operation to one Agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-sessions-session-id\n      path: /account/monitors/sessions/{session_id}\n      operations:\n      - name: get-account-monitors-sessions-session-id\n        method: GET\n        description: Associated Press View one Session\n        inputParameters:\n        - name: session_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID for a Session\n        - name: show_detail\n          in: query\n          type: boolean\n          description: Return full details of Monitors and latest Alert\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-sessions-session-id-disable\n      path: /account/monitors/sessions/{session_id}/disable\n      operations:\n  \
  \    - name: get-account-monitors-sessions-session-id-disable\n        method: GET\n        description: Associated Press Disable a Monitor on a Session\n        inputParameters:\n        - name: session_id\n          in: path\n          type: string\n          required: true\n          description: The unique ID for a Session\n        - name: agentid\n          in: query\n          type: string\n          description: Constrain operation to one Agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-monitors-sessions-session-id-enable\n      path: /account/monitors/sessions/{session_id}/enable\n      operations:\n      - name: get-account-monitors-sessions-session-id-enable\n        method: GET\n        description: Associated Press Enable a Monitor on a Session\n        inputParameters:\n        - name: session_id\n          in: path\n          type: string\n          required: true\n  \
  \        description: The unique ID for a Session\n        - name: agentid\n          in: query\n          type: string\n          description: Constrain operation to one Agent\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: associated-press-rest\n    description: REST adapter for Associated Press AP Media API.\n    resources:\n    - path: /content/{item_id}\n      name: get-content-item-id\n      operations:\n      - method: GET\n        name: get-content-item-id\n        description: Associated Press Single item metadata lookup\n        call: associated-press.get-content-item-id\n        with:\n          item_id: rest.item_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/search\n      name: get-content-search\n      operations:\n      - method: GET\n        name: get-content-search\n        description:\
  \ Associated Press Search for AP content\n        call: associated-press.get-content-search\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/feed\n      name: get-content-feed\n      operations:\n      - method: GET\n        name: get-content-feed\n        description: Associated Press Receive a feed of incoming AP content\n        call: associated-press.get-content-feed\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/rss\n      name: get-content-rss\n      operations:\n      - method: GET\n        name: get-content-rss\n        description: Associated Press Retrieve a list of available RSS XML feeds entitled to your plan.\n        call: associated-press.get-content-rss\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/rss/{rss_id}\n      name: get-content-rss-rss-id\n      operations:\n      - method: GET\n        name: get-content-rss-rss-id\n \
  \       description: Associated Press Receive a RSS feed of latest AP content\n        call: associated-press.get-content-rss-rss-id\n        with:\n          rss_id: rest.rss_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /content/ondemand\n      name: get-content-ondemand\n      operations:\n      - method: GET\n        name: get-content-ondemand\n        description: Associated Press Receive a feed of AP content items which have been sent to your organization's OnDemand\n          queue.\n        call: associated-press.get-content-ondemand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account\n      name: get-account\n      operations:\n      - method: GET\n        name: get-account\n        description: Associated Press View available account endpoints\n        call: associated-press.get-account\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/followedtopics\n\
  \      name: get-account-followedtopics\n      operations:\n      - method: GET\n        name: get-account-followedtopics\n        description: Associated Press View your Followed Topics\n        call: associated-press.get-account-followedtopics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/plans\n      name: get-account-plans\n      operations:\n      - method: GET\n        name: get-account-plans\n        description: Associated Press View your plans and meters\n        call: associated-press.get-account-plans\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/downloads\n      name: get-account-downloads\n      operations:\n      - method: GET\n        name: get-account-downloads\n        description: Associated Press View your order history.\n        call: associated-press.get-account-downloads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/quotas\n\
  \      name: get-account-quotas\n      operations:\n      - method: GET\n        name: get-account-quotas\n        description: Associated Press View your API request limits.\n        call: associated-press.get-account-quotas\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/create\n      name: post-account-monitors-create\n      operations:\n      - method: POST\n        name: post-account-monitors-create\n        description: Associated Press Create a new Monitor\n        call: associated-press.post-account-monitors-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/{monitorId}/update\n      name: post-account-monitors-monitorid-update\n      operations:\n      - method: POST\n        name: post-account-monitors-monitorid-update\n        description: Associated Press Update a Monitor\n        call: associated-press.post-account-monitors-monitorid-update\n        with:\n\
  \          monitorId: rest.monitorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/{monitorId}/delete\n      name: delete-account-monitors-monitorid-delete\n      operations:\n      - method: DELETE\n        name: delete-account-monitors-monitorid-delete\n        description: Associated Press Delete a Monitor\n        call: associated-press.delete-account-monitors-monitorid-delete\n        with:\n          monitorId: rest.monitorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors\n      name: get-account-monitors\n      operations:\n      - method: GET\n        name: get-account-monitors\n        description: Associated Press List your Monitors. (formerly /account/monitors/get)\n        call: associated-press.get-account-monitors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/{monitorId}\n      name: get-account-monitors-monitorid\n\
  \      operations:\n      - method: GET\n        name: get-account-monitors-monitorid\n        description: Associated Press View one Monitor\n        call: associated-press.get-account-monitors-monitorid\n        with:\n          monitorId: rest.monitorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/alerts\n      name: get-account-monitors-alerts\n      operations:\n      - method: GET\n        name: get-account-monitors-alerts\n        description: Associated Press View recent Alerts\n        call: associated-press.get-account-monitors-alerts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/sessions\n      name: get-account-monitors-sessions\n      operations:\n      - method: GET\n        name: get-account-monitors-sessions\n        description: Associated Press View recent Sessions that have Monitors.\n        call: associated-press.get-account-monitors-sessions\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/sessions/{session_id}\n      name: get-account-monitors-sessions-session-id\n      operations:\n      - method: GET\n        name: get-account-monitors-sessions-session-id\n        description: Associated Press View one Session\n        call: associated-press.get-account-monitors-sessions-session-id\n        with:\n          session_id: rest.session_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /account/monitors/sessions/{session_id}/disable\n      name: get-account-monitors-sessions-session-id-disable\n      operations:\n      - method: GET\n        name: get-account-monitors-sessions-session-id-disable\n        description: Associated Press Disable a Monitor on a Session\n        call: associated-press.get-account-monitors-sessions-session-id-disable\n        with:\n          session_id: rest.session_id\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /account/monitors/sessions/{session_id}/enable\n      name: get-account-monitors-sessions-session-id-enable\n      operations:\n      - method: GET\n        name: get-account-monitors-sessions-session-id-enable\n        description: Associated Press Enable a Monitor on a Session\n        call: associated-press.get-account-monitors-sessions-session-id-enable\n        with:\n          session_id: rest.session_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: associated-press-mcp\n    transport: http\n    description: MCP adapter for Associated Press AP Media API for AI agent use.\n    tools:\n    - name: get-content-item-id\n      description: Associated Press Single item metadata lookup\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: associated-press.get-content-item-id\n      with:\n        item_id: tools.item_id\n\
  \        include: tools.include\n        exclude: tools.exclude\n        pricing: tools.pricing\n        in_my_plan: tools.in_my_plan\n        format: tools.format\n      inputParameters:\n      - name: item_id\n        type: string\n        description: The itemid of the desired piece of content\n        required: true\n      - name: include\n        type: array\n        description: Comma separated list of fields to include from the response\n      - name: exclude\n        type: array\n        description: Comma separated list of fields to exclude from the response\n      - name: pricing\n        type: boolean\n        description: Whether to include pricing information with the results\n      - name: in_my_plan\n        type: boolean\n        description: Specifying in_my_plan=true in the request returns only those associations of the content item that do\n          not incur any additional cost to download.\n      - name: format\n        type: string\n        description: The desired\
  \ response format\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-search\n      description: Associated Press Search for AP content\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: associated-press.get-content-search\n      with:\n        q: tools.q\n        include: tools.include\n        exclude: tools.exclude\n        sort: tools.sort\n        page: tools.page\n        page_size: tools.page_size\n        pricing: tools.pricing\n        in_my_plan: tools.in_my_plan\n        session_label: tools.session_label\n      inputParameters:\n      - name: q\n        type: string\n        description: Your query\n      - name: include\n        type: array\n        description: Comma separated list of fields to include from the response\n      - name: exclude\n        type: array\n        description: Comma separated list of fields to exclude from the response\n      - name: sort\n        type:\
  \ string\n        description: Your desired sorting criteria\n      - name: page\n        type: string\n        description: The desired page number. Page numbers begin at 1\n      - name: page_size\n        type: integer\n        description: Number of items to return per page\n      - name: pricing\n        type: boolean\n        description: Whether to include pricing information with the results\n      - name: in_my_plan\n        type: boolean\n        description: Specifying in_my_plan=true in the request returns only those items that do not incur additional cost\n          to download. Additionally, items returned include only thos\n      - name: session_label\n        type: string\n        description: Attach an informational label to this session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-feed\n      description: Associated Press Receive a feed of incoming AP content\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: associated-press.get-content-feed\n      with:\n        q: tools.q\n        include: tools.include\n        exclude: tools.exclude\n        page_size: tools.page_size\n        pricing: tools.pricing\n        in_my_plan: tools.in_my_plan\n        with_monitor: tools.with_monitor\n        session_label: tools.session_label\n      inputParameters:\n      - name: q\n        type: string\n        description: Your query\n      - name: include\n        type: array\n        description: Comma separated list of fields to include from the response\n      - name: exclude\n        type: array\n        description: Comma separated list of fields to exclude from the response\n      - name: page_size\n        type: integer\n        description: Number of items to return per page\n      - name: pricing\n        type: boolean\n        description: Whether to include pricing information with the results\n      - name: in_my_plan\n        type: boolean\n        description:\
  \ Specifying in_my_plan=true in the request returns only those items that do not incur additional cost\n          to download. Additionally, items returned include only thos\n      - name: with_monitor\n        type: string\n        description: Apply the named Monitor to subsequent calls for this session\n      - name: session_label\n        type: string\n        description: Attach an informational label to this session\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-rss\n      description: Associated Press Retrieve a list of available RSS XML feeds entitled to your plan.\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: associated-press.get-content-rss\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-rss-rss-id\n      description: Associated Press Receive a RSS feed of latest AP content\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: associated-press.get-content-rss-rss-id\n      with:\n        rss_id: tools.rss_id\n        include: tools.include\n        exclude: tools.exclude\n        page_size: tools.page_size\n      inputParameters:\n      - name: rss_id\n        type: integer\n        description: The product ID for the desired RSS feed (see /content/rss)\n        required: true\n      - name: include\n        type: array\n        description: Comma separated list of fields to include from the response\n      - name: exclude\n        type: array\n        description: Comma separated list of fields to exclude from the response\n      - name: page_size\n        type: integer\n        description: Number of items to return per page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-content-ondemand\n      description: Associated Press Receive a feed of AP content items which have been sent to your organization's OnDemand\n        queue.\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: associated-press.get-content-ondemand\n      with:\n        consumer_id: tools.consumer_id\n        queue: tools.queue\n        include: tools.include\n        exclude: tools.exclude\n        page_size: tools.page_size\n        pricing: tools.pricing\n      inputParameters:\n      - name: consumer_id\n        type: string\n        description: A user defined identifier for the consumer of this feed. Each unique consumer ID will receive every item\n          in your organization's OnDemand queue once. If not spec\n      - name: queue\n        type: string\n        description: The ID of the desired queue.\n      - name: include\n        type: array\n        description: Comma separated list of fields to include from the response\n      - name: exclude\n        type: array\n        description: Comma separated list of fields to exclude from the response\n      - name: page_size\n    \
  \    type: integer\n        description: Number of items to return per page\n      - name: pricing\n        type: boolean\n        description: Whether to include pricing information with the results\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account\n      description: Associated Press View available account endpoints\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: associated-press.get-account\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-account-followedtopics\n      description: Associated Press View y\n\n# --- truncated at 32 KB (40 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/associated-press/refs/heads/main/capabilities/associated-press-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/associated-press/refs/heads/main/capabilities/associated-press-capability.yaml
tags:
- Associated
- Press
- API
tools:
- description: Associated Press Single item metadata lookup
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-item-id
- description: Associated Press Search for AP content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-search
- description: Associated Press Receive a feed of incoming AP content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-feed
- description: Associated Press Retrieve a list of available RSS XML feeds entitled to your plan.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-rss
- description: Associated Press Receive a RSS feed of latest AP content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-rss-rss-id
- description: Associated Press Receive a feed of AP content items which have been sent to your organization's OnDemand queue.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-content-ondemand
- description: Associated Press View available account endpoints
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account
- description: Associated Press View your Followed Topics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-followedtopics
- description: Associated Press View your plans and meters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-plans
- description: Associated Press View your order history.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-downloads
- description: Associated Press View your API request limits.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-quotas
- description: Associated Press Create a new Monitor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-account-monitors-create
- description: Associated Press Update a Monitor
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-account-monitors-monitorid-update
- description: Associated Press Delete a Monitor
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-account-monitors-monitorid-delete
- description: Associated Press List your Monitors. (formerly /account/monitors/get)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors
- description: Associated Press View one Monitor
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-monitorid
- description: Associated Press View recent Alerts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-alerts
- description: Associated Press View recent Sessions that have Monitors.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-sessions
- description: Associated Press View one Session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-sessions-session-id
- description: Associated Press Disable a Monitor on a Session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-sessions-session-id-disable
- description: Associated Press Enable a Monitor on a Session
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-account-monitors-sessions-session-id-enable
---
