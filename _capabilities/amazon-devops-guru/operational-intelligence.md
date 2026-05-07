---
categories: []
consumed_apis: []
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
- amazon devops guru
- get resource collection
- devops
- list events
- get remediation recommendations for an insight
- get cost estimation
- DevOps Engineer
- add or remove cloudformation stacks from the devops guru monitoring scope
- get the estimated monthly cost for devops guru monitoring your resources
- remediation recommendations
- machine learning powered operational insights
- Site Reliability Engineer
- get detailed information about a specific anomaly
- get account health with open insight counts
- list notification channels
- search insights
- anomalies linked to an insight
- account-level operational health
- search for insights with custom filters on severity, status, and service collection
- devops engineer using ml insights to proactively identify and resolve operational issues
- check the integration status with opscenter, cloudwatch logs, and other aws services
- get an overview of open and closed insights for a specified time period
- add an sns notification channel
- list sns notification channels configured for devops guru alerts
- list anomalies associated with an insight
- machine learning
- get detailed information about a specific insight including its severity and resource details
- list anomalies for insight
- individual insight details
- resource coverage configuration
- alert notification configuration
- ml-powered detection and analysis of operational anomalies
- update resource collection
- describe account health
- describe account overview
- get the collection of aws resources that devops guru is currently monitoring
- get actionable recommendations to resolve a specific insight
- list machine learning powered operational insights by status (ongoing, closed) and type (proactive, reactive)
- list anomalies associated with a specific insight to understand the root cause
- list anomalies
- anomaly detection
- list insights
- site reliability engineering
- operational intelligence
- search insights with filters
- list proactive and reactive insights
- aws
- list events during an insight's time range
- describe insight
- add notification channel
- describe anomaly
- list cloudwatch events correlated with an insight during its time window
- describe service integration
- get details about a specific insight
- end-to-end operational intelligence workflow for devops engineers and sres
- configuring resource coverage and notification channels
- events correlated with insights
- sre using devops guru to maintain service level objectives and reduce mttr
- update which resources devops guru monitors
- list recommendations
- get the resource collection devops guru monitors
- get the current health of the account including counts of open proactive and reactive insights
slug: operational-intelligence
source_filename: operational-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon DevOps Guru Operational Intelligence\n  description: Workflow capability for DevOps engineers and SREs to monitor application health, investigate anomalies, follow\n    remediation recommendations, and configure operational intelligence coverage using Amazon DevOps Guru's machine learning\n    powered insights.\n  tags:\n  - Amazon DevOps Guru\n  - Operational Intelligence\n  - Anomaly Detection\n  - Site Reliability Engineering\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: devops-guru\n    baseUri: https://devops-guru.us-east-1.amazonaws.com\n    description: Amazon DevOps Guru REST API for operational intelligence.\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_ACCESS_KEY_ID}}'\n\
  \      placement: header\n    resources:\n    - name: insights\n      path: /insights\n      description: Operational insights about application anomalies\n      operations:\n      - name: list-insights\n        method: POST\n        description: Lists insights with filtering by status and type\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: search-insights\n        method: POST\n        description: Searches for insights on the account with optional filtering\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-insight\n        method: GET\n        description: Returns details about an insight\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: anomalies\n      path: /anomalies\n      description: Anomalies detected\
  \ in application behavior\n      operations:\n      - name: list-anomalies-for-insight\n        method: POST\n        description: Lists anomalies associated with a specific insight\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-anomaly\n        method: GET\n        description: Returns details about an anomaly\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recommendations\n      path: /recommendations\n      description: Recommendations for remediating issues\n      operations:\n      - name: list-recommendations\n        method: POST\n        description: Returns a list of recommendations for each insight\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: events\n      path: /events\n      description:\
  \ Events that occurred during an insight\n      operations:\n      - name: list-events\n        method: POST\n        description: Returns a list of events during an insight time range\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: resource-collection\n      path: /resource-collections\n      description: Resource collection configuration\n      operations:\n      - name: get-resource-collection\n        method: GET\n        description: Returns the AWS resource collection configuration\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-resource-collection\n        method: PUT\n        description: Updates the collection of resources that DevOps Guru analyzes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: service-integration\n\
  \      path: /service-integrations\n      description: AWS service integrations configuration\n      operations:\n      - name: describe-service-integration\n        method: GET\n        description: Returns the integration status with other AWS services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-service-integration\n        method: PUT\n        description: Enables or disables integration with AWS services\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notification-channels\n      path: /channels\n      description: Notification channel configuration\n      operations:\n      - name: list-notification-channels\n        method: GET\n        description: Lists all notification channels configured for DevOps Guru\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: add-notification-channel\n        method: PUT\n        description: Adds a notification channel to DevOps Guru\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: remove-notification-channel\n        method: DELETE\n        description: Removes a notification channel from DevOps Guru\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cost-estimation\n      path: /cost-estimation\n      description: Cost estimation for DevOps Guru analysis\n      operations:\n      - name: get-cost-estimation\n        method: GET\n        description: Returns an estimate of the monthly cost for DevOps Guru\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: start-cost-estimation\n\
  \        method: PUT\n        description: Starts the analysis of your AWS resources for cost estimation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: account-health\n      path: /accounts/health\n      description: Account health overview\n      operations:\n      - name: describe-account-health\n        method: GET\n        description: Returns the number of open reactive and proactive insights\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: describe-account-overview\n        method: POST\n        description: Returns the number of open and closed insights in a specified time period\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: operational-intelligence-api\n  \
  \  description: Unified REST API for Amazon DevOps Guru operational intelligence workflows.\n    resources:\n    - path: /v1/account/health\n      name: account-health\n      description: Account-level operational health\n      operations:\n      - method: GET\n        name: describe-account-health\n        description: Get account health with open insight counts\n        call: devops-guru.describe-account-health\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights\n      name: insights\n      description: Machine learning powered operational insights\n      operations:\n      - method: GET\n        name: list-insights\n        description: List proactive and reactive insights\n        call: devops-guru.list-insights\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: search-insights\n        description: Search insights with filters\n        call: devops-guru.search-insights\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights/{insightId}\n      name: insight\n      description: Individual insight details\n      operations:\n      - method: GET\n        name: describe-insight\n        description: Get details about a specific insight\n        call: devops-guru.describe-insight\n        with:\n          Id: rest.insightId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/insights/{insightId}/anomalies\n      name: anomalies\n      description: Anomalies linked to an insight\n      operations:\n      - method: GET\n        name: list-anomalies\n        description: List anomalies associated with an insight\n        call: devops-guru.list-anomalies-for-insight\n        with:\n          InsightId: rest.insightId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recommendations\n      name: recommendations\n      description: Remediation\
  \ recommendations\n      operations:\n      - method: GET\n        name: list-recommendations\n        description: Get remediation recommendations for an insight\n        call: devops-guru.list-recommendations\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/events\n      name: events\n      description: Events correlated with insights\n      operations:\n      - method: GET\n        name: list-events\n        description: List events during an insight's time range\n        call: devops-guru.list-events\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/resource-collections\n      name: resource-collections\n      description: Resource coverage configuration\n      operations:\n      - method: GET\n        name: get-resource-collection\n        description: Get the resource collection DevOps Guru monitors\n        call: devops-guru.get-resource-collection\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n      - method: PUT\n        name: update-resource-collection\n        description: Update which resources DevOps Guru monitors\n        call: devops-guru.update-resource-collection\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/notification-channels\n      name: notification-channels\n      description: Alert notification configuration\n      operations:\n      - method: GET\n        name: list-notification-channels\n        description: List notification channels\n        call: devops-guru.list-notification-channels\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: PUT\n        name: add-notification-channel\n        description: Add an SNS notification channel\n        call: devops-guru.add-notification-channel\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: operational-intelligence-mcp\n    transport: http\n\
  \    description: MCP server for AI-assisted operational intelligence and anomaly investigation with Amazon DevOps Guru.\n    tools:\n    - name: describe-account-health\n      description: Get the current health of the account including counts of open proactive and reactive insights\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.describe-account-health\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-account-overview\n      description: Get an overview of open and closed insights for a specified time period\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.describe-account-overview\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-insights\n      description: List machine learning powered operational insights by status (ongoing, closed) and type (proactive, reactive)\n      hints:\n        readOnly: true\n        openWorld: true\n\
  \      call: devops-guru.list-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: search-insights\n      description: Search for insights with custom filters on severity, status, and service collection\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devops-guru.search-insights\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-insight\n      description: Get detailed information about a specific insight including its severity and resource details\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.describe-insight\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-anomalies-for-insight\n      description: List anomalies associated with a specific insight to understand the root cause\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devops-guru.list-anomalies-for-insight\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: describe-anomaly\n      description: Get detailed information about a specific anomaly\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.describe-anomaly\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recommendations\n      description: Get actionable recommendations to resolve a specific insight\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devops-guru.list-recommendations\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-events\n      description: List CloudWatch Events correlated with an insight during its time window\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devops-guru.list-events\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-resource-collection\n      description: Get the collection of AWS resources that DevOps\
  \ Guru is currently monitoring\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.get-resource-collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: update-resource-collection\n      description: Add or remove CloudFormation stacks from the DevOps Guru monitoring scope\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: devops-guru.update-resource-collection\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-service-integration\n      description: Check the integration status with OpsCenter, CloudWatch Logs, and other AWS services\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.describe-service-integration\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-notification-channels\n      description: List SNS notification channels configured for DevOps\
  \ Guru alerts\n      hints:\n        readOnly: true\n        openWorld: true\n      call: devops-guru.list-notification-channels\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-cost-estimation\n      description: Get the estimated monthly cost for DevOps Guru monitoring your resources\n      hints:\n        readOnly: true\n        openWorld: false\n      call: devops-guru.get-cost-estimation\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-devops-guru/refs/heads/main/capabilities/operational-intelligence.yaml
tags:
- Amazon DevOps Guru
- Operational Intelligence
- Anomaly Detection
- Site Reliability Engineering
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
