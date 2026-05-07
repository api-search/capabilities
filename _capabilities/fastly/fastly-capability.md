---
categories: []
consumed_apis: []
description: The Fastly Account API provides endpoints for managing customer accounts, users, and identity and access management (IAM) resources. Developers can programmatically manage user invitations, roles, permissions, and service groups to control access to Fastly resources. The API supports retrieving and updating customer information, managing user profiles, and configuring organizational settings for enterprise accounts.
layout: capability
name: Fastly Account API
operations:
- description: Get the current customer
  method: GET
  name: getcurrentcustomer
  path: /current_customer
- description: Get a customer
  method: GET
  name: getcustomer
  path: /customer/{customer_id}
- description: Update a customer
  method: PUT
  name: updatecustomer
  path: /customer/{customer_id}
- description: Get the current user
  method: GET
  name: getcurrentuser
  path: /current_user
- description: Get a user
  method: GET
  name: getuser
  path: /user/{user_id}
- description: Update a user
  method: PUT
  name: updateuser
  path: /user/{user_id}
- description: Delete a user
  method: DELETE
  name: deleteuser
  path: /user/{user_id}
- description: List users for a customer
  method: GET
  name: listcustomerusers
  path: /customer/{customer_id}/users
- description: Create a user invitation
  method: POST
  name: createinvitation
  path: /invitations
- description: List IAM roles
  method: GET
  name: listroles
  path: /roles
- description: Get an IAM role
  method: GET
  name: getrole
  path: /roles/{role_id}
- description: List IAM service groups
  method: GET
  name: listservicegroups
  path: /service-groups
- description: Create an IAM service group
  method: POST
  name: createservicegroup
  path: /service-groups
- description: List IAM user groups
  method: GET
  name: listusergroups
  path: /user-groups
- description: Create an IAM user group
  method: POST
  name: createusergroup
  path: /user-groups
personas: []
provider_name: fastly
provider_slug: fastly
search_terms:
- createservicegroup
- get the current customer
- getcurrentuser
- createusergroup
- getcustomer
- updatecustomer
- api
- create a user invitation
- list iam service groups
- delete a user
- get a customer
- list iam roles
- getuser
- get the current user
- get a user
- deleteuser
- listcustomerusers
- update a customer
- getrole
- list iam user groups
- listservicegroups
- updateuser
- getcurrentcustomer
- fastly
- createinvitation
- create an iam service group
- listusergroups
- listroles
- get an iam role
- create an iam user group
- update a user
- list users for a customer
slug: fastly-capability
source_filename: fastly-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fastly Account API\n  description: The Fastly Account API provides endpoints for managing customer accounts, users, and identity and access management\n    (IAM) resources. Developers can programmatically manage user invitations, roles, permissions, and service groups to control\n    access to Fastly resources. The API supports retrieving and updating customer information, managing user profiles, and\n    configuring organizational settings for enterprise accounts.\n  tags:\n  - Fastly\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fastly\n    baseUri: https://api.fastly.com\n    description: Fastly Account API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Fastly-Key\n      value: '{{FASTLY_TOKEN}}'\n    resources:\n    - name: current-customer\n      path: /current_customer\n      operations:\n      - name: getcurrentcustomer\n \
  \       method: GET\n        description: Get the current customer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-customer-id\n      path: /customer/{customer_id}\n      operations:\n      - name: getcustomer\n        method: GET\n        description: Get a customer\n        inputParameters:\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecustomer\n        method: PUT\n        description: Update a customer\n        inputParameters:\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the customer.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: current-user\n      path: /current_user\n      operations:\n      - name: getcurrentuser\n        method: GET\n        description: Get the current user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-user-id\n      path: /user/{user_id}\n      operations:\n      - name: getuser\n        method: GET\n        description: Get a user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n        method: PUT\n        description: Update a user\n        inputParameters:\n        - name: user_id\n\
  \          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteuser\n        method: DELETE\n        description: Delete a user\n        inputParameters:\n        - name: user_id\n          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the user.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: customer-customer-id-users\n      path: /customer/{customer_id}/users\n      operations:\n      - name: listcustomerusers\n        method: GET\n        description: List users for a customer\n        inputParameters:\n        - name: customer_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The alphanumeric string identifying the customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invitations\n      path: /invitations\n      operations:\n      - name: createinvitation\n        method: POST\n        description: Create a user invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: roles\n      path: /roles\n      operations:\n      - name: listroles\n        method: GET\n        description: List IAM roles\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n          description: The number of items per page.\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n    \
  \      type: object\n          value: $.\n    - name: roles-role-id\n      path: /roles/{role_id}\n      operations:\n      - name: getrole\n        method: GET\n        description: Get an IAM role\n        inputParameters:\n        - name: role_id\n          in: path\n          type: string\n          required: true\n          description: The alphanumeric string identifying the IAM role.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-groups\n      path: /service-groups\n      operations:\n      - name: listservicegroups\n        method: GET\n        description: List IAM service groups\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n          description: The number of items per page.\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor for pagination.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createservicegroup\n        method: POST\n        description: Create an IAM service group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-groups\n      path: /user-groups\n      operations:\n      - name: listusergroups\n        method: GET\n        description: List IAM user groups\n        inputParameters:\n        - name: per_page\n          in: query\n          type: integer\n          description: The number of items per page.\n        - name: cursor\n          in: query\n          type: string\n          description: The cursor for pagination.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createusergroup\n        method: POST\n        description: Create an IAM user group\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fastly-rest\n    description: REST adapter for Fastly Account API.\n    resources:\n    - path: /current_customer\n      name: getcurrentcustomer\n      operations:\n      - method: GET\n        name: getcurrentcustomer\n        description: Get the current customer\n        call: fastly.getcurrentcustomer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/{customer_id}\n      name: getcustomer\n      operations:\n      - method: GET\n        name: getcustomer\n        description: Get a customer\n        call: fastly.getcustomer\n        with:\n          customer_id: rest.customer_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/{customer_id}\n      name: updatecustomer\n      operations:\n      - method: PUT\n\
  \        name: updatecustomer\n        description: Update a customer\n        call: fastly.updatecustomer\n        with:\n          customer_id: rest.customer_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /current_user\n      name: getcurrentuser\n      operations:\n      - method: GET\n        name: getcurrentuser\n        description: Get the current user\n        call: fastly.getcurrentuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{user_id}\n      name: getuser\n      operations:\n      - method: GET\n        name: getuser\n        description: Get a user\n        call: fastly.getuser\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{user_id}\n      name: updateuser\n      operations:\n      - method: PUT\n        name: updateuser\n        description: Update a user\n        call: fastly.updateuser\n\
  \        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user/{user_id}\n      name: deleteuser\n      operations:\n      - method: DELETE\n        name: deleteuser\n        description: Delete a user\n        call: fastly.deleteuser\n        with:\n          user_id: rest.user_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /customer/{customer_id}/users\n      name: listcustomerusers\n      operations:\n      - method: GET\n        name: listcustomerusers\n        description: List users for a customer\n        call: fastly.listcustomerusers\n        with:\n          customer_id: rest.customer_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /invitations\n      name: createinvitation\n      operations:\n      - method: POST\n        name: createinvitation\n        description: Create a user invitation\n        call: fastly.createinvitation\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles\n      name: listroles\n      operations:\n      - method: GET\n        name: listroles\n        description: List IAM roles\n        call: fastly.listroles\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /roles/{role_id}\n      name: getrole\n      operations:\n      - method: GET\n        name: getrole\n        description: Get an IAM role\n        call: fastly.getrole\n        with:\n          role_id: rest.role_id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service-groups\n      name: listservicegroups\n      operations:\n      - method: GET\n        name: listservicegroups\n        description: List IAM service groups\n        call: fastly.listservicegroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /service-groups\n      name: createservicegroup\n      operations:\n\
  \      - method: POST\n        name: createservicegroup\n        description: Create an IAM service group\n        call: fastly.createservicegroup\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-groups\n      name: listusergroups\n      operations:\n      - method: GET\n        name: listusergroups\n        description: List IAM user groups\n        call: fastly.listusergroups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /user-groups\n      name: createusergroup\n      operations:\n      - method: POST\n        name: createusergroup\n        description: Create an IAM user group\n        call: fastly.createusergroup\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fastly-mcp\n    transport: http\n    description: MCP adapter for Fastly Account API for AI agent use.\n    tools:\n    - name: getcurrentcustomer\n      description: Get\
  \ the current customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.getcurrentcustomer\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcustomer\n      description: Get a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.getcustomer\n      with:\n        customer_id: tools.customer_id\n      inputParameters:\n      - name: customer_id\n        type: string\n        description: The alphanumeric string identifying the customer.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatecustomer\n      description: Update a customer\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: fastly.updatecustomer\n      with:\n        customer_id: tools.customer_id\n      inputParameters:\n      - name: customer_id\n    \
  \    type: string\n        description: The alphanumeric string identifying the customer.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcurrentuser\n      description: Get the current user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.getcurrentuser\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getuser\n      description: Get a user\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.getuser\n      with:\n        user_id: tools.user_id\n      inputParameters:\n      - name: user_id\n        type: string\n        description: The alphanumeric string identifying the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateuser\n      description: Update a user\n      hints:\n        readOnly: false\n        destructive:\
  \ false\n        idempotent: true\n      call: fastly.updateuser\n      with:\n        user_id: tools.user_id\n      inputParameters:\n      - name: user_id\n        type: string\n        description: The alphanumeric string identifying the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteuser\n      description: Delete a user\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fastly.deleteuser\n      with:\n        user_id: tools.user_id\n      inputParameters:\n      - name: user_id\n        type: string\n        description: The alphanumeric string identifying the user.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listcustomerusers\n      description: List users for a customer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.listcustomerusers\n\
  \      with:\n        customer_id: tools.customer_id\n      inputParameters:\n      - name: customer_id\n        type: string\n        description: The alphanumeric string identifying the customer.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createinvitation\n      description: Create a user invitation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fastly.createinvitation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listroles\n      description: List IAM roles\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.listroles\n      with:\n        per_page: tools.per_page\n        cursor: tools.cursor\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: The number of items per page.\n      - name: cursor\n        type: string\n        description:\
  \ The cursor for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getrole\n      description: Get an IAM role\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.getrole\n      with:\n        role_id: tools.role_id\n      inputParameters:\n      - name: role_id\n        type: string\n        description: The alphanumeric string identifying the IAM role.\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listservicegroups\n      description: List IAM service groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.listservicegroups\n      with:\n        per_page: tools.per_page\n        cursor: tools.cursor\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: The number of items per page.\n      - name: cursor\n        type: string\n\
  \        description: The cursor for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createservicegroup\n      description: Create an IAM service group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fastly.createservicegroup\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listusergroups\n      description: List IAM user groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fastly.listusergroups\n      with:\n        per_page: tools.per_page\n        cursor: tools.cursor\n      inputParameters:\n      - name: per_page\n        type: integer\n        description: The number of items per page.\n      - name: cursor\n        type: string\n        description: The cursor for pagination.\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createusergroup\n      description:\
  \ Create an IAM user group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fastly.createusergroup\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    FASTLY_TOKEN: FASTLY_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fastly/refs/heads/main/capabilities/fastly-capability.yaml
tags:
- Fastly
- API
tools:
- description: Get the current customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentcustomer
- description: Get a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustomer
- description: Update a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecustomer
- description: Get the current user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcurrentuser
- description: Get a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Update a user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Delete a user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteuser
- description: List users for a customer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listcustomerusers
- description: Create a user invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createinvitation
- description: List IAM roles
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listroles
- description: Get an IAM role
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrole
- description: List IAM service groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listservicegroups
- description: Create an IAM service group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createservicegroup
- description: List IAM user groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listusergroups
- description: Create an IAM user group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusergroup
---
