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
- get agent and endpoint scores.
- create an https destination for a log forwarding profile.
- executes containment, eradication, and recovery actions during security incidents.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- create syslog destination
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- firewall policy management, network objects, and cloud-native firewall configuration.
- tenant operator
- observability
- get dem application scores
- query aggregated threat monitoring data.
- list monitored applications.
- query aggregated application monitoring data.
- log forwarding profile management.
- get synthetic test results from autonomous dem.
- cloud security engineer
- digital experience monitoring, log management, and best practice assessment.
- update a specific log forwarding profile by id.
- network security engineer
- threat intelligence
- malware researcher
- list all log forwarding profiles.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- get performance metrics.
- network operations
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- submit a bpa request for a device.
- https destination management for log forwarding profiles.
- get dem test results
- get bpa report check details.
- ai runtime security scanning and automated red teaming for ai applications.
- submit bpa request
- synthetic test results from autonomous dem.
- cloud security posture management, compliance monitoring, and workload protection.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- threat intel analyst
- get bpa report checks
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- query application data
- bpa request status.
- list monitored applications from autonomous dem.
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- list monitored applications
- query license data
- monitors network health, performance, and digital experience metrics.
- query bandwidth data
- list email destinations
- query threat data
- secures ai applications with runtime scanning and vulnerability assessment.
- get log forwarding status
- list monitored agents
- individual log forwarding profile operations.
- list https destinations for a log forwarding profile.
- query aggregated application monitoring data with filters, time ranges, and grouping.
- compliance officer
- get the status of a log forwarding profile.
- digital experience
- performance metrics from autonomous dem.
- create log forwarding profile
- firewall admin
- list log forwarding profiles
- list https destinations
- email destination management for log forwarding profiles.
- list all tenants available for monitoring.
- red team operator
- conducts automated adversarial testing against ai systems and llm applications.
- xdr
- saas security admin
- platform engineer
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages logging infrastructure, integrations, and platform automation.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- create a new log forwarding profile.
- create an email destination for a log forwarding profile.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- bpa report retrieval.
- get bpa report
- iam admin
- incident responder
- subscription manager
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get dem metrics
- designs and implements network security architectures and policies.
- investigates security incidents, triages alerts, and coordinates response actions.
- mssp operator
- get log forwarding profile
- notifications
- compliance team
- get bpa request status
- manages service accounts, roles, and access policies for platform api access.
- query aggregated license monitoring data.
- monitoring
- get application experience scores.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- identity and access management, tenant hierarchies, and subscription management.
- analyzes suspicious files and samples for malware characteristics.
- log forwarding profile status.
- manages enterprise browser policies and secure browsing configurations.
- soc analyst
- best practice assessment
- list monitoring tenants.
- get dem agent scores
- syslog destination management for log forwarding profiles.
- vulnerability manager
- list email destinations for a log forwarding profile.
- query aggregated license monitoring data with filters, time ranges, and grouping.
- designs sase and sd-wan network architectures for secure remote access.
- enterprise browser policy management and secure browsing.
- palo alto networks
- update log forwarding profile
- get a bpa report.
- list monitored agents from autonomous dem.
- sre
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- create https destination
- network security
- bpa request operations.
- ai security engineer
- threat hunter
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- enterprise it
- soar
- query aggregated bandwidth monitoring data.
- get agent and endpoint scores from autonomous dem.
- data protection analyst
- get synthetic test results.
- manage enterprise browser policies, user sessions, and deployments.
- get agent scores
- investigates dlp incidents and manages sensitive data protection policies.
- cybersecurity
- check the status of a bpa request.
- network architect
- create email destination
- data loss prevention, saas security monitoring, and identity security posture.
- list syslog destinations for a log forwarding profile.
- monitored agents from autonomous dem.
- monitors and remediates cloud security misconfigurations and compliance violations.
- manages multi-tenant hierarchies and service group configurations for mssps.
- browser security admin
- get application scores
- sase
- application experience scores from autonomous dem.
- logging
- query aggregated url monitoring data.
- sd wan operator
- list dem applications
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- firewall
- manages multi-tenant security operations at scale for managed service providers.
- cloud security
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get performance metrics
- create a syslog destination for a log forwarding profile.
- researches threat actors, malware campaigns, and vulnerability trends.
- list monitored agents.
- delete log forwarding profile
- bpa report check details.
- list syslog destinations
- agent and endpoint scores from autonomous dem.
- sase admin
- query url data
- submit a bpa request.
- proactively searches for threats and iocs across telemetry data.
- monitored applications from autonomous dem.
- list monitoring tenants
- delete a specific log forwarding profile by id.
- get application experience scores from autonomous dem.
- get test results
- get a specific log forwarding profile by id.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get performance metrics from autonomous dem.
- list dem agents
slug: monitoring-and-observability
source_filename: monitoring-and-observability.yaml
source_heading: Capability Spec
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
  \     in: body\n                  type: boolean\n                  required: false\n                  descript\n\n# --- truncated at 32 KB (66 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/monitoring-and-observability.yaml\n"
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
