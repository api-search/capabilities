---
categories: []
consumed_apis: []
description: Unified API for QuantCDN Admin and QuantCloud Platform services
layout: capability
name: QuantCDN API
operations:
- description: List schedules for a crawler
  method: GET
  name: crawlerschedules-list
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules
- description: Add a new schedule
  method: POST
  name: crawlerschedules-add
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules
- description: Delete a schedule
  method: DELETE
  name: crawlerschedules-delete
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules/{crawler_schedule}
- description: Show a specific schedule
  method: GET
  name: crawlerschedules-show
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules/{crawler_schedule}
- description: Edit a schedule
  method: PATCH
  name: crawlerschedules-edit
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules/{crawler_schedule}
- description: List crawlers for the project
  method: GET
  name: crawlers-list
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers
- description: Create a new crawler
  method: POST
  name: crawlers-create
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers
- description: Delete a crawler
  method: DELETE
  name: crawlers-delete
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}
- description: Get details of a single crawler
  method: GET
  name: crawlers-read
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}
- description: Update a crawler
  method: PATCH
  name: crawlers-update
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}
- description: Run a crawler
  method: POST
  name: crawlers-run
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/run
- description: Get all runs for a crawler
  method: GET
  name: crawlers-getruns
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/runs
- description: Get a run by ID
  method: GET
  name: crawlers-getrunbyid
  path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/runs/{run_id}
- description: Delete custom headers
  method: DELETE
  name: headers-delete
  path: /api/v2/organizations/{organization}/projects/{project}/custom-headers
- description: List custom headers for a project
  method: GET
  name: headers-list
  path: /api/v2/organizations/{organization}/projects/{project}/custom-headers
- description: Create or update custom headers
  method: POST
  name: headers-create
  path: /api/v2/organizations/{organization}/projects/{project}/custom-headers
- description: List all domains for a project
  method: GET
  name: domains-list
  path: /api/v2/organizations/{organization}/projects/{project}/domains
- description: Add a new domain
  method: POST
  name: domains-create
  path: /api/v2/organizations/{organization}/projects/{project}/domains
- description: Delete a domain
  method: DELETE
  name: domains-delete
  path: /api/v2/organizations/{organization}/projects/{project}/domains/{domain}
- description: Get details of a single domain
  method: GET
  name: domains-read
  path: /api/v2/organizations/{organization}/projects/{project}/domains/{domain}
- description: Renew the SSL certificate for a domain
  method: POST
  name: domains-renew
  path: /api/v2/organizations/{organization}/projects/{project}/domains/{domain}/renew
- description: List key-value stores
  method: GET
  name: kv-list
  path: /api/v2/organizations/{organization}/projects/{project}/kv
- description: Add a kv store
  method: POST
  name: kv-create
  path: /api/v2/organizations/{organization}/projects/{project}/kv
- description: Delete a kv store
  method: DELETE
  name: kv-delete
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}
- description: Get a kv store
  method: GET
  name: kv-show
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}
- description: Unlink a KV store from this project
  method: DELETE
  name: kv-unlink-from-project
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/link
- description: Link a KV store to another project
  method: POST
  name: kv-link-to-project
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/link
- description: List items in a kv store
  method: GET
  name: kv-items-list
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items
- description: Add an item to a kv store
  method: POST
  name: kv-items-create
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items
- description: Delete an item from a kv store
  method: DELETE
  name: kv-items-delete
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items/{key}
- description: Get an item from a kv store
  method: GET
  name: kv-items-show
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items/{key}
- description: Update an item in a kv store
  method: PUT
  name: kv-items-update
  path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items/{key}
- description: Get hourly metrics
  method: GET
  name: gethourlymetrics
  path: /v2/organizations/{organization}/projects/{project}/metrics/hourly
- description: Get daily metrics
  method: GET
  name: getdailymetrics
  path: /v2/organizations/{organization}/projects/{project}/metrics/daily
- description: Get monthly metrics
  method: GET
  name: getmonthlymetrics
  path: /v2/organizations/{organization}/projects/{project}/metrics/monthly
- description: Retrieve all organizations
  method: GET
  name: organizations-list
  path: /api/v2/organizations
- description: Get details of a single organization
  method: GET
  name: organizations-read
  path: /api/v2/organizations/{organization}
- description: Retrieve all projects for an organization
  method: GET
  name: projects-list
  path: /api/v2/organizations/{organization}/projects
- description: Create a new project
  method: POST
  name: projects-create
  path: /api/v2/organizations/{organization}/projects
- description: Delete a project
  method: DELETE
  name: projects-delete
  path: /api/v2/organizations/{organization}/projects/{project}
- description: Get details of a single project
  method: GET
  name: projects-read
  path: /api/v2/organizations/{organization}/projects/{project}
- description: Update a project
  method: PATCH
  name: projects-update
  path: /api/v2/organizations/{organization}/projects/{project}
- description: Purge cache via URL or cache keys
  method: POST
  name: purge-create
  path: /api/v2/organizations/{organization}/projects/{project}/purge
- description: List authentication rules
  method: GET
  name: rulesauth-list
  path: /api/v2/organizations/{organization}/projects/{project}/rules/auth
- description: Create an authentication rule
  method: POST
  name: rulesauth-create
  path: /api/v2/organizations/{organization}/projects/{project}/rules/auth
- description: Delete an authentication rule
  method: DELETE
  name: rulesauth-delete
  path: /api/v2/organizations/{organization}/projects/{project}/rules/auth/{rule}
- description: Get details of an authentication rule
  method: GET
  name: rulesauth-read
  path: /api/v2/organizations/{organization}/projects/{project}/rules/auth/{rule}
- description: Update an authentication rule
  method: PATCH
  name: rulesauth-update
  path: /api/v2/organizations/{organization}/projects/{project}/rules/auth/{rule}
- description: List bot challenge rules
  method: GET
  name: rulesbotchallenge-list
  path: /api/v2/organizations/{organization}/projects/{project}/rules/bot-challenge
- description: Create a bot challenge rule
  method: POST
  name: rulesbotchallenge-create
  path: /api/v2/organizations/{organization}/projects/{project}/rules/bot-challenge
- description: Delete a bot challenge rule
  method: DELETE
  name: rulesbotchallenge-delete
  path: /api/v2/organizations/{organization}/projects/{project}/rules/bot-challenge/{rule}
- description: Get details of a bot challenge rule
  method: GET
  name: rulesbotchallenge-read
  path: /api/v2/organizations/{organization}/projects/{project}/rules/bot-challenge/{rule}
- description: Update a bot challenge rule
  method: PATCH
  name: rulesbotchallenge-update
  path: /api/v2/organizations/{organization}/projects/{project}/rules/bot-challenge/{rule}
- description: List content filter rules
  method: GET
  name: rulescontentfilter-list
  path: /api/v2/organizations/{organization}/projects/{project}/rules/content-filter
- description: Create a content filter rule
  method: POST
  name: rulescontentfilter-create
  path: /api/v2/organizations/{organization}/projects/{project}/rules/content-filter
- description: Delete a content filter rule
  method: DELETE
  name: rulescontentfilter-delete
  path: /api/v2/organizations/{organization}/projects/{project}/rules/content-filter/{rule}
- description: Get details of a content filter rule
  method: GET
  name: rulescontentfilter-read
  path: /api/v2/organizations/{organization}/projects/{project}/rules/content-filter/{rule}
- description: Update a content filter rule
  method: PATCH
  name: rulescontentfilter-update
  path: /api/v2/organizations/{organization}/projects/{project}/rules/content-filter/{rule}
- description: List custom response rules
  method: GET
  name: rulescustomresponse-list
  path: /api/v2/organizations/{organization}/projects/{project}/rules/custom-response
- description: Create a custom response rule
  method: POST
  name: rulescustomresponse-create
  path: /api/v2/organizations/{organization}/projects/{project}/rules/custom-response
personas: []
provider_name: QuantCDN
provider_slug: quantcdn
search_terms:
- gethourlymetrics
- crawlers getruns
- ai inference
- kv items update
- projects list
- rulesauth delete
- rulescontentfilter list
- show a specific schedule
- api
- retrieve all projects for an organization
- edit a schedule
- crawlers delete
- list custom response rules
- edge computing
- getdailymetrics
- organizations list
- crawlerschedules edit
- kv unlink from project
- crawlers read
- list bot challenge rules
- unlink a kv store from this project
- create a content filter rule
- get details of a single project
- rulesauth create
- get details of a content filter rule
- get an item from a kv store
- quantcdn
- domains list
- update a crawler
- add a new schedule
- organizations read
- kv items delete
- crawlers update
- domains create
- link a kv store to another project
- list content filter rules
- purge create
- projects update
- create or update custom headers
- list all domains for a project
- add a kv store
- delete a kv store
- projects read
- crawlerschedules add
- get a run by id
- headers list
- rulesbotchallenge list
- kv link to project
- delete a content filter rule
- get monthly metrics
- rulesbotchallenge read
- rulesauth read
- projects delete
- create a custom response rule
- get details of a single crawler
- rulescontentfilter update
- update an item in a kv store
- update a project
- projects create
- get details of a single domain
- rulescontentfilter read
- update a content filter rule
- update a bot challenge rule
- key-value storage
- rulescontentfilter delete
- list items in a kv store
- kv items show
- list crawlers for the project
- get a kv store
- kv create
- waf
- delete a domain
- get all runs for a crawler
- kv show
- renew the ssl certificate for a domain
- crawlerschedules delete
- kv items list
- kv items create
- delete a schedule
- domains renew
- delete custom headers
- rulesauth update
- update an authentication rule
- add an item to a kv store
- delete an item from a kv store
- dns
- cdn
- list custom headers for a project
- list key-value stores
- crawlers getrunbyid
- run a crawler
- delete a bot challenge rule
- get details of an authentication rule
- rulesbotchallenge update
- delete a project
- create a new crawler
- jamstack
- delete an authentication rule
- rulescustomresponse create
- rulesbotchallenge create
- headers create
- domains delete
- kv delete
- get hourly metrics
- headers delete
- create an authentication rule
- add a new domain
- edge
- rulescustomresponse list
- purge cache via url or cache keys
- rulesbotchallenge delete
- list schedules for a crawler
- kv list
- get details of a bot challenge rule
- create a bot challenge rule
- delete a crawler
- crawlers run
- domains read
- crawlers create
- create a new project
- crawlers list
- static hosting
- crawlerschedules list
- list authentication rules
- retrieve all organizations
- rulesauth list
- rulescontentfilter create
- get daily metrics
- crawlerschedules show
- get details of a single organization
- getmonthlymetrics
slug: quantcdn-capability
source_filename: quantcdn-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: QuantCDN API\n  description: Unified API for QuantCDN Admin and QuantCloud Platform services\n  tags:\n  - Quantcdn\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: quantcdn\n    baseUri: https://dashboard.quantcdn.io\n    description: QuantCDN API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{QUANTCDN_TOKEN}}'\n    resources:\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules\n      operations:\n      - name: crawlerschedules-list\n        method: GET\n        description: List schedules for a crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n        - name: project\n          in: path\n          type: string\n          required: true\n        - name: crawler\n\
  \          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlerschedules-add\n        method: POST\n        description: Add a new schedule\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/schedules/{crawler_schedule}\n\
  \      operations:\n      - name: crawlerschedules-delete\n        method: DELETE\n        description: Delete a schedule\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        - name: crawler_schedule\n          in: path\n          type: string\n          required: true\n          description: Crawler schedule identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlerschedules-show\n        method: GET\n        description: Show a specific schedule\n        inputParameters:\n        - name:\
  \ organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        - name: crawler_schedule\n          in: path\n          type: string\n          required: true\n          description: Crawler schedule identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlerschedules-edit\n        method: PATCH\n        description: Edit a schedule\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n         \
  \ in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        - name: crawler_schedule\n          in: path\n          type: string\n          required: true\n          description: Crawler schedule identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers\n      operations:\n      - name: crawlers-list\n        method: GET\n        description: List crawlers for the project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in:\
  \ path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlers-create\n        method: POST\n        description: Create a new crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}\n      operations:\n      - name: crawlers-delete\n        method: DELETE\n        description:\
  \ Delete a crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: The UUID of the crawler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlers-read\n        method: GET\n        description: Get details of a single crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project\
  \ identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: The UUID of the crawler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: crawlers-update\n        method: PATCH\n        description: Update a crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: The UUID of the crawler\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n\
  \      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/run\n      operations:\n      - name: crawlers-run\n        method: POST\n        description: Run a crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/runs\n      operations:\n      - name: crawlers-getruns\n        method: GET\n\
  \        description: Get all runs for a crawler\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/crawlers/{crawler}/runs/{run_id}\n      operations:\n      - name: crawlers-getrunbyid\n        method: GET\n        description: Get a run by ID\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n\
  \          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: crawler\n          in: path\n          type: string\n          required: true\n          description: Crawler identifier\n        - name: run_id\n          in: path\n          type: integer\n          required: true\n          description: Run identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/custom-headers\n      operations:\n      - name: headers-delete\n        method: DELETE\n        description: Delete custom headers\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n\
  \          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: headers-list\n        method: GET\n        description: List custom headers for a project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: headers-create\n        method: POST\n        description: Create or update custom headers\n        inputParameters:\n        -\
  \ name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/domains\n      operations:\n      - name: domains-list\n        method: GET\n        description: List all domains for a project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: domains-create\n        method: POST\n        description: Add a new domain\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/domains/{domain}\n      operations:\n      - name: domains-delete\n        method: DELETE\n        description: Delete a domain\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n      \
  \    required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Domain id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: domains-read\n        method: GET\n        description: Get details of a single domain\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Domain\
  \ id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/domains/{domain}/renew\n      operations:\n      - name: domains-renew\n        method: POST\n        description: Renew the SSL certificate for a domain\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: domain\n          in: path\n          type: string\n          required: true\n          description: Domain id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n\
  \      path: /api/v2/organizations/{organization}/projects/{project}/kv\n      operations:\n      - name: kv-list\n        method: GET\n        description: List key-value stores\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kv-create\n        method: POST\n        description: Add a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project\
  \ identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}\n      operations:\n      - name: kv-delete\n        method: DELETE\n        description: Delete a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kv-show\n        method: GET\n        description: Get a\
  \ kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/link\n      operations:\n      - name: kv-unlink-from-project\n        method: DELETE\n        description: Unlink a KV store from this project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n          description: KV store identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kv-link-to-project\n        method: POST\n        description: Link a KV store to another project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Source project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n          description: KV store identifier\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items\n      operations:\n      - name: kv-items-list\n        method: GET\n        description: List items in a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        - name: cursor\n          in: query\n          type: string\n          description: Cursor for pagination\n        - name: limit\n          in: query\n          type: integer\n          description: Number of items\
  \ to return\n        - name: search\n          in: query\n          type: string\n          description: Search filter for keys\n        - name: include_values\n          in: query\n          type: boolean\n          description: Include values in the response. Secret values will be redacted as '[ENCRYPTED]' for security.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kv-items-create\n        method: POST\n        description: Add an item to a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n       \
  \ outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/kv/{store_id}/items/{key}\n      operations:\n      - name: kv-items-delete\n        method: DELETE\n        description: Delete an item from a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: kv-items-show\n        method: GET\n        description: Get an item from a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: kv-items-update\n        method: PUT\n        description: Update an item in a kv store\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n\
  \        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: store_id\n          in: path\n          type: string\n          required: true\n        - name: key\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-organizations-organization-projects-project-m\n      path: /v2/organizations/{organization}/projects/{project}/metrics/hourly\n      operations:\n      - name: gethourlymetrics\n        method: GET\n        description: Get hourly metrics\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description:\
  \ Project identifier\n        - name: domain\n          in: query\n          type: string\n          description: Filter by domain ID or domain name\n        - name: metrics[]\n          in: query\n          type: array\n          description: 'Metrics to return (default: hits, bytes). Use the /metrics/available endpoint to list all metrics\n            by category.'\n        - name: timestamp_format\n          in: query\n          type: string\n          description: Timestamp format in response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-organizations-organization-projects-project-m\n      path: /v2/organizations/{organization}/projects/{project}/metrics/daily\n      operations:\n      - name: getdailymetrics\n        method: GET\n        description: Get daily metrics\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required:\
  \ true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: domain\n          in: query\n          type: string\n          description: Filter by domain ID or domain name\n        - name: metrics[]\n          in: query\n          type: array\n          description: 'Metrics to return (default: hits, bytes). Use the /metrics/available endpoint to list all metrics\n            by category.'\n        - name: timestamp_format\n          in: query\n          type: string\n          description: Timestamp format in response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: v2-organizations-organization-projects-project-m\n      path: /v2/organizations/{organization}/projects/{project}/metrics/monthly\n      operations:\n      - name: getmonthlymetrics\n  \
  \      method: GET\n        description: Get monthly metrics\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: domain\n          in: query\n          type: string\n          description: Filter by domain ID or domain name\n        - name: metrics[]\n          in: query\n          type: array\n          description: 'Metrics to return (default: hits, bytes). Use the /metrics/available endpoint to list all metrics\n            by category.'\n        - name: timestamp_format\n          in: query\n          type: string\n          description: Timestamp format in response\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations\n\
  \      path: /api/v2/organizations\n      operations:\n      - name: organizations-list\n        method: GET\n        description: Retrieve all organizations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization\n      path: /api/v2/organizations/{organization}\n      operations:\n      - name: organizations-read\n        method: GET\n        description: Get details of a single organization\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects\n      path: /api/v2/organizations/{organization}/projects\n      operations:\n      - name: projects-list\n        method: GET\n\
  \        description: Retrieve all projects for an organization\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: projects-create\n        method: POST\n        description: Create a new project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}\n      operations:\n      - name: projects-delete\n        method: DELETE\n        description: Delete a project\n\
  \        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: projects-read\n        method: GET\n        description: Get details of a single project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        - name: with_token\n          in: query\n          type: boolean\n          required: true\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: projects-update\n        method: PATCH\n        description: Update a project\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/purge\n      operations:\n      - name: purge-create\n        method: POST\n        description: Purge cache via URL or cache keys\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n         \
  \ description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/rules/auth\n      operations:\n      - name: rulesauth-list\n        method: GET\n        description: List authentication rules\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n      - name: rulesauth-create\n        method: POST\n        description: Create an authentication rule\n        inputParameters:\n        - name: organization\n          in: path\n          type: string\n          required: true\n          description: Organization identifier\n        - name: project\n          in: path\n          type: string\n          required: true\n          description: Project identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: api-v2-organizations-organization-projects-proje\n      path: /api/v2/organizations/{organization}/projects/{project}/rules/auth/{rule}\n      operations:\n      - name: rulesa\n\n# --- truncated at 32 KB (109 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/quantcdn/refs/heads/main/capabilities/quantcdn-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/quantcdn/refs/heads/main/capabilities/quantcdn-capability.yaml
tags:
- Quantcdn
- API
tools:
- description: List schedules for a crawler
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlerschedules-list
- description: Add a new schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: crawlerschedules-add
- description: Delete a schedule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: crawlerschedules-delete
- description: Show a specific schedule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlerschedules-show
- description: Edit a schedule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: crawlerschedules-edit
- description: List crawlers for the project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlers-list
- description: Create a new crawler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: crawlers-create
- description: Delete a crawler
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: crawlers-delete
- description: Get details of a single crawler
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlers-read
- description: Update a crawler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: crawlers-update
- description: Run a crawler
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: crawlers-run
- description: Get all runs for a crawler
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlers-getruns
- description: Get a run by ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: crawlers-getrunbyid
- description: Delete custom headers
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: headers-delete
- description: List custom headers for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: headers-list
- description: Create or update custom headers
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: headers-create
- description: List all domains for a project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: domains-list
- description: Add a new domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: domains-create
- description: Delete a domain
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: domains-delete
- description: Get details of a single domain
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: domains-read
- description: Renew the SSL certificate for a domain
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: domains-renew
- description: List key-value stores
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: kv-list
- description: Add a kv store
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kv-create
- description: Delete a kv store
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: kv-delete
- description: Get a kv store
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: kv-show
- description: Unlink a KV store from this project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: kv-unlink-from-project
- description: Link a KV store to another project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kv-link-to-project
- description: List items in a kv store
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: kv-items-list
- description: Add an item to a kv store
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: kv-items-create
- description: Delete an item from a kv store
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: kv-items-delete
- description: Get an item from a kv store
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: kv-items-show
- description: Update an item in a kv store
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: kv-items-update
- description: Get hourly metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethourlymetrics
- description: Get daily metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdailymetrics
- description: Get monthly metrics
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmonthlymetrics
- description: Retrieve all organizations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: organizations-list
- description: Get details of a single organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: organizations-read
- description: Retrieve all projects for an organization
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: projects-list
- description: Create a new project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: projects-create
- description: Delete a project
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: projects-delete
- description: Get details of a single project
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: projects-read
- description: Update a project
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: projects-update
- description: Purge cache via URL or cache keys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: purge-create
- description: List authentication rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulesauth-list
- description: Create an authentication rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulesauth-create
- description: Delete an authentication rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: rulesauth-delete
- description: Get details of an authentication rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulesauth-read
- description: Update an authentication rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulesauth-update
- description: List bot challenge rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulesbotchallenge-list
- description: Create a bot challenge rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulesbotchallenge-create
- description: Delete a bot challenge rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: rulesbotchallenge-delete
- description: Get details of a bot challenge rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulesbotchallenge-read
- description: Update a bot challenge rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulesbotchallenge-update
- description: List content filter rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulescontentfilter-list
- description: Create a content filter rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulescontentfilter-create
- description: Delete a content filter rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: rulescontentfilter-delete
- description: Get details of a content filter rule
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulescontentfilter-read
- description: Update a content filter rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulescontentfilter-update
- description: List custom response rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: rulescustomresponse-list
- description: Create a custom response rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rulescustomresponse-create
---
