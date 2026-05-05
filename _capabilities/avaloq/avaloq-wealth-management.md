---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Avaloq Wealth Management
operations: []
personas: []
provider_name: Avaloq
provider_slug: avaloq
search_terms:
- regulatory compliance, aml, and risk management.
- end-to-end workflow for client account management, transactions, and payment processing.
- digital banking
- payments
- banking
- investment portfolio and asset management.
- order management and trade execution.
- handles back-office operations, payments, and settlements.
- manages client portfolios and investment strategies.
- core banking operations including accounts, transactions, and customer management.
- maintains client relationships and coordinates banking services.
- payment processing for domestic and international transfers.
- financial services
- fintech
- wealth management
slug: avaloq-wealth-management
source_filename: avaloq-wealth-management.yaml
source_heading: Capability Spec
source_yaml: "name: Avaloq Wealth Management Workflow\ndescription: End-to-end wealth management workflow combining banking, payments, and client management for financial institutions.\npersona:\n  - Wealth Manager\n  - Relationship Advisor\n  - Operations Specialist\napis:\n  - name: Avaloq Banking API\n    shared: capabilities/shared/banking.yaml\n  - name: Avaloq Payments API\n    shared: capabilities/shared/payments.yaml\nservers:\n  rest:\n    port: 8080\n  mcp:\n    port: 9090\ntools:\n  - name: listAccounts\n    description: List all accounts for a customer.\n    source: banking\n    operationId: listAccounts\n  - name: getAccount\n    description: Get account details and balance.\n    source: banking\n    operationId: getAccount\n  - name: listTransactions\n    description: Retrieve account transaction history.\n    source: banking\n    operationId: listTransactions\n  - name: listCustomers\n    description: List customers in the banking system.\n    source: banking\n    operationId:\
  \ listCustomers\n  - name: initiatePayment\n    description: Submit a new payment instruction.\n    source: payments\n    operationId: initiatePayment\n  - name: listPayments\n    description: List payment instructions and their statuses.\n    source: payments\n    operationId: listPayments\n  - name: getPayment\n    description: Get details of a specific payment.\n    source: payments\n    operationId: getPayment\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/avaloq/refs/heads/main/capabilities/avaloq-wealth-management.yaml
tags: []
tools: []
---
