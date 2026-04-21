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
- firewall policy management, network objects, and cloud-native firewall configuration.
- proactively searches for threats and iocs across telemetry data.
- get test results
- notifications
- create an email destination for a log forwarding profile.
- query threat data
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- cloud security engineer
- query aggregated bandwidth monitoring data.
- create a new log forwarding profile.
- threat intel analyst
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- get performance metrics from autonomous dem.
- enterprise browser policy management and secure browsing.
- query aggregated license monitoring data.
- data loss prevention, saas security monitoring, and identity security posture.
- list all tenants available for monitoring.
- get performance metrics.
- mssp operator
- saas security admin
- query bandwidth data
- get application experience scores.
- check the status of a bpa request.
- data protection analyst
- enterprise it
- best practice assessment
- create log forwarding profile
- delete log forwarding profile
- list syslog destinations
- query aggregated threat monitoring data.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- individual log forwarding profile operations.
- browser security admin
- list monitored applications
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- network security
- list dem agents
- update a specific log forwarding profile by id.
- query aggregated application monitoring data.
- list monitored agents from autonomous dem.
- list dem applications
- get dem test results
- get application experience scores from autonomous dem.
- sd wan operator
- secures ai applications with runtime scanning and vulnerability assessment.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- threat hunter
- list email destinations for a log forwarding profile.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get bpa request status
- tenant operator
- manages enterprise browser policies and secure browsing configurations.
- firewall
- cloud security
- create syslog destination
- cloud security posture management, compliance monitoring, and workload protection.
- cybersecurity
- get the status of a log forwarding profile.
- network security engineer
- query aggregated license monitoring data with filters, time ranges, and grouping.
- get dem agent scores
- get a bpa report.
- monitoring
- subscription manager
- sase
- compliance team
- get log forwarding profile
- analyzes suspicious files and samples for malware characteristics.
- observability
- designs and implements network security architectures and policies.
- get agent and endpoint scores.
- query license data
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- list monitored applications from autonomous dem.
- query aggregated url monitoring data.
- ai security engineer
- vulnerability manager
- monitored applications from autonomous dem.
- manages multi-tenant hierarchies and service group configurations for mssps.
- create email destination
- xdr
- manages multi-tenant security operations at scale for managed service providers.
- list monitoring tenants
- firewall admin
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- investigates security incidents, triages alerts, and coordinates response actions.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get dem application scores
- get performance metrics
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- manages service accounts, roles, and access policies for platform api access.
- compliance officer
- incident responder
- get agent and endpoint scores from autonomous dem.
- sase admin
- email destination management for log forwarding profiles.
- designs sase and sd-wan network architectures for secure remote access.
- red team operator
- query aggregated application monitoring data with filters, time ranges, and grouping.
- get bpa report check details.
- https destination management for log forwarding profiles.
- list monitored agents.
- digital experience
- query application data
- soc analyst
- get synthetic test results from autonomous dem.
- soar
- palo alto networks
- log forwarding profile status.
- create an https destination for a log forwarding profile.
- investigates dlp incidents and manages sensitive data protection policies.
- bpa report check details.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- update log forwarding profile
- get bpa report
- get agent scores
- executes containment, eradication, and recovery actions during security incidents.
- query url data
- get dem metrics
- ai runtime security scanning and automated red teaming for ai applications.
- conducts automated adversarial testing against ai systems and llm applications.
- sre
- get log forwarding status
- list https destinations for a log forwarding profile.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- create a syslog destination for a log forwarding profile.
- list log forwarding profiles
- network operations
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- monitors network health, performance, and digital experience metrics.
- submit a bpa request.
- threat intelligence
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- identity and access management, tenant hierarchies, and subscription management.
- create https destination
- get a specific log forwarding profile by id.
- list monitoring tenants.
- monitored agents from autonomous dem.
- manage enterprise browser policies, user sessions, and deployments.
- manages logging infrastructure, integrations, and platform automation.
- syslog destination management for log forwarding profiles.
- get application scores
- get synthetic test results.
- list email destinations
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- bpa request operations.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- agent and endpoint scores from autonomous dem.
- malware researcher
- performance metrics from autonomous dem.
- submit bpa request
- network architect
- delete a specific log forwarding profile by id.
- list all log forwarding profiles.
- list https destinations
- digital experience monitoring, log management, and best practice assessment.
- submit a bpa request for a device.
- list monitored applications.
- logging
- bpa report retrieval.
- synthetic test results from autonomous dem.
- get bpa report checks
- bpa request status.
- list monitored agents
- platform engineer
- iam admin
- list syslog destinations for a log forwarding profile.
- monitors and remediates cloud security misconfigurations and compliance violations.
- researches threat actors, malware campaigns, and vulnerability trends.
- log forwarding profile management.
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- application experience scores from autonomous dem.
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
