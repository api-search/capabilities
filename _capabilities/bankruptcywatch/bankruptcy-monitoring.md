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
- us bankruptcy court cases and proceedings
- creditor
- bankruptcy
- legal
- lending
- list monitors
- list case claims
- Loan Officer
- Bankruptcy Attorney
- court data
- list all active bankruptcy monitoring alerts
- create a bankruptcy monitoring alert for a debtor or entity
- business or individual owed money by a bankruptcy filer
- Creditor
- lender monitoring borrowers for bankruptcy filings
- create bankruptcy monitor
- compliance
- attorney managing creditor representation in bankruptcy proceedings
- search bankruptcy cases
- file a proof of claim for a bankruptcy case
- bankruptcy case research, claims management, and automated monitoring
- automated alerts for bankruptcy filings
- list claims register for a bankruptcy case
- get detailed information about a specific bankruptcy case
- search for bankruptcy cases across all us bankruptcy court districts
- get bankruptcy case
- pacer
- retrieve docket entries for a bankruptcy case
- file proof of claim
- bankruptcywatch
- get case docket
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
