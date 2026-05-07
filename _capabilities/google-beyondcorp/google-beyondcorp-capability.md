---
categories: []
consumed_apis: []
description: The BeyondCorp API provides programmatic access to manage zero-trust access controls for enterprise resources. It enables creating and managing app connectors, app connections, client connector services, and security gateways for zero-trust enterprise deployments without requiring a traditional VPN.
layout: capability
name: Google BeyondCorp API
operations:
- description: Google BeyondCorp List app connectors
  method: GET
  name: listappconnectors
  path: /projects/{projectId}/locations/{location}/appConnectors
- description: Google BeyondCorp Create an app connector
  method: POST
  name: createappconnector
  path: /projects/{projectId}/locations/{location}/appConnectors
- description: Google BeyondCorp Get an app connector
  method: GET
  name: getappconnector
  path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}
- description: Google BeyondCorp Update an app connector
  method: PATCH
  name: updateappconnector
  path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}
- description: Google BeyondCorp Delete an app connector
  method: DELETE
  name: deleteappconnector
  path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}
- description: Google BeyondCorp List app connections
  method: GET
  name: listappconnections
  path: /projects/{projectId}/locations/{location}/appConnections
- description: Google BeyondCorp Create an app connection
  method: POST
  name: createappconnection
  path: /projects/{projectId}/locations/{location}/appConnections
- description: Google BeyondCorp Get an app connection
  method: GET
  name: getappconnection
  path: /projects/{projectId}/locations/{location}/appConnections/{appConnectionId}
- description: Google BeyondCorp Delete an app connection
  method: DELETE
  name: deleteappconnection
  path: /projects/{projectId}/locations/{location}/appConnections/{appConnectionId}
- description: Google BeyondCorp List security gateways
  method: GET
  name: listsecuritygateways
  path: /projects/{projectId}/locations/{location}/securityGateways
- description: Google BeyondCorp Create a security gateway
  method: POST
  name: createsecuritygateway
  path: /projects/{projectId}/locations/{location}/securityGateways
personas: []
provider_name: Google BeyondCorp
provider_slug: google-beyondcorp
search_terms:
- google beyondcorp create an app connector
- google beyondcorp list app connectors
- createappconnector
- api
- createappconnection
- deleteappconnection
- getappconnection
- google beyondcorp create a security gateway
- access control
- google
- beyondcorp
- updateappconnector
- listappconnections
- listappconnectors
- identity
- google beyondcorp delete an app connection
- getappconnector
- createsecuritygateway
- google beyondcorp update an app connector
- google beyondcorp list app connections
- google beyondcorp delete an app connector
- google beyondcorp list security gateways
- enterprise security
- deleteappconnector
- google beyondcorp create an app connection
- zero trust
- google beyondcorp get an app connection
- security
- vpn alternative
- google beyondcorp get an app connector
- listsecuritygateways
slug: google-beyondcorp-capability
source_filename: google-beyondcorp-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google BeyondCorp API\n  description: The BeyondCorp API provides programmatic access to manage zero-trust access controls for enterprise resources.\n    It enables creating and managing app connectors, app connections, client connector services, and security gateways for\n    zero-trust enterprise deployments without requiring a traditional VPN.\n  tags:\n  - Google\n  - Beyondcorp\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-beyondcorp\n    baseUri: https://beyondcorp.googleapis.com/v1\n    description: Google BeyondCorp API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_BEYONDCORP_TOKEN}}'\n    resources:\n    - name: projects-projectid-locations-location-appconnect\n      path: /projects/{projectId}/locations/{location}/appConnectors\n      operations:\n      - name: listappconnectors\n        method: GET\n        description:\
  \ Google BeyondCorp List app connectors\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: orderBy\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createappconnector\n        method: POST\n        description: Google BeyondCorp Create an app connector\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required:\
  \ true\n        - name: appConnectorId\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-appconnect\n      path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}\n      operations:\n      - name: getappconnector\n        method: GET\n        description: Google BeyondCorp Get an app connector\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: appConnectorId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateappconnector\n        method: PATCH\n \
  \       description: Google BeyondCorp Update an app connector\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: appConnectorId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteappconnector\n        method: DELETE\n        description: Google BeyondCorp Delete an app connector\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: appConnectorId\n          in: path\n          type: string\n\
  \          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-appconnect\n      path: /projects/{projectId}/locations/{location}/appConnections\n      operations:\n      - name: listappconnections\n        method: GET\n        description: Google BeyondCorp List app connections\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createappconnection\n        method: POST\n        description: Google BeyondCorp\
  \ Create an app connection\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-appconnect\n      path: /projects/{projectId}/locations/{location}/appConnections/{appConnectionId}\n      operations:\n      - name: getappconnection\n        method: GET\n        description: Google BeyondCorp Get an app connection\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: appConnectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteappconnection\n        method: DELETE\n        description: Google BeyondCorp Delete an app connection\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: appConnectionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-securityga\n      path: /projects/{projectId}/locations/{location}/securityGateways\n      operations:\n      - name: listsecuritygateways\n        method: GET\n        description: Google BeyondCorp List security gateways\n        inputParameters:\n        - name: projectId\n\
  \          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsecuritygateway\n        method: POST\n        description: Google BeyondCorp Create a security gateway\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-beyondcorp-rest\n    description: REST adapter for Google BeyondCorp API.\n    resources:\n    - path: /projects/{projectId}/locations/{location}/appConnectors\n      name:\
  \ listappconnectors\n      operations:\n      - method: GET\n        name: listappconnectors\n        description: Google BeyondCorp List app connectors\n        call: google-beyondcorp.listappconnectors\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnectors\n      name: createappconnector\n      operations:\n      - method: POST\n        name: createappconnector\n        description: Google BeyondCorp Create an app connector\n        call: google-beyondcorp.createappconnector\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}\n      name: getappconnector\n      operations:\n      - method: GET\n        name: getappconnector\n\
  \        description: Google BeyondCorp Get an app connector\n        call: google-beyondcorp.getappconnector\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          appConnectorId: rest.appConnectorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}\n      name: updateappconnector\n      operations:\n      - method: PATCH\n        name: updateappconnector\n        description: Google BeyondCorp Update an app connector\n        call: google-beyondcorp.updateappconnector\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          appConnectorId: rest.appConnectorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnectors/{appConnectorId}\n      name: deleteappconnector\n      operations:\n      - method: DELETE\n\
  \        name: deleteappconnector\n        description: Google BeyondCorp Delete an app connector\n        call: google-beyondcorp.deleteappconnector\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          appConnectorId: rest.appConnectorId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnections\n      name: listappconnections\n      operations:\n      - method: GET\n        name: listappconnections\n        description: Google BeyondCorp List app connections\n        call: google-beyondcorp.listappconnections\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnections\n      name: createappconnection\n      operations:\n      - method: POST\n        name: createappconnection\n        description:\
  \ Google BeyondCorp Create an app connection\n        call: google-beyondcorp.createappconnection\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnections/{appConnectionId}\n      name: getappconnection\n      operations:\n      - method: GET\n        name: getappconnection\n        description: Google BeyondCorp Get an app connection\n        call: google-beyondcorp.getappconnection\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          appConnectionId: rest.appConnectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/appConnections/{appConnectionId}\n      name: deleteappconnection\n      operations:\n      - method: DELETE\n        name: deleteappconnection\n        description: Google\
  \ BeyondCorp Delete an app connection\n        call: google-beyondcorp.deleteappconnection\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          appConnectionId: rest.appConnectionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/securityGateways\n      name: listsecuritygateways\n      operations:\n      - method: GET\n        name: listsecuritygateways\n        description: Google BeyondCorp List security gateways\n        call: google-beyondcorp.listsecuritygateways\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/securityGateways\n      name: createsecuritygateway\n      operations:\n      - method: POST\n        name: createsecuritygateway\n        description: Google BeyondCorp Create a security\
  \ gateway\n        call: google-beyondcorp.createsecuritygateway\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-beyondcorp-mcp\n    transport: http\n    description: MCP adapter for Google BeyondCorp API for AI agent use.\n    tools:\n    - name: listappconnectors\n      description: Google BeyondCorp List app connectors\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-beyondcorp.listappconnectors\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n        filter: tools.filter\n        orderBy: tools.orderBy\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n\
  \        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      - name: filter\n        type: string\n        description: filter\n      - name: orderBy\n        type: string\n        description: orderBy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createappconnector\n      description: Google BeyondCorp Create an app connector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-beyondcorp.createappconnector\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectorId: tools.appConnectorId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description:\
  \ location\n        required: true\n      - name: appConnectorId\n        type: string\n        description: appConnectorId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappconnector\n      description: Google BeyondCorp Get an app connector\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-beyondcorp.getappconnector\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectorId: tools.appConnectorId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: appConnectorId\n        type: string\n        description: appConnectorId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateappconnector\n      description:\
  \ Google BeyondCorp Update an app connector\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-beyondcorp.updateappconnector\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectorId: tools.appConnectorId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: appConnectorId\n        type: string\n        description: appConnectorId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteappconnector\n      description: Google BeyondCorp Delete an app connector\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: google-beyondcorp.deleteappconnector\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectorId: tools.appConnectorId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: appConnectorId\n        type: string\n        description: appConnectorId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listappconnections\n      description: Google BeyondCorp List app connections\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-beyondcorp.listappconnections\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n\
  \      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createappconnection\n      description: Google BeyondCorp Create an app connection\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-beyondcorp.createappconnection\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getappconnection\n      description: Google BeyondCorp Get an app connection\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-beyondcorp.getappconnection\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectionId: tools.appConnectionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: appConnectionId\n        type: string\n        description: appConnectionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteappconnection\n      description: Google BeyondCorp Delete an app connection\n      hints:\n        readOnly: false\n        destructive:\
  \ true\n        idempotent: true\n      call: google-beyondcorp.deleteappconnection\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        appConnectionId: tools.appConnectionId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: appConnectionId\n        type: string\n        description: appConnectionId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listsecuritygateways\n      description: Google BeyondCorp List security gateways\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-beyondcorp.listsecuritygateways\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n \
  \       type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsecuritygateway\n      description: Google BeyondCorp Create a security gateway\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-beyondcorp.createsecuritygateway\n      with:\n        projectId: tools.projectId\n        location: tools.location\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_BEYONDCORP_TOKEN: GOOGLE_BEYONDCORP_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-beyondcorp/refs/heads/main/capabilities/google-beyondcorp-capability.yaml
tags:
- Google
- Beyondcorp
- API
tools:
- description: Google BeyondCorp List app connectors
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappconnectors
- description: Google BeyondCorp Create an app connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createappconnector
- description: Google BeyondCorp Get an app connector
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappconnector
- description: Google BeyondCorp Update an app connector
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateappconnector
- description: Google BeyondCorp Delete an app connector
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteappconnector
- description: Google BeyondCorp List app connections
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listappconnections
- description: Google BeyondCorp Create an app connection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createappconnection
- description: Google BeyondCorp Get an app connection
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getappconnection
- description: Google BeyondCorp Delete an app connection
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteappconnection
- description: Google BeyondCorp List security gateways
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsecuritygateways
- description: Google BeyondCorp Create a security gateway
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsecuritygateway
---
