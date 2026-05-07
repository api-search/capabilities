---
categories: []
consumed_apis: []
description: 'This file describes the Yodlee Aggregation product APIs using the swagger notation that you can use to build your financial application. You can generate the client SDK in Python, JavaScript, PHP, or any other languages according to your development needs. For more details about the APIs, refer to <a href="https://developer.envestnet.com/resources/yodlee/yodlee-api-overview/docs">Yodlee API v1.1 - Overview</a>.<br><br>You will have to set the header before making the API call. The following headers apply to all the APIs:<ul><li>Authorization: This header holds the access token</li> <li> Api-Ve'
layout: capability
name: Envestnet Aggregation APIs
operations:
- description: Envestnet Get Consents Preferences
  method: GET
  name: getconsentpreferences
  path: /consents/preferences
- description: Envestnet Get Transactions
  method: GET
  name: gettransactions
  path: /transactions
- description: Envestnet Delete API Key
  method: DELETE
  name: deleteapikey
  path: /auth/apiKey/{key}
- description: Envestnet Get Provider Accounts
  method: GET
  name: getallprovideraccounts
  path: /providerAccounts
- description: Envestnet Update Account
  method: PUT
  name: editcredentialsorrefreshprovideraccount
  path: /providerAccounts
- description: Envestnet Get Transactions Count
  method: GET
  name: gettransactionscount
  path: /transactions/count
- description: Envestnet Get Transaction Summary
  method: GET
  name: gettransactionsummary
  path: /derived/transactionSummary
- description: Envestnet Renew Consent
  method: PUT
  name: renewconsent
  path: /consents/{consentId}/renewal
- description: Envestnet Get userData
  method: GET
  name: getdataextractsuserdata
  path: /dataExtracts/userData
- description: Envestnet Get Providers
  method: GET
  name: getallproviders
  path: /providers
- description: Envestnet Refresh Provider Account
  method: PUT
  name: refreshprovideraccount
  path: /providerAccounts/refresh
- description: Envestnet Get Provider Details
  method: GET
  name: getprovider
  path: /providers/{providerId}
- description: Envestnet Get Transaction Categorization Rules
  method: GET
  name: gettransactioncategorizationrules
  path: /transactions/categories/txnRules
- description: Envestnet Delete Category
  method: DELETE
  name: deletetransactioncategory
  path: /transactions/categories/{categoryId}
- description: Envestnet Get Documents
  method: GET
  name: getdocuments
  path: /documents
- description: Envestnet Evaluate Address
  method: POST
  name: evaluateaddress
  path: /accounts/evaluateAddress
- description: Envestnet Get Account Details
  method: GET
  name: getaccount
  path: /accounts/{accountId}
- description: Envestnet Update Account
  method: PUT
  name: updateaccount
  path: /accounts/{accountId}
- description: Envestnet Delete Account
  method: DELETE
  name: deleteaccount
  path: /accounts/{accountId}
- description: Envestnet Get Subscribed Notification Events
  method: GET
  name: getsubscribednotificationevents
  path: /configs/notifications/events
- description: Envestnet Get Consent History Count
  method: GET
  name: getconsenthistorycount
  path: /consents/history/count
- description: Envestnet Get Providers Count
  method: GET
  name: getproviderscount
  path: /providers/count
- description: Envestnet Get Historical Balances
  method: GET
  name: gethistoricalbalances
  path: /accounts/historicalBalances
- description: Envestnet Get Consent History
  method: GET
  name: getconsenthistory
  path: /consents/history
- description: Envestnet Get Networth Summary
  method: GET
  name: getnetworth
  path: /derived/networth
- description: Envestnet Saml Login
  method: POST
  name: samllogin
  path: /user/samlLogin
- description: Envestnet Register User
  method: POST
  name: registeruser
  path: /user/register
- description: Envestnet Get Security Details
  method: GET
  name: getsecurities
  path: /holdings/securities
- description: Envestnet Update Notification Subscription
  method: PUT
  name: updatesubscribednotificationevent
  path: /configs/notifications/events/{eventName}
- description: Envestnet Subscribe For Notification Event
  method: POST
  name: createsubscriptionnotificationevent
  path: /configs/notifications/events/{eventName}
- description: Envestnet Delete Notification Subscription
  method: DELETE
  name: deletesubscribednotificationevent
  path: /configs/notifications/events/{eventName}
- description: Envestnet Get Holdings
  method: GET
  name: getholdings
  path: /holdings
- description: Envestnet Add Holding
  method: POST
  name: addholding
  path: /holdings
- description: Envestnet Get API Keys
  method: GET
  name: getapikeys
  path: /auth/apiKey
- description: Envestnet Generate API Key
  method: POST
  name: generateapikey
  path: /auth/apiKey
- description: Envestnet Update Transaction Categorization Rule
  method: PUT
  name: updatetransactioncategorizationrule
  path: /transactions/categories/rules/{ruleId}
- description: Envestnet Run Transaction Categorization Rule
  method: POST
  name: runtransactioncategorizationrule
  path: /transactions/categories/rules/{ruleId}
- description: Envestnet Delete Transaction Categorization Rule
  method: DELETE
  name: deletetransactioncategorizationrule
  path: /transactions/categories/rules/{ruleId}
- description: Envestnet Download a Document
  method: GET
  name: downloaddocument
  path: /documents/{documentId}
- description: Envestnet Delete Document
  method: DELETE
  name: deletedocument
  path: /documents/{documentId}
- description: Envestnet Get Access Tokens
  method: GET
  name: getaccesstokens
  path: /user/accessTokens
- description: Envestnet Get Authorization Details
  method: GET
  name: getconsentdetails
  path: /consents/{consentId}
- description: Envestnet Put Consent
  method: PUT
  name: updateconsent
  path: /consents/{consentId}
- description: Envestnet Update Preferences
  method: PUT
  name: updatepreferences
  path: /providerAccounts/{providerAccountId}/preferences
- description: Envestnet Generate Access Token
  method: POST
  name: generateaccesstoken
  path: /auth/token
- description: Envestnet Delete Token
  method: DELETE
  name: deletetoken
  path: /auth/token
- description: Envestnet Get User Details
  method: GET
  name: getuser
  path: /user
- description: Envestnet Update User Details
  method: PUT
  name: updateuser
  path: /user
- description: Envestnet Get Provider Account Details
  method: GET
  name: getprovideraccount
  path: /providerAccounts/{providerAccountId}
- description: Envestnet Delete Provider Account
  method: DELETE
  name: deleteprovideraccount
  path: /providerAccounts/{providerAccountId}
- description: Envestnet Get Transaction Category List
  method: GET
  name: gettransactioncategories
  path: /transactions/categories
- description: Envestnet Update Category
  method: PUT
  name: updatetransactioncategory
  path: /transactions/categories
- description: Envestnet Create Category
  method: POST
  name: createtransactioncategory
  path: /transactions/categories
- description: Envestnet Get Transaction Categorization Rules
  method: GET
  name: gettransactioncategorizationrulesdeprecated
  path: /transactions/categories/rules
- description: Envestnet Create or Run Transaction Categorization Rule
  method: POST
  name: createorruntransactioncategorizationrules
  path: /transactions/categories/rules
- description: Envestnet Get Consents
  method: GET
  name: getconsents
  path: /consents
- description: Envestnet Post Consent
  method: POST
  name: createconsent
  path: /consents
- description: Envestnet Get Statements
  method: GET
  name: getstatements
  path: /statements
- description: Envestnet Get Accounts
  method: GET
  name: getallaccounts
  path: /accounts
- description: Envestnet Add Manual Account
  method: POST
  name: createmanualaccount
  path: /accounts
personas: []
provider_name: Envestnet
provider_slug: envestnet
search_terms:
- deletetransactioncategorizationrule
- envestnet get transaction summary
- getaccount
- getholdings
- envestnet get documents
- updateaccount
- createtransactioncategory
- api
- envestnet delete category
- gethistoricalbalances
- samllogin
- envestnet add holding
- downloaddocument
- envestnet create or run transaction categorization rule
- deletesubscribednotificationevent
- envestnet get security details
- account aggregation
- envestnet saml login
- createorruntransactioncategorizationrules
- envestnet get transactions
- gettransactions
- envestnet post consent
- envestnet get providers
- deletetoken
- updatetransactioncategorizationrule
- createsubscriptionnotificationevent
- envestnet
- gettransactioncategorizationrules
- envestnet get historical balances
- getsecurities
- getallaccounts
- envestnet delete api key
- deletetransactioncategory
- gettransactionsummary
- envestnet get consents preferences
- getstatements
- envestnet get accounts
- getsubscribednotificationevents
- envestnet get transactions count
- envestnet add manual account
- envestnet register user
- updatetransactioncategory
- deleteprovideraccount
- generateaccesstoken
- getconsenthistory
- getproviderscount
- envestnet delete token
- envestnet get api keys
- envestnet get account details
- envestnet get subscribed notification events
- envestnet delete transaction categorization rule
- gettransactioncategories
- createconsent
- envestnet put consent
- getdocuments
- registeruser
- envestnet get user details
- getaccesstokens
- wealth management
- renewconsent
- envestnet get provider details
- envestnet get userdata
- generateapikey
- updatepreferences
- envestnet get networth summary
- envestnet get consent history count
- updateconsent
- envestnet generate access token
- evaluateaddress
- deleteapikey
- envestnet update preferences
- refreshprovideraccount
- envestnet get statements
- envestnet get provider accounts
- envestnet update account
- envestnet get transaction categorization rules
- getprovider
- getdataextractsuserdata
- envestnet get consents
- envestnet subscribe for notification event
- envestnet delete document
- envestnet update category
- updateuser
- updatesubscribednotificationevent
- open banking
- envestnet download a document
- envestnet get providers count
- deletedocument
- getprovideraccount
- createmanualaccount
- envestnet evaluate address
- envestnet get access tokens
- gettransactioncategorizationrulesdeprecated
- getconsents
- envestnet get authorization details
- envestnet renew consent
- envestnet delete provider account
- envestnet run transaction categorization rule
- getallprovideraccounts
- getconsentdetails
- envestnet delete account
- getuser
- getnetworth
- envestnet get consent history
- envestnet delete notification subscription
- getallproviders
- envestnet get provider account details
- envestnet refresh provider account
- editcredentialsorrefreshprovideraccount
- runtransactioncategorizationrule
- envestnet get transaction category list
- envestnet update notification subscription
- envestnet update user details
- deleteaccount
- envestnet update transaction categorization rule
- financial
- envestnet generate api key
- addholding
- getapikeys
- envestnet create category
- gettransactionscount
- getconsenthistorycount
- getconsentpreferences
- envestnet get holdings
slug: envestnet-capability
source_filename: envestnet-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Envestnet Aggregation APIs\n  description: 'This file describes the Yodlee Aggregation product APIs using the swagger notation that you can use to build\n    your financial application. You can generate the client SDK in Python, JavaScript, PHP, or any other languages according\n    to your development needs. For more details about the APIs, refer to <a href=\"https://developer.envestnet.com/resources/yodlee/yodlee-api-overview/docs\">Yodlee\n    API v1.1 - Overview</a>.<br><br>You will have to set the header before making the API call. The following headers apply\n    to all the APIs:<ul><li>Authorization: This header holds the access token</li> <li> Api-Ve'\n  tags:\n  - Envestnet\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: envestnet\n    baseUri: ''\n    description: Envestnet Aggregation APIs HTTP API.\n    resources:\n    - name: consents-preferences\n     \
  \ path: /consents/preferences\n      operations:\n      - name: getconsentpreferences\n        method: GET\n        description: Envestnet Get Consents Preferences\n        inputParameters:\n        - name: consentId\n          in: query\n          type: string\n          required: true\n          description: consentId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions\n      path: /transactions\n      operations:\n      - name: gettransactions\n        method: GET\n        description: Envestnet Get Transactions\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          description: Comma separated accountIds\n        - name: baseType\n          in: query\n          type: string\n          description: DEBIT/CREDIT\n        - name: categoryId\n          in: query\n          type: string\n          description: Comma separated categoryIds\n\
  \        - name: categoryType\n          in: query\n          type: string\n          description: Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION)\n        - name: container\n          in: query\n          type: string\n          description: bank/creditCard/investment/insurance/loan\n        - name: convertToCurrency\n          in: query\n          type: string\n          description: On-demand currency conversion parameter\n        - name: detailCategoryId\n          in: query\n          type: string\n          description: Comma separated detailCategoryIds\n        - name: fromDate\n          in: query\n          type: string\n          description: Transaction from date(YYYY-MM-DD)\n        - name: highLevelCategoryId\n          in: query\n          type: string\n          description: Comma separated highLevelCategoryIds\n        - name: keyword\n          in: query\n          type: string\n          description: Transaction search\
  \ text\n        - name: skip\n          in: query\n          type: integer\n          description: skip (Min 0)\n        - name: toDate\n          in: query\n          type: string\n          description: Transaction end date (YYYY-MM-DD)\n        - name: top\n          in: query\n          type: integer\n          description: top (Max 500)\n        - name: type\n          in: query\n          type: string\n          description: Transaction Type(SELL,SWEEP, etc.) for bank/creditCard/investment\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-apikey-key\n      path: /auth/apiKey/{key}\n      operations:\n      - name: deleteapikey\n        method: DELETE\n        description: Envestnet Delete API Key\n        inputParameters:\n        - name: key\n          in: path\n          type: string\n          required: true\n          description: key\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: provideraccounts\n      path: /providerAccounts\n      operations:\n      - name: getallprovideraccounts\n        method: GET\n        description: Envestnet Get Provider Accounts\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          description: include\n        - name: providerIds\n          in: query\n          type: string\n          description: Comma separated providerIds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: editcredentialsorrefreshprovideraccount\n        method: PUT\n        description: Envestnet Update Account\n        inputParameters:\n        - name: providerAccountIds\n          in: query\n          type: string\n          required: true\n          description: comma separated providerAccountIds\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: transactions-count\n      path: /transactions/count\n      operations:\n      - name: gettransactionscount\n        method: GET\n        description: Envestnet Get Transactions Count\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          description: Comma separated accountIds\n        - name: baseType\n          in: query\n          type: string\n          description: DEBIT/CREDIT\n        - name: categoryId\n          in: query\n          type: string\n          description: Comma separated categoryIds\n        - name: categoryType\n          in: query\n          type: string\n          description: Transaction Category Type(LOAN, UNCATEGORIZE, INCOME, TRANSFER, EXPENSE or DEFERRED_COMPENSATION)\n        - name: container\n          in: query\n          type: string\n          description: bank/creditCard/investment/insurance/loan\n        - name: detailCategoryId\n\
  \          in: query\n          type: string\n          description: Comma separated detailCategoryIds\n        - name: fromDate\n          in: query\n          type: string\n          description: Transaction from date(YYYY-MM-DD)\n        - name: highLevelCategoryId\n          in: query\n          type: string\n          description: Comma separated highLevelCategoryIds\n        - name: keyword\n          in: query\n          type: string\n          description: Transaction search text\n        - name: toDate\n          in: query\n          type: string\n          description: Transaction end date (YYYY-MM-DD)\n        - name: type\n          in: query\n          type: string\n          description: Transaction Type(SELL,SWEEP, etc.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: derived-transactionsummary\n      path: /derived/transactionSummary\n      operations:\n      - name: gettransactionsummary\n\
  \        method: GET\n        description: Envestnet Get Transaction Summary\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          description: comma separated account Ids\n        - name: categoryId\n          in: query\n          type: string\n          description: comma separated categoryIds\n        - name: categoryType\n          in: query\n          type: string\n          description: LOAN, INCOME, EXPENSE, TRANSFER, UNCATEGORIZE or DEFERRED_COMPENSATION\n        - name: fromDate\n          in: query\n          type: string\n          description: YYYY-MM-DD format\n        - name: groupBy\n          in: query\n          type: string\n          required: true\n          description: CATEGORY_TYPE, HIGH_LEVEL_CATEGORY or CATEGORY\n        - name: include\n          in: query\n          type: string\n          description: details\n        - name: includeUserCategory\n          in: query\n          type: boolean\n          description:\
  \ TRUE/FALSE\n        - name: interval\n          in: query\n          type: string\n          description: D-daily, W-weekly, M-mothly or Y-yearly\n        - name: toDate\n          in: query\n          type: string\n          description: YYYY-MM-DD format\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consents-consentid-renewal\n      path: /consents/{consentId}/renewal\n      operations:\n      - name: renewconsent\n        method: PUT\n        description: Envestnet Renew Consent\n        inputParameters:\n        - name: consentId\n          in: path\n          type: integer\n          required: true\n          description: Consent Id to be renewed.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: dataextracts-userdata\n      path: /dataExtracts/userData\n      operations:\n      - name: getdataextractsuserdata\n\
  \        method: GET\n        description: Envestnet Get userData\n        inputParameters:\n        - name: fromDate\n          in: query\n          type: string\n          required: true\n          description: From DateTime (YYYY-MM-DDThh:mm:ssZ)\n        - name: loginName\n          in: query\n          type: string\n          required: true\n          description: Login Name\n        - name: toDate\n          in: query\n          type: string\n          required: true\n          description: To DateTime (YYYY-MM-DDThh:mm:ssZ)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers\n      path: /providers\n      operations:\n      - name: getallproviders\n        method: GET\n        description: Envestnet Get Providers\n        inputParameters:\n        - name: capability\n          in: query\n          type: string\n          description: CHALLENGE_DEPOSIT_VERIFICATION - capability search\
  \ is deprecated\n        - name: dataset$filter\n          in: query\n          type: string\n          description: 'Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be\n            the dataset or dataset attributes configured as default for '\n        - name: fullAccountNumberFields\n          in: query\n          type: string\n          description: Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber.\n        - name: institutionId\n          in: query\n          type: integer\n          description: Institution Id for Single site selection\n        - name: name\n          in: query\n          type: string\n          description: Name in minimum 1 character or routing number.\n        - name: priority\n          in: query\n          type: string\n          description: Search priority\n        - name: providerId\n          in: query\n          type: string\n          description: Max 5 Comma seperated\
  \ Provider Ids\n        - name: skip\n          in: query\n          type: integer\n          description: skip (Min 0) - This is not applicable along with 'name' parameter.\n        - name: top\n          in: query\n          type: integer\n          description: top (Max 500) - This is not applicable along with 'name' parameter.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provideraccounts-refresh\n      path: /providerAccounts/refresh\n      operations:\n      - name: refreshprovideraccount\n        method: PUT\n        description: Envestnet Refresh Provider Account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers-providerid\n      path: /providers/{providerId}\n      operations:\n      - name: getprovider\n        method: GET\n        description: Envestnet Get Provider Details\n        inputParameters:\n\
  \        - name: providerId\n          in: path\n          type: integer\n          required: true\n          description: providerId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-categories-txnrules\n      path: /transactions/categories/txnRules\n      operations:\n      - name: gettransactioncategorizationrules\n        method: GET\n        description: Envestnet Get Transaction Categorization Rules\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-categories-categoryid\n      path: /transactions/categories/{categoryId}\n      operations:\n      - name: deletetransactioncategory\n        method: DELETE\n        description: Envestnet Delete Category\n        inputParameters:\n        - name: categoryId\n          in: path\n          type: integer\n          required: true\n   \
  \       description: categoryId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents\n      path: /documents\n      operations:\n      - name: getdocuments\n        method: GET\n        description: Envestnet Get Documents\n        inputParameters:\n        - name: Keyword\n          in: query\n          type: string\n          description: The string used to search a document by its name.\n        - name: accountId\n          in: query\n          type: string\n          description: The unique identifier of an account. Retrieve documents for a given accountId.\n        - name: docType\n          in: query\n          type: string\n          description: 'Accepts only one of the following valid document types: STMT, TAX, and EBILL.'\n        - name: fromDate\n          in: query\n          type: string\n          description: The date from which documents have to be retrieved.\n        - name:\
  \ toDate\n          in: query\n          type: string\n          description: The date to which documents have to be retrieved.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-evaluateaddress\n      path: /accounts/evaluateAddress\n      operations:\n      - name: evaluateaddress\n        method: POST\n        description: Envestnet Evaluate Address\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-accountid\n      path: /accounts/{accountId}\n      operations:\n      - name: getaccount\n        method: GET\n        description: Envestnet Get Account Details\n        inputParameters:\n        - name: accountId\n          in: path\n          type: integer\n          required: true\n          description: accountId\n        - name: convertToCurrency\n          in: query\n          type: string\n\
  \          description: On-demand currency conversion parameter\n        - name: include\n          in: query\n          type: string\n          description: profile, holder, fullAccountNumber, fullAccountNumberList, paymentProfile, autoRefresh<br><b>Note:</b>fullAccountNumber\n            is deprecated and is replaced with fullA\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateaccount\n        method: PUT\n        description: Envestnet Update Account\n        inputParameters:\n        - name: accountId\n          in: path\n          type: integer\n          required: true\n          description: accountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteaccount\n        method: DELETE\n        description: Envestnet Delete Account\n        inputParameters:\n        - name: accountId\n    \
  \      in: path\n          type: integer\n          required: true\n          description: accountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configs-notifications-events\n      path: /configs/notifications/events\n      operations:\n      - name: getsubscribednotificationevents\n        method: GET\n        description: Envestnet Get Subscribed Notification Events\n        inputParameters:\n        - name: eventName\n          in: query\n          type: string\n          description: Name of the webhook subscription event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consents-history-count\n      path: /consents/history/count\n      operations:\n      - name: getconsenthistorycount\n        method: GET\n        description: Envestnet Get Consent History Count\n        inputParameters:\n        -\
  \ name: consentId\n          in: query\n          type: string\n          required: true\n          description: Consent Id generated through POST Consent.\n        - name: fromDate\n          in: query\n          type: string\n          description: Consent History from date(YYYY-MM-DD)\n        - name: toDate\n          in: query\n          type: string\n          description: Consent History end date (YYYY-MM-DD)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: providers-count\n      path: /providers/count\n      operations:\n      - name: getproviderscount\n        method: GET\n        description: Envestnet Get Providers Count\n        inputParameters:\n        - name: capability\n          in: query\n          type: string\n          description: CHALLENGE_DEPOSIT_VERIFICATION - capability search is deprecated\n        - name: dataset$filter\n          in: query\n          type: string\n  \
  \        description: 'Expression to filter the providers by dataset(s) or dataset attribute(s). The default value will be\n            the dataset or dataset attributes configured as default for '\n        - name: fullAccountNumberFields\n          in: query\n          type: string\n          description: Specify to filter the providers with values paymentAccountNumber,unmaskedAccountNumber.\n        - name: name\n          in: query\n          type: string\n          description: Name in minimum 1 character or routing number.\n        - name: priority\n          in: query\n          type: string\n          description: Search priority\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-historicalbalances\n      path: /accounts/historicalBalances\n      operations:\n      - name: gethistoricalbalances\n        method: GET\n        description: Envestnet Get Historical Balances\n        inputParameters:\n\
  \        - name: accountId\n          in: query\n          type: string\n          description: accountId\n        - name: fromDate\n          in: query\n          type: string\n          description: from date for balance retrieval (YYYY-MM-DD)\n        - name: includeCF\n          in: query\n          type: boolean\n          description: Consider carry forward logic for missing balances\n        - name: interval\n          in: query\n          type: string\n          description: D-daily, W-weekly or M-monthly\n        - name: skip\n          in: query\n          type: integer\n          description: skip (Min 0)\n        - name: toDate\n          in: query\n          type: string\n          description: toDate for balance retrieval (YYYY-MM-DD)\n        - name: top\n          in: query\n          type: integer\n          description: top (Max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ consents-history\n      path: /consents/history\n      operations:\n      - name: getconsenthistory\n        method: GET\n        description: Envestnet Get Consent History\n        inputParameters:\n        - name: consentId\n          in: query\n          type: string\n          required: true\n          description: Consent Id generated through POST Consent.\n        - name: fromDate\n          in: query\n          type: string\n          description: Consent History from date(YYYY-MM-DD)\n        - name: skip\n          in: query\n          type: integer\n          description: skip (Min 0)\n        - name: toDate\n          in: query\n          type: string\n          description: Consent History end date (YYYY-MM-DD)\n        - name: top\n          in: query\n          type: integer\n          description: top (Max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: derived-networth\n \
  \     path: /derived/networth\n      operations:\n      - name: getnetworth\n        method: GET\n        description: Envestnet Get Networth Summary\n        inputParameters:\n        - name: accountIds\n          in: query\n          type: string\n          description: comma separated accountIds\n        - name: container\n          in: query\n          type: string\n          description: bank/creditCard/investment/insurance/loan/realEstate/otherAssets/otherLiabilities\n        - name: fromDate\n          in: query\n          type: string\n          description: from date for balance retrieval (YYYY-MM-DD)\n        - name: include\n          in: query\n          type: string\n          description: details\n        - name: interval\n          in: query\n          type: string\n          description: D-daily, W-weekly or M-monthly\n        - name: skip\n          in: query\n          type: integer\n          description: skip (Min 0)\n        - name: toDate\n          in: query\n  \
  \        type: string\n          description: toDate for balance retrieval (YYYY-MM-DD)\n        - name: top\n          in: query\n          type: integer\n          description: top (Max 500)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-samllogin\n      path: /user/samlLogin\n      operations:\n      - name: samllogin\n        method: POST\n        description: Envestnet Saml Login\n        inputParameters:\n        - name: issuer\n          in: query\n          type: string\n          required: true\n          description: issuer\n        - name: samlResponse\n          in: query\n          type: string\n          required: true\n          description: samlResponse\n        - name: source\n          in: query\n          type: string\n          description: source\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: user-register\n      path: /user/register\n      operations:\n      - name: registeruser\n        method: POST\n        description: Envestnet Register User\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: holdings-securities\n      path: /holdings/securities\n      operations:\n      - name: getsecurities\n        method: GET\n        description: Envestnet Get Security Details\n        inputParameters:\n        - name: holdingId\n          in: query\n          type: string\n          description: Comma separated holdingId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: configs-notifications-events-eventname\n      path: /configs/notifications/events/{eventName}\n      operations:\n      - name: updatesubscribednotificationevent\n        method: PUT\n        description: Envestnet Update\
  \ Notification Subscription\n        inputParameters:\n        - name: eventName\n          in: path\n          type: string\n          required: true\n          description: Name of the webhook subscription event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createsubscriptionnotificationevent\n        method: POST\n        description: Envestnet Subscribe For Notification Event\n        inputParameters:\n        - name: eventName\n          in: path\n          type: string\n          required: true\n          description: Name of the webhook subscription event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletesubscribednotificationevent\n        method: DELETE\n        description: Envestnet Delete Notification Subscription\n        inputParameters:\n        - name: eventName\n          in: path\n\
  \          type: string\n          required: true\n          description: Name of the webhook subscription event\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: holdings\n      path: /holdings\n      operations:\n      - name: getholdings\n        method: GET\n        description: Envestnet Get Holdings\n        inputParameters:\n        - name: accountId\n          in: query\n          type: string\n          description: Comma separated accountId\n        - name: assetClassification.classificationType\n          in: query\n          type: string\n          description: e.g. Country, Sector, etc.\n        - name: classificationValue\n          in: query\n          type: string\n          description: e.g. US\n        - name: include\n          in: query\n          type: string\n          description: assetClassification\n        - name: providerAccountId\n          in: query\n          type: string\n\
  \          description: providerAccountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: addholding\n        method: POST\n        description: Envestnet Add Holding\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-apikey\n      path: /auth/apiKey\n      operations:\n      - name: getapikeys\n        method: GET\n        description: Envestnet Get API Keys\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: generateapikey\n        method: POST\n        description: Envestnet Generate API Key\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-categories-rules-ruleid\n      path: /transactions/categories/rules/{ruleId}\n\
  \      operations:\n      - name: updatetransactioncategorizationrule\n        method: PUT\n        description: Envestnet Update Transaction Categorization Rule\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: integer\n          required: true\n          description: ruleId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: runtransactioncategorizationrule\n        method: POST\n        description: Envestnet Run Transaction Categorization Rule\n        inputParameters:\n        - name: action\n          in: query\n          type: string\n          required: true\n        - name: ruleId\n          in: path\n          type: integer\n          required: true\n          description: Unique id of the categorization rule\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetransactioncategorizationrule\n\
  \        method: DELETE\n        description: Envestnet Delete Transaction Categorization Rule\n        inputParameters:\n        - name: ruleId\n          in: path\n          type: integer\n          required: true\n          description: ruleId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: documents-documentid\n      path: /documents/{documentId}\n      operations:\n      - name: downloaddocument\n        method: GET\n        description: Envestnet Download a Document\n        inputParameters:\n        - name: documentId\n          in: path\n          type: string\n          required: true\n          description: documentId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedocument\n        method: DELETE\n        description: Envestnet Delete Document\n        inputParameters:\n        - name:\
  \ documentId\n          in: path\n          type: string\n          required: true\n          description: documentId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user-accesstokens\n      path: /user/accessTokens\n      operations:\n      - name: getaccesstokens\n        method: GET\n        description: Envestnet Get Access Tokens\n        inputParameters:\n        - name: appIds\n          in: query\n          type: string\n          required: true\n          description: appIds\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: consents-consentid\n      path: /consents/{consentId}\n      operations:\n      - name: getconsentdetails\n        method: GET\n        description: Envestnet Get Authorization Details\n        inputParameters:\n        - name: consentId\n          in: path\n          type: integer\n\
  \          required: true\n          description: Consent Id generated through POST Consent.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateconsent\n        method: PUT\n        description: Envestnet Put Consent\n        inputParameters:\n        - name: consentId\n          in: path\n          type: integer\n          required: true\n          description: Consent Id generated through POST Consent.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provideraccounts-provideraccountid-preferences\n      path: /providerAccounts/{providerAccountId}/preferences\n      operations:\n      - name: updatepreferences\n        method: PUT\n        description: Envestnet Update Preferences\n        inputParameters:\n        - name: providerAccountId\n          in: path\n          type: integer\n          required:\
  \ true\n          description: providerAccountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: auth-token\n      path: /auth/token\n      operations:\n      - name: generateaccesstoken\n        method: POST\n        description: Envestnet Generate Access Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletetoken\n        method: DELETE\n        description: Envestnet Delete Token\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: user\n      path: /user\n      operations:\n      - name: getuser\n        method: GET\n        description: Envestnet Get User Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateuser\n\
  \        method: PUT\n        description: Envestnet Update User Details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: provideraccounts-provideraccountid\n      path: /providerAccounts/{providerAccountId}\n      operations:\n      - name: getprovideraccount\n        method: GET\n        description: Envestnet Get Provider Account Details\n        inputParameters:\n        - name: include\n          in: query\n          type: string\n          description: include credentials,questions\n        - name: providerAccountId\n          in: path\n          type: integer\n          required: true\n          description: providerAccountId\n        - name: requestId\n          in: query\n          type: string\n          description: The unique identifier for the request that returns contextual data\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: deleteprovideraccount\n        method: DELETE\n        description: Envestnet Delete Provider Account\n        inputParameters:\n        - name: providerAccountId\n          in: path\n          type: integer\n          required: true\n          description: providerAccountId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: transactions-categories\n      path: /transactions/categories\n      operations:\n      - name: gettransactioncategories\n        method: GET\n        description: Envestnet Get Transaction Category List\n        outputRawFormat: json\n        outputPar\n\n# --- truncated at 32 KB (93 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/envestnet/refs/heads/main/capabilities/envestnet-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/envestnet/refs/heads/main/capabilities/envestnet-capability.yaml
tags:
- Envestnet
- API
tools:
- description: Envestnet Get Consents Preferences
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsentpreferences
- description: Envestnet Get Transactions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactions
- description: Envestnet Delete API Key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteapikey
- description: Envestnet Get Provider Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallprovideraccounts
- description: Envestnet Update Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: editcredentialsorrefreshprovideraccount
- description: Envestnet Get Transactions Count
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactionscount
- description: Envestnet Get Transaction Summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactionsummary
- description: Envestnet Renew Consent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: renewconsent
- description: Envestnet Get userData
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdataextractsuserdata
- description: Envestnet Get Providers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallproviders
- description: Envestnet Refresh Provider Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: refreshprovideraccount
- description: Envestnet Get Provider Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprovider
- description: Envestnet Get Transaction Categorization Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactioncategorizationrules
- description: Envestnet Delete Category
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetransactioncategory
- description: Envestnet Get Documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdocuments
- description: Envestnet Evaluate Address
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: evaluateaddress
- description: Envestnet Get Account Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccount
- description: Envestnet Update Account
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateaccount
- description: Envestnet Delete Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteaccount
- description: Envestnet Get Subscribed Notification Events
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsubscribednotificationevents
- description: Envestnet Get Consent History Count
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsenthistorycount
- description: Envestnet Get Providers Count
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getproviderscount
- description: Envestnet Get Historical Balances
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gethistoricalbalances
- description: Envestnet Get Consent History
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsenthistory
- description: Envestnet Get Networth Summary
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnetworth
- description: Envestnet Saml Login
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: samllogin
- description: Envestnet Register User
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: registeruser
- description: Envestnet Get Security Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsecurities
- description: Envestnet Update Notification Subscription
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatesubscribednotificationevent
- description: Envestnet Subscribe For Notification Event
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createsubscriptionnotificationevent
- description: Envestnet Delete Notification Subscription
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletesubscribednotificationevent
- description: Envestnet Get Holdings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getholdings
- description: Envestnet Add Holding
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addholding
- description: Envestnet Get API Keys
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getapikeys
- description: Envestnet Generate API Key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateapikey
- description: Envestnet Update Transaction Categorization Rule
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetransactioncategorizationrule
- description: Envestnet Run Transaction Categorization Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: runtransactioncategorizationrule
- description: Envestnet Delete Transaction Categorization Rule
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetransactioncategorizationrule
- description: Envestnet Download a Document
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: downloaddocument
- description: Envestnet Delete Document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedocument
- description: Envestnet Get Access Tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getaccesstokens
- description: Envestnet Get Authorization Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsentdetails
- description: Envestnet Put Consent
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateconsent
- description: Envestnet Update Preferences
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatepreferences
- description: Envestnet Generate Access Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: generateaccesstoken
- description: Envestnet Delete Token
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletetoken
- description: Envestnet Get User Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getuser
- description: Envestnet Update User Details
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateuser
- description: Envestnet Get Provider Account Details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getprovideraccount
- description: Envestnet Delete Provider Account
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteprovideraccount
- description: Envestnet Get Transaction Category List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactioncategories
- description: Envestnet Update Category
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatetransactioncategory
- description: Envestnet Create Category
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtransactioncategory
- description: Envestnet Get Transaction Categorization Rules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettransactioncategorizationrulesdeprecated
- description: Envestnet Create or Run Transaction Categorization Rule
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createorruntransactioncategorizationrules
- description: Envestnet Get Consents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getconsents
- description: Envestnet Post Consent
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createconsent
- description: Envestnet Get Statements
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getstatements
- description: Envestnet Get Accounts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallaccounts
- description: Envestnet Add Manual Account
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createmanualaccount
---
