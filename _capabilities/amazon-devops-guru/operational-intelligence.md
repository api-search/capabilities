---
categories: []
consumed_apis:
- devops-guru
description: Workflow capability for DevOps engineers and SREs to monitor application health, investigate anomalies, follow remediation recommendations, and configure operational intelligence coverage using Amazon DevOps Guru's machine learning powered insights.
layout: capability
name: Amazon DevOps Guru Operational Intelligence
operations:
- description: Get account health with open insight counts
  method: GET
  name: describe-account-health
  path: /v1/account/health
- description: List proactive and reactive insights
  method: GET
  name: list-insights
  path: /v1/insights
- description: Search insights with filters
  method: POST
  name: search-insights
  path: /v1/insights
- description: Get details about a specific insight
  method: GET
  name: describe-insight
  path: /v1/insights/{insightId}
- description: List anomalies associated with an insight
  method: GET
  name: list-anomalies
  path: /v1/insights/{insightId}/anomalies
- description: Get remediation recommendations for an insight
  method: GET
  name: list-recommendations
  path: /v1/recommendations
- description: List events during an insight's time range
  method: GET
  name: list-events
  path: /v1/events
- description: Get the resource collection DevOps Guru monitors
  method: GET
  name: get-resource-collection
  path: /v1/resource-collections
- description: Update which resources DevOps Guru monitors
  method: PUT
  name: update-resource-collection
  path: /v1/resource-collections
- description: List notification channels
  method: GET
  name: list-notification-channels
  path: /v1/notification-channels
- description: Add an SNS notification channel
  method: PUT
  name: add-notification-channel
  path: /v1/notification-channels
personas: []
provider_name: Amazon DevOps Guru
provider_slug: amazon-devops-guru
search_terms:
- configuring resource coverage and notification channels
- describe insight
- list events
- get resource collection
- update resource collection
- list events during an insight's time range
- list anomalies
- list machine learning powered operational insights by status (ongoing, closed) and type (proactive, reactive)
- get the current health of the account including counts of open proactive and reactive insights
- search for insights with custom filters on severity, status, and service collection
- list insights
- sre using devops guru to maintain service level objectives and reduce mttr
- check the integration status with opscenter, cloudwatch logs, and other aws services
- list recommendations
- list anomalies associated with an insight
- amazon devops guru
- search insights
- describe anomaly
- ml-powered detection and analysis of operational anomalies
- get details about a specific insight
- machine learning
- get detailed information about a specific anomaly
- search insights with filters
- resource coverage configuration
- list proactive and reactive insights
- describe account health
- list notification channels
- account-level operational health
- get an overview of open and closed insights for a specified time period
- get actionable recommendations to resolve a specific insight
- get the collection of aws resources that devops guru is currently monitoring
- get the estimated monthly cost for devops guru monitoring your resources
- add or remove cloudformation stacks from the devops guru monitoring scope
- site reliability engineering
- get cost estimation
- DevOps Engineer
- get the resource collection devops guru monitors
- update which resources devops guru monitors
- devops
- aws
- add notification channel
- get detailed information about a specific insight including its severity and resource details
- operational intelligence
- alert notification configuration
- end-to-end operational intelligence workflow for devops engineers and sres
- Site Reliability Engineer
- describe service integration
- devops engineer using ml insights to proactively identify and resolve operational issues
- get account health with open insight counts
- list anomalies associated with a specific insight to understand the root cause
- describe account overview
- remediation recommendations
- individual insight details
- anomaly detection
- add an sns notification channel
- list anomalies for insight
- events correlated with insights
- list sns notification channels configured for devops guru alerts
- machine learning powered operational insights
- list cloudwatch events correlated with an insight during its time window
- get remediation recommendations for an insight
- anomalies linked to an insight
slug: operational-intelligence
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon DevOps Guru Operational Intelligence\n  description: >-\n    Workflow capability for DevOps engineers and SREs to monitor application health,\n    investigate anomalies, follow remediation recommendations, and configure\n    operational intelligence coverage using Amazon DevOps Guru's machine learning\n    powered insights.\n  tags:\n    - Amazon DevOps Guru\n    - Operational Intelligence\n    - Anomaly Detection\n    - Site Reliability Engineering\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: devops-guru\n      location: ./shared/devops-guru-api.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: operational-intelligence-api\n      description: Unified REST API for Amazon DevOps\
  \ Guru operational intelligence workflows.\n      resources:\n        - path: /v1/account/health\n          name: account-health\n          description: Account-level operational health\n          operations:\n            - method: GET\n              name: describe-account-health\n              description: Get account health with open insight counts\n              call: \"devops-guru.describe-account-health\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/insights\n          name: insights\n          description: Machine learning powered operational insights\n          operations:\n            - method: GET\n              name: list-insights\n              description: List proactive and reactive insights\n              call: \"devops-guru.list-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: search-insights\n\
  \              description: Search insights with filters\n              call: \"devops-guru.search-insights\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/insights/{insightId}\n          name: insight\n          description: Individual insight details\n          operations:\n            - method: GET\n              name: describe-insight\n              description: Get details about a specific insight\n              call: \"devops-guru.describe-insight\"\n              with:\n                Id: \"rest.insightId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/insights/{insightId}/anomalies\n          name: anomalies\n          description: Anomalies linked to an insight\n          operations:\n            - method: GET\n              name: list-anomalies\n              description: List anomalies associated with an insight\n        \
  \      call: \"devops-guru.list-anomalies-for-insight\"\n              with:\n                InsightId: \"rest.insightId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/recommendations\n          name: recommendations\n          description: Remediation recommendations\n          operations:\n            - method: GET\n              name: list-recommendations\n              description: Get remediation recommendations for an insight\n              call: \"devops-guru.list-recommendations\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/events\n          name: events\n          description: Events correlated with insights\n          operations:\n            - method: GET\n              name: list-events\n              description: List events during an insight's time range\n              call: \"devops-guru.list-events\"\n            \
  \  outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/resource-collections\n          name: resource-collections\n          description: Resource coverage configuration\n          operations:\n            - method: GET\n              name: get-resource-collection\n              description: Get the resource collection DevOps Guru monitors\n              call: \"devops-guru.get-resource-collection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-resource-collection\n              description: Update which resources DevOps Guru monitors\n              call: \"devops-guru.update-resource-collection\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/notification-channels\n          name: notification-channels\n          description: Alert notification configuration\n\
  \          operations:\n            - method: GET\n              name: list-notification-channels\n              description: List notification channels\n              call: \"devops-guru.list-notification-channels\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: add-notification-channel\n              description: Add an SNS notification channel\n              call: \"devops-guru.add-notification-channel\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: operational-intelligence-mcp\n      transport: http\n      description: MCP server for AI-assisted operational intelligence and anomaly investigation with Amazon DevOps Guru.\n      tools:\n        - name: describe-account-health\n          description: Get the current health of the account including counts of open proactive and reactive\
  \ insights\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.describe-account-health\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-account-overview\n          description: Get an overview of open and closed insights for a specified time period\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.describe-account-overview\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-insights\n          description: List machine learning powered operational insights by status (ongoing, closed) and type (proactive, reactive)\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.list-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: search-insights\n\
  \          description: Search for insights with custom filters on severity, status, and service collection\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.search-insights\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-insight\n          description: Get detailed information about a specific insight including its severity and resource details\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.describe-insight\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-anomalies-for-insight\n          description: List anomalies associated with a specific insight to understand the root cause\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.list-anomalies-for-insight\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: describe-anomaly\n          description: Get detailed information about a specific anomaly\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.describe-anomaly\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-recommendations\n          description: Get actionable recommendations to resolve a specific insight\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.list-recommendations\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-events\n          description: List CloudWatch Events correlated with an insight during its time window\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.list-events\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: get-resource-collection\n          description: Get the collection of AWS resources that DevOps Guru is currently monitoring\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.get-resource-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-resource-collection\n          description: Add or remove CloudFormation stacks from the DevOps Guru monitoring scope\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n          call: \"devops-guru.update-resource-collection\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: describe-service-integration\n          description: Check the integration status with OpsCenter, CloudWatch Logs, and other AWS services\n          hints:\n\
  \            readOnly: true\n            openWorld: false\n          call: \"devops-guru.describe-service-integration\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-notification-channels\n          description: List SNS notification channels configured for DevOps Guru alerts\n          hints:\n            readOnly: true\n            openWorld: true\n          call: \"devops-guru.list-notification-channels\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-cost-estimation\n          description: Get the estimated monthly cost for DevOps Guru monitoring your resources\n          hints:\n            readOnly: true\n            openWorld: false\n          call: \"devops-guru.get-cost-estimation\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-devops-guru/refs/heads/main/capabilities/operational-intelligence.yaml
tags:
- Amazon DevOps Guru
- Operational Intelligence
- Anomaly Detection
- Site Reliability Engineering
- AWS
tools:
- description: Get the current health of the account including counts of open proactive and reactive insights
  hints:
    openWorld: false
    readOnly: true
  name: describe-account-health
- description: Get an overview of open and closed insights for a specified time period
  hints:
    openWorld: false
    readOnly: true
  name: describe-account-overview
- description: List machine learning powered operational insights by status (ongoing, closed) and type (proactive, reactive)
  hints:
    openWorld: true
    readOnly: true
  name: list-insights
- description: Search for insights with custom filters on severity, status, and service collection
  hints:
    openWorld: true
    readOnly: true
  name: search-insights
- description: Get detailed information about a specific insight including its severity and resource details
  hints:
    openWorld: false
    readOnly: true
  name: describe-insight
- description: List anomalies associated with a specific insight to understand the root cause
  hints:
    openWorld: true
    readOnly: true
  name: list-anomalies-for-insight
- description: Get detailed information about a specific anomaly
  hints:
    openWorld: false
    readOnly: true
  name: describe-anomaly
- description: Get actionable recommendations to resolve a specific insight
  hints:
    openWorld: true
    readOnly: true
  name: list-recommendations
- description: List CloudWatch Events correlated with an insight during its time window
  hints:
    openWorld: true
    readOnly: true
  name: list-events
- description: Get the collection of AWS resources that DevOps Guru is currently monitoring
  hints:
    openWorld: false
    readOnly: true
  name: get-resource-collection
- description: Add or remove CloudFormation stacks from the DevOps Guru monitoring scope
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: update-resource-collection
- description: Check the integration status with OpsCenter, CloudWatch Logs, and other AWS services
  hints:
    openWorld: false
    readOnly: true
  name: describe-service-integration
- description: List SNS notification channels configured for DevOps Guru alerts
  hints:
    openWorld: true
    readOnly: true
  name: list-notification-channels
- description: Get the estimated monthly cost for DevOps Guru monitoring your resources
  hints:
    openWorld: false
    readOnly: true
  name: get-cost-estimation
---
