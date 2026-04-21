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
- list https destinations for a log forwarding profile.
- red team operator
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- get bpa report
- query threat data
- network architect
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- data loss prevention, saas security monitoring, and identity security posture.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- list all log forwarding profiles.
- list syslog destinations
- create email destination
- executes containment, eradication, and recovery actions during security incidents.
- get application scores
- log forwarding profile management.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- vulnerability manager
- firewall policy management, network objects, and cloud-native firewall configuration.
- get agent and endpoint scores from autonomous dem.
- sase admin
- secures ai applications with runtime scanning and vulnerability assessment.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- get performance metrics
- cybersecurity
- list monitored applications from autonomous dem.
- list email destinations
- list monitored applications
- query bandwidth data
- monitored applications from autonomous dem.
- list dem agents
- get a bpa report.
- list monitored agents from autonomous dem.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get log forwarding profile
- create an https destination for a log forwarding profile.
- get log forwarding status
- monitors and remediates cloud security misconfigurations and compliance violations.
- investigates dlp incidents and manages sensitive data protection policies.
- synthetic test results from autonomous dem.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- analyzes suspicious files and samples for malware characteristics.
- monitored agents from autonomous dem.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- conducts automated adversarial testing against ai systems and llm applications.
- list dem applications
- bpa report check details.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- create an email destination for a log forwarding profile.
- list monitoring tenants
- create log forwarding profile
- check the status of a bpa request.
- logging
- get dem agent scores
- network security engineer
- manages enterprise browser policies and secure browsing configurations.
- xdr
- ai runtime security scanning and automated red teaming for ai applications.
- enterprise browser policy management and secure browsing.
- submit a bpa request.
- list log forwarding profiles
- threat intel analyst
- log forwarding profile status.
- observability
- soar
- platform engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- list email destinations for a log forwarding profile.
- manages logging infrastructure, integrations, and platform automation.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- investigates security incidents, triages alerts, and coordinates response actions.
- list monitored agents
- ai security engineer
- subscription manager
- incident responder
- syslog destination management for log forwarding profiles.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- https destination management for log forwarding profiles.
- query aggregated application monitoring data with filters, time ranges, and grouping.
- designs and implements network security architectures and policies.
- list monitoring tenants.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- cloud security
- query aggregated application monitoring data.
- saas security admin
- create https destination
- update log forwarding profile
- email destination management for log forwarding profiles.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- submit bpa request
- monitoring
- manages multi-tenant security operations at scale for managed service providers.
- get the status of a log forwarding profile.
- manages service accounts, roles, and access policies for platform api access.
- create syslog destination
- query aggregated url monitoring data.
- get application experience scores.
- soc analyst
- identity and access management, tenant hierarchies, and subscription management.
- get bpa report checks
- get performance metrics.
- mssp operator
- network operations
- threat intelligence
- get agent scores
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- get bpa request status
- get synthetic test results from autonomous dem.
- proactively searches for threats and iocs across telemetry data.
- designs sase and sd-wan network architectures for secure remote access.
- get agent and endpoint scores.
- digital experience monitoring, log management, and best practice assessment.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- cloud security engineer
- query application data
- query aggregated license monitoring data.
- list monitored agents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- query aggregated license monitoring data with filters, time ranges, and grouping.
- query aggregated bandwidth monitoring data.
- enterprise it
- firewall
- data protection analyst
- delete a specific log forwarding profile by id.
- list all tenants available for monitoring.
- query aggregated threat monitoring data.
- create a syslog destination for a log forwarding profile.
- get dem application scores
- get dem test results
- list syslog destinations for a log forwarding profile.
- get bpa report check details.
- palo alto networks
- firewall admin
- browser security admin
- malware researcher
- iam admin
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- submit a bpa request for a device.
- agent and endpoint scores from autonomous dem.
- researches threat actors, malware campaigns, and vulnerability trends.
- get a specific log forwarding profile by id.
- network security
- list https destinations
- bpa request status.
- threat hunter
- query license data
- cloud security posture management, compliance monitoring, and workload protection.
- notifications
- query url data
- get application experience scores from autonomous dem.
- tenant operator
- sase
- get dem metrics
- application experience scores from autonomous dem.
- best practice assessment
- individual log forwarding profile operations.
- get test results
- get performance metrics from autonomous dem.
- sd wan operator
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- update a specific log forwarding profile by id.
- bpa request operations.
- create a new log forwarding profile.
- delete log forwarding profile
- compliance team
- manage enterprise browser policies, user sessions, and deployments.
- digital experience
- compliance officer
- performance metrics from autonomous dem.
- get synthetic test results.
- monitors network health, performance, and digital experience metrics.
- bpa report retrieval.
- list monitored applications.
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
