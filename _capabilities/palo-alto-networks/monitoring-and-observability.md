---
categories:
- monitoring
consumed_apis:
- autonomous-dem
- sase-aggregate-monitoring
- strata-logging-service
- aiops-ngfw-bpa
- sase-multitenant-notifications
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
- network security engineer
- get the status of a log forwarding profile.
- cloud security
- create a new log forwarding profile.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- sase
- get a specific log forwarding profile by id.
- designs and implements network security architectures and policies.
- list monitored applications
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- list monitored applications from autonomous dem.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- list email destinations for a log forwarding profile.
- bpa request status.
- https destination management for log forwarding profiles.
- get performance metrics
- get performance metrics.
- soc analyst
- sre
- network security
- data loss prevention, saas security monitoring, and identity security posture.
- create an https destination for a log forwarding profile.
- notifications
- query url data
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- syslog destination management for log forwarding profiles.
- monitored agents from autonomous dem.
- list monitored agents from autonomous dem.
- query aggregated bandwidth monitoring data.
- list dem agents
- list https destinations
- get bpa request status
- manages enterprise browser policies and secure browsing configurations.
- logging
- list email destinations
- manages service accounts, roles, and access policies for platform api access.
- researches threat actors, malware campaigns, and vulnerability trends.
- get dem test results
- create email destination
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- query aggregated license monitoring data with filters, time ranges, and grouping.
- cybersecurity
- application experience scores from autonomous dem.
- manages multi-tenant security operations at scale for managed service providers.
- query aggregated threat monitoring data.
- best practice assessment
- update a specific log forwarding profile by id.
- get log forwarding status
- conducts automated adversarial testing against ai systems and llm applications.
- proactively searches for threats and iocs across telemetry data.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get performance metrics from autonomous dem.
- log forwarding profile status.
- submit bpa request
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- sd wan operator
- monitors and remediates cloud security misconfigurations and compliance violations.
- observability
- list monitored agents.
- data protection analyst
- analyzes suspicious files and samples for malware characteristics.
- get bpa report check details.
- compliance officer
- xdr
- get bpa report checks
- network architect
- create syslog destination
- list all log forwarding profiles.
- incident responder
- get agent scores
- email destination management for log forwarding profiles.
- investigates security incidents, triages alerts, and coordinates response actions.
- threat intel analyst
- ai runtime security scanning and automated red teaming for ai applications.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- bpa request operations.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- investigates dlp incidents and manages sensitive data protection policies.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- delete log forwarding profile
- performance metrics from autonomous dem.
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get application scores
- cloud security engineer
- query application data
- list dem applications
- query aggregated url monitoring data.
- secures ai applications with runtime scanning and vulnerability assessment.
- cloud security posture management, compliance monitoring, and workload protection.
- log forwarding profile management.
- list syslog destinations
- threat intelligence
- monitoring
- query aggregated application monitoring data.
- iam admin
- get test results
- saas security admin
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get a bpa report.
- manage enterprise browser policies, user sessions, and deployments.
- submit a bpa request for a device.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- delete a specific log forwarding profile by id.
- query bandwidth data
- create a syslog destination for a log forwarding profile.
- get bpa report
- individual log forwarding profile operations.
- synthetic test results from autonomous dem.
- tenant operator
- get synthetic test results from autonomous dem.
- enterprise it
- monitors network health, performance, and digital experience metrics.
- digital experience
- monitored applications from autonomous dem.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get agent and endpoint scores.
- manages multi-tenant hierarchies and service group configurations for mssps.
- bpa report check details.
- identity and access management, tenant hierarchies, and subscription management.
- ai security engineer
- palo alto networks
- vulnerability manager
- subscription manager
- browser security admin
- firewall policy management, network objects, and cloud-native firewall configuration.
- bpa report retrieval.
- list https destinations for a log forwarding profile.
- create log forwarding profile
- list monitoring tenants.
- get dem application scores
- get agent and endpoint scores from autonomous dem.
- firewall admin
- create https destination
- get log forwarding profile
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- list syslog destinations for a log forwarding profile.
- create an email destination for a log forwarding profile.
- network operations
- designs sase and sd-wan network architectures for secure remote access.
- get synthetic test results.
- query license data
- submit a bpa request.
- agent and endpoint scores from autonomous dem.
- check the status of a bpa request.
- get application experience scores.
- digital experience monitoring, log management, and best practice assessment.
- threat hunter
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- list log forwarding profiles
- sase admin
- list all tenants available for monitoring.
- soar
- get application experience scores from autonomous dem.
- red team operator
- list monitored agents
- platform engineer
- get dem agent scores
- query threat data
- get dem metrics
- list monitored applications.
- list monitoring tenants
- update log forwarding profile
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- manages logging infrastructure, integrations, and platform automation.
- firewall
- executes containment, eradication, and recovery actions during security incidents.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- enterprise browser policy management and secure browsing.
- compliance team
- query aggregated application monitoring data with filters, time ranges, and grouping.
- query aggregated license monitoring data.
- mssp operator
slug: monitoring-and-observability
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Monitoring and Observability\"\n  description: \"Unified monitoring and observability capability for tracking digital experience, aggregating security data, managing log forwarding, and running best practice assessments across Autonomous DEM, SASE Aggregate Monitoring, Strata Logging Service, and AIOps BPA APIs.\"\n  tags:\n    - Palo Alto Networks\n    - Monitoring\n    - Observability\n    - Logging\n    - Digital Experience\n    - Best Practice Assessment\n    - Notifications\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      PALO_ALTO_OAUTH_TOKEN: PALO_ALTO_OAUTH_TOKEN\n\ncapability:\n  consumes:\n    - import: autonomous-dem\n      location: ./shared/autonomous-dem.yaml\n    - import: sase-aggregate-monitoring\n      location: ./shared/sase-aggregate-monitoring.yaml\n    - import: strata-logging-service\n      location: ./shared/strata-logging-service.yaml\n\
  \    - import: aiops-ngfw-bpa\n      location: ./shared/aiops-ngfw-bpa.yaml\n    - import: sase-multitenant-notifications\n      location: ./shared/sase-multitenant-notifications.yaml\n\n  exposes:\n    - type: rest\n      port: 8087\n      namespace: monitoring-and-observability-api\n      description: \"Unified REST API for monitoring and observability workflows across Autonomous DEM, SASE Aggregate Monitoring, Strata Logging Service, and AIOps BPA.\"\n      resources:\n\n        # -------------------------------------------------------\n        # Digital Experience Monitoring (Autonomous DEM)\n        # -------------------------------------------------------\n        - path: /v1/dem-application-scores\n          name: dem-application-scores\n          description: \"Application experience scores from Autonomous DEM.\"\n          operations:\n            - method: GET\n              name: get-dem-application-scores\n              description: \"Get application experience scores.\"\n\
  \              inputParameters:\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Pagination offset.\"\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Maximum number of results to return.\"\n              call: \"autonomous-dem.get-application-scores\"\n              with:\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n       \
  \         offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dem-agent-scores\n          name: dem-agent-scores\n          description: \"Agent and endpoint scores from Autonomous DEM.\"\n          operations:\n            - method: GET\n              name: get-dem-agent-scores\n              description: \"Get agent and endpoint scores.\"\n              inputParameters:\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n                - name: offset\n                  in: query\n                  type: integer\n\
  \                  required: false\n                  description: \"Pagination offset.\"\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Maximum number of results to return.\"\n              call: \"autonomous-dem.get-agent-scores\"\n              with:\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dem-tests/{test_id}/results\n          name: dem-test-results\n          description: \"Synthetic test results from Autonomous DEM.\"\n          operations:\n            - method: GET\n              name: get-dem-test-results\n              description: \"Get synthetic test results.\"\n              inputParameters:\n               \
  \ - name: test_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The ID of the test.\"\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n              call: \"autonomous-dem.get-test-results\"\n              with:\n                test_id: \"rest.test_id\"\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dem-applications\n          name: dem-applications\n          description: \"Monitored applications\
  \ from Autonomous DEM.\"\n          operations:\n            - method: GET\n              name: list-dem-applications\n              description: \"List monitored applications.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Pagination offset.\"\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Maximum number of results to return.\"\n              call: \"autonomous-dem.list-monitored-applications\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dem-agents\n          name: dem-agents\n          description: \"Monitored agents from Autonomous DEM.\"\n      \
  \    operations:\n            - method: GET\n              name: list-dem-agents\n              description: \"List monitored agents.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Pagination offset.\"\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Maximum number of results to return.\"\n              call: \"autonomous-dem.list-monitored-agents\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/dem-metrics\n          name: dem-metrics\n          description: \"Performance metrics from Autonomous DEM.\"\n          operations:\n            - method: GET\n\
  \              name: get-dem-metrics\n              description: \"Get performance metrics.\"\n              inputParameters:\n                - name: start_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: end_time\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n                - name: metric_type\n                  in: query\n                  type: string\n                  required: false\n                  description: \"The type of metric to retrieve.\"\n                - name: granularity\n                  in: query\n                  type: string\n                  required: false\n                  description: \"The granularity of the metrics.\"\n              call: \"autonomous-dem.get-performance-metrics\"\n          \
  \    with:\n                start_time: \"rest.start_time\"\n                end_time: \"rest.end_time\"\n                metric_type: \"rest.metric_type\"\n                granularity: \"rest.granularity\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # Aggregate Monitoring (SASE Aggregate Monitoring)\n        # -------------------------------------------------------\n        - path: /v1/monitoring/threats\n          name: monitoring-threats\n          description: \"Query aggregated threat monitoring data.\"\n          operations:\n            - method: POST\n              name: query-threat-data\n              description: \"Query aggregated threat monitoring data with filters, time ranges, and grouping.\"\n              inputParameters:\n                - name: tsg_id\n                  in: body\n                  type: string\n                  required:\
  \ false\n                  description: \"Tenant service group ID.\"\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter criteria.\"\n                - name: time_range\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Time range for the query.\"\n                - name: count\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Number of results to return.\"\n                - name: histogram\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Histogram configuration.\"\n                - name: group_by\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Group by configuration.\"\
  \n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"sase-aggregate-monitoring.query-threat-data\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                filter: \"rest.filter\"\n                time_range: \"rest.time_range\"\n                count: \"rest.count\"\n                histogram: \"rest.histogram\"\n                group_by: \"rest.group_by\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring/urls\n          name: monitoring-urls\n          description: \"Query aggregated URL monitoring data.\"\n          operations:\n            - method: POST\n              name: query-url-data\n              description: \"Query aggregated URL monitoring data with filters, time ranges, and grouping.\"\
  \n              inputParameters:\n                - name: tsg_id\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Tenant service group ID.\"\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter criteria.\"\n                - name: time_range\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Time range for the query.\"\n                - name: count\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Number of results to return.\"\n                - name: histogram\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Histogram configuration.\"\n                - name:\
  \ group_by\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Group by configuration.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"sase-aggregate-monitoring.query-url-data\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                filter: \"rest.filter\"\n                time_range: \"rest.time_range\"\n                count: \"rest.count\"\n                histogram: \"rest.histogram\"\n                group_by: \"rest.group_by\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring/applications\n          name: monitoring-applications\n          description: \"Query aggregated application monitoring data.\"\n   \
  \       operations:\n            - method: POST\n              name: query-application-data\n              description: \"Query aggregated application monitoring data with filters, time ranges, and grouping.\"\n              inputParameters:\n                - name: tsg_id\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Tenant service group ID.\"\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter criteria.\"\n                - name: time_range\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Time range for the query.\"\n                - name: count\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Number of results to return.\"\n   \
  \             - name: histogram\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Histogram configuration.\"\n                - name: group_by\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Group by configuration.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"sase-aggregate-monitoring.query-application-data\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                filter: \"rest.filter\"\n                time_range: \"rest.time_range\"\n                count: \"rest.count\"\n                histogram: \"rest.histogram\"\n                group_by: \"rest.group_by\"\n                sort: \"rest.sort\"\n              outputParameters:\n             \
  \   - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring/bandwidth\n          name: monitoring-bandwidth\n          description: \"Query aggregated bandwidth monitoring data.\"\n          operations:\n            - method: POST\n              name: query-bandwidth-data\n              description: \"Query aggregated bandwidth monitoring data with filters, time ranges, and grouping.\"\n              inputParameters:\n                - name: tsg_id\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Tenant service group ID.\"\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter criteria.\"\n                - name: time_range\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Time range for the\
  \ query.\"\n                - name: count\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Number of results to return.\"\n                - name: histogram\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Histogram configuration.\"\n                - name: group_by\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Group by configuration.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"sase-aggregate-monitoring.query-bandwidth-data\"\n              with:\n                tsg_id: \"rest.tsg_id\"\n                filter: \"rest.filter\"\n                time_range: \"rest.time_range\"\n          \
  \      count: \"rest.count\"\n                histogram: \"rest.histogram\"\n                group_by: \"rest.group_by\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring/licenses\n          name: monitoring-licenses\n          description: \"Query aggregated license monitoring data.\"\n          operations:\n            - method: POST\n              name: query-license-data\n              description: \"Query aggregated license monitoring data with filters, time ranges, and grouping.\"\n              inputParameters:\n                - name: tsg_id\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Tenant service group ID.\"\n                - name: filter\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Filter\
  \ criteria.\"\n                - name: time_range\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Time range for the query.\"\n                - name: count\n                  in: body\n                  type: integer\n                  required: false\n                  description: \"Number of results to return.\"\n                - name: histogram\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Histogram configuration.\"\n                - name: group_by\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Group by configuration.\"\n                - name: sort\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Sort configuration.\"\n              call: \"sase-aggregate-monitoring.query-license-data\"\
  \n              with:\n                tsg_id: \"rest.tsg_id\"\n                filter: \"rest.filter\"\n                time_range: \"rest.time_range\"\n                count: \"rest.count\"\n                histogram: \"rest.histogram\"\n                group_by: \"rest.group_by\"\n                sort: \"rest.sort\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/monitoring/tenants\n          name: monitoring-tenants\n          description: \"List monitoring tenants.\"\n          operations:\n            - method: GET\n              name: list-monitoring-tenants\n              description: \"List all tenants available for monitoring.\"\n              inputParameters:\n                - name: tsg_id\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Tenant service group ID.\"\n              call: \"sase-aggregate-monitoring.list-monitoring-tenants\"\
  \n              with:\n                tsg_id: \"rest.tsg_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # Log Forwarding (Strata Logging Service)\n        # -------------------------------------------------------\n        - path: /v1/log-forwarding-profiles\n          name: log-forwarding-profiles\n          description: \"Log forwarding profile management.\"\n          operations:\n            - method: GET\n              name: list-log-forwarding-profiles\n              description: \"List all log forwarding profiles.\"\n              inputParameters:\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                  description: \"Pagination offset.\"\n                - name: limit\n                  in: query\n                  type: integer\n                  required:\
  \ false\n                  description: \"Maximum number of results to return.\"\n              call: \"strata-logging-service.list-log-forwarding-profiles\"\n              with:\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-log-forwarding-profile\n              description: \"Create a new log forwarding profile.\"\n              inputParameters:\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the log forwarding profile.\"\n                - name: log_types\n                  in: body\n                  type: object\n                  required: true\n                  description: \"Log types to forward.\"\n                - name: description\n                  in: body\n           \
  \       type: string\n                  required: false\n                  description: \"Description of the profile.\"\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n                  description: \"Whether the profile is enabled.\"\n              call: \"strata-logging-service.create-log-forwarding-profile\"\n              with:\n                name: \"rest.name\"\n                log_types: \"rest.log_types\"\n                description: \"rest.description\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-forwarding-profiles/{profile_id}\n          name: log-forwarding-profile\n          description: \"Individual log forwarding profile operations.\"\n          operations:\n            - method: GET\n              name: get-log-forwarding-profile\n              description: \"Get\
  \ a specific log forwarding profile by ID.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.get-log-forwarding-profile\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: PUT\n              name: update-log-forwarding-profile\n              description: \"Update a specific log forwarding profile by ID.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.update-log-forwarding-profile\"\n              with:\n\
  \                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: DELETE\n              name: delete-log-forwarding-profile\n              description: \"Delete a specific log forwarding profile by ID.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.delete-log-forwarding-profile\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-forwarding-profiles/{profile_id}/destinations/syslog\n          name: syslog-destinations\n          description: \"Syslog destination management for log forwarding profiles.\"\n       \
  \   operations:\n            - method: GET\n              name: list-syslog-destinations\n              description: \"List syslog destinations for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.list-syslog-destinations\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-syslog-destination\n              description: \"Create a syslog destination for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description:\
  \ \"The log forwarding profile ID.\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the syslog destination.\"\n                - name: server\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Syslog server address.\"\n                - name: port\n                  in: body\n                  type: integer\n                  required: true\n                  description: \"Syslog server port.\"\n                - name: protocol\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Transport protocol.\"\n                - name: format\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Syslog message format.\"\n                - name: facility\n\
  \                  in: body\n                  type: string\n                  required: true\n                  description: \"Syslog facility.\"\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n                  description: \"Whether the destination is enabled.\"\n              call: \"strata-logging-service.create-syslog-destination\"\n              with:\n                profile_id: \"rest.profile_id\"\n                name: \"rest.name\"\n                server: \"rest.server\"\n                port: \"rest.port\"\n                protocol: \"rest.protocol\"\n                format: \"rest.format\"\n                facility: \"rest.facility\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-forwarding-profiles/{profile_id}/destinations/https\n          name: https-destinations\n  \
  \        description: \"HTTPS destination management for log forwarding profiles.\"\n          operations:\n            - method: GET\n              name: list-https-destinations\n              description: \"List HTTPS destinations for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.list-https-destinations\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-https-destination\n              description: \"Create an HTTPS destination for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n  \
  \                type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the HTTPS destination.\"\n                - name: uri\n                  in: body\n                  type: string\n                  required: true\n                  description: \"HTTPS destination URI.\"\n                - name: http_method\n                  in: body\n                  type: string\n                  required: true\n                  description: \"HTTP method to use.\"\n                - name: headers\n                  in: body\n                  type: object\n                  required: false\n                  description: \"Custom HTTP headers.\"\n                - name: tls_verify\n                  in: body\n                  type: boolean\n                  required:\
  \ false\n                  description: \"Whether to verify TLS certificates.\"\n                - name: enabled\n                  in: body\n                  type: boolean\n                  required: false\n                  description: \"Whether the destination is enabled.\"\n              call: \"strata-logging-service.create-https-destination\"\n              with:\n                profile_id: \"rest.profile_id\"\n                name: \"rest.name\"\n                uri: \"rest.uri\"\n                http_method: \"rest.http_method\"\n                headers: \"rest.headers\"\n                tls_verify: \"rest.tls_verify\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-forwarding-profiles/{profile_id}/destinations/email\n          name: email-destinations\n          description: \"Email destination management for log forwarding profiles.\"\n          operations:\n\
  \            - method: GET\n              name: list-email-destinations\n              description: \"List email destinations for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.list-email-destinations\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-email-destination\n              description: \"Create an email destination for a log forwarding profile.\"\n              inputParameters:\n                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding\
  \ profile ID.\"\n                - name: name\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Name of the email destination.\"\n                - name: gateway\n                  in: body\n                  type: string\n                  required: true\n                  description: \"Email gateway server.\"\n                - name: from\n                  in: body\n                  type: string\n                  required: true\n                  description: \"From email address.\"\n                - name: to\n                  in: body\n                  type: string\n                  required: true\n                  description: \"To email address.\"\n                - name: and_also_to\n                  in: body\n                  type: string\n                  required: false\n                  description: \"Additional recipient email address.\"\n                - name: enabled\n             \
  \     in: body\n                  type: boolean\n                  required: false\n                  description: \"Whether the destination is enabled.\"\n              call: \"strata-logging-service.create-email-destination\"\n              with:\n                profile_id: \"rest.profile_id\"\n                name: \"rest.name\"\n                gateway: \"rest.gateway\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                and_also_to: \"rest.and_also_to\"\n                enabled: \"rest.enabled\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/log-forwarding-profiles/{profile_id}/status\n          name: log-forwarding-status\n          description: \"Log forwarding profile status.\"\n          operations:\n            - method: GET\n              name: get-log-forwarding-status\n              description: \"Get the status of a log forwarding profile.\"\n              inputParameters:\n\
  \                - name: profile_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The log forwarding profile ID.\"\n              call: \"strata-logging-service.get-log-forwarding-status\"\n              with:\n                profile_id: \"rest.profile_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # -------------------------------------------------------\n        # Best Practice Assessment (AIOps NGFW BPA)\n        # -------------------------------------------------------\n        - path: /v1/bpa-requests\n          name: bpa-requests\n          description: \"BPA request operations.\"\n          operations:\n            - method: POST\n              name: submit-bpa-request\n              description: \"Submit a BPA request.\"\n              inputParameters:\n                - name: device_serial\n                  in: body\n        \
  \          type: string\n                  required: true\n                  description: \"The serial number of the device to assess.\"\n                - name: config_type\n                  in: body\n                  type: string\n                  required: true\n                  description: \"The configuration type for the BPA request.\"\n              call: \"aiops-ngfw-bpa.submit-bpa-request\"\n              with:\n                device_serial: \"rest.device_serial\"\n                config_type: \"rest.config_type\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bpa-requests/{request_id}\n          name: bpa-request-status\n          description: \"BPA request status.\"\n          operations:\n            - method: GET\n              name: get-bpa-request-status\n              description: \"Check the status of a BPA request.\"\n              inputParameters:\n                - name: request_id\n  \
  \                in: path\n                  type: string\n                  required: true\n                  description: \"The ID of the BPA request.\"\n              call: \"aiops-ngfw-bpa.get-bpa-request-status\"\n              with:\n                request_id: \"rest.request_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bpa-reports/{report_id}\n          name: bpa-report\n          description: \"BPA report retrieval.\"\n          operations:\n            - method: GET\n              name: get-bpa-report\n              description: \"Get a BPA report.\"\n              inputParameters:\n                - name: report_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The ID of the BPA report.\"\n              call: \"aiops-ngfw-bpa.get-bpa-report\"\n              with:\n                report_id: \"rest.report_id\"\n   \
  \           outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/bpa-reports/{report_id}/checks\n          name: bpa-report-checks\n          description: \"BPA report check details.\"\n          operations:\n            - method: GET\n              name: get-bpa-report-checks\n              description: \"Get BPA report check details.\"\n              inputParameters:\n                - name: report_id\n                  in: path\n                  type: string\n                  required: true\n                  description: \"The ID of the BPA report.\"\n              call: \"aiops-ngfw-bpa.get-bpa-report-checks\"\n              with:\n                report_id: \"rest.report_id\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    # =============================================================\n    # MCP Server — AI-assisted monitoring and observability\n    # =============================================================\n\
  \    - type: mcp\n      port: 9097\n      namespace: monitoring-and-observability-mcp\n      transport: http\n      description: \"MCP server for AI-assisted monitoring and observability across Autonomous DEM, SASE Aggregate Monitoring, Strata Logging Service, and AIOps BPA.\"\n      tools:\n\n        # ---------------------------------------------------------\n        # Digital Experience Monitoring (Autonomous DEM)\n        # ---------------------------------------------------------\n        - name: get-application-scores\n          description: \"Get application experience scores from Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: start_time\n              type: string\n              description: \"Start time for the query range.\"\n              required: false\n            - name: end_time\n              type: string\n       \
  \       description: \"End time for the query range.\"\n              required: false\n            - name: offset\n              type: integer\n              description: \"Pagination offset.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of results to return.\"\n              required: false\n          call: \"autonomous-dem.get-application-scores\"\n          with:\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-agent-scores\n          description: \"Get agent and endpoint scores from Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            -\
  \ name: start_time\n              type: string\n              description: \"Start time for the query range.\"\n              required: false\n            - name: end_time\n              type: string\n              description: \"End time for the query range.\"\n              required: false\n            - name: offset\n              type: integer\n              description: \"Pagination offset.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of results to return.\"\n              required: false\n          call: \"autonomous-dem.get-agent-scores\"\n          with:\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-test-results\n          description: \"Get synthetic test results from\
  \ Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: test_id\n              type: string\n              description: \"The ID of the test.\"\n              required: true\n            - name: start_time\n              type: string\n              description: \"Start time for the query range.\"\n              required: false\n            - name: end_time\n              type: string\n              description: \"End time for the query range.\"\n              required: false\n          call: \"autonomous-dem.get-test-results\"\n          with:\n            test_id: \"tools.test_id\"\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-monitored-applications\n          description: \"List monitored\
  \ applications from Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n              description: \"Pagination offset.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of results to return.\"\n              required: false\n          call: \"autonomous-dem.list-monitored-applications\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: list-monitored-agents\n          description: \"List monitored agents from Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n         \
  \ inputParameters:\n            - name: offset\n              type: integer\n              description: \"Pagination offset.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of results to return.\"\n              required: false\n          call: \"autonomous-dem.list-monitored-agents\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        - name: get-performance-metrics\n          description: \"Get performance metrics from Autonomous DEM.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: start_time\n              type: string\n              description: \"Start time for the query range.\"\n              required: false\n            -\
  \ name: end_time\n              type: string\n              description: \"End time for the query range.\"\n              required: false\n            - name: metric_type\n              type: string\n              description: \"The type of metric to retrieve.\"\n              required: false\n            - name: granularity\n              type: string\n              description: \"The granularity of the metrics.\"\n              required: false\n          call: \"autonomous-dem.get-performance-metrics\"\n          with:\n            start_time: \"tools.start_time\"\n            end_time: \"tools.end_time\"\n            metric_type: \"tools.metric_type\"\n            granularity: \"tools.granularity\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Aggregate Monitoring (SASE Aggregate Monitoring)\n        # ---------------------------------------------------------\n\
  \        - name: query-threat-data\n          description: \"Query aggregated threat monitoring data with filters, time ranges, and grouping.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n            - name: filter\n              type: object\n              description: \"Filter criteria.\"\n              required: false\n            - name: time_range\n              type: object\n              description: \"Time range for the query.\"\n              required: false\n            - name: count\n              type: integer\n              description: \"Number of results to return.\"\n              required: false\n            - name: histogram\n              type: object\n              description: \"Histogram configuration.\"\
  \n              required: false\n            - name: group_by\n              type: object\n              description: \"Group by configuration.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"sase-aggregate-monitoring.query-threat-data\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            filter: \"tools.filter\"\n            time_range: \"tools.time_range\"\n            count: \"tools.count\"\n            histogram: \"tools.histogram\"\n            group_by: \"tools.group_by\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-url-data\n          description: \"Query aggregated URL monitoring data with filters, time ranges, and grouping.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent:\
  \ true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n            - name: filter\n              type: object\n              description: \"Filter criteria.\"\n              required: false\n            - name: time_range\n              type: object\n              description: \"Time range for the query.\"\n              required: false\n            - name: count\n              type: integer\n              description: \"Number of results to return.\"\n              required: false\n            - name: histogram\n              type: object\n              description: \"Histogram configuration.\"\n              required: false\n            - name: group_by\n              type: object\n              description: \"Group by configuration.\"\n              required: false\n            - name: sort\n              type: object\n           \
  \   description: \"Sort configuration.\"\n              required: false\n          call: \"sase-aggregate-monitoring.query-url-data\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            filter: \"tools.filter\"\n            time_range: \"tools.time_range\"\n            count: \"tools.count\"\n            histogram: \"tools.histogram\"\n            group_by: \"tools.group_by\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-application-data\n          description: \"Query aggregated application monitoring data with filters, time ranges, and grouping.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n            - name:\
  \ filter\n              type: object\n              description: \"Filter criteria.\"\n              required: false\n            - name: time_range\n              type: object\n              description: \"Time range for the query.\"\n              required: false\n            - name: count\n              type: integer\n              description: \"Number of results to return.\"\n              required: false\n            - name: histogram\n              type: object\n              description: \"Histogram configuration.\"\n              required: false\n            - name: group_by\n              type: object\n              description: \"Group by configuration.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"sase-aggregate-monitoring.query-application-data\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            filter: \"tools.filter\"\
  \n            time_range: \"tools.time_range\"\n            count: \"tools.count\"\n            histogram: \"tools.histogram\"\n            group_by: \"tools.group_by\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: query-bandwidth-data\n          description: \"Query aggregated bandwidth monitoring data with filters, time ranges, and grouping.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n            - name: filter\n              type: object\n              description: \"Filter criteria.\"\n              required: false\n            - name: time_range\n              type: object\n              description: \"Time range for the query.\"\
  \n              required: false\n            - name: count\n              type: integer\n              description: \"Number of results to return.\"\n              required: false\n            - name: histogram\n              type: object\n              description: \"Histogram configuration.\"\n              required: false\n            - name: group_by\n              type: object\n              description: \"Group by configuration.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"sase-aggregate-monitoring.query-bandwidth-data\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            filter: \"tools.filter\"\n            time_range: \"tools.time_range\"\n            count: \"tools.count\"\n            histogram: \"tools.histogram\"\n            group_by: \"tools.group_by\"\n            sort: \"tools.sort\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: query-license-data\n          description: \"Query aggregated license monitoring data with filters, time ranges, and grouping.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n            - name: filter\n              type: object\n              description: \"Filter criteria.\"\n              required: false\n            - name: time_range\n              type: object\n              description: \"Time range for the query.\"\n              required: false\n            - name: count\n              type: integer\n              description: \"Number of results to return.\"\n              required: false\n            - name: histogram\n              type:\
  \ object\n              description: \"Histogram configuration.\"\n              required: false\n            - name: group_by\n              type: object\n              description: \"Group by configuration.\"\n              required: false\n            - name: sort\n              type: object\n              description: \"Sort configuration.\"\n              required: false\n          call: \"sase-aggregate-monitoring.query-license-data\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n            filter: \"tools.filter\"\n            time_range: \"tools.time_range\"\n            count: \"tools.count\"\n            histogram: \"tools.histogram\"\n            group_by: \"tools.group_by\"\n            sort: \"tools.sort\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-monitoring-tenants\n          description: \"List all tenants available for monitoring.\"\n          hints:\n            readOnly: true\n          \
  \  destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: tsg_id\n              type: string\n              description: \"Tenant service group ID.\"\n              required: false\n          call: \"sase-aggregate-monitoring.list-monitoring-tenants\"\n          with:\n            tsg_id: \"tools.tsg_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Log Forwarding (Strata Logging Service)\n        # ---------------------------------------------------------\n        - name: list-log-forwarding-profiles\n          description: \"List all log forwarding profiles.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: offset\n              type: integer\n           \
  \   description: \"Pagination offset.\"\n              required: false\n            - name: limit\n              type: integer\n              description: \"Maximum number of results to return.\"\n              required: false\n          call: \"strata-logging-service.list-log-forwarding-profiles\"\n          with:\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-log-forwarding-profile\n          description: \"Create a new log forwarding profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: name\n              type: string\n              description: \"Name of the log forwarding profile.\"\n              required: true\n            - name: log_types\n              type: object\n              description: \"\
  Log types to forward.\"\n              required: true\n            - name: description\n              type: string\n              description: \"Description of the profile.\"\n              required: false\n            - name: enabled\n              type: boolean\n              description: \"Whether the profile is enabled.\"\n              required: false\n          call: \"strata-logging-service.create-log-forwarding-profile\"\n          with:\n            name: \"tools.name\"\n            log_types: \"tools.log_types\"\n            description: \"tools.description\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-log-forwarding-profile\n          description: \"Get a specific log forwarding profile by ID.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n          \
  \  - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.get-log-forwarding-profile\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: update-log-forwarding-profile\n          description: \"Update a specific log forwarding profile by ID.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.update-log-forwarding-profile\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n\
  \              mapping: \"$.\"\n\n        - name: delete-log-forwarding-profile\n          description: \"Delete a specific log forwarding profile by ID.\"\n          hints:\n            readOnly: false\n            destructive: true\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.delete-log-forwarding-profile\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-syslog-destinations\n          description: \"List syslog destinations for a log forwarding profile.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n       \
  \     - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.list-syslog-destinations\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-syslog-destination\n          description: \"Create a syslog destination for a log forwarding profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n            - name: name\n              type: string\n              description: \"Name of the syslog destination.\"\n              required: true\n            - name: server\n     \
  \         type: string\n              description: \"Syslog server address.\"\n              required: true\n            - name: port\n              type: integer\n              description: \"Syslog server port.\"\n              required: true\n            - name: protocol\n              type: string\n              description: \"Transport protocol.\"\n              required: true\n            - name: format\n              type: string\n              description: \"Syslog message format.\"\n              required: true\n            - name: facility\n              type: string\n              description: \"Syslog facility.\"\n              required: true\n            - name: enabled\n              type: boolean\n              description: \"Whether the destination is enabled.\"\n              required: false\n          call: \"strata-logging-service.create-syslog-destination\"\n          with:\n            profile_id: \"tools.profile_id\"\n            name: \"tools.name\"\n           \
  \ server: \"tools.server\"\n            port: \"tools.port\"\n            protocol: \"tools.protocol\"\n            format: \"tools.format\"\n            facility: \"tools.facility\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-https-destinations\n          description: \"List HTTPS destinations for a log forwarding profile.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.list-https-destinations\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-https-destination\n\
  \          description: \"Create an HTTPS destination for a log forwarding profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n            - name: name\n              type: string\n              description: \"Name of the HTTPS destination.\"\n              required: true\n            - name: uri\n              type: string\n              description: \"HTTPS destination URI.\"\n              required: true\n            - name: http_method\n              type: string\n              description: \"HTTP method to use.\"\n              required: true\n            - name: headers\n              type: object\n              description: \"Custom HTTP headers.\"\n              required: false\n            - name: tls_verify\n\
  \              type: boolean\n              description: \"Whether to verify TLS certificates.\"\n              required: false\n            - name: enabled\n              type: boolean\n              description: \"Whether the destination is enabled.\"\n              required: false\n          call: \"strata-logging-service.create-https-destination\"\n          with:\n            profile_id: \"tools.profile_id\"\n            name: \"tools.name\"\n            uri: \"tools.uri\"\n            http_method: \"tools.http_method\"\n            headers: \"tools.headers\"\n            tls_verify: \"tools.tls_verify\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-email-destinations\n          description: \"List email destinations for a log forwarding profile.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld:\
  \ true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.list-email-destinations\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: create-email-destination\n          description: \"Create an email destination for a log forwarding profile.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n            - name: name\n              type: string\n              description: \"Name of the email destination.\"\n              required: true\n\
  \            - name: gateway\n              type: string\n              description: \"Email gateway server.\"\n              required: true\n            - name: from\n              type: string\n              description: \"From email address.\"\n              required: true\n            - name: to\n              type: string\n              description: \"To email address.\"\n              required: true\n            - name: and_also_to\n              type: string\n              description: \"Additional recipient email address.\"\n              required: false\n            - name: enabled\n              type: boolean\n              description: \"Whether the destination is enabled.\"\n              required: false\n          call: \"strata-logging-service.create-email-destination\"\n          with:\n            profile_id: \"tools.profile_id\"\n            name: \"tools.name\"\n            gateway: \"tools.gateway\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n  \
  \          and_also_to: \"tools.and_also_to\"\n            enabled: \"tools.enabled\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-log-forwarding-status\n          description: \"Get the status of a log forwarding profile.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: profile_id\n              type: string\n              description: \"The log forwarding profile ID.\"\n              required: true\n          call: \"strata-logging-service.get-log-forwarding-status\"\n          with:\n            profile_id: \"tools.profile_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ---------------------------------------------------------\n        # Best Practice Assessment (AIOps NGFW BPA)\n        # ---------------------------------------------------------\n\
  \        - name: submit-bpa-request\n          description: \"Submit a BPA request for a device.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: device_serial\n              type: string\n              description: \"The serial number of the device to assess.\"\n              required: true\n            - name: config_type\n              type: string\n              description: \"The configuration type for the BPA request.\"\n              required: true\n          call: \"aiops-ngfw-bpa.submit-bpa-request\"\n          with:\n            device_serial: \"tools.device_serial\"\n            config_type: \"tools.config_type\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bpa-request-status\n          description: \"Check the status of a BPA request.\"\n          hints:\n            readOnly:\
  \ true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: request_id\n              type: string\n              description: \"The ID of the BPA request.\"\n              required: true\n          call: \"aiops-ngfw-bpa.get-bpa-request-status\"\n          with:\n            request_id: \"tools.request_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bpa-report\n          description: \"Get a BPA report.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: report_id\n              type: string\n              description: \"The ID of the BPA report.\"\n              required: true\n          call: \"aiops-ngfw-bpa.get-bpa-report\"\n          with:\n            report_id: \"tools.report_id\"\n         \
  \ outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bpa-report-checks\n          description: \"Get BPA report check details.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: report_id\n              type: string\n              description: \"The ID of the BPA report.\"\n              required: true\n          call: \"aiops-ngfw-bpa.get-bpa-report-checks\"\n          with:\n            report_id: \"tools.report_id\"\n          outputParameters:\n            - type: array\n              mapping: \"$.\"\n"
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
