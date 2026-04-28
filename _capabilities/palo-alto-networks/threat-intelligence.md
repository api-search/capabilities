---
categories: []
consumed_apis:
- threat-vault
- wildfire
- dns-security
- security-advisory
description: Unified threat intelligence capability for researching IOCs, submitting malware samples, analyzing DNS threats, and tracking security advisories across Threat Vault, WildFire, DNS Security, and Security Advisories.
layout: capability
name: Palo Alto Networks Threat Intelligence
operations:
- description: Search for threats by type, ID, SHA256, name, CVE, or date range.
  method: GET
  name: get-threats
  path: /v1/threats
- description: Get the history of a specific threat by ID and type.
  method: GET
  name: get-threat-history
  path: /v1/threats/{threat_id}/history
- description: Get Advanced Threat Prevention reports.
  method: GET
  name: get-atp-reports
  path: /v1/atp-reports
- description: Get packet captures from ATP reports.
  method: GET
  name: get-atp-report-pcaps
  path: /v1/atp-reports/pcaps
- description: Get release notes for threat content updates.
  method: GET
  name: get-release-notes
  path: /v1/release-notes
- description: Get Threat Vault usage statistics.
  method: GET
  name: get-threat-vault-stats
  path: /v1/threat-vault-stats
- description: Submit a file for WildFire analysis.
  method: POST
  name: submit-file
  path: /v1/samples/files
- description: Submit a URL for WildFire analysis.
  method: POST
  name: submit-url
  path: /v1/samples/urls
- description: Submit a link for WildFire analysis.
  method: POST
  name: submit-link
  path: /v1/samples/links
- description: Get the verdict for a file hash.
  method: POST
  name: get-verdict
  path: /v1/verdicts
- description: Get verdicts for multiple file hashes (max 500).
  method: POST
  name: get-bulk-verdicts
  path: /v1/verdicts/bulk
- description: Get the analysis report for a file hash.
  method: POST
  name: get-analysis-report
  path: /v1/analysis-reports
- description: Download a sample file by hash.
  method: POST
  name: download-sample
  path: /v1/analysis-reports/samples
- description: Get packet capture for a file hash.
  method: POST
  name: get-analysis-pcap
  path: /v1/analysis-reports/pcaps
- description: Get threat intelligence for a specific domain.
  method: GET
  name: get-domain
  path: /v1/domains
- description: Get threat intelligence for multiple domains.
  method: GET
  name: get-domain-bulk
  path: /v1/domains/bulk
- description: Get DNS network statistics for a given time range.
  method: GET
  name: get-dns-stats
  path: /v1/dns-stats
- description: List security advisories with optional filtering by severity and affected product.
  method: GET
  name: list-advisories
  path: /v1/advisories
- description: Get details of a specific security advisory by ID.
  method: GET
  name: get-advisory
  path: /v1/advisories/{advisory_id}
- description: Get a security advisory by its CVE identifier.
  method: GET
  name: get-advisory-by-cve
  path: /v1/advisories/cve/{cve_id}
- description: List all products affected by security advisories.
  method: GET
  name: list-affected-products
  path: /v1/affected-products
personas:
- description: Researches threat actors, malware campaigns, and vulnerability trends.
  id: threat-intel-analyst
  name: Threat Intelligence Analyst
- description: Analyzes suspicious files and samples for malware characteristics.
  id: malware-researcher
  name: Malware Researcher
provider_name: Palo Alto Networks
provider_slug: palo-alto-networks
search_terms:
- firewall policy management, network objects, and cloud-native firewall configuration.
- sase admin
- get details of a specific security advisory by id.
- designs and implements network security architectures and policies.
- download a sample file by hash.
- threat vault api usage statistics.
- designs sase and sd-wan network architectures for secure remote access.
- get dns network stats
- list all palo alto networks products affected by security advisories.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- list all products affected by security advisories.
- list palo alto networks security advisories with optional filtering by severity and affected product.
- monitors and remediates cloud security misconfigurations and compliance violations.
- get packet capture for a file hash.
- get wildfire analysis reports.
- get advisory by cve
- manages multi-tenant security operations at scale for managed service providers.
- get the verdict for a file hash.
- mssp operator
- search threat signatures
- bulk lookup domains
- threat hunter
- network architect
- manages multi-tenant hierarchies and service group configurations for mssps.
- download a malware sample file by hash from wildfire.
- get the analysis report for a file hash.
- incident responder
- network operations
- download packet captures from atp reports in threat vault.
- get dns threat intelligence for multiple domains in bulk.
- submit file for analysis
- dns network statistics.
- get analysis pcap
- sase
- get advanced threat prevention reports from threat vault.
- malware analysis
- submit a link for wildfire malware analysis.
- get wildfire verdicts for multiple file hashes (max 500).
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- submit link for analysis
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- iam admin
- soar
- executes containment, eradication, and recovery actions during security incidents.
- get a security advisory by cve identifier.
- products affected by security advisories.
- analyzes suspicious files and samples for malware characteristics.
- manage enterprise browser policies, user sessions, and deployments.
- manages logging infrastructure, integrations, and platform automation.
- palo alto networks
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get dns stats
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- download pcap
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- cybersecurity
- vulnerability manager
- get the wildfire verdict for a file hash.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- malware researcher
- manages enterprise browser policies and secure browsing configurations.
- get a security advisory by its cve identifier.
- get threat intelligence for multiple domains.
- download sample
- lookup domain
- get wildfire verdicts for file hashes.
- get threat vault stats
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- manages service accounts, roles, and access policies for platform api access.
- firewall
- cloud security engineer
- data protection analyst
- list security advisories
- get dns network statistics for a given time range.
- soc analyst
- proactively searches for threats and iocs across telemetry data.
- palo alto networks security advisories.
- red team operator
- get wildfire verdicts for multiple file hashes.
- get advisory
- bulk query domain threat intelligence.
- get atp reports
- submit url
- threat intelligence
- get verdict
- list security advisories with optional filtering by severity and affected product.
- get the history of a specific threat signature by id and type from threat vault.
- secures ai applications with runtime scanning and vulnerability assessment.
- digital experience monitoring, log management, and best practice assessment.
- subscription manager
- submit a url for wildfire analysis.
- download a malware sample from wildfire.
- query domain threat intelligence from dns security.
- ai runtime security scanning and automated red teaming for ai applications.
- get details of a specific palo alto networks security advisory by id.
- get release notes
- compliance officer
- network security engineer
- cloud security
- data loss prevention, saas security monitoring, and identity security posture.
- get release notes for threat content updates from threat vault.
- advanced threat prevention reports.
- saas security admin
- enterprise browser policy management and secure browsing.
- firewall admin
- tenant operator
- submit a url for wildfire malware analysis.
- threat intel analyst
- cloud security posture management, compliance monitoring, and workload protection.
- submit a file for wildfire malware analysis.
- get domain
- investigates dlp incidents and manages sensitive data protection policies.
- search threat signatures by type, id, sha256, name, cve, or date range.
- content release notes for threat updates.
- compliance team
- get a specific security advisory by id.
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- get dns threat intelligence for a specific domain.
- get security advisory
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- download atp pcaps
- investigates security incidents, triages alerts, and coordinates response actions.
- get release notes for threat content updates.
- list affected products
- get verdicts for multiple file hashes (max 500).
- get domain bulk
- conducts automated adversarial testing against ai systems and llm applications.
- get packet captures from wildfire analysis.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- vulnerability management
- submit link
- get analysis report
- submit url for analysis
- search for threats by type, id, sha256, name, cve, or date range.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- ai security engineer
- get atp report pcaps
- browser security admin
- get the wildfire analysis report for a file hash.
- submit a file for wildfire analysis.
- get threat vault usage statistics.
- get a palo alto networks security advisory by its cve identifier.
- submit a link for wildfire analysis.
- monitors network health, performance, and digital experience metrics.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- get threats
- get the history of a specific threat by id and type.
- get threat vault api usage statistics.
- submit file
- xdr
- get packet captures from atp reports.
- get signature history for a specific threat.
- get bulk verdicts
- ioc research
- get threat intelligence for a specific domain.
- sd wan operator
- list advisories
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- download atp pcap files.
- sre
- download a packet capture for a file hash from wildfire.
- platform engineer
- enterprise it
- identity and access management, tenant hierarchies, and subscription management.
- get advanced threat prevention reports.
- get threat history
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
slug: threat-intelligence
tags:
- Palo Alto Networks
- Threat Intelligence
- Malware Analysis
- IOC Research
- Vulnerability Management
tools:
- description: Search for threat signatures by type, ID, SHA256, name, CVE, or date range in Threat Vault.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: search-threat-signatures
- description: Get the history of a specific threat signature by ID and type from Threat Vault.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-threat-history
- description: Get Advanced Threat Prevention reports from Threat Vault.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-atp-reports
- description: Download packet captures from ATP reports in Threat Vault.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-atp-pcaps
- description: Get release notes for threat content updates from Threat Vault.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-release-notes
- description: Get Threat Vault API usage statistics.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-threat-vault-stats
- description: Submit a file for WildFire malware analysis.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-file-for-analysis
- description: Submit a URL for WildFire malware analysis.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-url-for-analysis
- description: Submit a link for WildFire malware analysis.
  hints:
    destructive: false
    idempotent: false
    openWorld: true
    readOnly: false
  name: submit-link-for-analysis
- description: Get the WildFire verdict for a file hash.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-verdict
- description: Get WildFire verdicts for multiple file hashes (max 500).
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-bulk-verdicts
- description: Get the WildFire analysis report for a file hash.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-analysis-report
- description: Download a malware sample file by hash from WildFire.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-sample
- description: Download a packet capture for a file hash from WildFire.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: download-pcap
- description: Get DNS threat intelligence for a specific domain.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: lookup-domain
- description: Get DNS threat intelligence for multiple domains in bulk.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: bulk-lookup-domains
- description: Get DNS network statistics for a given time range.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-dns-network-stats
- description: List Palo Alto Networks security advisories with optional filtering by severity and affected product.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-security-advisories
- description: Get details of a specific Palo Alto Networks security advisory by ID.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-security-advisory
- description: Get a Palo Alto Networks security advisory by its CVE identifier.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: get-advisory-by-cve
- description: List all Palo Alto Networks products affected by security advisories.
  hints:
    destructive: false
    idempotent: true
    openWorld: true
    readOnly: true
  name: list-affected-products
---
