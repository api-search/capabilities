---
categories: []
consumed_apis: []
description: CAST AI is a Kubernetes cost optimization platform that provides APIs for managing clusters, autoscaling, node configuration, workload optimization, cost reporting, security insights, and more. The platform continuously monitors clusters and optimizes them for cost efficiency using autoscaling, spot instance automation, bin packing, and other techniques.
layout: capability
name: CAST AI Kubernetes Cost Optimization API
operations:
- description: CAST AI List cluster nodes
  method: GET
  name: externalclusterapi-listnodes
  path: /kubernetes/external-clusters/{clusterId}/nodes
- description: CAST AI Drain cluster node
  method: POST
  name: externalclusterapi-drainnode
  path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}/drain
- description: CAST AI Delete cluster node
  method: DELETE
  name: externalclusterapi-deletenode
  path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}
- description: CAST AI Get cluster policies
  method: GET
  name: policiesapi-getclusterpolicies
  path: /kubernetes/clusters/{clusterId}/policies
- description: CAST AI Upsert cluster policies
  method: PUT
  name: policiesapi-upsertclusterpolicies
  path: /kubernetes/clusters/{clusterId}/policies
- description: CAST AI List node templates
  method: GET
  name: nodetemplatesapi-listnodetemplates
  path: /kubernetes/clusters/{clusterId}/node-templates
- description: CAST AI Create node template
  method: POST
  name: nodetemplatesapi-createnodetemplate
  path: /kubernetes/clusters/{clusterId}/node-templates
- description: CAST AI Get node template
  method: GET
  name: nodetemplatesapi-getnodetemplate
  path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}
- description: CAST AI Update node template
  method: PUT
  name: nodetemplatesapi-updatenodetemplate
  path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}
- description: CAST AI Delete node template
  method: DELETE
  name: nodetemplatesapi-deletenodetemplate
  path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}
- description: CAST AI List node configurations
  method: GET
  name: nodeconfigurationapi-listconfigurations
  path: /kubernetes/clusters/{clusterId}/node-configurations
- description: CAST AI Create node configuration
  method: POST
  name: nodeconfigurationapi-createconfiguration
  path: /kubernetes/clusters/{clusterId}/node-configurations
- description: CAST AI Delete node configuration
  method: DELETE
  name: nodeconfigurationapi-deleteconfiguration
  path: /kubernetes/clusters/{clusterId}/node-configurations/{configurationId}
- description: CAST AI Trigger rebalancing plan
  method: POST
  name: autoscalerapi-executerebalancingplan
  path: /kubernetes/clusters/{clusterId}/rebalancing-plans/{rebalancingPlanId}/execute
- description: CAST AI Acknowledge cluster action
  method: POST
  name: clusteractionsapi-ackclusteraction
  path: /kubernetes/clusters/{clusterId}/actions/{actionId}/ack
- description: CAST AI Ingest cluster controller logs
  method: POST
  name: clusteractionsapi-ingestlogs
  path: /kubernetes/clusters/{clusterId}/actions/logs
- description: CAST AI List workloads
  method: GET
  name: workloadoptimizationapi-listworkloads
  path: /workload-autoscaling/clusters/{clusterId}/workloads
- description: CAST AI Get workload
  method: GET
  name: workloadoptimizationapi-getworkload
  path: /workload-autoscaling/clusters/{clusterId}/workloads/{workloadId}
- description: CAST AI Get agent statuses
  method: GET
  name: workloadoptimizationapi-getorganizationagentstat
  path: /workload-autoscaling/agent-statuses
- description: CAST AI Create rebalancing schedule
  method: POST
  name: scheduledrebalancingapi-createrebalancingschedul
  path: /scheduled-rebalancing/schedules
- description: CAST AI Get rebalancing schedule
  method: GET
  name: scheduledrebalancingapi-getrebalancingschedule
  path: /scheduled-rebalancing/schedules/{scheduleId}
- description: CAST AI Delete rebalancing schedule
  method: DELETE
  name: scheduledrebalancingapi-deleterebalancingschedul
  path: /scheduled-rebalancing/schedules/{scheduleId}
- description: CAST AI Get operation
  method: GET
  name: operationsapi-getoperation
  path: /operations/{operationId}
- description: CAST AI Add to blacklist
  method: POST
  name: inventoryblacklistapi-addblacklist
  path: /inventory/blacklist/add
- description: CAST AI Get node pricing
  method: GET
  name: pricingapi-getnodepricing
  path: /pricing/clusters/{clusterId}/nodes/{nodeId}
- description: CAST AI Sync GCP billing data
  method: POST
  name: pricingapi-syncgcpbillingapidata
  path: /pricing/sync-gcp-billing
- description: CAST AI Get cluster efficiency
  method: GET
  name: costreportsapi-getclusterefficiency
  path: /cost-reports/clusters/{clusterId}/efficiency
- description: CAST AI Get allocation group workloads efficiency
  method: GET
  name: allocationgroupapi-getallocationgroupworkloadsef
  path: /allocation-groups/{allocationGroupId}/workloads/efficiency
- description: CAST AI Get best practices report filters
  method: GET
  name: insightsapi-getbestpracticesreportfilters
  path: /security/insights/best-practices/filters
- description: CAST AI Get container image digests
  method: GET
  name: insightsapi-getcontainerimagedigests
  path: /security/insights/images/{tagId}/digests
- description: CAST AI Create hibernation schedule
  method: POST
  name: hibernationschedulesapi-createhibernationschedul
  path: /hibernation/schedules
- description: CAST AI Create or update API key settings
  method: PUT
  name: settingsapi-upsertapikeysettings
  path: /settings/api-keys/{apiKeyId}
- description: CAST AI Get LLM providers
  method: GET
  name: aienablerprovidersapi-getproviders
  path: /llm/providers
- description: CAST AI Register LLM providers
  method: POST
  name: aienablerprovidersapi-registerproviders
  path: /llm/providers
- description: CAST AI Get cluster metrics
  method: GET
  name: metricsapi-getclustermetrics
  path: /metrics/prom
- description: CAST AI Get node metrics
  method: GET
  name: metricsapi-getnodemetrics
  path: /metrics/nodes
- description: CAST AI Get workload metrics
  method: GET
  name: metricsapi-getworkloadmetrics
  path: /metrics/workloads
- description: CAST AI Get allocation group metrics
  method: GET
  name: metricsapi-getallocationgroupmetrics
  path: /metrics/allocation-groups
personas: []
provider_name: CAST AI
provider_slug: cast-ai
search_terms:
- workloadoptimizationapi getworkload
- scheduledrebalancingapi createrebalancingschedul
- cast ai drain cluster node
- finops
- metricsapi getworkloadmetrics
- aienablerprovidersapi getproviders
- cast ai upsert cluster policies
- metricsapi getallocationgroupmetrics
- settingsapi upsertapikeysettings
- cast ai get agent statuses
- clusteractionsapi ackclusteraction
- insightsapi getcontainerimagedigests
- metricsapi getclustermetrics
- cast ai get allocation group metrics
- api
- externalclusterapi deletenode
- observability
- nodetemplatesapi createnodetemplate
- cast ai create rebalancing schedule
- metricsapi getnodemetrics
- cast ai get cluster efficiency
- insightsapi getbestpracticesreportfilters
- cast ai sync gcp billing data
- cast ai list cluster nodes
- cast ai create node configuration
- nodeconfigurationapi listconfigurations
- cast ai get rebalancing schedule
- autoscaling
- clusteractionsapi ingestlogs
- costreportsapi getclusterefficiency
- ai
- kubernetes
- nodetemplatesapi deletenodetemplate
- cast ai delete node configuration
- cost optimization
- cast ai get workload
- cast ai trigger rebalancing plan
- cast ai register llm providers
- workloadoptimizationapi getorganizationagentstat
- cast ai acknowledge cluster action
- cast ai get container image digests
- workloadoptimizationapi listworkloads
- policiesapi getclusterpolicies
- cast ai create node template
- cast ai create or update api key settings
- devops
- cast ai get allocation group workloads efficiency
- cast ai list node configurations
- cast ai get node pricing
- cast ai get llm providers
- nodeconfigurationapi createconfiguration
- nodetemplatesapi updatenodetemplate
- cast ai update node template
- cast ai get cluster metrics
- allocationgroupapi getallocationgroupworkloadsef
- cast ai delete cluster node
- cast ai delete node template
- cast
- nodetemplatesapi listnodetemplates
- cast ai add to blacklist
- autoscalerapi executerebalancingplan
- scheduledrebalancingapi deleterebalancingschedul
- cast ai get node template
- externalclusterapi drainnode
- nodeconfigurationapi deleteconfiguration
- cast ai get best practices report filters
- operationsapi getoperation
- cast ai get node metrics
- nodetemplatesapi getnodetemplate
- cloud infrastructure
- cast ai get cluster policies
- pricingapi getnodepricing
- hibernationschedulesapi createhibernationschedul
- externalclusterapi listnodes
- cast ai create hibernation schedule
- cast ai get workload metrics
- scheduledrebalancingapi getrebalancingschedule
- pricingapi syncgcpbillingapidata
- inventoryblacklistapi addblacklist
- cast ai list node templates
- cast ai delete rebalancing schedule
- policiesapi upsertclusterpolicies
- cast ai ingest cluster controller logs
- cast ai get operation
- aienablerprovidersapi registerproviders
- cast ai list workloads
slug: cast-ai-capability
source_filename: cast-ai-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: CAST AI Kubernetes Cost Optimization API\n  description: CAST AI is a Kubernetes cost optimization platform that provides APIs for managing clusters, autoscaling, node\n    configuration, workload optimization, cost reporting, security insights, and more. The platform continuously monitors\n    clusters and optimizes them for cost efficiency using autoscaling, spot instance automation, bin packing, and other techniques.\n  tags:\n  - Cast\n  - Ai\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: cast-ai\n    baseUri: https://api.cast.ai/v1\n    description: CAST AI Kubernetes Cost Optimization API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{CAST_AI_TOKEN}}'\n    resources:\n    - name: kubernetes-external-clusters-clusterid-nodes\n      path: /kubernetes/external-clusters/{clusterId}/nodes\n      operations:\n\
  \      - name: externalclusterapi-listnodes\n        method: GET\n        description: CAST AI List cluster nodes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-external-clusters-clusterid-nodes-nod\n      path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}/drain\n      operations:\n      - name: externalclusterapi-drainnode\n        method: POST\n        description: CAST AI Drain cluster node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-external-clusters-clusterid-nodes-nod\n      path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}\n      operations:\n      - name: externalclusterapi-deletenode\n        method: DELETE\n        description: CAST AI Delete cluster node\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-policies\n      path: /kubernetes/clusters/{clusterId}/policies\n      operations:\n      - name: policiesapi-getclusterpolicies\n        method: GET\n        description: CAST AI Get cluster policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: policiesapi-upsertclusterpolicies\n        method: PUT\n        description: CAST AI Upsert cluster policies\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-node-templates\n      path: /kubernetes/clusters/{clusterId}/node-templates\n      operations:\n      - name: nodetemplatesapi-listnodetemplates\n        method: GET\n        description: CAST AI List node templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: nodetemplatesapi-createnodetemplate\n        method: POST\n        description: CAST AI Create node template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-node-templates-nod\n      path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}\n      operations:\n      - name: nodetemplatesapi-getnodetemplate\n        method: GET\n        description: CAST AI Get node template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: nodetemplatesapi-updatenodetemplate\n        method: PUT\n        description: CAST AI Update node template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: nodetemplatesapi-deletenodetemplate\n\
  \        method: DELETE\n        description: CAST AI Delete node template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-node-configuration\n      path: /kubernetes/clusters/{clusterId}/node-configurations\n      operations:\n      - name: nodeconfigurationapi-listconfigurations\n        method: GET\n        description: CAST AI List node configurations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: nodeconfigurationapi-createconfiguration\n        method: POST\n        description: CAST AI Create node configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-node-configuration\n      path: /kubernetes/clusters/{clusterId}/node-configurations/{configurationId}\n\
  \      operations:\n      - name: nodeconfigurationapi-deleteconfiguration\n        method: DELETE\n        description: CAST AI Delete node configuration\n        inputParameters:\n        - name: configurationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-rebalancing-plans-\n      path: /kubernetes/clusters/{clusterId}/rebalancing-plans/{rebalancingPlanId}/execute\n      operations:\n      - name: autoscalerapi-executerebalancingplan\n        method: POST\n        description: CAST AI Trigger rebalancing plan\n        inputParameters:\n        - name: rebalancingPlanId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-actions-actionid-a\n\
  \      path: /kubernetes/clusters/{clusterId}/actions/{actionId}/ack\n      operations:\n      - name: clusteractionsapi-ackclusteraction\n        method: POST\n        description: CAST AI Acknowledge cluster action\n        inputParameters:\n        - name: actionId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kubernetes-clusters-clusterid-actions-logs\n      path: /kubernetes/clusters/{clusterId}/actions/logs\n      operations:\n      - name: clusteractionsapi-ingestlogs\n        method: POST\n        description: CAST AI Ingest cluster controller logs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workload-autoscaling-clusters-clusterid-workload\n      path: /workload-autoscaling/clusters/{clusterId}/workloads\n      operations:\n\
  \      - name: workloadoptimizationapi-listworkloads\n        method: GET\n        description: CAST AI List workloads\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workload-autoscaling-clusters-clusterid-workload\n      path: /workload-autoscaling/clusters/{clusterId}/workloads/{workloadId}\n      operations:\n      - name: workloadoptimizationapi-getworkload\n        method: GET\n        description: CAST AI Get workload\n        inputParameters:\n        - name: workloadId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: workload-autoscaling-agent-statuses\n      path: /workload-autoscaling/agent-statuses\n      operations:\n      - name: workloadoptimizationapi-getorganizationagentstat\n        method: GET\n        description: CAST\
  \ AI Get agent statuses\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduled-rebalancing-schedules\n      path: /scheduled-rebalancing/schedules\n      operations:\n      - name: scheduledrebalancingapi-createrebalancingschedul\n        method: POST\n        description: CAST AI Create rebalancing schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: scheduled-rebalancing-schedules-scheduleid\n      path: /scheduled-rebalancing/schedules/{scheduleId}\n      operations:\n      - name: scheduledrebalancingapi-getrebalancingschedule\n        method: GET\n        description: CAST AI Get rebalancing schedule\n        inputParameters:\n        - name: scheduleId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: scheduledrebalancingapi-deleterebalancingschedul\n        method: DELETE\n        description: CAST AI Delete rebalancing schedule\n        inputParameters:\n        - name: scheduleId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-operationid\n      path: /operations/{operationId}\n      operations:\n      - name: operationsapi-getoperation\n        method: GET\n        description: CAST AI Get operation\n        inputParameters:\n        - name: operationId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: inventory-blacklist-add\n      path: /inventory/blacklist/add\n      operations:\n\
  \      - name: inventoryblacklistapi-addblacklist\n        method: POST\n        description: CAST AI Add to blacklist\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricing-clusters-clusterid-nodes-nodeid\n      path: /pricing/clusters/{clusterId}/nodes/{nodeId}\n      operations:\n      - name: pricingapi-getnodepricing\n        method: GET\n        description: CAST AI Get node pricing\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: pricing-sync-gcp-billing\n      path: /pricing/sync-gcp-billing\n      operations:\n      - name: pricingapi-syncgcpbillingapidata\n        method: POST\n        description: CAST AI Sync GCP billing data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-reports-clusters-clusterid-efficiency\n\
  \      path: /cost-reports/clusters/{clusterId}/efficiency\n      operations:\n      - name: costreportsapi-getclusterefficiency\n        method: GET\n        description: CAST AI Get cluster efficiency\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allocation-groups-allocationgroupid-workloads-ef\n      path: /allocation-groups/{allocationGroupId}/workloads/efficiency\n      operations:\n      - name: allocationgroupapi-getallocationgroupworkloadsef\n        method: GET\n        description: CAST AI Get allocation group workloads efficiency\n        inputParameters:\n        - name: allocationGroupId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-insights-best-practices-filters\n      path: /security/insights/best-practices/filters\n\
  \      operations:\n      - name: insightsapi-getbestpracticesreportfilters\n        method: GET\n        description: CAST AI Get best practices report filters\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: security-insights-images-tagid-digests\n      path: /security/insights/images/{tagId}/digests\n      operations:\n      - name: insightsapi-getcontainerimagedigests\n        method: GET\n        description: CAST AI Get container image digests\n        inputParameters:\n        - name: tagId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: hibernation-schedules\n      path: /hibernation/schedules\n      operations:\n      - name: hibernationschedulesapi-createhibernationschedul\n        method: POST\n        description: CAST AI Create\
  \ hibernation schedule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: settings-api-keys-apikeyid\n      path: /settings/api-keys/{apiKeyId}\n      operations:\n      - name: settingsapi-upsertapikeysettings\n        method: PUT\n        description: CAST AI Create or update API key settings\n        inputParameters:\n        - name: apiKeyId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: llm-providers\n      path: /llm/providers\n      operations:\n      - name: aienablerprovidersapi-getproviders\n        method: GET\n        description: CAST AI Get LLM providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: aienablerprovidersapi-registerproviders\n\
  \        method: POST\n        description: CAST AI Register LLM providers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-prom\n      path: /metrics/prom\n      operations:\n      - name: metricsapi-getclustermetrics\n        method: GET\n        description: CAST AI Get cluster metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-nodes\n      path: /metrics/nodes\n      operations:\n      - name: metricsapi-getnodemetrics\n        method: GET\n        description: CAST AI Get node metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-workloads\n      path: /metrics/workloads\n      operations:\n      - name: metricsapi-getworkloadmetrics\n        method: GET\n        description: CAST\
  \ AI Get workload metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: metrics-allocation-groups\n      path: /metrics/allocation-groups\n      operations:\n      - name: metricsapi-getallocationgroupmetrics\n        method: GET\n        description: CAST AI Get allocation group metrics\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: cast-ai-rest\n    description: REST adapter for CAST AI Kubernetes Cost Optimization API.\n    resources:\n    - path: /kubernetes/external-clusters/{clusterId}/nodes\n      name: externalclusterapi-listnodes\n      operations:\n      - method: GET\n        name: externalclusterapi-listnodes\n        description: CAST AI List cluster nodes\n        call: cast-ai.externalclusterapi-listnodes\n        outputParameters:\n       \
  \ - type: object\n          mapping: $.\n    - path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}/drain\n      name: externalclusterapi-drainnode\n      operations:\n      - method: POST\n        name: externalclusterapi-drainnode\n        description: CAST AI Drain cluster node\n        call: cast-ai.externalclusterapi-drainnode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/external-clusters/{clusterId}/nodes/{nodeId}\n      name: externalclusterapi-deletenode\n      operations:\n      - method: DELETE\n        name: externalclusterapi-deletenode\n        description: CAST AI Delete cluster node\n        call: cast-ai.externalclusterapi-deletenode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/policies\n      name: policiesapi-getclusterpolicies\n      operations:\n      - method: GET\n        name: policiesapi-getclusterpolicies\n        description:\
  \ CAST AI Get cluster policies\n        call: cast-ai.policiesapi-getclusterpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/policies\n      name: policiesapi-upsertclusterpolicies\n      operations:\n      - method: PUT\n        name: policiesapi-upsertclusterpolicies\n        description: CAST AI Upsert cluster policies\n        call: cast-ai.policiesapi-upsertclusterpolicies\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-templates\n      name: nodetemplatesapi-listnodetemplates\n      operations:\n      - method: GET\n        name: nodetemplatesapi-listnodetemplates\n        description: CAST AI List node templates\n        call: cast-ai.nodetemplatesapi-listnodetemplates\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-templates\n      name: nodetemplatesapi-createnodetemplate\n\
  \      operations:\n      - method: POST\n        name: nodetemplatesapi-createnodetemplate\n        description: CAST AI Create node template\n        call: cast-ai.nodetemplatesapi-createnodetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}\n      name: nodetemplatesapi-getnodetemplate\n      operations:\n      - method: GET\n        name: nodetemplatesapi-getnodetemplate\n        description: CAST AI Get node template\n        call: cast-ai.nodetemplatesapi-getnodetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}\n      name: nodetemplatesapi-updatenodetemplate\n      operations:\n      - method: PUT\n        name: nodetemplatesapi-updatenodetemplate\n        description: CAST AI Update node template\n        call: cast-ai.nodetemplatesapi-updatenodetemplate\n    \
  \    outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-templates/{nodeTemplateId}\n      name: nodetemplatesapi-deletenodetemplate\n      operations:\n      - method: DELETE\n        name: nodetemplatesapi-deletenodetemplate\n        description: CAST AI Delete node template\n        call: cast-ai.nodetemplatesapi-deletenodetemplate\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-configurations\n      name: nodeconfigurationapi-listconfigurations\n      operations:\n      - method: GET\n        name: nodeconfigurationapi-listconfigurations\n        description: CAST AI List node configurations\n        call: cast-ai.nodeconfigurationapi-listconfigurations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-configurations\n      name: nodeconfigurationapi-createconfiguration\n\
  \      operations:\n      - method: POST\n        name: nodeconfigurationapi-createconfiguration\n        description: CAST AI Create node configuration\n        call: cast-ai.nodeconfigurationapi-createconfiguration\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/node-configurations/{configurationId}\n      name: nodeconfigurationapi-deleteconfiguration\n      operations:\n      - method: DELETE\n        name: nodeconfigurationapi-deleteconfiguration\n        description: CAST AI Delete node configuration\n        call: cast-ai.nodeconfigurationapi-deleteconfiguration\n        with:\n          configurationId: rest.configurationId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/rebalancing-plans/{rebalancingPlanId}/execute\n      name: autoscalerapi-executerebalancingplan\n      operations:\n      - method: POST\n        name: autoscalerapi-executerebalancingplan\n\
  \        description: CAST AI Trigger rebalancing plan\n        call: cast-ai.autoscalerapi-executerebalancingplan\n        with:\n          rebalancingPlanId: rest.rebalancingPlanId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/actions/{actionId}/ack\n      name: clusteractionsapi-ackclusteraction\n      operations:\n      - method: POST\n        name: clusteractionsapi-ackclusteraction\n        description: CAST AI Acknowledge cluster action\n        call: cast-ai.clusteractionsapi-ackclusteraction\n        with:\n          actionId: rest.actionId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /kubernetes/clusters/{clusterId}/actions/logs\n      name: clusteractionsapi-ingestlogs\n      operations:\n      - method: POST\n        name: clusteractionsapi-ingestlogs\n        description: CAST AI Ingest cluster controller logs\n        call: cast-ai.clusteractionsapi-ingestlogs\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workload-autoscaling/clusters/{clusterId}/workloads\n      name: workloadoptimizationapi-listworkloads\n      operations:\n      - method: GET\n        name: workloadoptimizationapi-listworkloads\n        description: CAST AI List workloads\n        call: cast-ai.workloadoptimizationapi-listworkloads\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workload-autoscaling/clusters/{clusterId}/workloads/{workloadId}\n      name: workloadoptimizationapi-getworkload\n      operations:\n      - method: GET\n        name: workloadoptimizationapi-getworkload\n        description: CAST AI Get workload\n        call: cast-ai.workloadoptimizationapi-getworkload\n        with:\n          workloadId: rest.workloadId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /workload-autoscaling/agent-statuses\n      name: workloadoptimizationapi-getorganizationagentstat\n\
  \      operations:\n      - method: GET\n        name: workloadoptimizationapi-getorganizationagentstat\n        description: CAST AI Get agent statuses\n        call: cast-ai.workloadoptimizationapi-getorganizationagentstat\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled-rebalancing/schedules\n      name: scheduledrebalancingapi-createrebalancingschedul\n      operations:\n      - method: POST\n        name: scheduledrebalancingapi-createrebalancingschedul\n        description: CAST AI Create rebalancing schedule\n        call: cast-ai.scheduledrebalancingapi-createrebalancingschedul\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled-rebalancing/schedules/{scheduleId}\n      name: scheduledrebalancingapi-getrebalancingschedule\n      operations:\n      - method: GET\n        name: scheduledrebalancingapi-getrebalancingschedule\n        description: CAST AI Get rebalancing schedule\n      \
  \  call: cast-ai.scheduledrebalancingapi-getrebalancingschedule\n        with:\n          scheduleId: rest.scheduleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /scheduled-rebalancing/schedules/{scheduleId}\n      name: scheduledrebalancingapi-deleterebalancingschedul\n      operations:\n      - method: DELETE\n        name: scheduledrebalancingapi-deleterebalancingschedul\n        description: CAST AI Delete rebalancing schedule\n        call: cast-ai.scheduledrebalancingapi-deleterebalancingschedul\n        with:\n          scheduleId: rest.scheduleId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/{operationId}\n      name: operationsapi-getoperation\n      operations:\n      - method: GET\n        name: operationsapi-getoperation\n        description: CAST AI Get operation\n        call: cast-ai.operationsapi-getoperation\n        with:\n          operationId: rest.operationId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /inventory/blacklist/add\n      name: inventoryblacklistapi-addblacklist\n      operations:\n      - method: POST\n        name: inventoryblacklistapi-addblacklist\n        description: CAST AI Add to blacklist\n        call: cast-ai.inventoryblacklistapi-addblacklist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pricing/clusters/{clusterId}/nodes/{nodeId}\n      name: pricingapi-getnodepricing\n      operations:\n      - method: GET\n        name: pricingapi-getnodepricing\n        description: CAST AI Get node pricing\n        call: cast-ai.pricingapi-getnodepricing\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /pricing/sync-gcp-billing\n      name: pricingapi-syncgcpbillingapidata\n      operations:\n      - method: POST\n        name: pricingapi-syncgcpbillingapidata\n        description: CAST AI Sync GCP billing data\n        call: cast-ai.pricingapi-syncgcpbillingapidata\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cost-reports/clusters/{clusterId}/efficiency\n      name: costreportsapi-getclusterefficiency\n      operations:\n      - method: GET\n        name: costreportsapi-getclusterefficiency\n        description: CAST AI Get cluster efficiency\n        call: cast-ai.costreportsapi-getclusterefficiency\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /allocation-groups/{allocationGroupId}/workloads/efficiency\n      name: allocationgroupapi-getallocationgroupworkloadsef\n      operations:\n      - method: GET\n        name: allocationgroupapi-getallocationgroupworkloadsef\n        description: CAST AI Get allocation group workloads efficiency\n        call: cast-ai.allocationgroupapi-getallocationgroupworkloadsef\n        with:\n          allocationGroupId: rest.allocationGroupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /security/insights/best-practices/filters\n\
  \      name: insightsapi-getbestpracticesreportfilters\n      operations:\n      - method: GET\n        name: insightsapi-getbestpracticesreportfilters\n        description: CAST AI Get best practices report filters\n        call: cast-ai.insightsapi-getbestpracticesreportfilters\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /security/insights/images/{tagId}/digests\n      name: insightsapi-getcontainerimagedigests\n      operations:\n      - method: GET\n        name: insightsapi-getcontainerimagedigests\n        description: CAST AI Get container image digests\n        call: cast-ai.insightsapi-getcontainerimagedigests\n        with:\n          tagId: rest.tagId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /hibernation/schedules\n      name: hibernationschedulesapi-createhibernationschedul\n      operations:\n      - method: POST\n        name: hibernationschedulesapi-createhibernationschedul\n       \
  \ description: CAST AI Create hibernation schedule\n        call: cast-ai.hibernationschedulesapi-createhibernationschedul\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /settings/api-keys/{apiKeyId}\n      name: settingsapi-upsertapikeysettings\n      operations:\n      - method: PUT\n        name: settingsapi-upsertapikeysettings\n        description: CAST AI Create or update API key settings\n        call: cast-ai.settingsapi-upsertapikeysettings\n        with:\n          apiKeyId: rest.apiKeyId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /llm/providers\n      name: aienablerprovidersapi-getproviders\n      operations:\n      - method: GET\n        name: aienablerprovidersapi-getproviders\n        description: CAST AI Get LLM providers\n        call: cast-ai.aienablerprovidersapi-getproviders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /llm/providers\n      name:\
  \ aienablerprovidersapi-registerproviders\n      operations:\n      - method: POST\n        name: aienablerprovidersapi-registerproviders\n        description: CAST AI Register LLM providers\n        call: cast-ai.aienablerprovidersapi-registerproviders\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/prom\n      name: metricsapi-getclustermetrics\n      operations:\n      - method: GET\n        name: metricsapi-getclustermetrics\n        description: CAST AI Get cluster metrics\n        call: cast-ai.metricsapi-getclustermetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/nodes\n      name: metricsapi-getnodemetrics\n      operations:\n      - method: GET\n        name: metricsapi-getnodemetrics\n        description: CAST AI Get node metrics\n        call: cast-ai.metricsapi-getnodemetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/workloads\n\
  \      name: metricsapi-getworkloadmetrics\n      operations:\n      - method: GET\n        name: metricsapi-getworkloadmetrics\n        description: CAST AI Get workload metrics\n        call: cast-ai.metricsapi-getworkloadmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /metrics/allocation-groups\n      name: metricsapi-getallocationgroupmetrics\n      operations:\n      - method: GET\n        name: metricsapi-getallocationgroupmetrics\n        description: CAST AI Get allocation group metrics\n        call: cast-ai.metricsapi-getallocationgroupmetrics\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: cast-ai-mcp\n    transport: http\n    description: MCP adapter for CAST AI Kubernetes Cost Optimization API for AI agent use.\n    tools:\n    - name: externalclusterapi-listnodes\n      description: CAST AI List cluster nodes\n      hints:\n        readOnly: true\n     \
  \   destructive: false\n        idempotent: true\n      call: cast-ai.externalclusterapi-listnodes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: externalclusterapi-drainnode\n      description: CAST AI Drain cluster node\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cast-ai.externalclusterapi-drainnode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: externalclusterapi-deletenode\n      description: CAST AI Delete cluster node\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: cast-ai.externalclusterapi-deletenode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: policiesapi-getclusterpolicies\n      description: CAST AI Get cluster policies\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cast-ai.policiesapi-getclusterpolicies\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: policiesapi-upsertclusterpolicies\n      description: CAST AI Upsert cluster policies\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: cast-ai.policiesapi-upsertclusterpolicies\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nodetemplatesapi-listnodetemplates\n      description: CAST AI List node templates\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cast-ai.nodetemplatesapi-listnodetemplates\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nodetemplatesapi-createnodetemplate\n      description: CAST AI Create node template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: cast-ai.nodetemplatesapi-createnodetemplate\n      outputParameters:\n      - type: object\n       \
  \ mapping: $.\n    - name: nodetemplatesapi-getnodetemplate\n      description: CAST AI Get node template\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: cast-ai.nodetemplatesapi-getnodetemplate\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: nodetemplatesapi-updatenodetemplate\n      description: CAST AI Update node template\n      hints:\n        readOnly: false\n        destructive: false\n        id\n\n# --- truncated at 32 KB (42 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/cast-ai/refs/heads/main/capabilities/cast-ai-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/cast-ai/refs/heads/main/capabilities/cast-ai-capability.yaml
tags:
- Cast
- Ai
- API
tools:
- description: CAST AI List cluster nodes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: externalclusterapi-listnodes
- description: CAST AI Drain cluster node
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: externalclusterapi-drainnode
- description: CAST AI Delete cluster node
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: externalclusterapi-deletenode
- description: CAST AI Get cluster policies
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: policiesapi-getclusterpolicies
- description: CAST AI Upsert cluster policies
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: policiesapi-upsertclusterpolicies
- description: CAST AI List node templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: nodetemplatesapi-listnodetemplates
- description: CAST AI Create node template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: nodetemplatesapi-createnodetemplate
- description: CAST AI Get node template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: nodetemplatesapi-getnodetemplate
- description: CAST AI Update node template
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: nodetemplatesapi-updatenodetemplate
- description: CAST AI Delete node template
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: nodetemplatesapi-deletenodetemplate
- description: CAST AI List node configurations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: nodeconfigurationapi-listconfigurations
- description: CAST AI Create node configuration
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: nodeconfigurationapi-createconfiguration
- description: CAST AI Delete node configuration
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: nodeconfigurationapi-deleteconfiguration
- description: CAST AI Trigger rebalancing plan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: autoscalerapi-executerebalancingplan
- description: CAST AI Acknowledge cluster action
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clusteractionsapi-ackclusteraction
- description: CAST AI Ingest cluster controller logs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clusteractionsapi-ingestlogs
- description: CAST AI List workloads
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: workloadoptimizationapi-listworkloads
- description: CAST AI Get workload
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: workloadoptimizationapi-getworkload
- description: CAST AI Get agent statuses
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: workloadoptimizationapi-getorganizationagentstat
- description: CAST AI Create rebalancing schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: scheduledrebalancingapi-createrebalancingschedul
- description: CAST AI Get rebalancing schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: scheduledrebalancingapi-getrebalancingschedule
- description: CAST AI Delete rebalancing schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: scheduledrebalancingapi-deleterebalancingschedul
- description: CAST AI Get operation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsapi-getoperation
- description: CAST AI Add to blacklist
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: inventoryblacklistapi-addblacklist
- description: CAST AI Get node pricing
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: pricingapi-getnodepricing
- description: CAST AI Sync GCP billing data
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: pricingapi-syncgcpbillingapidata
- description: CAST AI Get cluster efficiency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: costreportsapi-getclusterefficiency
- description: CAST AI Get allocation group workloads efficiency
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: allocationgroupapi-getallocationgroupworkloadsef
- description: CAST AI Get best practices report filters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: insightsapi-getbestpracticesreportfilters
- description: CAST AI Get container image digests
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: insightsapi-getcontainerimagedigests
- description: CAST AI Create hibernation schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: hibernationschedulesapi-createhibernationschedul
- description: CAST AI Create or update API key settings
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: settingsapi-upsertapikeysettings
- description: CAST AI Get LLM providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: aienablerprovidersapi-getproviders
- description: CAST AI Register LLM providers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: aienablerprovidersapi-registerproviders
- description: CAST AI Get cluster metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: metricsapi-getclustermetrics
- description: CAST AI Get node metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: metricsapi-getnodemetrics
- description: CAST AI Get workload metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: metricsapi-getworkloadmetrics
- description: CAST AI Get allocation group metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: metricsapi-getallocationgroupmetrics
---
