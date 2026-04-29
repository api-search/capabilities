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
- xdr
- list palo alto networks security advisories with optional filtering by severity and affected product.
- research iocs, submit malware samples, analyze dns threats, and track security advisories.
- get threat vault stats
- get analysis pcap
- manage remote networks, ztna connectors, sd-wan sites, 5g security, and service provider interconnects.
- secures ai applications with runtime scanning and vulnerability assessment.
- tenant operator
- red team operator
- firewall policy management, network objects, and cloud-native firewall configuration.
- submit a file for wildfire malware analysis.
- search for threat signatures by type, id, sha256, name, cve, or date range in threat vault.
- get the wildfire verdict for a file hash.
- submit link
- download a malware sample file by hash from wildfire.
- get analysis report
- list advisories
- manages sd-wan sites, wan interfaces, and path policies for branch connectivity.
- soar
- submit a file for wildfire analysis.
- incident detection, investigation, response, and automation across endpoints, network, and cloud.
- palo alto networks security advisories.
- get advisory by cve
- ai security engineer
- get advisory
- get threats
- get bulk verdicts
- products affected by security advisories.
- get packet captures from atp reports.
- get the verdict for a file hash.
- compliance officer
- manage cloud alerts, enforce policies, monitor compliance, scan code, and assess data security.
- sre
- submit url
- get threat intelligence for multiple domains.
- threat research, malware analysis, ioc correlation, and vulnerability tracking.
- list all palo alto networks products affected by security advisories.
- get release notes
- cloud security
- submit a link for wildfire malware analysis.
- firewall
- platform engineer
- get threat history
- get details of a specific palo alto networks security advisory by id.
- sase
- get verdict
- analyzes suspicious files and samples for malware characteristics.
- get verdicts for multiple file hashes (max 500).
- get packet captures from wildfire analysis.
- dns network statistics.
- scan ai model inputs and outputs for threats and red-team ai applications for vulnerabilities.
- download atp pcap files.
- incident responder
- designs and implements network security architectures and policies.
- identity and access management, tenant hierarchies, and subscription management.
- submit file
- get threat intelligence for a specific domain.
- ioc research
- download sample
- get details of a specific security advisory by id.
- list security advisories with optional filtering by severity and affected product.
- get release notes for threat content updates.
- get dns threat intelligence for multiple domains in bulk.
- vulnerability manager
- list security advisories
- manages prisma access, sd-wan, and ztna configurations for the sase platform.
- compliance team
- submit file for analysis
- malware analysis
- download a sample file by hash.
- download pcap
- cloud security engineer
- saas security admin
- bulk lookup domains
- list affected products
- track digital experience, aggregate security data, manage log forwarding, run assessments, and handle notifications.
- get the history of a specific threat signature by id and type from threat vault.
- manages multi-tenant security operations at scale for managed service providers.
- vulnerability management
- sd wan operator
- query domain threat intelligence from dns security.
- get dns network statistics for a given time range.
- list all products affected by security advisories.
- manage firewall objects, security rules, nat rules, and cloud ngfw rule stacks.
- content release notes for threat updates.
- submit a link for wildfire analysis.
- search threat signatures
- download packet captures from atp reports in threat vault.
- subscription manager
- get wildfire analysis reports.
- search for threats by type, id, sha256, name, cve, or date range.
- ai runtime security scanning and automated red teaming for ai applications.
- executes containment, eradication, and recovery actions during security incidents.
- proactively searches for threats and iocs across telemetry data.
- get atp report pcaps
- investigates security incidents, triages alerts, and coordinates response actions.
- get wildfire verdicts for multiple file hashes (max 500).
- researches threat actors, malware campaigns, and vulnerability trends.
- get domain
- soc analyst
- submit link for analysis
- network security
- network operations
- enterprise browser policy management and secure browsing.
- manages multi-tenant hierarchies and service group configurations for mssps.
- threat intel analyst
- monitors and remediates cloud security misconfigurations and compliance violations.
- get atp reports
- manages service accounts, roles, and access policies for platform api access.
- get advanced threat prevention reports from threat vault.
- submit url for analysis
- threat hunter
- enterprise it
- get dns threat intelligence for a specific domain.
- download atp pcaps
- browser security admin
- get the wildfire analysis report for a file hash.
- network security engineer
- get a palo alto networks security advisory by its cve identifier.
- malware researcher
- manages firewall policies, objects, and configurations across physical and virtual firewalls.
- secure access service edge with remote networking, sd-wan, and zero trust access.
- manages enterprise browser policies and secure browsing configurations.
- get a security advisory by cve identifier.
- threat vault api usage statistics.
- get a specific security advisory by id.
- get the history of a specific threat by id and type.
- manage dlp incidents, email violations, saas assets, posture checks, and identity security.
- manage enterprise browser policies, user sessions, and deployments.
- mssp operator
- get wildfire verdicts for file hashes.
- cybersecurity
- lookup domain
- network architect
- download a malware sample from wildfire.
- get signature history for a specific threat.
- get the analysis report for a file hash.
- ensures cloud infrastructure meets regulatory and industry compliance standards.
- search threat signatures by type, id, sha256, name, cve, or date range.
- digital experience monitoring, log management, and best practice assessment.
- get dns network stats
- sase admin
- designs sase and sd-wan network architectures for secure remote access.
- data protection analyst
- bulk query domain threat intelligence.
- monitors network health, performance, and digital experience metrics.
- get security advisory
- get domain bulk
- get packet capture for a file hash.
- investigate incidents, triage alerts, manage endpoints, execute response playbooks, and assess attack surface.
- palo alto networks
- submit a url for wildfire malware analysis.
- download a packet capture for a file hash from wildfire.
- get advanced threat prevention reports.
- data loss prevention, saas security monitoring, and identity security posture.
- get threat vault usage statistics.
- manage service accounts, access policies, tenant hierarchies, subscriptions, and identity data.
- firewall admin
- investigates dlp incidents and manages sensitive data protection policies.
- get release notes for threat content updates from threat vault.
- iam admin
- manages logging infrastructure, integrations, and platform automation.
- get wildfire verdicts for multiple file hashes.
- threat intelligence
- get a security advisory by its cve identifier.
- advanced threat prevention reports.
- cloud security posture management, compliance monitoring, and workload protection.
- conducts automated adversarial testing against ai systems and llm applications.
- submit a url for wildfire analysis.
- get threat vault api usage statistics.
- get dns stats
slug: threat-intelligence
source_filename: threat-intelligence.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"Palo Alto Networks Threat Intelligence\"\n  description: \"Unified threat intelligence capability for researching IOCs, submitting malware samples, analyzing DNS threats, and tracking security advisories across Threat Vault, WildFire, DNS Security, and Security Advisories.\"\n  tags:\n    - Palo Alto Networks\n    - Threat Intelligence\n    - Malware Analysis\n    - IOC Research\n    - Vulnerability Management\n  created: \"2026-04-16\"\n  modified: \"2026-04-16\"\n\nbinds:\n  - namespace: env\n    keys:\n      THREAT_VAULT_API_KEY: THREAT_VAULT_API_KEY\n      WILDFIRE_API_KEY: WILDFIRE_API_KEY\n      DNS_SECURITY_API_KEY: DNS_SECURITY_API_KEY\n\ncapability:\n  consumes:\n    - import: threat-vault\n      location: ./shared/threat-vault.yaml\n    - import: wildfire\n      location: ./shared/wildfire.yaml\n    - import: dns-security\n      location: ./shared/dns-security.yaml\n    - import: security-advisory\n      location: ./shared/security-advisory.yaml\n\
  \n  exposes:\n    - type: rest\n      port: 8081\n      namespace: threat-intel-api\n      description: \"Unified REST API for threat intelligence research.\"\n      resources:\n\n        # ── Threat Signatures (Threat Vault) ──────────────────────────────\n        - path: /v1/threats\n          name: threats\n          description: \"Search threat signatures by type, ID, SHA256, name, CVE, or date range.\"\n          operations:\n            - method: GET\n              name: get-threats\n              description: \"Search for threats by type, ID, SHA256, name, CVE, or date range.\"\n              inputParameters:\n                - name: type\n                  in: query\n                  type: string\n                  required: false\n                - name: id\n                  in: query\n                  type: string\n                  required: false\n                - name: sha256\n                  in: query\n                  type: string\n                  required: false\n\
  \                - name: name\n                  in: query\n                  type: string\n                  required: false\n                - name: cve\n                  in: query\n                  type: string\n                  required: false\n                - name: from\n                  in: query\n                  type: string\n                  required: false\n                - name: to\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"threat-vault.get-threats\"\n              with:\n                type: \"rest.type\"\n                id: \"rest.id\"\n                sha256: \"rest.sha256\"\n                name: \"rest.name\"\n                cve: \"\
  rest.cve\"\n                from: \"rest.from\"\n                to: \"rest.to\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/threats/{threat_id}/history\n          name: threat-history\n          description: \"Get signature history for a specific threat.\"\n          operations:\n            - method: GET\n              name: get-threat-history\n              description: \"Get the history of a specific threat by ID and type.\"\n              inputParameters:\n                - name: threat_id\n                  in: path\n                  type: string\n                  required: true\n                - name: type\n                  in: query\n                  type: string\n                  required: true\n                - name: offset\n                  in: query\n                  type: integer\n                  required:\
  \ false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"threat-vault.get-threat-history\"\n              with:\n                id: \"rest.threat_id\"\n                type: \"rest.type\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Advanced Threat Prevention Reports ────────────────────────────\n        - path: /v1/atp-reports\n          name: atp-reports\n          description: \"Advanced Threat Prevention reports.\"\n          operations:\n            - method: GET\n              name: get-atp-reports\n              description: \"Get Advanced Threat Prevention reports.\"\n              inputParameters:\n                - name: sha256\n                  in: query\n                  type: string\n                  required: false\n  \
  \              - name: id\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"threat-vault.get-atp-reports\"\n              with:\n                sha256: \"rest.sha256\"\n                id: \"rest.id\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/atp-reports/pcaps\n          name: atp-report-pcaps\n          description: \"Download ATP PCAP files.\"\n          operations:\n            - method: GET\n              name: get-atp-report-pcaps\n              description: \"Get packet captures from ATP reports.\"\n\
  \              inputParameters:\n                - name: sha256\n                  in: query\n                  type: string\n                  required: true\n                - name: id\n                  in: query\n                  type: string\n                  required: false\n              call: \"threat-vault.get-atp-report-pcaps\"\n              with:\n                sha256: \"rest.sha256\"\n                id: \"rest.id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Content Release Notes ─────────────────────────────────────────\n        - path: /v1/release-notes\n          name: release-notes\n          description: \"Content release notes for threat updates.\"\n          operations:\n            - method: GET\n              name: get-release-notes\n              description: \"Get release notes for threat content updates.\"\n              inputParameters:\n                - name: type\n                \
  \  in: query\n                  type: string\n                  required: true\n                - name: version\n                  in: query\n                  type: string\n                  required: false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required: false\n              call: \"threat-vault.get-release-notes\"\n              with:\n                type: \"rest.type\"\n                version: \"rest.version\"\n                offset: \"rest.offset\"\n                limit: \"rest.limit\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Threat Vault API Stats ────────────────────────────────────────\n        - path: /v1/threat-vault-stats\n          name: threat-vault-stats\n          description: \"Threat Vault API\
  \ usage statistics.\"\n          operations:\n            - method: GET\n              name: get-threat-vault-stats\n              description: \"Get Threat Vault usage statistics.\"\n              call: \"threat-vault.get-stats\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Sample Submission & Analysis (WildFire) ───────────────────────\n        - path: /v1/samples/files\n          name: submit-file\n          description: \"Submit a file for WildFire malware analysis.\"\n          operations:\n            - method: POST\n              name: submit-file\n              description: \"Submit a file for WildFire analysis.\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: file\n                  in: body\n                  type: string\n                  required: true\n              call:\
  \ \"wildfire.submit-file\"\n              with:\n                apikey: \"rest.apikey\"\n                file: \"rest.file\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/samples/urls\n          name: submit-url\n          description: \"Submit a URL for WildFire malware analysis.\"\n          operations:\n            - method: POST\n              name: submit-url\n              description: \"Submit a URL for WildFire analysis.\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: url\n                  in: body\n                  type: string\n                  required: true\n              call: \"wildfire.submit-url\"\n              with:\n                apikey: \"rest.apikey\"\n                url: \"rest.url\"\n              outputParameters:\n                - type: object\n\
  \                  mapping: \"$.\"\n\n        - path: /v1/samples/links\n          name: submit-link\n          description: \"Submit a link for WildFire malware analysis.\"\n          operations:\n            - method: POST\n              name: submit-link\n              description: \"Submit a link for WildFire analysis.\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: link\n                  in: body\n                  type: string\n                  required: true\n              call: \"wildfire.submit-link\"\n              with:\n                apikey: \"rest.apikey\"\n                link: \"rest.link\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Verdicts (WildFire) ───────────────────────────────────────────\n        - path: /v1/verdicts\n          name: verdicts\n        \
  \  description: \"Get WildFire verdicts for file hashes.\"\n          operations:\n            - method: POST\n              name: get-verdict\n              description: \"Get the verdict for a file hash.\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: hash\n                  in: body\n                  type: string\n                  required: true\n              call: \"wildfire.get-verdict\"\n              with:\n                apikey: \"rest.apikey\"\n                hash: \"rest.hash\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/verdicts/bulk\n          name: bulk-verdicts\n          description: \"Get WildFire verdicts for multiple file hashes.\"\n          operations:\n            - method: POST\n              name: get-bulk-verdicts\n              description: \"\
  Get verdicts for multiple file hashes (max 500).\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: hash\n                  in: body\n                  type: object\n                  required: true\n              call: \"wildfire.get-bulk-verdicts\"\n              with:\n                apikey: \"rest.apikey\"\n                hash: \"rest.hash\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Analysis Reports (WildFire) ───────────────────────────────────\n        - path: /v1/analysis-reports\n          name: analysis-reports\n          description: \"Get WildFire analysis reports.\"\n          operations:\n            - method: POST\n              name: get-analysis-report\n              description: \"Get the analysis report for a file hash.\"\n              inputParameters:\n      \
  \          - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: hash\n                  in: body\n                  type: string\n                  required: true\n                - name: format\n                  in: body\n                  type: string\n                  required: false\n              call: \"wildfire.get-report\"\n              with:\n                apikey: \"rest.apikey\"\n                hash: \"rest.hash\"\n                format: \"rest.format\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analysis-reports/samples\n          name: analysis-report-samples\n          description: \"Download a malware sample from WildFire.\"\n          operations:\n            - method: POST\n              name: download-sample\n              description: \"Download a sample file by hash.\"\n              inputParameters:\n\
  \                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: hash\n                  in: body\n                  type: string\n                  required: true\n              call: \"wildfire.get-sample\"\n              with:\n                apikey: \"rest.apikey\"\n                hash: \"rest.hash\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/analysis-reports/pcaps\n          name: analysis-report-pcaps\n          description: \"Get packet captures from WildFire analysis.\"\n          operations:\n            - method: POST\n              name: get-analysis-pcap\n              description: \"Get packet capture for a file hash.\"\n              inputParameters:\n                - name: apikey\n                  in: body\n                  type: string\n                  required: true\n                - name: hash\n \
  \                 in: body\n                  type: string\n                  required: true\n                - name: platform\n                  in: body\n                  type: string\n                  required: false\n              call: \"wildfire.get-pcap\"\n              with:\n                apikey: \"rest.apikey\"\n                hash: \"rest.hash\"\n                platform: \"rest.platform\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── DNS Threat Intelligence ───────────────────────────────────────\n        - path: /v1/domains\n          name: domains\n          description: \"Query domain threat intelligence from DNS Security.\"\n          operations:\n            - method: GET\n              name: get-domain\n              description: \"Get threat intelligence for a specific domain.\"\n              inputParameters:\n                - name: domain\n                  in: query\n                  type:\
  \ string\n                  required: true\n                  description: \"The domain name to query.\"\n                - name: stime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: etime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n              call: \"dns-security.get-domain\"\n              with:\n                domain: \"rest.domain\"\n                stime: \"rest.stime\"\n                etime: \"rest.etime\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/domains/bulk\n          name: domains-bulk\n          description: \"Bulk query domain threat intelligence.\"\n          operations:\n            - method: GET\n              name: get-domain-bulk\n\
  \              description: \"Get threat intelligence for multiple domains.\"\n              inputParameters:\n                - name: domains\n                  in: query\n                  type: string\n                  required: true\n                  description: \"Comma-separated list of domain names to query.\"\n                - name: stime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the query range.\"\n                - name: etime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the query range.\"\n              call: \"dns-security.get-domain-bulk\"\n              with:\n                domains: \"rest.domains\"\n                stime: \"rest.stime\"\n                etime: \"rest.etime\"\n              outputParameters:\n                - type: object\n                  mapping: \"\
  $.\"\n\n        # ── DNS Network Stats ─────────────────────────────────────────────\n        - path: /v1/dns-stats\n          name: dns-stats\n          description: \"DNS network statistics.\"\n          operations:\n            - method: GET\n              name: get-dns-stats\n              description: \"Get DNS network statistics for a given time range.\"\n              inputParameters:\n                - name: stime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"Start time for the statistics range.\"\n                - name: etime\n                  in: query\n                  type: string\n                  required: false\n                  description: \"End time for the statistics range.\"\n              call: \"dns-security.get-network-stats\"\n              with:\n                stime: \"rest.stime\"\n                etime: \"rest.etime\"\n              outputParameters:\n                -\
  \ type: object\n                  mapping: \"$.\"\n\n        # ── Security Advisories ───────────────────────────────────────────\n        - path: /v1/advisories\n          name: advisories\n          description: \"Palo Alto Networks security advisories.\"\n          operations:\n            - method: GET\n              name: list-advisories\n              description: \"List security advisories with optional filtering by severity and affected product.\"\n              inputParameters:\n                - name: severity\n                  in: query\n                  type: string\n                  required: false\n                - name: affected_product\n                  in: query\n                  type: string\n                  required: false\n                - name: sort\n                  in: query\n                  type: string\n                  required: false\n                - name: limit\n                  in: query\n                  type: integer\n                  required:\
  \ false\n                - name: offset\n                  in: query\n                  type: integer\n                  required: false\n              call: \"security-advisory.list-advisories\"\n              with:\n                severity: \"rest.severity\"\n                affected_product: \"rest.affected_product\"\n                sort: \"rest.sort\"\n                limit: \"rest.limit\"\n                offset: \"rest.offset\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n        - path: /v1/advisories/{advisory_id}\n          name: advisory-detail\n          description: \"Get a specific security advisory by ID.\"\n          operations:\n            - method: GET\n              name: get-advisory\n              description: \"Get details of a specific security advisory by ID.\"\n              inputParameters:\n                - name: advisory_id\n                  in: path\n                  type: string\n              \
  \    required: true\n              call: \"security-advisory.get-advisory\"\n              with:\n                advisory_id: \"rest.advisory_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/advisories/cve/{cve_id}\n          name: advisory-by-cve\n          description: \"Get a security advisory by CVE identifier.\"\n          operations:\n            - method: GET\n              name: get-advisory-by-cve\n              description: \"Get a security advisory by its CVE identifier.\"\n              inputParameters:\n                - name: cve_id\n                  in: path\n                  type: string\n                  required: true\n              call: \"security-advisory.get-advisory-by-cve\"\n              with:\n                cve_id: \"rest.cve_id\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        # ── Affected Products ─────────────────────────────────────────────\n\
  \        - path: /v1/affected-products\n          name: affected-products\n          description: \"Products affected by security advisories.\"\n          operations:\n            - method: GET\n              name: list-affected-products\n              description: \"List all products affected by security advisories.\"\n              call: \"security-advisory.list-affected-products\"\n              outputParameters:\n                - type: array\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9091\n      namespace: threat-intel-mcp\n      transport: http\n      description: \"MCP server for AI-assisted threat intelligence research.\"\n      tools:\n\n        # ── Threat Signature Research ─────────────────────────────────────\n        - name: search-threat-signatures\n          description: \"Search for threat signatures by type, ID, SHA256, name, CVE, or date range in Threat Vault.\"\n          hints:\n            readOnly: true\n            destructive: false\n  \
  \          idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: type\n              type: string\n              required: false\n            - name: id\n              type: string\n              required: false\n            - name: sha256\n              type: string\n              required: false\n            - name: name\n              type: string\n              required: false\n            - name: cve\n              type: string\n              required: false\n            - name: from\n              type: string\n              required: false\n            - name: to\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"threat-vault.get-threats\"\n          with:\n            type: \"tools.type\"\n            id: \"tools.id\"\n            sha256:\
  \ \"tools.sha256\"\n            name: \"tools.name\"\n            cve: \"tools.cve\"\n            from: \"tools.from\"\n            to: \"tools.to\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-threat-history\n          description: \"Get the history of a specific threat signature by ID and type from Threat Vault.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: id\n              type: string\n              required: true\n            - name: type\n              type: string\n              required: true\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"threat-vault.get-threat-history\"\
  \n          with:\n            id: \"tools.id\"\n            type: \"tools.type\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-atp-reports\n          description: \"Get Advanced Threat Prevention reports from Threat Vault.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: sha256\n              type: string\n              required: false\n            - name: id\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"threat-vault.get-atp-reports\"\n          with:\n            sha256: \"tools.sha256\"\n            id: \"\
  tools.id\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-atp-pcaps\n          description: \"Download packet captures from ATP reports in Threat Vault.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: sha256\n              type: string\n              required: true\n            - name: id\n              type: string\n              required: false\n          call: \"threat-vault.get-atp-report-pcaps\"\n          with:\n            sha256: \"tools.sha256\"\n            id: \"tools.id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-release-notes\n          description: \"Get release notes for threat content updates from Threat Vault.\"\n         \
  \ hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: type\n              type: string\n              required: true\n            - name: version\n              type: string\n              required: false\n            - name: offset\n              type: integer\n              required: false\n            - name: limit\n              type: integer\n              required: false\n          call: \"threat-vault.get-release-notes\"\n          with:\n            type: \"tools.type\"\n            version: \"tools.version\"\n            offset: \"tools.offset\"\n            limit: \"tools.limit\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-threat-vault-stats\n          description: \"Get Threat Vault API usage statistics.\"\n          hints:\n            readOnly: true\n            destructive: false\n   \
  \         idempotent: true\n            openWorld: true\n          call: \"threat-vault.get-stats\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        # ── Malware Analysis (WildFire) ───────────────────────────────────\n        - name: submit-file-for-analysis\n          description: \"Submit a file for WildFire malware analysis.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: file\n              type: string\n              required: true\n          call: \"wildfire.submit-file\"\n          with:\n            apikey: \"tools.apikey\"\n            file: \"tools.file\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-url-for-analysis\n          description:\
  \ \"Submit a URL for WildFire malware analysis.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: url\n              type: string\n              required: true\n          call: \"wildfire.submit-url\"\n          with:\n            apikey: \"tools.apikey\"\n            url: \"tools.url\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: submit-link-for-analysis\n          description: \"Submit a link for WildFire malware analysis.\"\n          hints:\n            readOnly: false\n            destructive: false\n            idempotent: false\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: link\n\
  \              type: string\n              required: true\n          call: \"wildfire.submit-link\"\n          with:\n            apikey: \"tools.apikey\"\n            link: \"tools.link\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-verdict\n          description: \"Get the WildFire verdict for a file hash.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: hash\n              type: string\n              required: true\n          call: \"wildfire.get-verdict\"\n          with:\n            apikey: \"tools.apikey\"\n            hash: \"tools.hash\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-bulk-verdicts\n          description: \"Get WildFire\
  \ verdicts for multiple file hashes (max 500).\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: hash\n              type: object\n              required: true\n          call: \"wildfire.get-bulk-verdicts\"\n          with:\n            apikey: \"tools.apikey\"\n            hash: \"tools.hash\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-analysis-report\n          description: \"Get the WildFire analysis report for a file hash.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: hash\n\
  \              type: string\n              required: true\n            - name: format\n              type: string\n              required: false\n          call: \"wildfire.get-report\"\n          with:\n            apikey: \"tools.apikey\"\n            hash: \"tools.hash\"\n            format: \"tools.format\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: download-sample\n          description: \"Download a malware sample file by hash from WildFire.\"\n          hints:\n            readOnly: true\n            destructive: false\n            idempotent: true\n            openWorld: true\n          inputParameters:\n            - name: apikey\n              type: string\n              required: true\n            - name: hash\n              type: string\n              required: true\n          call: \"wildfire.get-sample\"\n          with:\n            apikey: \"tools.apikey\"\n            hash: \"tools.hash\"\n          outputParameters:\n\
  \            - type: object\n              mapping: \"$.\"\n\n        - name: download-pcap\n          descri\n\n# --- truncated at 32 KB (38 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/threat-intelligence.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/palo-alto-networks/refs/heads/main/capabilities/threat-intelligence.yaml
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
