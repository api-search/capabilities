---
consumed_apis:
- bankruptcywatch-pacer
description: BankruptcyWatch bankruptcy monitoring and case management workflow for creditors, lenders, and legal teams. Covers case search, docket retrieval, claims management, Proof of Claim filing, and automated bankruptcy monitoring alerts.
layout: capability
name: BankruptcyWatch Bankruptcy Monitoring
operations: []
personas: []
provider_name: BankruptcyWatch
provider_slug: bankruptcywatch
search_terms:
- list monitors
- list claims register for a bankruptcy case
- attorney managing creditor representation in bankruptcy proceedings
- lending
- bankruptcywatch
- create bankruptcy monitor
- bankruptcy
- bankruptcy case research, claims management, and automated monitoring
- court data
- create a bankruptcy monitoring alert for a debtor or entity
- retrieve docket entries for a bankruptcy case
- business or individual owed money by a bankruptcy filer
- legal
- file a proof of claim for a bankruptcy case
- us bankruptcy court cases and proceedings
- get case docket
- file proof of claim
- get bankruptcy case
- automated alerts for bankruptcy filings
- pacer
- compliance
- list all active bankruptcy monitoring alerts
- Creditor
- Bankruptcy Attorney
- search for bankruptcy cases across all us bankruptcy court districts
- creditor
- Loan Officer
- list case claims
- search bankruptcy cases
- get detailed information about a specific bankruptcy case
- lender monitoring borrowers for bankruptcy filings
slug: bankruptcy-monitoring
tags:
- BankruptcyWatch
- Bankruptcy
- PACER
- Creditor
- Legal
tools:
- description: Search for bankruptcy cases across all US bankruptcy court districts
  hints:
    openWorld: true
    readOnly: true
  name: search-bankruptcy-cases
- description: Get detailed information about a specific bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: get-bankruptcy-case
- description: Retrieve docket entries for a bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: get-case-docket
- description: List claims register for a bankruptcy case
  hints:
    openWorld: false
    readOnly: true
  name: list-case-claims
- description: File a Proof of Claim for a bankruptcy case
  hints:
    openWorld: false
    readOnly: false
  name: file-proof-of-claim
- description: Create a bankruptcy monitoring alert for a debtor or entity
  hints:
    openWorld: false
    readOnly: false
  name: create-bankruptcy-monitor
- description: List all active bankruptcy monitoring alerts
  hints:
    openWorld: false
    readOnly: true
  name: list-monitors
---
