---
categories: []
consumed_apis: []
description: Unified workflow for web hosting business automation combining client onboarding, billing management, support ticket handling, and domain management via WHMCS. Designed for hosting provider operations teams and resellers.
layout: capability
name: WHMCS Hosting Automation
operations:
- description: Retrieve a paginated list of client accounts.
  method: GET
  name: list-clients
  path: /v1/clients
- description: Retrieve detailed information for a specific client.
  method: GET
  name: get-client
  path: /v1/clients/{id}
- description: Retrieve a list of orders with optional filtering.
  method: GET
  name: list-orders
  path: /v1/orders
- description: Retrieve invoices with optional status and client filtering.
  method: GET
  name: list-invoices
  path: /v1/invoices
- description: Retrieve a specific invoice by ID.
  method: GET
  name: get-invoice
  path: /v1/invoices/{id}
- description: Retrieve a list of support tickets.
  method: GET
  name: list-tickets
  path: /v1/tickets
- description: Open a new support ticket.
  method: POST
  name: open-ticket
  path: /v1/tickets
- description: Perform a WHOIS lookup on a domain name.
  method: GET
  name: check-domain
  path: /v1/domains/whois
- description: Retrieve WHMCS system statistics and revenue metrics.
  method: GET
  name: get-stats
  path: /v1/system/stats
- description: Validate client login credentials.
  method: POST
  name: validate-login
  path: /v1/auth/validate
- description: Create an SSO token for client portal access.
  method: POST
  name: create-sso-token
  path: /v1/auth/sso
personas: []
provider_name: WHMCS
provider_slug: whmcs
search_terms:
- retrieve detailed information for a specific client.
- open a new support ticket.
- get system stats
- get client details
- get client
- single client account details.
- get invoice
- support ticket management.
- sso token generation.
- create client sso token
- support tickets
- single invoice details.
- retrieve a paginated list of client accounts.
- whmcs
- check domain
- validate client login credentials.
- create sso token
- client account management.
- retrieve a list of support tickets.
- invoice and billing management.
- perform a whois lookup on a domain name to check availability and registration status.
- retrieve a list of whmcs client accounts. use for customer lookup and account management workflows.
- list clients
- retrieve invoices with optional status and client filtering.
- system statistics and monitoring.
- retrieve whmcs support tickets, optionally filtered by client or status.
- create an sso token to enable a client to log into the whmcs client area without a password.
- list tickets
- retrieve a list of orders with optional filtering.
- order management.
- retrieve a specific invoice by id.
- retrieve whmcs system statistics and revenue metrics.
- perform a whois lookup on a domain name.
- create an sso token for client portal access.
- add client
- retrieve a list of whmcs orders, optionally filtered by client or status.
- create a new client account in whmcs.
- validate login
- open a new support ticket in whmcs on behalf of a client.
- retrieve detailed information for a specific whmcs client by id or email.
- retrieve a specific whmcs invoice by its id.
- support
- check domain whois
- client authentication.
- retrieve whmcs invoices, optionally filtered by client or payment status.
- validate a client's login credentials for authentication or sso workflows.
- open ticket
- client management
- list orders
- billing automation
- domain management
- retrieve whmcs system statistics including revenue metrics, active clients, and ticket counts.
- validate client login
- provisioning
- list invoices
- domain availability and whois lookup.
- web hosting
- get stats
slug: hosting-automation
source_filename: hosting-automation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: WHMCS Hosting Automation\n  description: Unified workflow for web hosting business automation combining client onboarding, billing management, support\n    ticket handling, and domain management via WHMCS. Designed for hosting provider operations teams and resellers.\n  tags:\n  - Web Hosting\n  - Billing Automation\n  - Client Management\n  - Domain Management\n  - Support\n  - WHMCS\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    WHMCS_API_IDENTIFIER: WHMCS_API_IDENTIFIER\n    WHMCS_API_SECRET: WHMCS_API_SECRET\n    WHMCS_BASE_URL: WHMCS_BASE_URL\ncapability:\n  consumes:\n  - type: http\n    namespace: whmcs\n    baseUri: '{{env.WHMCS_BASE_URL}}/includes/api.php'\n    description: WHMCS automation platform API for web hosting businesses.\n    authentication:\n      type: apikey\n      key: identifier\n      value: '{{env.WHMCS_API_IDENTIFIER}}'\n      placement: body\n    resources:\n    -\
  \ name: clients\n      path: ?action=GetClients\n      description: Client account management operations.\n      operations:\n      - name: get-clients\n        method: POST\n        description: Retrieve a list of client accounts.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        - name: limitstart\n          in: body\n          type: integer\n          required: false\n          description: Pagination start offset.\n        - name: limitnum\n          in: body\n          type: integer\n          required: false\n          description: Number of records to return.\n  \
  \      outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-client-details\n        method: POST\n        description: Retrieve detailed information for a specific client.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        - name: clientid\n          in: body\n          type: integer\n          required: false\n          description: Client ID to retrieve.\n        - name: email\n          in: body\n          type: string\n          required: false\n          description: Client email address.\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: add-client\n        method: POST\n        description: Add a new client account to WHMCS.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            firstname: '{{tools.firstname}}'\n            lastname: '{{tools.lastname}}'\n            email: '{{tools.email}}'\n\
  \            address1: '{{tools.address1}}'\n            city: '{{tools.city}}'\n            country: '{{tools.country}}'\n            postcode: '{{tools.postcode}}'\n            phonenumber: '{{tools.phonenumber}}'\n            password2: '{{tools.password2}}'\n    - name: orders\n      path: ?action=GetOrders\n      description: Order management operations.\n      operations:\n      - name: get-orders\n        method: POST\n        description: Retrieve a list of orders.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        - name: userid\n          in: body\n          type:\
  \ integer\n          required: false\n          description: Filter by client user ID.\n        - name: status\n          in: body\n          type: string\n          required: false\n          description: Filter by order status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: invoices\n      path: ?action=GetInvoices\n      description: Invoice and billing operations.\n      operations:\n      - name: get-invoices\n        method: POST\n        description: Retrieve a list of invoices.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n\
  \          description: Response format (json).\n        - name: userid\n          in: body\n          type: integer\n          required: false\n          description: Filter by client user ID.\n        - name: status\n          in: body\n          type: string\n          required: false\n          description: Filter by invoice status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-invoice\n        method: POST\n        description: Retrieve a specific invoice by ID.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description:\
  \ Response format (json).\n        - name: invoiceid\n          in: body\n          type: integer\n          required: true\n          description: Invoice ID to retrieve.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: tickets\n      path: ?action=GetTickets\n      description: Support ticket operations.\n      operations:\n      - name: get-tickets\n        method: POST\n        description: Retrieve a list of support tickets.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        -\
  \ name: clientid\n          in: body\n          type: integer\n          required: false\n          description: Filter by client ID.\n        - name: status\n          in: body\n          type: string\n          required: false\n          description: Filter by ticket status.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: open-ticket\n        method: POST\n        description: Open a new support ticket.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            deptid: '{{tools.deptid}}'\n            subject: '{{tools.subject}}'\n            message: '{{tools.message}}'\n            priority: '{{tools.priority}}'\n            clientid: '{{tools.clientid}}'\n    - name: domains\n      path: ?action=DomainWhois\n      description: Domain registration and management operations.\n      operations:\n      - name: domain-whois\n        method: POST\n        description: Perform a WHOIS lookup on a domain.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n\
  \          required: true\n          description: Response format (json).\n        - name: domain\n          in: body\n          type: string\n          required: true\n          description: Domain name to look up.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: system\n      path: ?action=GetStats\n      description: System administration and statistics.\n      operations:\n      - name: get-stats\n        method: POST\n        description: Retrieve WHMCS system statistics and dashboard data.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required:\
  \ true\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: whmcs-details\n        method: POST\n        description: Retrieve WHMCS installation version and configuration details.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: authentication\n      path: ?action=ValidateLogin\n      description: Authentication\
  \ and SSO operations.\n      operations:\n      - name: validate-login\n        method: POST\n        description: Validate a client's login credentials.\n        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            email: '{{tools.email}}'\n            password2: '{{tools.password2}}'\n      - name: create-sso-token\n        method: POST\n        description: Create a single sign-on token for a client.\n\
  \        inputParameters:\n        - name: identifier\n          in: body\n          type: string\n          required: true\n          description: API credential identifier.\n        - name: secret\n          in: body\n          type: string\n          required: true\n          description: API credential secret.\n        - name: responsetype\n          in: body\n          type: string\n          required: true\n          description: Response format (json).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: form\n          data:\n            client_id: '{{tools.client_id}}'\n            sso_destination: '{{tools.sso_destination}}'\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: hosting-automation-api\n    description: Unified REST API for WHMCS hosting business automation.\n    resources:\n    - path: /v1/clients\n      name: clients\n      description: Client account\
  \ management.\n      operations:\n      - method: GET\n        name: list-clients\n        description: Retrieve a paginated list of client accounts.\n        call: whmcs.get-clients\n        with:\n          limitstart: rest.limitstart\n          limitnum: rest.limitnum\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/clients/{id}\n      name: client-details\n      description: Single client account details.\n      operations:\n      - method: GET\n        name: get-client\n        description: Retrieve detailed information for a specific client.\n        call: whmcs.get-client-details\n        with:\n          clientid: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/orders\n      name: orders\n      description: Order management.\n      operations:\n      - method: GET\n        name: list-orders\n        description: Retrieve a list of orders with optional filtering.\n        call: whmcs.get-orders\n\
  \        with:\n          userid: rest.userid\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices\n      name: invoices\n      description: Invoice and billing management.\n      operations:\n      - method: GET\n        name: list-invoices\n        description: Retrieve invoices with optional status and client filtering.\n        call: whmcs.get-invoices\n        with:\n          userid: rest.userid\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/invoices/{id}\n      name: invoice-details\n      description: Single invoice details.\n      operations:\n      - method: GET\n        name: get-invoice\n        description: Retrieve a specific invoice by ID.\n        call: whmcs.get-invoice\n        with:\n          invoiceid: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tickets\n     \
  \ name: tickets\n      description: Support ticket management.\n      operations:\n      - method: GET\n        name: list-tickets\n        description: Retrieve a list of support tickets.\n        call: whmcs.get-tickets\n        with:\n          clientid: rest.clientid\n          status: rest.status\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: open-ticket\n        description: Open a new support ticket.\n        call: whmcs.open-ticket\n        with:\n          deptid: rest.deptid\n          subject: rest.subject\n          message: rest.message\n          priority: rest.priority\n          clientid: rest.clientid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/domains/whois\n      name: domain-whois\n      description: Domain availability and WHOIS lookup.\n      operations:\n      - method: GET\n        name: check-domain\n        description: Perform a WHOIS lookup on a domain\
  \ name.\n        call: whmcs.domain-whois\n        with:\n          domain: rest.domain\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/system/stats\n      name: system-stats\n      description: System statistics and monitoring.\n      operations:\n      - method: GET\n        name: get-stats\n        description: Retrieve WHMCS system statistics and revenue metrics.\n        call: whmcs.get-stats\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/validate\n      name: auth-validate\n      description: Client authentication.\n      operations:\n      - method: POST\n        name: validate-login\n        description: Validate client login credentials.\n        call: whmcs.validate-login\n        with:\n          email: rest.email\n          password2: rest.password2\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/auth/sso\n      name: sso-token\n      description:\
  \ SSO token generation.\n      operations:\n      - method: POST\n        name: create-sso-token\n        description: Create an SSO token for client portal access.\n        call: whmcs.create-sso-token\n        with:\n          client_id: rest.client_id\n          sso_destination: rest.sso_destination\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: hosting-automation-mcp\n    transport: http\n    description: MCP server for AI-assisted WHMCS hosting business automation.\n    tools:\n    - name: list-clients\n      description: Retrieve a list of WHMCS client accounts. Use for customer lookup and account management workflows.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-clients\n      with:\n        limitstart: tools.limitstart\n        limitnum: tools.limitnum\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-client-details\n      description:\
  \ Retrieve detailed information for a specific WHMCS client by ID or email.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-client-details\n      with:\n        clientid: tools.clientid\n        email: tools.email\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: add-client\n      description: Create a new client account in WHMCS.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: whmcs.add-client\n      with:\n        firstname: tools.firstname\n        lastname: tools.lastname\n        email: tools.email\n        address1: tools.address1\n        city: tools.city\n        country: tools.country\n        postcode: tools.postcode\n        phonenumber: tools.phonenumber\n        password2: tools.password2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-orders\n      description: Retrieve a list of WHMCS orders, optionally filtered\
  \ by client or status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-orders\n      with:\n        userid: tools.userid\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-invoices\n      description: Retrieve WHMCS invoices, optionally filtered by client or payment status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-invoices\n      with:\n        userid: tools.userid\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-invoice\n      description: Retrieve a specific WHMCS invoice by its ID.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-invoice\n      with:\n        invoiceid: tools.invoiceid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-tickets\n      description: Retrieve WHMCS support tickets, optionally\
  \ filtered by client or status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-tickets\n      with:\n        clientid: tools.clientid\n        status: tools.status\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: open-ticket\n      description: Open a new support ticket in WHMCS on behalf of a client.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: whmcs.open-ticket\n      with:\n        deptid: tools.deptid\n        subject: tools.subject\n        message: tools.message\n        priority: tools.priority\n        clientid: tools.clientid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: check-domain-whois\n      description: Perform a WHOIS lookup on a domain name to check availability and registration status.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.domain-whois\n      with:\n        domain:\
  \ tools.domain\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-system-stats\n      description: Retrieve WHMCS system statistics including revenue metrics, active clients, and ticket counts.\n      hints:\n        readOnly: true\n        openWorld: true\n      call: whmcs.get-stats\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: validate-client-login\n      description: Validate a client's login credentials for authentication or SSO workflows.\n      hints:\n        readOnly: true\n        openWorld: false\n      call: whmcs.validate-login\n      with:\n        email: tools.email\n        password2: tools.password2\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-client-sso-token\n      description: Create an SSO token to enable a client to log into the WHMCS client area without a password.\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n\
  \      call: whmcs.create-sso-token\n      with:\n        client_id: tools.client_id\n        sso_destination: tools.sso_destination\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/whmcs/refs/heads/main/capabilities/hosting-automation.yaml
tags:
- Web Hosting
- Billing Automation
- Client Management
- Domain Management
- Support
- WHMCS
tools:
- description: Retrieve a list of WHMCS client accounts. Use for customer lookup and account management workflows.
  hints:
    openWorld: true
    readOnly: true
  name: list-clients
- description: Retrieve detailed information for a specific WHMCS client by ID or email.
  hints:
    openWorld: true
    readOnly: true
  name: get-client-details
- description: Create a new client account in WHMCS.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: add-client
- description: Retrieve a list of WHMCS orders, optionally filtered by client or status.
  hints:
    openWorld: true
    readOnly: true
  name: list-orders
- description: Retrieve WHMCS invoices, optionally filtered by client or payment status.
  hints:
    openWorld: true
    readOnly: true
  name: list-invoices
- description: Retrieve a specific WHMCS invoice by its ID.
  hints:
    openWorld: true
    readOnly: true
  name: get-invoice
- description: Retrieve WHMCS support tickets, optionally filtered by client or status.
  hints:
    openWorld: true
    readOnly: true
  name: list-tickets
- description: Open a new support ticket in WHMCS on behalf of a client.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: open-ticket
- description: Perform a WHOIS lookup on a domain name to check availability and registration status.
  hints:
    openWorld: true
    readOnly: true
  name: check-domain-whois
- description: Retrieve WHMCS system statistics including revenue metrics, active clients, and ticket counts.
  hints:
    openWorld: true
    readOnly: true
  name: get-system-stats
- description: Validate a client's login credentials for authentication or SSO workflows.
  hints:
    openWorld: false
    readOnly: true
  name: validate-client-login
- description: Create an SSO token to enable a client to log into the WHMCS client area without a password.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-client-sso-token
---
