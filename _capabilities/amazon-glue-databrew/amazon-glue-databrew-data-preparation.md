---
categories:
- data-engineering
consumed_apis: []
description: Workflow capability for data analysts and data scientists preparing data using Amazon Glue DataBrew. Covers dataset management, recipe creation, job execution, and profiling for analytics and machine learning workflows.
layout: capability
name: Amazon Glue DataBrew Data Preparation
operations:
- description: List all DataBrew datasets
  method: GET
  name: list-datasets
  path: /v1/datasets
- description: Create a new dataset
  method: POST
  name: create-dataset
  path: /v1/datasets
- description: List all recipes
  method: GET
  name: list-recipes
  path: /v1/recipes
- description: Create a new recipe
  method: POST
  name: create-recipe
  path: /v1/recipes
- description: List all DataBrew jobs
  method: GET
  name: list-jobs
  path: /v1/jobs
- description: Start a job execution
  method: POST
  name: start-job-run
  path: /v1/jobs
- description: List all projects
  method: GET
  name: list-projects
  path: /v1/projects
personas: []
provider_name: Amazon Glue DataBrew
provider_slug: amazon-glue-databrew
search_terms:
- list recipes
- analytics
- create a new recipe with transformation steps
- list all databrew datasets
- create recipe job
- list all recipes
- list all collaborative databrew projects
- prepares datasets for machine learning model training
- manage and run databrew jobs
- Data Analyst
- Data Scientist
- publish recipe
- data analytics
- list all databrew jobs
- list all data transformation recipes
- start a job execution
- manage datasets for transformation
- amazon glue databrew
- machine learning
- create recipe
- manage data transformation recipes
- list projects
- create project
- describe dataset
- create dataset
- list job runs
- create a new dataset from s3, database, or other sources
- list all databrew transformation and profiling jobs
- execute a databrew transformation or profiling job
- list jobs
- list all databrew datasets available for preparation
- list all projects
- manage collaborative databrew projects
- create a job to apply a recipe to a dataset
- etl
- aws
- list datasets
- publish a recipe version for production use
- data preparation
- get details about a specific dataset
- prepares and cleans data for business analytics
- list all runs for a specific job
- create a new recipe
- create a new dataset
- start job run
- create a new databrew project for collaborative data preparation
slug: amazon-glue-databrew-data-preparation
source_filename: amazon-glue-databrew-data-preparation.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Amazon Glue DataBrew Data Preparation\n  description: Workflow capability for data analysts and data scientists preparing data using Amazon Glue DataBrew. Covers\n    dataset management, recipe creation, job execution, and profiling for analytics and machine learning workflows.\n  tags:\n  - Amazon Glue DataBrew\n  - Data Preparation\n  - ETL\n  - Analytics\n  - Machine Learning\n  - AWS\n  created: '2026-04-19'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n    AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n    AWS_REGION: AWS_REGION\ncapability:\n  consumes:\n  - type: http\n    namespace: amazon-glue-databrew\n    baseUri: https://databrew.amazonaws.com\n    description: Amazon Glue DataBrew API\n    authentication:\n      type: apikey\n      key: Authorization\n      value: '{{AWS_AUTH_HEADER}}'\n      placement: header\n    resources:\n    - name: datasets\n      path: /datasets\n\
  \      description: Manage DataBrew datasets\n      operations:\n      - name: ListDatasets\n        method: GET\n        description: List all datasets\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateDataset\n        method: POST\n        description: Create a new dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DescribeDataset\n        method: GET\n        description: Get dataset details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: DeleteDataset\n        method: DELETE\n        description: Delete a dataset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes\n      path: /recipes\n      description:\
  \ Manage data transformation recipes\n      operations:\n      - name: ListRecipes\n        method: GET\n        description: List all recipes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateRecipe\n        method: POST\n        description: Create a new recipe\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: PublishRecipe\n        method: POST\n        description: Publish a recipe version\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: jobs\n      path: /jobs\n      description: Manage DataBrew transformation jobs\n      operations:\n      - name: ListJobs\n        method: GET\n        description: List all jobs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n      - name: CreateRecipeJob\n        method: POST\n        description: Create a recipe job\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: StartJobRun\n        method: POST\n        description: Start a job run\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects\n      path: /projects\n      description: Manage DataBrew projects\n      operations:\n      - name: ListProjects\n        method: GET\n        description: List all projects\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: CreateProject\n        method: POST\n        description: Create a new project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n \
  \         value: $.\n  exposes:\n  - type: rest\n    port: 8082\n    namespace: glue-databrew-data-prep-api\n    description: Unified REST API for Amazon Glue DataBrew data preparation workflows.\n    resources:\n    - path: /v1/datasets\n      name: datasets\n      description: Manage datasets for transformation\n      operations:\n      - method: GET\n        name: list-datasets\n        description: List all DataBrew datasets\n        call: amazon-glue-databrew.ListDatasets\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-dataset\n        description: Create a new dataset\n        call: amazon-glue-databrew.CreateDataset\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipes\n      name: recipes\n      description: Manage data transformation recipes\n      operations:\n      - method: GET\n        name: list-recipes\n        description: List all recipes\n        call: amazon-glue-databrew.ListRecipes\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: create-recipe\n        description: Create a new recipe\n        call: amazon-glue-databrew.CreateRecipe\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/jobs\n      name: jobs\n      description: Manage and run DataBrew jobs\n      operations:\n      - method: GET\n        name: list-jobs\n        description: List all DataBrew jobs\n        call: amazon-glue-databrew.ListJobs\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: start-job-run\n        description: Start a job execution\n        call: amazon-glue-databrew.StartJobRun\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/projects\n      name: projects\n      description: Manage collaborative DataBrew projects\n      operations:\n      - method: GET\n        name: list-projects\n\
  \        description: List all projects\n        call: amazon-glue-databrew.ListProjects\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9092\n    namespace: glue-databrew-data-prep-mcp\n    transport: http\n    description: MCP server for AI-assisted data preparation using Amazon Glue DataBrew.\n    tools:\n    - name: list-datasets\n      description: List all DataBrew datasets available for preparation\n      hints:\n        readOnly: true\n        openWorld: true\n      call: amazon-glue-databrew.ListDatasets\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-dataset\n      description: Create a new dataset from S3, database, or other sources\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.CreateDataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: describe-dataset\n      description: Get details about a specific dataset\n      hints:\n\
  \        readOnly: true\n      call: amazon-glue-databrew.DescribeDataset\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recipes\n      description: List all data transformation recipes\n      hints:\n        readOnly: true\n      call: amazon-glue-databrew.ListRecipes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-recipe\n      description: Create a new recipe with transformation steps\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.CreateRecipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: publish-recipe\n      description: Publish a recipe version for production use\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.PublishRecipe\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-jobs\n      description: List all DataBrew transformation and profiling jobs\n      hints:\n        readOnly: true\n\
  \      call: amazon-glue-databrew.ListJobs\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-recipe-job\n      description: Create a job to apply a recipe to a dataset\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.CreateRecipeJob\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: start-job-run\n      description: Execute a DataBrew transformation or profiling job\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.StartJobRun\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-job-runs\n      description: List all runs for a specific job\n      hints:\n        readOnly: true\n      call: amazon-glue-databrew.ListJobRuns\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-projects\n      description: List all collaborative DataBrew projects\n      hints:\n        readOnly: true\n      call: amazon-glue-databrew.ListProjects\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: create-project\n      description: Create a new DataBrew project for collaborative data preparation\n      hints:\n        readOnly: false\n      call: amazon-glue-databrew.CreateProject\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-glue-databrew/refs/heads/main/capabilities/amazon-glue-databrew-data-preparation.yaml
tags:
- Amazon Glue DataBrew
- Data Preparation
- ETL
- Analytics
- Machine Learning
tools:
- description: List all DataBrew datasets available for preparation
  hints:
    openWorld: true
    readOnly: true
  name: list-datasets
- description: Create a new dataset from S3, database, or other sources
  hints:
    readOnly: false
  name: create-dataset
- description: Get details about a specific dataset
  hints:
    readOnly: true
  name: describe-dataset
- description: List all data transformation recipes
  hints:
    readOnly: true
  name: list-recipes
- description: Create a new recipe with transformation steps
  hints:
    readOnly: false
  name: create-recipe
- description: Publish a recipe version for production use
  hints:
    readOnly: false
  name: publish-recipe
- description: List all DataBrew transformation and profiling jobs
  hints:
    readOnly: true
  name: list-jobs
- description: Create a job to apply a recipe to a dataset
  hints:
    readOnly: false
  name: create-recipe-job
- description: Execute a DataBrew transformation or profiling job
  hints:
    readOnly: false
  name: start-job-run
- description: List all runs for a specific job
  hints:
    readOnly: true
  name: list-job-runs
- description: List all collaborative DataBrew projects
  hints:
    readOnly: true
  name: list-projects
- description: Create a new DataBrew project for collaborative data preparation
  hints:
    readOnly: false
  name: create-project
---
