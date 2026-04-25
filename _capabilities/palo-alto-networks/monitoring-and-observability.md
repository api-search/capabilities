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
- monitors and remediates cloud security misconfigurations and compliance violations.
- monitored agents from autonomous dem.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- query aggregated application monitoring data.
- network security
- get agent and endpoint scores.
- firewall
- bpa report retrieval.
- get a bpa report.
- compliance team
- designs sase and sd-wan network architectures for secure remote access.
- palo alto networks
- saas security admin
- investigates security incidents, triages alerts, and coordinates response actions.
- cloud security
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- submit a bpa request.
- ai security engineer
- monitoring
- create email destination
- get dem test results
- executes containment, eradication, and recovery actions during security incidents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- data loss prevention, saas security monitoring, and identity security posture.
- network architect
- manages enterprise browser policies and secure browsing configurations.
- get log forwarding profile
- list monitored agents.
- list monitored applications from autonomous dem.
- get dem metrics
- synthetic test results from autonomous dem.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- create syslog destination
- get bpa report checks
- digital experience monitoring, log management, and best practice assessment.
- list monitored applications.
- query threat data
- tenant operator
- query aggregated license monitoring data.
- iam admin
- list email destinations
- enterprise it
- delete log forwarding profile
- log forwarding profile management.
- get a specific log forwarding profile by id.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- manages multi-tenant security operations at scale for managed service providers.
- firewall policy management, network objects, and cloud-native firewall configuration.
- application experience scores from autonomous dem.
- conducts automated adversarial testing against ai systems and llm applications.
- red team operator
- get the status of a log forwarding profile.
- bpa request status.
- analyzes suspicious files and samples for malware characteristics.
- sd wan operator
- query application data
- firewall admin
- proactively searches for threats and iocs across telemetry data.
- get performance metrics from autonomous dem.
- platform engineer
- manage enterprise browser policies, user sessions, and deployments.
- bpa report check details.
- list monitored agents from autonomous dem.
- syslog destination management for log forwarding profiles.
- list dem agents
- monitored applications from autonomous dem.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data protection analyst
- list all log forwarding profiles.
- sase
- query url data
- get application experience scores.
- query bandwidth data
- query aggregated bandwidth monitoring data.
- secures ai applications with runtime scanning and vulnerability assessment.
- https destination management for log forwarding profiles.
- list dem applications
- bpa request operations.
- sre
- create a new log forwarding profile.
- list monitored applications
- query license data
- cloud security engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- performance metrics from autonomous dem.
- mssp operator
- manages logging infrastructure, integrations, and platform automation.
- check the status of a bpa request.
- threat intel analyst
- observability
- researches threat actors, malware campaigns, and vulnerability trends.
- get synthetic test results.
- notifications
- create an email destination for a log forwarding profile.
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- list email destinations for a log forwarding profile.
- query aggregated license monitoring data with filters, time ranges, and grouping.
- email destination management for log forwarding profiles.
- get application experience scores from autonomous dem.
- create https destination
- create a syslog destination for a log forwarding profile.
- threat hunter
- malware researcher
- digital experience
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- submit bpa request
- get bpa report
- identity and access management, tenant hierarchies, and subscription management.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- vulnerability manager
- list monitored agents
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- incident responder
- browser security admin
- query aggregated url monitoring data.
- list all tenants available for monitoring.
- get application scores
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- agent and endpoint scores from autonomous dem.
- update log forwarding profile
- soar
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- investigates dlp incidents and manages sensitive data protection policies.
- cloud security posture management, compliance monitoring, and workload protection.
- query aggregated application monitoring data with filters, time ranges, and grouping.
- best practice assessment
- get test results
- get dem agent scores
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- subscription manager
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- create an https destination for a log forwarding profile.
- get performance metrics
- sase admin
- logging
- get performance metrics.
- network security engineer
- list monitoring tenants
- individual log forwarding profile operations.
- list syslog destinations for a log forwarding profile.
- list https destinations for a log forwarding profile.
- list monitoring tenants.
- get dem application scores
- network operations
- get bpa report check details.
- submit a bpa request for a device.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- query aggregated threat monitoring data.
- xdr
- update a specific log forwarding profile by id.
- list syslog destinations
- delete a specific log forwarding profile by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- create log forwarding profile
- manages service accounts, roles, and access policies for platform api access.
- soc analyst
- get agent scores
- cybersecurity
- designs and implements network security architectures and policies.
- log forwarding profile status.
- compliance officer
- get agent and endpoint scores from autonomous dem.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- get log forwarding status
- get bpa request status
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- list https destinations
- get synthetic test results from autonomous dem.
- list log forwarding profiles
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
