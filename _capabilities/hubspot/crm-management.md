---
categories:
- crm-sales
consumed_apis: []
description: Unified CRM workflow for managing contacts, companies, deals, tickets, and their associations.
layout: capability
name: HubSpot CRM Management
operations: []
personas: []
provider_name: HubSpot
provider_slug: hubspot
search_terms:
- getticket
- hubspot batch read associations for multiple objects
- searchtickets
- hubspot batch archive deals
- searchcontacts
- hubspot archive a ticket
- batcharchivedeals
- batchcreatecontacts
- hubspot get a list
- analytics
- content
- hubspot batch create associations
- hubspot update a deal
- batchreadassociations
- hubspot list deal associations
- hubspot batch update tickets
- updatecontact
- hubspot get a ticket
- hubspot list ticket associations
- hubspot list contacts
- hubspot search contacts
- createdealassociation
- hubspot batch read contacts
- hubspot list companies
- deletedealassociation
- hubspot create a list
- deletelist
- hubspot delete a ticket association
- batchupdatedeals
- hubspot batch archive associations
- hubspot create a contact association
- batchcreateassociations
- hubspot remove members from a list
- hubspot delete a contact association
- searchcrmobjects
- hubspot list associations for an object
- createcompany
- hubspot delete an association between objects
- hubspot get a deal
- createobjectassociation
- hubspot update a company
- updatedeal
- addlistmembers
- removelistmembers
- hubspot create a ticket association
- listdeals
- hubspot batch archive tickets
- listassociationdefinitions
- hubspot delete a list
- hubspot create a company association
- listlists
- deletecontactassociation
- createticket
- hubspot batch archive contacts
- hubspot archive a contact
- createdeal
- marketing automation
- hubspot search deals
- crm
- deletedeal
- listdealassociations
- deleteassociationlabel
- hubspot batch read tickets
- hubspot list company associations
- hubspot update a contact
- batchupdatecontacts
- createcontactassociation
- listcompanies
- batcharchivecontacts
- hubspot create a deal
- hubspot list all lists
- hubspot batch create deals
- hubspot archive a company
- hubspot archive a deal
- hubspot search crm objects
- hubspot list contact associations
- createlist
- deletecompanyassociation
- listassociationlabels
- createticketassociation
- hubspot delete a company association
- hubspot
- batchreadtickets
- batcharchiveassociations
- hubspot list deals
- hubspot batch update deals
- batchcreatedeals
- contacts
- hubspot create an association label
- hubspot delete an association label
- hubspot batch create tickets
- hubspot batch update contacts
- commerce
- getcontact
- getlist
- createcontact
- hubspot create an association between objects
- email marketing
- listticketassociations
- updateticket
- hubspot batch create contacts
- hubspot update an association label
- hubspot add members to a list
- hubspot list tickets
- batchcreatetickets
- hubspot batch create companies
- listcompanyassociations
- updateassociationlabel
- searchdeals
- updatecompany
- deleteticketassociation
- batchcreatecompanies
- sales
- listcontactassociations
- batcharchivetickets
- deleteticket
- listcontacts
- batchupdatetickets
- getcompany
- hubspot search tickets
- marketing
- hubspot batch archive companies
- batchreaddeals
- batchupdatecompanies
- searchcompanies
- hubspot create a company
- deletecompany
- operations
- hubspot batch update companies
- hubspot get a contact
- hubspot create a contact
- hubspot list association labels
- createcompanyassociation
- hubspot update a ticket
- deleteobjectassociation
- hubspot get list members
- hubspot delete a deal association
- hubspot create a deal association
- hubspot batch read companies
- batchreadcontacts
- hubspot get a company
- hubspot batch read deals
- batchreadcompanies
- listtickets
- listobjectassociations
- getdeal
- createassociationlabel
- batcharchivecompanies
- getlistmemberships
- customer service
- hubspot create a ticket
- hubspot search companies
- hubspot list all association definitions
- deletecontact
slug: crm-management
source_filename: crm-management.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HubSpot CRM Management\n  description: Unified CRM workflow for managing contacts, companies, deals, tickets, and their associations.\n  tags:\n  - HubSpot\n  - CRM\n  - Sales\n  - Contacts\n  created: '2026-04-18'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    HUBSPOT_ACCESS_TOKEN: HUBSPOT_ACCESS_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: crm-contacts-api\n    baseUri: https://api.hubapi.com\n    description: Contact records store information about individuals. The contacts endpoints allow you to manage contact data\n      and sync it between HubSpot and other systems. You can create, retrieve, update, and delete\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: contacts\n      path: /contacts\n      description: contacts operations\n      operations:\n      - name: listcontacts\n        method: GET\n        description: HubSpot List Contacts\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcontact\n        method: POST\n        description: HubSpot Create a Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcontact\n        method: GET\n        description: HubSpot Get a Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecontact\n        method: PATCH\n        description: HubSpot Update a Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontact\n        method: DELETE\n        description: HubSpot Archive a Contact\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadcontacts\n        method: POST\n        description: HubSpot Batch Read Contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatecontacts\n        method: POST\n        description: HubSpot Batch Create Contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatecontacts\n        method: POST\n        description: HubSpot Batch Update Contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n      \
  \    value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivecontacts\n        method: POST\n        description: HubSpot Batch Archive Contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchcontacts\n        method: POST\n        description: HubSpot Search Contacts\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listcontactassociations\n        method: GET\n        description: HubSpot List Contact Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createcontactassociation\n        method: PUT\n        description: HubSpot Create a Contact Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecontactassociation\n        method: DELETE\n        description: HubSpot Delete a Contact Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-companies-api\n    baseUri: https://api.hubapi.com\n    description: Company records store data about businesses and organizations. The companies endpoints allow you to manage\n      this data and sync it between HubSpot and other systems, including creating, retrieving, upda\n    authentication:\n      type:\
  \ bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: companies\n      path: /companies\n      description: companies operations\n      operations:\n      - name: listcompanies\n        method: GET\n        description: HubSpot List Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcompany\n        method: POST\n        description: HubSpot Create a Company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getcompany\n        method: GET\n        description: HubSpot Get a Company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecompany\n        method: PATCH\n        description: HubSpot Update a Company\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: deletecompany\n        method: DELETE\n        description: HubSpot Archive a Company\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadcompanies\n        method: POST\n        description: HubSpot Batch Read Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatecompanies\n        method: POST\n        description: HubSpot Batch Create Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n \
  \     description: update operations\n      operations:\n      - name: batchupdatecompanies\n        method: POST\n        description: HubSpot Batch Update Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivecompanies\n        method: POST\n        description: HubSpot Batch Archive Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchcompanies\n        method: POST\n        description: HubSpot Search Companies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n\
  \      description: associations operations\n      operations:\n      - name: listcompanyassociations\n        method: GET\n        description: HubSpot List Company Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createcompanyassociation\n        method: PUT\n        description: HubSpot Create a Company Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecompanyassociation\n        method: DELETE\n        description: HubSpot Delete a Company Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-deals-api\n    baseUri: https://api.hubapi.com\n\
  \    description: A deal stores data about an ongoing transaction or sales opportunity. The deals endpoints allow you to manage\n      deal records and sync data between HubSpot and other systems, supporting the full lifecycl\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: deals\n      path: /deals\n      description: deals operations\n      operations:\n      - name: listdeals\n        method: GET\n        description: HubSpot List Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdeal\n        method: POST\n        description: HubSpot Create a Deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeal\n        method: GET\n        description: HubSpot Get a Deal\n        outputRawFormat: json\n        outputParameters:\n   \
  \     - name: result\n          type: object\n          value: $.\n      - name: updatedeal\n        method: PATCH\n        description: HubSpot Update a Deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedeal\n        method: DELETE\n        description: HubSpot Archive a Deal\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreaddeals\n        method: POST\n        description: HubSpot Batch Read Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatedeals\n        method: POST\n        description:\
  \ HubSpot Batch Create Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatedeals\n        method: POST\n        description: HubSpot Batch Update Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivedeals\n        method: POST\n        description: HubSpot Batch Archive Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchdeals\n        method: POST\n        description: HubSpot Search\
  \ Deals\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listdealassociations\n        method: GET\n        description: HubSpot List Deal Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createdealassociation\n        method: PUT\n        description: HubSpot Create a Deal Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedealassociation\n        method: DELETE\n        description: HubSpot Delete a Deal Association\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-tickets-api\n    baseUri: https://api.hubapi.com\n    description: Tickets represent customer requests for help and are tracked through support pipelines until resolved. The\n      tickets endpoints allow you to create, manage, and retrieve customer support ticket records a\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: tickets\n      path: /tickets\n      description: tickets operations\n      operations:\n      - name: listtickets\n        method: GET\n        description: HubSpot List Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createticket\n        method: POST\n        description: HubSpot Create a Ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: getticket\n        method: GET\n        description: HubSpot Get a Ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateticket\n        method: PATCH\n        description: HubSpot Update a Ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteticket\n        method: DELETE\n        description: HubSpot Archive a Ticket\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadtickets\n        method: POST\n        description: HubSpot Batch Read Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreatetickets\n        method: POST\n        description: HubSpot Batch Create Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: update\n      path: /update\n      description: update operations\n      operations:\n      - name: batchupdatetickets\n        method: POST\n        description: HubSpot Batch Update Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchivetickets\n        method: POST\n        description: HubSpot Batch Archive Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchtickets\n        method: POST\n        description: HubSpot Search Tickets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listticketassociations\n        method: GET\n        description: HubSpot List Ticket Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectId}'\n      path: /{toObjectId}\n      description: '{toObjectId} operations'\n      operations:\n      - name: createticketassociation\n        method: PUT\n        description: HubSpot Create a Ticket Association\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: deleteticketassociation\n        method: DELETE\n        description: HubSpot Delete a Ticket Association\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-associations-api\n    baseUri: https://api.hubapi.com\n    description: 'The HubSpot CRM Associations API enables you to manage relationships between CRM objects.\n\n\n      ## Overview\n\n      Associations represent the connections between different CRM records in HubSpot. This API allows '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: associations\n      path: /associations\n      description: associations operations\n      operations:\n      - name: listobjectassociations\n        method: GET\n        description: HubSpot List Associations for an Object\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createobjectassociation\n        method: PUT\n        description: HubSpot Create an Association Between Objects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: '{toObjectType}'\n      path: /{toObjectType}\n      description: '{toObjectType} operations'\n      operations:\n      - name: deleteobjectassociation\n        method: DELETE\n        description: HubSpot Delete an Association Between Objects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: read\n      path: /read\n      description: read operations\n      operations:\n      - name: batchreadassociations\n        method: POST\n        description: HubSpot Batch Read Associations for Multiple Objects\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: create\n      path: /create\n      description: create operations\n      operations:\n      - name: batchcreateassociations\n        method: POST\n        description: HubSpot Batch Create Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: archive\n      path: /archive\n      description: archive operations\n      operations:\n      - name: batcharchiveassociations\n        method: POST\n        description: HubSpot Batch Archive Associations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: labels\n      path: /labels\n      description: labels operations\n      operations:\n      - name: listassociationlabels\n        method: GET\n        description: HubSpot List Association Labels\n   \
  \     outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createassociationlabel\n        method: POST\n        description: HubSpot Create an Association Label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateassociationlabel\n        method: PUT\n        description: HubSpot Update an Association Label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteassociationlabel\n        method: DELETE\n        description: HubSpot Delete an Association Label\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: definitions\n      path: /definitions\n      description: definitions operations\n      operations:\n      - name: listassociationdefinitions\n\
  \        method: GET\n        description: HubSpot List All Association Definitions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-search-api\n    baseUri: https://api.hubapi.com\n    description: 'The CRM Search API allows you to query and filter CRM objects using a flexible search interface. You can\n      search across contacts, companies, deals, tickets, and other object types using filter groups, '\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: search\n      path: /search\n      description: search operations\n      operations:\n      - name: searchcrmobjects\n        method: POST\n        description: HubSpot Search CRM Objects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: crm-lists-api\n   \
  \ baseUri: https://api.hubapi.com\n    description: The Lists API allows you to create and manage lists of CRM records based on static membership or dynamic\n      filter criteria. Lists can be used to segment contacts, companies, and other CRM objects for ma\n    authentication:\n      type: bearer\n      token: '{{HUBSPOT_ACCESS_TOKEN}}'\n    resources:\n    - name: lists\n      path: /lists\n      description: lists operations\n      operations:\n      - name: listlists\n        method: GET\n        description: HubSpot List All Lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createlist\n        method: POST\n        description: HubSpot Create a List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getlist\n        method: GET\n        description: HubSpot Get a List\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletelist\n        method: DELETE\n        description: HubSpot Delete a List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: memberships\n      path: /memberships\n      description: memberships operations\n      operations:\n      - name: getlistmemberships\n        method: GET\n        description: HubSpot Get List Members\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: add\n      path: /add\n      description: add operations\n      operations:\n      - name: addlistmembers\n        method: PUT\n        description: HubSpot Add Members to a List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: remove\n\
  \      path: /remove\n      description: remove operations\n      operations:\n      - name: removelistmembers\n        method: PUT\n        description: HubSpot Remove Members from a List\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: mcp\n    port: 9090\n    namespace: crm-management-mcp\n    transport: http\n    description: MCP server for AI-assisted HubSpot CRM Management.\n    tools:\n    - name: listcontacts\n      description: HubSpot List Contacts\n      hints:\n        readOnly: true\n      call: crm-contacts-api.listcontacts\n    - name: createcontact\n      description: HubSpot Create a Contact\n      hints:\n        readOnly: false\n      call: crm-contacts-api.createcontact\n    - name: getcontact\n      description: HubSpot Get a Contact\n      hints:\n        readOnly: true\n      call: crm-contacts-api.getcontact\n    - name: updatecontact\n      description: HubSpot\
  \ Update a Contact\n      hints:\n        readOnly: false\n      call: crm-contacts-api.updatecontact\n    - name: deletecontact\n      description: HubSpot Archive a Contact\n      hints:\n        destructive: true\n      call: crm-contacts-api.deletecontact\n    - name: batchreadcontacts\n      description: HubSpot Batch Read Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchreadcontacts\n    - name: batchcreatecontacts\n      description: HubSpot Batch Create Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchcreatecontacts\n    - name: batchupdatecontacts\n      description: HubSpot Batch Update Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batchupdatecontacts\n    - name: batcharchivecontacts\n      description: HubSpot Batch Archive Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.batcharchivecontacts\n    - name: searchcontacts\n      description: HubSpot\
  \ Search Contacts\n      hints:\n        readOnly: false\n      call: crm-contacts-api.searchcontacts\n    - name: listcontactassociations\n      description: HubSpot List Contact Associations\n      hints:\n        readOnly: true\n      call: crm-contacts-api.listcontactassociations\n    - name: createcontactassociation\n      description: HubSpot Create a Contact Association\n      hints:\n        readOnly: false\n      call: crm-contacts-api.createcontactassociation\n    - name: deletecontactassociation\n      description: HubSpot Delete a Contact Association\n      hints:\n        destructive: true\n      call: crm-contacts-api.deletecontactassociation\n    - name: listcompanies\n      description: HubSpot List Companies\n      hints:\n        readOnly: true\n      call: crm-companies-api.listcompanies\n    - name: createcompany\n      description: HubSpot Create a Company\n      hints:\n        readOnly: false\n      call: crm-companies-api.createcompany\n    - name: getcompany\n\
  \      description: HubSpot Get a Company\n      hints:\n        readOnly: true\n      call: crm-companies-api.getcompany\n    - name: updatecompany\n      description: HubSpot Update a Company\n      hints:\n        readOnly: false\n      call: crm-companies-api.updatecompany\n    - name: deletecompany\n      description: HubSpot Archive a Company\n      hints:\n        destructive: true\n      call: crm-companies-api.deletecompany\n    - name: batchreadcompanies\n      description: HubSpot Batch Read Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchreadcompanies\n    - name: batchcreatecompanies\n      description: HubSpot Batch Create Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchcreatecompanies\n    - name: batchupdatecompanies\n      description: HubSpot Batch Update Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batchupdatecompanies\n    - name: batcharchivecompanies\n    \
  \  description: HubSpot Batch Archive Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.batcharchivecompanies\n    - name: searchcompanies\n      description: HubSpot Search Companies\n      hints:\n        readOnly: false\n      call: crm-companies-api.searchcompanies\n    - name: listcompanyassociations\n      description: HubSpot List Company Associations\n      hints:\n        readOnly: true\n      call: crm-companies-api.listcompanyassociations\n    - name: createcompanyassociation\n      description: HubSpot Create a Company Association\n      hints:\n        readOnly: false\n      call: crm-companies-api.createcompanyassociation\n    - name: deletecompanyassociation\n      description: HubSpot Delete a Company Association\n      hints:\n        destructive: true\n      call: crm-companies-api.deletecompanyassociation\n    - name: listdeals\n      description: HubSpot List Deals\n      hints:\n        readOnly: true\n      call: crm-deals-api.listdeals\n\
  \    - name: createdeal\n      description: HubSpot Create a Deal\n      hints:\n        readOnly: false\n      call: crm-deals-api.createdeal\n    - name: getdeal\n      description: HubSpot Get a Deal\n      hints:\n        readOnly: true\n      call: crm-deals-api.getdeal\n    - name: updatedeal\n      description: HubSpot Update a Deal\n      hints:\n        readOnly: false\n      call: crm-deals-api.updatedeal\n    - name: deletedeal\n      description: HubSpot Archive a Deal\n      hints:\n        destructive: true\n      call: crm-deals-api.deletedeal\n    - name: batchreaddeals\n      description: HubSpot Batch Read Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batchreaddeals\n    - name: batchcreatedeals\n      description: HubSpot Batch Create Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batchcreatedeals\n    - name: batchupdatedeals\n      description: HubSpot Batch Update Deals\n      hints:\n        readOnly: false\n   \
  \   call: crm-deals-api.batchupdatedeals\n    - name: batcharchivedeals\n      description: HubSpot Batch Archive Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.batcharchivedeals\n    - name: searchdeals\n      description: HubSpot Search Deals\n      hints:\n        readOnly: false\n      call: crm-deals-api.searchdeals\n    - name: listdealassociations\n      description: HubSpot List Deal Associations\n      hints:\n        readOnly: true\n      call: crm-deals-api.listdealassociations\n    - name: createdealassociation\n      description: HubSpot Create a Deal Association\n      hints:\n        readOnly: false\n      call: crm-deals-api.createdealassociation\n    - name: deletedealassociation\n      description: HubSpot Delete a Deal Association\n      hints:\n        destructive: true\n      call: crm-deals-api.deletedealassociation\n    - name: listtickets\n      description: HubSpot List Tickets\n      hints:\n        readOnly: true\n      call: crm-tickets-api.listtickets\n\
  \    - name: createticket\n      description: HubSpot Create a Ticket\n      hints:\n        readOnly: false\n      call: crm-tickets-api.createticket\n    - name: getticket\n      description: HubSpot Get a Ticket\n      hints:\n        readOnly: true\n      call: crm-tickets-api.getticket\n    - name: updateticket\n      description: HubSpot Update a Ticket\n      hints:\n        readOnly: false\n      call: crm-tickets-api.updateticket\n    - name: deleteticket\n      description: HubSpot Archive a Ticket\n      hints:\n        destructive: true\n      call: crm-tickets-api.deleteticket\n    - name: batchreadtickets\n      description: HubSpot Batch Read Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchreadtickets\n    - name: batchcreatetickets\n      description: HubSpot Batch Create Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchcreatetickets\n    - name: batchupdatetickets\n      description: HubSpot Batch Update\
  \ Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batchupdatetickets\n    - name: batcharchivetickets\n      description: HubSpot Batch Archive Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.batcharchivetickets\n    - name: searchtickets\n      description: HubSpot Search Tickets\n      hints:\n        readOnly: false\n      call: crm-tickets-api.searchtickets\n    - name: listticketassociations\n      description: HubSpot List Ticket Associations\n      hints:\n        readOnly: true\n      call: crm-tickets-api.listticketassociations\n    - name: createticketassociation\n      description: HubSpot Create a Ticket Association\n      hints:\n        readOnly: false\n      call: crm-tickets-api.createticketassociation\n    - name: deleteticketassociation\n      description: HubSpot Delete a Ticket Association\n      hints:\n        destructive: true\n      call: crm-tickets-api.deleteticketassociation\n    - name: listobjectassociations\n\
  \      description: HubSpot List Associations for an Object\n      hints:\n        readOnly: true\n      call: crm-associations-api.listobjectassociations\n    - name: createobjectassociation\n      description: HubSpot Create an Association Between Objects\n      hints:\n        readOnly: false\n      call: crm-associations-api.createobjectassociation\n    - name: deleteobjectassociation\n      description: HubSpot Delete an Association Between Objects\n      hints:\n        destructive: true\n      call: crm-associations-api.deleteobjectassociation\n    - name: batchreadassociations\n      description: HubSpot Batch Read Associations for Multiple Objects\n      hints:\n        readOnly: false\n      call: crm-associations-api.batchreadassociations\n    - name: batchcreateassociations\n      description: HubSpot Batch Cr\n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hubspot/refs/heads/main/capabilities/crm-management.yaml\n"
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
