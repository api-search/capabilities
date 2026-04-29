---
categories: []
consumed_apis: []
description: ''
layout: capability
name: Amazon Healthimaging Medical Imaging Operations
operations: []
personas: []
provider_name: Amazon HealthImaging
provider_slug: amazon-healthimaging
search_terms:
- dicom
- machine learning
- medical imaging
- aws
- healthcare
- hipaa
slug: amazon-healthimaging-medical-imaging-operations
source_yaml: "name: Amazon HealthImaging Medical Imaging Operations\nversion: 1.0.0-alpha1\ndescription: Workflow capability for managing HIPAA-eligible medical imaging data including datastores, image sets, and DICOM import jobs.\npersona:\n  - Healthcare Developer\n  - Medical Imaging Engineer\n  - HIPAA Compliance Officer\napis:\n  - Amazon HealthImaging\ntools:\n  - name: list_datastores\n    description: List all HealthImaging datastores in the account\n    operationId: ListDatastores\n    method: GET\n    path: /datastore\n  - name: create_datastore\n    description: Create a new datastore for storing medical imaging data\n    operationId: CreateDatastore\n    method: POST\n    path: /datastore\n  - name: get_datastore\n    description: Get details of a specific datastore\n    operationId: GetDatastore\n    method: GET\n    path: /datastore/{datastoreId}\n  - name: delete_datastore\n    description: Delete a datastore and all its contents\n    operationId: DeleteDatastore\n    method:\
  \ DELETE\n    path: /datastore/{datastoreId}\n  - name: search_image_sets\n    description: Search for image sets within a datastore\n    operationId: SearchImageSets\n    method: POST\n    path: /datastore/{datastoreId}/searchImageSets\n  - name: get_image_set\n    description: Get metadata about a specific image set\n    operationId: GetImageSet\n    method: GET\n    path: /datastore/{datastoreId}/imageSet/{imageSetId}/getImageSet\n  - name: get_image_set_metadata\n    description: Retrieve the metadata of an image set\n    operationId: GetImageSetMetadata\n    method: GET\n    path: /datastore/{datastoreId}/imageSet/{imageSetId}/getImageSetMetadata\n  - name: copy_image_set\n    description: Copy an image set to another datastore or location\n    operationId: CopyImageSet\n    method: POST\n    path: /datastore/{datastoreId}/imageSet/{sourceImageSetId}/copyImageSet\n  - name: start_dicom_import_job\n    description: Start a DICOM import job to ingest medical imaging data\n    operationId:\
  \ StartDICOMImportJob\n    method: POST\n    path: /datastore/{datastoreId}/dicomImportJob\n  - name: get_dicom_import_job\n    description: Get the status of a DICOM import job\n    operationId: GetDICOMImportJob\n    method: GET\n    path: /datastore/{datastoreId}/dicomImportJob/{jobId}\n  - name: list_dicom_import_jobs\n    description: List all DICOM import jobs for a datastore\n    operationId: ListDICOMImportJobs\n    method: GET\n    path: /datastore/{datastoreId}/dicomImportJobs\n  - name: get_image_frame\n    description: Retrieve an image frame from an image set\n    operationId: GetImageFrame\n    method: POST\n    path: /datastore/{datastoreId}/imageSet/{imageSetId}/getImageFrame\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/amazon-healthimaging/refs/heads/main/capabilities/amazon-healthimaging-medical-imaging-operations.yaml
tags: []
tools: []
---
