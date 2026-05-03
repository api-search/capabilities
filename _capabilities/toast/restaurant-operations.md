---
categories: []
consumed_apis:
- toast-orders
- toast-labor
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
- point of sale
- manages daily restaurant operations, staff, and order flow
- builds third-party integrations with the toast platform
- list payments
- create a new employee record at a restaurant
- update employee
- toast
- list payment records for a restaurant
- orders
- get payment identifiers
- list restaurant orders
- get restaurant order
- restaurant orders
- get a specific employee record
- restaurants
- get employee details
- get order payment
- Restaurant Manager
- restaurant order creation, tracking, and payment processing
- menu items, modifiers, and pricing management
- get multiple restaurant orders
- monitors multi-location restaurant performance and staff
- hospitality
- update employee information
- restaurant employees
- get details of a specific restaurant order
- labor
- get order
- get details of a specific payment
- list employees
- individual restaurant order
- list all employees at a restaurant location
- get a specific restaurant order
- employee records, scheduling, and shift management
- day-to-day restaurant operations including order monitoring and staff management
- individual employee
- get employee
- list restaurant employees
- list order payments
- location settings, availability, and restaurant metadata
- order payments
- Operations Team
- get multiple orders for a restaurant in a date range
- create employee
- food service
- list orders
- restaurant
- create a new employee
slug: restaurant-operations
source_filename: restaurant-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Toast Restaurant Operations\"\n  description: \"Unified workflow capability combining Toast Orders and Labor APIs for day-to-day restaurant operations management. Enables operators to monitor orders, manage payments, and oversee staff from a single interface. Used by restaurant managers and operations teams.\"\n  tags:\n    - Toast\n    - Restaurant\n    - Orders\n    - Labor\n    - Point of Sale\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys:\n      TOAST_CLIENT_ID: TOAST_CLIENT_ID\n      TOAST_CLIENT_SECRET: TOAST_CLIENT_SECRET\n      TOAST_RESTAURANT_GUID: TOAST_RESTAURANT_GUID\n      TOAST_ACCESS_TOKEN: TOAST_ACCESS_TOKEN\n\ncapability:\n  consumes:\n    - import: toast-orders\n      location: ./shared/orders.yaml\n    - import: toast-labor\n      location: ./shared/labor.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: restaurant-operations-api\n     \
  \ description: \"Unified REST API for Toast restaurant operations.\"\n      resources:\n        - path: /v1/orders\n          name: orders\n          description: \"Restaurant orders\"\n          operations:\n            - method: GET\n              name: list-orders\n              description: \"Get multiple restaurant orders\"\n              call: \"toast-orders.getOrdersBulk\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/orders/{guid}\n          name: order\n          description: \"Individual restaurant order\"\n          operations:\n            - method: GET\n              name: get-order\n              description: \"Get a specific restaurant order\"\n              call: \"toast-orders.getOrder\"\n              with:\n                guid: \"rest.guid\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/payments\n          name: payments\n\
  \          description: \"Order payments\"\n          operations:\n            - method: GET\n              name: list-payments\n              description: \"Get payment identifiers\"\n              call: \"toast-orders.getPayments\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/employees\n          name: employees\n          description: \"Restaurant employees\"\n          operations:\n            - method: GET\n              name: list-employees\n              description: \"List restaurant employees\"\n              call: \"toast-labor.listEmployees\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n            - method: POST\n              name: create-employee\n              description: \"Create a new employee\"\n              call: \"toast-labor.createEmployee\"\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n\n        - path: /v1/employees/{id}\n          name: employee\n          description: \"Individual employee\"\n          operations:\n            - method: GET\n              name: get-employee\n              description: \"Get employee details\"\n              call: \"toast-labor.getEmployee\"\n              with:\n                employeeId: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: restaurant-operations-mcp\n      transport: http\n      description: \"MCP server for AI-assisted restaurant operations management.\"\n      tools:\n        - name: list-restaurant-orders\n          description: \"Get multiple orders for a restaurant in a date range\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toast-orders.getOrdersBulk\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\
  \n        - name: get-restaurant-order\n          description: \"Get details of a specific restaurant order\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toast-orders.getOrder\"\n          with:\n            guid: \"tools.guid\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-order-payments\n          description: \"List payment records for a restaurant\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toast-orders.getPayments\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-order-payment\n          description: \"Get details of a specific payment\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toast-orders.getPayment\"\n          with:\n            guid: \"tools.guid\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n        - name: list-employees\n          description: \"List all employees at a restaurant location\"\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"toast-labor.listEmployees\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n        - name: get-employee\n          description: \"Get a specific employee record\"\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"toast-labor.getEmployee\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-employee\n          description: \"Create a new employee record at a restaurant\"\n          hints:\n            readOnly: false\n            openWorld: false\n          call: \"toast-labor.createEmployee\"\n          outputParameters:\n            - type: object\n     \
  \         mapping: \"$.\"\n        - name: update-employee\n          description: \"Update employee information\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"toast-labor.updateEmployee\"\n          with:\n            employeeId: \"tools.employeeId\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
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
