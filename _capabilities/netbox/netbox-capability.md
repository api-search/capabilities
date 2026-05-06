---
categories: []
consumed_apis: []
description: NetBox REST API API capability.
layout: capability
name: NetBox REST API
operations:
- description: Return the user making the request, if authenticated successfully.
  method: GET
  name: authentication-check-retrieve
  path: /api/authentication-check/
- description: Get a list of Circuit group assignment objects.
  method: GET
  name: circuits-circuit-group-assignments-list
  path: /api/circuits/circuit-group-assignments/
- description: Post a list of Circuit group assignment objects.
  method: POST
  name: circuits-circuit-group-assignments-create
  path: /api/circuits/circuit-group-assignments/
- description: Put a list of Circuit group assignment objects.
  method: PUT
  name: circuits-circuit-group-assignments-bulk-update
  path: /api/circuits/circuit-group-assignments/
- description: Patch a list of Circuit group assignment objects.
  method: PATCH
  name: circuits-circuit-group-assignments-bulk-partial-
  path: /api/circuits/circuit-group-assignments/
- description: Delete a list of Circuit group assignment objects.
  method: DELETE
  name: circuits-circuit-group-assignments-bulk-destroy
  path: /api/circuits/circuit-group-assignments/
- description: Get a Circuit group assignment object.
  method: GET
  name: circuits-circuit-group-assignments-retrieve
  path: /api/circuits/circuit-group-assignments/{id}/
- description: Put a Circuit group assignment object.
  method: PUT
  name: circuits-circuit-group-assignments-update
  path: /api/circuits/circuit-group-assignments/{id}/
- description: Patch a Circuit group assignment object.
  method: PATCH
  name: circuits-circuit-group-assignments-partial-updat
  path: /api/circuits/circuit-group-assignments/{id}/
- description: Delete a Circuit group assignment object.
  method: DELETE
  name: circuits-circuit-group-assignments-destroy
  path: /api/circuits/circuit-group-assignments/{id}/
- description: Get a list of circuit group objects.
  method: GET
  name: circuits-circuit-groups-list
  path: /api/circuits/circuit-groups/
- description: Post a list of circuit group objects.
  method: POST
  name: circuits-circuit-groups-create
  path: /api/circuits/circuit-groups/
- description: Put a list of circuit group objects.
  method: PUT
  name: circuits-circuit-groups-bulk-update
  path: /api/circuits/circuit-groups/
- description: Patch a list of circuit group objects.
  method: PATCH
  name: circuits-circuit-groups-bulk-partial-update
  path: /api/circuits/circuit-groups/
- description: Delete a list of circuit group objects.
  method: DELETE
  name: circuits-circuit-groups-bulk-destroy
  path: /api/circuits/circuit-groups/
- description: Get a circuit group object.
  method: GET
  name: circuits-circuit-groups-retrieve
  path: /api/circuits/circuit-groups/{id}/
- description: Put a circuit group object.
  method: PUT
  name: circuits-circuit-groups-update
  path: /api/circuits/circuit-groups/{id}/
- description: Patch a circuit group object.
  method: PATCH
  name: circuits-circuit-groups-partial-update
  path: /api/circuits/circuit-groups/{id}/
- description: Delete a circuit group object.
  method: DELETE
  name: circuits-circuit-groups-destroy
  path: /api/circuits/circuit-groups/{id}/
- description: Get a list of circuit termination objects.
  method: GET
  name: circuits-circuit-terminations-list
  path: /api/circuits/circuit-terminations/
- description: Post a list of circuit termination objects.
  method: POST
  name: circuits-circuit-terminations-create
  path: /api/circuits/circuit-terminations/
- description: Put a list of circuit termination objects.
  method: PUT
  name: circuits-circuit-terminations-bulk-update
  path: /api/circuits/circuit-terminations/
- description: Patch a list of circuit termination objects.
  method: PATCH
  name: circuits-circuit-terminations-bulk-partial-updat
  path: /api/circuits/circuit-terminations/
- description: Delete a list of circuit termination objects.
  method: DELETE
  name: circuits-circuit-terminations-bulk-destroy
  path: /api/circuits/circuit-terminations/
- description: Get a circuit termination object.
  method: GET
  name: circuits-circuit-terminations-retrieve
  path: /api/circuits/circuit-terminations/{id}/
- description: Put a circuit termination object.
  method: PUT
  name: circuits-circuit-terminations-update
  path: /api/circuits/circuit-terminations/{id}/
- description: Patch a circuit termination object.
  method: PATCH
  name: circuits-circuit-terminations-partial-update
  path: /api/circuits/circuit-terminations/{id}/
- description: Delete a circuit termination object.
  method: DELETE
  name: circuits-circuit-terminations-destroy
  path: /api/circuits/circuit-terminations/{id}/
- description: Return all CablePaths which traverse a given pass-through port.
  method: GET
  name: circuits-circuit-terminations-paths-retrieve
  path: /api/circuits/circuit-terminations/{id}/paths/
- description: Get a list of circuit type objects.
  method: GET
  name: circuits-circuit-types-list
  path: /api/circuits/circuit-types/
- description: Post a list of circuit type objects.
  method: POST
  name: circuits-circuit-types-create
  path: /api/circuits/circuit-types/
- description: Put a list of circuit type objects.
  method: PUT
  name: circuits-circuit-types-bulk-update
  path: /api/circuits/circuit-types/
- description: Patch a list of circuit type objects.
  method: PATCH
  name: circuits-circuit-types-bulk-partial-update
  path: /api/circuits/circuit-types/
- description: Delete a list of circuit type objects.
  method: DELETE
  name: circuits-circuit-types-bulk-destroy
  path: /api/circuits/circuit-types/
- description: Get a circuit type object.
  method: GET
  name: circuits-circuit-types-retrieve
  path: /api/circuits/circuit-types/{id}/
- description: Put a circuit type object.
  method: PUT
  name: circuits-circuit-types-update
  path: /api/circuits/circuit-types/{id}/
- description: Patch a circuit type object.
  method: PATCH
  name: circuits-circuit-types-partial-update
  path: /api/circuits/circuit-types/{id}/
- description: Delete a circuit type object.
  method: DELETE
  name: circuits-circuit-types-destroy
  path: /api/circuits/circuit-types/{id}/
- description: Get a list of circuit objects.
  method: GET
  name: circuits-circuits-list
  path: /api/circuits/circuits/
- description: Post a list of circuit objects.
  method: POST
  name: circuits-circuits-create
  path: /api/circuits/circuits/
- description: Put a list of circuit objects.
  method: PUT
  name: circuits-circuits-bulk-update
  path: /api/circuits/circuits/
- description: Patch a list of circuit objects.
  method: PATCH
  name: circuits-circuits-bulk-partial-update
  path: /api/circuits/circuits/
- description: Delete a list of circuit objects.
  method: DELETE
  name: circuits-circuits-bulk-destroy
  path: /api/circuits/circuits/
- description: Get a circuit object.
  method: GET
  name: circuits-circuits-retrieve
  path: /api/circuits/circuits/{id}/
- description: Put a circuit object.
  method: PUT
  name: circuits-circuits-update
  path: /api/circuits/circuits/{id}/
- description: Patch a circuit object.
  method: PATCH
  name: circuits-circuits-partial-update
  path: /api/circuits/circuits/{id}/
- description: Delete a circuit object.
  method: DELETE
  name: circuits-circuits-destroy
  path: /api/circuits/circuits/{id}/
- description: Get a list of provider account objects.
  method: GET
  name: circuits-provider-accounts-list
  path: /api/circuits/provider-accounts/
- description: Post a list of provider account objects.
  method: POST
  name: circuits-provider-accounts-create
  path: /api/circuits/provider-accounts/
- description: Put a list of provider account objects.
  method: PUT
  name: circuits-provider-accounts-bulk-update
  path: /api/circuits/provider-accounts/
- description: Patch a list of provider account objects.
  method: PATCH
  name: circuits-provider-accounts-bulk-partial-update
  path: /api/circuits/provider-accounts/
- description: Delete a list of provider account objects.
  method: DELETE
  name: circuits-provider-accounts-bulk-destroy
  path: /api/circuits/provider-accounts/
- description: Get a provider account object.
  method: GET
  name: circuits-provider-accounts-retrieve
  path: /api/circuits/provider-accounts/{id}/
- description: Put a provider account object.
  method: PUT
  name: circuits-provider-accounts-update
  path: /api/circuits/provider-accounts/{id}/
- description: Patch a provider account object.
  method: PATCH
  name: circuits-provider-accounts-partial-update
  path: /api/circuits/provider-accounts/{id}/
- description: Delete a provider account object.
  method: DELETE
  name: circuits-provider-accounts-destroy
  path: /api/circuits/provider-accounts/{id}/
- description: Get a list of provider network objects.
  method: GET
  name: circuits-provider-networks-list
  path: /api/circuits/provider-networks/
- description: Post a list of provider network objects.
  method: POST
  name: circuits-provider-networks-create
  path: /api/circuits/provider-networks/
- description: Put a list of provider network objects.
  method: PUT
  name: circuits-provider-networks-bulk-update
  path: /api/circuits/provider-networks/
- description: Patch a list of provider network objects.
  method: PATCH
  name: circuits-provider-networks-bulk-partial-update
  path: /api/circuits/provider-networks/
personas: []
provider_name: NetBox
provider_slug: netbox
search_terms:
- circuits circuit group assignments bulk update
- circuits circuit groups retrieve
- circuits circuit group assignments retrieve
- put a list of provider network objects.
- get a circuit type object.
- delete a circuit object.
- circuits provider accounts update
- get a circuit group assignment object.
- get a list of circuit type objects.
- delete a list of circuit group assignment objects.
- circuits circuit terminations partial update
- circuits provider networks bulk partial update
- patch a circuit object.
- network management
- patch a list of circuit group objects.
- circuits circuits destroy
- get a provider account object.
- circuits circuit types partial update
- delete a circuit group assignment object.
- get a list of circuit group assignment objects.
- circuits circuit groups destroy
- api
- netbox
- delete a list of circuit termination objects.
- circuits circuit types list
- get a list of provider account objects.
- circuits provider accounts retrieve
- delete a circuit group object.
- circuits provider accounts create
- network automation
- circuits circuit terminations create
- circuits circuits bulk update
- post a list of provider network objects.
- circuits circuit groups create
- post a list of circuit objects.
- patch a list of provider account objects.
- circuits provider networks create
- delete a circuit type object.
- circuits circuit types bulk partial update
- circuits provider accounts bulk update
- get a list of circuit group objects.
- circuits circuit group assignments create
- dcim
- circuits circuit terminations paths retrieve
- circuits circuit group assignments destroy
- circuits circuit types bulk destroy
- circuits provider accounts bulk destroy
- post a list of circuit type objects.
- circuits circuit group assignments list
- get a circuit termination object.
- open source
- patch a circuit type object.
- circuits circuit group assignments update
- circuits circuit terminations list
- return all cablepaths which traverse a given pass-through port.
- data center
- circuits circuit types destroy
- put a circuit group object.
- patch a provider account object.
- delete a list of circuit type objects.
- patch a list of circuit type objects.
- put a circuit termination object.
- circuits circuit groups bulk partial update
- patch a list of circuit termination objects.
- circuits circuit groups bulk update
- patch a list of provider network objects.
- put a list of provider account objects.
- circuits circuit terminations destroy
- infrastructure as code
- put a provider account object.
- patch a circuit group object.
- circuits circuit terminations bulk partial updat
- circuits circuits update
- delete a circuit termination object.
- put a circuit object.
- circuits circuits retrieve
- patch a circuit group assignment object.
- circuits circuits bulk partial update
- circuits circuit groups bulk destroy
- get a list of provider network objects.
- circuits circuit terminations bulk destroy
- circuits circuits create
- delete a provider account object.
- circuits provider accounts bulk partial update
- get a list of circuit termination objects.
- circuits circuit groups partial update
- circuits provider accounts partial update
- circuits circuit groups update
- circuits circuit terminations bulk update
- put a list of circuit type objects.
- get a circuit group object.
- circuits circuit types create
- get a list of circuit objects.
- circuits circuit group assignments partial updat
- delete a list of circuit objects.
- circuits circuit terminations update
- put a list of circuit group assignment objects.
- circuits circuit groups list
- return the user making the request, if authenticated successfully.
- put a list of circuit group objects.
- circuits circuit group assignments bulk destroy
- post a list of circuit termination objects.
- post a list of provider account objects.
- post a list of circuit group assignment objects.
- circuits circuits list
- circuits circuit group assignments bulk partial
- circuits circuit types retrieve
- authentication check retrieve
- circuits provider accounts list
- put a circuit group assignment object.
- put a list of circuit termination objects.
- get a circuit object.
- ipam
- circuits circuit terminations retrieve
- circuits provider accounts destroy
- circuits circuit types update
- post a list of circuit group objects.
- source of truth
- circuits circuits bulk destroy
- circuits provider networks list
- circuits provider networks bulk update
- delete a list of circuit group objects.
- patch a list of circuit group assignment objects.
- patch a circuit termination object.
- delete a list of provider account objects.
- circuits circuits partial update
- put a circuit type object.
- circuits circuit types bulk update
- put a list of circuit objects.
- patch a list of circuit objects.
slug: netbox-capability
source_filename: netbox-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NetBox REST API\n  description: NetBox REST API API capability.\n  tags:\n  - Netbox\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: netbox\n    baseUri: ''\n    description: NetBox REST API HTTP API.\n    authentication:\n      type: apikey\n      in: cookie\n      name: sessionid\n      value: '{{NETBOX_TOKEN}}'\n    resources:\n    - name: api-authentication-check\n      path: /api/authentication-check/\n      operations:\n      - name: authentication-check-retrieve\n        method: GET\n        description: Return the user making the request, if authenticated successfully.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-circuits-circuit-group-assignments\n      path: /api/circuits/circuit-group-assignments/\n      operations:\n      - name: circuits-circuit-group-assignments-list\n\
  \        method: GET\n        description: Get a list of Circuit group assignment objects.\n        inputParameters:\n        - name: circuit\n          in: query\n          type: array\n        - name: circuit_id\n          in: query\n          type: array\n        - name: created\n          in: query\n          type: array\n        - name: created__empty\n          in: query\n          type: array\n        - name: created__gt\n          in: query\n          type: array\n        - name: created__gte\n          in: query\n          type: array\n        - name: created__lt\n          in: query\n          type: array\n        - name: created__lte\n          in: query\n          type: array\n        - name: created__n\n          in: query\n          type: array\n        - name: created_by_request\n          in: query\n          type: string\n        - name: group\n          in: query\n          type: array\n          description: Circuit group (slug)\n        - name: group__n\n          in:\
  \ query\n          type: array\n          description: Circuit group (slug)\n        - name: group_id\n          in: query\n          type: array\n          description: Circuit group (ID)\n        - name: group_id__n\n          in: query\n          type: array\n          description: Circuit group (ID)\n        - name: id\n          in: query\n          type: array\n        - name: id__empty\n          in: query\n          type: boolean\n        - name: id__gt\n          in: query\n          type: array\n        - name: id__gte\n          in: query\n          type: array\n        - name: id__lt\n          in: query\n          type: array\n        - name: id__lte\n          in: query\n          type: array\n        - name: id__n\n          in: query\n          type: array\n        - name: last_updated\n          in: query\n          type: array\n        - name: last_updated__empty\n          in: query\n          type: array\n        - name: last_updated__gt\n          in: query\n     \
  \     type: array\n        - name: last_updated__gte\n          in: query\n          type: array\n        - name: last_updated__lt\n          in: query\n          type: array\n        - name: last_updated__lte\n          in: query\n          type: array\n        - name: last_updated__n\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: member_id\n          in: query\n          type: array\n        - name: member_id__empty\n          in: query\n          type: boolean\n        - name: member_id__gt\n          in: query\n          type: array\n        - name: member_id__gte\n          in: query\n          type: array\n        - name: member_id__lt\n          in: query\n          type: array\n        - name: member_id__lte\n          in: query\n          type: array\n        - name: member_id__n\n          in: query\n          type: array\n        -\
  \ name: member_type\n          in: query\n          type: array\n        - name: member_type__n\n          in: query\n          type: array\n        - name: modified_by_request\n          in: query\n          type: string\n        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: priority\n          in: query\n          type: string\n          description: '* `primary` - Primary * `secondary` - Secondary * `tertiary` - Tertiary * `inactive` - Inactive'\n        - name: priority__empty\n          in: query\n          type: boolean\n        - name: priority__ic\n          in: query\n          type: array\n        - name: priority__ie\n          in: query\n          type: array\n        - name: priority__iew\n          in: query\n          type: array\n\
  \        - name: priority__iregex\n          in: query\n          type: array\n        - name: priority__isw\n          in: query\n          type: array\n        - name: priority__n\n          in: query\n          type: string\n          description: '* `primary` - Primary * `secondary` - Secondary * `tertiary` - Tertiary * `inactive` - Inactive'\n        - name: priority__nic\n          in: query\n          type: array\n        - name: priority__nie\n          in: query\n          type: array\n        - name: priority__niew\n          in: query\n          type: array\n        - name: priority__nisw\n          in: query\n          type: array\n        - name: priority__regex\n          in: query\n          type: array\n        - name: provider\n          in: query\n          type: array\n        - name: provider_id\n          in: query\n          type: array\n        - name: q\n          in: query\n          type: string\n          description: Search\n        - name: tag\n          in:\
  \ query\n          type: array\n        - name: tag__n\n          in: query\n          type: array\n        - name: tag_id\n          in: query\n          type: array\n        - name: tag_id__n\n          in: query\n          type: array\n        - name: updated_by_request\n          in: query\n          type: string\n        - name: virtual_circuit\n          in: query\n          type: array\n        - name: virtual_circuit_id\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-create\n        method: POST\n        description: Post a list of Circuit group assignment objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-bulk-update\n        method: PUT\n        description: Put a list of Circuit\
  \ group assignment objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-bulk-partial-\n        method: PATCH\n        description: Patch a list of Circuit group assignment objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-bulk-destroy\n        method: DELETE\n        description: Delete a list of Circuit group assignment objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-circuits-circuit-group-assignments-id\n      path: /api/circuits/circuit-group-assignments/{id}/\n      operations:\n      - name: circuits-circuit-group-assignments-retrieve\n        method: GET\n        description: Get a Circuit group assignment object.\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this Circuit group assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-update\n        method: PUT\n        description: Put a Circuit group assignment object.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this Circuit group assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-partial-updat\n        method: PATCH\n        description: Patch a Circuit group assignment object.\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this Circuit group assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-group-assignments-destroy\n        method: DELETE\n        description: Delete a Circuit group assignment object.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this Circuit group assignment.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-circuits-circuit-groups\n      path: /api/circuits/circuit-groups/\n      operations:\n      - name: circuits-circuit-groups-list\n        method: GET\n        description: Get a list of circuit group objects.\n\
  \        inputParameters:\n        - name: created\n          in: query\n          type: array\n        - name: created__empty\n          in: query\n          type: array\n        - name: created__gt\n          in: query\n          type: array\n        - name: created__gte\n          in: query\n          type: array\n        - name: created__lt\n          in: query\n          type: array\n        - name: created__lte\n          in: query\n          type: array\n        - name: created__n\n          in: query\n          type: array\n        - name: created_by_request\n          in: query\n          type: string\n        - name: description\n          in: query\n          type: array\n        - name: description__empty\n          in: query\n          type: boolean\n        - name: description__ic\n          in: query\n          type: array\n        - name: description__ie\n          in: query\n          type: array\n        - name: description__iew\n          in: query\n          type: array\n\
  \        - name: description__iregex\n          in: query\n          type: array\n        - name: description__isw\n          in: query\n          type: array\n        - name: description__n\n          in: query\n          type: array\n        - name: description__nic\n          in: query\n          type: array\n        - name: description__nie\n          in: query\n          type: array\n        - name: description__niew\n          in: query\n          type: array\n        - name: description__nisw\n          in: query\n          type: array\n        - name: description__regex\n          in: query\n          type: array\n        - name: id\n          in: query\n          type: array\n        - name: id__empty\n          in: query\n          type: boolean\n        - name: id__gt\n          in: query\n          type: array\n        - name: id__gte\n          in: query\n          type: array\n        - name: id__lt\n          in: query\n          type: array\n        - name: id__lte\n  \
  \        in: query\n          type: array\n        - name: id__n\n          in: query\n          type: array\n        - name: last_updated\n          in: query\n          type: array\n        - name: last_updated__empty\n          in: query\n          type: array\n        - name: last_updated__gt\n          in: query\n          type: array\n        - name: last_updated__gte\n          in: query\n          type: array\n        - name: last_updated__lt\n          in: query\n          type: array\n        - name: last_updated__lte\n          in: query\n          type: array\n        - name: last_updated__n\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: modified_by_request\n          in: query\n          type: string\n        - name: name\n          in: query\n          type: array\n        - name: name__empty\n          in: query\n          type:\
  \ boolean\n        - name: name__ic\n          in: query\n          type: array\n        - name: name__ie\n          in: query\n          type: array\n        - name: name__iew\n          in: query\n          type: array\n        - name: name__iregex\n          in: query\n          type: array\n        - name: name__isw\n          in: query\n          type: array\n        - name: name__n\n          in: query\n          type: array\n        - name: name__nic\n          in: query\n          type: array\n        - name: name__nie\n          in: query\n          type: array\n        - name: name__niew\n          in: query\n          type: array\n        - name: name__nisw\n          in: query\n          type: array\n        - name: name__regex\n          in: query\n          type: array\n        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n        - name: ordering\n          in: query\n          type:\
  \ string\n          description: Which field to use when ordering the results.\n        - name: owner\n          in: query\n          type: array\n          description: Owner (name)\n        - name: owner__n\n          in: query\n          type: array\n          description: Owner (name)\n        - name: owner_group\n          in: query\n          type: array\n          description: Owner Group (name)\n        - name: owner_group__n\n          in: query\n          type: array\n          description: Owner Group (name)\n        - name: owner_group_id\n          in: query\n          type: array\n          description: Owner Group (ID)\n        - name: owner_group_id__n\n          in: query\n          type: array\n          description: Owner Group (ID)\n        - name: owner_id\n          in: query\n          type: array\n          description: Owner (ID)\n        - name: owner_id__n\n          in: query\n          type: array\n          description: Owner (ID)\n        - name: q\n    \
  \      in: query\n          type: string\n          description: Search\n        - name: slug\n          in: query\n          type: array\n        - name: slug__empty\n          in: query\n          type: boolean\n        - name: slug__ic\n          in: query\n          type: array\n        - name: slug__ie\n          in: query\n          type: array\n        - name: slug__iew\n          in: query\n          type: array\n        - name: slug__iregex\n          in: query\n          type: array\n        - name: slug__isw\n          in: query\n          type: array\n        - name: slug__n\n          in: query\n          type: array\n        - name: slug__nic\n          in: query\n          type: array\n        - name: slug__nie\n          in: query\n          type: array\n        - name: slug__niew\n          in: query\n          type: array\n        - name: slug__nisw\n          in: query\n          type: array\n        - name: slug__regex\n          in: query\n          type: array\n \
  \       - name: tag\n          in: query\n          type: array\n        - name: tag__n\n          in: query\n          type: array\n        - name: tag_id\n          in: query\n          type: array\n        - name: tag_id__n\n          in: query\n          type: array\n        - name: tenant\n          in: query\n          type: array\n          description: Tenant (slug)\n        - name: tenant__n\n          in: query\n          type: array\n          description: Tenant (slug)\n        - name: tenant_group\n          in: query\n          type: array\n        - name: tenant_group__n\n          in: query\n          type: array\n        - name: tenant_group_id\n          in: query\n          type: array\n        - name: tenant_group_id__n\n          in: query\n          type: array\n        - name: tenant_id\n          in: query\n          type: array\n          description: Tenant (ID)\n        - name: tenant_id__n\n          in: query\n          type: array\n          description: Tenant\
  \ (ID)\n        - name: updated_by_request\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-create\n        method: POST\n        description: Post a list of circuit group objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-bulk-update\n        method: PUT\n        description: Put a list of circuit group objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-bulk-partial-update\n        method: PATCH\n        description: Patch a list of circuit group objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: circuits-circuit-groups-bulk-destroy\n        method: DELETE\n        description: Delete a list of circuit group objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-circuits-circuit-groups-id\n      path: /api/circuits/circuit-groups/{id}/\n      operations:\n      - name: circuits-circuit-groups-retrieve\n        method: GET\n        description: Get a circuit group object.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this circuit group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-update\n        method: PUT\n        description: Put a circuit group object.\n        inputParameters:\n        - name: id\n          in: path\n\
  \          type: integer\n          required: true\n          description: A unique integer value identifying this circuit group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-partial-update\n        method: PATCH\n        description: Patch a circuit group object.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying this circuit group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-groups-destroy\n        method: DELETE\n        description: Delete a circuit group object.\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: A unique integer value identifying\
  \ this circuit group.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-circuits-circuit-terminations\n      path: /api/circuits/circuit-terminations/\n      operations:\n      - name: circuits-circuit-terminations-list\n        method: GET\n        description: Get a list of circuit termination objects.\n        inputParameters:\n        - name: cable_connector\n          in: query\n          type: array\n        - name: cable_connector__empty\n          in: query\n          type: boolean\n        - name: cable_connector__gt\n          in: query\n          type: array\n        - name: cable_connector__gte\n          in: query\n          type: array\n        - name: cable_connector__lt\n          in: query\n          type: array\n        - name: cable_connector__lte\n          in: query\n          type: array\n        - name: cable_connector__n\n          in: query\n          type: array\n   \
  \     - name: cable_end\n          in: query\n          type: string\n          description: '* `A` - A * `B` - B'\n        - name: cable_end__empty\n          in: query\n          type: boolean\n        - name: cable_end__ic\n          in: query\n          type: array\n        - name: cable_end__ie\n          in: query\n          type: array\n        - name: cable_end__iew\n          in: query\n          type: array\n        - name: cable_end__iregex\n          in: query\n          type: array\n        - name: cable_end__isw\n          in: query\n          type: array\n        - name: cable_end__n\n          in: query\n          type: string\n          description: '* `A` - A * `B` - B'\n        - name: cable_end__nic\n          in: query\n          type: array\n        - name: cable_end__nie\n          in: query\n          type: array\n        - name: cable_end__niew\n          in: query\n          type: array\n        - name: cable_end__nisw\n          in: query\n          type: array\n\
  \        - name: cable_end__regex\n          in: query\n          type: array\n        - name: cable_id\n          in: query\n          type: array\n          description: Cable (ID)\n        - name: cable_id__n\n          in: query\n          type: array\n          description: Cable (ID)\n        - name: cabled\n          in: query\n          type: boolean\n        - name: circuit_id\n          in: query\n          type: array\n          description: Circuit\n        - name: circuit_id__n\n          in: query\n          type: array\n          description: Circuit\n        - name: created\n          in: query\n          type: array\n        - name: created__empty\n          in: query\n          type: array\n        - name: created__gt\n          in: query\n          type: array\n        - name: created__gte\n          in: query\n          type: array\n        - name: created__lt\n          in: query\n          type: array\n        - name: created__lte\n          in: query\n          type:\
  \ array\n        - name: created__n\n          in: query\n          type: array\n        - name: created_by_request\n          in: query\n          type: string\n        - name: description\n          in: query\n          type: array\n        - name: description__empty\n          in: query\n          type: boolean\n        - name: description__ic\n          in: query\n          type: array\n        - name: description__ie\n          in: query\n          type: array\n        - name: description__iew\n          in: query\n          type: array\n        - name: description__iregex\n          in: query\n          type: array\n        - name: description__isw\n          in: query\n          type: array\n        - name: description__n\n          in: query\n          type: array\n        - name: description__nic\n          in: query\n          type: array\n        - name: description__nie\n          in: query\n          type: array\n        - name: description__niew\n          in: query\n   \
  \       type: array\n        - name: description__nisw\n          in: query\n          type: array\n        - name: description__regex\n          in: query\n          type: array\n        - name: id\n          in: query\n          type: array\n        - name: id__empty\n          in: query\n          type: boolean\n        - name: id__gt\n          in: query\n          type: array\n        - name: id__gte\n          in: query\n          type: array\n        - name: id__lt\n          in: query\n          type: array\n        - name: id__lte\n          in: query\n          type: array\n        - name: id__n\n          in: query\n          type: array\n        - name: last_updated\n          in: query\n          type: array\n        - name: last_updated__empty\n          in: query\n          type: array\n        - name: last_updated__gt\n          in: query\n          type: array\n        - name: last_updated__gte\n          in: query\n          type: array\n        - name: last_updated__lt\n\
  \          in: query\n          type: array\n        - name: last_updated__lte\n          in: query\n          type: array\n        - name: last_updated__n\n          in: query\n          type: array\n        - name: limit\n          in: query\n          type: integer\n          description: Number of results to return per page.\n        - name: location\n          in: query\n          type: array\n        - name: location__n\n          in: query\n          type: array\n        - name: location_id\n          in: query\n          type: array\n        - name: location_id__n\n          in: query\n          type: array\n        - name: mark_connected\n          in: query\n          type: boolean\n        - name: modified_by_request\n          in: query\n          type: string\n        - name: occupied\n          in: query\n          type: boolean\n        - name: offset\n          in: query\n          type: integer\n          description: The initial index from which to return the results.\n\
  \        - name: ordering\n          in: query\n          type: string\n          description: Which field to use when ordering the results.\n        - name: port_speed\n          in: query\n          type: array\n        - name: port_speed__empty\n          in: query\n          type: boolean\n        - name: port_speed__gt\n          in: query\n          type: array\n        - name: port_speed__gte\n          in: query\n          type: array\n        - name: port_speed__lt\n          in: query\n          type: array\n        - name: port_speed__lte\n          in: query\n          type: array\n        - name: port_speed__n\n          in: query\n          type: array\n        - name: pp_info\n          in: query\n          type: array\n        - name: pp_info__empty\n          in: query\n          type: boolean\n        - name: pp_info__ic\n          in: query\n          type: array\n        - name: pp_info__ie\n          in: query\n          type: array\n        - name: pp_info__iew\n\
  \          in: query\n          type: array\n        - name: pp_info__iregex\n          in: query\n          type: array\n        - name: pp_info__isw\n          in: query\n          type: array\n        - name: pp_info__n\n          in: query\n          type: array\n        - name: pp_info__nic\n          in: query\n          type: array\n        - name: pp_info__nie\n          in: query\n          type: array\n        - name: pp_info__niew\n          in: query\n          type: array\n        - name: pp_info__nisw\n          in: query\n          type: array\n        - name: pp_info__regex\n          in: query\n          type: array\n        - name: provider\n          in: query\n          type: array\n          description: Provider (slug)\n        - name: provider__n\n          in: query\n          type: array\n          description: Provider (slug)\n        - name: provider_id\n          in: query\n          type: array\n          description: Provider (ID)\n        - name: provider_id__n\n\
  \          in: query\n          type: array\n          description: Provider (ID)\n        - name: provider_network_id\n          in: query\n          type: array\n          description: ProviderNetwork (ID)\n        - name: provider_network_id__n\n          in: query\n          type: array\n          description: ProviderNetwork (ID)\n        - name: q\n          in: query\n          type: string\n          description: Search\n        - name: region\n          in: query\n          type: array\n        - name: region__n\n          in: query\n          type: array\n        - name: region_id\n          in: query\n          type: array\n        - name: region_id__n\n          in: query\n          type: array\n        - name: site\n          in: query\n          type: array\n          description: Site (slug)\n        - name: site__n\n          in: query\n          type: array\n          description: Site (slug)\n        - name: site_group\n          in: query\n          type: array\n   \
  \     - name: site_group__n\n          in: query\n          type: array\n        - name: site_group_id\n          in: query\n          type: array\n        - name: site_group_id__n\n          in: query\n          type: array\n        - name: site_id\n          in: query\n          type: array\n          description: Site (ID)\n        - name: site_id__n\n          in: query\n          type: array\n          description: Site (ID)\n        - name: tag\n          in: query\n          type: array\n        - name: tag__n\n          in: query\n          type: array\n        - name: tag_id\n          in: query\n          type: array\n        - name: tag_id__n\n          in: query\n          type: array\n        - name: term_side\n          in: query\n          type: string\n          description: '* `A` - A * `Z` - Z'\n        - name: term_side__empty\n          in: query\n          type: boolean\n        - name: term_side__ic\n          in: query\n          type: array\n        - name: term_side__ie\n\
  \          in: query\n          type: array\n        - name: term_side__iew\n          in: query\n          type: array\n        - name: term_side__iregex\n          in: query\n          type: array\n        - name: term_side__isw\n          in: query\n          type: array\n        - name: term_side__n\n          in: query\n          type: string\n          description: '* `A` - A * `Z` - Z'\n        - name: term_side__nic\n          in: query\n          type: array\n        - name: term_side__nie\n          in: query\n          type: array\n        - name: term_side__niew\n          in: query\n          type: array\n        - name: term_side__nisw\n          in: query\n          type: array\n        - name: term_side__regex\n          in: query\n          type: array\n        - name: termination_id\n          in: query\n          type: array\n        - name: termination_id__empty\n          in: query\n          type: boolean\n        - name: termination_id__gt\n          in: query\n\
  \          type: array\n        - name: termination_id__gte\n          in: query\n          type: array\n        - name: termination_id__lt\n          in: query\n          type: array\n        - name: termination_id__lte\n          in: query\n          type: array\n        - name: termination_id__n\n          in: query\n          type: array\n        - name: termination_type\n          in: query\n          type: array\n        - name: termination_type__n\n          in: query\n          type: array\n        - name: updated_by_request\n          in: query\n          type: string\n        - name: upstream_speed\n          in: query\n          type: array\n        - name: upstream_speed__empty\n          in: query\n          type: boolean\n        - name: upstream_speed__gt\n          in: query\n          type: array\n        - name: upstream_speed__gte\n          in: query\n          type: array\n        - name: upstream_speed__lt\n          in: query\n          type: array\n        - name:\
  \ upstream_speed__lte\n          in: query\n          type: array\n        - name: upstream_speed__n\n          in: query\n          type: array\n        - name: xconnect_id\n          in: query\n          type: array\n        - name: xconnect_id__empty\n          in: query\n          type: boolean\n        - name: xconnect_id__ic\n          in: query\n          type: array\n        - name: xconnect_id__ie\n          in: query\n          type: array\n        - name: xconnect_id__iew\n          in: query\n          type: array\n        - name: xconnect_id__iregex\n          in: query\n          type: array\n        - name: xconnect_id__isw\n          in: query\n          type: array\n        - name: xconnect_id__n\n          in: query\n          type: array\n        - name: xconnect_id__nic\n          in: query\n          type: array\n        - name: xconnect_id__nie\n          in: query\n          type: array\n        - name: xconnect_id__niew\n          in: query\n          type: array\n\
  \        - name: xconnect_id__nisw\n          in: query\n          type: array\n        - name: xconnect_id__regex\n          in: query\n          type: array\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-terminations-create\n        method: POST\n        description: Post a list of circuit termination objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-terminations-bulk-update\n        method: PUT\n        description: Put a list of circuit termination objects.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: circuits-circuit-terminations-bulk-partial-updat\n        method: PATCH\n        description: Patch a list of circuit termination o\n\n# --- truncated at 32 KB (215\
  \ KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/netbox/refs/heads/main/capabilities/netbox-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netbox/refs/heads/main/capabilities/netbox-capability.yaml
tags:
- Netbox
- API
tools:
- description: Return the user making the request, if authenticated successfully.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: authentication-check-retrieve
- description: Get a list of Circuit group assignment objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-group-assignments-list
- description: Post a list of Circuit group assignment objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-group-assignments-create
- description: Put a list of Circuit group assignment objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-group-assignments-bulk-update
- description: Patch a list of Circuit group assignment objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-group-assignments-bulk-partial-
- description: Delete a list of Circuit group assignment objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-group-assignments-bulk-destroy
- description: Get a Circuit group assignment object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-group-assignments-retrieve
- description: Put a Circuit group assignment object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-group-assignments-update
- description: Patch a Circuit group assignment object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-group-assignments-partial-updat
- description: Delete a Circuit group assignment object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-group-assignments-destroy
- description: Get a list of circuit group objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-groups-list
- description: Post a list of circuit group objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-groups-create
- description: Put a list of circuit group objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-groups-bulk-update
- description: Patch a list of circuit group objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-groups-bulk-partial-update
- description: Delete a list of circuit group objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-groups-bulk-destroy
- description: Get a circuit group object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-groups-retrieve
- description: Put a circuit group object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-groups-update
- description: Patch a circuit group object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-groups-partial-update
- description: Delete a circuit group object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-groups-destroy
- description: Get a list of circuit termination objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-terminations-list
- description: Post a list of circuit termination objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-terminations-create
- description: Put a list of circuit termination objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-terminations-bulk-update
- description: Patch a list of circuit termination objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-terminations-bulk-partial-updat
- description: Delete a list of circuit termination objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-terminations-bulk-destroy
- description: Get a circuit termination object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-terminations-retrieve
- description: Put a circuit termination object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-terminations-update
- description: Patch a circuit termination object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-terminations-partial-update
- description: Delete a circuit termination object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-terminations-destroy
- description: Return all CablePaths which traverse a given pass-through port.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-terminations-paths-retrieve
- description: Get a list of circuit type objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-types-list
- description: Post a list of circuit type objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-types-create
- description: Put a list of circuit type objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-types-bulk-update
- description: Patch a list of circuit type objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-types-bulk-partial-update
- description: Delete a list of circuit type objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-types-bulk-destroy
- description: Get a circuit type object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuit-types-retrieve
- description: Put a circuit type object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuit-types-update
- description: Patch a circuit type object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuit-types-partial-update
- description: Delete a circuit type object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuit-types-destroy
- description: Get a list of circuit objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuits-list
- description: Post a list of circuit objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuits-create
- description: Put a list of circuit objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuits-bulk-update
- description: Patch a list of circuit objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuits-bulk-partial-update
- description: Delete a list of circuit objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuits-bulk-destroy
- description: Get a circuit object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-circuits-retrieve
- description: Put a circuit object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-circuits-update
- description: Patch a circuit object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-circuits-partial-update
- description: Delete a circuit object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-circuits-destroy
- description: Get a list of provider account objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-provider-accounts-list
- description: Post a list of provider account objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-provider-accounts-create
- description: Put a list of provider account objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-provider-accounts-bulk-update
- description: Patch a list of provider account objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-provider-accounts-bulk-partial-update
- description: Delete a list of provider account objects.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-provider-accounts-bulk-destroy
- description: Get a provider account object.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-provider-accounts-retrieve
- description: Put a provider account object.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-provider-accounts-update
- description: Patch a provider account object.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-provider-accounts-partial-update
- description: Delete a provider account object.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: circuits-provider-accounts-destroy
- description: Get a list of provider network objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: circuits-provider-networks-list
- description: Post a list of provider network objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-provider-networks-create
- description: Put a list of provider network objects.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: circuits-provider-networks-bulk-update
- description: Patch a list of provider network objects.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: circuits-provider-networks-bulk-partial-update
---
