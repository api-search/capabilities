---
categories: []
consumed_apis: []
description: This OAS file describes the NGSI-LD API defined by the ETSI ISG CIM group. This Cross-domain Context Information Management API allows to provide, consume and subscribe to context information in multiple scenarios and involving multiple stakeholders
layout: capability
name: ETSI ISG CIM / NGSI-LD API
operations:
- description: Retrieve a set of entities which matches a specific query from an NGSI-LD system
  method: GET
  name: queryentities
  path: /entities/
- description: Create a new Entity within an NGSI-LD system
  method: POST
  name: createentity
  path: /entities/
- description: Retrieve an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to be retrieved by using query parameters
  method: GET
  name: retrieveentitybyid
  path: /entities/{entityId}
- description: Removes an specific Entity from an NGSI-LD system
  method: DELETE
  name: removeentitybyid
  path: /entities/{entityId}
- description: Append new Entity attributes to an existing Entity within an NGSI-LD system
  method: POST
  name: appendentityattrs
  path: /entities/{entityId}/attrs/
- description: Update existing Entity attributes within an NGSI-LD system
  method: PATCH
  name: updateentityattrs
  path: /entities/{entityId}/attrs/
- description: Update existing Entity attributes within an NGSI-LD system
  method: PATCH
  name: partialattrupdate
  path: /entities/{entityId}/attrs/{attrId}
- description: Removes an existing Entity attribute within an NGSI-LD system
  method: DELETE
  name: removeentityattr
  path: /entities/{entityId}/attrs/{attrId}
- description: Retrieves the subscriptions available in an NGSI-LD system
  method: GET
  name: retrievesubscriptions
  path: /subscriptions/
- description: Creates a new Subscription within an NGSI-LD system
  method: POST
  name: createsubscription
  path: /subscriptions/
- description: Retrieves a specific Subscription from an NGSI-LD system
  method: GET
  name: retrievesubscriptionbyid
  path: /subscriptions/{subscriptionId}
- description: Updates a specific Subscription within an NGSI-LD system
  method: PATCH
  name: updatesubscription
  path: /subscriptions/{subscriptionId}
- description: Removes a specific Subscription from an NGSI-LD system
  method: DELETE
  name: removesubscription
  path: /subscriptions/{subscriptionId}
- description: Retrieve a set of context sources which matches a specific query from an NGSI-LD system
  method: GET
  name: querycsources
  path: /csourceRegistrations/
- description: Registers a new context source within an NGSI-LD system
  method: POST
  name: registercsource
  path: /csourceRegistrations/
- description: Retrieves a specific context source registration from an NGSI-LD system
  method: GET
  name: retrievecsource
  path: /csourceRegistrations/{registrationId}
- description: Removes an specific context source registration within an NGSI-LD system
  method: DELETE
  name: removecsource
  path: /csourceRegistrations/{registrationId}
- description: Retrieves the context source discovery subscriptions available in an NGSI-LD system
  method: GET
  name: retrievecsourcesubscriptions
  path: /csourceSubscriptions/
- description: Creates a context source discovery Subscription within an NGSI-LD system
  method: POST
  name: createcsourcesubscription
  path: /csourceSubscriptions/
- description: Retrieves a specific Subscription from an NGSI-LD system
  method: GET
  name: retrievecsourcesubscriptionsbyid
  path: /csourceSubscriptions/{subscriptionId}
- description: Updates a specific context source discovery Subscription within an NGSI-LD system
  method: PATCH
  name: updatecsourcesubscription
  path: /csourceSubscriptions/{subscriptionId}
- description: Removes a specific Context Source Subscription from an NGSI-LD system
  method: DELETE
  name: removecsourcesubscription
  path: /csourceSubscriptions/{subscriptionId}
- description: Batch Entity creation
  method: POST
  name: batchentitycreation
  path: /entityOperations/create
- description: Batch Entity update
  method: POST
  name: batchentityupdate
  path: /entityOperations/update
- description: Batch Entity upsert
  method: POST
  name: batchentityupsert
  path: /entityOperations/upsert
- description: Batch Entity delete
  method: POST
  name: batchentitydelete
  path: /entityOperations/delete
- description: Query temporal evolution of Entities from an NGSI-LD system
  method: GET
  name: querytemporalentities
  path: /temporal/entities/
- description: Create or update temporal representation of an Entity within an NGSI-LD system
  method: POST
  name: createupdateentitytemporal
  path: /temporal/entities/
- description: Retrieve the temporal representation of an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to be retrieved by using query parameters
  method: GET
  name: retrieveentitytemporalbyid
  path: /temporal/entities/{entityId}
- description: Removes the temporal representation of an Entity from an NGSI-LD system
  method: DELETE
  name: removeentitytemporalbyid
  path: /temporal/entities/{entityId}
- description: Add new attributes to an existing Temporal Entity within an NGSI-LD system
  method: POST
  name: addtemporalentityattrs
  path: /temporal/entities/{entityId}/attrs/
- description: Attribute from Temporal Representation of Entity deletion
  method: DELETE
  name: removeentitytemporalattr
  path: /temporal/entities/{entityId}/attrs/{attrId}
- description: Allows modifying a specific Attribute (Property or Relationship) instance, identified by its instanceId, of a Temporal Representation of an Entity.
  method: PATCH
  name: modifyentitytemporalattrinstance
  path: /temporal/entities/{entityId}/attrs/{attrId}/{instanceId}
- description: Attribute Instance deletion by instance id.
  method: DELETE
  name: removeentitytemporalattrinstance
  path: /temporal/entities/{entityId}/attrs/{attrId}/{instanceId}
personas: []
provider_name: FIWARE
provider_slug: fiware
search_terms:
- update existing entity attributes within an ngsi-ld system
- addtemporalentityattrs
- createentity
- removes an existing entity attribute within an ngsi-ld system
- linked data
- retrievecsourcesubscriptionsbyid
- updates a specific subscription within an ngsi-ld system
- removeentitytemporalattr
- querycsources
- batch entity upsert
- retrieve a set of context sources which matches a specific query from an ngsi-ld system
- removes an specific context source registration within an ngsi-ld system
- attribute instance deletion by instance id.
- retrievecsource
- retrieves a specific subscription from an ngsi-ld system
- batchentitycreation
- smart cities
- creates a context source discovery subscription within an ngsi-ld system
- batch entity update
- batchentitydelete
- removes a specific context source subscription from an ngsi-ld system
- updatesubscription
- createsubscription
- retrieveentitybyid
- updatecsourcesubscription
- ngsi
- creates a new subscription within an ngsi-ld system
- standards
- partialattrupdate
- retrievesubscriptions
- retrieve a set of entities which matches a specific query from an ngsi-ld system
- context information
- internet of things
- removecsourcesubscription
- query temporal evolution of entities from an ngsi-ld system
- retrieves the context source discovery subscriptions available in an ngsi-ld system
- retrieve the temporal representation of an specific entity from an ngsi-ld system. it's possible to specify the entity attributes to be retrieved by using query parameters
- removeentitybyid
- batch entity delete
- create a new entity within an ngsi-ld system
- api
- appendentityattrs
- removes a specific subscription from an ngsi-ld system
- registercsource
- removeentitytemporalbyid
- removes the temporal representation of an entity from an ngsi-ld system
- querytemporalentities
- append new entity attributes to an existing entity within an ngsi-ld system
- updateentityattrs
- modifyentitytemporalattrinstance
- batchentityupdate
- createcsourcesubscription
- add new attributes to an existing temporal entity within an ngsi-ld system
- removeentitytemporalattrinstance
- retrieves the subscriptions available in an ngsi-ld system
- queryentities
- retrievesubscriptionbyid
- removecsource
- retrieve an specific entity from an ngsi-ld system. it's possible to specify the entity attributes to be retrieved by using query parameters
- retrievecsourcesubscriptions
- createupdateentitytemporal
- registers a new context source within an ngsi-ld system
- retrieveentitytemporalbyid
- devices
- batchentityupsert
- batch entity creation
- retrieves a specific context source registration from an ngsi-ld system
- removeentityattr
- create or update temporal representation of an entity within an ngsi-ld system
- attribute from temporal representation of entity deletion
- removesubscription
- fiware
- updates a specific context source discovery subscription within an ngsi-ld system
- removes an specific entity from an ngsi-ld system
- allows modifying a specific attribute (property or relationship) instance, identified by its instanceid, of a temporal representation of an entity.
slug: fiware-capability
source_filename: fiware-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ETSI ISG CIM / NGSI-LD API\n  description: This OAS file describes the NGSI-LD API defined by the ETSI ISG CIM group. This Cross-domain Context Information\n    Management API allows to provide, consume and subscribe to context information in multiple scenarios and involving multiple\n    stakeholders\n  tags:\n  - Fiware\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fiware\n    baseUri: https://api.example.com\n    description: ETSI ISG CIM / NGSI-LD API HTTP API.\n    resources:\n    - name: entities\n      path: /entities/\n      operations:\n      - name: queryentities\n        method: GET\n        description: Retrieve a set of entities which matches a specific query from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createentity\n        method: POST\n\
  \        description: Create a new Entity within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-entityid\n      path: /entities/{entityId}\n      operations:\n      - name: retrieveentitybyid\n        method: GET\n        description: Retrieve an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to\n          be retrieved by using query parameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeentitybyid\n        method: DELETE\n        description: Removes an specific Entity from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-entityid-attrs\n      path: /entities/{entityId}/attrs/\n      operations:\n      - name:\
  \ appendentityattrs\n        method: POST\n        description: Append new Entity attributes to an existing Entity within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateentityattrs\n        method: PATCH\n        description: Update existing Entity attributes within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entities-entityid-attrs-attrid\n      path: /entities/{entityId}/attrs/{attrId}\n      operations:\n      - name: partialattrupdate\n        method: PATCH\n        description: Update existing Entity attributes within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeentityattr\n        method: DELETE\n        description: Removes an existing\
  \ Entity attribute within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions\n      path: /subscriptions/\n      operations:\n      - name: retrievesubscriptions\n        method: GET\n        description: Retrieves the subscriptions available in an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscription\n        method: POST\n        description: Creates a new Subscription within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscriptions-subscriptionid\n      path: /subscriptions/{subscriptionId}\n      operations:\n      - name: retrievesubscriptionbyid\n        method: GET\n        description: Retrieves a specific Subscription from an\
  \ NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesubscription\n        method: PATCH\n        description: Updates a specific Subscription within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removesubscription\n        method: DELETE\n        description: Removes a specific Subscription from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: csourceregistrations\n      path: /csourceRegistrations/\n      operations:\n      - name: querycsources\n        method: GET\n        description: Retrieve a set of context sources which matches a specific query from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: registercsource\n        method: POST\n        description: Registers a new context source within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: csourceregistrations-registrationid\n      path: /csourceRegistrations/{registrationId}\n      operations:\n      - name: retrievecsource\n        method: GET\n        description: Retrieves a specific context source registration from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removecsource\n        method: DELETE\n        description: Removes an specific context source registration within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: csourcesubscriptions\n\
  \      path: /csourceSubscriptions/\n      operations:\n      - name: retrievecsourcesubscriptions\n        method: GET\n        description: Retrieves the context source discovery subscriptions available in an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcsourcesubscription\n        method: POST\n        description: Creates a context source discovery Subscription within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: csourcesubscriptions-subscriptionid\n      path: /csourceSubscriptions/{subscriptionId}\n      operations:\n      - name: retrievecsourcesubscriptionsbyid\n        method: GET\n        description: Retrieves a specific Subscription from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: updatecsourcesubscription\n        method: PATCH\n        description: Updates a specific context source discovery Subscription within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removecsourcesubscription\n        method: DELETE\n        description: Removes a specific Context Source Subscription from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entityoperations-create\n      path: /entityOperations/create\n      operations:\n      - name: batchentitycreation\n        method: POST\n        description: Batch Entity creation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entityoperations-update\n      path: /entityOperations/update\n\
  \      operations:\n      - name: batchentityupdate\n        method: POST\n        description: Batch Entity update\n        inputParameters:\n        - name: options\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entityoperations-upsert\n      path: /entityOperations/upsert\n      operations:\n      - name: batchentityupsert\n        method: POST\n        description: Batch Entity upsert\n        inputParameters:\n        - name: options\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: entityoperations-delete\n      path: /entityOperations/delete\n      operations:\n      - name: batchentitydelete\n        method: POST\n        description: Batch Entity delete\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: temporal-entities\n      path: /temporal/entities/\n      operations:\n      - name: querytemporalentities\n        method: GET\n        description: Query temporal evolution of Entities from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createupdateentitytemporal\n        method: POST\n        description: Create or update temporal representation of an Entity within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: temporal-entities-entityid\n      path: /temporal/entities/{entityId}\n      operations:\n      - name: retrieveentitytemporalbyid\n        method: GET\n        description: Retrieve the temporal representation of an specific Entity from an NGSI-LD system. It's possible to specify\n\
  \          the Entity attributes to be retrieved by using query parameters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeentitytemporalbyid\n        method: DELETE\n        description: Removes the temporal representation of an Entity from an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: temporal-entities-entityid-attrs\n      path: /temporal/entities/{entityId}/attrs/\n      operations:\n      - name: addtemporalentityattrs\n        method: POST\n        description: Add new attributes to an existing Temporal Entity within an NGSI-LD system\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: temporal-entities-entityid-attrs-attrid\n      path: /temporal/entities/{entityId}/attrs/{attrId}\n \
  \     operations:\n      - name: removeentitytemporalattr\n        method: DELETE\n        description: Attribute from Temporal Representation of Entity deletion\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: temporal-entities-entityid-attrs-attrid-instance\n      path: /temporal/entities/{entityId}/attrs/{attrId}/{instanceId}\n      operations:\n      - name: modifyentitytemporalattrinstance\n        method: PATCH\n        description: Allows modifying a specific Attribute (Property or Relationship) instance, identified by its instanceId,\n          of a Temporal Representation of an Entity.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: removeentitytemporalattrinstance\n        method: DELETE\n        description: Attribute Instance deletion by instance id.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: fiware-rest\n    description: REST adapter for ETSI ISG CIM / NGSI-LD API.\n    resources:\n    - path: /entities/\n      name: queryentities\n      operations:\n      - method: GET\n        name: queryentities\n        description: Retrieve a set of entities which matches a specific query from an NGSI-LD system\n        call: fiware.queryentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/\n      name: createentity\n      operations:\n      - method: POST\n        name: createentity\n        description: Create a new Entity within an NGSI-LD system\n        call: fiware.createentity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}\n      name: retrieveentitybyid\n      operations:\n      - method: GET\n        name: retrieveentitybyid\n        description:\
  \ Retrieve an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to\n          be retrieved by using query parameters\n        call: fiware.retrieveentitybyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}\n      name: removeentitybyid\n      operations:\n      - method: DELETE\n        name: removeentitybyid\n        description: Removes an specific Entity from an NGSI-LD system\n        call: fiware.removeentitybyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}/attrs/\n      name: appendentityattrs\n      operations:\n      - method: POST\n        name: appendentityattrs\n        description: Append new Entity attributes to an existing Entity within an NGSI-LD system\n        call: fiware.appendentityattrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}/attrs/\n      name:\
  \ updateentityattrs\n      operations:\n      - method: PATCH\n        name: updateentityattrs\n        description: Update existing Entity attributes within an NGSI-LD system\n        call: fiware.updateentityattrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}/attrs/{attrId}\n      name: partialattrupdate\n      operations:\n      - method: PATCH\n        name: partialattrupdate\n        description: Update existing Entity attributes within an NGSI-LD system\n        call: fiware.partialattrupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entities/{entityId}/attrs/{attrId}\n      name: removeentityattr\n      operations:\n      - method: DELETE\n        name: removeentityattr\n        description: Removes an existing Entity attribute within an NGSI-LD system\n        call: fiware.removeentityattr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /subscriptions/\n      name: retrievesubscriptions\n      operations:\n      - method: GET\n        name: retrievesubscriptions\n        description: Retrieves the subscriptions available in an NGSI-LD system\n        call: fiware.retrievesubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/\n      name: createsubscription\n      operations:\n      - method: POST\n        name: createsubscription\n        description: Creates a new Subscription within an NGSI-LD system\n        call: fiware.createsubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: retrievesubscriptionbyid\n      operations:\n      - method: GET\n        name: retrievesubscriptionbyid\n        description: Retrieves a specific Subscription from an NGSI-LD system\n        call: fiware.retrievesubscriptionbyid\n        outputParameters:\n        - type: object\n    \
  \      mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: updatesubscription\n      operations:\n      - method: PATCH\n        name: updatesubscription\n        description: Updates a specific Subscription within an NGSI-LD system\n        call: fiware.updatesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /subscriptions/{subscriptionId}\n      name: removesubscription\n      operations:\n      - method: DELETE\n        name: removesubscription\n        description: Removes a specific Subscription from an NGSI-LD system\n        call: fiware.removesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceRegistrations/\n      name: querycsources\n      operations:\n      - method: GET\n        name: querycsources\n        description: Retrieve a set of context sources which matches a specific query from an NGSI-LD system\n        call: fiware.querycsources\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /csourceRegistrations/\n      name: registercsource\n      operations:\n      - method: POST\n        name: registercsource\n        description: Registers a new context source within an NGSI-LD system\n        call: fiware.registercsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceRegistrations/{registrationId}\n      name: retrievecsource\n      operations:\n      - method: GET\n        name: retrievecsource\n        description: Retrieves a specific context source registration from an NGSI-LD system\n        call: fiware.retrievecsource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceRegistrations/{registrationId}\n      name: removecsource\n      operations:\n      - method: DELETE\n        name: removecsource\n        description: Removes an specific context source registration within an NGSI-LD system\n        call: fiware.removecsource\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceSubscriptions/\n      name: retrievecsourcesubscriptions\n      operations:\n      - method: GET\n        name: retrievecsourcesubscriptions\n        description: Retrieves the context source discovery subscriptions available in an NGSI-LD system\n        call: fiware.retrievecsourcesubscriptions\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceSubscriptions/\n      name: createcsourcesubscription\n      operations:\n      - method: POST\n        name: createcsourcesubscription\n        description: Creates a context source discovery Subscription within an NGSI-LD system\n        call: fiware.createcsourcesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceSubscriptions/{subscriptionId}\n      name: retrievecsourcesubscriptionsbyid\n      operations:\n      - method: GET\n        name: retrievecsourcesubscriptionsbyid\n\
  \        description: Retrieves a specific Subscription from an NGSI-LD system\n        call: fiware.retrievecsourcesubscriptionsbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceSubscriptions/{subscriptionId}\n      name: updatecsourcesubscription\n      operations:\n      - method: PATCH\n        name: updatecsourcesubscription\n        description: Updates a specific context source discovery Subscription within an NGSI-LD system\n        call: fiware.updatecsourcesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /csourceSubscriptions/{subscriptionId}\n      name: removecsourcesubscription\n      operations:\n      - method: DELETE\n        name: removecsourcesubscription\n        description: Removes a specific Context Source Subscription from an NGSI-LD system\n        call: fiware.removecsourcesubscription\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /entityOperations/create\n      name: batchentitycreation\n      operations:\n      - method: POST\n        name: batchentitycreation\n        description: Batch Entity creation\n        call: fiware.batchentitycreation\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entityOperations/update\n      name: batchentityupdate\n      operations:\n      - method: POST\n        name: batchentityupdate\n        description: Batch Entity update\n        call: fiware.batchentityupdate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entityOperations/upsert\n      name: batchentityupsert\n      operations:\n      - method: POST\n        name: batchentityupsert\n        description: Batch Entity upsert\n        call: fiware.batchentityupsert\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /entityOperations/delete\n      name: batchentitydelete\n      operations:\n      -\
  \ method: POST\n        name: batchentitydelete\n        description: Batch Entity delete\n        call: fiware.batchentitydelete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/\n      name: querytemporalentities\n      operations:\n      - method: GET\n        name: querytemporalentities\n        description: Query temporal evolution of Entities from an NGSI-LD system\n        call: fiware.querytemporalentities\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/\n      name: createupdateentitytemporal\n      operations:\n      - method: POST\n        name: createupdateentitytemporal\n        description: Create or update temporal representation of an Entity within an NGSI-LD system\n        call: fiware.createupdateentitytemporal\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}\n      name: retrieveentitytemporalbyid\n\
  \      operations:\n      - method: GET\n        name: retrieveentitytemporalbyid\n        description: Retrieve the temporal representation of an specific Entity from an NGSI-LD system. It's possible to specify\n          the Entity attributes to be retrieved by using query parameters\n        call: fiware.retrieveentitytemporalbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}\n      name: removeentitytemporalbyid\n      operations:\n      - method: DELETE\n        name: removeentitytemporalbyid\n        description: Removes the temporal representation of an Entity from an NGSI-LD system\n        call: fiware.removeentitytemporalbyid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}/attrs/\n      name: addtemporalentityattrs\n      operations:\n      - method: POST\n        name: addtemporalentityattrs\n        description: Add new attributes to an\
  \ existing Temporal Entity within an NGSI-LD system\n        call: fiware.addtemporalentityattrs\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}/attrs/{attrId}\n      name: removeentitytemporalattr\n      operations:\n      - method: DELETE\n        name: removeentitytemporalattr\n        description: Attribute from Temporal Representation of Entity deletion\n        call: fiware.removeentitytemporalattr\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}/attrs/{attrId}/{instanceId}\n      name: modifyentitytemporalattrinstance\n      operations:\n      - method: PATCH\n        name: modifyentitytemporalattrinstance\n        description: Allows modifying a specific Attribute (Property or Relationship) instance, identified by its instanceId,\n          of a Temporal Representation of an Entity.\n        call: fiware.modifyentitytemporalattrinstance\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /temporal/entities/{entityId}/attrs/{attrId}/{instanceId}\n      name: removeentitytemporalattrinstance\n      operations:\n      - method: DELETE\n        name: removeentitytemporalattrinstance\n        description: Attribute Instance deletion by instance id.\n        call: fiware.removeentitytemporalattrinstance\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: fiware-mcp\n    transport: http\n    description: MCP adapter for ETSI ISG CIM / NGSI-LD API for AI agent use.\n    tools:\n    - name: queryentities\n      description: Retrieve a set of entities which matches a specific query from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.queryentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createentity\n      description:\
  \ Create a new Entity within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.createentity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrieveentitybyid\n      description: Retrieve an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to be\n        retrieved by using query parameters\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.retrieveentitybyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeentitybyid\n      description: Removes an specific Entity from an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fiware.removeentitybyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: appendentityattrs\n      description: Append new\
  \ Entity attributes to an existing Entity within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.appendentityattrs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateentityattrs\n      description: Update existing Entity attributes within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.updateentityattrs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: partialattrupdate\n      description: Update existing Entity attributes within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.partialattrupdate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removeentityattr\n      description: Removes an existing Entity attribute within an NGSI-LD system\n\
  \      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fiware.removeentityattr\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievesubscriptions\n      description: Retrieves the subscriptions available in an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.retrievesubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createsubscription\n      description: Creates a new Subscription within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.createsubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievesubscriptionbyid\n      description: Retrieves a specific Subscription from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: fiware.retrievesubscriptionbyid\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesubscription\n      description: Updates a specific Subscription within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.updatesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removesubscription\n      description: Removes a specific Subscription from an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fiware.removesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querycsources\n      description: Retrieve a set of context sources which matches a specific query from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.querycsources\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: registercsource\n      description: Registers a new context source within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.registercsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievecsource\n      description: Retrieves a specific context source registration from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.retrievecsource\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removecsource\n      description: Removes an specific context source registration within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fiware.removecsource\n      outputParameters:\n      - type: object\n        mapping: $.\n\
  \    - name: retrievecsourcesubscriptions\n      description: Retrieves the context source discovery subscriptions available in an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.retrievecsourcesubscriptions\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createcsourcesubscription\n      description: Creates a context source discovery Subscription within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.createcsourcesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: retrievecsourcesubscriptionsbyid\n      description: Retrieves a specific Subscription from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.retrievecsourcesubscriptionsbyid\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: updatecsourcesubscription\n      description: Updates a specific context source discovery Subscription within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.updatecsourcesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: removecsourcesubscription\n      description: Removes a specific Context Source Subscription from an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: fiware.removecsourcesubscription\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchentitycreation\n      description: Batch Entity creation\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.batchentitycreation\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ batchentityupdate\n      description: Batch Entity update\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.batchentityupdate\n      with:\n        options: tools.options\n      inputParameters:\n      - name: options\n        type: string\n        description: options\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchentityupsert\n      description: Batch Entity upsert\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.batchentityupsert\n      with:\n        options: tools.options\n      inputParameters:\n      - name: options\n        type: string\n        description: options\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: batchentitydelete\n      description: Batch Entity delete\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: fiware.batchentitydelete\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: querytemporalentities\n      description: Query temporal evolution of Entities from an NGSI-LD system\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: fiware.querytemporalentities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createupdateentitytemporal\n      description: Create or update temporal representation of an Entity within an NGSI-LD system\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: fals\n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/fiware/refs/heads/main/capabilities/fiware-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fiware/refs/heads/main/capabilities/fiware-capability.yaml
tags:
- Fiware
- API
tools:
- description: Retrieve a set of entities which matches a specific query from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: queryentities
- description: Create a new Entity within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentity
- description: Retrieve an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to be retrieved by using query parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveentitybyid
- description: Removes an specific Entity from an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeentitybyid
- description: Append new Entity attributes to an existing Entity within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: appendentityattrs
- description: Update existing Entity attributes within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateentityattrs
- description: Update existing Entity attributes within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: partialattrupdate
- description: Removes an existing Entity attribute within an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeentityattr
- description: Retrieves the subscriptions available in an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievesubscriptions
- description: Creates a new Subscription within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscription
- description: Retrieves a specific Subscription from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievesubscriptionbyid
- description: Updates a specific Subscription within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesubscription
- description: Removes a specific Subscription from an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removesubscription
- description: Retrieve a set of context sources which matches a specific query from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querycsources
- description: Registers a new context source within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registercsource
- description: Retrieves a specific context source registration from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievecsource
- description: Removes an specific context source registration within an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removecsource
- description: Retrieves the context source discovery subscriptions available in an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievecsourcesubscriptions
- description: Creates a context source discovery Subscription within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcsourcesubscription
- description: Retrieves a specific Subscription from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrievecsourcesubscriptionsbyid
- description: Updates a specific context source discovery Subscription within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecsourcesubscription
- description: Removes a specific Context Source Subscription from an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removecsourcesubscription
- description: Batch Entity creation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchentitycreation
- description: Batch Entity update
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchentityupdate
- description: Batch Entity upsert
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchentityupsert
- description: Batch Entity delete
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchentitydelete
- description: Query temporal evolution of Entities from an NGSI-LD system
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: querytemporalentities
- description: Create or update temporal representation of an Entity within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createupdateentitytemporal
- description: Retrieve the temporal representation of an specific Entity from an NGSI-LD system. It's possible to specify the Entity attributes to be retrieved by using query parameters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: retrieveentitytemporalbyid
- description: Removes the temporal representation of an Entity from an NGSI-LD system
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeentitytemporalbyid
- description: Add new attributes to an existing Temporal Entity within an NGSI-LD system
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addtemporalentityattrs
- description: Attribute from Temporal Representation of Entity deletion
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeentitytemporalattr
- description: Allows modifying a specific Attribute (Property or Relationship) instance, identified by its instanceId, of a Temporal Representation of an Entity.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: modifyentitytemporalattrinstance
- description: Attribute Instance deletion by instance id.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: removeentitytemporalattrinstance
---
