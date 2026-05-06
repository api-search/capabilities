---
categories: []
consumed_apis: []
description: For more details, checkout https://docs.projectdiscovery.io/api-reference/editor/scan
layout: capability
name: PDCP API
operations:
- description: Search Templates
  method: GET
  name: get-v2-template-search
  path: /v2/template/search
- description: Upload Templates
  method: POST
  name: post-v2-template-user-upload
  path: /v2/template/user/upload
- description: Bulk Update User Template
  method: PATCH
  name: patch-v2-template-user-upload
  path: /v2/template/user/upload
- description: Get Scan List
  method: GET
  name: get-v1-scans
  path: /v1/scans
- description: Create Scan
  method: POST
  name: post-v1-scans
  path: /v1/scans
- description: Delete Scan in bulk
  method: DELETE
  name: delete-v1-scans
  path: /v1/scans
- description: Get Scan
  method: GET
  name: get-v1-scans-scan-id
  path: /v1/scans/{scan_id}
- description: Delete Scan
  method: DELETE
  name: delete-v1-scans-scan-id
  path: /v1/scans/{scan_id}
- description: Update Scan
  method: PATCH
  name: patch-v1-scans-scan-id
  path: /v1/scans/{scan_id}
- description: Import OSS Scan
  method: POST
  name: post-v1-scans-import
  path: /v1/scans/import
- description: Search user by name or email
  method: GET
  name: get-v1-admin-user-search
  path: /v1/admin/user/search
- description: Get billing assets for a user
  method: GET
  name: get-v1-admin-user-billing-assets
  path: /v1/admin/user/billing_assets
- description: Get audit logs for a user
  method: GET
  name: get-v1-admin-user-audit-logs
  path: /v1/admin/user/audit_logs
- description: change owner for a team (New owner will take control of the existing owner's subscription)
  method: POST
  name: post-v1-admin-team-change-owner
  path: /v1/admin/team/change_owner
- description: Set Scan token for user
  method: POST
  name: post-v1-admin-scan-token
  path: /v1/admin/scan/token
- description: Update Scan token for user
  method: PATCH
  name: patch-v1-admin-scan-token
  path: /v1/admin/scan/token
- description: Get Token Usage (admin)
  method: GET
  name: get-v1-admin-scan-token
  path: /v1/admin/scan/token
- description: Stop Scan
  method: POST
  name: post-v1-scans-scan-id-stop
  path: /v1/scans/{scan_id}/stop
- description: Rescan scan
  method: POST
  name: post-v1-scans-scan-id-rescan
  path: /v1/scans/{scan_id}/rescan
- description: Get Scan Vulnerability
  method: GET
  name: get-v1-scans-vuln-vulnid
  path: /v1/scans/vuln/{vuln_id}
- description: Get Scan Results
  method: GET
  name: get-v1-scans-result-scanid
  path: /v1/scans/result/{scanId}
- description: Get Vulnerability Changelogs
  method: GET
  name: get-v1-scans-vuln-vuln-id-changelogs
  path: /v1/scans/vuln/{vuln_id}/changelogs
- description: Get all Vulnerability Changelogs
  method: GET
  name: get-v1-scans-vuln-changelogs
  path: /v1/scans/vuln/changelogs
- description: Get All Results
  method: GET
  name: get-v1-results
  path: /v1/scans/results
- description: Get All Scan Stats
  method: GET
  name: get-v1-scans-stats
  path: /v1/scans/stats
- description: Retest vulnerability
  method: POST
  name: post-v1-scans-vuln-id-retest
  path: /v1/scans/{vuln_id}/retest
- description: Get Scans Result Filters
  method: GET
  name: get-v1-scans-results-filters
  path: /v1/scans/results/filters
- description: Get Results Stats
  method: GET
  name: get-v1-scans-results-stats
  path: /v1/scans/results/stats
- description: Get Scan Schedules
  method: GET
  name: get-v1-scans-schedule
  path: /v1/scans/schedule
- description: Set Scan Schedule
  method: POST
  name: post-v1-scans-schedule
  path: /v1/scans/schedule
- description: Delete Scan Schedule
  method: DELETE
  name: delete-v1-scans-schedule
  path: /v1/scans/schedule
- description: Get All Retest
  method: GET
  name: get-v1-retest
  path: /v1/retest
- description: Create Retest
  method: POST
  name: post-v1-retest
  path: /v1/retest
- description: Get Retest Vulnerability
  method: GET
  name: get-v1-retest-vuln-id
  path: /v1/retest/{vuln_id}
- description: Get Asset List
  method: GET
  name: get-v1-assets
  path: /v1/assets
- description: Upload Asset
  method: POST
  name: post-v1-assets
  path: /v1/assets
- description: Get Asset Metadata
  method: GET
  name: get-v1-assets-assetid
  path: /v1/assets/{asset_Id}
- description: Delete Asset
  method: DELETE
  name: delete-v1-assets-asset-id
  path: /v1/assets/{asset_Id}
- description: Update Asset Metadata
  method: PATCH
  name: patch-v1-assets-asset-id
  path: /v1/assets/{asset_Id}
- description: Get Asset Content
  method: GET
  name: get-v1-assets-id-contents
  path: /v1/assets/{asset_id}/contents
- description: Update Asset Content
  method: PATCH
  name: patch-v1-assets-asset-id-contents
  path: /v1/assets/{asset_id}/contents
- description: Get User Notification Preferences
  method: GET
  name: get-v1-user-notification-preference
  path: /v1/user/notification_preference
- description: Update User Notification Preferences
  method: PATCH
  name: patch-v1-user-notification-preference
  path: /v1/user/notification_preference
- description: Create Feedback
  method: POST
  name: post-v1-user-feedback
  path: /v1/user/feedback
- description: Email user deletion verification code
  method: POST
  name: post-v1-user-delete-code
  path: /v1/user/delete/code
- description: Get User Profile
  method: GET
  name: get-v1-user
  path: /v1/user
- description: Delete user from system along with all data
  method: DELETE
  name: delete-v1-user
  path: /v1/user
- description: Get API Key
  method: GET
  name: get-v1-user-apikey
  path: /v1/user/apikey
- description: Create API Key
  method: POST
  name: post-v1-user-apikey
  path: /v1/user/apikey
- description: Delete API Key
  method: DELETE
  name: delete-v1-user-apikey
  path: /v1/user/apikey
- description: Get User Setup Statistics
  method: GET
  name: get-v1-user-setup-stats
  path: /v1/user/onboarding_status
- description: Get Billing Assets details
  method: GET
  name: get-v1-user-billing-assets
  path: /v1/user/billing_assets
- description: Get Promocode Details
  method: GET
  name: get-v1-user-promocode
  path: /v1/user/promo_code
- description: Apply Promocode
  method: POST
  name: post-v1-user-promocode
  path: /v1/user/promo_code
- description: Rotate API Key
  method: POST
  name: post-v1-user-apikey-rotate
  path: /v1/user/apikey/rotate
- description: Request Domain Verification
  method: POST
  name: post-v1-user-domain-verification-request
  path: /v1/user/domain-verification/request
- description: Request Domain Delete
  method: DELETE
  name: delete-v1-user-domain-verification-request
  path: /v1/user/domain-verification/request
- description: Confirm Domain Verification
  method: POST
  name: post-v1-user-domain-verification-confirm
  path: /v1/user/domain-verification/confirm
- description: Get Domain Verification Status
  method: GET
  name: get-v1-user-domain-verification-status
  path: /v1/user/domain-verification/status
- description: Get Public Template List
  method: GET
  name: get-v1-template-public
  path: /v1/template/public
personas: []
provider_name: Nuclei
provider_slug: nuclei
search_terms:
- get all vulnerability changelogs
- get billing assets details
- confirm domain verification
- patch v1 user notification preference
- patch v1 scans scan id
- get scan vulnerability
- get v1 scans result scanid
- delete v1 user
- get promocode details
- post v1 user promocode
- delete v1 user domain verification request
- import oss scan
- get scan
- get v1 user notification preference
- get billing assets for a user
- delete api key
- update scan token for user
- get user profile
- api
- delete v1 scans
- get v1 admin user search
- get results stats
- search user by name or email
- post v1 scans scan id rescan
- get v1 scans vuln vulnid
- delete v1 scans schedule
- get v1 user setup stats
- update scan
- get user notification preferences
- bulk update user template
- patch v1 assets asset id
- rotate api key
- post v1 assets
- get scan schedules
- get scans result filters
- get v1 results
- update asset content
- upload asset
- get api key
- set scan schedule
- update asset metadata
- get v2 template search
- get v1 scans vuln vuln id changelogs
- create scan
- delete v1 user apikey
- open source
- delete v1 scans scan id
- get v1 retest vuln id
- request domain verification
- get asset list
- get v1 user billing assets
- post v1 user apikey rotate
- get v1 assets assetid
- get v1 user apikey
- apply promocode
- post v1 user feedback
- request domain delete
- post v1 scans scan id stop
- nuclei
- get scan list
- post v1 retest
- get token usage (admin)
- get vulnerability changelogs
- get v1 scans results filters
- email user deletion verification code
- get public template list
- get all retest
- get v1 template public
- get domain verification status
- get user setup statistics
- patch v2 template user upload
- get v1 scans scan id
- post v1 user domain verification request
- post v1 scans vuln id retest
- get v1 scans results stats
- post v1 scans
- get all results
- post v1 scans schedule
- get retest vulnerability
- patch v1 admin scan token
- create api key
- get scan results
- get v1 admin user billing assets
- dast
- post v1 admin scan token
- get audit logs for a user
- delete scan
- testing
- get all scan stats
- post v1 user apikey
- post v2 template user upload
- vulnerability scanner
- get v1 assets
- get v1 scans vuln changelogs
- delete scan schedule
- get v1 user promocode
- get v1 assets id contents
- create retest
- get v1 scans
- upload templates
- post v1 scans import
- get v1 user domain verification status
- search templates
- security testing
- get v1 user
- retest vulnerability
- delete scan in bulk
- change owner for a team (new owner will take control of the existing owner's subscription)
- delete asset
- update user notification preferences
- delete user from system along with all data
- stop scan
- get asset metadata
- get v1 admin user audit logs
- get v1 scans stats
- post v1 user domain verification confirm
- get v1 admin scan token
- get v1 scans schedule
- patch v1 assets asset id contents
- delete v1 assets asset id
- create feedback
- get v1 retest
- post v1 user delete code
- rescan scan
- set scan token for user
- post v1 admin team change owner
- get asset content
slug: nuclei-capability
source_filename: nuclei-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: PDCP API\n  description: For more details, checkout https://docs.projectdiscovery.io/api-reference/editor/scan\n  tags:\n  - Nuclei\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: nuclei\n    baseUri: https://api.projectdiscovery.io\n    description: PDCP API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-API-Key\n      value: '{{NUCLEI_TOKEN}}'\n    resources:\n    - name: v2-template-search\n      path: /v2/template/search\n      operations:\n      - name: get-v2-template-search\n        method: GET\n        description: Search Templates\n        inputParameters:\n        - name: scope\n          in: query\n          type: string\n          description: Scope of templates to search (public or private)\n        - name: limit\n          in: query\n          type: integer\n          description: Maximum number of results to return\n\
  \        - name: offset\n          in: query\n          type: integer\n          description: Number of results to skip for pagination\n        - name: fields\n          in: query\n          type: string\n          description: Specific fields to return in the response\n        - name: sort_asc\n          in: query\n          type: string\n          description: Field to sort results in ascending order\n        - name: sort_desc\n          in: query\n          type: string\n          description: Field to sort results in descending order\n        - name: q\n          in: query\n          type: string\n          description: Search query string\n        - name: highlight\n          in: query\n          type: boolean\n          description: Whether to highlight search matches in results\n        - name: facet_size\n          in: query\n          type: integer\n          description: Number of facets to return in the response\n        - name: X-Team-Id\n          in: header\n          type:\
  \ string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-template-user-upload\n      path: /v2/template/user/upload\n      operations:\n      - name: post-v2-template-user-upload\n        method: POST\n        description: Upload Templates\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v2-template-user-upload\n        method: PATCH\n        description: Bulk Update User Template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans\n      path: /v1/scans\n      operations:\n      - name: get-v1-scans\n        method: GET\n        description: Get Scan List\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: number of scan-status results\
  \ to skip\n        - name: limit\n          in: query\n          type: integer\n          description: number of scan-status results to fetch\n        - name: search\n          in: query\n          type: string\n          description: search term for running scans\n        - name: status\n          in: query\n          type: string\n          description: filter by status (failed, finished, queued, running, starting, uploaded, scheduled)\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description: comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: is_internal\n          in: query\n          type: boolean\n          description: filter by internal scans\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve\
  \ the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-scans\n        method: POST\n        description: Create Scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-scans\n        method: DELETE\n        description: Delete Scan in bulk\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: v1-scans-scan-id\n      path: /v1/scans/{scan_id}\n      operations:\n      - name: get-v1-scans-scan-id\n        method: GET\n        description: Get Scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-scans-scan-id\n        method: DELETE\n        description: Delete Scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v1-scans-scan-id\n        method:\
  \ PATCH\n        description: Update Scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-import\n      path: /v1/scans/import\n      operations:\n      - name: post-v1-scans-import\n        method: POST\n        description: Import OSS Scan\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-admin-user-search\n      path: /v1/admin/user/search\n\
  \      operations:\n      - name: get-v1-admin-user-search\n        method: GET\n        description: Search user by name or email\n        inputParameters:\n        - name: q\n          in: query\n          type: string\n          description: name or email filter\n        - name: plan\n          in: query\n          type: string\n          description: plan filter\n        - name: offset\n          in: query\n          type: integer\n          description: offset for pagination\n        - name: limit\n          in: query\n          type: integer\n          description: limit for pagination\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-admin-user-billing-assets\n      path: /v1/admin/user/billing_assets\n      operations:\n\
  \      - name: get-v1-admin-user-billing-assets\n        method: GET\n        description: Get billing assets for a user\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          required: true\n          description: email of the user\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-admin-user-audit-logs\n      path: /v1/admin/user/audit_logs\n      operations:\n      - name: get-v1-admin-user-audit-logs\n        method: GET\n        description: Get audit logs for a user\n        inputParameters:\n        - name: email\n          in: query\n          type: string\n          description: email of the user\n        - name: user_id\n          in: query\n          type: integer\n          description: user id of the user\n        - name: offset\n          in: query\n          type: integer\n          description: offset for pagination\n        - name:\
  \ path_name\n          in: query\n          type: string\n          description: path name filter\n        - name: status_code\n          in: query\n          type: string\n          description: status code filter comma separated e.g status_code=200,404\n        - name: status_code_not\n          in: query\n          type: string\n          description: status code not filter comma separated e.g status_code_not=200,404\n        - name: limit\n          in: query\n          type: integer\n          description: limit for pagination\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-admin-team-change-owner\n      path: /v1/admin/team/change_owner\n      operations:\n      - name: post-v1-admin-team-change-owner\n        method: POST\n        description: change owner for a team (New owner will take control of the existing owner's subscription)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: v1-admin-scan-token\n      path: /v1/admin/scan/token\n      operations:\n      - name: post-v1-admin-scan-token\n        method: POST\n        description: Set Scan token for user\n        inputParameters:\n        - name: method\n          in: query\n          type: string\n          required: true\n          description: '''create'' or ''update'' mode'\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patch-v1-admin-scan-token\n        method: PATCH\n        description: Update Scan token for user\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from:\
  \ https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: get-v1-admin-scan-token\n        method: GET\n        description: Get Token Usage (admin)\n        inputParameters:\n        - name: user_id\n          in: query\n          type: integer\n          required: true\n          description: user id to get scan token usage for\n        - name: email\n          in: query\n          type: string\n          description: email to get scan token usage for\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-scan-id-stop\n      path: /v1/scans/{scan_id}/stop\n      operations:\n      - name:\
  \ post-v1-scans-scan-id-stop\n        method: POST\n        description: Stop Scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-scan-id-rescan\n      path: /v1/scans/{scan_id}/rescan\n      operations:\n      - name: post-v1-scans-scan-id-rescan\n        method: POST\n        description: Rescan scan\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-vuln-vuln-id\n      path: /v1/scans/vuln/{vuln_id}\n\
  \      operations:\n      - name: get-v1-scans-vuln-vulnid\n        method: GET\n        description: Get Scan Vulnerability\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-result-scanid\n      path: /v1/scans/result/{scanId}\n      operations:\n      - name: get-v1-scans-result-scanid\n        method: GET\n        description: Get Scan Results\n        inputParameters:\n        - name: severity\n          in: query\n          type: string\n          description: comma separated severity e.g. severity=info,high\n        - name: search\n          in: query\n          type: string\n          description: search term\n        - name: limit\n          in: query\n          type: integer\n      \
  \    description: number of results\n        - name: offset\n          in: query\n          type: integer\n          description: number of results to skip\n        - name: templates\n          in: query\n          type: string\n          description: comma separated templates e.g. templates=tech-detect,azure-takeover\n        - name: hosts\n          in: query\n          type: string\n          description: comma separated host e.g. hosts=https://example.com,https://x.com\n        - name: domain\n          in: query\n          type: string\n          description: comma separated domain names e.g-> domain=domain1.com,domain2.com\n        - name: port\n          in: query\n          type: string\n          description: comma separated ports e.g. ports=80,443\n        - name: time\n          in: query\n          type: string\n          description: filter by time ( last_day, last_week, last_month )\n        - name: vuln_status\n          in: query\n          type: string\n          description:\
  \ comma separated vuln_status e.g vuln_status=open,fixed\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description: comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: asset_metadata\n          in: query\n          type: boolean\n          description: Asset details for the vulnerability\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-vuln-vuln-id-changelogs\n      path: /v1/scans/vuln/{vuln_id}/changelogs\n      operations:\n      - name: get-v1-scans-vuln-vuln-id-changelogs\n        method:\
  \ GET\n        description: Get Vulnerability Changelogs\n        inputParameters:\n        - name: time\n          in: query\n          type: string\n          description: time filter to select\n        - name: event_type\n          in: query\n          type: string\n          description: comma separated event_type e.g. event_type=vul_status,vul_status_change\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description: comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: limit\n          in: query\n          type: integer\n          description: number of results to get\n        - name: offset\n          in: query\n          type: integer\n          description: number of results to skip\n        - name: X-Team-Id\n          in: header\n          type: string\n\
  \          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-vuln-changelogs\n      path: /v1/scans/vuln/changelogs\n      operations:\n      - name: get-v1-scans-vuln-changelogs\n        method: GET\n        description: Get all Vulnerability Changelogs\n        inputParameters:\n        - name: time\n          in: query\n          type: string\n          description: time filter to select\n        - name: event_type\n          in: query\n          type: string\n          description: comma separated event_type e.g. event_type=vul_status,vul_status_change\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description:\
  \ comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: limit\n          in: query\n          type: integer\n          description: number of results to get\n        - name: offset\n          in: query\n          type: integer\n          description: number of results to skip\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-results\n      path: /v1/scans/results\n      operations:\n      - name: get-v1-results\n        method: GET\n        description: Get All Results\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: number of results to skip\n        - name: limit\n          in: query\n          type: integer\n    \
  \      description: number of results to get\n        - name: severity\n          in: query\n          type: string\n          description: string separated by comma e.g. info,high\n        - name: search\n          in: query\n          type: string\n          description: search term\n        - name: host\n          in: query\n          type: string\n          description: comma separated host e.g. hosts=https://example.com,https://x.com\n        - name: domain\n          in: query\n          type: string\n          description: comma separated domain names e.g-> domain=domain1.com,domain2.com\n        - name: port\n          in: query\n          type: string\n          description: comma separated ports e.g. ports=80,443\n        - name: templates\n          in: query\n          type: string\n          description: comma separated templates e.g. templates=tech-detect,azure-takeover\n        - name: time\n          in: query\n          type: string\n          description: filter by time\
  \ ( last_day, last_week, last_month )\n        - name: vuln_status\n          in: query\n          type: string\n          description: comma separated vuln_status e.g vuln_status=open,fixed\n        - name: tags\n          in: query\n          type: string\n          description: comma separated tags e.g tags=xss,cve\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description: comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: is_ticket\n          in: query\n          type: boolean\n          description: Return the records that have issue trackers\n        - name: labels\n          in: query\n          type: string\n          description: filter by comma separated labels e.g labels=p1,p2\n        - name: category\n          in: query\n          type: string\n\
  \          description: filter by comma separated categories e.g category=cve,xss\n        - name: is_regression\n          in: query\n          type: boolean\n          description: filter by is_regression\n        - name: is_internal\n          in: query\n          type: boolean\n          description: filter by is_internal (internal vs external hosts)\n        - name: asset_metadata\n          in: query\n          type: boolean\n          description: Asset details for the vulnerability\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-stats\n      path: /v1/scans/stats\n      operations:\n      - name: get-v1-scans-stats\n        method: GET\n        description: Get All Scan Stats\n        inputParameters:\n    \
  \    - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-vuln-id-retest\n      path: /v1/scans/{vuln_id}/retest\n      operations:\n      - name: post-v1-scans-vuln-id-retest\n        method: POST\n        description: Retest vulnerability\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-results-filters\n      path: /v1/scans/results/filters\n      operations:\n      - name: get-v1-scans-results-filters\n        method: GET\n        description:\
  \ Get Scans Result Filters\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: The number of items to skip before starting to collect the result set\n        - name: limit\n          in: query\n          type: integer\n          description: The numbers of items to return\n        - name: scan_id\n          in: query\n          type: string\n          description: specific scan_id results filters\n        - name: severity\n          in: query\n          type: string\n          description: comma separated severity e.g. severities=info,high\n        - name: templates\n          in: query\n          type: string\n          description: comma separated templates e.g. templates=tech-detect,azure-takeover\n        - name: host\n          in: query\n          type: string\n          description: comma separated host e.g. hosts=https://example.com,https://x.com\n        - name: domain\n          in: query\n          type: string\n\
  \          description: comma separated domain names e.g-> domain=domain1.com,domain2.com\n        - name: port\n          in: query\n          type: string\n          description: comma separated ports e.g. ports=80,443\n        - name: search\n          in: query\n          type: string\n          description: search term\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: type of filter\n        - name: time\n          in: query\n          type: string\n          description: filter by time ( last_day, last_week, last_month )\n        - name: vuln_status\n          in: query\n          type: string\n          description: comma separated vuln_status e.g vuln_status=open,fixed\n        - name: sort_asc\n          in: query\n          type: string\n          description: comma separated ascending sorting e.g sort_asc=created_at,severity\n        - name: sort_desc\n          in: query\n          type: string\n          description:\
  \ comma separated descending sorting e.g sort_desc=created_at,severity\n        - name: tags\n          in: query\n          type: string\n          description: comma separated tags e.g tags=xss,cve\n        - name: not_hosts\n          in: query\n          type: string\n          description: comma separated hosts that should not be returned e.g. not_hosts=https://example.com,https://x.com\n        - name: not_severity\n          in: query\n          type: string\n          description: comma separated severity that should not be returned e.g. not_severity=info,high\n        - name: not_templates\n          in: query\n          type: string\n          description: comma separated templates that should not be returned e.g. not_templates=tech-detect,azure-takeover\n        - name: labels\n          in: query\n          type: string\n          description: filter by comma separated labels e.g labels=p1,p2\n        - name: category\n          in: query\n          type: string\n         \
  \ description: filter by comma separated categories e.g category=cve,xss\n        - name: is_regression\n          in: query\n          type: boolean\n          description: filter by is_regression\n        - name: is_internal\n          in: query\n          type: boolean\n          description: filter by is_internal (internal vs external hosts)\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        - name: start_date\n          in: query\n          type: string\n          description: time filter start date\n        - name: end_date\n          in: query\n          type: string\n          description: time filter end date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-results-stats\n      path: /v1/scans/results/stats\n      operations:\n      - name: get-v1-scans-results-stats\n\
  \        method: GET\n        description: Get Results Stats\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: The number of items to skip before starting to collect the result set\n        - name: limit\n          in: query\n          type: integer\n          description: The numbers of items to return\n        - name: host\n          in: query\n          type: string\n          description: comma separated host e.g. hosts=https://example.com,https://x.com\n        - name: domain\n          in: query\n          type: string\n          description: comma separated domain names e.g-> domain=domain1.com,domain2.com\n        - name: port\n          in: query\n          type: string\n          description: comma separated ports e.g. ports=80,443\n        - name: templates\n          in: query\n          type: string\n          description: comma separated templates e.g. templates=tech-detect,azure-takeover\n        - name:\
  \ severity\n          in: query\n          type: string\n          description: comma separated severity e.g. severities=info,high\n        - name: search\n          in: query\n          type: string\n          description: search term\n        - name: scan_id\n          in: query\n          type: string\n          description: specific scan_id results filters\n        - name: time\n          in: query\n          type: string\n          description: filter by time ( last_day, last_week, last_month )\n        - name: vuln_status\n          in: query\n          type: string\n          description: comma separated vuln_status e.g vuln_status=open,fixed\n        - name: tags\n          in: query\n          type: string\n          description: comma separated tags e.g tags=xss,cve\n        - name: not_hosts\n          in: query\n          type: string\n          description: comma separated hosts that should not be returned e.g. not_hosts=https://example.com,https://x.com\n        - name: not_severity\n\
  \          in: query\n          type: string\n          description: comma separated severity that should not be returned e.g. not_severity=info,high\n        - name: not_templates\n          in: query\n          type: string\n          description: comma separated templates that should not be returned e.g. not_templates=tech-detect,azure-takeover\n        - name: labels\n          in: query\n          type: string\n          description: filter by comma separated labels e.g labels=p1,p2\n        - name: category\n          in: query\n          type: string\n          description: filter by comma separated categories e.g category=cve,xss\n        - name: is_regression\n          in: query\n          type: boolean\n          description: filter by is_regression\n        - name: is_internal\n          in: query\n          type: boolean\n          description: filter by is_internal (internal vs external hosts)\n        - name: X-Team-Id\n          in: header\n          type: string\n    \
  \      description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        - name: start_date\n          in: query\n          type: string\n          description: time filter start date\n        - name: end_date\n          in: query\n          type: string\n          description: time filter end date\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-scans-schedule\n      path: /v1/scans/schedule\n      operations:\n      - name: get-v1-scans-schedule\n        method: GET\n        description: Get Scan Schedules\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-scans-schedule\n\
  \        method: POST\n        description: Set Scan Schedule\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: delete-v1-scans-schedule\n        method: DELETE\n        description: Delete Scan Schedule\n        inputParameters:\n        - name: scan_id\n          in: query\n          type: string\n          required: true\n          description: scan_id of schedule to be deleted\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-retest\n\
  \      path: /v1/retest\n      operations:\n      - name: get-v1-retest\n        method: GET\n        description: Get All Retest\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          required: true\n          description: number of results to skip\n        - name: limit\n          in: query\n          type: integer\n          required: true\n          description: number of results\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: post-v1-retest\n        method: POST\n        description: Create Retest\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-retest-vuln-id\n      path: /v1/retest/{vuln_id}\n      operations:\n      - name: get-v1-retest-vuln-id\n        method: GET\n        description: Get Retest Vulnerability\n        inputParameters:\n        - name: X-Team-Id\n          in: header\n          type: string\n          description: 'Retrieve the Team ID from: https://cloud.projectdiscovery.io/settings/team'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v1-\n\n# --- truncated at 32 KB (97 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/nuclei/refs/heads/main/capabilities/nuclei-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/nuclei/refs/heads/main/capabilities/nuclei-capability.yaml
tags:
- Nuclei
- API
tools:
- description: Search Templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v2-template-search
- description: Upload Templates
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v2-template-user-upload
- description: Bulk Update User Template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v2-template-user-upload
- description: Get Scan List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans
- description: Create Scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans
- description: Delete Scan in bulk
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-scans
- description: Get Scan
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-scan-id
- description: Delete Scan
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-scans-scan-id
- description: Update Scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-scans-scan-id
- description: Import OSS Scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans-import
- description: Search user by name or email
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-admin-user-search
- description: Get billing assets for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-admin-user-billing-assets
- description: Get audit logs for a user
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-admin-user-audit-logs
- description: change owner for a team (New owner will take control of the existing owner's subscription)
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-admin-team-change-owner
- description: Set Scan token for user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-admin-scan-token
- description: Update Scan token for user
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-admin-scan-token
- description: Get Token Usage (admin)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-admin-scan-token
- description: Stop Scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans-scan-id-stop
- description: Rescan scan
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans-scan-id-rescan
- description: Get Scan Vulnerability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-vuln-vulnid
- description: Get Scan Results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-result-scanid
- description: Get Vulnerability Changelogs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-vuln-vuln-id-changelogs
- description: Get all Vulnerability Changelogs
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-vuln-changelogs
- description: Get All Results
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-results
- description: Get All Scan Stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-stats
- description: Retest vulnerability
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans-vuln-id-retest
- description: Get Scans Result Filters
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-results-filters
- description: Get Results Stats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-results-stats
- description: Get Scan Schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-scans-schedule
- description: Set Scan Schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-scans-schedule
- description: Delete Scan Schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-scans-schedule
- description: Get All Retest
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-retest
- description: Create Retest
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-retest
- description: Get Retest Vulnerability
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-retest-vuln-id
- description: Get Asset List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-assets
- description: Upload Asset
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-assets
- description: Get Asset Metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-assets-assetid
- description: Delete Asset
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-assets-asset-id
- description: Update Asset Metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-assets-asset-id
- description: Get Asset Content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-assets-id-contents
- description: Update Asset Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-assets-asset-id-contents
- description: Get User Notification Preferences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-notification-preference
- description: Update User Notification Preferences
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patch-v1-user-notification-preference
- description: Create Feedback
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-feedback
- description: Email user deletion verification code
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-delete-code
- description: Get User Profile
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user
- description: Delete user from system along with all data
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-user
- description: Get API Key
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-apikey
- description: Create API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-apikey
- description: Delete API Key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-user-apikey
- description: Get User Setup Statistics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-setup-stats
- description: Get Billing Assets details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-billing-assets
- description: Get Promocode Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-promocode
- description: Apply Promocode
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-promocode
- description: Rotate API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-apikey-rotate
- description: Request Domain Verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-domain-verification-request
- description: Request Domain Delete
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: delete-v1-user-domain-verification-request
- description: Confirm Domain Verification
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-v1-user-domain-verification-confirm
- description: Get Domain Verification Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-user-domain-verification-status
- description: Get Public Template List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-v1-template-public
---
