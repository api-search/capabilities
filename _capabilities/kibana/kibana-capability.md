---
categories: []
consumed_apis: []
description: 'The Kibana REST APIs enable you to manage resources such as connectors, data views, and saved objects. The API calls are stateless. Each request that you make happens in isolation from other calls and must include all of the necessary information for Kibana to fulfill the request. API requests return JSON output, which is a format that is machine-readable and works well for automation. To interact with Kibana APIs, use the following operations: - GET: Fetches the information. - PATCH: Applies partial modifications to the existing information. - POST: Adds new information. - PUT: Updates the ex'
layout: capability
name: Kibana APIs
operations:
- description: Get connector types
  method: GET
  name: get-actions-connector-types
  path: /api/actions/connector_types
- description: Handle OAuth callback
  method: GET
  name: get-actions-connector-oauth-callback
  path: /api/actions/connector/_oauth_callback
- description: '**Spaces method and path for this operation:** <div><span class="operation-verb get">get</span>&nbsp;<span class="operation-path">/s/{space_id}/api/actions/connector/_oauth_callback_script</span></div> Refer to [Spaces](https://www.elastic.'
  method: GET
  name: get-actions-connector-oauth-callback-script
  path: /api/actions/connector/_oauth_callback_script
- description: Delete a connector
  method: DELETE
  name: delete-actions-connector-id
  path: /api/actions/connector/{id}
- description: Get connector information
  method: GET
  name: get-actions-connector-id
  path: /api/actions/connector/{id}
- description: Create a connector
  method: POST
  name: post-actions-connector-id
  path: /api/actions/connector/{id}
- description: Update a connector
  method: PUT
  name: put-actions-connector-id
  path: /api/actions/connector/{id}
- description: Run a connector
  method: POST
  name: post-actions-connector-id-execute
  path: /api/actions/connector/{id}/_execute
- description: Get all connectors
  method: GET
  name: get-actions-connectors
  path: /api/actions/connectors
- description: Send A2A task
  method: POST
  name: post-agent-builder-a2a-agentid
  path: /api/agent_builder/a2a/{agentId}
- description: Get A2A agent card
  method: GET
  name: get-agent-builder-a2a-agentid-json
  path: /api/agent_builder/a2a/{agentId}.json
- description: List agents
  method: GET
  name: get-agent-builder-agents
  path: /api/agent_builder/agents
- description: Create an agent
  method: POST
  name: post-agent-builder-agents
  path: /api/agent_builder/agents
- description: Get agent consumption data
  method: POST
  name: post-agent-builder-agents-agent-id-consumption
  path: /api/agent_builder/agents/{agent_id}/consumption
- description: Delete an agent
  method: DELETE
  name: delete-agent-builder-agents-id
  path: /api/agent_builder/agents/{id}
- description: Get an agent by ID
  method: GET
  name: get-agent-builder-agents-id
  path: /api/agent_builder/agents/{id}
- description: Update an agent
  method: PUT
  name: put-agent-builder-agents-id
  path: /api/agent_builder/agents/{id}
- description: List conversations
  method: GET
  name: get-agent-builder-conversations
  path: /api/agent_builder/conversations
- description: Delete conversation by ID
  method: DELETE
  name: delete-agent-builder-conversations-conversation-
  path: /api/agent_builder/conversations/{conversation_id}
- description: Get conversation by ID
  method: GET
  name: get-agent-builder-conversations-conversation-id
  path: /api/agent_builder/conversations/{conversation_id}
- description: List conversation attachments
  method: GET
  name: get-agent-builder-conversations-conversation-id-
  path: /api/agent_builder/conversations/{conversation_id}/attachments
- description: Create conversation attachment
  method: POST
  name: post-agent-builder-conversations-conversation-id
  path: /api/agent_builder/conversations/{conversation_id}/attachments
- description: Delete conversation attachment
  method: DELETE
  name: delete-agent-builder-conversations-conversation-
  path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}
- description: Rename attachment
  method: PATCH
  name: patch-agent-builder-conversations-conversation-i
  path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}
- description: Update conversation attachment
  method: PUT
  name: put-agent-builder-conversations-conversation-id-
  path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}
- description: Restore deleted attachment
  method: POST
  name: post-agent-builder-conversations-conversation-id
  path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}/_restore
- description: Update attachment origin
  method: PUT
  name: put-agent-builder-conversations-conversation-id-
  path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}/origin
- description: Check attachment staleness
  method: GET
  name: get-agent-builder-conversations-conversation-id-
  path: /api/agent_builder/conversations/{conversation_id}/attachments/stale
- description: Send chat message
  method: POST
  name: post-agent-builder-converse
  path: /api/agent_builder/converse
- description: Send chat message (streaming)
  method: POST
  name: post-agent-builder-converse-async
  path: /api/agent_builder/converse/async
- description: MCP server
  method: POST
  name: post-agent-builder-mcp
  path: /api/agent_builder/mcp
- description: List plugins
  method: GET
  name: get-agent-builder-plugins
  path: /api/agent_builder/plugins
- description: Delete a plugin
  method: DELETE
  name: delete-agent-builder-plugins-pluginid
  path: /api/agent_builder/plugins/{pluginId}
- description: Get a plugin by id
  method: GET
  name: get-agent-builder-plugins-pluginid
  path: /api/agent_builder/plugins/{pluginId}
- description: Install a plugin
  method: POST
  name: post-agent-builder-plugins-install
  path: /api/agent_builder/plugins/install
- description: List skills
  method: GET
  name: get-agent-builder-skills
  path: /api/agent_builder/skills
- description: Create a skill
  method: POST
  name: post-agent-builder-skills
  path: /api/agent_builder/skills
- description: Delete a skill
  method: DELETE
  name: delete-agent-builder-skills-skillid
  path: /api/agent_builder/skills/{skillId}
- description: Get a skill by id
  method: GET
  name: get-agent-builder-skills-skillid
  path: /api/agent_builder/skills/{skillId}
- description: Update a skill
  method: PUT
  name: put-agent-builder-skills-skillid
  path: /api/agent_builder/skills/{skillId}
- description: List tools
  method: GET
  name: get-agent-builder-tools
  path: /api/agent_builder/tools
- description: Create a tool
  method: POST
  name: post-agent-builder-tools
  path: /api/agent_builder/tools
- description: Run a tool
  method: POST
  name: post-agent-builder-tools-execute
  path: /api/agent_builder/tools/_execute
- description: Delete a tool
  method: DELETE
  name: delete-agent-builder-tools-toolid
  path: /api/agent_builder/tools/{toolId}
- description: Get a tool by id
  method: GET
  name: get-agent-builder-tools-toolid
  path: /api/agent_builder/tools/{toolId}
- description: Update a tool
  method: PUT
  name: put-agent-builder-tools-toolid
  path: /api/agent_builder/tools/{toolId}
- description: Get the alerting framework health
  method: GET
  name: getalertinghealth
  path: /api/alerting/_health
- description: Get the rule types
  method: GET
  name: getruletypes
  path: /api/alerting/rule_types
- description: Delete a rule
  method: DELETE
  name: delete-alerting-rule-id
  path: /api/alerting/rule/{id}
- description: Get rule details
  method: GET
  name: get-alerting-rule-id
  path: /api/alerting/rule/{id}
- description: Create a rule
  method: POST
  name: post-alerting-rule-id
  path: /api/alerting/rule/{id}
- description: Update a rule
  method: PUT
  name: put-alerting-rule-id
  path: /api/alerting/rule/{id}
- description: Disable a rule
  method: POST
  name: post-alerting-rule-id-disable
  path: /api/alerting/rule/{id}/_disable
- description: Enable a rule
  method: POST
  name: post-alerting-rule-id-enable
  path: /api/alerting/rule/{id}/_enable
- description: Mute all alerts
  method: POST
  name: post-alerting-rule-id-mute-all
  path: /api/alerting/rule/{id}/_mute_all
- description: Unmute all alerts
  method: POST
  name: post-alerting-rule-id-unmute-all
  path: /api/alerting/rule/{id}/_unmute_all
- description: Update the API key for a rule
  method: POST
  name: post-alerting-rule-id-update-api-key
  path: /api/alerting/rule/{id}/_update_api_key
- description: Schedule a snooze for the rule
  method: POST
  name: post-alerting-rule-id-snooze-schedule
  path: /api/alerting/rule/{id}/snooze_schedule
- description: Mute an alert
  method: POST
  name: post-alerting-rule-rule-id-alert-alert-id-mute
  path: /api/alerting/rule/{rule_id}/alert/{alert_id}/_mute
- description: Unmute an alert
  method: POST
  name: post-alerting-rule-rule-id-alert-alert-id-unmute
  path: /api/alerting/rule/{rule_id}/alert/{alert_id}/_unmute
personas: []
provider_name: Kibana
provider_slug: kibana
search_terms:
- get alerting rule id
- delete a rule
- api
- get agent builder conversations conversation id
- put agent builder tools toolid
- get an agent by id
- delete a connector
- update a connector
- put alerting rule id
- enable a rule
- mute all alerts
- get connector types
- post alerting rule id update api key
- post alerting rule rule id alert alert id unmute
- post agent builder agents
- create a connector
- post agent builder a2a agentid
- patch agent builder conversations conversation i
- get agent builder tools toolid
- kibana
- getalertinghealth
- delete conversation attachment
- get agent builder conversations
- update a tool
- get a plugin by id
- send chat message (streaming)
- alerting
- post agent builder mcp
- post alerting rule id mute all
- visualization
- unmute an alert
- run a connector
- list plugins
- post alerting rule id unmute all
- restore deleted attachment
- put agent builder agents id
- get actions connectors
- send a2a task
- get the rule types
- run a tool
- get actions connector oauth callback script
- delete a tool
- list conversations
- install a plugin
- update an agent
- update the api key for a rule
- send chat message
- get the alerting framework health
- elastic stack
- put agent builder skills skillid
- delete agent builder plugins pluginid
- get actions connector id
- get a tool by id
- list agents
- post agent builder converse async
- logging
- get conversation by id
- put agent builder conversations conversation id
- get actions connector oauth callback
- get agent builder skills skillid
- update conversation attachment
- get agent builder skills
- delete a plugin
- delete a skill
- post agent builder plugins install
- delete an agent
- list tools
- monitoring
- post actions connector id execute
- get connector information
- delete conversation by id
- update a skill
- observability
- disable a rule
- unmute all alerts
- get rule details
- get a skill by id
- create a skill
- delete agent builder agents id
- post agent builder conversations conversation id
- get agent builder a2a agentid json
- list conversation attachments
- post agent builder skills
- schedule a snooze for the rule
- get actions connector types
- analytics
- mute an alert
- post alerting rule id
- post agent builder converse
- post alerting rule id disable
- post agent builder tools
- rename attachment
- get a2a agent card
- delete agent builder skills skillid
- mcp server
- get agent builder plugins pluginid
- create an agent
- put actions connector id
- handle oauth callback
- post agent builder tools execute
- post actions connector id
- getruletypes
- post agent builder agents agent id consumption
- delete agent builder conversations conversation
- get agent builder tools
- '**spaces method and path for this operation:** <div><span class="operation-verb get">get</span>&nbsp;<span class="operation-path">/s/{space_id}/api/actions/connector/_oauth_callback_script</span></div> refer to [spaces](https://www.elastic.'
- create a tool
- post alerting rule id enable
- post alerting rule rule id alert alert id mute
- dashboards
- get agent builder conversations conversation id
- update attachment origin
- get all connectors
- post alerting rule id snooze schedule
- get agent consumption data
- get agent builder agents id
- get agent builder plugins
- create a rule
- create conversation attachment
- get agent builder agents
- list skills
- check attachment staleness
- delete alerting rule id
- update a rule
- delete agent builder tools toolid
- delete actions connector id
slug: kibana-capability
source_filename: kibana-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Kibana APIs\n  description: 'The Kibana REST APIs enable you to manage resources such as connectors, data views, and saved objects. The\n    API calls are stateless. Each request that you make happens in isolation from other calls and must include all of the\n    necessary information for Kibana to fulfill the request. API requests return JSON output, which is a format that is machine-readable\n    and works well for automation. To interact with Kibana APIs, use the following operations: - GET: Fetches the information.\n    - PATCH: Applies partial modifications to the existing information. - POST: Adds new information. - PUT: Updates the ex'\n  tags:\n  - Kibana\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: kibana\n    baseUri: https://localhost:5601\n    description: Kibana APIs HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n\
  \      value: '{{KIBANA_TOKEN}}'\n    resources:\n    - name: api-actions-connector-types\n      path: /api/actions/connector_types\n      operations:\n      - name: get-actions-connector-types\n        method: GET\n        description: Get connector types\n        inputParameters:\n        - name: feature_id\n          in: query\n          type: string\n          description: A filter to limit the retrieved connector types to those that support a specific feature (such as alerting\n            or cases).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-actions-connector-oauth-callback\n      path: /api/actions/connector/_oauth_callback\n      operations:\n      - name: get-actions-connector-oauth-callback\n        method: GET\n        description: Handle OAuth callback\n        inputParameters:\n        - name: code\n          in: query\n          type: string\n          description: The authorization\
  \ code returned by the OAuth provider.\n        - name: state\n          in: query\n          type: string\n          description: The state parameter for CSRF protection.\n        - name: error\n          in: query\n          type: string\n          description: Error code if the authorization failed.\n        - name: error_description\n          in: query\n          type: string\n          description: Human-readable error description.\n        - name: session_state\n          in: query\n          type: string\n          description: Session state from the OAuth provider (e.g., Microsoft).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-actions-connector-oauth-callback-script\n      path: /api/actions/connector/_oauth_callback_script\n      operations:\n      - name: get-actions-connector-oauth-callback-script\n        method: GET\n        description: '**Spaces method and path for this operation:**\
  \ <div><span class=\"operation-verb get\">get</span>&nbsp;<span\n          class=\"operation-path\">/s/{space_id}/api/actions/connector/_oauth_callback_script</span></div> Refer to [Spaces](https://www.elastic.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-actions-connector-id\n      path: /api/actions/connector/{id}\n      operations:\n      - name: delete-actions-connector-id\n        method: DELETE\n        description: Delete a connector\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: An identifier for the connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: get-actions-connector-id\n        method: GET\n        description: Get connector information\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: An identifier for the connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-actions-connector-id\n        method: POST\n        description: Create a connector\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: An identifier for the connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: put-actions-connector-id\n        method: PUT\n        description: Update a connector\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: An identifier for the connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-actions-connector-id-execute\n      path: /api/actions/connector/{id}/_execute\n      operations:\n      - name: post-actions-connector-id-execute\n        method: POST\n        description: Run a connector\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n\
  \        - name: id\n          in: path\n          type: string\n          required: true\n          description: An identifier for the connector.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-actions-connectors\n      path: /api/actions/connectors\n      operations:\n      - name: get-actions-connectors\n        method: GET\n        description: Get all connectors\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-a2a-agentid\n      path: /api/agent_builder/a2a/{agentId}\n      operations:\n      - name: post-agent-builder-a2a-agentid\n        method: POST\n        description: Send A2A task\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the agent to send the A2A\
  \ task to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-a2a-agentid-json\n      path: /api/agent_builder/a2a/{agentId}.json\n      operations:\n      - name: get-agent-builder-a2a-agentid-json\n        method: GET\n        description: Get A2A agent card\n        inputParameters:\n        - name: agentId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the agent to get A2A metadata for.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-agents\n      path: /api/agent_builder/agents\n      operations:\n      - name: get-agent-builder-agents\n        method: GET\n        description: List agents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n      - name: post-agent-builder-agents\n        method: POST\n        description: Create an agent\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-agents-agent-id-consumption\n      path: /api/agent_builder/agents/{agent_id}/consumption\n      operations:\n      - name: post-agent-builder-agents-agent-id-consumption\n        method: POST\n        description: Get agent consumption data\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: agent_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: The unique identifier of the agent.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-agents-id\n      path: /api/agent_builder/agents/{id}\n      operations:\n      - name: delete-agent-builder-agents-id\n        method: DELETE\n        description: Delete an agent\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the agent to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-builder-agents-id\n        method: GET\n        description: Get an agent by ID\n  \
  \      inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the agent to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-agent-builder-agents-id\n        method: PUT\n        description: Update an agent\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the agent to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations\n      path: /api/agent_builder/conversations\n      operations:\n\
  \      - name: get-agent-builder-conversations\n        method: GET\n        description: List conversations\n        inputParameters:\n        - name: agent_id\n          in: query\n          type: string\n          description: Optional agent ID to filter conversations by a specific agent.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id\n      path: /api/agent_builder/conversations/{conversation_id}\n      operations:\n      - name: delete-agent-builder-conversations-conversation-\n        method: DELETE\n        description: Delete conversation by ID\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The unique identifier of the conversation to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-builder-conversations-conversation-id\n        method: GET\n        description: Get conversation by ID\n        inputParameters:\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id-\n      path: /api/agent_builder/conversations/{conversation_id}/attachments\n      operations:\n      - name: get-agent-builder-conversations-conversation-id-\n        method: GET\n        description: List conversation attachments\n        inputParameters:\n        - name:\
  \ conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: include_deleted\n          in: query\n          type: boolean\n          description: Whether to include deleted attachments in the list.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-agent-builder-conversations-conversation-id\n        method: POST\n        description: Create conversation attachment\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id-\n      path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}\n      operations:\n      - name: delete-agent-builder-conversations-conversation-\n        method: DELETE\n        description: Delete conversation attachment\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: attachment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the attachment to delete.\n        - name: permanent\n          in: query\n          type: boolean\n\
  \          description: If true, permanently removes the attachment (only for unreferenced attachments).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-agent-builder-conversations-conversation-i\n        method: PATCH\n        description: Rename attachment\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: attachment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the attachment to rename.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: put-agent-builder-conversations-conversation-id-\n        method: PUT\n        description: Update conversation attachment\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: attachment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the attachment to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id-\n      path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}/_restore\n\
  \      operations:\n      - name: post-agent-builder-conversations-conversation-id\n        method: POST\n        description: Restore deleted attachment\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: attachment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the attachment to restore.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id-\n      path: /api/agent_builder/conversations/{conversation_id}/attachments/{attachment_id}/origin\n      operations:\n\
  \      - name: put-agent-builder-conversations-conversation-id-\n        method: PUT\n        description: Update attachment origin\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        - name: attachment_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the attachment to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-conversations-conversation-id-\n      path: /api/agent_builder/conversations/{conversation_id}/attachments/stale\n      operations:\n      - name: get-agent-builder-conversations-conversation-id-\n\
  \        method: GET\n        description: Check attachment staleness\n        inputParameters:\n        - name: conversation_id\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the conversation.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-converse\n      path: /api/agent_builder/converse\n      operations:\n      - name: post-agent-builder-converse\n        method: POST\n        description: Send chat message\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-converse-async\n      path: /api/agent_builder/converse/async\n\
  \      operations:\n      - name: post-agent-builder-converse-async\n        method: POST\n        description: Send chat message (streaming)\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-mcp\n      path: /api/agent_builder/mcp\n      operations:\n      - name: post-agent-builder-mcp\n        method: POST\n        description: MCP server\n        inputParameters:\n        - name: namespace\n          in: query\n          type: string\n          description: Comma-separated list of namespaces to filter tools. Only tools matching the specified namespaces will\n            be returned.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: api-agent-builder-plugins\n      path: /api/agent_builder/plugins\n      operations:\n      - name: get-agent-builder-plugins\n        method: GET\n        description: List plugins\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-plugins-pluginid\n      path: /api/agent_builder/plugins/{pluginId}\n      operations:\n      - name: delete-agent-builder-plugins-pluginid\n        method: DELETE\n        description: Delete a plugin\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: pluginId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the plugin.\n        - name: force\n          in: query\n          type: boolean\n\
  \          description: If true, removes the plugin skills from agents that use them and then deletes the plugin. If false\n            and any agent uses the plugin skills, the request returns 409\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-builder-plugins-pluginid\n        method: GET\n        description: Get a plugin by id\n        inputParameters:\n        - name: pluginId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the plugin.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-plugins-install\n      path: /api/agent_builder/plugins/install\n      operations:\n      - name: post-agent-builder-plugins-install\n        method: POST\n        description: Install a plugin\n        inputParameters:\n\
  \        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-skills\n      path: /api/agent_builder/skills\n      operations:\n      - name: get-agent-builder-skills\n        method: GET\n        description: List skills\n        inputParameters:\n        - name: include_plugins\n          in: query\n          type: boolean\n          description: Set to true to include skills from plugins.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-agent-builder-skills\n        method: POST\n        description: Create a skill\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required:\
  \ true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-skills-skillid\n      path: /api/agent_builder/skills/{skillId}\n      operations:\n      - name: delete-agent-builder-skills-skillid\n        method: DELETE\n        description: Delete a skill\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: skillId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the skill.\n        - name: force\n          in: query\n          type: boolean\n          description: If true, removes the skill from agents that use it and then deletes it. If false and any agent uses\n            the skill,\
  \ the request returns 409 Conflict with the list of\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-builder-skills-skillid\n        method: GET\n        description: Get a skill by id\n        inputParameters:\n        - name: skillId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the skill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-agent-builder-skills-skillid\n        method: PUT\n        description: Update a skill\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: skillId\n          in: path\n          type: string\n          required: true\n   \
  \       description: The unique identifier of the skill.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-tools\n      path: /api/agent_builder/tools\n      operations:\n      - name: get-agent-builder-tools\n        method: GET\n        description: List tools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-agent-builder-tools\n        method: POST\n        description: Create a tool\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-tools-execute\n      path: /api/agent_builder/tools/_execute\n\
  \      operations:\n      - name: post-agent-builder-tools-execute\n        method: POST\n        description: Run a tool\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-agent-builder-tools-toolid\n      path: /api/agent_builder/tools/{toolId}\n      operations:\n      - name: delete-agent-builder-tools-toolid\n        method: DELETE\n        description: Delete a tool\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: toolId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier\
  \ of the tool to delete.\n        - name: force\n          in: query\n          type: boolean\n          description: If true, removes the tool from agents that use it and then deletes it. If false and any agent uses\n            the tool, the request returns 409 Conflict with the list of a\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-agent-builder-tools-toolid\n        method: GET\n        description: Get a tool by id\n        inputParameters:\n        - name: toolId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the tool to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-agent-builder-tools-toolid\n        method: PUT\n        description: Update a tool\n        inputParameters:\n        - name: kbn-xsrf\n\
  \          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: toolId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier of the tool to update.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-health\n      path: /api/alerting/_health\n      operations:\n      - name: getalertinghealth\n        method: GET\n        description: Get the alerting framework health\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-rule-types\n      path: /api/alerting/rule_types\n      operations:\n      - name: getruletypes\n        method: GET\n        description: Get the rule types\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-rule-id\n      path: /api/alerting/rule/{id}\n      operations:\n      - name: delete-alerting-rule-id\n        method: DELETE\n        description: Delete a rule\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-alerting-rule-id\n        method: GET\n        description: Get rule details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule.\n       \
  \ outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-alerting-rule-id\n        method: POST\n        description: Create a rule\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule. If it is omitted, an ID is randomly generated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-alerting-rule-id\n        method: PUT\n        description: Update a rule\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect\
  \ against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-rule-id-disable\n      path: /api/alerting/rule/{id}/_disable\n      operations:\n      - name: post-alerting-rule-id-disable\n        method: POST\n        description: Disable a rule\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-rule-id-enable\n\
  \      path: /api/alerting/rule/{id}/_enable\n      operations:\n      - name: post-alerting-rule-id-enable\n        method: POST\n        description: Enable a rule\n        inputParameters:\n        - name: kbn-xsrf\n          in: header\n          type: string\n          required: true\n          description: A required header to protect against CSRF attacks\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The identifier for the rule.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-alerting-rule-id-mute-a\n\n# --- truncated at 32 KB (88 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/kibana/refs/heads/main/capabilities/kibana-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/kibana/refs/heads/main/capabilities/kibana-capability.yaml
tags:
- Kibana
- API
tools:
- description: Get connector types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions-connector-types
- description: Handle OAuth callback
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions-connector-oauth-callback
- description: '**Spaces method and path for this operation:** <div><span class="operation-verb get">get</span>&nbsp;<span class="operation-path">/s/{space_id}/api/actions/connector/_oauth_callback_script</span></div> Refer to [Spaces](https://www.elastic.'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions-connector-oauth-callback-script
- description: Delete a connector
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-actions-connector-id
- description: Get connector information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions-connector-id
- description: Create a connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-actions-connector-id
- description: Update a connector
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-actions-connector-id
- description: Run a connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-actions-connector-id-execute
- description: Get all connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions-connectors
- description: Send A2A task
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-a2a-agentid
- description: Get A2A agent card
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-a2a-agentid-json
- description: List agents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-agents
- description: Create an agent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-agents
- description: Get agent consumption data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-agents-agent-id-consumption
- description: Delete an agent
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-agents-id
- description: Get an agent by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-agents-id
- description: Update an agent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-agent-builder-agents-id
- description: List conversations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-conversations
- description: Delete conversation by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-conversations-conversation-
- description: Get conversation by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-conversations-conversation-id
- description: List conversation attachments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-conversations-conversation-id-
- description: Create conversation attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-conversations-conversation-id
- description: Delete conversation attachment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-conversations-conversation-
- description: Rename attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-agent-builder-conversations-conversation-i
- description: Update conversation attachment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-agent-builder-conversations-conversation-id-
- description: Restore deleted attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-conversations-conversation-id
- description: Update attachment origin
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-agent-builder-conversations-conversation-id-
- description: Check attachment staleness
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-conversations-conversation-id-
- description: Send chat message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-converse
- description: Send chat message (streaming)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-converse-async
- description: MCP server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-mcp
- description: List plugins
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-plugins
- description: Delete a plugin
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-plugins-pluginid
- description: Get a plugin by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-plugins-pluginid
- description: Install a plugin
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-plugins-install
- description: List skills
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-skills
- description: Create a skill
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-skills
- description: Delete a skill
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-skills-skillid
- description: Get a skill by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-skills-skillid
- description: Update a skill
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-agent-builder-skills-skillid
- description: List tools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-tools
- description: Create a tool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-tools
- description: Run a tool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-agent-builder-tools-execute
- description: Delete a tool
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-agent-builder-tools-toolid
- description: Get a tool by id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-agent-builder-tools-toolid
- description: Update a tool
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-agent-builder-tools-toolid
- description: Get the alerting framework health
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getalertinghealth
- description: Get the rule types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getruletypes
- description: Delete a rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-alerting-rule-id
- description: Get rule details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-alerting-rule-id
- description: Create a rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id
- description: Update a rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-alerting-rule-id
- description: Disable a rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-disable
- description: Enable a rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-enable
- description: Mute all alerts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-mute-all
- description: Unmute all alerts
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-unmute-all
- description: Update the API key for a rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-update-api-key
- description: Schedule a snooze for the rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-id-snooze-schedule
- description: Mute an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-rule-id-alert-alert-id-mute
- description: Unmute an alert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-alerting-rule-rule-id-alert-alert-id-unmute
---
