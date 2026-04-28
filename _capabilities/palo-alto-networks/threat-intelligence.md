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
- get wildfire verdicts for file hashes.
- sase
- get details of a specific security advisory by id.
- list affected products
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- palo alto networks security advisories.
- firewall admin
- get the verdict for a file hash.
- get release notes for threat content updates from threat vault.
- advanced threat prevention reports.
- download pcap
- soc analyst
- get domain
- submit a file for wildfire analysis.
- download atp pcap files.
- get details of a specific palo alto networks security advisory by id.
- get advisory by cve
- get atp report pcaps
- get threat vault usage statistics.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- ioc research
- sre
- get threat vault stats
- get dns threat intelligence for multiple domains in bulk.
- platform engineer
- get wildfire verdicts for multiple file hashes (max 500).
- get domain bulk
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- bulk query domain threat intelligence.
- download atp pcaps
- vulnerability management
- get security advisory
- threat intelligence
- get threat history
- submit link
- tenant operator
- ai runtime security scanning and automated red teaming for ai applications.
- submit link for analysis
- download a packet capture for a file hash from wildfire.
- manages multi-tenant hierarchies and service group configurations for mssps.
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- cloud security
- threat vault api usage statistics.
- network security
- analyzes suspicious files and samples for malware characteristics.
- data protection analyst
- malware researcher
- saas security admin
- get the history of a specific threat by id and type.
- enterprise browser policy management and secure browsing.
- monitors network health, performance, and digital experience metrics.
- get packet captures from atp reports.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- submit a url for wildfire malware analysis.
- download sample
- download a sample file by hash.
- query domain threat intelligence from dns security.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- submit a file for wildfire malware analysis.
- proactively searches for threats and iocs across telemetry data.
- compliance officer
- compliance team
- products affected by security advisories.
- get a security advisory by its cve identifier.
- list all products affected by security advisories.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- designs and implements network security architectures and policies.
- get release notes for threat content updates.
- submit a link for wildfire malware analysis.
- manages enterprise browser policies and secure browsing configurations.
- palo alto networks
- cloud security engineer
- investigates security incidents, triages alerts, and coordinates response actions.
- data loss prevention, saas security monitoring, and identity security posture.
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- xdr
- get wildfire analysis reports.
- submit a url for wildfire analysis.
- cloud security posture management, compliance monitoring, and workload protection.
- sd wan operator
- get bulk verdicts
- get release notes
- incident responder
- researches threat actors, malware campaigns, and vulnerability trends.
- get verdict
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- malware analysis
- search threat signatures by type, id, sha256, name, cve, or date range.
- executes containment, eradication, and recovery actions during security incidents.
- get the history of a specific threat signature by id and type from threat vault.
- iam admin
- manages service accounts, roles, and access policies for platform api access.
- cybersecurity
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- firewall
- list security advisories
- get analysis report
- conducts automated adversarial testing against ai systems and llm applications.
- get a security advisory by cve identifier.
- network architect
- subscription manager
- get dns threat intelligence for a specific domain.
- search for threats by type, id, sha256, name, cve, or date range.
- download a malware sample file by hash from wildfire.
- download a malware sample from wildfire.
- submit file for analysis
- get the analysis report for a file hash.
- search threat signatures
- sase admin
- submit url
- red team operator
- content release notes for threat updates.
- manage enterprise browser policies, user sessions, and deployments.
- ai security engineer
- submit a link for wildfire analysis.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- submit file
- manages logging infrastructure, integrations, and platform automation.
- dns network statistics.
- get signature history for a specific threat.
- get advanced threat prevention reports.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get threat vault api usage statistics.
- get advanced threat prevention reports from threat vault.
- investigates dlp incidents and manages sensitive data protection policies.
- get packet captures from wildfire analysis.
- get dns stats
- lookup domain
- get advisory
- enterprise it
- get dns network stats
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- list all palo alto networks products affected by security advisories.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get a specific security advisory by id.
- bulk lookup domains
- browser security admin
- monitors and remediates cloud security misconfigurations and compliance violations.
- get packet capture for a file hash.
- list security advisories with optional filtering by severity and affected product.
- download packet captures from atp reports in threat vault.
- digital experience monitoring, log management, and best practice assessment.
- get the wildfire verdict for a file hash.
- get atp reports
- threat intel analyst
- vulnerability manager
- get dns network statistics for a given time range.
- get threat intelligence for multiple domains.
- get verdicts for multiple file hashes (max 500).
- firewall policy management, network objects, and cloud-native firewall configuration.
- get wildfire verdicts for multiple file hashes.
- threat hunter
- secure access service edge with remote networking, sd-wan, and zero trust access.
- network security engineer
- get analysis pcap
- get threat intelligence for a specific domain.
- list palo alto networks security advisories with optional filtering by severity and affected product.
- get the wildfire analysis report for a file hash.
- secures ai applications with runtime scanning and vulnerability assessment.
- get threats
- soar
- list advisories
- mssp operator
- network operations
- get a palo alto networks security advisory by its cve identifier.
- submit url for analysis
- designs sase and sd-wan network architectures for secure remote access.
- manages multi-tenant security operations at scale for managed service providers.
- identity and access management, tenant hierarchies, and subscription management.
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
