---
categories: []
consumed_apis: []
description: Unified workflow capability combining the Tray.ai Platform API and Embedded API for building and managing automated integrations. Covers connector discovery and invocation, embedded user lifecycle, solution instance management, authentication provisioning, and workflow promotion across environments. Designed for integration developers, embedded ISV partners, and automation engineers building on Tray.ai.
layout: capability
name: Tray.ai Integration Automation
operations:
- description: List all available Tray.ai service connectors
  method: GET
  name: list-connectors
  path: /v1/connectors
- description: Get operations and schemas for a specific connector version
  method: GET
  name: get-connector-version
  path: /v1/connectors/{connectorName}/versions/{connectorVersion}
- description: Execute a Tray.ai connector operation against a third-party service
  method: POST
  name: call-connector
  path: /v1/connectors/{connectorName}/versions/{connectorVersion}/call
- description: List all platform authentications
  method: GET
  name: list-authentications
  path: /v1/authentications
- description: Create a new platform authentication
  method: POST
  name: create-authentication
  path: /v1/authentications
- description: Get a specific authentication by ID
  method: GET
  name: get-authentication
  path: /v1/authentications/{authenticationId}
- description: Delete a platform authentication
  method: DELETE
  name: delete-authentication
  path: /v1/authentications/{authenticationId}
- description: List all available triggers
  method: GET
  name: list-triggers
  path: /v1/triggers
- description: Create a trigger subscription
  method: POST
  name: create-subscription
  path: /v1/subscriptions
- description: List all organization users
  method: GET
  name: list-users
  path: /v1/users
- description: List all workspaces in the organization
  method: GET
  name: list-workspaces
  path: /v1/workspaces
- description: Create an external user in the embedded application
  method: POST
  name: create-embedded-user
  path: /v1/embedded/users
- description: Get all published solutions available for embedding
  method: GET
  name: get-solutions
  path: /v1/embedded/solutions
- description: Create a solution instance for an embedded end user
  method: POST
  name: create-solution-instance
  path: /v1/embedded/solution-instances
- description: Get solution instances for embedded users
  method: GET
  name: get-solution-instances
  path: /v1/embedded/solution-instances
personas: []
provider_name: Tray.ai
provider_slug: tray-ai
search_terms:
- manage platform workspaces
- list all workspaces in the tray.ai organization
- create a solution instance from a published solution for an embedded end user
- list all organization users
- list all available tray.ai service connectors (700+ integrations)
- create a trigger subscription to receive real-time data from a third-party service
- manage trigger subscriptions
- get all published solutions available for embedding
- list connectors
- integration
- discover and invoke tray.ai service connectors
- get operations and input/output schemas for a specific connector version
- manage trigger subscriptions for real-time events
- delete a platform authentication by id
- execute a tray.ai connector operation to interact with a third-party service
- create platform authentication
- list all platform authentications
- get or delete a specific authentication
- create a solution instance for an embedded end user
- create subscription
- create an external user in the embedded application
- get solution instances for embedded users
- get connector version with available operations
- get embedded solutions
- update solution instance
- manage platform organization users
- get all published solutions available in the embedded application
- list triggers
- manage embedded external users
- create solution instance
- embedded integration
- get a specific authentication by id
- delete platform authentication
- create an external embedded user in the tray.ai application
- manage solution instances for embedded users
- get solution instances
- call connector
- ipaas
- update an existing solution instance (enable, disable, reconfigure)
- workflow automation
- execute a tray.ai connector operation against a third-party service
- list all available tray.ai triggers for real-time data from third-party services
- manage third-party service authentications
- delete authentication
- create a trigger subscription
- create authentication
- list all platform authentications for third-party services
- list workspaces
- list all users in the tray.ai organization
- import workflows
- export tray.ai workflows for environment promotion (staging to production)
- list all workspaces in the organization
- delete a platform authentication
- platform
- list users
- connectors
- list authentications
- create a new platform authentication for a third-party service
- create a new platform authentication
- list all available triggers
- import tray.ai workflows from exported data into the embedded account
- list platform authentications
- list all available tray.ai service connectors
- get authentication
- get published solutions for embedding
- export workflows
- get connector version
- create embedded user
- get solutions
- execute a connector operation
- get operations and schemas for a specific connector version
- automation
slug: integration-automation
source_filename: integration-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Tray.ai Integration Automation\n  description: Unified workflow capability combining the Tray.ai Platform API and Embedded API for building and managing automated\n    integrations. Covers connector discovery and invocation, embedded user lifecycle, solution instance management, authentication\n    provisioning, and workflow promotion across environments. Designed for integration developers, embedded ISV partners,\n    and automation engineers building on Tray.ai.\n  tags:\n  - Automation\n  - Connectors\n  - Embedded Integration\n  - Integration\n  - iPaaS\n  - Platform\n  - Workflow Automation\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TRAY_PLATFORM_BEARER_TOKEN: TRAY_PLATFORM_BEARER_TOKEN\n    TRAY_EMBEDDED_MASTER_TOKEN: TRAY_EMBEDDED_MASTER_TOKEN\n    TRAY_EMBEDDED_USER_TOKEN: TRAY_EMBEDDED_USER_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: tray-platform\n    baseUri:\
  \ https://api.tray.io/core/v1\n    description: Tray.ai Platform REST API for connectors, authentications, triggers, users, workspaces, and projects.\n    authentication:\n      type: bearer\n      token: '{{TRAY_PLATFORM_BEARER_TOKEN}}'\n    resources:\n    - name: connectors\n      path: /connectors\n      description: Access and invoke Tray.ai service connectors\n      operations:\n      - name: list-connectors\n        method: GET\n        description: Returns a list of all available connectors from Tray's connector library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-connector-version\n        method: GET\n        description: Retrieves details of a specific connector version including operations\n        inputParameters:\n        - name: connectorName\n          in: path\n          type: string\n          required: true\n          description: The name of the connector (e.g., salesforce,\
  \ slack)\n        - name: connectorVersion\n          in: path\n          type: string\n          required: true\n          description: The version of the connector (e.g., 2.1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: call-connector\n        method: POST\n        description: Executes a connector operation against a third-party service\n        inputParameters:\n        - name: connectorName\n          in: path\n          type: string\n          required: true\n          description: The name of the connector\n        - name: connectorVersion\n          in: path\n          type: string\n          required: true\n          description: The version of the connector\n        body:\n          type: json\n          data:\n            operation: '{{tools.operation}}'\n            authId: '{{tools.authId}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: authentications\n      path: /authentications\n      description: Manage third-party service authentications\n      operations:\n      - name: list-authentications\n        method: GET\n        description: Retrieves a list of authentications associated with the user or organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-authentication\n        method: POST\n        description: Creates a new user authentication for a third-party service\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            serviceEnvironmentId: '{{tools.serviceEnvironmentId}}'\n            userData: '{{tools.userData}}'\n            credentials: '{{tools.credentials}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n      - name: get-authentication\n        method: GET\n        description: Retrieves metadata for a user authentication by ID\n        inputParameters:\n        - name: authenticationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-authentication\n        method: DELETE\n        description: Deletes a user authentication\n        inputParameters:\n        - name: authenticationId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the authentication\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: triggers\n      path: /triggers\n      description: Manage trigger subscriptions\
  \ for real-time data\n      operations:\n      - name: list-triggers\n        method: GET\n        description: Returns a list of all available triggers from Tray's trigger library\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-subscription\n        method: POST\n        description: Creates a new trigger subscription using a trigger operation\n        body:\n          type: json\n          data:\n            triggerName: '{{tools.triggerName}}'\n            connectorName: '{{tools.connectorName}}'\n            connectorVersion: '{{tools.connectorVersion}}'\n            authId: '{{tools.authId}}'\n            input: '{{tools.input}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-subscription\n        method: DELETE\n        description: Deletes a trigger subscription by ID\n        inputParameters:\n\
  \        - name: subscriptionId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the subscription\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: users\n      path: /users\n      description: Manage users and roles within the Tray organization\n      operations:\n      - name: list-users\n        method: GET\n        description: Retrieves a list of users within the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invite-user\n        method: POST\n        description: Invites a user to the organization by email address\n        body:\n          type: json\n          data:\n            email: '{{tools.email}}'\n            role: '{{tools.role}}'\n            workspaceId: '{{tools.workspaceId}}'\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workspaces\n      path: /workspaces\n      description: Manage workspaces within the Tray organization\n      operations:\n      - name: list-workspaces\n        method: GET\n        description: Retrieves a list of workspaces in the organization\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-workspace\n        method: GET\n        description: Retrieves details for a specific workspace by ID\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-workspace-users\n        method: GET\n        description: Retrieves\
  \ a list of users belonging to a specific workspace\n        inputParameters:\n        - name: workspaceId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Manage project lifecycle and environment promotion\n      operations:\n      - name: export-project\n        method: POST\n        description: Exports a project version for environment promotion\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n          description: The unique identifier for the project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-project\n        method: POST\n     \
  \   description: Imports a project version from exported data into the target workspace\n        body:\n          type: json\n          data:\n            exportedData: '{{tools.exportedData}}'\n            workspaceId: '{{tools.workspaceId}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deploy-connector\n        method: POST\n        description: Deploys a CDK connector to the Tray platform\n        inputParameters:\n        - name: connectorName\n          in: path\n          type: string\n          required: true\n          description: The name of the CDK connector to deploy\n        - name: connectorVersion\n          in: path\n          type: string\n          required: true\n          description: The version of the CDK connector to deploy\n        body:\n          type: json\n          data:\n            connectorBundle: '{{tools.connectorBundle}}'\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: tray-embedded\n    baseUri: https://tray.io\n    description: Tray.ai Embedded GraphQL API for in-app integration experiences.\n    authentication:\n      type: bearer\n      token: '{{TRAY_EMBEDDED_MASTER_TOKEN}}'\n    resources:\n    - name: users\n      path: /graphql\n      description: Manage embedded external users\n      operations:\n      - name: create-external-user\n        method: POST\n        description: Creates a new external user for the embedded application\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-users\n        method: POST\n        description: Retrieves a list of external users with pagination support\n        body:\n          type: json\n        \
  \  data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-external-user\n        method: POST\n        description: Updates an external user's properties\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-user\n        method: POST\n        description: Removes an external user from the embedded application\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: authorize\n        method: POST\n        description: Generates a user access token from a master token\n        body:\n        \
  \  type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solutions\n      path: /graphql\n      description: Manage published solutions\n      operations:\n      - name: get-solutions\n        method: POST\n        description: Retrieves a list of published solutions available in the embedded application\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: solution-instances\n      path: /graphql\n      description: Manage solution instances for end users\n      operations:\n      - name: create-solution-instance\n        method: POST\n        description: Creates a new solution instance from a published solution for an end user\n        body:\n          type:\
  \ json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-solution-instances\n        method: POST\n        description: Retrieves solution instances for a user or all users\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-solution-instance\n        method: POST\n        description: Updates an existing solution instance\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-solution-instance\n        method: POST\n        description: Deletes a solution instance and\
  \ all associated data\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authentications\n      path: /graphql\n      description: Manage third-party service authentications for embedded users\n      operations:\n      - name: create-user-authentication\n        method: POST\n        description: Creates a new authentication for a third-party service for a user\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-authentications\n        method: POST\n        description: Retrieves a list of authentications for third-party services\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-authentication\n        method: POST\n        description: Deletes a third-party service authentication\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workflows\n      path: /graphql\n      description: Export and import workflows between embedded accounts\n      operations:\n      - name: export-workflows\n        method: POST\n        description: Exports workflows from the embedded account\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: import-workflows\n        method: POST\n\
  \        description: Imports workflows into the embedded account from exported data\n        body:\n          type: json\n          data:\n            query: '{{tools.query}}'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: tray-automation-api\n    description: Unified REST API for Tray.ai integration automation workflows.\n    resources:\n    - path: /v1/connectors\n      name: connectors\n      description: Discover and invoke Tray.ai service connectors\n      operations:\n      - method: GET\n        name: list-connectors\n        description: List all available Tray.ai service connectors\n        call: tray-platform.list-connectors\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors/{connectorName}/versions/{connectorVersion}\n      name: connector-version\n      description: Get connector version\
  \ with available operations\n      operations:\n      - method: GET\n        name: get-connector-version\n        description: Get operations and schemas for a specific connector version\n        call: tray-platform.get-connector-version\n        with:\n          connectorName: rest.connectorName\n          connectorVersion: rest.connectorVersion\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/connectors/{connectorName}/versions/{connectorVersion}/call\n      name: connector-call\n      description: Execute a connector operation\n      operations:\n      - method: POST\n        name: call-connector\n        description: Execute a Tray.ai connector operation against a third-party service\n        call: tray-platform.call-connector\n        with:\n          connectorName: rest.connectorName\n          connectorVersion: rest.connectorVersion\n          operation: rest.operation\n          authId: rest.authId\n          input: rest.input\n       \
  \ outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authentications\n      name: authentications\n      description: Manage third-party service authentications\n      operations:\n      - method: GET\n        name: list-authentications\n        description: List all platform authentications\n        call: tray-platform.list-authentications\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-authentication\n        description: Create a new platform authentication\n        call: tray-platform.create-authentication\n        with:\n          name: rest.name\n          serviceEnvironmentId: rest.serviceEnvironmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/authentications/{authenticationId}\n      name: authentication\n      description: Get or delete a specific authentication\n      operations:\n      - method: GET\n        name: get-authentication\n\
  \        description: Get a specific authentication by ID\n        call: tray-platform.get-authentication\n        with:\n          authenticationId: rest.authenticationId\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: DELETE\n        name: delete-authentication\n        description: Delete a platform authentication\n        call: tray-platform.delete-authentication\n        with:\n          authenticationId: rest.authenticationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/triggers\n      name: triggers\n      description: Manage trigger subscriptions for real-time events\n      operations:\n      - method: GET\n        name: list-triggers\n        description: List all available triggers\n        call: tray-platform.list-triggers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/subscriptions\n      name: subscriptions\n      description: Manage trigger\
  \ subscriptions\n      operations:\n      - method: POST\n        name: create-subscription\n        description: Create a trigger subscription\n        call: tray-platform.create-subscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/users\n      name: platform-users\n      description: Manage platform organization users\n      operations:\n      - method: GET\n        name: list-users\n        description: List all organization users\n        call: tray-platform.list-users\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/workspaces\n      name: workspaces\n      description: Manage platform workspaces\n      operations:\n      - method: GET\n        name: list-workspaces\n        description: List all workspaces in the organization\n        call: tray-platform.list-workspaces\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embedded/users\n      name: embedded-users\n\
  \      description: Manage embedded external users\n      operations:\n      - method: POST\n        name: create-embedded-user\n        description: Create an external user in the embedded application\n        call: tray-embedded.create-external-user\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embedded/solutions\n      name: embedded-solutions\n      description: Get published solutions for embedding\n      operations:\n      - method: GET\n        name: get-solutions\n        description: Get all published solutions available for embedding\n        call: tray-embedded.get-solutions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/embedded/solution-instances\n      name: embedded-solution-instances\n      description: Manage solution instances for embedded users\n      operations:\n      - method: POST\n        name: create-solution-instance\n        description: Create a solution instance for an\
  \ embedded end user\n        call: tray-embedded.create-solution-instance\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: GET\n        name: get-solution-instances\n        description: Get solution instances for embedded users\n        call: tray-embedded.get-solution-instances\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: tray-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted Tray.ai integration automation.\n    tools:\n    - name: list-connectors\n      description: List all available Tray.ai service connectors (700+ integrations)\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tray-platform.list-connectors\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-connector-version\n      description: Get operations and input/output schemas for a specific connector version\n      hints:\n\
  \        readOnly: true\n        openWorld: false\n      call: tray-platform.get-connector-version\n      with:\n        connectorName: tools.connectorName\n        connectorVersion: tools.connectorVersion\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: call-connector\n      description: Execute a Tray.ai connector operation to interact with a third-party service\n      hints:\n        readOnly: false\n        openWorld: true\n      call: tray-platform.call-connector\n      with:\n        connectorName: tools.connectorName\n        connectorVersion: tools.connectorVersion\n        operation: tools.operation\n        authId: tools.authId\n        input: tools.input\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-platform-authentications\n      description: List all platform authentications for third-party services\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-platform.list-authentications\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-platform-authentication\n      description: Create a new platform authentication for a third-party service\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-platform.create-authentication\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: delete-platform-authentication\n      description: Delete a platform authentication by ID\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: tray-platform.delete-authentication\n      with:\n        authenticationId: tools.authenticationId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-triggers\n      description: List all available Tray.ai triggers for real-time data from third-party services\n      hints:\n        readOnly: true\n        openWorld: true\n      call: tray-platform.list-triggers\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: create-subscription\n      description: Create a trigger subscription to receive real-time data from a third-party service\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-platform.create-subscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-users\n      description: List all users in the Tray.ai organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-platform.list-users\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-workspaces\n      description: List all workspaces in the Tray.ai organization\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-platform.list-workspaces\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-embedded-user\n      description: Create an external embedded user in the Tray.ai application\n\
  \      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-embedded.create-external-user\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-embedded-solutions\n      description: Get all published solutions available in the embedded application\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-embedded.get-solutions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-solution-instance\n      description: Create a solution instance from a published solution for an embedded end user\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-embedded.create-solution-instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-solution-instances\n      description: Get solution instances for embedded users\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-embedded.get-solution-instances\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-solution-instance\n      description: Update an existing solution instance (enable, disable, reconfigure)\n      hints:\n        readOnly: false\n        idempotent: true\n      call: tray-embedded.update-solution-instance\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: export-workflows\n      description: Export Tray.ai workflows for environment promotion (staging to production)\n      hints:\n        readOnly: true\n        openWorld: false\n      call: tray-embedded.export-workflows\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: import-workflows\n      description: Import Tray.ai workflows from exported data into the embedded account\n      hints:\n        readOnly: false\n        openWorld: false\n      call: tray-embedded.import-workflows\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/tray-ai/refs/heads/main/capabilities/integration-automation.yaml
tags:
- Automation
- Connectors
- Embedded Integration
- Integration
- iPaaS
- Platform
- Workflow Automation
tools:
- description: List all available Tray.ai service connectors (700+ integrations)
  hints:
    openWorld: true
    readOnly: true
  name: list-connectors
- description: Get operations and input/output schemas for a specific connector version
  hints:
    openWorld: false
    readOnly: true
  name: get-connector-version
- description: Execute a Tray.ai connector operation to interact with a third-party service
  hints:
    openWorld: true
    readOnly: false
  name: call-connector
- description: List all platform authentications for third-party services
  hints:
    openWorld: false
    readOnly: true
  name: list-platform-authentications
- description: Create a new platform authentication for a third-party service
  hints:
    openWorld: false
    readOnly: false
  name: create-platform-authentication
- description: Delete a platform authentication by ID
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-platform-authentication
- description: List all available Tray.ai triggers for real-time data from third-party services
  hints:
    openWorld: true
    readOnly: true
  name: list-triggers
- description: Create a trigger subscription to receive real-time data from a third-party service
  hints:
    openWorld: false
    readOnly: false
  name: create-subscription
- description: List all users in the Tray.ai organization
  hints:
    openWorld: false
    readOnly: true
  name: list-users
- description: List all workspaces in the Tray.ai organization
  hints:
    openWorld: false
    readOnly: true
  name: list-workspaces
- description: Create an external embedded user in the Tray.ai application
  hints:
    openWorld: false
    readOnly: false
  name: create-embedded-user
- description: Get all published solutions available in the embedded application
  hints:
    openWorld: false
    readOnly: true
  name: get-embedded-solutions
- description: Create a solution instance from a published solution for an embedded end user
  hints:
    openWorld: false
    readOnly: false
  name: create-solution-instance
- description: Get solution instances for embedded users
  hints:
    openWorld: false
    readOnly: true
  name: get-solution-instances
- description: Update an existing solution instance (enable, disable, reconfigure)
  hints:
    idempotent: true
    readOnly: false
  name: update-solution-instance
- description: Export Tray.ai workflows for environment promotion (staging to production)
  hints:
    openWorld: false
    readOnly: true
  name: export-workflows
- description: Import Tray.ai workflows from exported data into the embedded account
  hints:
    openWorld: false
    readOnly: false
  name: import-workflows
---
