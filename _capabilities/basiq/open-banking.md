---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Open Banking
operations: []
personas: []
provider_name: Basiq
provider_slug: basiq
search_terms:
- consumer-consented access to bank account and transaction data
- australia
- open banking
- income verification and expense analysis for lending decisions
- Fintech Developer
- Lender
- banking
- cdr
- financial advisor using transaction data for budgeting and planning
- transactions
- lender using bank data for income verification and affordability assessment
- financial data
- fintech
- Financial Planner
- bank data retrieval, income verification, and affordability assessment
- developer building financial apps leveraging open banking data
slug: open-banking
source_yaml: "name: Open Banking\ndescription: >-\n  Workflow capability for building open banking and financial data applications\n  using the Basiq API. Covers bank connection, account data retrieval, transaction\n  history, and affordability assessment for Australian and New Zealand consumers.\nversion: \"1.0\"\napis:\n  - basiq:basiq\npersonas:\n  - Fintech Developer\n  - Lender\n  - Financial Planner\ntools:\n  - name: create_user\n    description: Register a new end consumer to initiate their open banking journey.\n    operation: createUser\n    api: basiq:basiq\n  - name: connect_bank\n    description: Connect a user's bank account using institution credentials or CDR consent flow.\n    operation: createConnection\n    api: basiq:basiq\n  - name: get_accounts\n    description: Retrieve all bank accounts for a connected user including balances.\n    operation: listAccounts\n    api: basiq:basiq\n  - name: get_transactions\n    description: Fetch transaction history for a user across\
  \ all connected accounts.\n    operation: listTransactions\n    api: basiq:basiq\n  - name: verify_income\n    description: Get income verification report derived from transaction pattern analysis.\n    operation: getIncomeVerification\n    api: basiq:basiq\n  - name: analyze_expenses\n    description: Get categorized monthly expense report for affordability assessment.\n    operation: getExpenses\n    api: basiq:basiq\n  - name: manage_connections\n    description: List, refresh, and manage user bank connections.\n    operation: listConnections\n    api: basiq:basiq\nmcp:\n  adapter: basiq-mcp\n  namespace: basiq-api\n  port: 9080\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/basiq/refs/heads/main/capabilities/open-banking.yaml
tags: []
tools: []
---
