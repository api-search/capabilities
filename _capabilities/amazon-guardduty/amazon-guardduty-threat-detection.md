---
consumed_apis:
- amazon-guardduty
description: Workflow capability for security teams using Amazon GuardDuty for AWS threat detection and response. Covers finding management, detector configuration, threat intelligence integration, and automated response workflows.
layout: capability
name: Amazon GuardDuty Threat Detection
operations:
- description: List all GuardDuty detectors
  method: GET
  name: list-detectors
  path: /v1/detectors
- description: Enable GuardDuty for an account
  method: POST
  name: create-detector
  path: /v1/detectors
- description: List threat findings
  method: GET
  name: list-findings
  path: /v1/findings
- description: Archive reviewed findings
  method: POST
  name: archive-findings
  path: /v1/findings
- description: Create a finding filter
  method: POST
  name: create-filter
  path: /v1/filters
- description: List threat intelligence sets
  method: GET
  name: list-threat-intel-sets
  path: /v1/threat-intel
personas: []
provider_name: Amazon GuardDuty
provider_slug: amazon-guardduty
search_terms:
- monitors security alerts and manages threat response workflows
- list members
- list threat findings
- get findings statistics
- enable guardduty for an account
- list trusted ip address sets excluded from threat detection
- security operations
- amazon guardduty
- list all active guardduty detectors across the account
- threat findings from guardduty analysis
- archive threat findings that have been reviewed and resolved
- archive findings
- list member accounts monitored by this guardduty administrator account
- anomaly detection
- list detectors
- list finding filters
- incident response
- machine learning
- configures guardduty detectors and threat intelligence feeds
- create a trusted ip set to exclude known safe ips from alerts
- Cloud Security Engineer
- create filter
- list all guardduty detectors
- threat intelligence feeds
- get detailed information about specific threat findings including full context
- list trusted ip sets
- create a suppression filter to reduce noise from benign findings
- compliance
- archive reviewed findings
- security
- create detector
- investigates and responds to threat findings from guardduty
- guardduty detector management
- list active threat findings detected by guardduty with severity filters
- get finding details
- monitoring
- get detector status
- create finding filter
- Security Analyst
- create trusted ip set
- aws
- list findings
- get finding statistics and severity counts for security posture overview
- list threat intelligence sets used for enhanced detection
- threat detection
- list all finding suppression filters
- create a finding filter
- get the configuration and status of a guardduty detector
- list threat intelligence sets
- finding suppression filters
- SOC Engineer
- list threat intel sets
slug: amazon-guardduty-threat-detection
tags:
- Amazon GuardDuty
- Threat Detection
- Security Operations
- Incident Response
- AWS
tools:
- description: List all active GuardDuty detectors across the account
  hints:
    openWorld: true
    readOnly: true
  name: list-detectors
- description: Get the configuration and status of a GuardDuty detector
  hints:
    readOnly: true
  name: get-detector-status
- description: List active threat findings detected by GuardDuty with severity filters
  hints:
    readOnly: true
  name: list-threat-findings
- description: Get detailed information about specific threat findings including full context
  hints:
    readOnly: true
  name: get-finding-details
- description: Archive threat findings that have been reviewed and resolved
  hints:
    readOnly: false
  name: archive-findings
- description: Create a suppression filter to reduce noise from benign findings
  hints:
    readOnly: false
  name: create-finding-filter
- description: List all finding suppression filters
  hints:
    readOnly: true
  name: list-finding-filters
- description: List trusted IP address sets excluded from threat detection
  hints:
    readOnly: true
  name: list-trusted-ip-sets
- description: Create a trusted IP set to exclude known safe IPs from alerts
  hints:
    readOnly: false
  name: create-trusted-ip-set
- description: List threat intelligence sets used for enhanced detection
  hints:
    readOnly: true
  name: list-threat-intel-sets
- description: Get finding statistics and severity counts for security posture overview
  hints:
    readOnly: true
  name: get-findings-statistics
- description: List member accounts monitored by this GuardDuty administrator account
  hints:
    readOnly: true
  name: list-members
---
