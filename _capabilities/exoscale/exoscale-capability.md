---
categories: []
consumed_apis: []
description: Infrastructure automation API, allowing programmatic access to all Exoscale products and services.
layout: capability
name: Exoscale API
operations:
- description: Delete a Load Balancer Service
  method: DELETE
  name: delete-load-balancer-service
  path: /load-balancer/{id}/service/{service-id}
- description: Update a Load Balancer Service
  method: PUT
  name: update-load-balancer-service
  path: /load-balancer/{id}/service/{service-id}
- description: Retrieve Load Balancer Service details
  method: GET
  name: get-load-balancer-service
  path: /load-balancer/{id}/service/{service-id}
- description: '[BETA] Delete OpenSearch logs external integration endpoint'
  method: DELETE
  name: delete-dbaas-external-endpoint-opensearch
  path: /dbaas-external-endpoint-opensearch/{endpoint-id}
- description: '[BETA] Get OpenSearch Logs external integration endpoint settings'
  method: GET
  name: get-dbaas-external-endpoint-opensearch
  path: /dbaas-external-endpoint-opensearch/{endpoint-id}
- description: '[BETA] Update OpenSearch Logs external integration endpoint'
  method: PUT
  name: update-dbaas-external-endpoint-opensearch
  path: /dbaas-external-endpoint-opensearch/{endpoint-id}
- description: Get DBaaS OpenSearch ACL configuration
  method: GET
  name: get-dbaas-opensearch-acl-config
  path: /dbaas-opensearch/{name}/acl-config
- description: Create a DBaaS OpenSearch ACL configuration
  method: PUT
  name: update-dbaas-opensearch-acl-config
  path: /dbaas-opensearch/{name}/acl-config
- description: Scale an Instance Pool
  method: PUT
  name: scale-instance-pool
  path: /instance-pool/{id}:scale
- description: Create a Snapshot of a Compute instance
  method: POST
  name: create-snapshot
  path: /instance/{id}:create-snapshot
- description: Stop a DBaaS Valkey migration
  method: POST
  name: stop-dbaas-valkey-migration
  path: /dbaas-valkey/{name}/migration/stop
- description: Query the PTR DNS records for an elastic IP
  method: GET
  name: get-reverse-dns-elastic-ip
  path: /reverse-dns/elastic-ip/{id}
- description: Update/Create the PTR DNS record for an elastic IP
  method: POST
  name: update-reverse-dns-elastic-ip
  path: /reverse-dns/elastic-ip/{id}
- description: Delete the PTR DNS record for an elastic IP
  method: DELETE
  name: delete-reverse-dns-elastic-ip
  path: /reverse-dns/elastic-ip/{id}
- description: List Anti-affinity Groups
  method: GET
  name: list-anti-affinity-groups
  path: /anti-affinity-group
- description: Create an Anti-affinity Group
  method: POST
  name: create-anti-affinity-group
  path: /anti-affinity-group
- description: List AI API Keys
  method: GET
  name: list-ai-api-keys
  path: /ai/ai-api-key
- description: Create AI API Key
  method: POST
  name: create-ai-api-key
  path: /ai/ai-api-key
- description: Retrieve organization usage reports
  method: GET
  name: get-usage-report
  path: /usage-report
- description: List Events
  method: GET
  name: list-events
  path: /event
- description: Delete a Security Group rule
  method: DELETE
  name: delete-rule-from-security-group
  path: /security-group/{id}/rules/{rule-id}
- description: Initiate Grafana maintenance update
  method: PUT
  name: start-dbaas-grafana-maintenance
  path: /dbaas-grafana/{name}/maintenance/start
- description: '[BETA] Disable Key Rotation'
  method: POST
  name: disable-kms-key-rotation
  path: /kms-key/{id}/disable-key-rotation
- description: Check whether you can upgrade Postgres service to a newer version
  method: POST
  name: create-dbaas-pg-upgrade-check
  path: /dbaas-postgres/{service}/upgrade-check
- description: Reset the credentials of a DBaaS mysql user
  method: PUT
  name: reset-dbaas-mysql-user-password
  path: /dbaas-mysql/{service-name}/user/{username}/password/reset
- description: Get inference-engine Help
  method: GET
  name: get-inference-engine-help
  path: /ai/help/inference-engine-parameters
- description: Create a Load Balancer
  method: POST
  name: create-load-balancer
  path: /load-balancer
- description: List Load Balancers
  method: GET
  name: list-load-balancers
  path: /load-balancer
- description: Create a Security Group
  method: POST
  name: create-security-group
  path: /security-group
- description: List Security Groups.
  method: GET
  name: list-security-groups
  path: /security-group
- description: Create a DBaaS PostgreSQL connection pool
  method: POST
  name: create-dbaas-pg-connection-pool
  path: /dbaas-postgres/{service-name}/connection-pool
- description: Update a DBaaS MySQL service
  method: PUT
  name: update-dbaas-service-mysql
  path: /dbaas-mysql/{name}
- description: Get a DBaaS MySQL service
  method: GET
  name: get-dbaas-service-mysql
  path: /dbaas-mysql/{name}
- description: Create a DBaaS MySQL service
  method: POST
  name: create-dbaas-service-mysql
  path: /dbaas-mysql/{name}
- description: Delete a MySQL service
  method: DELETE
  name: delete-dbaas-service-mysql
  path: /dbaas-mysql/{name}
- description: '[BETA] Request generation of key/secret that allow caller to assume target role'
  method: POST
  name: assume-iam-role
  path: /iam-role/{target-role-id}/assume
- description: Attach a Compute instance to a Private Network
  method: PUT
  name: attach-instance-to-private-network
  path: /private-network/{id}:attach
- description: '[BETA] Get KMS Key'
  method: GET
  name: get-kms-key
  path: /kms-key/{id}
- description: Initiate Thanos maintenance update
  method: PUT
  name: start-dbaas-thanos-maintenance
  path: /dbaas-thanos/{name}/maintenance/start
- description: '[BETA] Delete ElasticSearch logs external integration endpoint'
  method: DELETE
  name: delete-dbaas-external-endpoint-elasticsearch
  path: /dbaas-external-endpoint-elasticsearch/{endpoint-id}
- description: '[BETA] Get ElasticSearch Logs external integration endpoint settings'
  method: GET
  name: get-dbaas-external-endpoint-elasticsearch
  path: /dbaas-external-endpoint-elasticsearch/{endpoint-id}
- description: '[BETA] Update ElasticSearch Logs external integration endpoint'
  method: PUT
  name: update-dbaas-external-endpoint-elasticsearch
  path: /dbaas-external-endpoint-elasticsearch/{endpoint-id}
- description: Create Model
  method: POST
  name: create-model
  path: /ai/model
- description: List Models
  method: GET
  name: list-models
  path: /ai/model
- description: Create a DBaaS MySQL user
  method: POST
  name: create-dbaas-mysql-user
  path: /dbaas-mysql/{service-name}/user
- description: DBaaS Service Types
  method: GET
  name: list-dbaas-service-types
  path: /dbaas-service-type
- description: Scale Deployment
  method: POST
  name: scale-deployment
  path: /ai/deployment/{id}/scale
- description: Retrieve Instance Type details
  method: GET
  name: get-instance-type
  path: /instance-type/{id}
- description: Reveal the password used during instance creation or the latest password reset.
  method: GET
  name: reveal-instance-password
  path: /instance/{id}:password
- description: Get the active template for a given kube version and variant (standard | nvidia)
  method: GET
  name: get-active-nodepool-template
  path: /sks-template/{kube-version}/{variant}
- description: Resize a Compute instance disk
  method: PUT
  name: resize-instance-disk
  path: /instance/{id}:resize-disk
- description: List DBaaS services
  method: GET
  name: list-dbaas-services
  path: /dbaas-service
- description: Create an Elastic IP
  method: POST
  name: create-elastic-ip
  path: /elastic-ip
- description: List Elastic IPs
  method: GET
  name: list-elastic-ips
  path: /elastic-ip
- description: List Zones
  method: GET
  name: list-zones
  path: /zone
- description: List Instance Pools
  method: GET
  name: list-instance-pools
  path: /instance-pool
- description: Create an Instance Pool
  method: POST
  name: create-instance-pool
  path: /instance-pool
- description: '[BETA] Create RSyslog external integration endpoint'
  method: POST
  name: create-dbaas-external-endpoint-rsyslog
  path: /dbaas-external-endpoint-rsyslog/{name}
- description: Generate a new Kubeconfig file for a SKS cluster
  method: POST
  name: generate-sks-cluster-kubeconfig
  path: /sks-cluster-kubeconfig/{id}
- description: List DNS domain records
  method: GET
  name: list-dns-domain-records
  path: /dns-domain/{domain-id}/record
personas: []
provider_name: Exoscale
provider_slug: exoscale
search_terms:
- list events
- get reverse dns elastic ip
- attach a compute instance to a private network
- create elastic ip
- generate sks cluster kubeconfig
- create a load balancer
- query the ptr dns records for an elastic ip
- list load balancers
- get the active template for a given kube version and variant (standard | nvidia)
- reset the credentials of a dbaas mysql user
- create a security group
- create security group
- list elastic ips
- delete reverse dns elastic ip
- create a dbaas opensearch acl configuration
- cloud
- create dbaas mysql user
- create snapshot
- create dbaas pg upgrade check
- create anti affinity group
- list ai api keys
- retrieve instance type details
- api
- delete load balancer service
- initiate grafana maintenance update
- list models
- scale an instance pool
- get dbaas external endpoint opensearch
- scale deployment
- list dbaas services
- get dbaas service mysql
- compute
- create a dbaas mysql service
- storage
- create a dbaas postgresql connection pool
- infrastructure
- retrieve organization usage reports
- create load balancer
- get active nodepool template
- delete a security group rule
- delete a load balancer service
- create a dbaas mysql user
- update a dbaas mysql service
- kubernetes
- get instance type
- create an elastic ip
- update dbaas opensearch acl config
- delete dbaas external endpoint opensearch
- '[beta] request generation of key/secret that allow caller to assume target role'
- update load balancer service
- '[beta] create rsyslog external integration endpoint'
- create dbaas external endpoint rsyslog
- check whether you can upgrade postgres service to a newer version
- reveal the password used during instance creation or the latest password reset.
- delete the ptr dns record for an elastic ip
- delete rule from security group
- get a dbaas mysql service
- delete dbaas external endpoint elasticsearch
- get inference-engine help
- reveal instance password
- create instance pool
- '[beta] update opensearch logs external integration endpoint'
- list anti-affinity groups
- dbaas
- resize a compute instance disk
- stop a dbaas valkey migration
- disable kms key rotation
- assume iam role
- create model
- start dbaas thanos maintenance
- '[beta] get elasticsearch logs external integration endpoint settings'
- list dns domain records
- create a snapshot of a compute instance
- get usage report
- dbaas service types
- get kms key
- retrieve load balancer service details
- '[beta] update elasticsearch logs external integration endpoint'
- create an anti-affinity group
- list anti affinity groups
- get load balancer service
- reset dbaas mysql user password
- list zones
- create dbaas pg connection pool
- '[beta] get kms key'
- exoscale
- start dbaas grafana maintenance
- get dbaas opensearch acl configuration
- europe
- update/create the ptr dns record for an elastic ip
- update dbaas service mysql
- create dbaas service mysql
- delete dbaas service mysql
- list dbaas service types
- update dbaas external endpoint opensearch
- create ai api key
- get dbaas opensearch acl config
- update reverse dns elastic ip
- get inference engine help
- '[beta] delete elasticsearch logs external integration endpoint'
- get dbaas external endpoint elasticsearch
- scale instance pool
- attach instance to private network
- initiate thanos maintenance update
- update a load balancer service
- list security groups
- delete a mysql service
- '[beta] get opensearch logs external integration endpoint settings'
- generate a new kubeconfig file for a sks cluster
- create an instance pool
- '[beta] disable key rotation'
- list instance pools
- update dbaas external endpoint elasticsearch
- '[beta] delete opensearch logs external integration endpoint'
- list security groups.
- stop dbaas valkey migration
- resize instance disk
slug: exoscale-capability
source_filename: exoscale-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Exoscale API\n  description: Infrastructure automation API, allowing programmatic access to all Exoscale products and services.\n  tags:\n  - Exoscale\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: exoscale\n    baseUri: https://api-ch-gva-2.exoscale.com/v2\n    description: Exoscale API HTTP API.\n    resources:\n    - name: load-balancer-id-service-service-id\n      path: /load-balancer/{id}/service/{service-id}\n      operations:\n      - name: delete-load-balancer-service\n        method: DELETE\n        description: Delete a Load Balancer Service\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: service-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: update-load-balancer-service\n        method: PUT\n        description: Update a Load Balancer Service\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: service-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-load-balancer-service\n        method: GET\n        description: Retrieve Load Balancer Service details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        - name: service-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-external-endpoint-opensearch-endpoint-id\n\
  \      path: /dbaas-external-endpoint-opensearch/{endpoint-id}\n      operations:\n      - name: delete-dbaas-external-endpoint-opensearch\n        method: DELETE\n        description: '[BETA] Delete OpenSearch logs external integration endpoint'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dbaas-external-endpoint-opensearch\n        method: GET\n        description: '[BETA] Get OpenSearch Logs external integration endpoint settings'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dbaas-external-endpoint-opensearch\n        method: PUT\n    \
  \    description: '[BETA] Update OpenSearch Logs external integration endpoint'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-opensearch-name-acl-config\n      path: /dbaas-opensearch/{name}/acl-config\n      operations:\n      - name: get-dbaas-opensearch-acl-config\n        method: GET\n        description: Get DBaaS OpenSearch ACL configuration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dbaas-opensearch-acl-config\n        method: PUT\n        description: Create a DBaaS OpenSearch ACL configuration\n        inputParameters:\n        - name:\
  \ name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-pool-id-scale\n      path: /instance-pool/{id}:scale\n      operations:\n      - name: scale-instance-pool\n        method: PUT\n        description: Scale an Instance Pool\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-id-create-snapshot\n      path: /instance/{id}:create-snapshot\n      operations:\n      - name: create-snapshot\n        method: POST\n        description: Create a Snapshot of a Compute instance\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-valkey-name-migration-stop\n      path: /dbaas-valkey/{name}/migration/stop\n      operations:\n      - name: stop-dbaas-valkey-migration\n        method: POST\n        description: Stop a DBaaS Valkey migration\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: reverse-dns-elastic-ip-id\n      path: /reverse-dns/elastic-ip/{id}\n      operations:\n      - name: get-reverse-dns-elastic-ip\n        method: GET\n        description: Query the PTR DNS records for an elastic IP\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: update-reverse-dns-elastic-ip\n        method: POST\n        description: Update/Create the PTR DNS record for an elastic IP\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-reverse-dns-elastic-ip\n        method: DELETE\n        description: Delete the PTR DNS record for an elastic IP\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anti-affinity-group\n      path: /anti-affinity-group\n      operations:\n      - name: list-anti-affinity-groups\n        method: GET\n        description: List Anti-affinity Groups\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-anti-affinity-group\n        method: POST\n        description: Create an Anti-affinity Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-ai-api-key\n      path: /ai/ai-api-key\n      operations:\n      - name: list-ai-api-keys\n        method: GET\n        description: List AI API Keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-ai-api-key\n        method: POST\n        description: Create AI API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usage-report\n      path: /usage-report\n      operations:\n      - name: get-usage-report\n        method:\
  \ GET\n        description: Retrieve organization usage reports\n        inputParameters:\n        - name: period\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: event\n      path: /event\n      operations:\n      - name: list-events\n        method: GET\n        description: List Events\n        inputParameters:\n        - name: from\n          in: query\n          type: string\n        - name: to\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-group-id-rules-rule-id\n      path: /security-group/{id}/rules/{rule-id}\n      operations:\n      - name: delete-rule-from-security-group\n        method: DELETE\n        description: Delete a Security Group rule\n        inputParameters:\n        - name: id\n     \
  \     in: path\n          type: string\n          required: true\n        - name: rule-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-grafana-name-maintenance-start\n      path: /dbaas-grafana/{name}/maintenance/start\n      operations:\n      - name: start-dbaas-grafana-maintenance\n        method: PUT\n        description: Initiate Grafana maintenance update\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kms-key-id-disable-key-rotation\n      path: /kms-key/{id}/disable-key-rotation\n      operations:\n      - name: disable-kms-key-rotation\n        method: POST\n        description: '[BETA] Disable Key Rotation'\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-postgres-service-upgrade-check\n      path: /dbaas-postgres/{service}/upgrade-check\n      operations:\n      - name: create-dbaas-pg-upgrade-check\n        method: POST\n        description: Check whether you can upgrade Postgres service to a newer version\n        inputParameters:\n        - name: service\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-mysql-service-name-user-username-password-\n      path: /dbaas-mysql/{service-name}/user/{username}/password/reset\n      operations:\n      - name: reset-dbaas-mysql-user-password\n        method: PUT\n        description:\
  \ Reset the credentials of a DBaaS mysql user\n        inputParameters:\n        - name: service-name\n          in: path\n          type: string\n          required: true\n        - name: username\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-help-inference-engine-parameters\n      path: /ai/help/inference-engine-parameters\n      operations:\n      - name: get-inference-engine-help\n        method: GET\n        description: Get inference-engine Help\n        inputParameters:\n        - name: version\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: load-balancer\n      path: /load-balancer\n      operations:\n      - name: create-load-balancer\n        method: POST\n        description:\
  \ Create a Load Balancer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-load-balancers\n        method: GET\n        description: List Load Balancers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-group\n      path: /security-group\n      operations:\n      - name: create-security-group\n        method: POST\n        description: Create a Security Group\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-security-groups\n        method: GET\n        description: List Security Groups.\n        inputParameters:\n        - name: visibility\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: dbaas-postgres-service-name-connection-pool\n      path: /dbaas-postgres/{service-name}/connection-pool\n      operations:\n      - name: create-dbaas-pg-connection-pool\n        method: POST\n        description: Create a DBaaS PostgreSQL connection pool\n        inputParameters:\n        - name: service-name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-mysql-name\n      path: /dbaas-mysql/{name}\n      operations:\n      - name: update-dbaas-service-mysql\n        method: PUT\n        description: Update a DBaaS MySQL service\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dbaas-service-mysql\n\
  \        method: GET\n        description: Get a DBaaS MySQL service\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-dbaas-service-mysql\n        method: POST\n        description: Create a DBaaS MySQL service\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-dbaas-service-mysql\n        method: DELETE\n        description: Delete a MySQL service\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: iam-role-target-role-id-assume\n      path: /iam-role/{target-role-id}/assume\n      operations:\n      - name: assume-iam-role\n        method: POST\n        description: '[BETA] Request generation of key/secret that allow caller to assume target role'\n        inputParameters:\n        - name: target-role-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: private-network-id-attach\n      path: /private-network/{id}:attach\n      operations:\n      - name: attach-instance-to-private-network\n        method: PUT\n        description: Attach a Compute instance to a Private Network\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: kms-key-id\n      path: /kms-key/{id}\n      operations:\n      - name: get-kms-key\n        method: GET\n        description: '[BETA] Get KMS Key'\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-thanos-name-maintenance-start\n      path: /dbaas-thanos/{name}/maintenance/start\n      operations:\n      - name: start-dbaas-thanos-maintenance\n        method: PUT\n        description: Initiate Thanos maintenance update\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-external-endpoint-elasticsearch-endpoint-i\n      path:\
  \ /dbaas-external-endpoint-elasticsearch/{endpoint-id}\n      operations:\n      - name: delete-dbaas-external-endpoint-elasticsearch\n        method: DELETE\n        description: '[BETA] Delete ElasticSearch logs external integration endpoint'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-dbaas-external-endpoint-elasticsearch\n        method: GET\n        description: '[BETA] Get ElasticSearch Logs external integration endpoint settings'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-dbaas-external-endpoint-elasticsearch\n        method: PUT\n\
  \        description: '[BETA] Update ElasticSearch Logs external integration endpoint'\n        inputParameters:\n        - name: endpoint-id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-model\n      path: /ai/model\n      operations:\n      - name: create-model\n        method: POST\n        description: Create Model\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-models\n        method: GET\n        description: List Models\n        inputParameters:\n        - name: visibility\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-mysql-service-name-user\n      path: /dbaas-mysql/{service-name}/user\n\
  \      operations:\n      - name: create-dbaas-mysql-user\n        method: POST\n        description: Create a DBaaS MySQL user\n        inputParameters:\n        - name: service-name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-service-type\n      path: /dbaas-service-type\n      operations:\n      - name: list-dbaas-service-types\n        method: GET\n        description: DBaaS Service Types\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ai-deployment-id-scale\n      path: /ai/deployment/{id}/scale\n      operations:\n      - name: scale-deployment\n        method: POST\n        description: Scale Deployment\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-type-id\n      path: /instance-type/{id}\n      operations:\n      - name: get-instance-type\n        method: GET\n        description: Retrieve Instance Type details\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-id-password\n      path: /instance/{id}:password\n      operations:\n      - name: reveal-instance-password\n        method: GET\n        description: Reveal the password used during instance creation or the latest password reset.\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: sks-template-kube-version-variant\n      path: /sks-template/{kube-version}/{variant}\n      operations:\n      - name: get-active-nodepool-template\n        method: GET\n        description: Get the active template for a given kube version and variant (standard | nvidia)\n        inputParameters:\n        - name: kube-version\n          in: path\n          type: string\n          required: true\n        - name: variant\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-id-resize-disk\n      path: /instance/{id}:resize-disk\n      operations:\n      - name: resize-instance-disk\n        method: PUT\n        description: Resize a Compute instance disk\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required:\
  \ true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-service\n      path: /dbaas-service\n      operations:\n      - name: list-dbaas-services\n        method: GET\n        description: List DBaaS services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: elastic-ip\n      path: /elastic-ip\n      operations:\n      - name: create-elastic-ip\n        method: POST\n        description: Create an Elastic IP\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: list-elastic-ips\n        method: GET\n        description: List Elastic IPs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: zone\n      path: /zone\n      operations:\n\
  \      - name: list-zones\n        method: GET\n        description: List Zones\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: instance-pool\n      path: /instance-pool\n      operations:\n      - name: list-instance-pools\n        method: GET\n        description: List Instance Pools\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-instance-pool\n        method: POST\n        description: Create an Instance Pool\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dbaas-external-endpoint-rsyslog-name\n      path: /dbaas-external-endpoint-rsyslog/{name}\n      operations:\n      - name: create-dbaas-external-endpoint-rsyslog\n        method: POST\n        description: '[BETA] Create RSyslog external integration\
  \ endpoint'\n        inputParameters:\n        - name: name\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sks-cluster-kubeconfig-id\n      path: /sks-cluster-kubeconfig/{id}\n      operations:\n      - name: generate-sks-cluster-kubeconfig\n        method: POST\n        description: Generate a new Kubeconfig file for a SKS cluster\n        inputParameters:\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dns-domain-domain-id-record\n      path: /dns-domain/{domain-id}/record\n      operations:\n      - name: list-dns-domain-records\n        method: GET\n        description: List DNS domain records\n        inputParameters:\n        - name: domain-id\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: exoscale-rest\n    description: REST adapter for Exoscale API.\n    resources:\n    - path: /load-balancer/{id}/service/{service-id}\n      name: delete-load-balancer-service\n      operations:\n      - method: DELETE\n        name: delete-load-balancer-service\n        description: Delete a Load Balancer Service\n        call: exoscale.delete-load-balancer-service\n        with:\n          id: rest.id\n          service-id: rest.service-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /load-balancer/{id}/service/{service-id}\n      name: update-load-balancer-service\n      operations:\n      - method: PUT\n        name: update-load-balancer-service\n        description: Update a Load Balancer\
  \ Service\n        call: exoscale.update-load-balancer-service\n        with:\n          id: rest.id\n          service-id: rest.service-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /load-balancer/{id}/service/{service-id}\n      name: get-load-balancer-service\n      operations:\n      - method: GET\n        name: get-load-balancer-service\n        description: Retrieve Load Balancer Service details\n        call: exoscale.get-load-balancer-service\n        with:\n          id: rest.id\n          service-id: rest.service-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-external-endpoint-opensearch/{endpoint-id}\n      name: delete-dbaas-external-endpoint-opensearch\n      operations:\n      - method: DELETE\n        name: delete-dbaas-external-endpoint-opensearch\n        description: '[BETA] Delete OpenSearch logs external integration endpoint'\n        call: exoscale.delete-dbaas-external-endpoint-opensearch\n\
  \        with:\n          endpoint-id: rest.endpoint-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-external-endpoint-opensearch/{endpoint-id}\n      name: get-dbaas-external-endpoint-opensearch\n      operations:\n      - method: GET\n        name: get-dbaas-external-endpoint-opensearch\n        description: '[BETA] Get OpenSearch Logs external integration endpoint settings'\n        call: exoscale.get-dbaas-external-endpoint-opensearch\n        with:\n          endpoint-id: rest.endpoint-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-external-endpoint-opensearch/{endpoint-id}\n      name: update-dbaas-external-endpoint-opensearch\n      operations:\n      - method: PUT\n        name: update-dbaas-external-endpoint-opensearch\n        description: '[BETA] Update OpenSearch Logs external integration endpoint'\n        call: exoscale.update-dbaas-external-endpoint-opensearch\n        with:\n\
  \          endpoint-id: rest.endpoint-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-opensearch/{name}/acl-config\n      name: get-dbaas-opensearch-acl-config\n      operations:\n      - method: GET\n        name: get-dbaas-opensearch-acl-config\n        description: Get DBaaS OpenSearch ACL configuration\n        call: exoscale.get-dbaas-opensearch-acl-config\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-opensearch/{name}/acl-config\n      name: update-dbaas-opensearch-acl-config\n      operations:\n      - method: PUT\n        name: update-dbaas-opensearch-acl-config\n        description: Create a DBaaS OpenSearch ACL configuration\n        call: exoscale.update-dbaas-opensearch-acl-config\n        with:\n          name: rest.name\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instance-pool/{id}:scale\n  \
  \    name: scale-instance-pool\n      operations:\n      - method: PUT\n        name: scale-instance-pool\n        description: Scale an Instance Pool\n        call: exoscale.scale-instance-pool\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /instance/{id}:create-snapshot\n      name: create-snapshot\n      operations:\n      - method: POST\n        name: create-snapshot\n        description: Create a Snapshot of a Compute instance\n        call: exoscale.create-snapshot\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-valkey/{name}/migration/stop\n      name: stop-dbaas-valkey-migration\n      operations:\n      - method: POST\n        name: stop-dbaas-valkey-migration\n        description: Stop a DBaaS Valkey migration\n        call: exoscale.stop-dbaas-valkey-migration\n        with:\n          name: rest.name\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /reverse-dns/elastic-ip/{id}\n      name: get-reverse-dns-elastic-ip\n      operations:\n      - method: GET\n        name: get-reverse-dns-elastic-ip\n        description: Query the PTR DNS records for an elastic IP\n        call: exoscale.get-reverse-dns-elastic-ip\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reverse-dns/elastic-ip/{id}\n      name: update-reverse-dns-elastic-ip\n      operations:\n      - method: POST\n        name: update-reverse-dns-elastic-ip\n        description: Update/Create the PTR DNS record for an elastic IP\n        call: exoscale.update-reverse-dns-elastic-ip\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /reverse-dns/elastic-ip/{id}\n      name: delete-reverse-dns-elastic-ip\n      operations:\n      - method: DELETE\n        name: delete-reverse-dns-elastic-ip\n\
  \        description: Delete the PTR DNS record for an elastic IP\n        call: exoscale.delete-reverse-dns-elastic-ip\n        with:\n          id: rest.id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /anti-affinity-group\n      name: list-anti-affinity-groups\n      operations:\n      - method: GET\n        name: list-anti-affinity-groups\n        description: List Anti-affinity Groups\n        call: exoscale.list-anti-affinity-groups\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /anti-affinity-group\n      name: create-anti-affinity-group\n      operations:\n      - method: POST\n        name: create-anti-affinity-group\n        description: Create an Anti-affinity Group\n        call: exoscale.create-anti-affinity-group\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ai/ai-api-key\n      name: list-ai-api-keys\n      operations:\n      - method: GET\n        name:\
  \ list-ai-api-keys\n        description: List AI API Keys\n        call: exoscale.list-ai-api-keys\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ai/ai-api-key\n      name: create-ai-api-key\n      operations:\n      - method: POST\n        name: create-ai-api-key\n        description: Create AI API Key\n        call: exoscale.create-ai-api-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /usage-report\n      name: get-usage-report\n      operations:\n      - method: GET\n        name: get-usage-report\n        description: Retrieve organization usage reports\n        call: exoscale.get-usage-report\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /event\n      name: list-events\n      operations:\n      - method: GET\n        name: list-events\n        description: List Events\n        call: exoscale.list-events\n        outputParameters:\n        - type: object\n \
  \         mapping: $.\n    - path: /security-group/{id}/rules/{rule-id}\n      name: delete-rule-from-security-group\n      operations:\n      - method: DELETE\n        name: delete-rule-from-security-group\n        description: Delete a Security Group rule\n        call: exoscale.delete-rule-from-security-group\n        with:\n          id: rest.id\n          rule-id: rest.rule-id\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /dbaas-grafana/{name}/maintenance/start\n      name: start-dbaas-grafana-maintenance\n      operations:\n      - method: PUT\n        name: start-dbaas-grafana-maintenance\n        description: Initiate Grafana maintenance update\n        call: exoscale.start-dbaas-grafana-maintenance\n        with:\n          name: res\n\n# --- truncated at 32 KB (70 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/exoscale/refs/heads/main/capabilities/exoscale-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/exoscale/refs/heads/main/capabilities/exoscale-capability.yaml
tags:
- Exoscale
- API
tools:
- description: Delete a Load Balancer Service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-load-balancer-service
- description: Update a Load Balancer Service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-load-balancer-service
- description: Retrieve Load Balancer Service details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-load-balancer-service
- description: '[BETA] Delete OpenSearch logs external integration endpoint'
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-dbaas-external-endpoint-opensearch
- description: '[BETA] Get OpenSearch Logs external integration endpoint settings'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dbaas-external-endpoint-opensearch
- description: '[BETA] Update OpenSearch Logs external integration endpoint'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-dbaas-external-endpoint-opensearch
- description: Get DBaaS OpenSearch ACL configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dbaas-opensearch-acl-config
- description: Create a DBaaS OpenSearch ACL configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-dbaas-opensearch-acl-config
- description: Scale an Instance Pool
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: scale-instance-pool
- description: Create a Snapshot of a Compute instance
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-snapshot
- description: Stop a DBaaS Valkey migration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: stop-dbaas-valkey-migration
- description: Query the PTR DNS records for an elastic IP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-reverse-dns-elastic-ip
- description: Update/Create the PTR DNS record for an elastic IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: update-reverse-dns-elastic-ip
- description: Delete the PTR DNS record for an elastic IP
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-reverse-dns-elastic-ip
- description: List Anti-affinity Groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-anti-affinity-groups
- description: Create an Anti-affinity Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-anti-affinity-group
- description: List AI API Keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-ai-api-keys
- description: Create AI API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-ai-api-key
- description: Retrieve organization usage reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-usage-report
- description: List Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-events
- description: Delete a Security Group rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-rule-from-security-group
- description: Initiate Grafana maintenance update
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-dbaas-grafana-maintenance
- description: '[BETA] Disable Key Rotation'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: disable-kms-key-rotation
- description: Check whether you can upgrade Postgres service to a newer version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dbaas-pg-upgrade-check
- description: Reset the credentials of a DBaaS mysql user
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: reset-dbaas-mysql-user-password
- description: Get inference-engine Help
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-inference-engine-help
- description: Create a Load Balancer
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-load-balancer
- description: List Load Balancers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-load-balancers
- description: Create a Security Group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-security-group
- description: List Security Groups.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-security-groups
- description: Create a DBaaS PostgreSQL connection pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dbaas-pg-connection-pool
- description: Update a DBaaS MySQL service
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-dbaas-service-mysql
- description: Get a DBaaS MySQL service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dbaas-service-mysql
- description: Create a DBaaS MySQL service
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dbaas-service-mysql
- description: Delete a MySQL service
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-dbaas-service-mysql
- description: '[BETA] Request generation of key/secret that allow caller to assume target role'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: assume-iam-role
- description: Attach a Compute instance to a Private Network
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: attach-instance-to-private-network
- description: '[BETA] Get KMS Key'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-kms-key
- description: Initiate Thanos maintenance update
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: start-dbaas-thanos-maintenance
- description: '[BETA] Delete ElasticSearch logs external integration endpoint'
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-dbaas-external-endpoint-elasticsearch
- description: '[BETA] Get ElasticSearch Logs external integration endpoint settings'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-dbaas-external-endpoint-elasticsearch
- description: '[BETA] Update ElasticSearch Logs external integration endpoint'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-dbaas-external-endpoint-elasticsearch
- description: Create Model
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-model
- description: List Models
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-models
- description: Create a DBaaS MySQL user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dbaas-mysql-user
- description: DBaaS Service Types
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-dbaas-service-types
- description: Scale Deployment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scale-deployment
- description: Retrieve Instance Type details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-instance-type
- description: Reveal the password used during instance creation or the latest password reset.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: reveal-instance-password
- description: Get the active template for a given kube version and variant (standard | nvidia)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-active-nodepool-template
- description: Resize a Compute instance disk
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: resize-instance-disk
- description: List DBaaS services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-dbaas-services
- description: Create an Elastic IP
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-elastic-ip
- description: List Elastic IPs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-elastic-ips
- description: List Zones
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-zones
- description: List Instance Pools
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-instance-pools
- description: Create an Instance Pool
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-instance-pool
- description: '[BETA] Create RSyslog external integration endpoint'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: create-dbaas-external-endpoint-rsyslog
- description: Generate a new Kubeconfig file for a SKS cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generate-sks-cluster-kubeconfig
- description: List DNS domain records
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: list-dns-domain-records
---
