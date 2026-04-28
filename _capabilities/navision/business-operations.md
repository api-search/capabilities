---
categories:
- procurement-supply-chain
consumed_apis:
- business-central-v2
description: Unified workflow for day-to-day business operations in Dynamics 365 Business Central combining the Business Central API v2.0 for managing customers, vendors, items, orders, invoices, and financials. Used by accountants, sales teams, and operations managers.
layout: capability
name: Dynamics NAV Business Operations
operations:
- description: List available companies
  method: GET
  name: list-companies
  path: /v1/companies
- description: List all customers
  method: GET
  name: list-customers
  path: /v1/customers
- description: Create a customer
  method: POST
  name: create-customer
  path: /v1/customers
- description: Get a customer
  method: GET
  name: get-customer
  path: /v1/customers/{customer_id}
- description: List all vendors
  method: GET
  name: list-vendors
  path: /v1/vendors
- description: List all items
  method: GET
  name: list-items
  path: /v1/items
- description: List sales orders
  method: GET
  name: list-sales-orders
  path: /v1/sales-orders
- description: Create a sales order
  method: POST
  name: create-sales-order
  path: /v1/sales-orders
- description: List purchase orders
  method: GET
  name: list-purchase-orders
  path: /v1/purchase-orders
- description: List accounts
  method: GET
  name: list-accounts
  path: /v1/accounts
- description: List journals
  method: GET
  name: list-journals
  path: /v1/journals
- description: List sales invoices
  method: GET
  name: list-sales-invoices
  path: /v1/sales-invoices
personas: []
provider_name: Microsoft Dynamics NAV
provider_slug: navision
search_terms:
- list companies
- create purchase order
- microsoft
- general ledger accounts
- dynamics nav
- list inventory items
- customer management
- company information
- list customers
- sales invoices
- purchase orders
- general journals
- list journals
- finance
- create a sales order
- create a new vendor
- list vendors
- create a new sales order
- inventory
- list employees
- single customer
- create vendor
- navision
- list purchase invoices
- list all items
- list sales orders
- list purchase orders
- list all vendors
- create a new purchase order
- list general ledger accounts
- vendor management
- sales orders
- business central
- list all sales orders
- business management
- create customer
- create sales order
- list accounts
- create a customer
- list all purchase orders
- list all employees
- list general journals
- create a new customer
- list available companies
- create item
- list all customers
- sales
- erp
- inventory items
- dynamics 365
- list items
- list sales invoices
- get customer
- create a new inventory item
- purchasing
- get a customer by id
- get a customer
slug: business-operations
tags:
- Business Central
- Dynamics 365
- ERP
- Finance
- Sales
- Purchasing
tools:
- description: List available companies
  hints:
    idempotent: true
    readOnly: true
  name: list-companies
- description: List all customers
  hints:
    idempotent: true
    readOnly: true
  name: list-customers
- description: Create a new customer
  hints:
    readOnly: false
  name: create-customer
- description: Get a customer by ID
  hints:
    idempotent: true
    readOnly: true
  name: get-customer
- description: List all vendors
  hints:
    idempotent: true
    readOnly: true
  name: list-vendors
- description: Create a new vendor
  hints:
    readOnly: false
  name: create-vendor
- description: List inventory items
  hints:
    idempotent: true
    readOnly: true
  name: list-items
- description: Create a new inventory item
  hints:
    readOnly: false
  name: create-item
- description: List all sales orders
  hints:
    idempotent: true
    readOnly: true
  name: list-sales-orders
- description: Create a new sales order
  hints:
    readOnly: false
  name: create-sales-order
- description: List all purchase orders
  hints:
    idempotent: true
    readOnly: true
  name: list-purchase-orders
- description: Create a new purchase order
  hints:
    readOnly: false
  name: create-purchase-order
- description: List general ledger accounts
  hints:
    idempotent: true
    readOnly: true
  name: list-accounts
- description: List general journals
  hints:
    idempotent: true
    readOnly: true
  name: list-journals
- description: List sales invoices
  hints:
    idempotent: true
    readOnly: true
  name: list-sales-invoices
- description: List purchase invoices
  hints:
    idempotent: true
    readOnly: true
  name: list-purchase-invoices
- description: List all employees
  hints:
    idempotent: true
    readOnly: true
  name: list-employees
---
