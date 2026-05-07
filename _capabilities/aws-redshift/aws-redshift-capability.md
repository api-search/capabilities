---
categories: []
consumed_apis: []
description: <p>You can use the Amazon Redshift Data API to run queries on Amazon Redshift tables. You can run SQL statements, which are committed if the statement succeeds. </p> <p>For more information about the Amazon Redshift Data API and CLI usage examples, see <a href="https://docs.aws.amazon.com/redshift/latest/mgmt/data-api.html">Using the Amazon Redshift Data API</a> in the <i>Amazon Redshift Management Guide</i>. </p>
layout: capability
name: Redshift Data API Service
operations:
- description: Amazon Redshift Data - Batch Execute Statement
  method: POST
  name: batchexecutestatement
  path: /#X-Amz-Target=RedshiftData.BatchExecuteStatement
- description: Amazon Redshift Data - Cancel Statement
  method: POST
  name: cancelstatement
  path: /#X-Amz-Target=RedshiftData.CancelStatement
- description: Amazon Redshift Data - Describe Statement
  method: POST
  name: describestatement
  path: /#X-Amz-Target=RedshiftData.DescribeStatement
- description: Amazon Redshift Data - Describe Table
  method: POST
  name: describetable
  path: /#X-Amz-Target=RedshiftData.DescribeTable
- description: Amazon Redshift Data - Execute Statement
  method: POST
  name: executestatement
  path: /#X-Amz-Target=RedshiftData.ExecuteStatement
- description: Amazon Redshift Data - Get Statement Result
  method: POST
  name: getstatementresult
  path: /#X-Amz-Target=RedshiftData.GetStatementResult
- description: Amazon Redshift Data - List Databases
  method: POST
  name: listdatabases
  path: /#X-Amz-Target=RedshiftData.ListDatabases
- description: Amazon Redshift Data - List Schemas
  method: POST
  name: listschemas
  path: /#X-Amz-Target=RedshiftData.ListSchemas
- description: Amazon Redshift Data - List Statements
  method: POST
  name: liststatements
  path: /#X-Amz-Target=RedshiftData.ListStatements
- description: Amazon Redshift Data - List Tables
  method: POST
  name: listtables
  path: /#X-Amz-Target=RedshiftData.ListTables
personas: []
provider_name: AWS Redshift
provider_slug: aws-redshift
search_terms:
- amazon redshift data - list statements
- analytics
- amazon redshift data - get statement result
- amazon redshift data - execute statement
- amazon redshift data - describe table
- data warehouse
- api
- describestatement
- amazon redshift data - list tables
- getstatementresult
- redshift
- amazon redshift data - cancel statement
- describetable
- amazon redshift data - list schemas
- big data
- sql
- listtables
- executestatement
- listschemas
- amazon redshift data - list databases
- listdatabases
- cancelstatement
- amazon redshift data - describe statement
- liststatements
- aws
- batchexecutestatement
- cloud database
- amazon redshift data - batch execute statement
slug: aws-redshift-capability
source_filename: aws-redshift-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Redshift Data API Service\n  description: <p>You can use the Amazon Redshift Data API to run queries on Amazon Redshift tables. You can run SQL statements,\n    which are committed if the statement succeeds. </p> <p>For more information about the Amazon Redshift Data API and CLI\n    usage examples, see <a href=\"https://docs.aws.amazon.com/redshift/latest/mgmt/data-api.html\">Using the Amazon Redshift\n    Data API</a> in the <i>Amazon Redshift Management Guide</i>. </p>\n  tags:\n  - Aws\n  - Redshift\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: aws-redshift\n    baseUri: http://redshift-data.us-east-1.amazonaws.com\n    description: Redshift Data API Service HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{AWS_REDSHIFT_TOKEN}}'\n    resources:\n    - name: x-amz-target-redshiftdata-batchexecutestatement\n\
  \      path: /#X-Amz-Target=RedshiftData.BatchExecuteStatement\n      operations:\n      - name: batchexecutestatement\n        method: POST\n        description: Amazon Redshift Data - Batch Execute Statement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-cancelstatement\n      path: /#X-Amz-Target=RedshiftData.CancelStatement\n      operations:\n      - name: cancelstatement\n        method: POST\n        description: Amazon Redshift Data - Cancel Statement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-describestatement\n\
  \      path: /#X-Amz-Target=RedshiftData.DescribeStatement\n      operations:\n      - name: describestatement\n        method: POST\n        description: Amazon Redshift Data - Describe Statement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-describetable\n      path: /#X-Amz-Target=RedshiftData.DescribeTable\n      operations:\n      - name: describetable\n        method: POST\n        description: Amazon Redshift Data - Describe Table\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n   \
  \       type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-executestatement\n      path: /#X-Amz-Target=RedshiftData.ExecuteStatement\n      operations:\n      - name: executestatement\n        method: POST\n        description: Amazon Redshift Data - Execute Statement\n        inputParameters:\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-getstatementresult\n      path: /#X-Amz-Target=RedshiftData.GetStatementResult\n      operations:\n      - name: getstatementresult\n        method: POST\n        description: Amazon Redshift Data - Get Statement Result\n        inputParameters:\n        - name: NextToken\n       \
  \   in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-listdatabases\n      path: /#X-Amz-Target=RedshiftData.ListDatabases\n      operations:\n      - name: listdatabases\n        method: POST\n        description: Amazon Redshift Data - List Databases\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: x-amz-target-redshiftdata-listschemas\n      path: /#X-Amz-Target=RedshiftData.ListSchemas\n      operations:\n      - name: listschemas\n        method: POST\n        description: Amazon Redshift Data - List Schemas\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-liststatements\n      path: /#X-Amz-Target=RedshiftData.ListStatements\n      operations:\n      - name: liststatements\n        method: POST\n        description: Amazon Redshift Data - List Statements\n        inputParameters:\n\
  \        - name: MaxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: x-amz-target-redshiftdata-listtables\n      path: /#X-Amz-Target=RedshiftData.ListTables\n      operations:\n      - name: listtables\n        method: POST\n        description: Amazon Redshift Data - List Tables\n        inputParameters:\n        - name: MaxResults\n          in: query\n          type: string\n          description: Pagination limit\n        - name: NextToken\n          in: query\n          type: string\n          description: Pagination token\n        - name: X-Amz-Target\n          in: header\n          type:\
  \ string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: aws-redshift-rest\n    description: REST adapter for Redshift Data API Service.\n    resources:\n    - path: /#X-Amz-Target=RedshiftData.BatchExecuteStatement\n      name: batchexecutestatement\n      operations:\n      - method: POST\n        name: batchexecutestatement\n        description: Amazon Redshift Data - Batch Execute Statement\n        call: aws-redshift.batchexecutestatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.CancelStatement\n      name: cancelstatement\n      operations:\n      - method: POST\n        name: cancelstatement\n        description: Amazon Redshift Data - Cancel Statement\n        call: aws-redshift.cancelstatement\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.DescribeStatement\n      name: describestatement\n      operations:\n      - method: POST\n        name: describestatement\n        description: Amazon Redshift Data - Describe Statement\n        call: aws-redshift.describestatement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.DescribeTable\n      name: describetable\n      operations:\n      - method: POST\n        name: describetable\n        description: Amazon Redshift Data - Describe Table\n        call: aws-redshift.describetable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.ExecuteStatement\n      name: executestatement\n      operations:\n      - method: POST\n        name: executestatement\n        description: Amazon Redshift Data - Execute Statement\n        call: aws-redshift.executestatement\n        outputParameters:\n   \
  \     - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.GetStatementResult\n      name: getstatementresult\n      operations:\n      - method: POST\n        name: getstatementresult\n        description: Amazon Redshift Data - Get Statement Result\n        call: aws-redshift.getstatementresult\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.ListDatabases\n      name: listdatabases\n      operations:\n      - method: POST\n        name: listdatabases\n        description: Amazon Redshift Data - List Databases\n        call: aws-redshift.listdatabases\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.ListSchemas\n      name: listschemas\n      operations:\n      - method: POST\n        name: listschemas\n        description: Amazon Redshift Data - List Schemas\n        call: aws-redshift.listschemas\n        outputParameters:\n \
  \       - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.ListStatements\n      name: liststatements\n      operations:\n      - method: POST\n        name: liststatements\n        description: Amazon Redshift Data - List Statements\n        call: aws-redshift.liststatements\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /#X-Amz-Target=RedshiftData.ListTables\n      name: listtables\n      operations:\n      - method: POST\n        name: listtables\n        description: Amazon Redshift Data - List Tables\n        call: aws-redshift.listtables\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: aws-redshift-mcp\n    transport: http\n    description: MCP adapter for Redshift Data API Service for AI agent use.\n    tools:\n    - name: batchexecutestatement\n      description: Amazon Redshift Data - Batch Execute Statement\n      hints:\n        readOnly:\
  \ false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.batchexecutestatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: cancelstatement\n      description: Amazon Redshift Data - Cancel Statement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.cancelstatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describestatement\n      description: Amazon Redshift Data - Describe Statement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.describestatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describetable\n      description: Amazon Redshift Data - Describe Table\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.describetable\n      with:\n\
  \        MaxResults: tools.MaxResults\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n        type: string\n        description: Pagination limit\n      - name: NextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: executestatement\n      description: Amazon Redshift Data - Execute Statement\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.executestatement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getstatementresult\n      description: Amazon Redshift Data - Get Statement Result\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.getstatementresult\n      with:\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: NextToken\n        type: string\n        description:\
  \ Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listdatabases\n      description: Amazon Redshift Data - List Databases\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.listdatabases\n      with:\n        MaxResults: tools.MaxResults\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n        type: string\n        description: Pagination limit\n      - name: NextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listschemas\n      description: Amazon Redshift Data - List Schemas\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.listschemas\n      with:\n        MaxResults: tools.MaxResults\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n\
  \        type: string\n        description: Pagination limit\n      - name: NextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: liststatements\n      description: Amazon Redshift Data - List Statements\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.liststatements\n      with:\n        MaxResults: tools.MaxResults\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n        type: string\n        description: Pagination limit\n      - name: NextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listtables\n      description: Amazon Redshift Data - List Tables\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: aws-redshift.listtables\n\
  \      with:\n        MaxResults: tools.MaxResults\n        NextToken: tools.NextToken\n      inputParameters:\n      - name: MaxResults\n        type: string\n        description: Pagination limit\n      - name: NextToken\n        type: string\n        description: Pagination token\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    AWS_REDSHIFT_TOKEN: AWS_REDSHIFT_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/aws-redshift/refs/heads/main/capabilities/aws-redshift-capability.yaml
tags:
- Aws
- Redshift
- API
tools:
- description: Amazon Redshift Data - Batch Execute Statement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: batchexecutestatement
- description: Amazon Redshift Data - Cancel Statement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cancelstatement
- description: Amazon Redshift Data - Describe Statement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describestatement
- description: Amazon Redshift Data - Describe Table
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: describetable
- description: Amazon Redshift Data - Execute Statement
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: executestatement
- description: Amazon Redshift Data - Get Statement Result
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: getstatementresult
- description: Amazon Redshift Data - List Databases
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listdatabases
- description: Amazon Redshift Data - List Schemas
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listschemas
- description: Amazon Redshift Data - List Statements
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: liststatements
- description: Amazon Redshift Data - List Tables
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: listtables
---
