---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Amazon Healthlake Health Data Operations
operations: []
personas: []
provider_name: Amazon HealthLake
provider_slug: amazon-healthlake
search_terms:
- fhir
- cloud computing
- hipaa
- aws
- health data
- healthcare
slug: amazon-healthlake-health-data-operations
source_yaml: "name: Amazon HealthLake Health Data Operations\nversion: 1.0.0-alpha1\ndescription: Workflow capability for managing FHIR health data including datastores, import and export jobs.\npersona:\n  - Healthcare Developer\n  - FHIR Data Engineer\n  - HIPAA Compliance Officer\napis:\n  - Amazon HealthLake\ntools:\n  - name: create_fhir_datastore\n    description: Create a new FHIR datastore for health data storage\n    operationId: CreateFHIRDatastore\n    method: POST\n    path: /datastore\n  - name: list_fhir_datastores\n    description: List all FHIR datastores in the account\n    operationId: ListFHIRDatastores\n    method: GET\n    path: /datastore\n  - name: describe_fhir_datastore\n    description: Get details of a specific FHIR datastore\n    operationId: DescribeFHIRDatastore\n    method: GET\n    path: /datastore/{DatastoreId}\n  - name: delete_fhir_datastore\n    description: Delete a FHIR datastore\n    operationId: DeleteFHIRDatastore\n    method: DELETE\n    path: /datastore/{DatastoreId}\n\
  \  - name: start_fhir_import_job\n    description: Start a FHIR import job to load health data\n    operationId: StartFHIRImportJob\n    method: POST\n    path: /datastore/{DatastoreId}/fhirImport\n  - name: describe_fhir_import_job\n    description: Get status of a FHIR import job\n    operationId: DescribeFHIRImportJob\n    method: GET\n    path: /datastore/{DatastoreId}/fhirImport/{JobId}\n  - name: list_fhir_import_jobs\n    description: List all FHIR import jobs for a datastore\n    operationId: ListFHIRImportJobs\n    method: GET\n    path: /datastore/{DatastoreId}/fhirImport\n  - name: start_fhir_export_job\n    description: Start a FHIR export job to export health data\n    operationId: StartFHIRExportJob\n    method: POST\n    path: /datastore/{DatastoreId}/fhirExport\n  - name: describe_fhir_export_job\n    description: Get status of a FHIR export job\n    operationId: DescribeFHIRExportJob\n    method: GET\n    path: /datastore/{DatastoreId}/fhirExport/{JobId}\n  - name: list_fhir_export_jobs\n\
  \    description: List all FHIR export jobs for a datastore\n    operationId: ListFHIRExportJobs\n    method: GET\n    path: /datastore/{DatastoreId}/fhirExport\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-healthlake/refs/heads/main/capabilities/amazon-healthlake-health-data-operations.yaml
tags: []
tools: []
---
