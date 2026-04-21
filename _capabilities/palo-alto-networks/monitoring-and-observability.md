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
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list email destinations
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- investigates dlp incidents and manages sensitive data protection policies.
- list syslog destinations
- xdr
- update a specific log forwarding profile by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- list dem agents
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- get dem metrics
- query bandwidth data
- secures ai applications with runtime scanning and vulnerability assessment.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get dem agent scores
- agent and endpoint scores from autonomous dem.
- monitors network health, performance, and digital experience metrics.
- get agent and endpoint scores from autonomous dem.
- query aggregated url monitoring data with filters, time ranges, and grouping.
- delete log forwarding profile
- analyzes suspicious files and samples for malware characteristics.
- delete a specific log forwarding profile by id.
- manages enterprise browser policies and secure browsing configurations.
- firewall policy management, network objects, and cloud-native firewall configuration.
- sre
- bpa report retrieval.
- get performance metrics.
- query aggregated bandwidth monitoring data.
- log forwarding profile management.
- monitoring
- get a bpa report.
- logging
- query aggregated threat monitoring data.
- create an email destination for a log forwarding profile.
- create syslog destination
- create https destination
- query aggregated application monitoring data.
- check the status of a bpa request.
- create email destination
- designs sase and sd-wan network architectures for secure remote access.
- vulnerability manager
- soar
- firewall admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- tenant operator
- get performance metrics from autonomous dem.
- digital experience
- soc analyst
- manages service accounts, roles, and access policies for platform api access.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data loss prevention, saas security monitoring, and identity security posture.
- submit bpa request
- get bpa report checks
- query aggregated license monitoring data with filters, time ranges, and grouping.
- submit a bpa request.
- cloud security posture management, compliance monitoring, and workload protection.
- query aggregated license monitoring data.
- get bpa report
- threat intelligence
- get synthetic test results from autonomous dem.
- ai security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- bpa request status.
- compliance team
- get dem application scores
- individual log forwarding profile operations.
- enterprise it
- get synthetic test results.
- incident responder
- list monitoring tenants
- subscription manager
- malware researcher
- list monitored applications
- network operations
- manage enterprise browser policies, user sessions, and deployments.
- get the status of a log forwarding profile.
- conducts automated adversarial testing against ai systems and llm applications.
- list dem applications
- threat intel analyst
- firewall
- create an https destination for a log forwarding profile.
- browser security admin
- list log forwarding profiles
- list monitored applications from autonomous dem.
- notifications
- query license data
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- threat hunter
- get test results
- query aggregated url monitoring data.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- list monitored applications.
- list https destinations
- compliance officer
- submit a bpa request for a device.
- get log forwarding profile
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get bpa request status
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- ai runtime security scanning and automated red teaming for ai applications.
- saas security admin
- manages multi-tenant security operations at scale for managed service providers.
- list syslog destinations for a log forwarding profile.
- query url data
- get application scores
- digital experience monitoring, log management, and best practice assessment.
- list monitoring tenants.
- data protection analyst
- list all log forwarding profiles.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- platform engineer
- cloud security
- list email destinations for a log forwarding profile.
- network architect
- proactively searches for threats and iocs across telemetry data.
- red team operator
- query application data
- application experience scores from autonomous dem.
- email destination management for log forwarding profiles.
- monitored agents from autonomous dem.
- syslog destination management for log forwarding profiles.
- query threat data
- query aggregated application monitoring data with filters, time ranges, and grouping.
- performance metrics from autonomous dem.
- get bpa report check details.
- create a syslog destination for a log forwarding profile.
- bpa request operations.
- executes containment, eradication, and recovery actions during security incidents.
- researches threat actors, malware campaigns, and vulnerability trends.
- observability
- list all tenants available for monitoring.
- sase
- https destination management for log forwarding profiles.
- cybersecurity
- get application experience scores from autonomous dem.
- manages multi-tenant hierarchies and service group configurations for mssps.
- list monitored agents from autonomous dem.
- palo alto networks
- query aggregated threat monitoring data with filters, time ranges, and grouping.
- identity and access management, tenant hierarchies, and subscription management.
- get a specific log forwarding profile by id.
- get log forwarding status
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- synthetic test results from autonomous dem.
- monitored applications from autonomous dem.
- cloud security engineer
- designs and implements network security architectures and policies.
- bpa report check details.
- best practice assessment
- create log forwarding profile
- log forwarding profile status.
- list monitored agents
- get performance metrics
- mssp operator
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- sase admin
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- update log forwarding profile
- iam admin
- enterprise browser policy management and secure browsing.
- create a new log forwarding profile.
- network security
- sd wan operator
- manages logging infrastructure, integrations, and platform automation.
- get agent and endpoint scores.
- get application experience scores.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- get dem test results
- list monitored agents.
- query aggregated bandwidth monitoring data with filters, time ranges, and grouping.
- list https destinations for a log forwarding profile.
- get agent scores
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- network security engineer
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
