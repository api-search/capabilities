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
- submit url for analysis
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- manages service accounts, roles, and access policies for platform api access.
- dns network statistics.
- search threat signatures
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- submit link for analysis
- get threat vault api usage statistics.
- manage enterprise browser policies, user sessions, and deployments.
- cloud security posture management, compliance monitoring, and workload protection.
- get advisory by cve
- palo alto networks security advisories.
- compliance team
- subscription manager
- incident responder
- enterprise browser policy management and secure browsing.
- tenant operator
- get packet captures from wildfire analysis.
- red team operator
- mssp operator
- get atp reports
- sase admin
- get release notes for threat content updates.
- submit a file for wildfire analysis.
- get dns network statistics for a given time range.
- investigates dlp incidents and manages sensitive data protection policies.
- get verdicts for multiple file hashes (max 500).
- monitors network health, performance, and digital experience metrics.
- get atp report pcaps
- list security advisories with optional filtering by severity and affected product.
- list advisories
- lookup domain
- get a security advisory by its cve identifier.
- ioc research
- list security advisories
- list affected products
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- cloud security
- proactively searches for threats and iocs across telemetry data.
- conducts automated adversarial testing against ai systems and llm applications.
- download a packet capture for a file hash from wildfire.
- sre
- download sample
- get wildfire verdicts for file hashes.
- data loss prevention, saas security monitoring, and identity security posture.
- get bulk verdicts
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- get the analysis report for a file hash.
- get security advisory
- download a malware sample from wildfire.
- submit link
- submit a url for wildfire analysis.
- manages enterprise browser policies and secure browsing configurations.
- search threat signatures by type, id, sha256, name, cve, or date range.
- manages logging infrastructure, integrations, and platform automation.
- ai runtime security scanning and automated red teaming for ai applications.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- get threat vault stats
- firewall
- get domain bulk
- get dns threat intelligence for multiple domains in bulk.
- submit a file for wildfire malware analysis.
- get analysis pcap
- bulk query domain threat intelligence.
- network security
- list palo alto networks security advisories with optional filtering by severity and affected product.
- manages multi-tenant security operations at scale for managed service providers.
- get wildfire verdicts for multiple file hashes (max 500).
- malware analysis
- get the wildfire analysis report for a file hash.
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- bulk lookup domains
- get a security advisory by cve identifier.
- executes containment, eradication, and recovery actions during security incidents.
- get advisory
- advanced threat prevention reports.
- data protection analyst
- submit a url for wildfire malware analysis.
- palo alto networks
- vulnerability manager
- get the history of a specific threat by id and type.
- xdr
- sase
- soc analyst
- get threat vault usage statistics.
- submit file for analysis
- researches threat actors, malware campaigns, and vulnerability trends.
- monitors and remediates cloud security misconfigurations and compliance violations.
- digital experience monitoring, log management, and best practice assessment.
- get a palo alto networks security advisory by its cve identifier.
- soar
- get packet captures from atp reports.
- submit a link for wildfire malware analysis.
- get analysis report
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- get verdict
- get domain
- get signature history for a specific threat.
- sd wan operator
- download a sample file by hash.
- secures ai applications with runtime scanning and vulnerability assessment.
- get the history of a specific threat signature by id and type from threat vault.
- investigates security incidents, triages alerts, and coordinates response actions.
- network architect
- get dns network stats
- iam admin
- saas security admin
- get wildfire verdicts for multiple file hashes.
- submit url
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- get the verdict for a file hash.
- get threat intelligence for a specific domain.
- list all palo alto networks products affected by security advisories.
- browser security admin
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- network operations
- ai security engineer
- threat intelligence
- get threats
- secure access service edge with remote networking, sd-wan, and zero trust access.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- get packet capture for a file hash.
- designs sase and sd-wan network architectures for secure remote access.
- enterprise it
- get dns threat intelligence for a specific domain.
- cybersecurity
- download pcap
- get dns stats
- get release notes
- get details of a specific security advisory by id.
- compliance officer
- submit a link for wildfire analysis.
- get advanced threat prevention reports.
- content release notes for threat updates.
- download a malware sample file by hash from wildfire.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- download atp pcaps
- download packet captures from atp reports in threat vault.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- get the wildfire verdict for a file hash.
- get threat intelligence for multiple domains.
- get advanced threat prevention reports from threat vault.
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- network security engineer
- vulnerability management
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- products affected by security advisories.
- submit file
- platform engineer
- designs and implements network security architectures and policies.
- manages multi-tenant hierarchies and service group configurations for mssps.
- get details of a specific palo alto networks security advisory by id.
- get a specific security advisory by id.
- analyzes suspicious files and samples for malware characteristics.
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- get release notes for threat content updates from threat vault.
- firewall policy management, network objects, and cloud-native firewall configuration.
- list all products affected by security advisories.
- search for threats by type, id, sha256, name, cve, or date range.
- query domain threat intelligence from dns security.
- threat vault api usage statistics.
- threat intel analyst
- firewall admin
- threat hunter
- identity and access management, tenant hierarchies, and subscription management.
- malware researcher
- cloud security engineer
- get threat history
- get wildfire analysis reports.
- download atp pcap files.
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
