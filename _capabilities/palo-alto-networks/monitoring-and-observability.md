---
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
- get a bpa report.
- get log forwarding profile
- https destination management for log forwarding profiles.
- vulnerability manager
- delete log forwarding profile
- sd wan operator
- enterprise browser policy management and secure browsing.
- get a specific log forwarding profile by id.
- query bandwidth data
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- designs and implements network security architectures and policies.
- firewall
- compliance officer
- syslog destination management for log forwarding profiles.
- get dem metrics
- manages enterprise browser policies and secure browsing configurations.
- log forwarding profile status.
- data protection analyst
- get bpa report checks
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- mssp operator
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- list syslog destinations for a log forwarding profile.
- executes containment, eradication, and recovery actions during security incidents.
- get test results
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- get agent and endpoint scores from autonomous dem.
- threat intelligence
- malware researcher
- data loss prevention, saas security monitoring, and identity security posture.
- list https destinations for a log forwarding profile.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- analyzes suspicious files and samples for malware characteristics.
- list monitoring tenants
- saas security admin
- query aggregated url monitoring data with filters, time ranges, and grouping.
- monitored agents from autonomous dem.
- get dem application scores
- list email destinations
- designs sase and sd-wan network architectures for secure remote access.
- list monitoring tenants.
- firewall admin
- secures ai applications with runtime scanning and vulnerability assessment.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- bpa report retrieval.
- red team operator
- get performance metrics
- log forwarding profile management.
- get application experience scores from autonomous dem.
- get synthetic test results.
- query license data
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- monitoring
- sase
- bpa request operations.
- notifications
- ai runtime security scanning and automated red teaming for ai applications.
- list https destinations
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- submit a bpa request.
- network security engineer
- browser security admin
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- query aggregated license monitoring data.
- create https destination
- list all tenants available for monitoring.
- tenant operator
- investigates dlp incidents and manages sensitive data protection policies.
- threat intel analyst
- get application scores
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- agent and endpoint scores from autonomous dem.
- subscription manager
- manages multi-tenant security operations at scale for managed service providers.
- performance metrics from autonomous dem.
- network operations
- cloud security
- update log forwarding profile
- identity and access management, tenant hierarchies, and subscription management.
- soar
- logging
- incident responder
- list log forwarding profiles
- bpa report check details.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- individual log forwarding profile operations.
- soc analyst
- xdr
- list dem applications
- list email destinations for a log forwarding profile.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- create an https destination for a log forwarding profile.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- email destination management for log forwarding profiles.
- create an email destination for a log forwarding profile.
- compliance team
- enterprise it
- cloud security engineer
- researches threat actors, malware campaigns, and vulnerability trends.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- query aggregated threat monitoring data.
- list monitored agents.
- manages logging infrastructure, integrations, and platform automation.
- get bpa report
- network security
- palo alto networks
- get bpa report check details.
- check the status of a bpa request.
- query application data
- update a specific log forwarding profile by id.
- create log forwarding profile
- query aggregated license monitoring data with filters, time ranges, and grouping.
- get dem test results
- get performance metrics.
- threat hunter
- monitors and remediates cloud security misconfigurations and compliance violations.
- get bpa request status
- monitored applications from autonomous dem.
- query aggregated application monitoring data.
- list monitored applications from autonomous dem.
- submit a bpa request for a device.
- query aggregated application monitoring data with filters, time ranges, and grouping.
- proactively searches for threats and iocs across telemetry data.
- delete a specific log forwarding profile by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- query aggregated bandwidth monitoring data.
- query threat data
- get performance metrics from autonomous dem.
- firewall policy management, network objects, and cloud-native firewall configuration.
- list dem agents
- get agent scores
- create syslog destination
- sase admin
- cloud security posture management, compliance monitoring, and workload protection.
- bpa request status.
- network architect
- get agent and endpoint scores.
- list all log forwarding profiles.
- create a syslog destination for a log forwarding profile.
- manage enterprise browser policies, user sessions, and deployments.
- get the status of a log forwarding profile.
- submit bpa request
- list syslog destinations
- get dem agent scores
- application experience scores from autonomous dem.
- query url data
- create email destination
- iam admin
- list monitored agents from autonomous dem.
- sre
- query aggregated url monitoring data.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- digital experience monitoring, log management, and best practice assessment.
- best practice assessment
- observability
- get log forwarding status
- conducts automated adversarial testing against ai systems and llm applications.
- create a new log forwarding profile.
- digital experience
- get synthetic test results from autonomous dem.
- list monitored agents
- list monitored applications
- list monitored applications.
- get application experience scores.
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- synthetic test results from autonomous dem.
slug: monitoring-and-observability
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
