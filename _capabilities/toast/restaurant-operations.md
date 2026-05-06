---
categories: []
consumed_apis: []
description: Unified workflow capability combining Toast Orders and Labor APIs for day-to-day restaurant operations management. Enables operators to monitor orders, manage payments, and oversee staff from a single interface. Used by restaurant managers and operations teams.
layout: capability
name: Toast Restaurant Operations
operations:
- description: Get multiple restaurant orders
  method: GET
  name: list-orders
  path: /v1/orders
- description: Get a specific restaurant order
  method: GET
  name: get-order
  path: /v1/orders/{guid}
- description: Get payment identifiers
  method: GET
  name: list-payments
  path: /v1/payments
- description: List restaurant employees
  method: GET
  name: list-employees
  path: /v1/employees
- description: Create a new employee
  method: POST
  name: create-employee
  path: /v1/employees
- description: Get employee details
  method: GET
  name: get-employee
  path: /v1/employees/{id}
personas: []
provider_name: Toast
provider_slug: toast
search_terms:
- restaurant order creation, tracking, and payment processing
- update employee
- list payment records for a restaurant
- Restaurant Manager
- restaurant employees
- Operations Team
- get order payment
- create a new employee
- update employee information
- get order
- get a specific employee record
- order payments
- employee records, scheduling, and shift management
- get multiple orders for a restaurant in a date range
- get multiple restaurant orders
- restaurant orders
- get restaurant order
- restaurants
- individual employee
- list payments
- create a new employee record at a restaurant
- day-to-day restaurant operations including order monitoring and staff management
- get details of a specific payment
- restaurant
- create employee
- individual restaurant order
- get a specific restaurant order
- toast
- hospitality
- get employee
- point of sale
- list restaurant employees
- list employees
- list restaurant orders
- monitors multi-location restaurant performance and staff
- menu items, modifiers, and pricing management
- list orders
- food service
- builds third-party integrations with the toast platform
- list order payments
- manages daily restaurant operations, staff, and order flow
- orders
- list all employees at a restaurant location
- get employee details
- labor
- location settings, availability, and restaurant metadata
- get details of a specific restaurant order
- get payment identifiers
slug: restaurant-operations
source_filename: restaurant-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Toast Restaurant Operations\n  description: Unified workflow capability combining Toast Orders and Labor APIs for day-to-day restaurant operations management.\n    Enables operators to monitor orders, manage payments, and oversee staff from a single interface. Used by restaurant managers\n    and operations teams.\n  tags:\n  - Toast\n  - Restaurant\n  - Orders\n  - Labor\n  - Point of Sale\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    TOAST_CLIENT_ID: TOAST_CLIENT_ID\n    TOAST_CLIENT_SECRET: TOAST_CLIENT_SECRET\n    TOAST_RESTAURANT_GUID: TOAST_RESTAURANT_GUID\n    TOAST_ACCESS_TOKEN: TOAST_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: toast-orders\n    baseUri: https://ws-api.toasttab.com\n    description: Toast Orders API\n    authentication:\n      type: bearer\n      token: '{{TOAST_ACCESS_TOKEN}}'\n    resources:\n    - name: orders\n      path: /orders\n    \
  \  description: Restaurant orders\n      operations:\n      - name: getOrder\n        method: GET\n        description: Toast Get an Order\n        inputParameters:\n        - name: guid\n          in: path\n          type: string\n          required: true\n          description: The GUID of the order\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getOrdersBulk\n        method: GET\n        description: Toast Get Multiple Orders\n        inputParameters:\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        - name: startDate\n          in: query\n          type: string\n          required: false\n          description: Start date\
  \ for order query\n        - name: endDate\n          in: query\n          type: string\n          required: false\n          description: End date for order query\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n    - name: payments\n      path: /payments\n      description: Order payments\n      operations:\n      - name: getPayments\n        method: GET\n        description: Toast Get Payment Identifiers\n        inputParameters:\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: array\n          value: $.\n      - name: getPayment\n        method: GET\n        description: Toast Get a Payment\n        inputParameters:\n        - name: guid\n          in: path\n          type: string\n          required:\
  \ true\n          description: Payment GUID\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: toast-labor\n    baseUri: https://ws-api.toasttab.com\n    description: Toast Labor API\n    authentication:\n      type: bearer\n      token: '{{TOAST_ACCESS_TOKEN}}'\n    resources:\n    - name: employees\n      path: /employees\n      description: Restaurant employees\n      operations:\n      - name: listEmployees\n        method: GET\n        description: Toast List Employees\n        inputParameters:\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: array\n          value: $.\n      - name: createEmployee\n        method: POST\n        description: Toast Create an Employee\n        inputParameters:\n        - name: Toast-Restaurant-External-ID\n          in: header\n          type: string\n          required: true\n          description: Restaurant GUID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            firstName: '{{tools.firstName}}'\n            lastName: '{{tools.lastName}}'\n            email: '{{tools.email}}'\n      - name: getEmployee\n        method: GET\n        description: Toast Get an Employee\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: updateEmployee\n        method: PATCH\n        description: Toast Update an Employee\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteEmployee\n        method: DELETE\n        description: Toast Delete an Employee\n        inputParameters:\n        - name: employeeId\n          in: path\n          type: string\n          required: true\n          description: Employee identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: restaurant-operations-api\n    description: Unified REST API for Toast restaurant operations.\n    resources:\n    - path:\
  \ /v1/orders\n      name: orders\n      description: Restaurant orders\n      operations:\n      - method: GET\n        name: list-orders\n        description: Get multiple restaurant orders\n        call: toast-orders.getOrdersBulk\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/orders/{guid}\n      name: order\n      description: Individual restaurant order\n      operations:\n      - method: GET\n        name: get-order\n        description: Get a specific restaurant order\n        call: toast-orders.getOrder\n        with:\n          guid: rest.guid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/payments\n      name: payments\n      description: Order payments\n      operations:\n      - method: GET\n        name: list-payments\n        description: Get payment identifiers\n        call: toast-orders.getPayments\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path:\
  \ /v1/employees\n      name: employees\n      description: Restaurant employees\n      operations:\n      - method: GET\n        name: list-employees\n        description: List restaurant employees\n        call: toast-labor.listEmployees\n        outputParameters:\n        - type: array\n          mapping: $.\n      - method: POST\n        name: create-employee\n        description: Create a new employee\n        call: toast-labor.createEmployee\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/employees/{id}\n      name: employee\n      description: Individual employee\n      operations:\n      - method: GET\n        name: get-employee\n        description: Get employee details\n        call: toast-labor.getEmployee\n        with:\n          employeeId: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: restaurant-operations-mcp\n    transport: http\n    description:\
  \ MCP server for AI-assisted restaurant operations management.\n    tools:\n    - name: list-restaurant-orders\n      description: Get multiple orders for a restaurant in a date range\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toast-orders.getOrdersBulk\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-restaurant-order\n      description: Get details of a specific restaurant order\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toast-orders.getOrder\n      with:\n        guid: tools.guid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-order-payments\n      description: List payment records for a restaurant\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toast-orders.getPayments\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-order-payment\n      description: Get details of a specific payment\n\
  \      hints:\n        readOnly: true\n        openWorld: false\n      call: toast-orders.getPayment\n      with:\n        guid: tools.guid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-employees\n      description: List all employees at a restaurant location\n      hints:\n        readOnly: true\n        openWorld: true\n      call: toast-labor.listEmployees\n      outputParameters:\n      - type: array\n        mapping: $.\n    - name: get-employee\n      description: Get a specific employee record\n      hints:\n        readOnly: true\n        openWorld: false\n      call: toast-labor.getEmployee\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-employee\n      description: Create a new employee record at a restaurant\n      hints:\n        readOnly: false\n        openWorld: false\n      call: toast-labor.createEmployee\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: update-employee\n      description: Update employee information\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: toast-labor.updateEmployee\n      with:\n        employeeId: tools.employeeId\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/toast/refs/heads/main/capabilities/restaurant-operations.yaml
tags:
- Toast
- Restaurant
- Orders
- Labor
- Point of Sale
tools:
- description: Get multiple orders for a restaurant in a date range
  hints:
    openWorld: true
    readOnly: true
  name: list-restaurant-orders
- description: Get details of a specific restaurant order
  hints:
    openWorld: false
    readOnly: true
  name: get-restaurant-order
- description: List payment records for a restaurant
  hints:
    openWorld: true
    readOnly: true
  name: list-order-payments
- description: Get details of a specific payment
  hints:
    openWorld: false
    readOnly: true
  name: get-order-payment
- description: List all employees at a restaurant location
  hints:
    openWorld: true
    readOnly: true
  name: list-employees
- description: Get a specific employee record
  hints:
    openWorld: false
    readOnly: true
  name: get-employee
- description: Create a new employee record at a restaurant
  hints:
    openWorld: false
    readOnly: false
  name: create-employee
- description: Update employee information
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-employee
---
