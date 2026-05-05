---
categories:
- crm-sales
consumed_apis:
- crm-contacts-api
- crm-companies-api
- crm-deals-api
- crm-tickets-api
- crm-associations-api
- crm-search-api
- crm-lists-api
description: Unified CRM workflow for managing contacts, companies, deals, tickets, and their associations.
layout: capability
name: HubSpot CRM Management
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- hubspot list company associations
- hubspot batch create tickets
- deleteticketassociation
- hubspot list deals
- hubspot create a contact
- updatedeal
- batchcreatecompanies
- hubspot
- searchtickets
- searchcrmobjects
- listassociationlabels
- createticketassociation
- hubspot remove members from a list
- operations
- searchcompanies
- hubspot create a ticket association
- hubspot list associations for an object
- hubspot archive a deal
- content
- hubspot delete a company association
- crm
- hubspot batch read associations for multiple objects
- hubspot batch archive contacts
- batchreadtickets
- hubspot batch create contacts
- hubspot create a deal association
- hubspot update a deal
- hubspot batch read contacts
- hubspot delete a ticket association
- hubspot create a contact association
- batchreadcompanies
- hubspot search deals
- batchcreatedeals
- email marketing
- deleteticket
- hubspot batch archive tickets
- batchreadassociations
- hubspot delete a deal association
- commerce
- updatecompany
- marketing
- batchreadcontacts
- deletecompany
- hubspot get a list
- analytics
- hubspot get a contact
- hubspot add members to a list
- marketing automation
- createticket
- hubspot batch read companies
- hubspot list tickets
- hubspot get a deal
- listdealassociations
- hubspot delete a contact association
- getdeal
- listticketassociations
- updatecontact
- searchcontacts
- getticket
- hubspot create a deal
- hubspot search companies
- createobjectassociation
- batchupdatecompanies
- hubspot create a list
- deletecontact
- hubspot delete an association between objects
- createcompany
- addlistmembers
- hubspot batch read tickets
- sales
- batchcreateassociations
- listcompanies
- hubspot batch update contacts
- hubspot list ticket associations
- hubspot search contacts
- hubspot batch create deals
- deletedealassociation
- hubspot update a ticket
- batchreaddeals
- listobjectassociations
- hubspot search crm objects
- deletelist
- createcontactassociation
- getlistmemberships
- hubspot update a contact
- batcharchivecompanies
- batchupdatetickets
- hubspot archive a ticket
- hubspot search tickets
- deleteassociationlabel
- listcontactassociations
- hubspot create an association label
- hubspot list all lists
- hubspot list association labels
- batcharchiveassociations
- listassociationdefinitions
- batchupdatecontacts
- hubspot update a company
- hubspot batch update companies
- hubspot create a company
- createassociationlabel
- hubspot list contact associations
- listcompanyassociations
- hubspot get list members
- hubspot list companies
- listcontacts
- createlist
- batcharchivedeals
- createcompanyassociation
- updateticket
- batcharchivetickets
- batchcreatecontacts
- hubspot batch update deals
- createcontact
- hubspot create a company association
- contacts
- customer service
- hubspot delete a list
- deletecontactassociation
- hubspot list deal associations
- hubspot batch read deals
- hubspot create a ticket
- hubspot list all association definitions
- batchupdatedeals
- hubspot batch update tickets
- updateassociationlabel
- listdeals
- deletedeal
- listtickets
- createdealassociation
- hubspot batch create associations
- hubspot archive a company
- listlists
- hubspot update an association label
- hubspot batch create companies
- hubspot get a ticket
- hubspot delete an association label
- hubspot create an association between objects
- getcontact
- deletecompanyassociation
- hubspot batch archive deals
- hubspot list contacts
- getcompany
- createdeal
- searchdeals
- hubspot archive a contact
- hubspot batch archive companies
- deleteobjectassociation
- hubspot batch archive associations
- batcharchivecontacts
- removelistmembers
- getlist
- batchcreatetickets
- hubspot get a company
slug: crm-management
source_filename: crm-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha1\ninfo:\n  label: HubSpot CRM Management\n  description: Unified CRM workflow for managing contacts, companies, deals, tickets, and their associations.\n  tags:\n  - HubSpot\n  - CRM\n  - Sales\n  - Contacts\n  created: '2026-04-18'\n  modified: '2026-04-18'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - import: crm-contacts-api\n    location: ./shared/crm-contacts-api.yaml\n  - import: crm-companies-api\n    location: ./shared/crm-companies-api.yaml\n  - import: crm-deals-api\n    location: ./shared/crm-deals-api.yaml\n  - import: crm-tickets-api\n    location: ./shared/crm-tickets-api.yaml\n  - import: crm-associations-api\n    location: ./shared/crm-associations-api.yaml\n  - import: crm-search-api\n    location: ./shared/crm-search-api.yaml\n  - import: crm-lists-api\n    location: ./shared/crm-lists-api.yaml\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: crm-management-mcp\n\
  \    transport: http\n    description: MCP server for AI-assisted HubSpot CRM Management.\n    tools:\n    - name: listcontacts\n      description: HubSpot List Contacts\n      hints:\n        readOnly: true\n      call: crm-contacts-api.listcontacts\n    - name: createcontact\n      description: HubSpot Create a Contact\n      hints:\n        readOnly: false\n      call: crm-contacts-api.createcontact\n    - name: getcontact\n      description: HubSpot Get a Contact\n      hints:\n        readOnly: true\n      call: crm-contacts-api.getcontact\n    - name: updatecontact\n      description: HubSpot Update a Contact\n      hints:\n        readOnly: false\n      call: crm-contacts-api.updatecontact\n    - name: deletecontact\n      description: HubSpot Archive a Contact\n      hints:\n        destructive: true\n      call: crm-contacts-api.deletecontact\n    - name: batchreadcontacts\n      description: HubSpot Batch Read Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchreadcontacts\n\
  \    - name: batchcreatecontacts\n      description: HubSpot Batch Create Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchcreatecontacts\n    - name: batchupdatecontacts\n      description: HubSpot Batch Update Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchupdatecontacts\n    - name: batcharchivecontacts\n      description: HubSpot Batch Archive Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batcharchivecontacts\n    - name: searchcontacts\n      description: HubSpot Search Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.searchcontacts\n    - name: listcontactassociations\n      description: HubSpot List Contact Associations\n      hints:\n        readOnly: true\n      call: crm-contacts-api.listcontactassociations\n    - name: createcontactassociation\n      description: HubSpot Create a Contact Association\n      hints:\n        readOnly: false\n      call:\
  \ crm-contacts-api.createcontactassociation\n    - name: deletecontactassociation\n      description: HubSpot Delete a Contact Association\n      hints:\n        destructive: true\n      call: crm-contacts-api.deletecontactassociation\n    - name: listcompanies\n      description: HubSpot List Companies\n      hints:\n        readOnly: true\n      call: crm-companies-api.listcompanies\n    - name: createcompany\n      description: HubSpot Create a Company\n      hints:\n        readOnly: false\n      call: crm-companies-api.createcompany\n    - name: getcompany\n      description: HubSpot Get a Company\n      hints:\n        readOnly: true\n      call: crm-companies-api.getcompany\n    - name: updatecompany\n      description: HubSpot Update a Company\n      hints:\n        readOnly: false\n      call: crm-companies-api.updatecompany\n    - name: deletecompany\n      description: HubSpot Archive a Company\n      hints:\n        destructive: true\n      call: crm-companies-api.deletecompany\n\
  \    - name: batchreadcompanies\n      description: HubSpot Batch Read Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchreadcompanies\n    - name: batchcreatecompanies\n      description: HubSpot Batch Create Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchcreatecompanies\n    - name: batchupdatecompanies\n      description: HubSpot Batch Update Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchupdatecompanies\n    - name: batcharchivecompanies\n      description: HubSpot Batch Archive Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batcharchivecompanies\n    - name: searchcompanies\n      description: HubSpot Search Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.searchcompanies\n    - name: listcompanyassociations\n      description: HubSpot List Company Associations\n      hints:\n        readOnly: true\n      call:\
  \ crm-companies-api.listcompanyassociations\n    - name: createcompanyassociation\n      description: HubSpot Create a Company Association\n      hints:\n        readOnly: false\n      call: crm-companies-api.createcompanyassociation\n    - name: deletecompanyassociation\n      description: HubSpot Delete a Company Association\n      hints:\n        destructive: true\n      call: crm-companies-api.deletecompanyassociation\n    - name: listdeals\n      description: HubSpot List Deals\n      hints:\n        readOnly: true\n      call: crm-deals-api.listdeals\n    - name: createdeal\n      description: HubSpot Create a Deal\n      hints:\n        readOnly: false\n      call: crm-deals-api.createdeal\n    - name: getdeal\n      description: HubSpot Get a Deal\n      hints:\n        readOnly: true\n      call: crm-deals-api.getdeal\n    - name: updatedeal\n      description: HubSpot Update a Deal\n      hints:\n        readOnly: false\n      call: crm-deals-api.updatedeal\n    - name: deletedeal\n\
  \      description: HubSpot Archive a Deal\n      hints:\n        destructive: true\n      call: crm-deals-api.deletedeal\n    - name: batchreaddeals\n      description: HubSpot Batch Read Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batchreaddeals\n    - name: batchcreatedeals\n      description: HubSpot Batch Create Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batchcreatedeals\n    - name: batchupdatedeals\n      description: HubSpot Batch Update Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batchupdatedeals\n    - name: batcharchivedeals\n      description: HubSpot Batch Archive Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batcharchivedeals\n    - name: searchdeals\n      description: HubSpot Search Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.searchdeals\n    - name: listdealassociations\n      description: HubSpot List Deal Associations\n      hints:\n\
  \        readOnly: true\n      call: crm-deals-api.listdealassociations\n    - name: createdealassociation\n      description: HubSpot Create a Deal Association\n      hints:\n        readOnly: false\n      call: crm-deals-api.createdealassociation\n    - name: deletedealassociation\n      description: HubSpot Delete a Deal Association\n      hints:\n        destructive: true\n      call: crm-deals-api.deletedealassociation\n    - name: listtickets\n      description: HubSpot List Tickets\n      hints:\n        readOnly: true\n      call: crm-tickets-api.listtickets\n    - name: createticket\n      description: HubSpot Create a Ticket\n      hints:\n        readOnly: false\n      call: crm-tickets-api.createticket\n    - name: getticket\n      description: HubSpot Get a Ticket\n      hints:\n        readOnly: true\n      call: crm-tickets-api.getticket\n    - name: updateticket\n      description: HubSpot Update a Ticket\n      hints:\n        readOnly: false\n      call: crm-tickets-api.updateticket\n\
  \    - name: deleteticket\n      description: HubSpot Archive a Ticket\n      hints:\n        destructive: true\n      call: crm-tickets-api.deleteticket\n    - name: batchreadtickets\n      description: HubSpot Batch Read Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchreadtickets\n    - name: batchcreatetickets\n      description: HubSpot Batch Create Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchcreatetickets\n    - name: batchupdatetickets\n      description: HubSpot Batch Update Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchupdatetickets\n    - name: batcharchivetickets\n      description: HubSpot Batch Archive Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batcharchivetickets\n    - name: searchtickets\n      description: HubSpot Search Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.searchtickets\n    - name: listticketassociations\n\
  \      description: HubSpot List Ticket Associations\n      hints:\n        readOnly: true\n      call: crm-tickets-api.listticketassociations\n    - name: createticketassociation\n      description: HubSpot Create a Ticket Association\n      hints:\n        readOnly: false\n      call: crm-tickets-api.createticketassociation\n    - name: deleteticketassociation\n      description: HubSpot Delete a Ticket Association\n      hints:\n        destructive: true\n      call: crm-tickets-api.deleteticketassociation\n    - name: listobjectassociations\n      description: HubSpot List Associations for an Object\n      hints:\n        readOnly: true\n      call: crm-associations-api.listobjectassociations\n    - name: createobjectassociation\n      description: HubSpot Create an Association Between Objects\n      hints:\n        readOnly: false\n      call: crm-associations-api.createobjectassociation\n    - name: deleteobjectassociation\n      description: HubSpot Delete an Association Between\
  \ Objects\n      hints:\n        destructive: true\n      call: crm-associations-api.deleteobjectassociation\n    - name: batchreadassociations\n      description: HubSpot Batch Read Associations for Multiple Objects\n      hints:\n        readOnly: false\n      call: crm-associations-api.batchreadassociations\n    - name: batchcreateassociations\n      description: HubSpot Batch Create Associations\n      hints:\n        readOnly: false\n      call: crm-associations-api.batchcreateassociations\n    - name: batcharchiveassociations\n      description: HubSpot Batch Archive Associations\n      hints:\n        readOnly: false\n      call: crm-associations-api.batcharchiveassociations\n    - name: listassociationlabels\n      description: HubSpot List Association Labels\n      hints:\n        readOnly: true\n      call: crm-associations-api.listassociationlabels\n    - name: createassociationlabel\n      description: HubSpot Create an Association Label\n      hints:\n        readOnly: false\n\
  \      call: crm-associations-api.createassociationlabel\n    - name: updateassociationlabel\n      description: HubSpot Update an Association Label\n      hints:\n        readOnly: false\n      call: crm-associations-api.updateassociationlabel\n    - name: deleteassociationlabel\n      description: HubSpot Delete an Association Label\n      hints:\n        destructive: true\n      call: crm-associations-api.deleteassociationlabel\n    - name: listassociationdefinitions\n      description: HubSpot List All Association Definitions\n      hints:\n        readOnly: true\n      call: crm-associations-api.listassociationdefinitions\n    - name: searchcrmobjects\n      description: HubSpot Search CRM Objects\n      hints:\n        readOnly: false\n      call: crm-search-api.searchcrmobjects\n    - name: listlists\n      description: HubSpot List All Lists\n      hints:\n        readOnly: true\n      call: crm-lists-api.listlists\n    - name: createlist\n      description: HubSpot Create a List\n\
  \      hints:\n        readOnly: false\n      call: crm-lists-api.createlist\n    - name: getlist\n      description: HubSpot Get a List\n      hints:\n        readOnly: true\n      call: crm-lists-api.getlist\n    - name: deletelist\n      description: HubSpot Delete a List\n      hints:\n        destructive: true\n      call: crm-lists-api.deletelist\n    - name: getlistmemberships\n      description: HubSpot Get List Members\n      hints:\n        readOnly: true\n      call: crm-lists-api.getlistmemberships\n    - name: addlistmembers\n      description: HubSpot Add Members to a List\n      hints:\n        readOnly: false\n      call: crm-lists-api.addlistmembers\n    - name: removelistmembers\n      description: HubSpot Remove Members from a List\n      hints:\n        readOnly: false\n      call: crm-lists-api.removelistmembers\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/crm-management.yaml
tags:
- HubSpot
- CRM
- Sales
- Contacts
tools:
- description: HubSpot List Contacts
  hints:
    readOnly: true
  name: listcontacts
- description: HubSpot Create a Contact
  hints:
    readOnly: false
  name: createcontact
- description: HubSpot Get a Contact
  hints:
    readOnly: true
  name: getcontact
- description: HubSpot Update a Contact
  hints:
    readOnly: false
  name: updatecontact
- description: HubSpot Archive a Contact
  hints:
    destructive: true
  name: deletecontact
- description: HubSpot Batch Read Contacts
  hints:
    readOnly: false
  name: batchreadcontacts
- description: HubSpot Batch Create Contacts
  hints:
    readOnly: false
  name: batchcreatecontacts
- description: HubSpot Batch Update Contacts
  hints:
    readOnly: false
  name: batchupdatecontacts
- description: HubSpot Batch Archive Contacts
  hints:
    readOnly: false
  name: batcharchivecontacts
- description: HubSpot Search Contacts
  hints:
    readOnly: false
  name: searchcontacts
- description: HubSpot List Contact Associations
  hints:
    readOnly: true
  name: listcontactassociations
- description: HubSpot Create a Contact Association
  hints:
    readOnly: false
  name: createcontactassociation
- description: HubSpot Delete a Contact Association
  hints:
    destructive: true
  name: deletecontactassociation
- description: HubSpot List Companies
  hints:
    readOnly: true
  name: listcompanies
- description: HubSpot Create a Company
  hints:
    readOnly: false
  name: createcompany
- description: HubSpot Get a Company
  hints:
    readOnly: true
  name: getcompany
- description: HubSpot Update a Company
  hints:
    readOnly: false
  name: updatecompany
- description: HubSpot Archive a Company
  hints:
    destructive: true
  name: deletecompany
- description: HubSpot Batch Read Companies
  hints:
    readOnly: false
  name: batchreadcompanies
- description: HubSpot Batch Create Companies
  hints:
    readOnly: false
  name: batchcreatecompanies
- description: HubSpot Batch Update Companies
  hints:
    readOnly: false
  name: batchupdatecompanies
- description: HubSpot Batch Archive Companies
  hints:
    readOnly: false
  name: batcharchivecompanies
- description: HubSpot Search Companies
  hints:
    readOnly: false
  name: searchcompanies
- description: HubSpot List Company Associations
  hints:
    readOnly: true
  name: listcompanyassociations
- description: HubSpot Create a Company Association
  hints:
    readOnly: false
  name: createcompanyassociation
- description: HubSpot Delete a Company Association
  hints:
    destructive: true
  name: deletecompanyassociation
- description: HubSpot List Deals
  hints:
    readOnly: true
  name: listdeals
- description: HubSpot Create a Deal
  hints:
    readOnly: false
  name: createdeal
- description: HubSpot Get a Deal
  hints:
    readOnly: true
  name: getdeal
- description: HubSpot Update a Deal
  hints:
    readOnly: false
  name: updatedeal
- description: HubSpot Archive a Deal
  hints:
    destructive: true
  name: deletedeal
- description: HubSpot Batch Read Deals
  hints:
    readOnly: false
  name: batchreaddeals
- description: HubSpot Batch Create Deals
  hints:
    readOnly: false
  name: batchcreatedeals
- description: HubSpot Batch Update Deals
  hints:
    readOnly: false
  name: batchupdatedeals
- description: HubSpot Batch Archive Deals
  hints:
    readOnly: false
  name: batcharchivedeals
- description: HubSpot Search Deals
  hints:
    readOnly: false
  name: searchdeals
- description: HubSpot List Deal Associations
  hints:
    readOnly: true
  name: listdealassociations
- description: HubSpot Create a Deal Association
  hints:
    readOnly: false
  name: createdealassociation
- description: HubSpot Delete a Deal Association
  hints:
    destructive: true
  name: deletedealassociation
- description: HubSpot List Tickets
  hints:
    readOnly: true
  name: listtickets
- description: HubSpot Create a Ticket
  hints:
    readOnly: false
  name: createticket
- description: HubSpot Get a Ticket
  hints:
    readOnly: true
  name: getticket
- description: HubSpot Update a Ticket
  hints:
    readOnly: false
  name: updateticket
- description: HubSpot Archive a Ticket
  hints:
    destructive: true
  name: deleteticket
- description: HubSpot Batch Read Tickets
  hints:
    readOnly: false
  name: batchreadtickets
- description: HubSpot Batch Create Tickets
  hints:
    readOnly: false
  name: batchcreatetickets
- description: HubSpot Batch Update Tickets
  hints:
    readOnly: false
  name: batchupdatetickets
- description: HubSpot Batch Archive Tickets
  hints:
    readOnly: false
  name: batcharchivetickets
- description: HubSpot Search Tickets
  hints:
    readOnly: false
  name: searchtickets
- description: HubSpot List Ticket Associations
  hints:
    readOnly: true
  name: listticketassociations
- description: HubSpot Create a Ticket Association
  hints:
    readOnly: false
  name: createticketassociation
- description: HubSpot Delete a Ticket Association
  hints:
    destructive: true
  name: deleteticketassociation
- description: HubSpot List Associations for an Object
  hints:
    readOnly: true
  name: listobjectassociations
- description: HubSpot Create an Association Between Objects
  hints:
    readOnly: false
  name: createobjectassociation
- description: HubSpot Delete an Association Between Objects
  hints:
    destructive: true
  name: deleteobjectassociation
- description: HubSpot Batch Read Associations for Multiple Objects
  hints:
    readOnly: false
  name: batchreadassociations
- description: HubSpot Batch Create Associations
  hints:
    readOnly: false
  name: batchcreateassociations
- description: HubSpot Batch Archive Associations
  hints:
    readOnly: false
  name: batcharchiveassociations
- description: HubSpot List Association Labels
  hints:
    readOnly: true
  name: listassociationlabels
- description: HubSpot Create an Association Label
  hints:
    readOnly: false
  name: createassociationlabel
- description: HubSpot Update an Association Label
  hints:
    readOnly: false
  name: updateassociationlabel
- description: HubSpot Delete an Association Label
  hints:
    destructive: true
  name: deleteassociationlabel
- description: HubSpot List All Association Definitions
  hints:
    readOnly: true
  name: listassociationdefinitions
- description: HubSpot Search CRM Objects
  hints:
    readOnly: false
  name: searchcrmobjects
- description: HubSpot List All Lists
  hints:
    readOnly: true
  name: listlists
- description: HubSpot Create a List
  hints:
    readOnly: false
  name: createlist
- description: HubSpot Get a List
  hints:
    readOnly: true
  name: getlist
- description: HubSpot Delete a List
  hints:
    destructive: true
  name: deletelist
- description: HubSpot Get List Members
  hints:
    readOnly: true
  name: getlistmemberships
- description: HubSpot Add Members to a List
  hints:
    readOnly: false
  name: addlistmembers
- description: HubSpot Remove Members from a List
  hints:
    readOnly: false
  name: removelistmembers
---
