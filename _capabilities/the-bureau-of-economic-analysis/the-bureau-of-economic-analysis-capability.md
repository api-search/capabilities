---
categories: []
consumed_apis: []
description: The Bureau of Economic Analysis (BEA) Data API provides programmatic access to BEA published economic statistics using industry-standard methods and procedures. The API includes methods for retrieving a subset of statistical data and the metadata that describes it. Available datasets include National Income and Product Accounts (NIPA), Multinational Enterprises (MNE), Fixed Assets, International Transactions Accounts (ITA), International Investment Position (IIP), Input-Output tables, Regional data, GDP by Industry, and more.
layout: capability
name: Bureau of Economic Analysis API
operations:
- description: Get Dataset List
  method: GET
  name: getdatasetlist
  path: /
- description: Get Parameter List
  method: GET
  name: getparameterlist
  path: /parameters
- description: Get Parameter Values
  method: GET
  name: getparametervalues
  path: /parameter-values
- description: Get NIPA Data
  method: GET
  name: getnipadata
  path: /nipa-data
- description: Get Regional Data
  method: GET
  name: getregionaldata
  path: /regional-data
- description: Get GDP by Industry Data
  method: GET
  name: getgdpbyindustrydata
  path: /gdp-by-industry-data
- description: Get International Transactions Data
  method: GET
  name: getitadata
  path: /ita-data
- description: Get Fixed Assets Data
  method: GET
  name: getfixedassetsdata
  path: /fixed-assets-data
- description: Get Input-Output Data
  method: GET
  name: getinputoutputdata
  path: /input-output-data
- description: Get Multinational Enterprises Data
  method: GET
  name: getmnedata
  path: /mne-data
personas: []
provider_name: The Bureau of Economic Analysis
provider_slug: the-bureau-of-economic-analysis
search_terms:
- getparameterlist
- economics
- get regional data
- get fixed assets data
- national accounts
- bureau
- get international transactions data
- get dataset list
- getinputoutputdata
- getnipadata
- gdp
- economic
- getmnedata
- the
- get nipa data
- api
- of
- getparametervalues
- get multinational enterprises data
- getitadata
- getdatasetlist
- federal government
- getfixedassetsdata
- get gdp by industry data
- analysis
- get parameter list
- getregionaldata
- getgdpbyindustrydata
- get input-output data
- get parameter values
- statistics
- open data
slug: the-bureau-of-economic-analysis-capability
source_filename: the-bureau-of-economic-analysis-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Bureau of Economic Analysis API\n  description: The Bureau of Economic Analysis (BEA) Data API provides programmatic access to BEA published economic statistics\n    using industry-standard methods and procedures. The API includes methods for retrieving a subset of statistical data and\n    the metadata that describes it. Available datasets include National Income and Product Accounts (NIPA), Multinational\n    Enterprises (MNE), Fixed Assets, International Transactions Accounts (ITA), International Investment Position (IIP), Input-Output\n    tables, Regional data, GDP by Industry, and more.\n  tags:\n  - The\n  - Bureau\n  - Of\n  - Economic\n  - Analysis\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: the-bureau-of-economic-analysis\n    baseUri: https://apps.bea.gov/api/data\n    description: Bureau of Economic Analysis API HTTP API.\n    authentication:\n      type:\
  \ apikey\n      in: query\n      name: UserID\n      value: '{{THE_BUREAU_OF_ECONOMIC_ANALYSIS_TOKEN}}'\n    resources:\n    - name: resource\n      path: /\n      operations:\n      - name: getdatasetlist\n        method: GET\n        description: Get Dataset List\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n          description: Your registered BEA API key (36-character UUID).\n        - name: method\n          in: query\n          type: string\n          required: true\n          description: API method to invoke.\n        - name: ResultFormat\n          in: query\n          type: string\n          description: Format for the response data.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parameters\n      path: /parameters\n      operations:\n      - name: getparameterlist\n        method: GET\n        description:\
  \ Get Parameter List\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n          description: Your registered BEA API key.\n        - name: method\n          in: query\n          type: string\n          required: true\n          description: API method to invoke.\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n          description: Name of the dataset for which to retrieve parameters.\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: parameter-values\n      path: /parameter-values\n      operations:\n      - name: getparametervalues\n        method: GET\n        description: Get Parameter Values\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n         \
  \ required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n        - name: ParameterName\n          in: query\n          type: string\n          required: true\n          description: Name of the parameter for which to retrieve valid values.\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: nipa-data\n      path: /nipa-data\n      operations:\n      - name: getnipadata\n        method: GET\n        description: Get NIPA Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n     \
  \     in: query\n          type: string\n          required: true\n        - name: TableName\n          in: query\n          type: string\n          required: true\n          description: NIPA table name (e.g., T10101 for GDP).\n        - name: Frequency\n          in: query\n          type: string\n          required: true\n          description: Data frequency.\n        - name: Year\n          in: query\n          type: string\n          required: true\n          description: Year(s) for data retrieval. Use 'X' for all years.\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: regional-data\n      path: /regional-data\n      operations:\n      - name: getregionaldata\n        method: GET\n        description: Get Regional Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n \
  \         required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n        - name: TableName\n          in: query\n          type: string\n          required: true\n          description: Regional table code (e.g., SQGDP1 for Quarterly GDP by State).\n        - name: LineCode\n          in: query\n          type: integer\n          required: true\n          description: Line code within the regional table.\n        - name: GeoFips\n          in: query\n          type: string\n          required: true\n          description: Geographic FIPS code. Use 'STATE' for all states, '00000' for US total.\n        - name: Year\n          in: query\n          type: string\n          required: true\n          description: Year(s) for data retrieval. Use 'LAST5' for last 5 years.\n        - name: ResultFormat\n          in: query\n          type: string\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: gdp-by-industry-data\n      path: /gdp-by-industry-data\n      operations:\n      - name: getgdpbyindustrydata\n        method: GET\n        description: Get GDP by Industry Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n        - name: TableID\n          in: query\n          type: integer\n          required: true\n          description: Table identifier within GDPbyIndustry dataset.\n        - name: Frequency\n          in: query\n          type: string\n          required: true\n        - name: Year\n          in: query\n          type: string\n          required: true\n    \
  \    - name: Industry\n          in: query\n          type: string\n          required: true\n          description: Industry code. Use 'ALL' for all industries.\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: ita-data\n      path: /ita-data\n      operations:\n      - name: getitadata\n        method: GET\n        description: Get International Transactions Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n        - name: Indicator\n          in: query\n          type: string\n          required: true\n          description: ITA indicator code (e.g., BalGds\
  \ for Balance on Goods).\n        - name: AreaOrCountry\n          in: query\n          type: string\n          required: true\n          description: Country or area code. Use 'AllCountries' for all.\n        - name: Frequency\n          in: query\n          type: string\n          required: true\n        - name: Year\n          in: query\n          type: string\n          required: true\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: fixed-assets-data\n      path: /fixed-assets-data\n      operations:\n      - name: getfixedassetsdata\n        method: GET\n        description: Get Fixed Assets Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n       \
  \ - name: DatasetName\n          in: query\n          type: string\n          required: true\n        - name: TableName\n          in: query\n          type: string\n          required: true\n          description: Fixed assets table name (e.g., FAAt101 for Current-Cost Net Stock).\n        - name: Year\n          in: query\n          type: string\n          required: true\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: input-output-data\n      path: /input-output-data\n      operations:\n      - name: getinputoutputdata\n        method: GET\n        description: Get Input-Output Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n\
  \          in: query\n          type: string\n          required: true\n        - name: TableID\n          in: query\n          type: integer\n          required: true\n          description: Input-Output table identifier.\n        - name: Year\n          in: query\n          type: string\n          required: true\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: mne-data\n      path: /mne-data\n      operations:\n      - name: getmnedata\n        method: GET\n        description: Get Multinational Enterprises Data\n        inputParameters:\n        - name: UserID\n          in: query\n          type: string\n          required: true\n        - name: method\n          in: query\n          type: string\n          required: true\n        - name: DatasetName\n          in: query\n          type: string\n          required: true\n\
  \        - name: DirectionOfInvestment\n          in: query\n          type: string\n          required: true\n          description: Direction of investment - outward (US parent) or inward (foreign parent).\n        - name: ClassificationCode\n          in: query\n          type: string\n          required: true\n          description: Industry or country classification code.\n        - name: Year\n          in: query\n          type: string\n          required: true\n        - name: SeriesID\n          in: query\n          type: integer\n          required: true\n          description: MNE series identifier for the measure requested.\n        - name: ResultFormat\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: the-bureau-of-economic-analysis-rest\n    description: REST adapter for Bureau of Economic Analysis\
  \ API.\n    resources:\n    - path: /\n      name: getdatasetlist\n      operations:\n      - method: GET\n        name: getdatasetlist\n        description: Get Dataset List\n        call: the-bureau-of-economic-analysis.getdatasetlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /parameters\n      name: getparameterlist\n      operations:\n      - method: GET\n        name: getparameterlist\n        description: Get Parameter List\n        call: the-bureau-of-economic-analysis.getparameterlist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /parameter-values\n      name: getparametervalues\n      operations:\n      - method: GET\n        name: getparametervalues\n        description: Get Parameter Values\n        call: the-bureau-of-economic-analysis.getparametervalues\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /nipa-data\n      name: getnipadata\n      operations:\n\
  \      - method: GET\n        name: getnipadata\n        description: Get NIPA Data\n        call: the-bureau-of-economic-analysis.getnipadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /regional-data\n      name: getregionaldata\n      operations:\n      - method: GET\n        name: getregionaldata\n        description: Get Regional Data\n        call: the-bureau-of-economic-analysis.getregionaldata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /gdp-by-industry-data\n      name: getgdpbyindustrydata\n      operations:\n      - method: GET\n        name: getgdpbyindustrydata\n        description: Get GDP by Industry Data\n        call: the-bureau-of-economic-analysis.getgdpbyindustrydata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /ita-data\n      name: getitadata\n      operations:\n      - method: GET\n        name: getitadata\n        description: Get International\
  \ Transactions Data\n        call: the-bureau-of-economic-analysis.getitadata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /fixed-assets-data\n      name: getfixedassetsdata\n      operations:\n      - method: GET\n        name: getfixedassetsdata\n        description: Get Fixed Assets Data\n        call: the-bureau-of-economic-analysis.getfixedassetsdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /input-output-data\n      name: getinputoutputdata\n      operations:\n      - method: GET\n        name: getinputoutputdata\n        description: Get Input-Output Data\n        call: the-bureau-of-economic-analysis.getinputoutputdata\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /mne-data\n      name: getmnedata\n      operations:\n      - method: GET\n        name: getmnedata\n        description: Get Multinational Enterprises Data\n        call: the-bureau-of-economic-analysis.getmnedata\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: the-bureau-of-economic-analysis-mcp\n    transport: http\n    description: MCP adapter for Bureau of Economic Analysis API for AI agent use.\n    tools:\n    - name: getdatasetlist\n      description: Get Dataset List\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getdatasetlist\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: Your registered BEA API key (36-character UUID).\n        required: true\n      - name: method\n        type: string\n        description: API method to invoke.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: Format for the response data.\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: getparameterlist\n      description: Get Parameter List\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getparameterlist\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: Your registered BEA API key.\n        required: true\n      - name: method\n        type: string\n        description: API method to invoke.\n        required: true\n      - name: DatasetName\n        type: string\n        description: Name of the dataset for which to retrieve parameters.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getparametervalues\n\
  \      description: Get Parameter Values\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getparametervalues\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        ParameterName: tools.ParameterName\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: ParameterName\n        type: string\n        description: Name of the parameter for which to retrieve valid values.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type:\
  \ object\n        mapping: $.\n    - name: getnipadata\n      description: Get NIPA Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getnipadata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        TableName: tools.TableName\n        Frequency: tools.Frequency\n        Year: tools.Year\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: TableName\n        type: string\n        description: NIPA table name (e.g., T10101 for GDP).\n        required: true\n      - name: Frequency\n        type: string\n  \
  \      description: Data frequency.\n        required: true\n      - name: Year\n        type: string\n        description: Year(s) for data retrieval. Use 'X' for all years.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getregionaldata\n      description: Get Regional Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getregionaldata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        TableName: tools.TableName\n        LineCode: tools.LineCode\n        GeoFips: tools.GeoFips\n        Year: tools.Year\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n\
  \        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: TableName\n        type: string\n        description: Regional table code (e.g., SQGDP1 for Quarterly GDP by State).\n        required: true\n      - name: LineCode\n        type: integer\n        description: Line code within the regional table.\n        required: true\n      - name: GeoFips\n        type: string\n        description: Geographic FIPS code. Use 'STATE' for all states, '00000' for US total.\n        required: true\n      - name: Year\n        type: string\n        description: Year(s) for data retrieval. Use 'LAST5' for last 5 years.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getgdpbyindustrydata\n      description: Get GDP by Industry\
  \ Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getgdpbyindustrydata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        TableID: tools.TableID\n        Frequency: tools.Frequency\n        Year: tools.Year\n        Industry: tools.Industry\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: TableID\n        type: integer\n        description: Table identifier within GDPbyIndustry dataset.\n        required: true\n      - name: Frequency\n        type: string\n        description: Frequency\n       \
  \ required: true\n      - name: Year\n        type: string\n        description: Year\n        required: true\n      - name: Industry\n        type: string\n        description: Industry code. Use 'ALL' for all industries.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getitadata\n      description: Get International Transactions Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getitadata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        Indicator: tools.Indicator\n        AreaOrCountry: tools.AreaOrCountry\n        Frequency: tools.Frequency\n        Year: tools.Year\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n     \
  \   description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: Indicator\n        type: string\n        description: ITA indicator code (e.g., BalGds for Balance on Goods).\n        required: true\n      - name: AreaOrCountry\n        type: string\n        description: Country or area code. Use 'AllCountries' for all.\n        required: true\n      - name: Frequency\n        type: string\n        description: Frequency\n        required: true\n      - name: Year\n        type: string\n        description: Year\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getfixedassetsdata\n      description: Get Fixed Assets Data\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getfixedassetsdata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        TableName: tools.TableName\n        Year: tools.Year\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: TableName\n        type: string\n        description: Fixed assets table name (e.g., FAAt101 for Current-Cost Net Stock).\n        required: true\n      - name: Year\n        type: string\n        description: Year\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getinputoutputdata\n      description: Get Input-Output Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getinputoutputdata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        TableID: tools.TableID\n        Year: tools.Year\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n        type: string\n        description: DatasetName\n        required: true\n      - name: TableID\n        type: integer\n        description: Input-Output table identifier.\n        required: true\n      - name: Year\n        type: string\n\
  \        description: Year\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmnedata\n      description: Get Multinational Enterprises Data\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: the-bureau-of-economic-analysis.getmnedata\n      with:\n        UserID: tools.UserID\n        method: tools.method\n        DatasetName: tools.DatasetName\n        DirectionOfInvestment: tools.DirectionOfInvestment\n        ClassificationCode: tools.ClassificationCode\n        Year: tools.Year\n        SeriesID: tools.SeriesID\n        ResultFormat: tools.ResultFormat\n      inputParameters:\n      - name: UserID\n        type: string\n        description: UserID\n        required: true\n      - name: method\n        type: string\n        description: method\n        required: true\n      - name: DatasetName\n\
  \        type: string\n        description: DatasetName\n        required: true\n      - name: DirectionOfInvestment\n        type: string\n        description: Direction of investment - outward (US parent) or inward (foreign parent).\n        required: true\n      - name: ClassificationCode\n        type: string\n        description: Industry or country classification code.\n        required: true\n      - name: Year\n        type: string\n        description: Year\n        required: true\n      - name: SeriesID\n        type: integer\n        description: MNE series identifier for the measure requested.\n        required: true\n      - name: ResultFormat\n        type: string\n        description: ResultFormat\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    THE_BUREAU_OF_ECONOMIC_ANALYSIS_TOKEN: THE_BUREAU_OF_ECONOMIC_ANALYSIS_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/the-bureau-of-economic-analysis/refs/heads/main/capabilities/the-bureau-of-economic-analysis-capability.yaml
tags:
- The
- Bureau
- Of
- Economic
- Analysis
- API
tools:
- description: Get Dataset List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getdatasetlist
- description: Get Parameter List
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparameterlist
- description: Get Parameter Values
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getparametervalues
- description: Get NIPA Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getnipadata
- description: Get Regional Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getregionaldata
- description: Get GDP by Industry Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getgdpbyindustrydata
- description: Get International Transactions Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getitadata
- description: Get Fixed Assets Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfixedassetsdata
- description: Get Input-Output Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getinputoutputdata
- description: Get Multinational Enterprises Data
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmnedata
---
