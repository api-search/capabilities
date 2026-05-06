---
categories: []
consumed_apis: []
description: Netlify is a hosting service for the programmable web. It understands your documents and provides an API to handle atomic deploys of websites, manage form submissions, inject JavaScript snippets, and much more. This is a REST-style API that uses JSON for serialization and OAuth 2 for authentication. This document is an OpenAPI reference for the Netlify API that you can explore. For more detailed instructions for common uses, please visit the [online documentation](https://www.netlify.com/docs/api/). Visit our Community forum to join the conversation about [understanding and using Netlify’s API
layout: capability
name: Netlify Netlify's API documentation
operations:
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment variables.'
  method: GET
  name: listsites
  path: /sites
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [createEnvVars](#tag/environmentVariables/operation/createEnvVars) to create environment variables for a site.'
  method: POST
  name: createsite
  path: /sites
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment variables.'
  method: GET
  name: getsite
  path: /sites/{site_id}
- description: DELETE /sites/{site_id}
  method: DELETE
  name: deletesite
  path: /sites/{site_id}
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [updateEnvVar](#tag/environmentVariables/operation/updateEnvVar) to update a site''s environment variables.'
  method: PATCH
  name: updatesite
  path: /sites/{site_id}
- description: GET /sites/{site_id}/ssl
  method: GET
  name: showsitetlscertificate
  path: /sites/{site_id}/ssl
- description: POST /sites/{site_id}/ssl
  method: POST
  name: provisionsitetlscertificate
  path: /sites/{site_id}/ssl
- description: Returns all environment variables for an account or site. An account corresponds to a team in the Netlify UI. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experi
  method: GET
  name: getenvvars
  path: /accounts/{account_id}/env
- description: Creates new environment variables. Granular scopes are available on Pro plans and above. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic enviro
  method: POST
  name: createenvvars
  path: /accounts/{account_id}/env
- description: Returns all environment variables for a site. This convenience method behaves the same as `getEnvVars` but doesn't require an `account_id` as input.
  method: GET
  name: getsiteenvvars
  path: /api/v1/sites/{site_id}/env
- description: Returns an individual environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate now w
  method: GET
  name: getenvvar
  path: /accounts/{account_id}/env/{key}
- description: Updates an existing environment variable and all of its values. Existing values will be replaced by values provided. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic
  method: PUT
  name: updateenvvar
  path: /accounts/{account_id}/env/{key}
- description: Deletes an environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate now with the Net
  method: DELETE
  name: deleteenvvar
  path: /accounts/{account_id}/env/{key}
- description: Updates or creates a new value for an existing environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables expe
  method: PATCH
  name: setenvvarvalue
  path: /accounts/{account_id}/env/{key}
- description: Deletes a specific environment variable value. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate no
  method: DELETE
  name: deleteenvvarvalue
  path: /accounts/{account_id}/env/{key}/value/{id}
- description: GET /sites/{site_id}/functions
  method: GET
  name: searchsitefunctions
  path: /sites/{site_id}/functions
- description: GET /sites/{site_id}/forms
  method: GET
  name: listsiteforms
  path: /sites/{site_id}/forms
- description: DELETE /sites/{site_id}/forms/{form_id}
  method: DELETE
  name: deletesiteform
  path: /sites/{site_id}/forms/{form_id}
- description: GET /sites/{site_id}/submissions
  method: GET
  name: listsitesubmissions
  path: /sites/{site_id}/submissions
- description: GET /sites/{site_id}/files
  method: GET
  name: listsitefiles
  path: /sites/{site_id}/files
- description: GET /sites/{site_id}/assets
  method: GET
  name: listsiteassets
  path: /sites/{site_id}/assets
- description: POST /sites/{site_id}/assets
  method: POST
  name: createsiteasset
  path: /sites/{site_id}/assets
- description: GET /sites/{site_id}/assets/{asset_id}
  method: GET
  name: getsiteassetinfo
  path: /sites/{site_id}/assets/{asset_id}
- description: PUT /sites/{site_id}/assets/{asset_id}
  method: PUT
  name: updatesiteasset
  path: /sites/{site_id}/assets/{asset_id}
- description: DELETE /sites/{site_id}/assets/{asset_id}
  method: DELETE
  name: deletesiteasset
  path: /sites/{site_id}/assets/{asset_id}
- description: GET /sites/{site_id}/assets/{asset_id}/public_signature
  method: GET
  name: getsiteassetpublicsignature
  path: /sites/{site_id}/assets/{asset_id}/public_signature
- description: GET /sites/{site_id}/files/{file_path}
  method: GET
  name: getsitefilebypathname
  path: /sites/{site_id}/files/{file_path}
- description: Purges cached content from Netlify's CDN. Supports purging by Cache-Tag.
  method: POST
  name: purgecache
  path: /purge
- description: GET /sites/{site_id}/snippets
  method: GET
  name: listsitesnippets
  path: /sites/{site_id}/snippets
- description: POST /sites/{site_id}/snippets
  method: POST
  name: createsitesnippet
  path: /sites/{site_id}/snippets
- description: GET /sites/{site_id}/snippets/{snippet_id}
  method: GET
  name: getsitesnippet
  path: /sites/{site_id}/snippets/{snippet_id}
- description: PUT /sites/{site_id}/snippets/{snippet_id}
  method: PUT
  name: updatesitesnippet
  path: /sites/{site_id}/snippets/{snippet_id}
- description: DELETE /sites/{site_id}/snippets/{snippet_id}
  method: DELETE
  name: deletesitesnippet
  path: /sites/{site_id}/snippets/{snippet_id}
- description: GET /sites/{site_id}/metadata
  method: GET
  name: getsitemetadata
  path: /sites/{site_id}/metadata
- description: PUT /sites/{site_id}/metadata
  method: PUT
  name: updatesitemetadata
  path: /sites/{site_id}/metadata
- description: GET /sites/{site_id}/build_hooks
  method: GET
  name: listsitebuildhooks
  path: /sites/{site_id}/build_hooks
- description: POST /sites/{site_id}/build_hooks
  method: POST
  name: createsitebuildhook
  path: /sites/{site_id}/build_hooks
- description: GET /sites/{site_id}/build_hooks/{id}
  method: GET
  name: getsitebuildhook
  path: /sites/{site_id}/build_hooks/{id}
- description: PUT /sites/{site_id}/build_hooks/{id}
  method: PUT
  name: updatesitebuildhook
  path: /sites/{site_id}/build_hooks/{id}
- description: DELETE /sites/{site_id}/build_hooks/{id}
  method: DELETE
  name: deletesitebuildhook
  path: /sites/{site_id}/build_hooks/{id}
- description: GET /sites/{site_id}/deploys
  method: GET
  name: listsitedeploys
  path: /sites/{site_id}/deploys
- description: POST /sites/{site_id}/deploys
  method: POST
  name: createsitedeploy
  path: /sites/{site_id}/deploys
- description: GET /sites/{site_id}/deploys/{deploy_id}
  method: GET
  name: getsitedeploy
  path: /sites/{site_id}/deploys/{deploy_id}
- description: PUT /sites/{site_id}/deploys/{deploy_id}
  method: PUT
  name: updatesitedeploy
  path: /sites/{site_id}/deploys/{deploy_id}
- description: DELETE /sites/{site_id}/deploys/{deploy_id}
  method: DELETE
  name: deletesitedeploy
  path: /sites/{site_id}/deploys/{deploy_id}
- description: POST /deploys/{deploy_id}/cancel
  method: POST
  name: cancelsitedeploy
  path: /deploys/{deploy_id}/cancel
- description: POST /sites/{site_id}/deploys/{deploy_id}/restore
  method: POST
  name: restoresitedeploy
  path: /sites/{site_id}/deploys/{deploy_id}/restore
- description: GET /sites/{site_id}/builds
  method: GET
  name: listsitebuilds
  path: /sites/{site_id}/builds
- description: POST /sites/{site_id}/builds
  method: POST
  name: createsitebuild
  path: /sites/{site_id}/builds
- description: GET /sites/{site_id}/deployed-branches
  method: GET
  name: listsitedeployedbranches
  path: /sites/{site_id}/deployed-branches
- description: '[Beta] Unlinks the repo from the site. This action will also: - Delete associated deploy keys - Delete outgoing webhooks for the repo - Delete the site''s build hooks'
  method: PUT
  name: unlinksiterepo
  path: /sites/{site_id}/unlink_repo
- description: GET /builds/{build_id}
  method: GET
  name: getsitebuild
  path: /builds/{build_id}
- description: POST /builds/{build_id}/log
  method: POST
  name: updatesitebuildlog
  path: /builds/{build_id}/log
- description: POST /builds/{build_id}/start
  method: POST
  name: notifybuildstart
  path: /builds/{build_id}/start
- description: GET /{account_id}/builds/status
  method: GET
  name: getaccountbuildstatus
  path: /{account_id}/builds/status
- description: GET /sites/{site_id}/dns
  method: GET
  name: getdnsforsite
  path: /sites/{site_id}/dns
- description: PUT /sites/{site_id}/dns
  method: PUT
  name: configurednsforsite
  path: /sites/{site_id}/dns
- description: PUT /sites/{site_id}/rollback
  method: PUT
  name: rollbacksitedeploy
  path: /sites/{site_id}/rollback
- description: GET /deploys/{deploy_id}
  method: GET
  name: getdeploy
  path: /deploys/{deploy_id}
- description: DELETE /deploys/{deploy_id}
  method: DELETE
  name: deletedeploy
  path: /deploys/{deploy_id}
personas: []
provider_name: Netlify
provider_slug: netlify
search_terms:
- get /sites/{site_id}/ssl
- post /sites/{site_id}/builds
- setenvvarvalue
- delete /sites/{site_id}/deploys/{deploy_id}
- get /sites/{site_id}/assets/{asset_id}
- updatesitebuildhook
- returns all environment variables for a site. this convenience method behaves the same as `getenvvars` but doesn't require an `account_id` as input.
- getaccountbuildstatus
- post /sites/{site_id}/assets
- getenvvars
- cloud
- get /deploys/{deploy_id}
- updateenvvar
- updatesitedeploy
- '**note:** environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. please use [createenvvars](#tag/environmentvariables/operation/createenvvars) to create environment variables for a site.'
- delete /sites/{site_id}/forms/{form_id}
- post /sites/{site_id}/deploys
- edge computing
- updatesite
- delete /deploys/{deploy_id}
- post /sites/{site_id}/build_hooks
- get /sites/{site_id}/builds
- listsitedeploys
- get /sites/{site_id}/build_hooks
- listsitebuilds
- api
- cancelsitedeploy
- listsiteforms
- post /builds/{build_id}/log
- get /sites/{site_id}/assets/{asset_id}/public_signature
- updatesitesnippet
- showsitetlscertificate
- configurednsforsite
- web hosting
- createenvvars
- listsiteassets
- get /sites/{site_id}/dns
- updates an existing environment variable and all of its values. existing values will be replaced by values provided. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic
- get /sites/{site_id}/functions
- createsitebuildhook
- restoresitedeploy
- getsitebuildhook
- get /{account_id}/builds/status
- createsitesnippet
- '**note:** environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. please use [getenvvars](#tag/environmentvariables/operation/getenvvars) to retrieve site environment variables.'
- get /sites/{site_id}/snippets/{snippet_id}
- '[beta] unlinks the repo from the site. this action will also: - delete associated deploy keys - delete outgoing webhooks for the repo - delete the site''s build hooks'
- get /sites/{site_id}/build_hooks/{id}
- delete /sites/{site_id}/build_hooks/{id}
- getsiteassetinfo
- delete /sites/{site_id}/assets/{asset_id}
- deletesitedeploy
- rollbacksitedeploy
- put /sites/{site_id}/dns
- serverless
- getdnsforsite
- delete /sites/{site_id}
- provisionsitetlscertificate
- deletesite
- getenvvar
- listsitedeployedbranches
- cdn
- returns an individual environment variable. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. migrate now w
- serverless functions
- createsitedeploy
- createsite
- getsitedeploy
- searchsitefunctions
- getsitebuild
- get /builds/{build_id}
- deleteenvvar
- get /sites/{site_id}/deploys
- deletesiteform
- returns all environment variables for an account or site. an account corresponds to a team in the netlify ui. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experi
- deleteenvvarvalue
- static sites
- deletesitebuildhook
- updatesiteasset
- getsitesnippet
- post /sites/{site_id}/ssl
- getsitefilebypathname
- listsitefiles
- creates new environment variables. granular scopes are available on pro plans and above. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic enviro
- get /sites/{site_id}/deploys/{deploy_id}
- post /sites/{site_id}/deploys/{deploy_id}/restore
- purgecache
- get /sites/{site_id}/snippets
- continuous deployment
- getsiteassetpublicsignature
- listsitesnippets
- post /deploys/{deploy_id}/cancel
- updatesitemetadata
- put /sites/{site_id}/snippets/{snippet_id}
- put /sites/{site_id}/deploys/{deploy_id}
- listsitesubmissions
- get /sites/{site_id}/deployed-branches
- deletesiteasset
- put /sites/{site_id}/build_hooks/{id}
- get /sites/{site_id}/metadata
- deletes an environment variable. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. migrate now with the net
- deletedeploy
- createsitebuild
- updates or creates a new value for an existing environment variable. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables expe
- get /sites/{site_id}/submissions
- put /sites/{site_id}/rollback
- '**note:** environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. please use [updateenvvar](#tag/environmentvariables/operation/updateenvvar) to update a site''s environment variables.'
- get /sites/{site_id}/files/{file_path}
- deletes a specific environment variable value. to use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. migrate no
- createsiteasset
- purges cached content from netlify's cdn. supports purging by cache-tag.
- websites
- deletesitesnippet
- jamstack
- delete /sites/{site_id}/snippets/{snippet_id}
- put /sites/{site_id}/metadata
- get /sites/{site_id}/files
- listsitebuildhooks
- listsites
- getdeploy
- notifybuildstart
- netlify
- updatesitebuildlog
- put /sites/{site_id}/assets/{asset_id}
- get /sites/{site_id}/forms
- getsiteenvvars
- post /sites/{site_id}/snippets
- getsite
- get /sites/{site_id}/assets
- unlinksiterepo
- post /builds/{build_id}/start
- getsitemetadata
slug: netlify-capability
source_filename: netlify-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Netlify Netlify's API documentation\n  description: Netlify is a hosting service for the programmable web. It understands your documents and provides an API to\n    handle atomic deploys of websites, manage form submissions, inject JavaScript snippets, and much more. This is a REST-style\n    API that uses JSON for serialization and OAuth 2 for authentication. This document is an OpenAPI reference for the Netlify\n    API that you can explore. For more detailed instructions for common uses, please visit the [online documentation](https://www.netlify.com/docs/api/).\n    Visit our Community forum to join the conversation about [understanding and using Netlify’s API\n  tags:\n  - Netlify\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: netlify\n    baseUri: https://api.netlify.com/api/v1\n    description: Netlify Netlify's API documentation HTTP API.\n    authentication:\n\
  \      type: bearer\n      token: '{{NETLIFY_TOKEN}}'\n    resources:\n    - name: sites\n      path: /sites\n      operations:\n      - name: listsites\n        method: GET\n        description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to\n          a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment\n          variables.'\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n        - name: filter\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsite\n        method: POST\n        description: '**Note:** Environment variable keys and values have\
  \ moved from `build_settings.env` and `repo.env` to\n          a new endpoint. Please use [createEnvVars](#tag/environmentVariables/operation/createEnvVars) to create environment\n          variables for a site.'\n        inputParameters:\n        - name: configure_dns\n          in: query\n          type: boolean\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id\n      path: /sites/{site_id}\n      operations:\n      - name: getsite\n        method: GET\n        description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to\n          a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment\n          variables.'\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: feature_flags\n       \
  \   in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesite\n        method: DELETE\n        description: DELETE /sites/{site_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesite\n        method: PATCH\n        description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to\n          a new endpoint. Please use [updateEnvVar](#tag/environmentVariables/operation/updateEnvVar) to update a site''s\n          environment variables.'\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n     \
  \   outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-ssl\n      path: /sites/{site_id}/ssl\n      operations:\n      - name: showsitetlscertificate\n        method: GET\n        description: GET /sites/{site_id}/ssl\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: provisionsitetlscertificate\n        method: POST\n        description: POST /sites/{site_id}/ssl\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: certificate\n          in: query\n          type: string\n        - name: key\n          in: query\n          type: string\n        - name: ca_certificates\n          in: query\n          type: string\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-env\n      path: /accounts/{account_id}/env\n      operations:\n      - name: getenvvars\n        method: GET\n        description: Returns all environment variables for an account or site. An account corresponds to a team in the Netlify\n          UI. To use this endpoint, your site must no longer be using the <a href=\"https://docs.netlify.com/environment-variables/classic-experi\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: context_name\n          in: query\n          type: string\n          description: Filter by deploy context\n        - name: scope\n          in: query\n          type: string\n          description: Filter by scope\n        - name: site_id\n          in: query\n          type: string\n\
  \          description: If specified, only return environment variables set on this site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createenvvars\n        method: POST\n        description: Creates new environment variables. Granular scopes are available on Pro plans and above. To use this\n          endpoint, your site must no longer be using the <a href=\"https://docs.netlify.com/environment-variables/classic-experience/\">classic\n          enviro\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, create an environment variable on the site level, not the account level\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n    - name: api-v1-sites-site-id-env\n      path: /api/v1/sites/{site_id}/env\n      operations:\n      - name: getsiteenvvars\n        method: GET\n        description: Returns all environment variables for a site. This convenience method behaves the same as `getEnvVars`\n          but doesn't require an `account_id` as input.\n        inputParameters:\n        - name: context_name\n          in: query\n          type: string\n          description: Filter by deploy context\n        - name: scope\n          in: query\n          type: string\n          description: Filter by scope\n        - name: site_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to site_id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-env-key\n      path: /accounts/{account_id}/env/{key}\n      operations:\n\
  \      - name: getenvvar\n        method: GET\n        description: Returns an individual environment variable. To use this endpoint, your site must no longer be using the\n          <a href=\"https://docs.netlify.com/environment-variables/classic-experience/\">classic environment variables experience</a>.\n          Migrate now w\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The environment variable key (case-sensitive)\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, return the environment variable for a specific site (no merging is performed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateenvvar\n\
  \        method: PUT\n        description: Updates an existing environment variable and all of its values. Existing values will be replaced by values\n          provided. To use this endpoint, your site must no longer be using the <a href=\"https://docs.netlify.com/environment-variables/classic\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The existing environment variable key name (case-sensitive)\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, update an environment variable set on this site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteenvvar\n        method: DELETE\n        description:\
  \ Deletes an environment variable. To use this endpoint, your site must no longer be using the <a href=\"https://docs.netlify.com/environment-variables/classic-experience/\">classic\n          environment variables experience</a>. Migrate now with the Net\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The environment variable key (case-sensitive)\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, delete the environment variable from this site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: setenvvarvalue\n        method: PATCH\n        description: Updates or creates a new value for an existing environment\
  \ variable. To use this endpoint, your site\n          must no longer be using the <a href=\"https://docs.netlify.com/environment-variables/classic-experience/\">classic\n          environment variables expe\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The existing environment variable key name (case-sensitive)\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, update an environment variable set on this site\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-env-key-value-id\n      path: /accounts/{account_id}/env/{key}/value/{id}\n      operations:\n      - name: deleteenvvarvalue\n\
  \        method: DELETE\n        description: Deletes a specific environment variable value. To use this endpoint, your site must no longer be using\n          the <a href=\"https://docs.netlify.com/environment-variables/classic-experience/\">classic environment variables experience</a>.\n          Migrate no\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n          description: Scope response to account_id\n        - name: id\n          in: path\n          type: string\n          required: true\n          description: The environment variable value's ID\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: The environment variable key name (case-sensitive)\n        - name: site_id\n          in: query\n          type: string\n          description: If provided, delete the value from an environment variable on this site\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-functions\n      path: /sites/{site_id}/functions\n      operations:\n      - name: searchsitefunctions\n        method: GET\n        description: GET /sites/{site_id}/functions\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: filter\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-forms\n      path: /sites/{site_id}/forms\n      operations:\n      - name: listsiteforms\n        method: GET\n        description: GET /sites/{site_id}/forms\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: sites-site-id-forms-form-id\n      path: /sites/{site_id}/forms/{form_id}\n      operations:\n      - name: deletesiteform\n        method: DELETE\n        description: DELETE /sites/{site_id}/forms/{form_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: form_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-submissions\n      path: /sites/{site_id}/submissions\n      operations:\n      - name: listsitesubmissions\n        method: GET\n        description: GET /sites/{site_id}/submissions\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n    \
  \      type: integer\n        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-files\n      path: /sites/{site_id}/files\n      operations:\n      - name: listsitefiles\n        method: GET\n        description: GET /sites/{site_id}/files\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-assets\n      path: /sites/{site_id}/assets\n      operations:\n      - name: listsiteassets\n        method: GET\n        description: GET /sites/{site_id}/assets\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsiteasset\n        method: POST\n        description: POST /sites/{site_id}/assets\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: name\n          in: query\n          type: string\n          required: true\n        - name: size\n          in: query\n          type: integer\n          required: true\n        - name: content_type\n          in: query\n          type: string\n          required: true\n        - name: visibility\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-assets-asset-id\n      path: /sites/{site_id}/assets/{asset_id}\n      operations:\n      - name: getsiteassetinfo\n        method: GET\n        description: GET /sites/{site_id}/assets/{asset_id}\n\
  \        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesiteasset\n        method: PUT\n        description: PUT /sites/{site_id}/assets/{asset_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n        - name: state\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesiteasset\n        method: DELETE\n        description: DELETE /sites/{site_id}/assets/{asset_id}\n\
  \        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-assets-asset-id-public-signature\n      path: /sites/{site_id}/assets/{asset_id}/public_signature\n      operations:\n      - name: getsiteassetpublicsignature\n        method: GET\n        description: GET /sites/{site_id}/assets/{asset_id}/public_signature\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: asset_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-files-file-path\n\
  \      path: /sites/{site_id}/files/{file_path}\n      operations:\n      - name: getsitefilebypathname\n        method: GET\n        description: GET /sites/{site_id}/files/{file_path}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: file_path\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: purge\n      path: /purge\n      operations:\n      - name: purgecache\n        method: POST\n        description: Purges cached content from Netlify's CDN. Supports purging by Cache-Tag.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-snippets\n      path: /sites/{site_id}/snippets\n      operations:\n      - name: listsitesnippets\n        method:\
  \ GET\n        description: GET /sites/{site_id}/snippets\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitesnippet\n        method: POST\n        description: POST /sites/{site_id}/snippets\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-snippets-snippet-id\n      path: /sites/{site_id}/snippets/{snippet_id}\n      operations:\n      - name: getsitesnippet\n        method: GET\n        description: GET /sites/{site_id}/snippets/{snippet_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n       \
  \   required: true\n        - name: snippet_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitesnippet\n        method: PUT\n        description: PUT /sites/{site_id}/snippets/{snippet_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: snippet_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesitesnippet\n        method: DELETE\n        description: DELETE /sites/{site_id}/snippets/{snippet_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: snippet_id\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-metadata\n      path: /sites/{site_id}/metadata\n      operations:\n      - name: getsitemetadata\n        method: GET\n        description: GET /sites/{site_id}/metadata\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitemetadata\n        method: PUT\n        description: PUT /sites/{site_id}/metadata\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-build-hooks\n\
  \      path: /sites/{site_id}/build_hooks\n      operations:\n      - name: listsitebuildhooks\n        method: GET\n        description: GET /sites/{site_id}/build_hooks\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitebuildhook\n        method: POST\n        description: POST /sites/{site_id}/build_hooks\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-build-hooks-id\n      path: /sites/{site_id}/build_hooks/{id}\n      operations:\n      - name: getsitebuildhook\n        method: GET\n        description: GET /sites/{site_id}/build_hooks/{id}\n\
  \        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitebuildhook\n        method: PUT\n        description: PUT /sites/{site_id}/build_hooks/{id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesitebuildhook\n        method: DELETE\n        description: DELETE /sites/{site_id}/build_hooks/{id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type:\
  \ string\n          required: true\n        - name: id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-deploys\n      path: /sites/{site_id}/deploys\n      operations:\n      - name: listsitedeploys\n        method: GET\n        description: GET /sites/{site_id}/deploys\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: deploy-previews\n          in: query\n          type: boolean\n        - name: production\n          in: query\n          type: boolean\n        - name: state\n          in: query\n          type: string\n        - name: branch\n          in: query\n          type: string\n        - name: latest-published\n          in: query\n          type: boolean\n        - name: page\n          in: query\n          type: integer\n\
  \        - name: per_page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitedeploy\n        method: POST\n        description: POST /sites/{site_id}/deploys\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: deploy-previews\n          in: query\n          type: boolean\n        - name: production\n          in: query\n          type: boolean\n        - name: state\n          in: query\n          type: string\n        - name: branch\n          in: query\n          type: string\n        - name: latest-published\n          in: query\n          type: boolean\n        - name: title\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ sites-site-id-deploys-deploy-id\n      path: /sites/{site_id}/deploys/{deploy_id}\n      operations:\n      - name: getsitedeploy\n        method: GET\n        description: GET /sites/{site_id}/deploys/{deploy_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: deploy_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesitedeploy\n        method: PUT\n        description: PUT /sites/{site_id}/deploys/{deploy_id}\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: deploy_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deletesitedeploy\n        method: DELETE\n        description: DELETE /sites/{site_id}/deploys/{deploy_id}\n        inputParameters:\n        - name: deploy_id\n          in: path\n          type: string\n          required: true\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: deploys-deploy-id-cancel\n      path: /deploys/{deploy_id}/cancel\n      operations:\n      - name: cancelsitedeploy\n        method: POST\n        description: POST /deploys/{deploy_id}/cancel\n        inputParameters:\n        - name: deploy_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-deploys-deploy-id-restore\n\
  \      path: /sites/{site_id}/deploys/{deploy_id}/restore\n      operations:\n      - name: restoresitedeploy\n        method: POST\n        description: POST /sites/{site_id}/deploys/{deploy_id}/restore\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: deploy_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-builds\n      path: /sites/{site_id}/builds\n      operations:\n      - name: listsitebuilds\n        method: GET\n        description: GET /sites/{site_id}/builds\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        - name: per_page\n          in: query\n          type: integer\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsitebuild\n        method: POST\n        description: POST /sites/{site_id}/builds\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-deployed-branches\n      path: /sites/{site_id}/deployed-branches\n      operations:\n      - name: listsitedeployedbranches\n        method: GET\n        description: GET /sites/{site_id}/deployed-branches\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-unlink-repo\n\
  \      path: /sites/{site_id}/unlink_repo\n      operations:\n      - name: unlinksiterepo\n        method: PUT\n        description: '[Beta] Unlinks the repo from the site. This action will also: - Delete associated deploy keys - Delete\n          outgoing webhooks for the repo - Delete the site''s build hooks'\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: builds-build-id\n      path: /builds/{build_id}\n      operations:\n      - name: getsitebuild\n        method: GET\n        description: GET /builds/{build_id}\n        inputParameters:\n        - name: build_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: builds-build-id-log\n\
  \      path: /builds/{build_id}/log\n      operations:\n      - name: updatesitebuildlog\n        method: POST\n        description: POST /builds/{build_id}/log\n        inputParameters:\n        - name: build_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: builds-build-id-start\n      path: /builds/{build_id}/start\n      operations:\n      - name: notifybuildstart\n        method: POST\n        description: POST /builds/{build_id}/start\n        inputParameters:\n        - name: build_id\n          in: path\n          type: string\n          required: true\n        - name: buildbot_version\n          in: query\n          type: string\n        - name: build_version\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n       \
  \   value: $.\n    - name: account-id-builds-status\n      path: /{account_id}/builds/status\n      operations:\n      - name: getaccountbuildstatus\n        method: GET\n        description: GET /{account_id}/builds/status\n        inputParameters:\n        - name: account_id\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sites-site-id-dns\n      path: /sites/{site_id}/dns\n      operations:\n      - name: getdnsforsite\n        method: GET\n        description: GET /sites/{site_id}/dns\n        inputParameters:\n        - name: site_id\n          in: path\n          type: string\n          requ\n\n# --- truncated at 32 KB (93 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/netlify/refs/heads/main/capabilities/netlify-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/netlify/refs/heads/main/capabilities/netlify-capability.yaml
tags:
- Netlify
- API
tools:
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment variables.'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsites
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [createEnvVars](#tag/environmentVariables/operation/createEnvVars) to create environment variables for a site.'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsite
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [getEnvVars](#tag/environmentVariables/operation/getEnvVars) to retrieve site environment variables.'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsite
- description: DELETE /sites/{site_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesite
- description: '**Note:** Environment variable keys and values have moved from `build_settings.env` and `repo.env` to a new endpoint. Please use [updateEnvVar](#tag/environmentVariables/operation/updateEnvVar) to update a site''s environment variables.'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesite
- description: GET /sites/{site_id}/ssl
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: showsitetlscertificate
- description: POST /sites/{site_id}/ssl
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: provisionsitetlscertificate
- description: Returns all environment variables for an account or site. An account corresponds to a team in the Netlify UI. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experi
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvvars
- description: Creates new environment variables. Granular scopes are available on Pro plans and above. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic enviro
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createenvvars
- description: Returns all environment variables for a site. This convenience method behaves the same as `getEnvVars` but doesn't require an `account_id` as input.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsiteenvvars
- description: Returns an individual environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate now w
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getenvvar
- description: Updates an existing environment variable and all of its values. Existing values will be replaced by values provided. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateenvvar
- description: Deletes an environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate now with the Net
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvvar
- description: Updates or creates a new value for an existing environment variable. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables expe
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: setenvvarvalue
- description: Deletes a specific environment variable value. To use this endpoint, your site must no longer be using the <a href="https://docs.netlify.com/environment-variables/classic-experience/">classic environment variables experience</a>. Migrate no
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteenvvarvalue
- description: GET /sites/{site_id}/functions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchsitefunctions
- description: GET /sites/{site_id}/forms
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsiteforms
- description: DELETE /sites/{site_id}/forms/{form_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesiteform
- description: GET /sites/{site_id}/submissions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitesubmissions
- description: GET /sites/{site_id}/files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitefiles
- description: GET /sites/{site_id}/assets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsiteassets
- description: POST /sites/{site_id}/assets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsiteasset
- description: GET /sites/{site_id}/assets/{asset_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsiteassetinfo
- description: PUT /sites/{site_id}/assets/{asset_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesiteasset
- description: DELETE /sites/{site_id}/assets/{asset_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesiteasset
- description: GET /sites/{site_id}/assets/{asset_id}/public_signature
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsiteassetpublicsignature
- description: GET /sites/{site_id}/files/{file_path}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitefilebypathname
- description: Purges cached content from Netlify's CDN. Supports purging by Cache-Tag.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: purgecache
- description: GET /sites/{site_id}/snippets
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitesnippets
- description: POST /sites/{site_id}/snippets
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsitesnippet
- description: GET /sites/{site_id}/snippets/{snippet_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitesnippet
- description: PUT /sites/{site_id}/snippets/{snippet_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesitesnippet
- description: DELETE /sites/{site_id}/snippets/{snippet_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesitesnippet
- description: GET /sites/{site_id}/metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitemetadata
- description: PUT /sites/{site_id}/metadata
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesitemetadata
- description: GET /sites/{site_id}/build_hooks
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitebuildhooks
- description: POST /sites/{site_id}/build_hooks
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsitebuildhook
- description: GET /sites/{site_id}/build_hooks/{id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitebuildhook
- description: PUT /sites/{site_id}/build_hooks/{id}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesitebuildhook
- description: DELETE /sites/{site_id}/build_hooks/{id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesitebuildhook
- description: GET /sites/{site_id}/deploys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitedeploys
- description: POST /sites/{site_id}/deploys
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsitedeploy
- description: GET /sites/{site_id}/deploys/{deploy_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitedeploy
- description: PUT /sites/{site_id}/deploys/{deploy_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesitedeploy
- description: DELETE /sites/{site_id}/deploys/{deploy_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesitedeploy
- description: POST /deploys/{deploy_id}/cancel
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelsitedeploy
- description: POST /sites/{site_id}/deploys/{deploy_id}/restore
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: restoresitedeploy
- description: GET /sites/{site_id}/builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitebuilds
- description: POST /sites/{site_id}/builds
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsitebuild
- description: GET /sites/{site_id}/deployed-branches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listsitedeployedbranches
- description: '[Beta] Unlinks the repo from the site. This action will also: - Delete associated deploy keys - Delete outgoing webhooks for the repo - Delete the site''s build hooks'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: unlinksiterepo
- description: GET /builds/{build_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsitebuild
- description: POST /builds/{build_id}/log
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesitebuildlog
- description: POST /builds/{build_id}/start
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: notifybuildstart
- description: GET /{account_id}/builds/status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccountbuildstatus
- description: GET /sites/{site_id}/dns
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdnsforsite
- description: PUT /sites/{site_id}/dns
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: configurednsforsite
- description: PUT /sites/{site_id}/rollback
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: rollbacksitedeploy
- description: GET /deploys/{deploy_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeploy
- description: DELETE /deploys/{deploy_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeploy
---
