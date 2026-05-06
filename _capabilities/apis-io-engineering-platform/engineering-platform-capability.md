---
categories: []
consumed_apis: []
description: <fullname>Amazon API Gateway</fullname> <p>Amazon API Gateway helps developers deliver robust, secure, and scalable mobile and web application back ends. API Gateway allows developers to securely connect mobile and web applications to APIs that run on AWS Lambda, Amazon EC2, or other publicly addressable web services that are hosted outside of AWS.</p>
layout: capability
name: APIs.io Engineering Platform Amazon API Gateway
operations:
- description: Create an ApiKey resource.
  method: POST
  name: createapikey
  path: /apikeys
- description: Gets information about the current ApiKeys resource.
  method: GET
  name: getapikeys
  path: /apikeys
- description: Adds a new Authorizer resource to an existing RestApi resource.
  method: POST
  name: createauthorizer
  path: /restapis/{restapi_id}/authorizers
- description: Describe an existing Authorizers resource.
  method: GET
  name: getauthorizers
  path: /restapis/{restapi_id}/authorizers
- description: Creates a new BasePathMapping resource.
  method: POST
  name: createbasepathmapping
  path: /domainnames/{domain_name}/basepathmappings
- description: Represents a collection of BasePathMapping resources.
  method: GET
  name: getbasepathmappings
  path: /domainnames/{domain_name}/basepathmappings
- description: Creates a Deployment resource, which makes a specified RestApi callable over the internet.
  method: POST
  name: createdeployment
  path: /restapis/{restapi_id}/deployments
- description: Gets information about a Deployments collection.
  method: GET
  name: getdeployments
  path: /restapis/{restapi_id}/deployments
- description: Creates a documentation part.
  method: POST
  name: createdocumentationpart
  path: /restapis/{restapi_id}/documentation/parts
- description: Gets documentation parts.
  method: GET
  name: getdocumentationparts
  path: /restapis/{restapi_id}/documentation/parts
- description: Imports documentation parts
  method: PUT
  name: importdocumentationparts
  path: /restapis/{restapi_id}/documentation/parts
- description: Creates a documentation version
  method: POST
  name: createdocumentationversion
  path: /restapis/{restapi_id}/documentation/versions
- description: Gets documentation versions.
  method: GET
  name: getdocumentationversions
  path: /restapis/{restapi_id}/documentation/versions
- description: Creates a new domain name.
  method: POST
  name: createdomainname
  path: /domainnames
- description: Represents a collection of DomainName resources.
  method: GET
  name: getdomainnames
  path: /domainnames
- description: Adds a new Model resource to an existing RestApi resource.
  method: POST
  name: createmodel
  path: /restapis/{restapi_id}/models
- description: Describes existing Models defined for a RestApi resource.
  method: GET
  name: getmodels
  path: /restapis/{restapi_id}/models
- description: Creates a RequestValidator of a given RestApi.
  method: POST
  name: createrequestvalidator
  path: /restapis/{restapi_id}/requestvalidators
- description: Gets the RequestValidators collection of a given RestApi.
  method: GET
  name: getrequestvalidators
  path: /restapis/{restapi_id}/requestvalidators
- description: Creates a Resource resource.
  method: POST
  name: createresource
  path: /restapis/{restapi_id}/resources/{parent_id}
- description: Creates a new RestApi resource.
  method: POST
  name: createrestapi
  path: /restapis
- description: Lists the RestApis resources for your collection.
  method: GET
  name: getrestapis
  path: /restapis
- description: Creates a new Stage resource that references a pre-existing Deployment for the API.
  method: POST
  name: createstage
  path: /restapis/{restapi_id}/stages
- description: Gets information about one or more Stage resources.
  method: GET
  name: getstages
  path: /restapis/{restapi_id}/stages
- description: Creates a usage plan with the throttle and quota limits, as well as the associated API stages, specified in the payload.
  method: POST
  name: createusageplan
  path: /usageplans
- description: Gets all the usage plans of the caller's account.
  method: GET
  name: getusageplans
  path: /usageplans
- description: Creates a usage plan key for adding an existing API key to a usage plan.
  method: POST
  name: createusageplankey
  path: /usageplans/{usageplanId}/keys
- description: Gets all the usage plan keys representing the API keys added to a specified usage plan.
  method: GET
  name: getusageplankeys
  path: /usageplans/{usageplanId}/keys
- description: Creates a VPC link, under the caller's account in a selected region, in an asynchronous operation that typically takes 2-4 minutes to complete and become operational. The caller must have permissions to create and update VPC Endpoint servic
  method: POST
  name: createvpclink
  path: /vpclinks
- description: Gets the VpcLinks collection under the caller's account in a selected region.
  method: GET
  name: getvpclinks
  path: /vpclinks
- description: Deletes the ApiKey resource.
  method: DELETE
  name: deleteapikey
  path: /apikeys/{api_Key}
- description: Gets information about the current ApiKey resource.
  method: GET
  name: getapikey
  path: /apikeys/{api_Key}
- description: Changes information about an ApiKey resource.
  method: PATCH
  name: updateapikey
  path: /apikeys/{api_Key}
- description: Deletes an existing Authorizer resource.
  method: DELETE
  name: deleteauthorizer
  path: /restapis/{restapi_id}/authorizers/{authorizer_id}
- description: Describe an existing Authorizer resource.
  method: GET
  name: getauthorizer
  path: /restapis/{restapi_id}/authorizers/{authorizer_id}
- description: Simulate the execution of an Authorizer in your RestApi with headers, parameters, and an incoming request body.
  method: POST
  name: testinvokeauthorizer
  path: /restapis/{restapi_id}/authorizers/{authorizer_id}
- description: Updates an existing Authorizer resource.
  method: PATCH
  name: updateauthorizer
  path: /restapis/{restapi_id}/authorizers/{authorizer_id}
- description: Deletes the BasePathMapping resource.
  method: DELETE
  name: deletebasepathmapping
  path: /domainnames/{domain_name}/basepathmappings/{base_path}
- description: Describe a BasePathMapping resource.
  method: GET
  name: getbasepathmapping
  path: /domainnames/{domain_name}/basepathmappings/{base_path}
- description: Changes information about the BasePathMapping resource.
  method: PATCH
  name: updatebasepathmapping
  path: /domainnames/{domain_name}/basepathmappings/{base_path}
- description: Deletes the ClientCertificate resource.
  method: DELETE
  name: deleteclientcertificate
  path: /clientcertificates/{clientcertificate_id}
- description: Gets information about the current ClientCertificate resource.
  method: GET
  name: getclientcertificate
  path: /clientcertificates/{clientcertificate_id}
- description: Changes information about an ClientCertificate resource.
  method: PATCH
  name: updateclientcertificate
  path: /clientcertificates/{clientcertificate_id}
- description: Deletes a Deployment resource. Deleting a deployment will only succeed if there are no Stage resources associated with it.
  method: DELETE
  name: deletedeployment
  path: /restapis/{restapi_id}/deployments/{deployment_id}
- description: Gets information about a Deployment resource.
  method: GET
  name: getdeployment
  path: /restapis/{restapi_id}/deployments/{deployment_id}
- description: Changes information about a Deployment resource.
  method: PATCH
  name: updatedeployment
  path: /restapis/{restapi_id}/deployments/{deployment_id}
- description: Deletes a documentation part
  method: DELETE
  name: deletedocumentationpart
  path: /restapis/{restapi_id}/documentation/parts/{part_id}
- description: Gets a documentation part.
  method: GET
  name: getdocumentationpart
  path: /restapis/{restapi_id}/documentation/parts/{part_id}
- description: Updates a documentation part.
  method: PATCH
  name: updatedocumentationpart
  path: /restapis/{restapi_id}/documentation/parts/{part_id}
- description: Deletes a documentation version.
  method: DELETE
  name: deletedocumentationversion
  path: /restapis/{restapi_id}/documentation/versions/{doc_version}
- description: Gets a documentation version.
  method: GET
  name: getdocumentationversion
  path: /restapis/{restapi_id}/documentation/versions/{doc_version}
- description: Updates a documentation version.
  method: PATCH
  name: updatedocumentationversion
  path: /restapis/{restapi_id}/documentation/versions/{doc_version}
- description: Deletes the DomainName resource.
  method: DELETE
  name: deletedomainname
  path: /domainnames/{domain_name}
- description: Represents a domain name that is contained in a simpler, more intuitive URL that can be called.
  method: GET
  name: getdomainname
  path: /domainnames/{domain_name}
- description: Changes information about the DomainName resource.
  method: PATCH
  name: updatedomainname
  path: /domainnames/{domain_name}
- description: Clears any customization of a GatewayResponse of a specified response type on the given RestApi and resets it with the default settings.
  method: DELETE
  name: deletegatewayresponse
  path: /restapis/{restapi_id}/gatewayresponses/{response_type}
- description: Gets a GatewayResponse of a specified response type on the given RestApi.
  method: GET
  name: getgatewayresponse
  path: /restapis/{restapi_id}/gatewayresponses/{response_type}
- description: Creates a customization of a GatewayResponse of a specified response type and status code on the given RestApi.
  method: PUT
  name: putgatewayresponse
  path: /restapis/{restapi_id}/gatewayresponses/{response_type}
- description: Updates a GatewayResponse of a specified response type on the given RestApi.
  method: PATCH
  name: updategatewayresponse
  path: /restapis/{restapi_id}/gatewayresponses/{response_type}
- description: Represents a delete integration.
  method: DELETE
  name: deleteintegration
  path: /restapis/{restapi_id}/resources/{resource_id}/methods/{http_method}/integration
personas: []
provider_name: APIs.io Engineering Platform
provider_slug: apis-io-engineering-platform
search_terms:
- getdocumentationversion
- creates a requestvalidator of a given restapi.
- createusageplankey
- changes information about a deployment resource.
- gets all the usage plans of the caller's account.
- updatedomainname
- deletedocumentationversion
- deletebasepathmapping
- getapikey
- updates an existing authorizer resource.
- creates a new restapi resource.
- getgatewayresponse
- getusageplans
- api
- deletes the apikey resource.
- changes information about the domainname resource.
- represents a domain name that is contained in a simpler, more intuitive url that can be called.
- deletedeployment
- createdocumentationversion
- updateapikey
- getrestapis
- gets information about the current apikeys resource.
- gets a documentation part.
- deletes the domainname resource.
- clears any customization of a gatewayresponse of a specified response type on the given restapi and resets it with the default settings.
- deleteapikey
- createdocumentationpart
- getdocumentationversions
- updateclientcertificate
- creates a documentation part.
- gets the vpclinks collection under the caller's account in a selected region.
- deletes a documentation part
- testinvokeauthorizer
- changes information about an apikey resource.
- creates a new domain name.
- creates a usage plan with the throttle and quota limits, as well as the associated api stages, specified in the payload.
- represents a collection of domainname resources.
- describes existing models defined for a restapi resource.
- deletes an existing authorizer resource.
- creates a deployment resource, which makes a specified restapi callable over the internet.
- updates a documentation part.
- getstages
- deletes a documentation version.
- creates a new basepathmapping resource.
- getdeployments
- adds a new authorizer resource to an existing restapi resource.
- createauthorizer
- updatedeployment
- gets all the usage plan keys representing the api keys added to a specified usage plan.
- create an apikey resource.
- gets a documentation version.
- gets documentation parts.
- importdocumentationparts
- gets a gatewayresponse of a specified response type on the given restapi.
- simulate the execution of an authorizer in your restapi with headers, parameters, and an incoming request body.
- adds a new model resource to an existing restapi resource.
- changes information about an clientcertificate resource.
- apis.io
- createrequestvalidator
- getdocumentationpart
- creates a documentation version
- lists the restapis resources for your collection.
- creates a resource resource.
- deleteauthorizer
- createdomainname
- getvpclinks
- updates a documentation version.
- gets information about the current clientcertificate resource.
- deletes a deployment resource. deleting a deployment will only succeed if there are no stage resources associated with it.
- createmodel
- updatebasepathmapping
- deletedomainname
- updategatewayresponse
- createvpclink
- getclientcertificate
- deletegatewayresponse
- updateauthorizer
- getrequestvalidators
- gets information about a deployments collection.
- createusageplan
- updatedocumentationpart
- createstage
- getapikeys
- getmodels
- getauthorizer
- getdocumentationparts
- gets information about the current apikey resource.
- deletes the basepathmapping resource.
- deletes the clientcertificate resource.
- createresource
- getusageplankeys
- getbasepathmapping
- gets documentation versions.
- represents a delete integration.
- imports documentation parts
- engineering
- represents a collection of basepathmapping resources.
- getdomainnames
- describe an existing authorizers resource.
- getbasepathmappings
- creates a vpc link, under the caller's account in a selected region, in an asynchronous operation that typically takes 2-4 minutes to complete and become operational. the caller must have permissions to create and update vpc endpoint servic
- describe a basepathmapping resource.
- updates a gatewayresponse of a specified response type on the given restapi.
- changes information about the basepathmapping resource.
- deleteintegration
- createbasepathmapping
- updatedocumentationversion
- getdomainname
- createdeployment
- deleteclientcertificate
- creates a usage plan key for adding an existing api key to a usage plan.
- gets information about a deployment resource.
- describe an existing authorizer resource.
- deletedocumentationpart
- createrestapi
- creates a customization of a gatewayresponse of a specified response type and status code on the given restapi.
- putgatewayresponse
- platform
- creates a new stage resource that references a pre-existing deployment for the api.
- getdeployment
- gets the requestvalidators collection of a given restapi.
- createapikey
- gets information about one or more stage resources.
- getauthorizers
slug: engineering-platform-capability
source_filename: engineering-platform-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: APIs.io Engineering Platform Amazon API Gateway\n  description: <fullname>Amazon API Gateway</fullname> <p>Amazon API Gateway helps developers deliver robust, secure, and\n    scalable mobile and web application back ends. API Gateway allows developers to securely connect mobile and web applications\n    to APIs that run on AWS Lambda, Amazon EC2, or other publicly addressable web services that are hosted outside of AWS.</p>\n  tags:\n  - Engineering\n  - Platform\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: engineering-platform\n    baseUri: http://apigateway.us-east-1.amazonaws.com\n    description: APIs.io Engineering Platform Amazon API Gateway HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{ENGINEERING_PLATFORM_TOKEN}}'\n    resources:\n    - name: apikeys\n      path: /apikeys\n      operations:\n\
  \      - name: createapikey\n        method: POST\n        description: Create an ApiKey resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getapikeys\n        method: GET\n        description: Gets information about the current ApiKeys resource.\n        inputParameters:\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        - name: name\n          in: query\n          type: string\n          description: The name of queried API keys.\n        - name: customerId\n          in: query\n          type: string\n          description: The identifier of a customer in AWS Marketplace or an external\
  \ system, such as a developer portal.\n        - name: includeValues\n          in: query\n          type: boolean\n          description: A boolean flag to specify whether (<code>true</code>) or not (<code>false</code>) the result contains\n            key values.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-authorizers\n      path: /restapis/{restapi_id}/authorizers\n      operations:\n      - name: createauthorizer\n        method: POST\n        description: Adds a new Authorizer resource to an existing RestApi resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getauthorizers\n\
  \        method: GET\n        description: Describe an existing Authorizers resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainnames-domain-name-basepathmappings\n      path: /domainnames/{domain_name}/basepathmappings\n      operations:\n      - name: createbasepathmapping\n        method: POST\n        description: Creates a new BasePathMapping resource.\n\
  \        inputParameters:\n        - name: domain_name\n          in: path\n          type: string\n          required: true\n          description: The domain name of the BasePathMapping resource to create.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbasepathmappings\n        method: GET\n        description: Represents a collection of BasePathMapping resources.\n        inputParameters:\n        - name: domain_name\n          in: path\n          type: string\n          required: true\n          description: The domain name of a BasePathMapping resource.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value\
  \ is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-deployments\n      path: /restapis/{restapi_id}/deployments\n      operations:\n      - name: createdeployment\n        method: POST\n        description: Creates a Deployment resource, which makes a specified RestApi callable over the internet.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeployments\n        method: GET\n        description: Gets information about a Deployments collection.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The string identifier of the associated RestApi.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-documentation-parts\n      path: /restapis/{restapi_id}/documentation/parts\n      operations:\n      - name: createdocumentationpart\n        method: POST\n        description: Creates a documentation part.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n   \
  \     outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdocumentationparts\n        method: GET\n        description: Gets documentation parts.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: type\n          in: query\n          type: string\n          description: The type of API entities of the to-be-retrieved documentation parts.\n        - name: name\n          in: query\n          type: string\n          description: The name of API entities of the to-be-retrieved documentation parts.\n        - name: path\n          in: query\n          type: string\n          description: The path of API entities of the to-be-retrieved documentation parts.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position\
  \ in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        - name: locationStatus\n          in: query\n          type: string\n          description: The status of the API documentation parts to retrieve. Valid values are <code>DOCUMENTED</code> for\n            retrieving DocumentationPart resources with content and <cod\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: importdocumentationparts\n        method: PUT\n        description: Imports documentation parts\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: mode\n          in: query\n          type: string\n\
  \          description: 'A query parameter to indicate whether to overwrite (<code>OVERWRITE</code>) any existing DocumentationParts\n            definition or to merge (<code>MERGE</code>) the new '\n        - name: failonwarnings\n          in: query\n          type: boolean\n          description: A query parameter to specify whether to rollback the documentation importation (<code>true</code>)\n            or not (<code>false</code>) when a warning is encountered. Th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-documentation-versions\n      path: /restapis/{restapi_id}/documentation/versions\n      operations:\n      - name: createdocumentationversion\n        method: POST\n        description: Creates a documentation version\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description:\
  \ The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdocumentationversions\n        method: GET\n        description: Gets documentation versions.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainnames\n      path:\
  \ /domainnames\n      operations:\n      - name: createdomainname\n        method: POST\n        description: Creates a new domain name.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdomainnames\n        method: GET\n        description: Represents a collection of DomainName resources.\n        inputParameters:\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-models\n      path: /restapis/{restapi_id}/models\n      operations:\n      - name:\
  \ createmodel\n        method: POST\n        description: Adds a new Model resource to an existing RestApi resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The RestApi identifier under which the Model will be created.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getmodels\n        method: GET\n        description: Describes existing Models defined for a RestApi resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n\
  \          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-requestvalidators\n      path: /restapis/{restapi_id}/requestvalidators\n      operations:\n      - name: createrequestvalidator\n        method: POST\n        description: Creates a RequestValidator of a given RestApi.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getrequestvalidators\n        method: GET\n        description: Gets the RequestValidators collection of a given RestApi.\n        inputParameters:\n    \
  \    - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-resources-parent-id\n      path: /restapis/{restapi_id}/resources/{parent_id}\n      operations:\n      - name: createresource\n        method: POST\n        description: Creates a Resource resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n\
  \          description: The string identifier of the associated RestApi.\n        - name: parent_id\n          in: path\n          type: string\n          required: true\n          description: The parent resource's identifier.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis\n      path: /restapis\n      operations:\n      - name: createrestapi\n        method: POST\n        description: Creates a new RestApi resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getrestapis\n        method: GET\n        description: Lists the RestApis resources for your collection.\n        inputParameters:\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n     \
  \     type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-stages\n      path: /restapis/{restapi_id}/stages\n      operations:\n      - name: createstage\n        method: POST\n        description: Creates a new Stage resource that references a pre-existing Deployment for the API.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getstages\n        method: GET\n        description: Gets information about one or more Stage resources.\n        inputParameters:\n\
  \        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: deploymentId\n          in: query\n          type: string\n          description: The stages' deployment identifiers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usageplans\n      path: /usageplans\n      operations:\n      - name: createusageplan\n        method: POST\n        description: Creates a usage plan with the throttle and quota limits, as well as the associated API stages, specified\n          in the payload.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getusageplans\n        method: GET\n        description: Gets all the usage plans of the caller's account.\n        inputParameters:\n        - name:\
  \ position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: keyId\n          in: query\n          type: string\n          description: The identifier of the API key associated with the usage plans.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: usageplans-usageplanid-keys\n      path: /usageplans/{usageplanId}/keys\n      operations:\n      - name: createusageplankey\n        method: POST\n        description: Creates a usage plan key for adding an existing API key to a usage plan.\n        inputParameters:\n        - name: usageplanId\n          in: path\n          type: string\n          required: true\n   \
  \       description: The Id of the UsagePlan resource representing the usage plan containing the to-be-created UsagePlanKey\n            resource representing a plan customer.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getusageplankeys\n        method: GET\n        description: Gets all the usage plan keys representing the API keys added to a specified usage plan.\n        inputParameters:\n        - name: usageplanId\n          in: path\n          type: string\n          required: true\n          description: The Id of the UsagePlan resource representing the usage plan containing the to-be-retrieved UsagePlanKey\n            resource representing a plan customer.\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n     \
  \     description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        - name: name\n          in: query\n          type: string\n          description: A query parameter specifying the name of the to-be-returned usage plan keys.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vpclinks\n      path: /vpclinks\n      operations:\n      - name: createvpclink\n        method: POST\n        description: Creates a VPC link, under the caller's account in a selected region, in an asynchronous operation that\n          typically takes 2-4 minutes to complete and become operational. The caller must have permissions to create and update\n          VPC Endpoint servic\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getvpclinks\n        method: GET\n      \
  \  description: Gets the VpcLinks collection under the caller's account in a selected region.\n        inputParameters:\n        - name: position\n          in: query\n          type: string\n          description: The current pagination position in the paged result set.\n        - name: limit\n          in: query\n          type: integer\n          description: The maximum number of returned results per page. The default value is 25 and the maximum value is 500.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: apikeys-api-key\n      path: /apikeys/{api_Key}\n      operations:\n      - name: deleteapikey\n        method: DELETE\n        description: Deletes the ApiKey resource.\n        inputParameters:\n        - name: api_Key\n          in: path\n          type: string\n          required: true\n          description: The identifier of the ApiKey resource to be deleted.\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getapikey\n        method: GET\n        description: Gets information about the current ApiKey resource.\n        inputParameters:\n        - name: api_Key\n          in: path\n          type: string\n          required: true\n          description: The identifier of the ApiKey resource.\n        - name: includeValue\n          in: query\n          type: boolean\n          description: A boolean flag to specify whether (<code>true</code>) or not (<code>false</code>) the result contains\n            the key value.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateapikey\n        method: PATCH\n        description: Changes information about an ApiKey resource.\n        inputParameters:\n        - name: api_Key\n          in: path\n          type: string\n          required: true\n\
  \          description: The identifier of the ApiKey resource to be updated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-authorizers-authorizer-id\n      path: /restapis/{restapi_id}/authorizers/{authorizer_id}\n      operations:\n      - name: deleteauthorizer\n        method: DELETE\n        description: Deletes an existing Authorizer resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: authorizer_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Authorizer resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getauthorizer\n        method:\
  \ GET\n        description: Describe an existing Authorizer resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: authorizer_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Authorizer resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: testinvokeauthorizer\n        method: POST\n        description: Simulate the execution of an Authorizer in your RestApi with headers, parameters, and an incoming request\n          body.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: authorizer_id\n     \
  \     in: path\n          type: string\n          required: true\n          description: Specifies a test invoke authorizer request's Authorizer ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateauthorizer\n        method: PATCH\n        description: Updates an existing Authorizer resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: authorizer_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Authorizer resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: domainnames-domain-name-basepathmappings-base-pa\n      path: /domainnames/{domain_name}/basepathmappings/{base_path}\n\
  \      operations:\n      - name: deletebasepathmapping\n        method: DELETE\n        description: Deletes the BasePathMapping resource.\n        inputParameters:\n        - name: domain_name\n          in: path\n          type: string\n          required: true\n          description: The domain name of the BasePathMapping resource to delete.\n        - name: base_path\n          in: path\n          type: string\n          required: true\n          description: <p>The base path name of the BasePathMapping resource to delete.</p> <p>To specify an empty base path,\n            set this parameter to <code>'(none)'</code>.</p>\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getbasepathmapping\n        method: GET\n        description: Describe a BasePathMapping resource.\n        inputParameters:\n        - name: domain_name\n          in: path\n          type: string\n          required: true\n\
  \          description: The domain name of the BasePathMapping resource to be described.\n        - name: base_path\n          in: path\n          type: string\n          required: true\n          description: The base path name that callers of the API must provide as part of the URL after the domain name. This\n            value must be unique for all of the mappings across a sin\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebasepathmapping\n        method: PATCH\n        description: Changes information about the BasePathMapping resource.\n        inputParameters:\n        - name: domain_name\n          in: path\n          type: string\n          required: true\n          description: The domain name of the BasePathMapping resource to change.\n        - name: base_path\n          in: path\n          type: string\n          required: true\n          description: <p>The base path of the\
  \ BasePathMapping resource to change.</p> <p>To specify an empty base path, set\n            this parameter to <code>'(none)'</code>.</p>\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: clientcertificates-clientcertificate-id\n      path: /clientcertificates/{clientcertificate_id}\n      operations:\n      - name: deleteclientcertificate\n        method: DELETE\n        description: Deletes the ClientCertificate resource.\n        inputParameters:\n        - name: clientcertificate_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the ClientCertificate resource to be deleted.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getclientcertificate\n        method: GET\n        description: Gets information about the current ClientCertificate resource.\n\
  \        inputParameters:\n        - name: clientcertificate_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the ClientCertificate resource to be described.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateclientcertificate\n        method: PATCH\n        description: Changes information about an ClientCertificate resource.\n        inputParameters:\n        - name: clientcertificate_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the ClientCertificate resource to be updated.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-deployments-deployment-id\n      path: /restapis/{restapi_id}/deployments/{deployment_id}\n      operations:\n      - name: deletedeployment\n\
  \        method: DELETE\n        description: Deletes a Deployment resource. Deleting a deployment will only succeed if there are no Stage resources\n          associated with it.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: deployment_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Deployment resource to delete.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: getdeployment\n        method: GET\n        description: Gets information about a Deployment resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n \
  \       - name: deployment_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the Deployment resource to get information about.\n        - name: embed\n          in: query\n          type: array\n          description: 'A query parameter to retrieve the specified embedded resources of the returned Deployment resource\n            in the response. In a REST API call, this <code>embed</code> '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedeployment\n        method: PATCH\n        description: Changes information about a Deployment resource.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: deployment_id\n          in: path\n          type: string\n          required:\
  \ true\n          description: The replacement identifier for the Deployment resource to change information about.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: restapis-restapi-id-documentation-parts-part-id\n      path: /restapis/{restapi_id}/documentation/parts/{part_id}\n      operations:\n      - name: deletedocumentationpart\n        method: DELETE\n        description: Deletes a documentation part\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: part_id\n          in: path\n          type: string\n          required: true\n          description: The identifier of the to-be-deleted documentation part.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \      - name: getdocumentationpart\n        method: GET\n        description: Gets a documentation part.\n        inputParameters:\n        - name: restapi_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        - name: part_id\n          in: path\n          type: string\n          required: true\n          description: The string identifier of the associated RestApi.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedocumentationpart\n        method: PATCH\n        descri\n\n# --- truncated at 32 KB (105 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/apis-io-engineering-platform/refs/heads/main/capabilities/engineering-platform-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/apis-io-engineering-platform/refs/heads/main/capabilities/engineering-platform-capability.yaml
tags:
- Engineering
- Platform
- API
tools:
- description: Create an ApiKey resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createapikey
- description: Gets information about the current ApiKeys resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikeys
- description: Adds a new Authorizer resource to an existing RestApi resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createauthorizer
- description: Describe an existing Authorizers resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthorizers
- description: Creates a new BasePathMapping resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbasepathmapping
- description: Represents a collection of BasePathMapping resources.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbasepathmappings
- description: Creates a Deployment resource, which makes a specified RestApi callable over the internet.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdeployment
- description: Gets information about a Deployments collection.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployments
- description: Creates a documentation part.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocumentationpart
- description: Gets documentation parts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentationparts
- description: Imports documentation parts
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: importdocumentationparts
- description: Creates a documentation version
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdocumentationversion
- description: Gets documentation versions.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentationversions
- description: Creates a new domain name.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdomainname
- description: Represents a collection of DomainName resources.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomainnames
- description: Adds a new Model resource to an existing RestApi resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmodel
- description: Describes existing Models defined for a RestApi resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmodels
- description: Creates a RequestValidator of a given RestApi.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrequestvalidator
- description: Gets the RequestValidators collection of a given RestApi.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrequestvalidators
- description: Creates a Resource resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createresource
- description: Creates a new RestApi resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createrestapi
- description: Lists the RestApis resources for your collection.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getrestapis
- description: Creates a new Stage resource that references a pre-existing Deployment for the API.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createstage
- description: Gets information about one or more Stage resources.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstages
- description: Creates a usage plan with the throttle and quota limits, as well as the associated API stages, specified in the payload.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusageplan
- description: Gets all the usage plans of the caller's account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusageplans
- description: Creates a usage plan key for adding an existing API key to a usage plan.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createusageplankey
- description: Gets all the usage plan keys representing the API keys added to a specified usage plan.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getusageplankeys
- description: Creates a VPC link, under the caller's account in a selected region, in an asynchronous operation that typically takes 2-4 minutes to complete and become operational. The caller must have permissions to create and update VPC Endpoint servic
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createvpclink
- description: Gets the VpcLinks collection under the caller's account in a selected region.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getvpclinks
- description: Deletes the ApiKey resource.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: Gets information about the current ApiKey resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikey
- description: Changes information about an ApiKey resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateapikey
- description: Deletes an existing Authorizer resource.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteauthorizer
- description: Describe an existing Authorizer resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getauthorizer
- description: Simulate the execution of an Authorizer in your RestApi with headers, parameters, and an incoming request body.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: testinvokeauthorizer
- description: Updates an existing Authorizer resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateauthorizer
- description: Deletes the BasePathMapping resource.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebasepathmapping
- description: Describe a BasePathMapping resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbasepathmapping
- description: Changes information about the BasePathMapping resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebasepathmapping
- description: Deletes the ClientCertificate resource.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteclientcertificate
- description: Gets information about the current ClientCertificate resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getclientcertificate
- description: Changes information about an ClientCertificate resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateclientcertificate
- description: Deletes a Deployment resource. Deleting a deployment will only succeed if there are no Stage resources associated with it.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedeployment
- description: Gets information about a Deployment resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdeployment
- description: Changes information about a Deployment resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedeployment
- description: Deletes a documentation part
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocumentationpart
- description: Gets a documentation part.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentationpart
- description: Updates a documentation part.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocumentationpart
- description: Deletes a documentation version.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocumentationversion
- description: Gets a documentation version.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocumentationversion
- description: Updates a documentation version.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedocumentationversion
- description: Deletes the DomainName resource.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedomainname
- description: Represents a domain name that is contained in a simpler, more intuitive URL that can be called.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdomainname
- description: Changes information about the DomainName resource.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatedomainname
- description: Clears any customization of a GatewayResponse of a specified response type on the given RestApi and resets it with the default settings.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletegatewayresponse
- description: Gets a GatewayResponse of a specified response type on the given RestApi.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgatewayresponse
- description: Creates a customization of a GatewayResponse of a specified response type and status code on the given RestApi.
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: putgatewayresponse
- description: Updates a GatewayResponse of a specified response type on the given RestApi.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updategatewayresponse
- description: Represents a delete integration.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteintegration
---
