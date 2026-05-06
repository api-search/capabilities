---
categories: []
consumed_apis: []
description: The <b>Account API</b> gives sellers the ability to configure their eBay seller accounts, including the seller's policies (eBay business policies and seller-defined custom policies), opt in and out of eBay seller programs, configure sales tax tables, and get account information. <br><br>For details on the availability of the methods in this API, see <a href="/api-docs/sell/account/overview.html#requirements">Account API requirements and restrictions</a>.
layout: capability
name: eBay Account API
operations:
- description: This method retrieves the list of custom policies specified by the <b>policy_types</b> query parameter.<br><br><span class="tablenote"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MAR
  method: GET
  name: getcustompolicies
  path: /custom_policy/
- description: 'This method creates a new custom policy in which a seller specifies their terms for complying with local governmental regulations. <br/><br/>Two Custom Policy types are supported: <ul><li>Product Compliance (PRODUCT_COMPLIANCE)</li> <li>Tak'
  method: POST
  name: createcustompolicy
  path: /custom_policy/
- description: This method retrieves the custom policy specified by the <b>custom_policy_id</b> path parameter.<br><br><span class="tablenote"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MARKETPLAC
  method: GET
  name: getcustompolicy
  path: /custom_policy/{custom_policy_id}
- description: This method updates an existing custom policy specified by the <b>custom_policy_id</b> path parameter. This method overwrites the policy's <b>Name</b>, <b>Label</b>, and <b>Description</b> fields. Therefore, the complete, current text of al
  method: PUT
  name: updatecustompolicy
  path: /custom_policy/{custom_policy_id}
- description: This method creates a new fulfillment policy where the policy encapsulates seller's terms for fulfilling item purchases. Fulfillment policies include the shipment options that the seller offers to buyers. <br><br>Each policy targets a speci
  method: POST
  name: createfulfillmentpolicy
  path: /fulfillment_policy/
- description: This method retrieves the complete details of a fulfillment policy. Supply the ID of the policy you want to retrieve using the <b>fulfillmentPolicyId</b> path parameter.
  method: GET
  name: getfulfillmentpolicy
  path: /fulfillment_policy/{fulfillmentPolicyId}
- description: This method updates an existing fulfillment policy. Specify the policy you want to update using the <b>fulfillment_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the ex
  method: PUT
  name: updatefulfillmentpolicy
  path: /fulfillment_policy/{fulfillmentPolicyId}
- description: This method deletes a fulfillment policy. Supply the ID of the policy you want to delete in the <b>fulfillmentPolicyId</b> path parameter.
  method: DELETE
  name: deletefulfillmentpolicy
  path: /fulfillment_policy/{fulfillmentPolicyId}
- description: This method retrieves all the fulfillment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace
  method: GET
  name: getfulfillmentpolicies
  path: /fulfillment_policy
- description: This method retrieves the details for a specific fulfillment policy. In the request, supply both the policy <code>name</code> and its associated <code>marketplace_id</code> as query parameters. <br><br><b>Marketplaces and locales</b> <br><b
  method: GET
  name: getfulfillmentpolicybyname
  path: /fulfillment_policy/get_by_policy_name
- description: This method retrieves all the payment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that
  method: GET
  name: getpaymentpolicies
  path: /payment_policy
- description: This method creates a new payment policy where the policy encapsulates seller's terms for order payments. <br><br>Each policy targets a specific eBay marketplace and category group, and you can create multiple policies for each combination.
  method: POST
  name: createpaymentpolicy
  path: /payment_policy
- description: This method retrieves the complete details of a payment policy. Supply the ID of the policy you want to retrieve using the <b>paymentPolicyId</b> path parameter.
  method: GET
  name: getpaymentpolicy
  path: /payment_policy/{payment_policy_id}
- description: This method updates an existing payment policy. Specify the policy you want to update using the <b>payment_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing p
  method: PUT
  name: updatepaymentpolicy
  path: /payment_policy/{payment_policy_id}
- description: This method deletes a payment policy. Supply the ID of the policy you want to delete in the <b>paymentPolicyId</b> path parameter.
  method: DELETE
  name: deletepaymentpolicy
  path: /payment_policy/{payment_policy_id}
- description: This method retrieves the details of a specific payment policy. Supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b> <br><br>Get the
  method: GET
  name: getpaymentpolicybyname
  path: /payment_policy/get_by_policy_name
- description: <span class="tablenote"><b>Note:</b> This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow.</span><br>This method returns whether or not the user is opted-in to the
  method: GET
  name: getpaymentsprogram
  path: /payments_program/{marketplace_id}/{payments_program_type}
- description: <span class="tablenote"><b>Note:</b> This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow.</span><br>This method retrieves a seller's onboarding status for a payme
  method: GET
  name: getpaymentsprogramonboarding
  path: /payments_program/{marketplace_id}/{payments_program_type}/onboarding
- description: This method retrieves the seller's current set of privileges, including whether or not the seller's eBay registration has been completed, as well as the details of their site-wide <b>sellingLimt</b> (the amount and quantity they can sell on
  method: GET
  name: getprivileges
  path: /privilege
- description: This method gets a list of the seller programs that the seller has opted-in to.
  method: GET
  name: getoptedinprograms
  path: /program/get_opted_in_programs
- description: This method opts the seller in to an eBay seller program. Refer to the <a href="/api-docs/sell/account/overview.html#opt-in" target="_blank">Account API overview</a> for information about available eBay seller programs.<br><br><span class="
  method: POST
  name: optintoprogram
  path: /program/opt_in
- description: This method opts the seller out of a seller program to which you have previously opted-in to. Get a list of the seller programs you have opted-in to using the <b>getOptedInPrograms</b> call.
  method: POST
  name: optoutofprogram
  path: /program/opt_out
- description: This method retrieves a seller's <i>shipping rate tables</i> for the country specified in the <b>country_code</b> query parameter. If you call this method without specifying a country code, the call returns all of the seller's shipping rate
  method: GET
  name: getratetables
  path: /rate_table
- description: This method retrieves all the return policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that
  method: GET
  name: getreturnpolicies
  path: /return_policy
- description: This method creates a new return policy where the policy encapsulates seller's terms for returning items. <br><br>Each policy targets a specific marketplace, and you can create multiple policies for each marketplace. Return policies are not
  method: POST
  name: createreturnpolicy
  path: /return_policy
- description: This method retrieves the complete details of the return policy specified by the <b>returnPolicyId</b> path parameter.
  method: GET
  name: getreturnpolicy
  path: /return_policy/{return_policy_id}
- description: This method updates an existing return policy. Specify the policy you want to update using the <b>return_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing pol
  method: PUT
  name: updatereturnpolicy
  path: /return_policy/{return_policy_id}
- description: This method deletes a return policy. Supply the ID of the policy you want to delete in the <b>returnPolicyId</b> path parameter.
  method: DELETE
  name: deletereturnpolicy
  path: /return_policy/{return_policy_id}
- description: This method retrieves the details of a specific return policy. Supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b> <br><br>Get the
  method: GET
  name: getreturnpolicybyname
  path: /return_policy/get_by_policy_name
- description: This call retrieves the current sales-tax table entry for a specific tax jurisdiction. Specify the jurisdiction to retrieve using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters. All four response fields will be returned if
  method: GET
  name: getsalestax
  path: /sales_tax/{countryCode}/{jurisdictionId}
- description: 'This method creates or updates a sales-tax table entry for a jurisdiction. Specify the tax table entry you want to configure using the two path parameters: <b>countryCode</b> and <b>jurisdictionId</b>. <br><br>A tax table entry for a jurisd'
  method: PUT
  name: createorreplacesalestax
  path: /sales_tax/{countryCode}/{jurisdictionId}
- description: This call deletes a sales-tax table entry for a jurisdiction. Specify the jurisdiction to delete using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters.<br><br><span class="tablenote"><b>Note:</b> Sales-tax tables are only a
  method: DELETE
  name: deletesalestax
  path: /sales_tax/{countryCode}/{jurisdictionId}
- description: Use this call to retrieve all sales tax table entries that the seller has defined for a specific country. All four response fields will be returned for each tax jurisdiction that matches the search criteria. <br><br><span class="tablenote">
  method: GET
  name: getsalestaxes
  path: /sales_tax
- description: This method retrieves a list of subscriptions associated with the seller account.
  method: GET
  name: getsubscription
  path: /subscription
- description: <span class="tablenote"><b>Note:</b>This method was originally created to see which onboarding requirements were still pending for sellers being onboarded for eBay managed payments, but now that all seller accounts are onboarded globally, t
  method: GET
  name: getkyc
  path: /kyc
- description: This method allows developers to check the seller eligibility status for eBay advertising programs.
  method: GET
  name: getadvertisingeligibility
  path: /advertising_eligibility
personas: []
provider_name: eBay
provider_slug: ebay
search_terms:
- getpaymentsprogramonboarding
- getreturnpolicy
- getfulfillmentpolicy
- createreturnpolicy
- this method opts the seller out of a seller program to which you have previously opted-in to. get a list of the seller programs you have opted-in to using the <b>getoptedinprograms</b> call.
- getfulfillmentpolicies
- this method retrieves the complete details of a fulfillment policy. supply the id of the policy you want to retrieve using the <b>fulfillmentpolicyid</b> path parameter.
- getsubscription
- deletesalestax
- this method retrieves the custom policy specified by the <b>custom_policy_id</b> path parameter.<br><br><span class="tablenote"><b>note:</b> custom policies are no longer coupled with a specific ebay marketplace, so the <b>ebay-c-marketplac
- this method updates an existing fulfillment policy. specify the policy you want to update using the <b>fulfillment_policy_id</b> path parameter. supply a complete policy payload with the updates you want to make; this call overwrites the ex
- api
- getfulfillmentpolicybyname
- this method retrieves all the fulfillment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>marketplaces and locales</b> <br><br>get the correct policies for a marketplace
- ebay
- updatepaymentpolicy
- this method creates a new payment policy where the policy encapsulates seller's terms for order payments. <br><br>each policy targets a specific ebay marketplace and category group, and you can create multiple policies for each combination.
- this method retrieves a seller's <i>shipping rate tables</i> for the country specified in the <b>country_code</b> query parameter. if you call this method without specifying a country code, the call returns all of the seller's shipping rate
- this method retrieves the details of a specific payment policy. supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>marketplaces and locales</b> <br><br>get the
- this method retrieves a list of subscriptions associated with the seller account.
- deletepaymentpolicy
- getadvertisingeligibility
- getoptedinprograms
- getprivileges
- getsalestaxes
- marketplace
- this method retrieves all the return policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>marketplaces and locales</b> <br><br>get the correct policies for a marketplace that
- getkyc
- this method retrieves the complete details of a payment policy. supply the id of the policy you want to retrieve using the <b>paymentpolicyid</b> path parameter.
- this method deletes a return policy. supply the id of the policy you want to delete in the <b>returnpolicyid</b> path parameter.
- createpaymentpolicy
- updatereturnpolicy
- this call retrieves the current sales-tax table entry for a specific tax jurisdiction. specify the jurisdiction to retrieve using the <b>countrycode</b> and <b>jurisdictionid</b> path parameters. all four response fields will be returned if
- optintoprogram
- createcustompolicy
- this method deletes a payment policy. supply the id of the policy you want to delete in the <b>paymentpolicyid</b> path parameter.
- updatefulfillmentpolicy
- <span class="tablenote"><b>note:</b> this method is no longer applicable, as all seller accounts globally have been enabled for the new ebay payment and checkout flow.</span><br>this method retrieves a seller's onboarding status for a payme
- 'this method creates a new custom policy in which a seller specifies their terms for complying with local governmental regulations. <br/><br/>two custom policy types are supported: <ul><li>product compliance (product_compliance)</li> <li>tak'
- updatecustompolicy
- 'this method creates or updates a sales-tax table entry for a jurisdiction. specify the tax table entry you want to configure using the two path parameters: <b>countrycode</b> and <b>jurisdictionid</b>. <br><br>a tax table entry for a jurisd'
- this method gets a list of the seller programs that the seller has opted-in to.
- this method retrieves the details of a specific return policy. supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>marketplaces and locales</b> <br><br>get the
- getratetables
- this method creates a new fulfillment policy where the policy encapsulates seller's terms for fulfilling item purchases. fulfillment policies include the shipment options that the seller offers to buyers. <br><br>each policy targets a speci
- commerce
- getcustompolicy
- this method updates an existing return policy. specify the policy you want to update using the <b>return_policy_id</b> path parameter. supply a complete policy payload with the updates you want to make; this call overwrites the existing pol
- this method updates an existing custom policy specified by the <b>custom_policy_id</b> path parameter. this method overwrites the policy's <b>name</b>, <b>label</b>, and <b>description</b> fields. therefore, the complete, current text of al
- this method updates an existing payment policy. specify the policy you want to update using the <b>payment_policy_id</b> path parameter. supply a complete policy payload with the updates you want to make; this call overwrites the existing p
- this method deletes a fulfillment policy. supply the id of the policy you want to delete in the <b>fulfillmentpolicyid</b> path parameter.
- <span class="tablenote"><b>note:</b> this method is no longer applicable, as all seller accounts globally have been enabled for the new ebay payment and checkout flow.</span><br>this method returns whether or not the user is opted-in to the
- optoutofprogram
- products
- getpaymentpolicybyname
- getreturnpolicies
- deletefulfillmentpolicy
- auctions
- this method allows developers to check the seller eligibility status for ebay advertising programs.
- this method retrieves the list of custom policies specified by the <b>policy_types</b> query parameter.<br><br><span class="tablenote"><b>note:</b> custom policies are no longer coupled with a specific ebay marketplace, so the <b>ebay-c-mar
- getpaymentpolicies
- this method retrieves the details for a specific fulfillment policy. in the request, supply both the policy <code>name</code> and its associated <code>marketplace_id</code> as query parameters. <br><br><b>marketplaces and locales</b> <br><b
- deletereturnpolicy
- createorreplacesalestax
- getsalestax
- getpaymentsprogram
- use this call to retrieve all sales tax table entries that the seller has defined for a specific country. all four response fields will be returned for each tax jurisdiction that matches the search criteria. <br><br><span class="tablenote">
- this call deletes a sales-tax table entry for a jurisdiction. specify the jurisdiction to delete using the <b>countrycode</b> and <b>jurisdictionid</b> path parameters.<br><br><span class="tablenote"><b>note:</b> sales-tax tables are only a
- <span class="tablenote"><b>note:</b>this method was originally created to see which onboarding requirements were still pending for sellers being onboarded for ebay managed payments, but now that all seller accounts are onboarded globally, t
- this method opts the seller in to an ebay seller program. refer to the <a href="/api-docs/sell/account/overview.html#opt-in" target="_blank">account api overview</a> for information about available ebay seller programs.<br><br><span class="
- this method retrieves the seller's current set of privileges, including whether or not the seller's ebay registration has been completed, as well as the details of their site-wide <b>sellinglimt</b> (the amount and quantity they can sell on
- this method retrieves all the payment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>marketplaces and locales</b> <br><br>get the correct policies for a marketplace that
- getpaymentpolicy
- this method retrieves the complete details of the return policy specified by the <b>returnpolicyid</b> path parameter.
- this method creates a new return policy where the policy encapsulates seller's terms for returning items. <br><br>each policy targets a specific marketplace, and you can create multiple policies for each marketplace. return policies are not
- createfulfillmentpolicy
- getcustompolicies
- getreturnpolicybyname
slug: ebay-capability
source_filename: ebay-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: eBay Account API\n  description: The <b>Account API</b> gives sellers the ability to configure their eBay seller accounts, including the seller's\n    policies (eBay business policies and seller-defined custom policies), opt in and out of eBay seller programs, configure\n    sales tax tables, and get account information. <br><br>For details on the availability of the methods in this API, see\n    <a href=\"/api-docs/sell/account/overview.html#requirements\">Account API requirements and restrictions</a>.\n  tags:\n  - Ebay\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: ebay\n    baseUri: https://api.ebay.com/sell/account/v1\n    description: eBay Account API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{EBAY_TOKEN}}'\n    resources:\n    - name: custom-policy\n      path: /custom_policy/\n      operations:\n      - name: getcustompolicies\n    \
  \    method: GET\n        description: This method retrieves the list of custom policies specified by the <b>policy_types</b> query parameter.<br><br><span\n          class=\"tablenote\"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MAR\n        inputParameters:\n        - name: policy_types\n          in: query\n          type: string\n          description: This query parameter specifies the type of custom policies to be returned.<br><br>Multiple policy types\n            may be requested in a single call by providing a comma-d\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcustompolicy\n        method: POST\n        description: 'This method creates a new custom policy in which a seller specifies their terms for complying with local\n          governmental regulations. <br/><br/>Two Custom Policy types are supported: <ul><li>Product\
  \ Compliance (PRODUCT_COMPLIANCE)</li>\n          <li>Tak'\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: custom-policy-custom-policy-id\n      path: /custom_policy/{custom_policy_id}\n      operations:\n      - name: getcustompolicy\n        method: GET\n        description: This method retrieves the custom policy specified by the <b>custom_policy_id</b> path parameter.<br><br><span\n          class=\"tablenote\"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MARKETPLAC\n        inputParameters:\n        - name: custom_policy_id\n\
  \          in: path\n          type: string\n          required: true\n          description: This path parameter is the unique identifier of the custom policy to retrieve.<br><br> This ID can\n            be retrieved for a custom policy by using the <a href=\"/api-d\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecustompolicy\n        method: PUT\n        description: This method updates an existing custom policy specified by the <b>custom_policy_id</b> path parameter.\n          This method overwrites the policy's <b>Name</b>, <b>Label</b>, and <b>Description</b> fields. Therefore, the complete,\n          current text of al\n        inputParameters:\n        - name: custom_policy_id\n          in: path\n          type: string\n          required: true\n          description: This path parameter is the unique identifier of the custom policy to retrieve.<br><br> This ID can\n         \
  \   be retrieved for a custom policy by using the <a href=\"/api-d\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fulfillment-policy\n      path: /fulfillment_policy/\n      operations:\n      - name: createfulfillmentpolicy\n        method: POST\n        description: This method creates a new fulfillment policy where the policy encapsulates seller's terms for fulfilling\n          item purchases. Fulfillment policies include the shipment options that the seller offers to buyers. <br><br>Each\n          policy targets a speci\n        inputParameters:\n        - name: Content-Type\n          in: header\n\
  \          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fulfillment-policy-fulfillmentpolicyid\n      path: /fulfillment_policy/{fulfillmentPolicyId}\n      operations:\n      - name: getfulfillmentpolicy\n        method: GET\n        description: This method retrieves the complete details of a fulfillment policy. Supply the ID of the policy you want\n          to retrieve using the <b>fulfillmentPolicyId</b> path parameter.\n        inputParameters:\n        - name: fulfillmentPolicyId\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the fulfillment policy you want to retrieve.<br><br>\
  \ This ID\n            can be retrieved for a fulfillment policy by using the <a h\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefulfillmentpolicy\n        method: PUT\n        description: This method updates an existing fulfillment policy. Specify the policy you want to update using the <b>fulfillment_policy_id</b>\n          path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the ex\n        inputParameters:\n        - name: fulfillmentPolicyId\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the fulfillment policy you want to update.<br><br>This ID can\n            be retrieved for a specific fulfillment policy by using th\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description:\
  \ 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletefulfillmentpolicy\n        method: DELETE\n        description: This method deletes a fulfillment policy. Supply the ID of the policy you want to delete in the <b>fulfillmentPolicyId</b>\n          path parameter.\n        inputParameters:\n        - name: fulfillmentPolicyId\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the fulfillment policy to delete.<br><br> This ID can be retrieved\n            for a fulfillment policy by using the <a href=\"/api-d\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: fulfillment-policy\n      path: /fulfillment_policy\n      operations:\n      - name: getfulfillmentpolicies\n        method: GET\n        description: 'This method retrieves all the fulfillment policies configured for the marketplace you specify using\n          the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct\n          policies for a marketplace '\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the eBay marketplace of the policies you want to retrieve. For implementation\n            help, refer to eBay API documentation at https://de\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fulfillment-policy-get-by-policy-name\n      path: /fulfillment_policy/get_by_policy_name\n      operations:\n\
  \      - name: getfulfillmentpolicybyname\n        method: GET\n        description: This method retrieves the details for a specific fulfillment policy. In the request, supply both the\n          policy <code>name</code> and its associated <code>marketplace_id</code> as query parameters. <br><br><b>Marketplaces\n          and locales</b> <br><b\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the eBay marketplace of the policy you want to retrieve. For implementation\n            help, refer to eBay API documentation at https://deve\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the seller-defined name of the fulfillment policy you want to retrieve.<br><br>This\n            value can be retrieved for a fulfillment poli\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-policy\n      path: /payment_policy\n      operations:\n      - name: getpaymentpolicies\n        method: GET\n        description: This method retrieves all the payment policies configured for the marketplace you specify using the <code>marketplace_id</code>\n          query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the eBay marketplace of the policies you want to retrieve. For implementation\n            help, refer to eBay API documentation at https://de\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createpaymentpolicy\n        method:\
  \ POST\n        description: This method creates a new payment policy where the policy encapsulates seller's terms for order payments.\n          <br><br>Each policy targets a specific eBay marketplace and category group, and you can create multiple policies\n          for each combination.\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-policy-payment-policy-id\n      path: /payment_policy/{payment_policy_id}\n      operations:\n      - name: getpaymentpolicy\n        method: GET\n        description: This method retrieves the complete details of a payment policy.\
  \ Supply the ID of the policy you want\n          to retrieve using the <b>paymentPolicyId</b> path parameter.\n        inputParameters:\n        - name: payment_policy_id\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the payment policy you want to retrieve. <br><br> This ID can\n            be retrieved for a payment policy by using the <a href=\"/a\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatepaymentpolicy\n        method: PUT\n        description: This method updates an existing payment policy. Specify the policy you want to update using the <b>payment_policy_id</b>\n          path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing\n          p\n        inputParameters:\n        - name: payment_policy_id\n          in: path\n        \
  \  type: string\n          required: true\n          description: This path parameter specifies the ID of the payment policy you want to update. <br><br> This ID can\n            be retrieved for a payment policy by using the <a href=\"/api\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletepaymentpolicy\n        method: DELETE\n        description: This method deletes a payment policy. Supply the ID of the policy you want to delete in the <b>paymentPolicyId</b>\n          path parameter.\n        inputParameters:\n        - name: payment_policy_id\n          in: path\n          type: string\n\
  \          required: true\n          description: This path parameter specifies the unique identifier of the payment policy you want to delete.<br><br>\n            This ID can be retrieved for a payment policy by using the\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payment-policy-get-by-policy-name\n      path: /payment_policy/get_by_policy_name\n      operations:\n      - name: getpaymentpolicybyname\n        method: GET\n        description: This method retrieves the details of a specific payment policy. Supply both the policy <code>name</code>\n          and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b>\n          <br><br>Get the\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the eBay\
  \ marketplace of the policy you want to retrieve. For implementation\n            help, refer to eBay API documentation at https://deve\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the seller-defined name of the payment policy you want to retrieve.<br><br>\n            This value can be retrieved for a payment policy by u\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-program-marketplace-id-payments-program\n      path: /payments_program/{marketplace_id}/{payments_program_type}\n      operations:\n      - name: getpaymentsprogram\n        method: GET\n        description: <span class=\"tablenote\"><b>Note:</b> This method is no longer applicable, as all seller accounts globally\n          have been enabled for the new eBay payment and checkout flow.</span><br>This method returns whether\
  \ or not the user\n          is opted-in to the\n        inputParameters:\n        - name: marketplace_id\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the eBay marketplace of the payments program for which you want to retrieve\n            the seller's status.\n        - name: payments_program_type\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the payments program whose status is returned by the call.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: payments-program-marketplace-id-payments-program\n      path: /payments_program/{marketplace_id}/{payments_program_type}/onboarding\n      operations:\n      - name: getpaymentsprogramonboarding\n        method: GET\n        description: <span class=\"tablenote\"><b>Note:</b> This method is no longer\
  \ applicable, as all seller accounts globally\n          have been enabled for the new eBay payment and checkout flow.</span><br>This method retrieves a seller's onboarding\n          status for a payme\n        inputParameters:\n        - name: marketplace_id\n          in: path\n          type: string\n          required: true\n          description: The eBay marketplace ID associated with the onboarding status to retrieve.\n        - name: payments_program_type\n          in: path\n          type: string\n          required: true\n          description: The type of payments program whose status is returned by the method.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: privilege\n      path: /privilege\n      operations:\n      - name: getprivileges\n        method: GET\n        description: This method retrieves the seller's current set of privileges, including whether or not the seller's eBay\n\
  \          registration has been completed, as well as the details of their site-wide <b>sellingLimt</b> (the amount and quantity\n          they can sell on\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: program-get-opted-in-programs\n      path: /program/get_opted_in_programs\n      operations:\n      - name: getoptedinprograms\n        method: GET\n        description: This method gets a list of the seller programs that the seller has opted-in to.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: program-opt-in\n      path: /program/opt_in\n      operations:\n      - name: optintoprogram\n        method: POST\n        description: This method opts the seller in to an eBay seller program. Refer to the <a href=\"/api-docs/sell/account/overview.html#opt-in\"\n          target=\"_blank\">Account API overview</a>\
  \ for information about available eBay seller programs.<br><br><span class=\"\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: program-opt-out\n      path: /program/opt_out\n      operations:\n      - name: optoutofprogram\n        method: POST\n        description: This method opts the seller out of a seller program to which you have previously opted-in to. Get a list\n          of the seller programs you have opted-in to using the <b>getOptedInPrograms</b> call.\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n        \
  \  required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rate-table\n      path: /rate_table\n      operations:\n      - name: getratetables\n        method: GET\n        description: This method retrieves a seller's <i>shipping rate tables</i> for the country specified in the <b>country_code</b>\n          query parameter. If you call this method without specifying a country code, the call returns all of the seller's\n          shipping rate\n        inputParameters:\n        - name: country_code\n          in: query\n          type: string\n          description: This query parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html\n            \" title=\"\
  https://www.iso.org \" target=\"_blank\">ISO 3166</\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: return-policy\n      path: /return_policy\n      operations:\n      - name: getreturnpolicies\n        method: GET\n        description: 'This method retrieves all the return policies configured for the marketplace you specify using the <code>marketplace_id</code>\n          query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that '\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the ID of the eBay marketplace of the policy you want to retrieve. For\n            implementation help, refer to eBay API documentation at ht\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n      \
  \    type: object\n          value: $.\n      - name: createreturnpolicy\n        method: POST\n        description: This method creates a new return policy where the policy encapsulates seller's terms for returning items.\n          <br><br>Each policy targets a specific marketplace, and you can create multiple policies for each marketplace. Return\n          policies are not\n        inputParameters:\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: return-policy-return-policy-id\n      path: /return_policy/{return_policy_id}\n      operations:\n      - name: getreturnpolicy\n        method: GET\n \
  \       description: This method retrieves the complete details of the return policy specified by the <b>returnPolicyId</b>\n          path parameter.\n        inputParameters:\n        - name: return_policy_id\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the unique identifier of the return policy you want to retrieve. <br><br>\n            This ID can be retrieved for a return policy by using th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatereturnpolicy\n        method: PUT\n        description: This method updates an existing return policy. Specify the policy you want to update using the <b>return_policy_id</b>\n          path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing\n          pol\n        inputParameters:\n        - name: return_policy_id\n\
  \          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the return policy you want to update. <br><br> This ID can\n            be retrieved for a return policy by using the <a href=\"/api-d\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: 'This header indicates the format of the request body provided by the client. Its value should be set\n            to <b>application/json</b>. <br><br> For more information, '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletereturnpolicy\n        method: DELETE\n        description: This method deletes a return policy. Supply the ID of the policy you want to delete in the <b>returnPolicyId</b>\n          path parameter.\n        inputParameters:\n        - name: return_policy_id\n          in: path\n\
  \          type: string\n          required: true\n          description: This path parameter specifies the unique identifier of the return policy you want to delete.<br><br>\n            This ID can be retrieved for a return policy by using the <\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: return-policy-get-by-policy-name\n      path: /return_policy/get_by_policy_name\n      operations:\n      - name: getreturnpolicybyname\n        method: GET\n        description: 'This method retrieves the details of a specific return policy. Supply both the policy <code>name</code>\n          and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b>\n          <br><br>Get the '\n        inputParameters:\n        - name: marketplace_id\n          in: query\n          type: string\n          required: true\n          description: This query parameter\
  \ specifies the ID of the eBay marketplace of the policy you want to retrieve. For\n            implementation help, refer to eBay API documentation at ht\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: This query parameter specifies the seller-defined name of the return policy you want to retrieve.<br><br>\n            This value can be retrieved for a return policy by usi\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-tax-countrycode-jurisdictionid\n      path: /sales_tax/{countryCode}/{jurisdictionId}\n      operations:\n      - name: getsalestax\n        method: GET\n        description: This call retrieves the current sales-tax table entry for a specific tax jurisdiction. Specify the jurisdiction\n          to retrieve using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters. All four response fields will\n\
  \          be returned if\n        inputParameters:\n        - name: countryCode\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html\n            \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a\n        - name: jurisdictionId\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the sales tax jurisdiction for the tax table entry to be retrieved.<br><br>Valid\n            jurisdiction IDs can be retrieved using\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createorreplacesalestax\n        method: PUT\n        description: 'This method creates or updates a sales-tax table entry for a jurisdiction. Specify the tax table entry\n          you want to configure\
  \ using the two path parameters: <b>countryCode</b> and <b>jurisdictionId</b>. <br><br>A tax\n          table entry for a jurisd'\n        inputParameters:\n        - name: countryCode\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html\n            \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a\n        - name: jurisdictionId\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the ID of the tax jurisdiction for the table entry to be created.<br><br>Valid\n            jurisdiction IDs can be retrieved using the <a href\n        - name: Content-Type\n          in: header\n          type: string\n          required: true\n          description: This header indicates the format of the request body provided by the client. Its value should be set\n            to\
  \ <b>application/json</b>.<br><br>For more information, re\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesalestax\n        method: DELETE\n        description: This call deletes a sales-tax table entry for a jurisdiction. Specify the jurisdiction to delete using\n          the <b>countryCode</b> and <b>jurisdictionId</b> path parameters.<br><br><span class=\"tablenote\"><b>Note:</b> Sales-tax\n          tables are only a\n        inputParameters:\n        - name: countryCode\n          in: path\n          type: string\n          required: true\n          description: This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html\n            \" title=\"https://www.iso.org \" target=\"_blank\">ISO 3166</a\n        - name: jurisdictionId\n          in: path\n          type: string\n          required: true\n          description: This path parameter\
  \ specifies the ID of the sales tax jurisdiction whose table entry you want to delete.<br><br>Valid\n            jurisdiction IDs can be retrieved using th\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: sales-tax\n      path: /sales_tax\n      operations:\n      - name: getsalestaxes\n        method: GET\n        description: Use this call to retrieve all sales tax table entries that the seller has defined for a specific country.\n          All four response fields will be returned for each tax jurisdiction that matches the search criteria. <br><br><span\n          class=\"tablenote\">\n        inputParameters:\n        - name: country_code\n          in: query\n          type: string\n          required: true\n          description: This path parameter specifies the two-letter <a href=\"https://www.iso.org/iso-3166-country-codes.html\n            \" title=\"https://www.iso.org \" target=\"_blank\"\
  >ISO 3166</a\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: subscription\n      path: /subscription\n      operations:\n      - name: getsubscription\n        method: GET\n        description: This method retrieves a list of subscriptions associated with the seller account.\n        inputParameters:\n        - name: limit\n          in: query\n          type: string\n          description: This field is for future use.\n        - name: continuation_token\n          in: query\n          type: string\n          description: This field is for future use.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: kyc\n      path: /kyc\n      operations:\n      - name: getkyc\n        method: GET\n        description: <span class=\"tablenote\"><b>Note:</b>This method was originally created to see which onboarding requirements\n\
  \          were still pending for sellers being onboarded for eBay managed payments, but now that all seller accounts are onboarded\n          globally, t\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: advertising-eligibility\n      path: /advertising_eligibility\n      operations:\n      - name: getadvertisingeligibility\n        method: GET\n        description: This method allows developers to check the seller eligibility status for eBay advertising programs.\n        inputParameters:\n        - name: program_types\n          in: query\n          type: string\n          description: A comma-separated list of eBay advertising programs for which eligibility status will be returned.<br><br>\n            See the <a href=\"/api-docs/sell/account/types/plser:A\n        - name: X-EBAY-C-MARKETPLACE-ID\n          in: header\n          type: string\n          required: true\n          description: The\
  \ unique identifier of the eBay marketplace for which the seller eligibility status shall be checked.\n            This header is required or the call will fail.<br><br>Se\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: ebay-rest\n    description: REST adapter for eBay Account API.\n    resources:\n    - path: /custom_policy/\n      name: getcustompolicies\n      operations:\n      - method: GET\n  \n\n# --- truncated at 32 KB (78 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/ebay/refs/heads/main/capabilities/ebay-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/ebay/refs/heads/main/capabilities/ebay-capability.yaml
tags:
- Ebay
- API
tools:
- description: This method retrieves the list of custom policies specified by the <b>policy_types</b> query parameter.<br><br><span class="tablenote"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MAR
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustompolicies
- description: 'This method creates a new custom policy in which a seller specifies their terms for complying with local governmental regulations. <br/><br/>Two Custom Policy types are supported: <ul><li>Product Compliance (PRODUCT_COMPLIANCE)</li> <li>Tak'
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcustompolicy
- description: This method retrieves the custom policy specified by the <b>custom_policy_id</b> path parameter.<br><br><span class="tablenote"><b>Note:</b> Custom policies are no longer coupled with a specific eBay marketplace, so the <b>EBAY-C-MARKETPLAC
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcustompolicy
- description: This method updates an existing custom policy specified by the <b>custom_policy_id</b> path parameter. This method overwrites the policy's <b>Name</b>, <b>Label</b>, and <b>Description</b> fields. Therefore, the complete, current text of al
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecustompolicy
- description: This method creates a new fulfillment policy where the policy encapsulates seller's terms for fulfilling item purchases. Fulfillment policies include the shipment options that the seller offers to buyers. <br><br>Each policy targets a speci
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfulfillmentpolicy
- description: This method retrieves the complete details of a fulfillment policy. Supply the ID of the policy you want to retrieve using the <b>fulfillmentPolicyId</b> path parameter.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfulfillmentpolicy
- description: This method updates an existing fulfillment policy. Specify the policy you want to update using the <b>fulfillment_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the ex
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatefulfillmentpolicy
- description: This method deletes a fulfillment policy. Supply the ID of the policy you want to delete in the <b>fulfillmentPolicyId</b> path parameter.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletefulfillmentpolicy
- description: This method retrieves all the fulfillment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfulfillmentpolicies
- description: This method retrieves the details for a specific fulfillment policy. In the request, supply both the policy <code>name</code> and its associated <code>marketplace_id</code> as query parameters. <br><br><b>Marketplaces and locales</b> <br><b
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfulfillmentpolicybyname
- description: This method retrieves all the payment policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentpolicies
- description: This method creates a new payment policy where the policy encapsulates seller's terms for order payments. <br><br>Each policy targets a specific eBay marketplace and category group, and you can create multiple policies for each combination.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createpaymentpolicy
- description: This method retrieves the complete details of a payment policy. Supply the ID of the policy you want to retrieve using the <b>paymentPolicyId</b> path parameter.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentpolicy
- description: This method updates an existing payment policy. Specify the policy you want to update using the <b>payment_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing p
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepaymentpolicy
- description: This method deletes a payment policy. Supply the ID of the policy you want to delete in the <b>paymentPolicyId</b> path parameter.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletepaymentpolicy
- description: This method retrieves the details of a specific payment policy. Supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b> <br><br>Get the
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentpolicybyname
- description: <span class="tablenote"><b>Note:</b> This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow.</span><br>This method returns whether or not the user is opted-in to the
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentsprogram
- description: <span class="tablenote"><b>Note:</b> This method is no longer applicable, as all seller accounts globally have been enabled for the new eBay payment and checkout flow.</span><br>This method retrieves a seller's onboarding status for a payme
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getpaymentsprogramonboarding
- description: This method retrieves the seller's current set of privileges, including whether or not the seller's eBay registration has been completed, as well as the details of their site-wide <b>sellingLimt</b> (the amount and quantity they can sell on
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprivileges
- description: This method gets a list of the seller programs that the seller has opted-in to.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getoptedinprograms
- description: This method opts the seller in to an eBay seller program. Refer to the <a href="/api-docs/sell/account/overview.html#opt-in" target="_blank">Account API overview</a> for information about available eBay seller programs.<br><br><span class="
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: optintoprogram
- description: This method opts the seller out of a seller program to which you have previously opted-in to. Get a list of the seller programs you have opted-in to using the <b>getOptedInPrograms</b> call.
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: optoutofprogram
- description: This method retrieves a seller's <i>shipping rate tables</i> for the country specified in the <b>country_code</b> query parameter. If you call this method without specifying a country code, the call returns all of the seller's shipping rate
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getratetables
- description: This method retrieves all the return policies configured for the marketplace you specify using the <code>marketplace_id</code> query parameter. <br><br><b>Marketplaces and locales</b> <br><br>Get the correct policies for a marketplace that
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreturnpolicies
- description: This method creates a new return policy where the policy encapsulates seller's terms for returning items. <br><br>Each policy targets a specific marketplace, and you can create multiple policies for each marketplace. Return policies are not
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createreturnpolicy
- description: This method retrieves the complete details of the return policy specified by the <b>returnPolicyId</b> path parameter.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreturnpolicy
- description: This method updates an existing return policy. Specify the policy you want to update using the <b>return_policy_id</b> path parameter. Supply a complete policy payload with the updates you want to make; this call overwrites the existing pol
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatereturnpolicy
- description: This method deletes a return policy. Supply the ID of the policy you want to delete in the <b>returnPolicyId</b> path parameter.
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletereturnpolicy
- description: This method retrieves the details of a specific return policy. Supply both the policy <code>name</code> and its associated <code>marketplace_id</code> in the request query parameters. <br><br><b>Marketplaces and locales</b> <br><br>Get the
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreturnpolicybyname
- description: This call retrieves the current sales-tax table entry for a specific tax jurisdiction. Specify the jurisdiction to retrieve using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters. All four response fields will be returned if
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsalestax
- description: 'This method creates or updates a sales-tax table entry for a jurisdiction. Specify the tax table entry you want to configure using the two path parameters: <b>countryCode</b> and <b>jurisdictionId</b>. <br><br>A tax table entry for a jurisd'
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: createorreplacesalestax
- description: This call deletes a sales-tax table entry for a jurisdiction. Specify the jurisdiction to delete using the <b>countryCode</b> and <b>jurisdictionId</b> path parameters.<br><br><span class="tablenote"><b>Note:</b> Sales-tax tables are only a
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesalestax
- description: Use this call to retrieve all sales tax table entries that the seller has defined for a specific country. All four response fields will be returned for each tax jurisdiction that matches the search criteria. <br><br><span class="tablenote">
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsalestaxes
- description: This method retrieves a list of subscriptions associated with the seller account.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscription
- description: <span class="tablenote"><b>Note:</b>This method was originally created to see which onboarding requirements were still pending for sellers being onboarded for eBay managed payments, but now that all seller accounts are onboarded globally, t
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getkyc
- description: This method allows developers to check the seller eligibility status for eBay advertising programs.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadvertisingeligibility
---
