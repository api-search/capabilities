---
categories: []
consumed_apis: []
description: Manage administrative functions for Anthropic organizations, workspaces, users, invites, and API keys.
layout: capability
name: Anthropic Admin API
operations:
- description: Anthropic Get Current Organization
  method: GET
  name: getcurrentorganization
  path: /organizations/me
- description: Anthropic List Organization Members
  method: GET
  name: listorganizationmembers
  path: /organizations/users
- description: Anthropic Get Organization Member
  method: GET
  name: getorganizationmember
  path: /organizations/users/{user_id}
- description: Anthropic Update Organization Member
  method: POST
  name: updateorganizationmember
  path: /organizations/users/{user_id}
- description: Anthropic Remove Organization Member
  method: DELETE
  name: removeorganizationmember
  path: /organizations/users/{user_id}
- description: Anthropic List Organization Invites
  method: GET
  name: listorganizationinvites
  path: /organizations/invites
- description: Anthropic Create Organization Invite
  method: POST
  name: createorganizationinvite
  path: /organizations/invites
- description: Anthropic Get Organization Invite
  method: GET
  name: getorganizationinvite
  path: /organizations/invites/{invite_id}
- description: Anthropic Delete Organization Invite
  method: DELETE
  name: deleteorganizationinvite
  path: /organizations/invites/{invite_id}
- description: Anthropic List Workspaces
  method: GET
  name: listworkspaces
  path: /organizations/workspaces
- description: Anthropic Create Workspace
  method: POST
  name: createworkspace
  path: /organizations/workspaces
- description: Anthropic Get Workspace
  method: GET
  name: getworkspace
  path: /organizations/workspaces/{workspace_id}
- description: Anthropic Update Workspace
  method: POST
  name: updateworkspace
  path: /organizations/workspaces/{workspace_id}
- description: Anthropic Archive Workspace
  method: POST
  name: archiveworkspace
  path: /organizations/workspaces/{workspace_id}/archive
- description: Anthropic List Workspace Members
  method: GET
  name: listworkspacemembers
  path: /organizations/workspaces/{workspace_id}/members
- description: Anthropic Add Workspace Member
  method: POST
  name: addworkspacemember
  path: /organizations/workspaces/{workspace_id}/members
- description: Anthropic Get Workspace Member
  method: GET
  name: getworkspacemember
  path: /organizations/workspaces/{workspace_id}/members/{user_id}
- description: Anthropic Update Workspace Member
  method: POST
  name: updateworkspacemember
  path: /organizations/workspaces/{workspace_id}/members/{user_id}
- description: Anthropic Remove Workspace Member
  method: DELETE
  name: removeworkspacemember
  path: /organizations/workspaces/{workspace_id}/members/{user_id}
- description: Anthropic List Api Keys
  method: GET
  name: listapikeys
  path: /organizations/api_keys
- description: Anthropic Get Api Key
  method: GET
  name: getapikey
  path: /organizations/api_keys/{api_key_id}
- description: Anthropic Update Api Key
  method: POST
  name: updateapikey
  path: /organizations/api_keys/{api_key_id}
personas: []
provider_name: Anthropic
provider_slug: anthropic
search_terms:
- anthropic get workspace
- anthropic get workspace member
- anthropic update api key
- foundation models
- createorganizationinvite
- anthropic remove organization member
- listorganizationinvites
- listworkspaces
- updateworkspace
- ai
- api
- updateworkspacemember
- listorganizationmembers
- removeorganizationmember
- getcurrentorganization
- anthropic add workspace member
- anthropic create workspace
- artificial intelligence
- anthropic get organization invite
- machine learning
- listapikeys
- getorganizationinvite
- removeworkspacemember
- listworkspacemembers
- anthropic get api key
- anthropic create organization invite
- anthropic get organization member
- updateorganizationmember
- updateapikey
- anthropic list workspaces
- large language models
- deleteorganizationinvite
- anthropic update organization member
- anthropic list workspace members
- anthropic update workspace
- anthropic list organization invites
- getapikey
- anthropic get current organization
- createworkspace
- anthropic list organization members
- anthropic delete organization invite
- anthropic update workspace member
- getworkspacemember
- anthropic remove workspace member
- getorganizationmember
- archiveworkspace
- addworkspacemember
- getworkspace
- anthropic list api keys
- anthropic archive workspace
- claude
- anthropic
slug: anthropic-capability
source_filename: anthropic-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Anthropic Admin API\n  description: Manage administrative functions for Anthropic organizations, workspaces, users, invites, and API keys.\n  tags:\n  - Anthropic\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: anthropic\n    baseUri: https://api.anthropic.com/v1\n    description: Anthropic Admin API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: x-api-key\n      value: '{{ANTHROPIC_TOKEN}}'\n    resources:\n    - name: organizations-me\n      path: /organizations/me\n      operations:\n      - name: getcurrentorganization\n        method: GET\n        description: Anthropic Get Current Organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-users\n      path: /organizations/users\n      operations:\n      - name: listorganizationmembers\n\
  \        method: GET\n        description: Anthropic List Organization Members\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          description: Filter by user email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-users-user-id\n      path: /organizations/users/{user_id}\n      operations:\n      - name: getorganizationmember\n        method: GET\n        description: Anthropic Get Organization Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateorganizationmember\n        method: POST\n        description: Anthropic Update Organization Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeorganizationmember\n        method: DELETE\n\
  \        description: Anthropic Remove Organization Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-invites\n      path: /organizations/invites\n      operations:\n      - name: listorganizationinvites\n        method: GET\n        description: Anthropic List Organization Invites\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorganizationinvite\n        method: POST\n        description: Anthropic Create Organization Invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-invites-invite-id\n      path: /organizations/invites/{invite_id}\n      operations:\n      - name: getorganizationinvite\n        method: GET\n        description: Anthropic Get Organization Invite\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteorganizationinvite\n        method: DELETE\n        description: Anthropic Delete Organization Invite\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-workspaces\n      path: /organizations/workspaces\n      operations:\n      - name: listworkspaces\n        method: GET\n        description: Anthropic List Workspaces\n        inputParameters:\n        - name: include_archived\n          in: query\n          type: boolean\n          description: Whether to include archived workspaces in the response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createworkspace\n        method: POST\n        description: Anthropic Create Workspace\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-workspaces-workspace-id\n      path: /organizations/workspaces/{workspace_id}\n      operations:\n      - name: getworkspace\n        method: GET\n        description: Anthropic Get Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateworkspace\n        method: POST\n        description: Anthropic Update Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-workspaces-workspace-id-archive\n      path: /organizations/workspaces/{workspace_id}/archive\n      operations:\n      - name: archiveworkspace\n        method: POST\n        description: Anthropic Archive Workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: organizations-workspaces-workspace-id-members\n      path: /organizations/workspaces/{workspace_id}/members\n      operations:\n      - name: listworkspacemembers\n        method: GET\n        description: Anthropic List Workspace Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addworkspacemember\n        method: POST\n        description: Anthropic Add Workspace Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-workspaces-workspace-id-members-us\n      path: /organizations/workspaces/{workspace_id}/members/{user_id}\n      operations:\n      - name: getworkspacemember\n        method: GET\n        description: Anthropic Get Workspace Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: updateworkspacemember\n        method: POST\n        description: Anthropic Update Workspace Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeworkspacemember\n        method: DELETE\n        description: Anthropic Remove Workspace Member\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-api-keys\n      path: /organizations/api_keys\n      operations:\n      - name: listapikeys\n        method: GET\n        description: Anthropic List Api Keys\n        inputParameters:\n        - name: workspace_id\n          in: query\n          type: string\n          description: Filter by workspace ID\n        - name: status\n          in: query\n          type: string\n          description: Filter by API key status\n        - name:\
  \ created_by_user_id\n          in: query\n          type: string\n          description: Filter by the user who created the API key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: organizations-api-keys-api-key-id\n      path: /organizations/api_keys/{api_key_id}\n      operations:\n      - name: getapikey\n        method: GET\n        description: Anthropic Get Api Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: POST\n        description: Anthropic Update Api Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: anthropic-rest\n    description: REST adapter for Anthropic Admin API.\n    resources:\n    - path: /organizations/me\n   \
  \   name: getcurrentorganization\n      operations:\n      - method: GET\n        name: getcurrentorganization\n        description: Anthropic Get Current Organization\n        call: anthropic.getcurrentorganization\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/users\n      name: listorganizationmembers\n      operations:\n      - method: GET\n        name: listorganizationmembers\n        description: Anthropic List Organization Members\n        call: anthropic.listorganizationmembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/users/{user_id}\n      name: getorganizationmember\n      operations:\n      - method: GET\n        name: getorganizationmember\n        description: Anthropic Get Organization Member\n        call: anthropic.getorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/users/{user_id}\n\
  \      name: updateorganizationmember\n      operations:\n      - method: POST\n        name: updateorganizationmember\n        description: Anthropic Update Organization Member\n        call: anthropic.updateorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/users/{user_id}\n      name: removeorganizationmember\n      operations:\n      - method: DELETE\n        name: removeorganizationmember\n        description: Anthropic Remove Organization Member\n        call: anthropic.removeorganizationmember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/invites\n      name: listorganizationinvites\n      operations:\n      - method: GET\n        name: listorganizationinvites\n        description: Anthropic List Organization Invites\n        call: anthropic.listorganizationinvites\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/invites\n\
  \      name: createorganizationinvite\n      operations:\n      - method: POST\n        name: createorganizationinvite\n        description: Anthropic Create Organization Invite\n        call: anthropic.createorganizationinvite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/invites/{invite_id}\n      name: getorganizationinvite\n      operations:\n      - method: GET\n        name: getorganizationinvite\n        description: Anthropic Get Organization Invite\n        call: anthropic.getorganizationinvite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/invites/{invite_id}\n      name: deleteorganizationinvite\n      operations:\n      - method: DELETE\n        name: deleteorganizationinvite\n        description: Anthropic Delete Organization Invite\n        call: anthropic.deleteorganizationinvite\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /organizations/workspaces\n      name: listworkspaces\n      operations:\n      - method: GET\n        name: listworkspaces\n        description: Anthropic List Workspaces\n        call: anthropic.listworkspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces\n      name: createworkspace\n      operations:\n      - method: POST\n        name: createworkspace\n        description: Anthropic Create Workspace\n        call: anthropic.createworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}\n      name: getworkspace\n      operations:\n      - method: GET\n        name: getworkspace\n        description: Anthropic Get Workspace\n        call: anthropic.getworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}\n      name: updateworkspace\n      operations:\n\
  \      - method: POST\n        name: updateworkspace\n        description: Anthropic Update Workspace\n        call: anthropic.updateworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/archive\n      name: archiveworkspace\n      operations:\n      - method: POST\n        name: archiveworkspace\n        description: Anthropic Archive Workspace\n        call: anthropic.archiveworkspace\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/members\n      name: listworkspacemembers\n      operations:\n      - method: GET\n        name: listworkspacemembers\n        description: Anthropic List Workspace Members\n        call: anthropic.listworkspacemembers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/members\n      name: addworkspacemember\n      operations:\n\
  \      - method: POST\n        name: addworkspacemember\n        description: Anthropic Add Workspace Member\n        call: anthropic.addworkspacemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/members/{user_id}\n      name: getworkspacemember\n      operations:\n      - method: GET\n        name: getworkspacemember\n        description: Anthropic Get Workspace Member\n        call: anthropic.getworkspacemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/members/{user_id}\n      name: updateworkspacemember\n      operations:\n      - method: POST\n        name: updateworkspacemember\n        description: Anthropic Update Workspace Member\n        call: anthropic.updateworkspacemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/workspaces/{workspace_id}/members/{user_id}\n\
  \      name: removeworkspacemember\n      operations:\n      - method: DELETE\n        name: removeworkspacemember\n        description: Anthropic Remove Workspace Member\n        call: anthropic.removeworkspacemember\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/api_keys\n      name: listapikeys\n      operations:\n      - method: GET\n        name: listapikeys\n        description: Anthropic List Api Keys\n        call: anthropic.listapikeys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/api_keys/{api_key_id}\n      name: getapikey\n      operations:\n      - method: GET\n        name: getapikey\n        description: Anthropic Get Api Key\n        call: anthropic.getapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /organizations/api_keys/{api_key_id}\n      name: updateapikey\n      operations:\n      - method: POST\n        name:\
  \ updateapikey\n        description: Anthropic Update Api Key\n        call: anthropic.updateapikey\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: anthropic-mcp\n    transport: http\n    description: MCP adapter for Anthropic Admin API for AI agent use.\n    tools:\n    - name: getcurrentorganization\n      description: Anthropic Get Current Organization\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getcurrentorganization\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganizationmembers\n      description: Anthropic List Organization Members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.listorganizationmembers\n      with:\n        email: tools.email\n      inputParameters:\n      - name: email\n        type: string\n        description: Filter\
  \ by user email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationmember\n      description: Anthropic Get Organization Member\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getorganizationmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateorganizationmember\n      description: Anthropic Update Organization Member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.updateorganizationmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeorganizationmember\n      description: Anthropic Remove Organization Member\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: anthropic.removeorganizationmember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listorganizationinvites\n\
  \      description: Anthropic List Organization Invites\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.listorganizationinvites\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createorganizationinvite\n      description: Anthropic Create Organization Invite\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.createorganizationinvite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getorganizationinvite\n      description: Anthropic Get Organization Invite\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getorganizationinvite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteorganizationinvite\n      description: Anthropic Delete Organization Invite\n      hints:\n        readOnly: false\n  \
  \      destructive: true\n        idempotent: true\n      call: anthropic.deleteorganizationinvite\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkspaces\n      description: Anthropic List Workspaces\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.listworkspaces\n      with:\n        include_archived: tools.include_archived\n      inputParameters:\n      - name: include_archived\n        type: boolean\n        description: Whether to include archived workspaces in the response\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createworkspace\n      description: Anthropic Create Workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.createworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkspace\n      description: Anthropic Get Workspace\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkspace\n      description: Anthropic Update Workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.updateworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: archiveworkspace\n      description: Anthropic Archive Workspace\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.archiveworkspace\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listworkspacemembers\n      description: Anthropic List Workspace Members\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.listworkspacemembers\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: addworkspacemember\n      description: Anthropic Add Workspace Member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.addworkspacemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getworkspacemember\n      description: Anthropic Get Workspace Member\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getworkspacemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateworkspacemember\n      description: Anthropic Update Workspace Member\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.updateworkspacemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeworkspacemember\n      description: Anthropic Remove Workspace Member\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: anthropic.removeworkspacemember\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listapikeys\n      description: Anthropic List Api Keys\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.listapikeys\n      with:\n        workspace_id: tools.workspace_id\n        status: tools.status\n        created_by_user_id: tools.created_by_user_id\n      inputParameters:\n      - name: workspace_id\n        type: string\n        description: Filter by workspace ID\n      - name: status\n        type: string\n        description: Filter by API key status\n      - name: created_by_user_id\n        type: string\n        description: Filter by the user who created the API key\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getapikey\n      description: Anthropic Get Api\
  \ Key\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: anthropic.getapikey\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateapikey\n      description: Anthropic Update Api Key\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: anthropic.updateapikey\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    ANTHROPIC_TOKEN: ANTHROPIC_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/anthropic/refs/heads/main/capabilities/anthropic-capability.yaml
tags:
- Anthropic
- API
tools:
- description: Anthropic Get Current Organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentorganization
- description: Anthropic List Organization Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationmembers
- description: Anthropic Get Organization Member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationmember
- description: Anthropic Update Organization Member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateorganizationmember
- description: Anthropic Remove Organization Member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeorganizationmember
- description: Anthropic List Organization Invites
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listorganizationinvites
- description: Anthropic Create Organization Invite
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorganizationinvite
- description: Anthropic Get Organization Invite
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getorganizationinvite
- description: Anthropic Delete Organization Invite
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteorganizationinvite
- description: Anthropic List Workspaces
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspaces
- description: Anthropic Create Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createworkspace
- description: Anthropic Get Workspace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspace
- description: Anthropic Update Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateworkspace
- description: Anthropic Archive Workspace
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: archiveworkspace
- description: Anthropic List Workspace Members
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listworkspacemembers
- description: Anthropic Add Workspace Member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addworkspacemember
- description: Anthropic Get Workspace Member
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getworkspacemember
- description: Anthropic Update Workspace Member
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateworkspacemember
- description: Anthropic Remove Workspace Member
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeworkspacemember
- description: Anthropic List Api Keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listapikeys
- description: Anthropic Get Api Key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
- description: Anthropic Update Api Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapikey
---
