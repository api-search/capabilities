---
categories: []
consumed_apis: []
description: '# Overview This is the official documentation for the Hetzner Cloud API. ## Introduction The Hetzner Cloud API operates over HTTPS and uses JSON as its data format. The API is a RESTful API and utilizes HTTP methods and HTTP status codes to specify requests and responses. As an alternative to working directly with our API you may also consider to use: - Our CLI program [hcloud](https://github.com/hetznercloud/cli) - Our [library for Go](https://github.com/hetznercloud/hcloud-go) - Our [library for Python](https://github.com/hetznercloud/hcloud-python) You can find even more libraries, tools an'
layout: capability
name: Hetzner Cloud API
operations:
- description: Get multiple Actions
  method: GET
  name: get-actions
  path: /actions
- description: Get an Action
  method: GET
  name: get-action
  path: /actions/{id}
- description: List Certificates
  method: GET
  name: list-certificates
  path: /certificates
- description: Create a Certificate
  method: POST
  name: create-certificate
  path: /certificates
- description: List Actions
  method: GET
  name: list-certificates-actions
  path: /certificates/actions
- description: Get an Action
  method: GET
  name: get-certificates-action
  path: /certificates/actions/{id}
- description: Get a Certificate
  method: GET
  name: get-certificate
  path: /certificates/{id}
- description: Update a Certificate
  method: PUT
  name: update-certificate
  path: /certificates/{id}
- description: Delete a Certificate
  method: DELETE
  name: delete-certificate
  path: /certificates/{id}
- description: List Actions for a Certificate
  method: GET
  name: list-certificate-actions
  path: /certificates/{id}/actions
- description: Retry Issuance or Renewal
  method: POST
  name: retry-certificate
  path: /certificates/{id}/actions/retry
- description: Get an Action for a Certificate
  method: GET
  name: get-certificate-action
  path: /certificates/{id}/actions/{action_id}
- description: List Data Centers
  method: GET
  name: list-datacenters
  path: /datacenters
- description: Get a Data Center
  method: GET
  name: get-datacenter
  path: /datacenters/{id}
- description: List Firewalls
  method: GET
  name: list-firewalls
  path: /firewalls
- description: Create a Firewall
  method: POST
  name: create-firewall
  path: /firewalls
- description: List Actions
  method: GET
  name: list-firewalls-actions
  path: /firewalls/actions
- description: Get an Action
  method: GET
  name: get-firewalls-action
  path: /firewalls/actions/{id}
- description: Get a Firewall
  method: GET
  name: get-firewall
  path: /firewalls/{id}
- description: Update a Firewall
  method: PUT
  name: update-firewall
  path: /firewalls/{id}
- description: Delete a Firewall
  method: DELETE
  name: delete-firewall
  path: /firewalls/{id}
- description: List Actions for a Firewall
  method: GET
  name: list-firewall-actions
  path: /firewalls/{id}/actions
- description: Apply to Resources
  method: POST
  name: apply-firewall-to-resources
  path: /firewalls/{id}/actions/apply_to_resources
- description: Remove from Resources
  method: POST
  name: remove-firewall-from-resources
  path: /firewalls/{id}/actions/remove_from_resources
- description: Set Rules
  method: POST
  name: set-firewall-rules
  path: /firewalls/{id}/actions/set_rules
- description: Get an Action for a Firewall
  method: GET
  name: get-firewall-action
  path: /firewalls/{id}/actions/{action_id}
- description: List Floating IPs
  method: GET
  name: list-floating-ips
  path: /floating_ips
- description: Create a Floating IP
  method: POST
  name: create-floating-ip
  path: /floating_ips
- description: List Actions
  method: GET
  name: list-floating-ips-actions
  path: /floating_ips/actions
- description: Get an Action
  method: GET
  name: get-floating-ips-action
  path: /floating_ips/actions/{id}
- description: Get a Floating IP
  method: GET
  name: get-floating-ip
  path: /floating_ips/{id}
- description: Update a Floating IP
  method: PUT
  name: update-floating-ip
  path: /floating_ips/{id}
- description: Delete a Floating IP
  method: DELETE
  name: delete-floating-ip
  path: /floating_ips/{id}
- description: List Actions for a Floating IP
  method: GET
  name: list-floating-ip-actions
  path: /floating_ips/{id}/actions
- description: Assign a Floating IP to a Server
  method: POST
  name: assign-floating-ip
  path: /floating_ips/{id}/actions/assign
- description: Change reverse DNS records for a Floating IP
  method: POST
  name: change-floating-ip-dns-ptr
  path: /floating_ips/{id}/actions/change_dns_ptr
- description: Change Floating IP Protection
  method: POST
  name: change-floating-ip-protection
  path: /floating_ips/{id}/actions/change_protection
- description: Unassign a Floating IP
  method: POST
  name: unassign-floating-ip
  path: /floating_ips/{id}/actions/unassign
- description: Get an Action for a Floating IP
  method: GET
  name: get-floating-ip-action
  path: /floating_ips/{id}/actions/{action_id}
- description: List Images
  method: GET
  name: list-images
  path: /images
- description: List Actions
  method: GET
  name: list-images-actions
  path: /images/actions
- description: Get an Action
  method: GET
  name: get-images-action
  path: /images/actions/{id}
- description: Get an Image
  method: GET
  name: get-image
  path: /images/{id}
- description: Update an Image
  method: PUT
  name: update-image
  path: /images/{id}
- description: Delete an Image
  method: DELETE
  name: delete-image
  path: /images/{id}
- description: List Actions for an Image
  method: GET
  name: list-image-actions
  path: /images/{id}/actions
- description: Change Image Protection
  method: POST
  name: change-image-protection
  path: /images/{id}/actions/change_protection
- description: Get an Action for an Image
  method: GET
  name: get-image-action
  path: /images/{id}/actions/{action_id}
- description: List ISOs
  method: GET
  name: list-isos
  path: /isos
- description: Get an ISO
  method: GET
  name: get-iso
  path: /isos/{id}
- description: List Load Balancer Types
  method: GET
  name: list-load-balancer-types
  path: /load_balancer_types
- description: Get a Load Balancer Type
  method: GET
  name: get-load-balancer-type
  path: /load_balancer_types/{id}
- description: List Load Balancers
  method: GET
  name: list-load-balancers
  path: /load_balancers
- description: Create a Load Balancer
  method: POST
  name: create-load-balancer
  path: /load_balancers
- description: List Actions
  method: GET
  name: list-load-balancers-actions
  path: /load_balancers/actions
- description: Get an Action
  method: GET
  name: get-load-balancers-action
  path: /load_balancers/actions/{id}
- description: Get a Load Balancer
  method: GET
  name: get-load-balancer
  path: /load_balancers/{id}
- description: Update a Load Balancer
  method: PUT
  name: update-load-balancer
  path: /load_balancers/{id}
- description: Delete a Load Balancer
  method: DELETE
  name: delete-load-balancer
  path: /load_balancers/{id}
- description: List Actions for a Load Balancer
  method: GET
  name: list-load-balancer-actions
  path: /load_balancers/{id}/actions
personas: []
provider_name: Hetzner
provider_slug: hetzner
search_terms:
- hetzner
- get floating ips action
- change reverse dns records for a floating ip
- create a load balancer
- list load balancers
- dns
- retry certificate
- update floating ip
- change image protection
- get certificate action
- list images actions
- list actions for a certificate
- get multiple actions
- list firewalls actions
- update a firewall
- get images action
- create floating ip
- set firewall rules
- update firewall
- set rules
- list floating ips actions
- api
- get certificate
- get firewall
- get load balancers action
- delete image
- create certificate
- servers
- get a data center
- get load balancer
- get an action for a floating ip
- get action
- delete a floating ip
- delete a certificate
- update image
- remove from resources
- get an action for an image
- get image action
- get firewall action
- infrastructure
- get load balancer type
- delete an image
- create load balancer
- list datacenters
- delete load balancer
- delete certificate
- list certificates
- get floating ip
- change floating ip protection
- update an image
- delete a firewall
- get floating ip action
- get a certificate
- get a floating ip
- list certificate actions
- get an action for a firewall
- get iso
- apply to resources
- assign a floating ip to a server
- list load balancer types
- get datacenter
- delete firewall
- list load balancers actions
- list floating ips
- create firewall
- assign floating ip
- list isos
- list actions for a load balancer
- list certificates actions
- apply firewall to resources
- update load balancer
- list data centers
- list floating ip actions
- update a certificate
- get an image
- list actions for a floating ip
- update certificate
- list actions for a firewall
- list firewalls
- get a firewall
- list load balancer actions
- delete a load balancer
- create a certificate
- list images
- get actions
- get an action for a certificate
- delete floating ip
- get an action
- change floating ip dns ptr
- get an iso
- list actions
- create a floating ip
- unassign floating ip
- list actions for an image
- get firewalls action
- list firewall actions
- cloud hosting
- update a load balancer
- list image actions
- retry issuance or renewal
- get a load balancer
- create a firewall
- get image
- update a floating ip
- remove firewall from resources
- unassign a floating ip
- get certificates action
- get a load balancer type
slug: hetzner-capability
source_filename: hetzner-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Hetzner Cloud API\n  description: '# Overview This is the official documentation for the Hetzner Cloud API. ## Introduction The Hetzner Cloud\n    API operates over HTTPS and uses JSON as its data format. The API is a RESTful API and utilizes HTTP methods and HTTP\n    status codes to specify requests and responses. As an alternative to working directly with our API you may also consider\n    to use: - Our CLI program [hcloud](https://github.com/hetznercloud/cli) - Our [library for Go](https://github.com/hetznercloud/hcloud-go)\n    - Our [library for Python](https://github.com/hetznercloud/hcloud-python) You can find even more libraries, tools an'\n  tags:\n  - Hetzner\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: hetzner\n    baseUri: https://api.hetzner.cloud/v1\n    description: Hetzner Cloud API HTTP API.\n    authentication:\n      type: bearer\n      token:\
  \ '{{HETZNER_TOKEN}}'\n    resources:\n    - name: actions\n      path: /actions\n      operations:\n      - name: get-actions\n        method: GET\n        description: Get multiple Actions\n        inputParameters:\n        - name: id\n          in: query\n          type: array\n          required: true\n          description: Filter the actions by ID. May be used multiple times. The response will only contain actions matching\n            the specified IDs.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: actions-id\n      path: /actions/{id}\n      operations:\n      - name: get-action\n        method: GET\n        description: Get an Action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: certificates\n      path: /certificates\n      operations:\n      - name: list-certificates\n        method: GET\n        description: List Certificates\n        inputParameters:\n        - name: sort\n          in: query\n          type: array\n          description: Sort resources by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: name\n          in: query\n          type: string\n          description: Filter resources by their name. The response will only contain the resources matching exactly the specified\n            name.\n        - name: label_selector\n          in: query\n          type: string\n          description: Filter resources by labels. The response will only contain resources matching the label selector. For\n            more information, see \"[Label Selector](#description/label\n        - name: type\n          in: query\n          type: array\n\
  \          description: Filter resources by type. May be used multiple times. The response will only contain the resources\n            with the specified type.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-certificate\n        method: POST\n        description: Create a Certificate\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates-actions\n      path: /certificates/actions\n      operations:\n  \
  \    - name: list-certificates-actions\n        method: GET\n        description: List Actions\n        inputParameters:\n        - name: id\n          in: query\n          type: array\n          description: Filter the actions by ID. May be used multiple times. The response will only contain actions matching\n            the specified IDs.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n\
  \          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates-actions-id\n      path: /certificates/actions/{id}\n      operations:\n      - name: get-certificates-action\n        method: GET\n        description: Get an Action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates-id\n      path: /certificates/{id}\n      operations:\n      - name: get-certificate\n        method: GET\n        description: Get a Certificate\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-certificate\n        method: PUT\n        description: Update a Certificate\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-certificate\n        method: DELETE\n        description: Delete a Certificate\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: certificates-id-actions\n      path: /certificates/{id}/actions\n      operations:\n      - name: list-certificate-actions\n        method: GET\n        description: List Actions for a Certificate\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"\
  [Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates-id-actions-retry\n      path: /certificates/{id}/actions/retry\n      operations:\n      - name: retry-certificate\n        method: POST\n        description: Retry Issuance or Renewal\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: certificates-id-actions-action-id\n      path: /certificates/{id}/actions/{action_id}\n      operations:\n\
  \      - name: get-certificate-action\n        method: GET\n        description: Get an Action for a Certificate\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Certificate.\n        - name: action_id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datacenters\n      path: /datacenters\n      operations:\n      - name: list-datacenters\n        method: GET\n        description: List Data Centers\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter resources by their name. The response will only contain the resources matching exactly the specified\n            name.\n        - name: sort\n          in: query\n    \
  \      type: array\n          description: Sort resources by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: datacenters-id\n      path: /datacenters/{id}\n      operations:\n      - name: get-datacenter\n        method: GET\n        description: Get a Data Center\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ ID of the Data Center.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls\n      path: /firewalls\n      operations:\n      - name: list-firewalls\n        method: GET\n        description: List Firewalls\n        inputParameters:\n        - name: sort\n          in: query\n          type: array\n          description: Sort resources by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: name\n          in: query\n          type: string\n          description: Filter resources by their name. The response will only contain the resources matching exactly the specified\n            name.\n        - name: label_selector\n          in: query\n          type: string\n          description: Filter resources by labels. The response will only contain resources matching the label selector. For\n            more information,\
  \ see \"[Label Selector](#description/label\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-firewall\n        method: POST\n        description: Create a Firewall\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-actions\n      path: /firewalls/actions\n      operations:\n      - name: list-firewalls-actions\n        method: GET\n        description: List Actions\n        inputParameters:\n        - name:\
  \ id\n          in: query\n          type: array\n          description: Filter the actions by ID. May be used multiple times. The response will only contain actions matching\n            the specified IDs.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information,\
  \ see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-actions-id\n      path: /firewalls/actions/{id}\n      operations:\n      - name: get-firewalls-action\n        method: GET\n        description: Get an Action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id\n      path: /firewalls/{id}\n      operations:\n      - name: get-firewall\n        method: GET\n        description: Get a Firewall\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-firewall\n        method: PUT\n        description: Update a Firewall\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-firewall\n        method: DELETE\n        description: Delete a Firewall\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id-actions\n      path: /firewalls/{id}/actions\n      operations:\n      - name: list-firewall-actions\n        method:\
  \ GET\n        description: List Actions for a Firewall\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more\
  \ information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id-actions-apply-to-resources\n      path: /firewalls/{id}/actions/apply_to_resources\n      operations:\n      - name: apply-firewall-to-resources\n        method: POST\n        description: Apply to Resources\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id-actions-remove-from-resources\n      path: /firewalls/{id}/actions/remove_from_resources\n      operations:\n      - name: remove-firewall-from-resources\n        method: POST\n        description: Remove from Resources\n        inputParameters:\n        - name:\
  \ id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id-actions-set-rules\n      path: /firewalls/{id}/actions/set_rules\n      operations:\n      - name: set-firewall-rules\n        method: POST\n        description: Set Rules\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: firewalls-id-actions-action-id\n      path: /firewalls/{id}/actions/{action_id}\n      operations:\n      - name: get-firewall-action\n        method: GET\n        description: Get an Action for a Firewall\n        inputParameters:\n        - name: id\n\
  \          in: path\n          type: integer\n          required: true\n          description: ID of the Firewall.\n        - name: action_id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips\n      path: /floating_ips\n      operations:\n      - name: list-floating-ips\n        method: GET\n        description: List Floating IPs\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          description: Filter resources by their name. The response will only contain the resources matching exactly the specified\n            name.\n        - name: label_selector\n          in: query\n          type: string\n          description: Filter resources by labels. The response will only contain resources matching the label selector. For\n   \
  \         more information, see \"[Label Selector](#description/label\n        - name: sort\n          in: query\n          type: array\n          description: Sort resources by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-floating-ip\n        method: POST\n        description: Create a Floating IP\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: floating-ips-actions\n      path: /floating_ips/actions\n      operations:\n      - name: list-floating-ips-actions\n        method: GET\n        description: List Actions\n        inputParameters:\n        - name: id\n          in: query\n          type: array\n          description: Filter the actions by ID. May be used multiple times. The response will only contain actions matching\n            the specified IDs.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n     \
  \     description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-actions-id\n      path: /floating_ips/actions/{id}\n      operations:\n      - name: get-floating-ips-action\n        method: GET\n        description: Get an Action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id\n      path: /floating_ips/{id}\n      operations:\n\
  \      - name: get-floating-ip\n        method: GET\n        description: Get a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-floating-ip\n        method: PUT\n        description: Update a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-floating-ip\n        method: DELETE\n        description: Delete a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n        \
  \  description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id-actions\n      path: /floating_ips/{id}/actions\n      operations:\n      - name: list-floating-ip-actions\n        method: GET\n        description: List Actions for a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n     \
  \   - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id-actions-assign\n      path: /floating_ips/{id}/actions/assign\n      operations:\n      - name: assign-floating-ip\n        method: POST\n        description: Assign a Floating IP to a Server\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: floating-ips-id-actions-change-dns-ptr\n      path: /floating_ips/{id}/actions/change_dns_ptr\n      operations:\n      - name: change-floating-ip-dns-ptr\n        method: POST\n        description: Change reverse DNS records for a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id-actions-change-protection\n      path: /floating_ips/{id}/actions/change_protection\n      operations:\n      - name: change-floating-ip-protection\n        method: POST\n        description: Change Floating IP Protection\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n     \
  \   outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id-actions-unassign\n      path: /floating_ips/{id}/actions/unassign\n      operations:\n      - name: unassign-floating-ip\n        method: POST\n        description: Unassign a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Floating IP.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: floating-ips-id-actions-action-id\n      path: /floating_ips/{id}/actions/{action_id}\n      operations:\n      - name: get-floating-ip-action\n        method: GET\n        description: Get an Action for a Floating IP\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ ID of the Floating IP.\n        - name: action_id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images\n      path: /images\n      operations:\n      - name: list-images\n        method: GET\n        description: List Images\n        inputParameters:\n        - name: sort\n          in: query\n          type: array\n          description: Sort resources by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: type\n          in: query\n          type: array\n          description: Filter resources by type. May be used multiple times. The response will only contain the resources\n            with the specified type.\n        - name: status\n          in: query\n          type: array\n          description: Filter\
  \ resources by status. May be used multiple times. The response will only contain the resources\n            with the specified status.\n        - name: bound_to\n          in: query\n          type: array\n          description: Filter Images by their linked Server ID. May be used multiple times. Only available for Images of type\n            `backup`.\n        - name: include_deprecated\n          in: query\n          type: boolean\n          description: Include deprecated Images.\n        - name: name\n          in: query\n          type: string\n          description: Filter resources by their name. The response will only contain the resources matching exactly the specified\n            name.\n        - name: label_selector\n          in: query\n          type: string\n          description: Filter resources by labels. The response will only contain resources matching the label selector. For\n            more information, see \"[Label Selector](#description/label\n        - name:\
  \ architecture\n          in: query\n          type: string\n          description: Filter resources by cpu architecture. The response will only contain the resources with the specified\n            cpu architecture.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\".\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-actions\n      path: /images/actions\n      operations:\n      - name: list-images-actions\n        method: GET\n        description: List Actions\n        inputParameters:\n        - name: id\n          in: query\n          type: array\n   \
  \       description: Filter the actions by ID. May be used multiple times. The response will only contain actions matching\n            the specified IDs.\n        - name: sort\n          in: query\n          type: array\n          description: Sort actions by field and direction. May be used multiple times. For more information, see \"[Sorting](#description/sorting)\".\n        - name: status\n          in: query\n          type: array\n          description: Filter the actions by status. May be used multiple times. The response will only contain actions matching\n            the specified statuses.\n        - name: page\n          in: query\n          type: integer\n          description: Page number to return. For more information, see \"[Pagination](#description/pagination)\".\n        - name: per_page\n          in: query\n          type: integer\n          description: Maximum number of entries returned per page. For more information, see \"[Pagination](#description/pagination)\"\
  .\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-actions-id\n      path: /images/actions/{id}\n      operations:\n      - name: get-images-action\n        method: GET\n        description: Get an Action\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Action.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-id\n      path: /images/{id}\n      operations:\n      - name: get-image\n        method: GET\n        description: Get an Image\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: update-image\n        method: PUT\n        description: Update an Image\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-image\n        method: DELETE\n        description: Delete an Image\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: ID of the Image.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: images-id-actions\n      path: /images/{id}/actions\n\n\n# --- truncated at 32 KB (103 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/hetzner/refs/heads/main/capabilities/hetzner-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/hetzner/refs/heads/main/capabilities/hetzner-capability.yaml
tags:
- Hetzner
- API
tools:
- description: Get multiple Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-action
- description: List Certificates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-certificates
- description: Create a Certificate
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-certificate
- description: List Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-certificates-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-certificates-action
- description: Get a Certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-certificate
- description: Update a Certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-certificate
- description: Delete a Certificate
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-certificate
- description: List Actions for a Certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-certificate-actions
- description: Retry Issuance or Renewal
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: retry-certificate
- description: Get an Action for a Certificate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-certificate-action
- description: List Data Centers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-datacenters
- description: Get a Data Center
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-datacenter
- description: List Firewalls
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-firewalls
- description: Create a Firewall
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-firewall
- description: List Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-firewalls-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-firewalls-action
- description: Get a Firewall
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-firewall
- description: Update a Firewall
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-firewall
- description: Delete a Firewall
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-firewall
- description: List Actions for a Firewall
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-firewall-actions
- description: Apply to Resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: apply-firewall-to-resources
- description: Remove from Resources
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: remove-firewall-from-resources
- description: Set Rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: set-firewall-rules
- description: Get an Action for a Firewall
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-firewall-action
- description: List Floating IPs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-floating-ips
- description: Create a Floating IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-floating-ip
- description: List Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-floating-ips-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-floating-ips-action
- description: Get a Floating IP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-floating-ip
- description: Update a Floating IP
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-floating-ip
- description: Delete a Floating IP
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-floating-ip
- description: List Actions for a Floating IP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-floating-ip-actions
- description: Assign a Floating IP to a Server
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assign-floating-ip
- description: Change reverse DNS records for a Floating IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: change-floating-ip-dns-ptr
- description: Change Floating IP Protection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: change-floating-ip-protection
- description: Unassign a Floating IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unassign-floating-ip
- description: Get an Action for a Floating IP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-floating-ip-action
- description: List Images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-images
- description: List Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-images-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-images-action
- description: Get an Image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-image
- description: Update an Image
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-image
- description: Delete an Image
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-image
- description: List Actions for an Image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-image-actions
- description: Change Image Protection
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: change-image-protection
- description: Get an Action for an Image
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-image-action
- description: List ISOs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-isos
- description: Get an ISO
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-iso
- description: List Load Balancer Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-load-balancer-types
- description: Get a Load Balancer Type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-load-balancer-type
- description: List Load Balancers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-load-balancers
- description: Create a Load Balancer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-load-balancer
- description: List Actions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-load-balancers-actions
- description: Get an Action
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-load-balancers-action
- description: Get a Load Balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-load-balancer
- description: Update a Load Balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-load-balancer
- description: Delete a Load Balancer
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-load-balancer
- description: List Actions for a Load Balancer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-load-balancer-actions
---
