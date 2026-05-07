---
categories: []
consumed_apis: []
description: API for managing Packer images.
layout: capability
name: HashiCorp Cloud Platform Packer Artifact Registry
operations:
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  method: GET
  name: getbuild
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  method: DELETE
  name: deletebuild
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  method: PATCH
  name: updatebuild
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
  method: GET
  name: listbuckets
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
- description: PUT /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
  method: PUT
  name: createbucket
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  method: GET
  name: getbucket
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  method: DELETE
  name: deletebucket
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  method: PATCH
  name: updatebucket
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
  method: GET
  name: listchannels
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
  method: POST
  name: createchannel
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  method: GET
  name: getchannel
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  method: DELETE
  name: deletechannel
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  method: PATCH
  name: updatechannel
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- description: 'GetIteration allows the user to retrieve an iteration using one of the following identifiers: * iteration_id * incremental_version * fingerprint'
  method: GET
  name: getiteration
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iteration
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
  method: GET
  name: listiterations
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
  method: POST
  name: createiteration
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
- description: API Endpoints to ease UI implementation
  method: GET
  name: getancestorimages
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/ancestors
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children
  method: GET
  name: getchildimages
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}
  method: POST
  name: createbuild
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds
  method: GET
  name: listbuilds
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}
  method: DELETE
  name: deleteiteration
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}
- description: UpdateIteration is used to mark an iteration "complete", once all builds are complete. To make build-specific updates for builds within the iteration, use the UpdateBuild endpoint.
  method: PATCH
  name: updateiteration
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
  method: GET
  name: getregistry
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
- description: PUT /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
  method: PUT
  name: createregistry
  path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
personas: []
provider_name: Packer
provider_slug: packer
search_terms:
- createbuild
- devops
- post /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
- automation
- getchildimages
- listbuilds
- hashicorp
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds
- api
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
- delete /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}
- delete /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- delete /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
- updatebuild
- patch /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- listbuckets
- getregistry
- createiteration
- patch /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- 'getiteration allows the user to retrieve an iteration using one of the following identifiers: * iteration_id * incremental_version * fingerprint'
- put /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
- updateiteration is used to mark an iteration "complete", once all builds are complete. to make build-specific updates for builds within the iteration, use the updatebuild endpoint.
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
- post /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
- getbucket
- post /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}
- deletebuild
- createregistry
- createbucket
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
- getchannel
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- packer
- updatebucket
- getancestorimages
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
- infrastructure as code
- listiterations
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
- image building
- api endpoints to ease ui implementation
- deleteiteration
- getbuild
- updatechannel
- updateiteration
- get /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
- createchannel
- getiteration
- deletechannel
- deletebucket
- listchannels
- delete /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
- put /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
- patch /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
slug: packer-capability
source_filename: packer-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: HashiCorp Cloud Platform Packer Artifact Registry\n  description: API for managing Packer images.\n  tags:\n  - Packer\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: packer\n    baseUri: //api.cloud.hashicorp.com\n    description: HashiCorp Cloud Platform Packer Artifact Registry HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PACKER_TOKEN}}'\n    resources:\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}\n      operations:\n      - name: getbuild\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}\n        inputParameters:\n        - name: location.organization_id\n\
  \          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: build_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the build that should be retrieved; this ID was created and set by the HCP Packer\n            registry when the build was created.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n      - name: deletebuild\n        method: DELETE\n        description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: build_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the build that should be deleted; this ID was created and set by the HCP Packer\n            registry when the build was created.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the\
  \ named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebuild\n        method: PATCH\n        description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: build_id\n          in: path\n          type: string\n          required: true\n\
  \          description: Unique identifier of the build that should be updated; this ID was created and set by the HCP Packer\n            registry when the build was created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images\n      operations:\n      - name: listbuckets\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ project_id is the projects id.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: pagination.page_size\n          in: query\n          type: integer\n          description: The max number of results per page that should be returned. If the number of available results is larger\n            than `page_size`, a `next_page_token` is returned which\n        - name: pagination.next_page_token\n          in: query\n          type: string\n          description: Specifies a page token to use to retrieve the next page. Set this to the `next_page_token` returned\n            by previous list requests to get the next page of results. I\n        - name: pagination.previous_page_token\n   \
  \       in: query\n          type: string\n          description: Specifies a page token to use to retrieve the previous page. Set this to the `previous_page_token`\n            returned by previous list requests to get the previous page o\n        - name: sorting.order_by\n          in: query\n          type: array\n          description: Specifies the list of per field ordering that should be used for sorting. The order matters as rows\n            are sorted in order by fields and when the field matches, th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbucket\n        method: PUT\n        description: PUT /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the\
  \ id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}\n      operations:\n      - name: getbucket\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n   \
  \       required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: bucket_id\n          in: query\n          type: string\n          description: Unique identifier of the bucket; created and set by the HCP Packer registry when the bucket is created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebucket\n        method: DELETE\n        description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}\n\
  \        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: updatebucket\n        method: PATCH\n        description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels\n\
  \      operations:\n      - name: listchannels\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket you want to list channels for.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n    \
  \      in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createchannel\n        method: POST\n        description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket to associate the channel\
  \ with.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}\n      operations:\n      - name: getchannel\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n\
  \          required: true\n          description: Human-readable name for the bucket that the channel is associated with.\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the channel.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletechannel\n        method: DELETE\n        description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}\n        inputParameters:\n        - name:\
  \ location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket that the channel is associated with.\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the channel.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\"\
  , \"us-east1\").\n        - name: revocation_message\n          in: query\n          type: string\n          description: Optional field to provide the reason for why this channel is being revoked. Only useful for a channel\n            that is assigned to an iteration.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatechannel\n        method: PATCH\n        description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n\
  \          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket that the channel is associated with.\n        - name: slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the channel.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iteration\n      operations:\n      - name: getiteration\n        method: GET\n        description: 'GetIteration allows the user to retrieve an iteration using one of the following identifiers: * iteration_id\n          * incremental_version * fingerprint'\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n\
  \          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: incremental_version\n          in: query\n          type: integer\n          description: The human-readable version number assigned to this iteration.\n        - name: iteration_id\n          in: query\n          type:\
  \ string\n          description: Unique identifier of the iteration. This was created and set by the HCP Packer registry when the iteration\n            was created.\n        - name: fingerprint\n          in: query\n          type: string\n          description: Fingerprint of the iteration. The fingerprint is set by Packer when you call `packer build`. It will\n            most often correspond to a git commit sha, but can be manua\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations\n      operations:\n      - name: listiterations\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations\n        inputParameters:\n\
  \        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: include_incomplete\n          in: query\n          type: boolean\n          description: If true, the request will return information\
  \ about iterations that have not been marked \"complete\".\n            By default, this is false and the list request will only ret\n        - name: pagination.page_size\n          in: query\n          type: integer\n          description: The max number of results per page that should be returned. If the number of available results is larger\n            than `page_size`, a `next_page_token` is returned which\n        - name: pagination.next_page_token\n          in: query\n          type: string\n          description: Specifies a page token to use to retrieve the next page. Set this to the `next_page_token` returned\n            by previous list requests to get the next page of results. I\n        - name: pagination.previous_page_token\n          in: query\n          type: string\n          description: Specifies a page token to use to retrieve the previous page. Set this to the `previous_page_token`\n            returned by previous list requests to get the previous page o\n     \
  \   - name: sorting.order_by\n          in: query\n          type: array\n          description: Specifies the list of per field ordering that should be used for sorting. The order matters as rows\n            are sorted in order by fields and when the field matches, th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createiteration\n        method: POST\n        description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n\
  \          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/ancestors\n      operations:\n      - name: getancestorimages\n        method: GET\n        description: API Endpoints to ease UI implementation\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n     \
  \   - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: incremental_version\n          in: path\n          type: integer\n          required: true\n          description: The human-readable version number assigned to this iteration.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children\n\
  \      operations:\n      - name: getchildimages\n        method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: incremental_version\n          in: path\n          type: integer\n          required: true\n          description: The human-readable version number assigned to this iteration.\n        - name: location.region.provider\n\
  \          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}\n      operations:\n      - name: createbuild\n        method: POST\n        description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket.\n        - name: iteration_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the iteration that this build should be associated with.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds\n      operations:\n      - name: listbuilds\n     \
  \   method: GET\n        description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: bucket_slug\n          in: path\n          type: string\n          required: true\n          description: Human-readable name for the bucket to list builds for.\n        - name: iteration_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the iteration to list builds for; this was created and set by the HCP Packer registry\n            when the iteration was\
  \ created.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: pagination.page_size\n          in: query\n          type: integer\n          description: The max number of results per page that should be returned. If the number of available results is larger\n            than `page_size`, a `next_page_token` is returned which\n        - name: pagination.next_page_token\n          in: query\n          type: string\n          description: Specifies a page token to use to retrieve the next page. Set this to the `next_page_token` returned\n            by previous list requests to get the next page of results. I\n        - name: pagination.previous_page_token\n          in: query\n    \
  \      type: string\n          description: Specifies a page token to use to retrieve the previous page. Set this to the `previous_page_token`\n            returned by previous list requests to get the previous page o\n        - name: sorting.order_by\n          in: query\n          type: array\n          description: Specifies the list of per field ordering that should be used for sorting. The order matters as rows\n            are sorted in order by fields and when the field matches, th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}\n      operations:\n      - name: deleteiteration\n        method: DELETE\n        description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}\n\
  \        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: iteration_id\n          in: path\n          type: string\n          required: true\n          description: Unique identifier of the iteration. This was created and set by the HCP Packer registry when the iteration\n            was created.\n        - name: location.region.provider\n          in: query\n          type: string\n          description: provider is the named cloud provider (\"aws\", \"gcp\", \"azure\").\n        - name: location.region.region\n          in: query\n          type: string\n          description: region is the cloud region (\"us-west1\", \"us-east1\").\n        - name: bucket_slug\n\
  \          in: query\n          type: string\n          description: Human-readable name for the bucket.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateiteration\n        method: PATCH\n        description: UpdateIteration is used to mark an iteration \"complete\", once all builds are complete. To make build-specific\n          updates for builds within the iteration, use the UpdateBuild endpoint.\n        inputParameters:\n        - name: location.organization_id\n          in: path\n          type: string\n          required: true\n          description: organization_id is the id of the organization.\n        - name: location.project_id\n          in: path\n          type: string\n          required: true\n          description: project_id is the projects id.\n        - name: iteration_id\n          in: path\n          type: string\n          required: true\n          description: Unique\
  \ identifier of the iteration. This was created and set by the HCP Packer registry when the iteration\n            was created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: packer-2021-04-30-organizations-location-organiz\n      path: /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry\n      operations:\n      - name: getregistry\n  \n\n# --- truncated at 32 KB (84 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/packer/refs/heads/main/capabilities/packer-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/packer/refs/heads/main/capabilities/packer-capability.yaml
tags:
- Packer
- API
tools:
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbuild
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebuild
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/builds/{build_id}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebuild
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuckets
- description: PUT /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createbucket
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbucket
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebucket
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebucket
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listchannels
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createchannel
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannel
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletechannel
- description: PATCH /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/channels/{slug}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatechannel
- description: 'GetIteration allows the user to retrieve an iteration using one of the following identifiers: * iteration_id * incremental_version * fingerprint'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getiteration
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listiterations
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createiteration
- description: API Endpoints to ease UI implementation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getancestorimages
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{incremental_version}/children
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchildimages
- description: POST /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbuild
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/images/{bucket_slug}/iterations/{iteration_id}/builds
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbuilds
- description: DELETE /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/iterations/{iteration_id}
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteiteration
- description: UpdateIteration is used to mark an iteration "complete", once all builds are complete. To make build-specific updates for builds within the iteration, use the UpdateBuild endpoint.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateiteration
- description: GET /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getregistry
- description: PUT /packer/2021-04-30/organizations/{location.organization_id}/projects/{location.project_id}/registry
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createregistry
---
