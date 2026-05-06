---
categories: []
consumed_apis: []
description: The Data Catalog API provides a unified view of all data assets and enables metadata management, data discovery, and data governance across an organization. It allows programmatic creation and management of entries, tag templates, and policy tags.
layout: capability
name: Google Cloud Data Catalog API
operations:
- description: Google Cloud Data Catalog Search Data Catalog
  method: POST
  name: searchcatalog
  path: /catalog:search
- description: Google Cloud Data Catalog List entry groups
  method: GET
  name: listentrygroups
  path: /projects/{projectId}/locations/{location}/entryGroups
- description: Google Cloud Data Catalog Create an entry group
  method: POST
  name: createentrygroup
  path: /projects/{projectId}/locations/{location}/entryGroups
- description: Google Cloud Data Catalog List entries
  method: GET
  name: listentries
  path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries
- description: Google Cloud Data Catalog Create an entry
  method: POST
  name: createentry
  path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries
- description: Google Cloud Data Catalog Get an entry
  method: GET
  name: getentry
  path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}
- description: Google Cloud Data Catalog Update an entry
  method: PATCH
  name: updateentry
  path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}
- description: Google Cloud Data Catalog Delete an entry
  method: DELETE
  name: deleteentry
  path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}
- description: Google Cloud Data Catalog Create a tag template
  method: POST
  name: createtagtemplate
  path: /projects/{projectId}/locations/{location}/tagTemplates
- description: Google Cloud Data Catalog Get a tag template
  method: GET
  name: gettagtemplate
  path: /projects/{projectId}/locations/{location}/tagTemplates/{tagTemplateId}
personas: []
provider_name: Google Cloud Data Catalog
provider_slug: google-cloud-data-catalog
search_terms:
- listentrygroups
- google cloud data catalog list entry groups
- google cloud data catalog create a tag template
- getentry
- searchcatalog
- deleteentry
- updateentry
- cloud
- google cloud data catalog delete an entry
- google
- google cloud data catalog create an entry group
- google cloud data catalog get a tag template
- createtagtemplate
- google cloud data catalog create an entry
- data governance
- google cloud data catalog search data catalog
- createentrygroup
- google cloud data catalog update an entry
- api
- listentries
- google cloud data catalog get an entry
- createentry
- data
- google cloud data catalog list entries
- catalog
- metadata
- gettagtemplate
- data catalog
- google cloud
slug: google-cloud-data-catalog-capability
source_filename: google-cloud-data-catalog-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Google Cloud Data Catalog API\n  description: The Data Catalog API provides a unified view of all data assets and enables metadata management, data discovery,\n    and data governance across an organization. It allows programmatic creation and management of entries, tag templates,\n    and policy tags.\n  tags:\n  - Google\n  - Cloud\n  - Data\n  - Catalog\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: google-cloud-data-catalog\n    baseUri: https://datacatalog.googleapis.com/v1\n    description: Google Cloud Data Catalog API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{GOOGLE_CLOUD_DATA_CATALOG_TOKEN}}'\n    resources:\n    - name: catalog-search\n      path: /catalog:search\n      operations:\n      - name: searchcatalog\n        method: POST\n        description: Google Cloud Data Catalog Search Data Catalog\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-entrygroup\n      path: /projects/{projectId}/locations/{location}/entryGroups\n      operations:\n      - name: listentrygroups\n        method: GET\n        description: Google Cloud Data Catalog List entry groups\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createentrygroup\n        method: POST\n        description: Google Cloud Data Catalog Create an entry group\n        inputParameters:\n\
  \        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-entrygroup\n      path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries\n      operations:\n      - name: listentries\n        method: GET\n        description: Google Cloud Data Catalog List entries\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: path\n          type: string\n   \
  \       required: true\n        - name: pageSize\n          in: query\n          type: integer\n        - name: pageToken\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createentry\n        method: POST\n        description: Google Cloud Data Catalog Create an entry\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: path\n          type: string\n          required: true\n        - name: entryId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-entrygroup\n\
  \      path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}\n      operations:\n      - name: getentry\n        method: GET\n        description: Google Cloud Data Catalog Get an entry\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: path\n          type: string\n          required: true\n        - name: entryId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateentry\n        method: PATCH\n        description: Google Cloud Data Catalog Update an entry\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n\
  \        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: path\n          type: string\n          required: true\n        - name: entryId\n          in: path\n          type: string\n          required: true\n        - name: updateMask\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteentry\n        method: DELETE\n        description: Google Cloud Data Catalog Delete an entry\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: entryGroupId\n          in: path\n          type: string\n          required: true\n        - name: entryId\n          in: path\n          type: string\n    \
  \      required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-tagtemplat\n      path: /projects/{projectId}/locations/{location}/tagTemplates\n      operations:\n      - name: createtagtemplate\n        method: POST\n        description: Google Cloud Data Catalog Create a tag template\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: tagTemplateId\n          in: query\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-projectid-locations-location-tagtemplat\n      path: /projects/{projectId}/locations/{location}/tagTemplates/{tagTemplateId}\n\
  \      operations:\n      - name: gettagtemplate\n        method: GET\n        description: Google Cloud Data Catalog Get a tag template\n        inputParameters:\n        - name: projectId\n          in: path\n          type: string\n          required: true\n        - name: location\n          in: path\n          type: string\n          required: true\n        - name: tagTemplateId\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: google-cloud-data-catalog-rest\n    description: REST adapter for Google Cloud Data Catalog API.\n    resources:\n    - path: /catalog:search\n      name: searchcatalog\n      operations:\n      - method: POST\n        name: searchcatalog\n        description: Google Cloud Data Catalog Search Data Catalog\n        call: google-cloud-data-catalog.searchcatalog\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups\n      name: listentrygroups\n      operations:\n      - method: GET\n        name: listentrygroups\n        description: Google Cloud Data Catalog List entry groups\n        call: google-cloud-data-catalog.listentrygroups\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups\n      name: createentrygroup\n      operations:\n      - method: POST\n        name: createentrygroup\n        description: Google Cloud Data Catalog Create an entry group\n        call: google-cloud-data-catalog.createentrygroup\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries\n\
  \      name: listentries\n      operations:\n      - method: GET\n        name: listentries\n        description: Google Cloud Data Catalog List entries\n        call: google-cloud-data-catalog.listentries\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          entryGroupId: rest.entryGroupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries\n      name: createentry\n      operations:\n      - method: POST\n        name: createentry\n        description: Google Cloud Data Catalog Create an entry\n        call: google-cloud-data-catalog.createentry\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          entryGroupId: rest.entryGroupId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}\n\
  \      name: getentry\n      operations:\n      - method: GET\n        name: getentry\n        description: Google Cloud Data Catalog Get an entry\n        call: google-cloud-data-catalog.getentry\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          entryGroupId: rest.entryGroupId\n          entryId: rest.entryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}\n      name: updateentry\n      operations:\n      - method: PATCH\n        name: updateentry\n        description: Google Cloud Data Catalog Update an entry\n        call: google-cloud-data-catalog.updateentry\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          entryGroupId: rest.entryGroupId\n          entryId: rest.entryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/entryGroups/{entryGroupId}/entries/{entryId}\n\
  \      name: deleteentry\n      operations:\n      - method: DELETE\n        name: deleteentry\n        description: Google Cloud Data Catalog Delete an entry\n        call: google-cloud-data-catalog.deleteentry\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          entryGroupId: rest.entryGroupId\n          entryId: rest.entryId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/tagTemplates\n      name: createtagtemplate\n      operations:\n      - method: POST\n        name: createtagtemplate\n        description: Google Cloud Data Catalog Create a tag template\n        call: google-cloud-data-catalog.createtagtemplate\n        with:\n          projectId: rest.projectId\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{projectId}/locations/{location}/tagTemplates/{tagTemplateId}\n\
  \      name: gettagtemplate\n      operations:\n      - method: GET\n        name: gettagtemplate\n        description: Google Cloud Data Catalog Get a tag template\n        call: google-cloud-data-catalog.gettagtemplate\n        with:\n          projectId: rest.projectId\n          location: rest.location\n          tagTemplateId: rest.tagTemplateId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: google-cloud-data-catalog-mcp\n    transport: http\n    description: MCP adapter for Google Cloud Data Catalog API for AI agent use.\n    tools:\n    - name: searchcatalog\n      description: Google Cloud Data Catalog Search Data Catalog\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-catalog.searchcatalog\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listentrygroups\n      description: Google Cloud Data Catalog\
  \ List entry groups\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-catalog.listentrygroups\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createentrygroup\n      description: Google Cloud Data Catalog Create an entry group\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-catalog.createentrygroup\n\
  \      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: entryGroupId\n        type: string\n        description: entryGroupId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listentries\n      description: Google Cloud Data Catalog List entries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-catalog.listentries\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n        pageSize: tools.pageSize\n        pageToken: tools.pageToken\n      inputParameters:\n      - name: projectId\n\
  \        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: entryGroupId\n        type: string\n        description: entryGroupId\n        required: true\n      - name: pageSize\n        type: integer\n        description: pageSize\n      - name: pageToken\n        type: string\n        description: pageToken\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createentry\n      description: Google Cloud Data Catalog Create an entry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-catalog.createentry\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n        entryId: tools.entryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n\
  \        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: entryGroupId\n        type: string\n        description: entryGroupId\n        required: true\n      - name: entryId\n        type: string\n        description: entryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getentry\n      description: Google Cloud Data Catalog Get an entry\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-catalog.getentry\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n        entryId: tools.entryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required:\
  \ true\n      - name: entryGroupId\n        type: string\n        description: entryGroupId\n        required: true\n      - name: entryId\n        type: string\n        description: entryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateentry\n      description: Google Cloud Data Catalog Update an entry\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-catalog.updateentry\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n        entryId: tools.entryId\n        updateMask: tools.updateMask\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: entryGroupId\n        type: string\n        description:\
  \ entryGroupId\n        required: true\n      - name: entryId\n        type: string\n        description: entryId\n        required: true\n      - name: updateMask\n        type: string\n        description: updateMask\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteentry\n      description: Google Cloud Data Catalog Delete an entry\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: google-cloud-data-catalog.deleteentry\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        entryGroupId: tools.entryGroupId\n        entryId: tools.entryId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: entryGroupId\n        type: string\n        description: entryGroupId\n        required:\
  \ true\n      - name: entryId\n        type: string\n        description: entryId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createtagtemplate\n      description: Google Cloud Data Catalog Create a tag template\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: google-cloud-data-catalog.createtagtemplate\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        tagTemplateId: tools.tagTemplateId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: tagTemplateId\n        type: string\n        description: tagTemplateId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: gettagtemplate\n      description:\
  \ Google Cloud Data Catalog Get a tag template\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: google-cloud-data-catalog.gettagtemplate\n      with:\n        projectId: tools.projectId\n        location: tools.location\n        tagTemplateId: tools.tagTemplateId\n      inputParameters:\n      - name: projectId\n        type: string\n        description: projectId\n        required: true\n      - name: location\n        type: string\n        description: location\n        required: true\n      - name: tagTemplateId\n        type: string\n        description: tagTemplateId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\nbinds:\n- namespace: env\n  keys:\n    GOOGLE_CLOUD_DATA_CATALOG_TOKEN: GOOGLE_CLOUD_DATA_CATALOG_TOKEN\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/google-cloud-data-catalog/refs/heads/main/capabilities/google-cloud-data-catalog-capability.yaml
tags:
- Google
- Cloud
- Data
- Catalog
- API
tools:
- description: Google Cloud Data Catalog Search Data Catalog
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: searchcatalog
- description: Google Cloud Data Catalog List entry groups
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentrygroups
- description: Google Cloud Data Catalog Create an entry group
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentrygroup
- description: Google Cloud Data Catalog List entries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listentries
- description: Google Cloud Data Catalog Create an entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createentry
- description: Google Cloud Data Catalog Get an entry
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getentry
- description: Google Cloud Data Catalog Update an entry
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateentry
- description: Google Cloud Data Catalog Delete an entry
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteentry
- description: Google Cloud Data Catalog Create a tag template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createtagtemplate
- description: Google Cloud Data Catalog Get a tag template
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettagtemplate
---
