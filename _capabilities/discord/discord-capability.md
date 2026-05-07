---
categories: []
consumed_apis: []
description: The Discord Interactions API enables applications to create and respond to application commands (slash commands), message components, and modals. It supports both Gateway-based and webhook-based interaction handling, allowing bots to build rich, interactive user experiences within Discord.
layout: capability
name: Discord Interactions API
operations:
- description: Discord List global application commands
  method: GET
  name: getglobalapplicationcommands
  path: /applications/{application_id}/commands
- description: Discord Create global application command
  method: POST
  name: createglobalapplicationcommand
  path: /applications/{application_id}/commands
- description: Discord Bulk overwrite global application commands
  method: PUT
  name: bulkoverwriteglobalapplicationcommands
  path: /applications/{application_id}/commands
- description: Discord Get global application command
  method: GET
  name: getglobalapplicationcommand
  path: /applications/{application_id}/commands/{command_id}
- description: Discord Edit global application command
  method: PATCH
  name: editglobalapplicationcommand
  path: /applications/{application_id}/commands/{command_id}
- description: Discord Delete global application command
  method: DELETE
  name: deleteglobalapplicationcommand
  path: /applications/{application_id}/commands/{command_id}
- description: Discord List guild application commands
  method: GET
  name: getguildapplicationcommands
  path: /applications/{application_id}/guilds/{guild_id}/commands
- description: Discord Create guild application command
  method: POST
  name: createguildapplicationcommand
  path: /applications/{application_id}/guilds/{guild_id}/commands
- description: Discord Bulk overwrite guild application commands
  method: PUT
  name: bulkoverwriteguildapplicationcommands
  path: /applications/{application_id}/guilds/{guild_id}/commands
- description: Discord Get guild application command
  method: GET
  name: getguildapplicationcommand
  path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}
- description: Discord Edit guild application command
  method: PATCH
  name: editguildapplicationcommand
  path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}
- description: Discord Delete guild application command
  method: DELETE
  name: deleteguildapplicationcommand
  path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}
- description: Discord List guild application command permissions
  method: GET
  name: getguildapplicationcommandpermissions
  path: /applications/{application_id}/guilds/{guild_id}/commands/permissions
- description: Discord Get application command permissions
  method: GET
  name: getapplicationcommandpermissions
  path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}/permissions
- description: Discord Edit application command permissions
  method: PUT
  name: editapplicationcommandpermissions
  path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}/permissions
- description: Discord Create interaction response
  method: POST
  name: createinteractionresponse
  path: /interactions/{interaction_id}/{interaction_token}/callback
- description: Discord Get original interaction response
  method: GET
  name: getoriginalinteractionresponse
  path: /webhooks/{application_id}/{interaction_token}/messages/@original
- description: Discord Edit original interaction response
  method: PATCH
  name: editoriginalinteractionresponse
  path: /webhooks/{application_id}/{interaction_token}/messages/@original
- description: Discord Delete original interaction response
  method: DELETE
  name: deleteoriginalinteractionresponse
  path: /webhooks/{application_id}/{interaction_token}/messages/@original
- description: Discord Create followup message
  method: POST
  name: createfollowupmessage
  path: /webhooks/{application_id}/{interaction_token}
- description: Discord Get followup message
  method: GET
  name: getfollowupmessage
  path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}
- description: Discord Edit followup message
  method: PATCH
  name: editfollowupmessage
  path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}
- description: Discord Delete followup message
  method: DELETE
  name: deletefollowupmessage
  path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}
personas: []
provider_name: Discord
provider_slug: discord
search_terms:
- createfollowupmessage
- getapplicationcommandpermissions
- bulkoverwriteglobalapplicationcommands
- discord bulk overwrite guild application commands
- video
- editoriginalinteractionresponse
- getglobalapplicationcommands
- discord get original interaction response
- discord create global application command
- api
- discord create guild application command
- getguildapplicationcommandpermissions
- discord create interaction response
- editguildapplicationcommand
- createguildapplicationcommand
- deleteguildapplicationcommand
- discord create followup message
- discord bulk overwrite global application commands
- discord
- deleteoriginalinteractionresponse
- discord get global application command
- discord edit followup message
- bulkoverwriteguildapplicationcommands
- communication
- discord get application command permissions
- createinteractionresponse
- editfollowupmessage
- discord edit application command permissions
- editapplicationcommandpermissions
- deleteglobalapplicationcommand
- discord delete followup message
- discord get followup message
- getglobalapplicationcommand
- getguildapplicationcommand
- discord delete original interaction response
- getguildapplicationcommands
- gaming
- discord edit global application command
- deletefollowupmessage
- createglobalapplicationcommand
- editglobalapplicationcommand
- chat
- discord delete guild application command
- getfollowupmessage
- discord edit guild application command
- discord list guild application command permissions
- discord list global application commands
- discord list guild application commands
- voice
- social
- discord get guild application command
- getoriginalinteractionresponse
- discord delete global application command
- messaging
- discord edit original interaction response
slug: discord-capability
source_filename: discord-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Discord Interactions API\n  description: The Discord Interactions API enables applications to create and respond to application commands (slash commands),\n    message components, and modals. It supports both Gateway-based and webhook-based interaction handling, allowing bots to\n    build rich, interactive user experiences within Discord.\n  tags:\n  - Discord\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: discord\n    baseUri: https://discord.com/api/v10\n    description: Discord Interactions API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{DISCORD_TOKEN}}'\n    resources:\n    - name: applications-application-id-commands\n      path: /applications/{application_id}/commands\n      operations:\n      - name: getglobalapplicationcommands\n        method: GET\n        description: Discord List global application commands\n        inputParameters:\n\
  \        - name: with_localizations\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createglobalapplicationcommand\n        method: POST\n        description: Discord Create global application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: bulkoverwriteglobalapplicationcommands\n        method: PUT\n        description: Discord Bulk overwrite global application commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-application-id-commands-command-id\n      path: /applications/{application_id}/commands/{command_id}\n      operations:\n      - name: getglobalapplicationcommand\n        method: GET\n        description: Discord Get global application\
  \ command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editglobalapplicationcommand\n        method: PATCH\n        description: Discord Edit global application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteglobalapplicationcommand\n        method: DELETE\n        description: Discord Delete global application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-application-id-guilds-guild-id-comm\n      path: /applications/{application_id}/guilds/{guild_id}/commands\n      operations:\n      - name: getguildapplicationcommands\n        method: GET\n        description: Discord List guild application commands\n        inputParameters:\n        - name: with_localizations\n    \
  \      in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createguildapplicationcommand\n        method: POST\n        description: Discord Create guild application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: bulkoverwriteguildapplicationcommands\n        method: PUT\n        description: Discord Bulk overwrite guild application commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-application-id-guilds-guild-id-comm\n      path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}\n      operations:\n      - name: getguildapplicationcommand\n        method: GET\n        description: Discord Get guild application command\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editguildapplicationcommand\n        method: PATCH\n        description: Discord Edit guild application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteguildapplicationcommand\n        method: DELETE\n        description: Discord Delete guild application command\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: applications-application-id-guilds-guild-id-comm\n      path: /applications/{application_id}/guilds/{guild_id}/commands/permissions\n      operations:\n      - name: getguildapplicationcommandpermissions\n        method: GET\n        description: Discord List guild application command permissions\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: applications-application-id-guilds-guild-id-comm\n      path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}/permissions\n      operations:\n      - name: getapplicationcommandpermissions\n        method: GET\n        description: Discord Get application command permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editapplicationcommandpermissions\n        method: PUT\n        description: Discord Edit application command permissions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: interactions-interaction-id-interaction-token-ca\n      path: /interactions/{interaction_id}/{interaction_token}/callback\n      operations:\n      - name: createinteractionresponse\n        method: POST\n        description: Discord\
  \ Create interaction response\n        inputParameters:\n        - name: interaction_id\n          in: path\n          type: string\n          required: true\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-application-id-interaction-token-messag\n      path: /webhooks/{application_id}/{interaction_token}/messages/@original\n      operations:\n      - name: getoriginalinteractionresponse\n        method: GET\n        description: Discord Get original interaction response\n        inputParameters:\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editoriginalinteractionresponse\n        method:\
  \ PATCH\n        description: Discord Edit original interaction response\n        inputParameters:\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteoriginalinteractionresponse\n        method: DELETE\n        description: Discord Delete original interaction response\n        inputParameters:\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-application-id-interaction-token\n      path: /webhooks/{application_id}/{interaction_token}\n      operations:\n      - name: createfollowupmessage\n        method: POST\n        description: Discord Create followup message\n        inputParameters:\n\
  \        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: webhooks-application-id-interaction-token-messag\n      path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}\n      operations:\n      - name: getfollowupmessage\n        method: GET\n        description: Discord Get followup message\n        inputParameters:\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        - name: message_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editfollowupmessage\n        method: PATCH\n        description: Discord Edit followup message\n        inputParameters:\n     \
  \   - name: interaction_token\n          in: path\n          type: string\n          required: true\n        - name: message_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefollowupmessage\n        method: DELETE\n        description: Discord Delete followup message\n        inputParameters:\n        - name: interaction_token\n          in: path\n          type: string\n          required: true\n        - name: message_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: discord-rest\n    description: REST adapter for Discord Interactions API.\n    resources:\n    - path: /applications/{application_id}/commands\n\
  \      name: getglobalapplicationcommands\n      operations:\n      - method: GET\n        name: getglobalapplicationcommands\n        description: Discord List global application commands\n        call: discord.getglobalapplicationcommands\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/commands\n      name: createglobalapplicationcommand\n      operations:\n      - method: POST\n        name: createglobalapplicationcommand\n        description: Discord Create global application command\n        call: discord.createglobalapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/commands\n      name: bulkoverwriteglobalapplicationcommands\n      operations:\n      - method: PUT\n        name: bulkoverwriteglobalapplicationcommands\n        description: Discord Bulk overwrite global application commands\n        call: discord.bulkoverwriteglobalapplicationcommands\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/commands/{command_id}\n      name: getglobalapplicationcommand\n      operations:\n      - method: GET\n        name: getglobalapplicationcommand\n        description: Discord Get global application command\n        call: discord.getglobalapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/commands/{command_id}\n      name: editglobalapplicationcommand\n      operations:\n      - method: PATCH\n        name: editglobalapplicationcommand\n        description: Discord Edit global application command\n        call: discord.editglobalapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/commands/{command_id}\n      name: deleteglobalapplicationcommand\n      operations:\n      - method: DELETE\n        name:\
  \ deleteglobalapplicationcommand\n        description: Discord Delete global application command\n        call: discord.deleteglobalapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands\n      name: getguildapplicationcommands\n      operations:\n      - method: GET\n        name: getguildapplicationcommands\n        description: Discord List guild application commands\n        call: discord.getguildapplicationcommands\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands\n      name: createguildapplicationcommand\n      operations:\n      - method: POST\n        name: createguildapplicationcommand\n        description: Discord Create guild application command\n        call: discord.createguildapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /applications/{application_id}/guilds/{guild_id}/commands\n      name: bulkoverwriteguildapplicationcommands\n      operations:\n      - method: PUT\n        name: bulkoverwriteguildapplicationcommands\n        description: Discord Bulk overwrite guild application commands\n        call: discord.bulkoverwriteguildapplicationcommands\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}\n      name: getguildapplicationcommand\n      operations:\n      - method: GET\n        name: getguildapplicationcommand\n        description: Discord Get guild application command\n        call: discord.getguildapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}\n      name: editguildapplicationcommand\n      operations:\n      - method: PATCH\n        name: editguildapplicationcommand\n\
  \        description: Discord Edit guild application command\n        call: discord.editguildapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}\n      name: deleteguildapplicationcommand\n      operations:\n      - method: DELETE\n        name: deleteguildapplicationcommand\n        description: Discord Delete guild application command\n        call: discord.deleteguildapplicationcommand\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/permissions\n      name: getguildapplicationcommandpermissions\n      operations:\n      - method: GET\n        name: getguildapplicationcommandpermissions\n        description: Discord List guild application command permissions\n        call: discord.getguildapplicationcommandpermissions\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}/permissions\n      name: getapplicationcommandpermissions\n      operations:\n      - method: GET\n        name: getapplicationcommandpermissions\n        description: Discord Get application command permissions\n        call: discord.getapplicationcommandpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /applications/{application_id}/guilds/{guild_id}/commands/{command_id}/permissions\n      name: editapplicationcommandpermissions\n      operations:\n      - method: PUT\n        name: editapplicationcommandpermissions\n        description: Discord Edit application command permissions\n        call: discord.editapplicationcommandpermissions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /interactions/{interaction_id}/{interaction_token}/callback\n      name: createinteractionresponse\n      operations:\n\
  \      - method: POST\n        name: createinteractionresponse\n        description: Discord Create interaction response\n        call: discord.createinteractionresponse\n        with:\n          interaction_id: rest.interaction_id\n          interaction_token: rest.interaction_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/@original\n      name: getoriginalinteractionresponse\n      operations:\n      - method: GET\n        name: getoriginalinteractionresponse\n        description: Discord Get original interaction response\n        call: discord.getoriginalinteractionresponse\n        with:\n          interaction_token: rest.interaction_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/@original\n      name: editoriginalinteractionresponse\n      operations:\n      - method: PATCH\n    \
  \    name: editoriginalinteractionresponse\n        description: Discord Edit original interaction response\n        call: discord.editoriginalinteractionresponse\n        with:\n          interaction_token: rest.interaction_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/@original\n      name: deleteoriginalinteractionresponse\n      operations:\n      - method: DELETE\n        name: deleteoriginalinteractionresponse\n        description: Discord Delete original interaction response\n        call: discord.deleteoriginalinteractionresponse\n        with:\n          interaction_token: rest.interaction_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}\n      name: createfollowupmessage\n      operations:\n      - method: POST\n        name: createfollowupmessage\n        description: Discord Create followup\
  \ message\n        call: discord.createfollowupmessage\n        with:\n          interaction_token: rest.interaction_token\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}\n      name: getfollowupmessage\n      operations:\n      - method: GET\n        name: getfollowupmessage\n        description: Discord Get followup message\n        call: discord.getfollowupmessage\n        with:\n          interaction_token: rest.interaction_token\n          message_id: rest.message_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}\n      name: editfollowupmessage\n      operations:\n      - method: PATCH\n        name: editfollowupmessage\n        description: Discord Edit followup message\n        call: discord.editfollowupmessage\n        with:\n          interaction_token: rest.interaction_token\n\
  \          message_id: rest.message_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /webhooks/{application_id}/{interaction_token}/messages/{message_id}\n      name: deletefollowupmessage\n      operations:\n      - method: DELETE\n        name: deletefollowupmessage\n        description: Discord Delete followup message\n        call: discord.deletefollowupmessage\n        with:\n          interaction_token: rest.interaction_token\n          message_id: rest.message_id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: discord-mcp\n    transport: http\n    description: MCP adapter for Discord Interactions API for AI agent use.\n    tools:\n    - name: getglobalapplicationcommands\n      description: Discord List global application commands\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getglobalapplicationcommands\n\
  \      with:\n        with_localizations: tools.with_localizations\n      inputParameters:\n      - name: with_localizations\n        type: boolean\n        description: with_localizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createglobalapplicationcommand\n      description: Discord Create global application command\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.createglobalapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulkoverwriteglobalapplicationcommands\n      description: Discord Bulk overwrite global application commands\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: discord.bulkoverwriteglobalapplicationcommands\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getglobalapplicationcommand\n      description: Discord Get global\
  \ application command\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getglobalapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editglobalapplicationcommand\n      description: Discord Edit global application command\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.editglobalapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteglobalapplicationcommand\n      description: Discord Delete global application command\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: discord.deleteglobalapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getguildapplicationcommands\n      description: Discord List guild application commands\n      hints:\n        readOnly: true\n\
  \        destructive: false\n        idempotent: true\n      call: discord.getguildapplicationcommands\n      with:\n        with_localizations: tools.with_localizations\n      inputParameters:\n      - name: with_localizations\n        type: boolean\n        description: with_localizations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createguildapplicationcommand\n      description: Discord Create guild application command\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.createguildapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: bulkoverwriteguildapplicationcommands\n      description: Discord Bulk overwrite guild application commands\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: discord.bulkoverwriteguildapplicationcommands\n      outputParameters:\n      - type: object\n \
  \       mapping: $.\n    - name: getguildapplicationcommand\n      description: Discord Get guild application command\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getguildapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editguildapplicationcommand\n      description: Discord Edit guild application command\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.editguildapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteguildapplicationcommand\n      description: Discord Delete guild application command\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: discord.deleteguildapplicationcommand\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getguildapplicationcommandpermissions\n\
  \      description: Discord List guild application command permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getguildapplicationcommandpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapplicationcommandpermissions\n      description: Discord Get application command permissions\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getapplicationcommandpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editapplicationcommandpermissions\n      description: Discord Edit application command permissions\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: discord.editapplicationcommandpermissions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinteractionresponse\n      description:\
  \ Discord Create interaction response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.createinteractionresponse\n      with:\n        interaction_id: tools.interaction_id\n        interaction_token: tools.interaction_token\n      inputParameters:\n      - name: interaction_id\n        type: string\n        description: interaction_id\n        required: true\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getoriginalinteractionresponse\n      description: Discord Get original interaction response\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getoriginalinteractionresponse\n      with:\n        interaction_token: tools.interaction_token\n      inputParameters:\n      - name: interaction_token\n        type:\
  \ string\n        description: interaction_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editoriginalinteractionresponse\n      description: Discord Edit original interaction response\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.editoriginalinteractionresponse\n      with:\n        interaction_token: tools.interaction_token\n      inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteoriginalinteractionresponse\n      description: Discord Delete original interaction response\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: discord.deleteoriginalinteractionresponse\n      with:\n        interaction_token: tools.interaction_token\n  \
  \    inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createfollowupmessage\n      description: Discord Create followup message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.createfollowupmessage\n      with:\n        interaction_token: tools.interaction_token\n      inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfollowupmessage\n      description: Discord Get followup message\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: discord.getfollowupmessage\n      with:\n        interaction_token: tools.interaction_token\n        message_id:\
  \ tools.message_id\n      inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      - name: message_id\n        type: string\n        description: message_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: editfollowupmessage\n      description: Discord Edit followup message\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: discord.editfollowupmessage\n      with:\n        interaction_token: tools.interaction_token\n        message_id: tools.message_id\n      inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      - name: message_id\n        type: string\n        description: message_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletefollowupmessage\n\
  \      description: Discord Delete followup message\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: discord.deletefollowupmessage\n      with:\n        interaction_token: tools.interaction_token\n        message_id: tools.message_id\n      inputParameters:\n      - name: interaction_token\n        type: string\n        description: interaction_token\n        required: true\n      - name: message_id\n        type: string\n        description: message_id\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    DISCORD_TOKEN: DISCORD_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/discord/refs/heads/main/capabilities/discord-capability.yaml
tags:
- Discord
- API
tools:
- description: Discord List global application commands
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getglobalapplicationcommands
- description: Discord Create global application command
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createglobalapplicationcommand
- description: Discord Bulk overwrite global application commands
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: bulkoverwriteglobalapplicationcommands
- description: Discord Get global application command
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getglobalapplicationcommand
- description: Discord Edit global application command
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editglobalapplicationcommand
- description: Discord Delete global application command
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteglobalapplicationcommand
- description: Discord List guild application commands
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getguildapplicationcommands
- description: Discord Create guild application command
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createguildapplicationcommand
- description: Discord Bulk overwrite guild application commands
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: bulkoverwriteguildapplicationcommands
- description: Discord Get guild application command
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getguildapplicationcommand
- description: Discord Edit guild application command
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editguildapplicationcommand
- description: Discord Delete guild application command
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteguildapplicationcommand
- description: Discord List guild application command permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getguildapplicationcommandpermissions
- description: Discord Get application command permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapplicationcommandpermissions
- description: Discord Edit application command permissions
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editapplicationcommandpermissions
- description: Discord Create interaction response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinteractionresponse
- description: Discord Get original interaction response
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoriginalinteractionresponse
- description: Discord Edit original interaction response
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editoriginalinteractionresponse
- description: Discord Delete original interaction response
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteoriginalinteractionresponse
- description: Discord Create followup message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfollowupmessage
- description: Discord Get followup message
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfollowupmessage
- description: Discord Edit followup message
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: editfollowupmessage
- description: Discord Delete followup message
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefollowupmessage
---
