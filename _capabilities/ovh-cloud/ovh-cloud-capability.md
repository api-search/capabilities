---
categories: []
consumed_apis: []
description: Specification for OVHcloud API
layout: capability
name: OVH Cloud OVHcloud API specification
operations:
- description: OVH Cloud Get all cloud pending orders
  method: GET
  name: get-cloud-order
  path: /cloud/order
- description: OVH Cloud Get product availability
  method: GET
  name: get-cloud-order-rule-availability
  path: /cloud/order/rule/availability
- description: OVH Cloud Get instance categories
  method: GET
  name: get-cloud-order-rule-instancecategory
  path: /cloud/order/rule/instanceCategory
- description: OVH Cloud List available services
  method: GET
  name: get-cloud-project
  path: /cloud/project
- description: OVH Cloud Get this object properties
  method: GET
  name: get-cloud-project-servicename
  path: /cloud/project/{serviceName}
- description: OVH Cloud Alter this object properties
  method: PUT
  name: put-cloud-project-servicename
  path: /cloud/project/{serviceName}
- description: OVH Cloud Activate monthly billing on multiple instances
  method: POST
  name: post-cloud-project-servicename-activatemonthlybi
  path: /cloud/project/{serviceName}/activateMonthlyBilling
- description: OVH Cloud List container registry capabilities per region
  method: GET
  name: get-cloud-project-servicename-capabilities-conta
  path: /cloud/project/{serviceName}/capabilities/containerRegistry
- description: OVH Cloud List of admissionPlugins managed by MKS product that can be enabled or disabled.
  method: GET
  name: get-cloud-project-servicename-capabilities-kube-
  path: /cloud/project/{serviceName}/capabilities/kube/admissionplugins
- description: OVH Cloud List Kubernetes available flavors for a region
  method: GET
  name: get-cloud-project-servicename-capabilities-kube-
  path: /cloud/project/{serviceName}/capabilities/kube/flavors
- description: OVH Cloud List available log kinds
  method: GET
  name: get-cloud-project-servicename-capabilities-kube-
  path: /cloud/project/{serviceName}/capabilities/kube/log/kind
- description: OVH Cloud Get a log kind
  method: GET
  name: get-cloud-project-servicename-capabilities-kube-
  path: /cloud/project/{serviceName}/capabilities/kube/log/kind/{name}
- description: OVH Cloud List Kubernetes regions where cluster creation is possible.
  method: GET
  name: get-cloud-project-servicename-capabilities-kube-
  path: /cloud/project/{serviceName}/capabilities/kube/regions
- description: OVH Cloud List all available regions
  method: GET
  name: get-cloud-project-servicename-capabilities-loadb
  path: /cloud/project/{serviceName}/capabilities/loadbalancer/region
- description: OVH Cloud Get specific information of a region
  method: GET
  name: get-cloud-project-servicename-capabilities-loadb
  path: /cloud/project/{serviceName}/capabilities/loadbalancer/region/{regionName}
- description: OVH Cloud List product availability
  method: GET
  name: get-cloud-project-servicename-capabilities-produ
  path: /cloud/project/{serviceName}/capabilities/productAvailability
- description: OVH Cloud Confirm service termination
  method: POST
  name: post-cloud-project-servicename-confirmterminatio
  path: /cloud/project/{serviceName}/confirmTermination
- description: OVH Cloud List registries of the project
  method: GET
  name: get-cloud-project-servicename-containerregistry
  path: /cloud/project/{serviceName}/containerRegistry
- description: OVH Cloud Create a new registry
  method: POST
  name: post-cloud-project-servicename-containerregistry
  path: /cloud/project/{serviceName}/containerRegistry
- description: OVH Cloud Delete a registry
  method: DELETE
  name: delete-cloud-project-servicename-containerregist
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}
- description: OVH Cloud Get the registry information
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}
- description: OVH Cloud Update the registry
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}
- description: OVH Cloud Get available plans for the current registry.
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/capabilities/plan
- description: OVH Cloud List your IP restrictions applied on Harbor UI and API
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/management
- description: OVH Cloud Replace IP restrictions applied on Harbor UI and API
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/management
- description: OVH Cloud List your IP restrictions applied on artifact manager component
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/registry
- description: OVH Cloud Replace IP restrictions applied on artifact manager component (Docker, Helm, etc...)
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/registry
- description: OVH Cloud Delete the registry's OIDC Configuration
  method: DELETE
  name: delete-cloud-project-servicename-containerregist
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/openIdConnect
- description: OVH Cloud Get the registry's OIDC configuration
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/openIdConnect
- description: OVH Cloud Add or replace the registry's OIDC configuration
  method: POST
  name: post-cloud-project-servicename-containerregistry
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/openIdConnect
- description: OVH Cloud Edit the registry's OIDC configuration
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/openIdConnect
- description: OVH Cloud Show the actual plan of the registry.
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/plan
- description: OVH Cloud Update the plan of a registry.
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/plan
- description: OVH Cloud List registry user
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users
- description: OVH Cloud Create a new registry user
  method: POST
  name: post-cloud-project-servicename-containerregistry
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users
- description: OVH Cloud Delete a registry user
  method: DELETE
  name: delete-cloud-project-servicename-containerregist
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users/{userID}
- description: OVH Cloud Get registry user
  method: GET
  name: get-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users/{userID}
- description: OVH Cloud Set the user as Admin
  method: PUT
  name: put-cloud-project-servicename-containerregistry-
  path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users/{userID}/setAsAdmin
- description: OVH Cloud Get database engines availability
  method: GET
  name: get-cloud-project-servicename-database-availabil
  path: /cloud/project/{serviceName}/database/availability
- description: OVH Cloud Get database engines capabilities
  method: GET
  name: get-cloud-project-servicename-database-capabilit
  path: /cloud/project/{serviceName}/database/capabilities
- description: OVH Cloud List all the cassandra clusters of the project
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra
- description: OVH Cloud Create a new cassandra cluster
  method: POST
  name: post-cloud-project-servicename-database-cassandr
  path: /cloud/project/{serviceName}/database/cassandra
- description: OVH Cloud Delete a cassandra cluster
  method: DELETE
  name: delete-cloud-project-servicename-database-cassan
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}
- description: OVH Cloud Get cassandra cluster properties
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}
- description: OVH Cloud Update an existing cassandra cluster
  method: PUT
  name: put-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}
- description: OVH Cloud Get cassandra advanced configuration
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/advancedConfiguration
- description: OVH Cloud Update cassandra advanced configuration
  method: PUT
  name: put-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/advancedConfiguration
- description: OVH Cloud List backups of the cassandra
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/backup
- description: OVH Cloud Get cassandra backups
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/backup/{backupId}
- description: OVH Cloud Get cassandra advanced configuration fields
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/capabilities/advancedConfiguration
- description: OVH Cloud Get integration capabilities related to the cassandra service
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/capabilities/integration
- description: OVH Cloud Retrieve the certificates of the cassandra cluster
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/certificates
- description: OVH Cloud List integrations
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/integration
- description: OVH Cloud Create a new integration
  method: POST
  name: post-cloud-project-servicename-database-cassandr
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/integration
- description: OVH Cloud Delete an integration
  method: DELETE
  name: delete-cloud-project-servicename-database-cassan
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/integration/{integrationId}
- description: OVH Cloud Get an integration
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/integration/{integrationId}
- description: OVH Cloud List cassandra ip restrictions
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/ipRestriction
- description: OVH Cloud Add ip restrictions to the cassandra
  method: POST
  name: post-cloud-project-servicename-database-cassandr
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/ipRestriction
- description: OVH Cloud Deletes the given IP from the restricted IPs of the cassandra
  method: DELETE
  name: delete-cloud-project-servicename-database-cassan
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/ipRestriction/{ipBlock}
- description: OVH Cloud Get cassandra ip restrictions
  method: GET
  name: get-cloud-project-servicename-database-cassandra
  path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/ipRestriction/{ipBlock}
personas: []
provider_name: OVH Cloud
provider_slug: ovh-cloud
search_terms:
- api
- put cloud project servicename database cassandra
- ovh cloud show the actual plan of the registry.
- ovh cloud delete a registry user
- ovh cloud get available plans for the current registry.
- ovh cloud activate monthly billing on multiple instances
- hosting
- get cloud project servicename
- ovh cloud alter this object properties
- get cloud project servicename database cassandra
- ovh cloud delete an integration
- get cloud order
- ovh cloud get an integration
- get cloud project servicename capabilities kube
- ovh cloud get the registry's oidc configuration
- ovh cloud list available log kinds
- get cloud project servicename containerregistry
- delete cloud project servicename containerregist
- ovh cloud add or replace the registry's oidc configuration
- post cloud project servicename activatemonthlybi
- ovh cloud get cassandra advanced configuration
- ovh cloud list all the cassandra clusters of the project
- ovh cloud list your ip restrictions applied on artifact manager component
- get cloud order rule availability
- ovh cloud list integrations
- ovh cloud list registry user
- ovh cloud get all cloud pending orders
- ovh cloud get cassandra backups
- ovh cloud get registry user
- ovh
- ovh cloud list available services
- ovh cloud create a new registry user
- cloud
- delete cloud project servicename database cassan
- ovh cloud get database engines capabilities
- get cloud project servicename capabilities loadb
- get cloud project servicename database capabilit
- post cloud project servicename confirmterminatio
- get cloud project
- ovh cloud confirm service termination
- ovh cloud list backups of the cassandra
- ovh cloud get cassandra ip restrictions
- ovh cloud get specific information of a region
- get cloud project servicename database availabil
- ovh cloud create a new registry
- ovh cloud list registries of the project
- ovh cloud update the registry
- ovh cloud list all available regions
- ovh cloud update the plan of a registry.
- ovh cloud get database engines availability
- ovh cloud list kubernetes available flavors for a region
- ovh cloud deletes the given ip from the restricted ips of the cassandra
- ovh cloud list container registry capabilities per region
- ovh cloud get integration capabilities related to the cassandra service
- ovh cloud get cassandra advanced configuration fields
- ovh cloud update an existing cassandra cluster
- post cloud project servicename database cassandr
- ovh cloud delete a cassandra cluster
- get cloud project servicename capabilities conta
- get cloud project servicename capabilities produ
- ovh cloud list product availability
- ovh cloud get the registry information
- ovh cloud add ip restrictions to the cassandra
- ovh cloud replace ip restrictions applied on harbor ui and api
- get cloud order rule instancecategory
- ovh cloud list your ip restrictions applied on harbor ui and api
- ovh cloud create a new integration
- ovh cloud set the user as admin
- ovh cloud retrieve the certificates of the cassandra cluster
- servers
- ovh cloud get a log kind
- ovh cloud list of admissionplugins managed by mks product that can be enabled or disabled.
- ovh cloud get this object properties
- ovh cloud delete a registry
- ovh cloud delete the registry's oidc configuration
- get cloud project servicename containerregistry
- ovh cloud update cassandra advanced configuration
- ovh cloud get instance categories
- put cloud project servicename
- compute
- ovh cloud edit the registry's oidc configuration
- ovh cloud list kubernetes regions where cluster creation is possible.
- ovh cloud get cassandra cluster properties
- ovh cloud list cassandra ip restrictions
- ovh cloud create a new cassandra cluster
- put cloud project servicename containerregistry
- ovh cloud get product availability
- post cloud project servicename containerregistry
- ovh cloud replace ip restrictions applied on artifact manager component (docker, helm, etc...)
slug: ovh-cloud-capability
source_filename: ovh-cloud-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: OVH Cloud OVHcloud API specification\n  description: Specification for OVHcloud API\n  tags:\n  - Ovh\n  - Cloud\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ovh-cloud\n    baseUri: https://api.us.ovhcloud.com/v1\n    description: OVH Cloud OVHcloud API specification HTTP API.\n    authentication:\n      type: bearer\n      token: '{{OVH_CLOUD_TOKEN}}'\n    resources:\n    - name: cloud-order\n      path: /cloud/order\n      operations:\n      - name: get-cloud-order\n        method: GET\n        description: OVH Cloud Get all cloud pending orders\n        inputParameters:\n        - name: planCode\n          in: query\n          type: string\n          description: Order plan code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-order-rule-availability\n      path: /cloud/order/rule/availability\n\
  \      operations:\n      - name: get-cloud-order-rule-availability\n        method: GET\n        description: OVH Cloud Get product availability\n        inputParameters:\n        - name: addonFamily\n          in: query\n          type: string\n          description: Addon family filter\n        - name: ovhSubsidiary\n          in: query\n          type: string\n          required: true\n          description: OVH subsidiary\n        - name: planCode\n          in: query\n          type: string\n          description: Plan code filter\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-order-rule-instancecategory\n      path: /cloud/order/rule/instanceCategory\n      operations:\n      - name: get-cloud-order-rule-instancecategory\n        method: GET\n        description: OVH Cloud Get instance categories\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n    - name: cloud-project\n      path: /cloud/project\n      operations:\n      - name: get-cloud-project\n        method: GET\n        description: OVH Cloud List available services\n        inputParameters:\n        - name: iamTags\n          in: query\n          type: object\n          description: Filter resources on IAM tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename\n      path: /cloud/project/{serviceName}\n      operations:\n      - name: get-cloud-project-servicename\n        method: GET\n        description: OVH Cloud Get this object properties\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n  \
  \        value: $.\n      - name: put-cloud-project-servicename\n        method: PUT\n        description: OVH Cloud Alter this object properties\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-activatemonthlybilling\n      path: /cloud/project/{serviceName}/activateMonthlyBilling\n      operations:\n      - name: post-cloud-project-servicename-activatemonthlybi\n        method: POST\n        description: OVH Cloud Activate monthly billing on multiple instances\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n        \
  \  type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-container\n      path: /cloud/project/{serviceName}/capabilities/containerRegistry\n      operations:\n      - name: get-cloud-project-servicename-capabilities-conta\n        method: GET\n        description: OVH Cloud List container registry capabilities per region\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-kube-admi\n      path: /cloud/project/{serviceName}/capabilities/kube/admissionplugins\n      operations:\n      - name: get-cloud-project-servicename-capabilities-kube-\n        method: GET\n        description: OVH Cloud List of admissionPlugins managed by MKS product that can be enabled or disabled.\n\
  \        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-kube-flav\n      path: /cloud/project/{serviceName}/capabilities/kube/flavors\n      operations:\n      - name: get-cloud-project-servicename-capabilities-kube-\n        method: GET\n        description: OVH Cloud List Kubernetes available flavors for a region\n        inputParameters:\n        - name: region\n          in: query\n          type: string\n          description: 'The region to list available flavors from. Example: GRA11.'\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-kube-log-\n      path: /cloud/project/{serviceName}/capabilities/kube/log/kind\n      operations:\n      - name: get-cloud-project-servicename-capabilities-kube-\n        method: GET\n        description: OVH Cloud List available log kinds\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-kube-log-\n      path: /cloud/project/{serviceName}/capabilities/kube/log/kind/{name}\n      operations:\n      - name: get-cloud-project-servicename-capabilities-kube-\n        method: GET\n        description: OVH Cloud Get a log kind\n        inputParameters:\n        - name: name\n          in: path\n          type:\
  \ string\n          required: true\n          description: Name\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-kube-regi\n      path: /cloud/project/{serviceName}/capabilities/kube/regions\n      operations:\n      - name: get-cloud-project-servicename-capabilities-kube-\n        method: GET\n        description: OVH Cloud List Kubernetes regions where cluster creation is possible.\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-loadbalan\n\
  \      path: /cloud/project/{serviceName}/capabilities/loadbalancer/region\n      operations:\n      - name: get-cloud-project-servicename-capabilities-loadb\n        method: GET\n        description: OVH Cloud List all available regions\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-loadbalan\n      path: /cloud/project/{serviceName}/capabilities/loadbalancer/region/{regionName}\n      operations:\n      - name: get-cloud-project-servicename-capabilities-loadb\n        method: GET\n        description: OVH Cloud Get specific information of a region\n        inputParameters:\n        - name: regionName\n          in: path\n          type: string\n          required: true\n          description: Region\
  \ name\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-capabilities-productav\n      path: /cloud/project/{serviceName}/capabilities/productAvailability\n      operations:\n      - name: get-cloud-project-servicename-capabilities-produ\n        method: GET\n        description: OVH Cloud List product availability\n        inputParameters:\n        - name: addonFamily\n          in: query\n          type: string\n          description: Addon family filter\n        - name: ovhSubsidiary\n          in: query\n          type: string\n          required: true\n          description: OVH subsidiary\n        - name: planCode\n          in: query\n          type: string\n          description: Plan code filter\n        - name: planFamily\n    \
  \      in: query\n          type: string\n          description: Plan family filter (deprecated, use addonFamily instead)\n        - name: product\n          in: query\n          type: string\n          description: Product filter\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-confirmtermination\n      path: /cloud/project/{serviceName}/confirmTermination\n      operations:\n      - name: post-cloud-project-servicename-confirmterminatio\n        method: POST\n        description: OVH Cloud Confirm service termination\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: The project id\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry\n      path: /cloud/project/{serviceName}/containerRegistry\n      operations:\n      - name: get-cloud-project-servicename-containerregistry\n        method: GET\n        description: OVH Cloud List registries of the project\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-cloud-project-servicename-containerregistry\n        method: POST\n        description: OVH Cloud Create a new registry\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}\n      operations:\n      - name: delete-cloud-project-servicename-containerregist\n        method: DELETE\n        description: OVH Cloud Delete a registry\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud Get the registry information\n        inputParameters:\n        - name: registryID\n          in: path\n\
  \          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Update the registry\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/capabilities/plan\n\
  \      operations:\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud Get available plans for the current registry.\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/management\n      operations:\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud List your IP restrictions applied on Harbor UI and API\n        inputParameters:\n        - name: registryID\n\
  \          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Replace IP restrictions applied on Harbor UI and API\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n\
  \      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/ipRestrictions/registry\n      operations:\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud List your IP restrictions applied on artifact manager component\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Replace IP restrictions applied on artifact manager component (Docker, Helm, etc...)\n        inputParameters:\n        - name: registryID\n          in: path\n   \
  \       type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/openIdConnect\n      operations:\n      - name: delete-cloud-project-servicename-containerregist\n        method: DELETE\n        description: OVH Cloud Delete the registry's OIDC Configuration\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud Get the registry's OIDC configuration\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-cloud-project-servicename-containerregistry\n        method: POST\n        description: OVH Cloud Add or replace the registry's OIDC configuration\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n\
  \        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Edit the registry's OIDC configuration\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/plan\n      operations:\n\
  \      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud Show the actual plan of the registry.\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Update the plan of a registry.\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description:\
  \ Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users\n      operations:\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud List registry user\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-cloud-project-servicename-containerregistry\n        method: POST\n        description: OVH Cloud Create a new registry\
  \ user\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users/{userID}\n      operations:\n      - name: delete-cloud-project-servicename-containerregist\n        method: DELETE\n        description: OVH Cloud Delete a registry user\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n\
  \          description: Service name\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: UserID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cloud-project-servicename-containerregistry-\n        method: GET\n        description: OVH Cloud Get registry user\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: UserID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-containerregistry-regi\n\
  \      path: /cloud/project/{serviceName}/containerRegistry/{registryID}/users/{userID}/setAsAdmin\n      operations:\n      - name: put-cloud-project-servicename-containerregistry-\n        method: PUT\n        description: OVH Cloud Set the user as Admin\n        inputParameters:\n        - name: registryID\n          in: path\n          type: string\n          required: true\n          description: RegistryID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        - name: userID\n          in: path\n          type: string\n          required: true\n          description: UserID\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-availability\n      path: /cloud/project/{serviceName}/database/availability\n      operations:\n      - name: get-cloud-project-servicename-database-availabil\n\
  \        method: GET\n        description: OVH Cloud Get database engines availability\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          description: Type of action on which restrict the availabilities\n        - name: clusterId\n          in: query\n          type: string\n          description: Cluster ID on which restrict the availabilities\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        - name: target\n          in: query\n          type: string\n          description: Type of target on which restrict the availabilities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-capabilities\n      path: /cloud/project/{serviceName}/database/capabilities\n      operations:\n      - name: get-cloud-project-servicename-database-capabilit\n\
  \        method: GET\n        description: OVH Cloud Get database engines capabilities\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra\n      path: /cloud/project/{serviceName}/database/cassandra\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud List all the cassandra clusters of the project\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-cloud-project-servicename-database-cassandr\n\
  \        method: POST\n        description: OVH Cloud Create a new cassandra cluster\n        inputParameters:\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n      path: /cloud/project/{serviceName}/database/cassandra/{clusterId}\n      operations:\n      - name: delete-cloud-project-servicename-database-cassan\n        method: DELETE\n        description: OVH Cloud Delete a cassandra cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud Get cassandra cluster properties\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: put-cloud-project-servicename-database-cassandra\n        method: PUT\n        description: OVH Cloud Update an existing cassandra cluster\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n\
  \          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n      path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/advancedConfiguration\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud Get cassandra advanced configuration\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name:\
  \ put-cloud-project-servicename-database-cassandra\n        method: PUT\n        description: OVH Cloud Update cassandra advanced configuration\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n      path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/backup\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud List backups of the cassandra\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n  \
  \        description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n      path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/backup/{backupId}\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud Get cassandra backups\n        inputParameters:\n        - name: backupId\n          in: path\n          type: string\n          required: true\n          description: Backup ID\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n    \
  \      description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n      path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/capabilities/advancedConfiguration\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud Get cassandra advanced configuration fields\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cloud-project-servicename-database-cassandra-clu\n     \
  \ path: /cloud/project/{serviceName}/database/cassandra/{clusterId}/capabilities/integration\n      operations:\n      - name: get-cloud-project-servicename-database-cassandra\n        method: GET\n        description: OVH Cloud Get integration capabilities related to the cassandra service\n        inputParameters:\n        - name: clusterId\n          in: path\n          type: string\n          required: true\n          description: Cluster ID\n        - name: serviceName\n          in: path\n          type: string\n          required: true\n          description: Service name\n        outputRawFo\n\n# --- truncated at 32 KB (107 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ovh-cloud/refs/heads/main/capabilities/ovh-cloud-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ovh-cloud/refs/heads/main/capabilities/ovh-cloud-capability.yaml
tags:
- Ovh
- Cloud
- API
tools:
- description: OVH Cloud Get all cloud pending orders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-order
- description: OVH Cloud Get product availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-order-rule-availability
- description: OVH Cloud Get instance categories
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-order-rule-instancecategory
- description: OVH Cloud List available services
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project
- description: OVH Cloud Get this object properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename
- description: OVH Cloud Alter this object properties
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename
- description: OVH Cloud Activate monthly billing on multiple instances
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-activatemonthlybi
- description: OVH Cloud List container registry capabilities per region
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-conta
- description: OVH Cloud List of admissionPlugins managed by MKS product that can be enabled or disabled.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-kube-
- description: OVH Cloud List Kubernetes available flavors for a region
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-kube-
- description: OVH Cloud List available log kinds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-kube-
- description: OVH Cloud Get a log kind
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-kube-
- description: OVH Cloud List Kubernetes regions where cluster creation is possible.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-kube-
- description: OVH Cloud List all available regions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-loadb
- description: OVH Cloud Get specific information of a region
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-loadb
- description: OVH Cloud List product availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-capabilities-produ
- description: OVH Cloud Confirm service termination
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-confirmterminatio
- description: OVH Cloud List registries of the project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry
- description: OVH Cloud Create a new registry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-containerregistry
- description: OVH Cloud Delete a registry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-containerregist
- description: OVH Cloud Get the registry information
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Update the registry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud Get available plans for the current registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud List your IP restrictions applied on Harbor UI and API
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Replace IP restrictions applied on Harbor UI and API
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud List your IP restrictions applied on artifact manager component
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Replace IP restrictions applied on artifact manager component (Docker, Helm, etc...)
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud Delete the registry's OIDC Configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-containerregist
- description: OVH Cloud Get the registry's OIDC configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Add or replace the registry's OIDC configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-containerregistry
- description: OVH Cloud Edit the registry's OIDC configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud Show the actual plan of the registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Update the plan of a registry.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud List registry user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Create a new registry user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-containerregistry
- description: OVH Cloud Delete a registry user
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-containerregist
- description: OVH Cloud Get registry user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-containerregistry-
- description: OVH Cloud Set the user as Admin
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-containerregistry-
- description: OVH Cloud Get database engines availability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-availabil
- description: OVH Cloud Get database engines capabilities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-capabilit
- description: OVH Cloud List all the cassandra clusters of the project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Create a new cassandra cluster
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-database-cassandr
- description: OVH Cloud Delete a cassandra cluster
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-database-cassan
- description: OVH Cloud Get cassandra cluster properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Update an existing cassandra cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-database-cassandra
- description: OVH Cloud Get cassandra advanced configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Update cassandra advanced configuration
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: put-cloud-project-servicename-database-cassandra
- description: OVH Cloud List backups of the cassandra
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Get cassandra backups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Get cassandra advanced configuration fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Get integration capabilities related to the cassandra service
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Retrieve the certificates of the cassandra cluster
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud List integrations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Create a new integration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-database-cassandr
- description: OVH Cloud Delete an integration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-database-cassan
- description: OVH Cloud Get an integration
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud List cassandra ip restrictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
- description: OVH Cloud Add ip restrictions to the cassandra
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-cloud-project-servicename-database-cassandr
- description: OVH Cloud Deletes the given IP from the restricted IPs of the cassandra
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-cloud-project-servicename-database-cassan
- description: OVH Cloud Get cassandra ip restrictions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-cloud-project-servicename-database-cassandra
---
