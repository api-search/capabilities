---
categories:
- monitoring
consumed_apis: []
description: Unified monitoring and observability capability for tracking digital experience, aggregating security data, managing log forwarding, and running best practice assessments across Autonomous DEM, SASE Aggregate Monitoring, Strata Logging Service, and AIOps BPA APIs.
layout: capability
name: Palo Alto Networks Monitoring and Observability
operations:
- description: Get application experience scores.
  method: GET
  name: get-dem-application-scores
  path: /v1/dem-application-scores
- description: Get agent and endpoint scores.
  method: GET
  name: get-dem-agent-scores
  path: /v1/dem-agent-scores
- description: Get synthetic test results.
  method: GET
  name: get-dem-test-results
  path: /v1/dem-tests/{test_id}/results
- description: List monitored applications.
  method: GET
  name: list-dem-applications
  path: /v1/dem-applications
- description: List monitored agents.
  method: GET
  name: list-dem-agents
  path: /v1/dem-agents
- description: Get performance metrics.
  method: GET
  name: get-dem-metrics
  path: /v1/dem-metrics
- description: Query aggregated threat monitoring data with filters, time ranges, and grouping.
  method: POST
  name: query-threat-data
  path: /v1/monitoring/threats
- description: Query aggregated URL monitoring data with filters, time ranges, and grouping.
  method: POST
  name: query-url-data
  path: /v1/monitoring/urls
- description: Query aggregated application monitoring data with filters, time ranges, and grouping.
  method: POST
  name: query-application-data
  path: /v1/monitoring/applications
- description: Query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
  method: POST
  name: query-bandwidth-data
  path: /v1/monitoring/bandwidth
- description: Query aggregated license monitoring data with filters, time ranges, and grouping.
  method: POST
  name: query-license-data
  path: /v1/monitoring/licenses
- description: List all tenants available for monitoring.
  method: GET
  name: list-monitoring-tenants
  path: /v1/monitoring/tenants
- description: List all log forwarding profiles.
  method: GET
  name: list-log-forwarding-profiles
  path: /v1/log-forwarding-profiles
- description: Create a new log forwarding profile.
  method: POST
  name: create-log-forwarding-profile
  path: /v1/log-forwarding-profiles
- description: Get a specific log forwarding profile by ID.
  method: GET
  name: get-log-forwarding-profile
  path: /v1/log-forwarding-profiles/{profile_id}
- description: Update a specific log forwarding profile by ID.
  method: PUT
  name: update-log-forwarding-profile
  path: /v1/log-forwarding-profiles/{profile_id}
- description: Delete a specific log forwarding profile by ID.
  method: DELETE
  name: delete-log-forwarding-profile
  path: /v1/log-forwarding-profiles/{profile_id}
- description: List syslog destinations for a log forwarding profile.
  method: GET
  name: list-syslog-destinations
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/syslog
- description: Create a syslog destination for a log forwarding profile.
  method: POST
  name: create-syslog-destination
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/syslog
- description: List HTTPS destinations for a log forwarding profile.
  method: GET
  name: list-https-destinations
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/https
- description: Create an HTTPS destination for a log forwarding profile.
  method: POST
  name: create-https-destination
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/https
- description: List email destinations for a log forwarding profile.
  method: GET
  name: list-email-destinations
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/email
- description: Create an email destination for a log forwarding profile.
  method: POST
  name: create-email-destination
  path: /v1/log-forwarding-profiles/{profile_id}/destinations/email
- description: Get the status of a log forwarding profile.
  method: GET
  name: get-log-forwarding-status
  path: /v1/log-forwarding-profiles/{profile_id}/status
- description: Submit a BPA request.
  method: POST
  name: submit-bpa-request
  path: /v1/bpa-requests
- description: Check the status of a BPA request.
  method: GET
  name: get-bpa-request-status
  path: /v1/bpa-requests/{request_id}
- description: Get a BPA report.
  method: GET
  name: get-bpa-report
  path: /v1/bpa-reports/{report_id}
- description: Get BPA report check details.
  method: GET
  name: get-bpa-report-checks
  path: /v1/bpa-reports/{report_id}/checks
personas:
- description: Monitors network health, performance, and digital experience metrics.
  id: network-operations
  name: Network Operations
- description: Manages logging infrastructure, integrations, and platform automation.
  id: platform-engineer
  name: Platform Engineer
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- list monitored applications from autonomous dem.
- list https destinations
- analyzes suspicious files and samples for malware characteristics.
- query application data
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get dem agent scores
- list monitored applications
- malware researcher
- get log forwarding profile
- threat intelligence
- delete log forwarding profile
- create https destination
- get performance metrics.
- identity and access management, tenant hierarchies, and subscription management.
- create an email destination for a log forwarding profile.
- get application scores
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- list email destinations
- query aggregated license monitoring data with filters, time ranges, and grouping.
- create email destination
- manage enterprise browser policies, user sessions, and deployments.
- enterprise browser policy management and secure browsing.
- cloud security
- get test results
- create syslog destination
- proactively searches for threats and iocs across telemetry data.
- application experience scores from autonomous dem.
- sre
- list dem applications
- data loss prevention, saas security monitoring, and identity security posture.
- get a bpa report.
- get bpa report check details.
- bpa report retrieval.
- palo alto networks
- list monitoring tenants.
- list monitored agents
- designs and implements network security architectures and policies.
- list all log forwarding profiles.
- list dem agents
- best practice assessment
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- delete a specific log forwarding profile by id.
- get synthetic test results.
- update a specific log forwarding profile by id.
- compliance team
- get bpa report
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- get performance metrics
- threat hunter
- enterprise it
- log forwarding profile management.
- https destination management for log forwarding profiles.
- log forwarding profile status.
- query url data
- syslog destination management for log forwarding profiles.
- create log forwarding profile
- list email destinations for a log forwarding profile.
- network operations
- data protection analyst
- submit bpa request
- agent and endpoint scores from autonomous dem.
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- list log forwarding profiles
- check the status of a bpa request.
- mssp operator
- create an https destination for a log forwarding profile.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- submit a bpa request.
- secures ai applications with runtime scanning and vulnerability assessment.
- digital experience monitoring, log management, and best practice assessment.
- get agent scores
- update log forwarding profile
- iam admin
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- individual log forwarding profile operations.
- get bpa request status
- get application experience scores from autonomous dem.
- digital experience
- query aggregated threat monitoring data.
- conducts automated adversarial testing against ai systems and llm applications.
- firewall
- manages service accounts, roles, and access policies for platform api access.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security engineer
- browser security admin
- query bandwidth data
- query aggregated bandwidth monitoring data.
- create a new log forwarding profile.
- query aggregated application monitoring data with filters, time ranges, and grouping.
- logging
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- list syslog destinations
- compliance officer
- manages logging infrastructure, integrations, and platform automation.
- get dem metrics
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- notifications
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- investigates security incidents, triages alerts, and coordinates response actions.
- query threat data
- network architect
- query aggregated url monitoring data.
- subscription manager
- get the status of a log forwarding profile.
- cloud security posture management, compliance monitoring, and workload protection.
- saas security admin
- bpa request operations.
- firewall admin
- monitoring
- query license data
- manages multi-tenant hierarchies and service group configurations for mssps.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- red team operator
- soc analyst
- sase
- get synthetic test results from autonomous dem.
- observability
- ai security engineer
- synthetic test results from autonomous dem.
- email destination management for log forwarding profiles.
- bpa request status.
- get performance metrics from autonomous dem.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manages multi-tenant security operations at scale for managed service providers.
- query aggregated application monitoring data.
- monitors and remediates cloud security misconfigurations and compliance violations.
- cybersecurity
- performance metrics from autonomous dem.
- get log forwarding status
- submit a bpa request for a device.
- list monitored agents.
- bpa report check details.
- sase admin
- list monitored agents from autonomous dem.
- platform engineer
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security engineer
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- create a syslog destination for a log forwarding profile.
- monitored applications from autonomous dem.
- list all tenants available for monitoring.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list https destinations for a log forwarding profile.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get bpa report checks
- get agent and endpoint scores from autonomous dem.
- get dem application scores
- sd wan operator
- threat intel analyst
- get application experience scores.
- vulnerability manager
- get dem test results
- incident responder
- list monitoring tenants
- get agent and endpoint scores.
- network security
- xdr
- list monitored applications.
- monitored agents from autonomous dem.
- executes containment, eradication, and recovery actions during security incidents.
- soar
- get a specific log forwarding profile by id.
- manages enterprise browser policies and secure browsing configurations.
- designs sase and sd-wan network architectures for secure remote access.
- list syslog destinations for a log forwarding profile.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- investigates dlp incidents and manages sensitive data protection policies.
- monitors network health, performance, and digital experience metrics.
- query aggregated license monitoring data.
- firewall policy management, network objects, and cloud-native firewall configuration.
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Palo Alto Networks Monitoring and Observability\n  description: Unified monitoring and observability capability for tracking digital experience, aggregating security data,\n    managing log forwarding, and running best practice assessments across Autonomous DEM, SASE Aggregate Monitoring, Strata\n    Logging Service, and AIOps BPA APIs.\n  tags:\n  - Palo Alto Networks\n  - Monitoring\n  - Observability\n  - Logging\n  - Digital Experience\n  - Best Practice Assessment\n  - Notifications\n  created: '2026-04-16'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\ncapability:\n  consumes:\n  - type: http\n    namespace: autonomous-dem\n    baseUri: https://api.sase.paloaltonetworks.com\n    description: Palo Alto Networks Autonomous DEM API for monitoring digital experience across applications and agents.\n    authentication:\n      type: bearer\n      token: '{{PALO_ALTO_OAUTH_TOKEN}}'\n\
  \    resources:\n    - name: application-scores\n      path: /mt/monitor/adem/v1/applications/scores\n      description: Application experience scores.\n      operations:\n      - name: get-application-scores\n        method: GET\n        description: Get application experience scores.\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: scores\n\
  \          type: array\n          value: $.scores\n    - name: agent-scores\n      path: /mt/monitor/adem/v1/agents/scores\n      description: Agent and endpoint scores.\n      operations:\n      - name: get-agent-scores\n        method: GET\n        description: Get agent and endpoint scores.\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ scores\n          type: array\n          value: $.scores\n    - name: test-results\n      path: /mt/monitor/adem/v1/tests\n      description: Synthetic test results.\n      operations:\n      - name: get-test-results\n        method: GET\n        description: Get synthetic test results.\n        inputParameters:\n        - name: test_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the test.\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        outputRawFormat: json\n        outputParameters:\n        - name: results\n          type: array\n          value: $.results\n    - name: applications\n      path: /mt/monitor/adem/v1/applications\n      description: Monitored applications.\n\
  \      operations:\n      - name: list-monitored-applications\n        method: GET\n        description: List monitored applications.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: applications\n          type: array\n          value: $.applications\n    - name: agents\n      path: /mt/monitor/adem/v1/agents\n      description: Monitored agents.\n      operations:\n      - name: list-monitored-agents\n        method: GET\n        description: List monitored agents.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name:\
  \ limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        outputRawFormat: json\n        outputParameters:\n        - name: agents\n          type: array\n          value: $.agents\n    - name: metrics\n      path: /mt/monitor/adem/v1/metrics\n      description: Performance metrics.\n      operations:\n      - name: get-performance-metrics\n        method: GET\n        description: Get performance metrics.\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        - name: metric_type\n          in: query\n          type: string\n          required: false\n          description: The type of metric to retrieve.\n    \
  \    - name: granularity\n          in: query\n          type: string\n          required: false\n          description: The granularity of the metrics.\n        outputRawFormat: json\n        outputParameters:\n        - name: metrics\n          type: array\n          value: $.metrics\n  - type: http\n    namespace: sase-aggregate-monitoring\n    baseUri: https://api.sase.paloaltonetworks.com/mt/monitor/v1\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: aggregate-queries\n      path: /agg/query\n      operations:\n      - name: query-threat-data\n        method: POST\n        description: Query aggregated threat monitoring data with filters, time ranges, and grouping.\n        path: /threat\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tsg_id: '{{tools.tsg_id}}'\n        \
  \    filter: '{{tools.filter}}'\n            time_range: '{{tools.time_range}}'\n            count: '{{tools.count}}'\n            histogram: '{{tools.histogram}}'\n            group_by: '{{tools.group_by}}'\n            sort: '{{tools.sort}}'\n      - name: query-url-data\n        method: POST\n        description: Query aggregated URL monitoring data with filters, time ranges, and grouping.\n        path: /url\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tsg_id: '{{tools.tsg_id}}'\n            filter: '{{tools.filter}}'\n            time_range: '{{tools.time_range}}'\n            count: '{{tools.count}}'\n            histogram: '{{tools.histogram}}'\n            group_by: '{{tools.group_by}}'\n            sort: '{{tools.sort}}'\n      - name: query-application-data\n        method: POST\n        description: Query aggregated application\
  \ monitoring data with filters, time ranges, and grouping.\n        path: /application\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tsg_id: '{{tools.tsg_id}}'\n            filter: '{{tools.filter}}'\n            time_range: '{{tools.time_range}}'\n            count: '{{tools.count}}'\n            histogram: '{{tools.histogram}}'\n            group_by: '{{tools.group_by}}'\n            sort: '{{tools.sort}}'\n      - name: query-bandwidth-data\n        method: POST\n        description: Query aggregated bandwidth monitoring data with filters, time ranges, and grouping.\n        path: /bandwidth\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tsg_id: '{{tools.tsg_id}}'\n            filter: '{{tools.filter}}'\n\
  \            time_range: '{{tools.time_range}}'\n            count: '{{tools.count}}'\n            histogram: '{{tools.histogram}}'\n            group_by: '{{tools.group_by}}'\n            sort: '{{tools.sort}}'\n      - name: query-license-data\n        method: POST\n        description: Query aggregated license monitoring data with filters, time ranges, and grouping.\n        path: /license\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            tsg_id: '{{tools.tsg_id}}'\n            filter: '{{tools.filter}}'\n            time_range: '{{tools.time_range}}'\n            count: '{{tools.count}}'\n            histogram: '{{tools.histogram}}'\n            group_by: '{{tools.group_by}}'\n            sort: '{{tools.sort}}'\n    - name: tenants\n      path: /tenants\n      operations:\n      - name: list-monitoring-tenants\n        method: GET\n       \
  \ description: List all tenants available for monitoring.\n        inputParameters:\n        - name: tsg_id\n          in: query\n          type: string\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: strata-logging-service\n    baseUri: https://api.sase.paloaltonetworks.com/logging-service/v1\n    description: Strata Logging Service API for managing log forwarding profiles and their syslog, HTTPS, and email destinations.\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: log-forwarding-profiles\n      path: /log-forwarding-profiles\n      operations:\n      - name: list-log-forwarding-profiles\n        method: GET\n        description: List all log forwarding profiles.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n\
  \        - name: limit\n          in: query\n          type: integer\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-log-forwarding-profile\n        method: POST\n        description: Create a new log forwarding profile.\n        inputParameters:\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: log_types\n          in: body\n          type: object\n          required: true\n        - name: description\n          in: body\n          type: string\n          required: false\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            log_types:\
  \ '{{tools.log_types}}'\n            description: '{{tools.description}}'\n            enabled: '{{tools.enabled}}'\n    - name: log-forwarding-profile\n      path: /log-forwarding-profiles/{profile_id}\n      operations:\n      - name: get-log-forwarding-profile\n        method: GET\n        description: Get a specific log forwarding profile by ID.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: update-log-forwarding-profile\n        method: PUT\n        description: Update a specific log forwarding profile by ID.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n\
  \          type: json\n          data: {}\n      - name: delete-log-forwarding-profile\n        method: DELETE\n        description: Delete a specific log forwarding profile by ID.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: syslog-destinations\n      path: /log-forwarding-profiles/{profile_id}/destinations/syslog\n      operations:\n      - name: list-syslog-destinations\n        method: GET\n        description: List syslog destinations for a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-syslog-destination\n        method:\
  \ POST\n        description: Create a syslog destination for a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: server\n          in: body\n          type: string\n          required: true\n        - name: port\n          in: body\n          type: integer\n          required: true\n        - name: protocol\n          in: body\n          type: string\n          required: true\n        - name: format\n          in: body\n          type: string\n          required: true\n        - name: facility\n          in: body\n          type: string\n          required: true\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            server: '{{tools.server}}'\n            port: '{{tools.port}}'\n            protocol: '{{tools.protocol}}'\n            format: '{{tools.format}}'\n            facility: '{{tools.facility}}'\n            enabled: '{{tools.enabled}}'\n    - name: https-destinations\n      path: /log-forwarding-profiles/{profile_id}/destinations/https\n      operations:\n      - name: list-https-destinations\n        method: GET\n        description: List HTTPS destinations for a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-https-destination\n        method: POST\n        description: Create an HTTPS destination for a log forwarding profile.\n        inputParameters:\n\
  \        - name: profile_id\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: uri\n          in: body\n          type: string\n          required: true\n        - name: http_method\n          in: body\n          type: string\n          required: true\n        - name: headers\n          in: body\n          type: object\n          required: false\n        - name: tls_verify\n          in: body\n          type: boolean\n          required: false\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            uri: '{{tools.uri}}'\n            http_method: '{{tools.http_method}}'\n            headers: '{{tools.headers}}'\n\
  \            tls_verify: '{{tools.tls_verify}}'\n            enabled: '{{tools.enabled}}'\n    - name: email-destinations\n      path: /log-forwarding-profiles/{profile_id}/destinations/email\n      operations:\n      - name: list-email-destinations\n        method: GET\n        description: List email destinations for a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-email-destination\n        method: POST\n        description: Create an email destination for a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: body\n          type: string\n          required: true\n        - name: gateway\n          in: body\n\
  \          type: string\n          required: true\n        - name: from\n          in: body\n          type: string\n          required: true\n        - name: to\n          in: body\n          type: string\n          required: true\n        - name: and_also_to\n          in: body\n          type: string\n          required: false\n        - name: enabled\n          in: body\n          type: boolean\n          required: false\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            name: '{{tools.name}}'\n            gateway: '{{tools.gateway}}'\n            from: '{{tools.from}}'\n            to: '{{tools.to}}'\n            and_also_to: '{{tools.and_also_to}}'\n            enabled: '{{tools.enabled}}'\n    - name: log-forwarding-status\n      path: /log-forwarding-profiles/{profile_id}/status\n      operations:\n      - name: get-log-forwarding-status\n\
  \        method: GET\n        description: Get the status of a log forwarding profile.\n        inputParameters:\n        - name: profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  - type: http\n    namespace: aiops-ngfw-bpa\n    baseUri: https://api.sase.paloaltonetworks.com/aiops/bpa\n    description: Palo Alto Networks AIOps for NGFW BPA API for submitting and retrieving best practice assessment requests\n      and reports.\n    authentication:\n      type: bearer\n      token: '{{PALO_ALTO_OAUTH_TOKEN}}'\n    resources:\n    - name: requests\n      path: /requests\n      description: BPA request operations.\n      operations:\n      - name: submit-bpa-request\n        method: POST\n        description: Submit a BPA request.\n        inputParameters:\n        - name: device_serial\n          in: body\n          type: string\n\
  \          required: true\n          description: The serial number of the device to assess.\n        - name: config_type\n          in: body\n          type: string\n          required: true\n          description: The configuration type for the BPA request.\n        outputRawFormat: json\n        outputParameters:\n        - name: request_id\n          type: string\n          value: $.request_id\n        - name: status\n          type: string\n          value: $.status\n        body:\n          type: json\n          data:\n            device_serial: '{{tools.device_serial}}'\n            config_type: '{{tools.config_type}}'\n      - name: get-bpa-request-status\n        method: GET\n        description: Check the status of a BPA request.\n        inputParameters:\n        - name: request_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the BPA request.\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ request_id\n          type: string\n          value: $.request_id\n        - name: status\n          type: string\n          value: $.status\n    - name: reports\n      path: /reports\n      description: BPA report operations.\n      operations:\n      - name: get-bpa-report\n        method: GET\n        description: Get a BPA report.\n        inputParameters:\n        - name: report_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the BPA report.\n        outputRawFormat: json\n        outputParameters:\n        - name: report\n          type: object\n          value: $.\n      - name: get-bpa-report-checks\n        method: GET\n        description: Get BPA report check details.\n        inputParameters:\n        - name: report_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the BPA report.\n        outputRawFormat: json\n        outputParameters:\n        - name: checks\n\
  \          type: array\n          value: $.checks\n  - type: http\n    namespace: sase-multitenant-notifications\n    baseUri: https://api.sase.paloaltonetworks.com\n    authentication:\n      type: bearer\n      token: '{{env.PALO_ALTO_SASE_ACCESS_TOKEN}}'\n    resources:\n    - name: notification-profiles\n      path: /api/cloud/2.0/agg/notifications/profiles\n      operations:\n      - name: list-notification-profiles\n        method: GET\n        description: List notification profiles associated with the current tenant.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: create-notification-profile\n        method: POST\n        description: Create a new notification profile with inputs and output channels.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n     \
  \       profileName: '{{tools.profileName}}'\n            opState: '{{tools.opState}}'\n            description: '{{tools.description}}'\n            tenantList: '{{tools.tenantList}}'\n            notifTypeDetails: '{{tools.notifTypeDetails}}'\n            notifChannels: '{{tools.notifChannels}}'\n      - name: get-notification-profile\n        method: GET\n        description: Get a specific notification profile by ID.\n        path: /{notification_profile_id}\n        inputParameters:\n        - name: notification_profile_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-notification-profile\n        method: DELETE\n        description: Delete a notification profile by ID.\n        path: /{notification_profile_id}\n        inputParameters:\n        - name: notification_profile_id\n          in: path\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: notification-profile-opstate\n      path: /api/cloud/2.0/agg/notifications/profiles/opstate\n      operations:\n      - name: update-profile-opstate\n        method: PUT\n        description: Enable or disable a notification profile.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            profileId: '{{tools.profileId}}'\n            opState: '{{tools.opState}}'\n    - name: notification-profile-types\n      path: /api/cloud/2.0/agg/notifications/profiles/types\n      operations:\n      - name: get-notification-types\n        method: GET\n        description: Retrieve valid notification types, categories, and sub-categories.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: notification-webhook-test\n      path: /api/cloud/2.0/agg/notifications/profiles/webhook/test\n      operations:\n      - name: test-webhook-connectivity\n        method: POST\n        description: Test webhook connectivity from the notification service.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            urls: '{{tools.urls}}'\n            auth_type: '{{tools.auth_type}}'\n            token: '{{tools.token}}'\n    - name: notification-profile-retry\n      path: /api/cloud/2.0/agg/notifications/profiles/retryOp\n      operations:\n      - name: retry-profile-operation\n        method: POST\n        description: Retry incident profile push to selected child tenants.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n        body:\n          type: json\n          data:\n            profileId: '{{tools.profileId}}'\n            tenantList: '{{tools.tenantList}}'\n    - name: notifications\n      path: /api/cloud/2.0/agg/notifications/list\n      operations:\n      - name: list-notifications\n        method: POST\n        description: List notifications for all child tenants with filtering and sorting.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filters: '{{tools.filters}}'\n            sortByList: '{{tools.sortByList}}'\n            page: '{{tools.page}}'\n    - name: notification-count\n      path: /api/cloud/2.0/agg/notifications/list/count\n      operations:\n      - name: get-notification-count\n        method: POST\n        description: Get notification count filtered by state or type.\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            filters: '{{tools.filters}}'\n            sortByList: '{{tools.sortByList}}'\n    - name: notification-state\n      path: /api/cloud/2.0/agg/notifications/list/state\n      operations:\n      - name: set-notification-read-state\n        method: POST\n        description: Set read state to READ or UNREAD for specified notifications.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            notifIds: '{{tools.notifIds}}'\n            readState: '{{tools.readState}}'\n      - name: get-notification-read-state\n        method: GET\n        description: Get read state of a specific notification.\n        path: /{notification_id}\n        inputParameters:\n        - name: notification_id\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8087\n    namespace: monitoring-and-observability-api\n    description: Unified REST API for monitoring and observability workflows across Autonomous DEM, SASE Aggregate Monitoring,\n      Strata Logging Service, and AIOps BPA.\n    resources:\n    - path: /v1/dem-application-scores\n      name: dem-application-scores\n      description: Application experience scores from Autonomous DEM.\n      operations:\n      - method: GET\n        name: get-dem-application-scores\n        description: Get application experience scores.\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n\
  \          required: false\n          description: End time for the query range.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        call: autonomous-dem.get-application-scores\n        with:\n          start_time: rest.start_time\n          end_time: rest.end_time\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/dem-agent-scores\n      name: dem-agent-scores\n      description: Agent and endpoint scores from Autonomous DEM.\n      operations:\n      - method: GET\n        name: get-dem-agent-scores\n        description: Get agent and endpoint scores.\n        inputParameters:\n        - name: start_time\n          in: query\n          type:\
  \ string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        call: autonomous-dem.get-agent-scores\n        with:\n          start_time: rest.start_time\n          end_time: rest.end_time\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/dem-tests/{test_id}/results\n      name: dem-test-results\n      description: Synthetic test results from Autonomous DEM.\n      operations:\n      - method: GET\n        name:\
  \ get-dem-test-results\n        description: Get synthetic test results.\n        inputParameters:\n        - name: test_id\n          in: path\n          type: string\n          required: true\n          description: The ID of the test.\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n          type: string\n          required: false\n          description: End time for the query range.\n        call: autonomous-dem.get-test-results\n        with:\n          test_id: rest.test_id\n          start_time: rest.start_time\n          end_time: rest.end_time\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/dem-applications\n      name: dem-applications\n      description: Monitored applications from Autonomous DEM.\n      operations:\n      - method: GET\n        name: list-dem-applications\n     \
  \   description: List monitored applications.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        call: autonomous-dem.list-monitored-applications\n        with:\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/dem-agents\n      name: dem-agents\n      description: Monitored agents from Autonomous DEM.\n      operations:\n      - method: GET\n        name: list-dem-agents\n        description: List monitored agents.\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset.\n        - name: limit\n        \
  \  in: query\n          type: integer\n          required: false\n          description: Maximum number of results to return.\n        call: autonomous-dem.list-monitored-agents\n        with:\n          offset: rest.offset\n          limit: rest.limit\n        outputParameters:\n        - type: array\n          mapping: $.\n    - path: /v1/dem-metrics\n      name: dem-metrics\n      description: Performance metrics from Autonomous DEM.\n      operations:\n      - method: GET\n        name: get-dem-metrics\n        description: Get performance metrics.\n        inputParameters:\n        - name: start_time\n          in: query\n          type: string\n          required: false\n          description: Start time for the query range.\n        - name: end_time\n          in: query\n   \n\n# --- truncated at 32 KB (78 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/monitoring-and-observability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/monitoring-and-observability.yaml
tags:
- Palo Alto Networks
- Monitoring
- Observability
- Logging
- Digital Experience
- Best Practice Assessment
- Notifications
tools:
- description: Get application experience scores from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-application-scores
- description: Get agent and endpoint scores from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-agent-scores
- description: Get synthetic test results from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-test-results
- description: List monitored applications from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-monitored-applications
- description: List monitored agents from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-monitored-agents
- description: Get performance metrics from Autonomous DEM.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-performance-metrics
- description: Query aggregated threat monitoring data with filters, time ranges, and grouping.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-threat-data
- description: Query aggregated URL monitoring data with filters, time ranges, and grouping.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-url-data
- description: Query aggregated application monitoring data with filters, time ranges, and grouping.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-application-data
- description: Query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-bandwidth-data
- description: Query aggregated license monitoring data with filters, time ranges, and grouping.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: query-license-data
- description: List all tenants available for monitoring.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-monitoring-tenants
- description: List all log forwarding profiles.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-log-forwarding-profiles
- description: Create a new log forwarding profile.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-log-forwarding-profile
- description: Get a specific log forwarding profile by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-log-forwarding-profile
- description: Update a specific log forwarding profile by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: false
  name: update-log-forwarding-profile
- description: Delete a specific log forwarding profile by ID.
  hints:
    destructive: true
    idempotent: true
    openWorld: true
    readOnly: false
  name: delete-log-forwarding-profile
- description: List syslog destinations for a log forwarding profile.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-syslog-destinations
- description: Create a syslog destination for a log forwarding profile.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-syslog-destination
- description: List HTTPS destinations for a log forwarding profile.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-https-destinations
- description: Create an HTTPS destination for a log forwarding profile.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-https-destination
- description: List email destinations for a log forwarding profile.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-email-destinations
- description: Create an email destination for a log forwarding profile.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: create-email-destination
- description: Get the status of a log forwarding profile.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-log-forwarding-status
- description: Submit a BPA request for a device.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-bpa-request
- description: Check the status of a BPA request.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-bpa-request-status
- description: Get a BPA report.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-bpa-report
- description: Get BPA report check details.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-bpa-report-checks
---
