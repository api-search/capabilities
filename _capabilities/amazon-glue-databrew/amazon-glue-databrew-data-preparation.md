---
categories:
- data-engineering
consumed_apis:
- amazon-glue-databrew
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
- manage datasets for transformation
- list job runs
- list all databrew datasets available for preparation
- manage data transformation recipes
- Data Scientist
- list projects
- list all projects
- create a new dataset from s3, database, or other sources
- amazon glue databrew
- manage collaborative databrew projects
- prepares and cleans data for business analytics
- list all databrew jobs
- create dataset
- list all databrew datasets
- create a new recipe with transformation steps
- list jobs
- create a new dataset
- list datasets
- list all runs for a specific job
- aws
- list all recipes
- list recipes
- Data Analyst
- list all databrew transformation and profiling jobs
- create recipe
- execute a databrew transformation or profiling job
- create a new recipe
- data preparation
- list all data transformation recipes
- start a job execution
- machine learning
- publish a recipe version for production use
- publish recipe
- describe dataset
- list all collaborative databrew projects
- data analytics
- create a new databrew project for collaborative data preparation
- get details about a specific dataset
- etl
- create recipe job
- analytics
- start job run
- create project
- create a job to apply a recipe to a dataset
- prepares datasets for machine learning model training
- manage and run databrew jobs
slug: amazon-glue-databrew-data-preparation
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: Amazon Glue DataBrew Data Preparation\n  description: >-\n    Workflow capability for data analysts and data scientists preparing data\n    using Amazon Glue DataBrew. Covers dataset management, recipe creation,\n    job execution, and profiling for analytics and machine learning workflows.\n  tags:\n    - Amazon Glue DataBrew\n    - Data Preparation\n    - ETL\n    - Analytics\n    - Machine Learning\n    - AWS\n  created: \"2026-04-19\"\n  modified: \"2026-04-19\"\n\nbinds:\n  - namespace: env\n    keys:\n      AWS_ACCESS_KEY_ID: AWS_ACCESS_KEY_ID\n      AWS_SECRET_ACCESS_KEY: AWS_SECRET_ACCESS_KEY\n      AWS_REGION: AWS_REGION\n\ncapability:\n  consumes:\n    - import: amazon-glue-databrew\n      location: ./shared/amazon-glue-databrew.yaml\n\n  exposes:\n    - type: rest\n      port: 8082\n      namespace: glue-databrew-data-prep-api\n      description: Unified REST API for Amazon Glue DataBrew data preparation workflows.\n \
  \     resources:\n        - path: /v1/datasets\n          name: datasets\n          description: Manage datasets for transformation\n          operations:\n            - method: GET\n              name: list-datasets\n              description: List all DataBrew datasets\n              call: amazon-glue-databrew.ListDatasets\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-dataset\n              description: Create a new dataset\n              call: amazon-glue-databrew.CreateDataset\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/recipes\n          name: recipes\n          description: Manage data transformation recipes\n          operations:\n            - method: GET\n              name: list-recipes\n              description: List all recipes\n              call: amazon-glue-databrew.ListRecipes\n      \
  \        outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: create-recipe\n              description: Create a new recipe\n              call: amazon-glue-databrew.CreateRecipe\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n        - path: /v1/jobs\n          name: jobs\n          description: Manage and run DataBrew jobs\n          operations:\n            - method: GET\n              name: list-jobs\n              description: List all DataBrew jobs\n              call: amazon-glue-databrew.ListJobs\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n            - method: POST\n              name: start-job-run\n              description: Start a job execution\n              call: amazon-glue-databrew.StartJobRun\n              outputParameters:\n                - type: object\n                  mapping:\
  \ \"$.\"\n        - path: /v1/projects\n          name: projects\n          description: Manage collaborative DataBrew projects\n          operations:\n            - method: GET\n              name: list-projects\n              description: List all projects\n              call: amazon-glue-databrew.ListProjects\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9092\n      namespace: glue-databrew-data-prep-mcp\n      transport: http\n      description: MCP server for AI-assisted data preparation using Amazon Glue DataBrew.\n      tools:\n        - name: list-datasets\n          description: List all DataBrew datasets available for preparation\n          hints:\n            readOnly: true\n            openWorld: true\n          call: amazon-glue-databrew.ListDatasets\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-dataset\n          description:\
  \ Create a new dataset from S3, database, or other sources\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.CreateDataset\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: describe-dataset\n          description: Get details about a specific dataset\n          hints:\n            readOnly: true\n          call: amazon-glue-databrew.DescribeDataset\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-recipes\n          description: List all data transformation recipes\n          hints:\n            readOnly: true\n          call: amazon-glue-databrew.ListRecipes\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-recipe\n          description: Create a new recipe with transformation steps\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.CreateRecipe\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: publish-recipe\n          description: Publish a recipe version for production use\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.PublishRecipe\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-jobs\n          description: List all DataBrew transformation and profiling jobs\n          hints:\n            readOnly: true\n          call: amazon-glue-databrew.ListJobs\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-recipe-job\n          description: Create a job to apply a recipe to a dataset\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.CreateRecipeJob\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: start-job-run\n          description:\
  \ Execute a DataBrew transformation or profiling job\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.StartJobRun\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-job-runs\n          description: List all runs for a specific job\n          hints:\n            readOnly: true\n          call: amazon-glue-databrew.ListJobRuns\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: list-projects\n          description: List all collaborative DataBrew projects\n          hints:\n            readOnly: true\n          call: amazon-glue-databrew.ListProjects\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n        - name: create-project\n          description: Create a new DataBrew project for collaborative data preparation\n          hints:\n            readOnly: false\n          call: amazon-glue-databrew.CreateProject\n\
  \          outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-glue-databrew/refs/heads/main/capabilities/amazon-glue-databrew-data-preparation.yaml
tags:
- Amazon Glue DataBrew
- Data Preparation
- ETL
- Analytics
- Machine Learning
- AWS
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
