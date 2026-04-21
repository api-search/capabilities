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
- security operations
- list trusted ip sets
- archive reviewed findings
- list threat findings
- list findings
- list members
- machine learning
- get the configuration and status of a guardduty detector
- get detailed information about specific threat findings including full context
- list detectors
- finding suppression filters
- list threat intelligence sets used for enhanced detection
- list threat intelligence sets
- investigates and responds to threat findings from guardduty
- get findings statistics
- archive findings
- Cloud Security Engineer
- security
- create a suppression filter to reduce noise from benign findings
- list all finding suppression filters
- create a trusted ip set to exclude known safe ips from alerts
- incident response
- get detector status
- archive threat findings that have been reviewed and resolved
- create finding filter
- Security Analyst
- threat detection
- guardduty detector management
- create trusted ip set
- create filter
- create a finding filter
- threat findings from guardduty analysis
- compliance
- create detector
- list all guardduty detectors
- enable guardduty for an account
- list finding filters
- amazon guardduty
- get finding statistics and severity counts for security posture overview
- SOC Engineer
- list member accounts monitored by this guardduty administrator account
- monitoring
- get finding details
- monitors security alerts and manages threat response workflows
- aws
- configures guardduty detectors and threat intelligence feeds
- anomaly detection
- list trusted ip address sets excluded from threat detection
- list all active guardduty detectors across the account
- list active threat findings detected by guardduty with severity filters
- list threat intel sets
- threat intelligence feeds
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
