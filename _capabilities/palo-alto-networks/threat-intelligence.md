---
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
- query domain threat intelligence from dns security.
- get release notes
- content release notes for threat updates.
- get the history of a specific threat signature by id and type from threat vault.
- red team operator
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- get bulk verdicts
- get a palo alto networks security advisory by its cve identifier.
- submit file
- network architect
- get verdict
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- data loss prevention, saas security monitoring, and identity security posture.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- download a packet capture for a file hash from wildfire.
- submit a link for wildfire malware analysis.
- executes containment, eradication, and recovery actions during security incidents.
- get packet captures from wildfire analysis.
- get security advisory
- get advanced threat prevention reports from threat vault.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- vulnerability manager
- malware analysis
- firewall policy management, network objects, and cloud-native firewall configuration.
- submit a url for wildfire analysis.
- get dns threat intelligence for multiple domains in bulk.
- get threat vault stats
- sase admin
- secures ai applications with runtime scanning and vulnerability assessment.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- cybersecurity
- get wildfire analysis reports.
- get wildfire verdicts for multiple file hashes.
- get the wildfire verdict for a file hash.
- list security advisories
- get a security advisory by cve identifier.
- get threat vault api usage statistics.
- get wildfire verdicts for multiple file hashes (max 500).
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get verdicts for multiple file hashes (max 500).
- monitors and remediates cloud security misconfigurations and compliance violations.
- investigates dlp incidents and manages sensitive data protection policies.
- search for threats by type, id, sha256, name, cve, or date range.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- analyzes suspicious files and samples for malware characteristics.
- list affected products
- submit link
- download packet captures from atp reports in threat vault.
- get atp reports
- get dns network statistics for a given time range.
- submit a link for wildfire analysis.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- conducts automated adversarial testing against ai systems and llm applications.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get atp report pcaps
- get the analysis report for a file hash.
- search threat signatures
- get the wildfire analysis report for a file hash.
- download sample
- get a specific security advisory by id.
- network security engineer
- manages enterprise browser policies and secure browsing configurations.
- xdr
- get advisory by cve
- ai runtime security scanning and automated red teaming for ai applications.
- enterprise browser policy management and secure browsing.
- threat intel analyst
- list advisories
- platform engineer
- soar
- submit url
- get analysis pcap
- download a sample file by hash.
- get advisory
- manages multi-tenant hierarchies and service group configurations for mssps.
- manages logging infrastructure, integrations, and platform automation.
- investigates security incidents, triages alerts, and coordinates response actions.
- list security advisories with optional filtering by severity and affected product.
- subscription manager
- ai security engineer
- incident responder
- designs and implements network security architectures and policies.
- bulk query domain threat intelligence.
- submit link for analysis
- download pcap
- get dns stats
- submit a file for wildfire malware analysis.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- cloud security
- get the history of a specific threat by id and type.
- get threat intelligence for a specific domain.
- palo alto networks security advisories.
- saas security admin
- get threats
- get advanced threat prevention reports.
- list all palo alto networks products affected by security advisories.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- get wildfire verdicts for file hashes.
- submit url for analysis
- get threat intelligence for multiple domains.
- download a malware sample from wildfire.
- manages multi-tenant security operations at scale for managed service providers.
- manages service accounts, roles, and access policies for platform api access.
- get a security advisory by its cve identifier.
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- soc analyst
- identity and access management, tenant hierarchies, and subscription management.
- mssp operator
- get packet captures from atp reports.
- network operations
- submit file for analysis
- download atp pcap files.
- threat intelligence
- lookup domain
- sre
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- list palo alto networks security advisories with optional filtering by severity and affected product.
- proactively searches for threats and iocs across telemetry data.
- designs sase and sd-wan network architectures for secure remote access.
- download atp pcaps
- get dns network stats
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- get domain bulk
- dns network statistics.
- get the verdict for a file hash.
- cloud security engineer
- digital experience monitoring, log management, and best practice assessment.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get release notes for threat content updates from threat vault.
- get dns threat intelligence for a specific domain.
- enterprise it
- firewall
- data protection analyst
- ioc research
- get threat history
- get release notes for threat content updates.
- get domain
- palo alto networks
- firewall admin
- browser security admin
- submit a url for wildfire malware analysis.
- iam admin
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- researches threat actors, malware campaigns, and vulnerability trends.
- network security
- threat vault api usage statistics.
- threat hunter
- cloud security posture management, compliance monitoring, and workload protection.
- products affected by security advisories.
- vulnerability management
- bulk lookup domains
- list all products affected by security advisories.
- get analysis report
- advanced threat prevention reports.
- tenant operator
- sase
- search threat signatures by type, id, sha256, name, cve, or date range.
- download a malware sample file by hash from wildfire.
- submit a file for wildfire analysis.
- get details of a specific palo alto networks security advisory by id.
- sd wan operator
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- get details of a specific security advisory by id.
- compliance team
- manage enterprise browser policies, user sessions, and deployments.
- get packet capture for a file hash.
- compliance officer
- get threat vault usage statistics.
- monitors network health, performance, and digital experience metrics.
- get signature history for a specific threat.
- malware researcher
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
