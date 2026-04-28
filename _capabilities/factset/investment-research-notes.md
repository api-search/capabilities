---
categories: []
consumed_apis:
- factset-irn-config
- factset-irn-contacts
- factset-irn-symbols
- factset-irn-meetings
- factset-irn-notes
description: Unified workflow for managing internal research notes including configuration, contacts, custom symbols, meetings, and notes. Used by research analysts and relationship managers.
layout: capability
name: FactSet Investment Research Notes
operations:
- description: List IRN contacts.
  method: GET
  name: list-contacts
  path: /v1/irn-contacts
- description: List IRN meetings.
  method: GET
  name: list-meetings
  path: /v1/irn-meetings
- description: List IRN notes.
  method: GET
  name: list-notes
  path: /v1/irn-notes
personas: []
provider_name: Factset
provider_slug: factset
search_terms:
- list irn contacts
- list irn custom symbols.
- irn
- list irn meetings
- list irn notes
- list irn meetings.
- financial data
- research notes
- list contacts
- list notes
- list irn contacts.
- list meetings
- get irn config
- irn note management.
- list irn notes.
- irn meeting management.
- market data
- research
- list irn symbols
- investment analytics
- get irn configuration.
- crm
- financial
- irn contact management.
- portfolio analytics
- factset
slug: investment-research-notes
tags:
- FactSet
- IRN
- Research Notes
- CRM
tools:
- description: Get IRN configuration.
  hints:
    readOnly: true
  name: get-irn-config
- description: List IRN contacts.
  hints:
    readOnly: true
  name: list-irn-contacts
- description: List IRN custom symbols.
  hints:
    readOnly: true
  name: list-irn-symbols
- description: List IRN meetings.
  hints:
    readOnly: true
  name: list-irn-meetings
- description: List IRN notes.
  hints:
    readOnly: true
  name: list-irn-notes
---
