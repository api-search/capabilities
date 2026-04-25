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
- submit link for analysis
- palo alto networks security advisories.
- monitors and remediates cloud security misconfigurations and compliance violations.
- download atp pcaps
- network security
- get atp reports
- get advanced threat prevention reports from threat vault.
- get the verdict for a file hash.
- firewall
- get wildfire analysis reports.
- compliance team
- designs sase and sd-wan network architectures for secure remote access.
- palo alto networks
- download sample
- get advisory by cve
- saas security admin
- investigates security incidents, triages alerts, and coordinates response actions.
- cloud security
- list security advisories with optional filtering by severity and affected product.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get security advisory
- get threat history
- ai security engineer
- vulnerability management
- executes containment, eradication, and recovery actions during security incidents.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- data loss prevention, saas security monitoring, and identity security posture.
- network architect
- get release notes for threat content updates from threat vault.
- manages enterprise browser policies and secure browsing configurations.
- list all products affected by security advisories.
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- list affected products
- malware analysis
- get wildfire verdicts for file hashes.
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- get packet capture for a file hash.
- digital experience monitoring, log management, and best practice assessment.
- get threat vault api usage statistics.
- get packet captures from wildfire analysis.
- get dns network stats
- submit url
- bulk query domain threat intelligence.
- download packet captures from atp reports in threat vault.
- tenant operator
- get verdict
- download a packet capture for a file hash from wildfire.
- iam admin
- enterprise it
- lookup domain
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- submit a file for wildfire analysis.
- submit a file for wildfire malware analysis.
- get threat vault usage statistics.
- manages multi-tenant security operations at scale for managed service providers.
- firewall policy management, network objects, and cloud-native firewall configuration.
- download a malware sample from wildfire.
- get threats
- conducts automated adversarial testing against ai systems and llm applications.
- red team operator
- analyzes suspicious files and samples for malware characteristics.
- list palo alto networks security advisories with optional filtering by severity and affected product.
- sd wan operator
- download a malware sample file by hash from wildfire.
- download pcap
- proactively searches for threats and iocs across telemetry data.
- firewall admin
- get analysis pcap
- query domain threat intelligence from dns security.
- platform engineer
- manage enterprise browser policies, user sessions, and deployments.
- get the wildfire analysis report for a file hash.
- submit url for analysis
- download atp pcap files.
- get domain bulk
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- data protection analyst
- sase
- dns network statistics.
- get bulk verdicts
- list advisories
- secures ai applications with runtime scanning and vulnerability assessment.
- search threat signatures
- sre
- get dns stats
- list security advisories
- get wildfire verdicts for multiple file hashes.
- content release notes for threat updates.
- get domain
- search threat signatures by type, id, sha256, name, cve, or date range.
- products affected by security advisories.
- cloud security engineer
- manages multi-tenant hierarchies and service group configurations for mssps.
- submit a link for wildfire malware analysis.
- enterprise browser policy management and secure browsing.
- get release notes
- get threat intelligence for multiple domains.
- monitors network health, performance, and digital experience metrics.
- manages logging infrastructure, integrations, and platform automation.
- mssp operator
- submit file for analysis
- threat intel analyst
- researches threat actors, malware campaigns, and vulnerability trends.
- get the analysis report for a file hash.
- ioc research
- threat intelligence
- ai runtime security scanning and automated red teaming for ai applications.
- get dns threat intelligence for a specific domain.
- get verdicts for multiple file hashes (max 500).
- get a palo alto networks security advisory by its cve identifier.
- threat vault api usage statistics.
- threat hunter
- malware researcher
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- submit file
- submit a url for wildfire malware analysis.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- identity and access management, tenant hierarchies, and subscription management.
- vulnerability manager
- submit link
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- incident responder
- browser security admin
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- get packet captures from atp reports.
- search for threats by type, id, sha256, name, cve, or date range.
- soar
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get the wildfire verdict for a file hash.
- investigates dlp incidents and manages sensitive data protection policies.
- get a security advisory by its cve identifier.
- bulk lookup domains
- submit a link for wildfire analysis.
- cloud security posture management, compliance monitoring, and workload protection.
- download a sample file by hash.
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- subscription manager
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- get release notes for threat content updates.
- get atp report pcaps
- sase admin
- get signature history for a specific threat.
- network security engineer
- get advanced threat prevention reports.
- get analysis report
- get dns threat intelligence for multiple domains in bulk.
- get threat intelligence for a specific domain.
- network operations
- advanced threat prevention reports.
- get wildfire verdicts for multiple file hashes (max 500).
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- xdr
- get advisory
- get details of a specific palo alto networks security advisory by id.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get a security advisory by cve identifier.
- get the history of a specific threat by id and type.
- get dns network statistics for a given time range.
- manages service accounts, roles, and access policies for platform api access.
- soc analyst
- cybersecurity
- designs and implements network security architectures and policies.
- get threat vault stats
- submit a url for wildfire analysis.
- compliance officer
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get a specific security advisory by id.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get details of a specific security advisory by id.
- list all palo alto networks products affected by security advisories.
- get the history of a specific threat signature by id and type from threat vault.
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
