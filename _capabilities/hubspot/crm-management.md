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
- hubspot batch create companies
- updatecompany
- hubspot search deals
- hubspot search companies
- searchcompanies
- createcompany
- hubspot create a list
- updateticket
- hubspot archive a contact
- createdeal
- marketing automation
- marketing
- hubspot batch update deals
- getdeal
- removelistmembers
- hubspot list contacts
- hubspot batch update companies
- deleteobjectassociation
- hubspot batch archive contacts
- addlistmembers
- hubspot list tickets
- hubspot get a company
- hubspot batch update tickets
- batcharchivetickets
- deleteticket
- getlist
- batchupdatedeals
- hubspot list all association definitions
- hubspot get a ticket
- hubspot search tickets
- email marketing
- getcompany
- customer service
- searchcontacts
- hubspot list companies
- hubspot archive a ticket
- hubspot batch create deals
- hubspot delete a list
- sales
- hubspot archive a deal
- deletecontact
- batchcreatedeals
- batcharchiveassociations
- contacts
- hubspot batch read contacts
- createdealassociation
- deletecontactassociation
- hubspot create a company
- hubspot delete a company association
- createticketassociation
- listobjectassociations
- hubspot delete an association between objects
- hubspot create a ticket association
- hubspot get a list
- hubspot list ticket associations
- batcharchivecompanies
- deletecompanyassociation
- batcharchivedeals
- listdeals
- hubspot delete a deal association
- searchdeals
- searchcrmobjects
- hubspot batch create associations
- createassociationlabel
- listcontactassociations
- hubspot batch read deals
- analytics
- hubspot create a contact association
- hubspot archive a company
- hubspot delete an association label
- hubspot list all lists
- listticketassociations
- hubspot list association labels
- batcharchivecontacts
- deletecompany
- hubspot update a contact
- hubspot list contact associations
- batchreadassociations
- hubspot search contacts
- getcontact
- listcompanyassociations
- createcontactassociation
- hubspot list deal associations
- batchcreatecompanies
- hubspot create a ticket
- batchupdatecompanies
- listcontacts
- hubspot list associations for an object
- hubspot create a deal
- getticket
- updateassociationlabel
- batchreadtickets
- listassociationdefinitions
- batchreadcompanies
- listlists
- hubspot batch read associations for multiple objects
- searchtickets
- commerce
- hubspot search crm objects
- createlist
- batchcreatecontacts
- deletedeal
- deletelist
- createcontact
- deleteticketassociation
- hubspot batch update contacts
- hubspot get list members
- deleteassociationlabel
- hubspot remove members from a list
- hubspot batch create contacts
- hubspot batch read companies
- createticket
- updatecontact
- crm
- hubspot batch archive associations
- hubspot update a company
- hubspot
- hubspot create a company association
- hubspot list deals
- hubspot delete a ticket association
- batchupdatetickets
- hubspot create an association label
- batchcreateassociations
- hubspot get a contact
- content
- hubspot create a contact
- batchreadcontacts
- hubspot batch archive deals
- listassociationlabels
- hubspot batch create tickets
- hubspot get a deal
- hubspot list company associations
- hubspot batch read tickets
- hubspot create a deal association
- deletedealassociation
- updatedeal
- batchcreatetickets
- hubspot create an association between objects
- hubspot batch archive tickets
- batchupdatecontacts
- listcompanies
- hubspot add members to a list
- createobjectassociation
- operations
- listtickets
- hubspot update an association label
- hubspot delete a contact association
- hubspot update a deal
- createcompanyassociation
- listdealassociations
- hubspot batch archive companies
- getlistmemberships
- hubspot update a ticket
- batchreaddeals
slug: crm-management
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
