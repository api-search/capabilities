---
categories: []
consumed_apis: []
description: Phrase Strings is a translation management platform for software projects. You can collaborate on language file translation with your team or order translations through our platform. The API allows you to import locale files, download locale files, tag keys or interact in other ways with the localization data stored in Phrase Strings for your account.
layout: capability
name: Phrase Strings API Reference
operations:
- description: Build ICU skeletons
  method: POST
  name: icu-skeleton
  path: /icu/skeleton
- description: List formats
  method: GET
  name: formats-list
  path: /formats
- description: List documents
  method: GET
  name: documents-list
  path: /projects/{project_id}/documents
- description: Delete document
  method: DELETE
  name: document-delete
  path: /projects/{project_id}/documents/{id}
- description: Get Project Report
  method: GET
  name: report-show
  path: /projects/{project_id}/report
- description: List Locale Reports
  method: GET
  name: report-locales-list
  path: /projects/{project_id}/report/locales
- description: List Figma attachments
  method: GET
  name: figma-attachments-list
  path: /projects/{project_id}/figma_attachments
- description: Create a Figma attachment
  method: POST
  name: figma-attachment-create
  path: /projects/{project_id}/figma_attachments
- description: Get a single Figma attachment
  method: GET
  name: figma-attachment-show
  path: /projects/{project_id}/figma_attachments/{id}
- description: Update a Figma attachment
  method: PATCH
  name: figma-attachment-update
  path: /projects/{project_id}/figma_attachments/{id}
- description: Delete a Figma attachment
  method: DELETE
  name: figma-attachment-delete
  path: /projects/{project_id}/figma_attachments/{id}
- description: Attach the Figma attachment to a key
  method: POST
  name: figma-attachment-attach-to-key
  path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys
- description: Detach the Figma attachment from a key
  method: DELETE
  name: figma-attachment-detach-from-key
  path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys/{id}
- description: List style guides
  method: GET
  name: styleguides-list
  path: /projects/{project_id}/styleguides
- description: Create a style guide
  method: POST
  name: styleguide-create
  path: /projects/{project_id}/styleguides
- description: Get a single style guide
  method: GET
  name: styleguide-show
  path: /projects/{project_id}/styleguides/{id}
- description: Update a style guide
  method: PATCH
  name: styleguide-update
  path: /projects/{project_id}/styleguides/{id}
- description: Delete a style guide
  method: DELETE
  name: styleguide-delete
  path: /projects/{project_id}/styleguides/{id}
- description: List properties
  method: GET
  name: custom-metadata-properties-list
  path: /accounts/{account_id}/custom_metadata/properties
- description: Create a property
  method: POST
  name: custom-metadata-property-create
  path: /accounts/{account_id}/custom_metadata/properties
- description: Get a single property
  method: GET
  name: custom-metadata-property-show
  path: /accounts/{account_id}/custom_metadata/properties/{id}
- description: Update a property
  method: PATCH
  name: custom-metadata-property-update
  path: /accounts/{account_id}/custom_metadata/properties/{id}
- description: Destroy property
  method: DELETE
  name: custom-metadata-properties-delete
  path: /accounts/{account_id}/custom_metadata/properties/{id}
- description: List invitations
  method: GET
  name: invitations-list
  path: /accounts/{account_id}/invitations
- description: Create a new invitation
  method: POST
  name: invitation-create
  path: /accounts/{account_id}/invitations
- description: Get a single invitation
  method: GET
  name: invitation-show
  path: /accounts/{account_id}/invitations/{id}
- description: Update an invitation
  method: PATCH
  name: invitation-update
  path: /accounts/{account_id}/invitations/{id}
- description: Delete an invitation
  method: DELETE
  name: invitation-delete
  path: /accounts/{account_id}/invitations/{id}
- description: Resend an invitation
  method: POST
  name: invitation-resend
  path: /accounts/{account_id}/invitations/{id}/resend
- description: Update a member's invitation access
  method: PATCH
  name: invitation-update-settings
  path: /projects/{project_id}/invitations/{id}
- description: List screenshot markers
  method: GET
  name: screenshot-markers-list
  path: /projects/{project_id}/screenshots/{id}/markers
- description: Get a single screenshot marker
  method: GET
  name: screenshot-marker-show
  path: /projects/{project_id}/screenshots/{screenshot_id}/markers/{id}
- description: Create a screenshot marker
  method: POST
  name: screenshot-marker-create
  path: /projects/{project_id}/screenshots/{screenshot_id}/markers
- description: Update a screenshot marker
  method: PATCH
  name: screenshot-marker-update
  path: /projects/{project_id}/screenshots/{screenshot_id}/markers
- description: Delete a screenshot marker
  method: DELETE
  name: screenshot-marker-delete
  path: /projects/{project_id}/screenshots/{screenshot_id}/markers
- description: List locales used in account
  method: GET
  name: account-locales
  path: /accounts/{id}/locales
- description: List locales
  method: GET
  name: locales-list
  path: /projects/{project_id}/locales
- description: Create a locale
  method: POST
  name: locale-create
  path: /projects/{project_id}/locales
- description: Get a single locale
  method: GET
  name: locale-show
  path: /projects/{project_id}/locales/{id}
- description: Update a locale
  method: PATCH
  name: locale-update
  path: /projects/{project_id}/locales/{id}
- description: Delete a locale
  method: DELETE
  name: locale-delete
  path: /projects/{project_id}/locales/{id}
- description: Download a locale
  method: GET
  name: locale-download
  path: /projects/{project_id}/locales/{id}/download
- description: Initiate async download of a locale
  method: POST
  name: locale-download-create
  path: /projects/{project_id}/locales/{locale_id}/downloads
- description: Show status of an async locale download
  method: GET
  name: locale-download-show
  path: /projects/{project_id}/locales/{locale_id}/downloads/{id}
- description: List distributions
  method: GET
  name: distributions-list
  path: /accounts/{account_id}/distributions
- description: Create a distribution
  method: POST
  name: distribution-create
  path: /accounts/{account_id}/distributions
- description: Get a single distribution
  method: GET
  name: distribution-show
  path: /accounts/{account_id}/distributions/{id}
- description: Update a distribution
  method: PATCH
  name: distribution-update
  path: /accounts/{account_id}/distributions/{id}
- description: Delete a distribution
  method: DELETE
  name: distribution-delete
  path: /accounts/{account_id}/distributions/{id}
- description: List releases
  method: GET
  name: releases-list
  path: /accounts/{account_id}/distributions/{distribution_id}/releases
- description: Create a release
  method: POST
  name: release-create
  path: /accounts/{account_id}/distributions/{distribution_id}/releases
- description: Get a single release
  method: GET
  name: release-show
  path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}
- description: Update a release
  method: PATCH
  name: release-update
  path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}
- description: Delete a release
  method: DELETE
  name: release-delete
  path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}
- description: Publish a release
  method: POST
  name: release-publish
  path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}/publish
- description: List release triggers
  method: GET
  name: release-triggers-list
  path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers
- description: Create a release trigger
  method: POST
  name: release-triggers-create
  path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers
- description: Get a single release trigger
  method: GET
  name: release-triggers-show
  path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers/{id}
- description: Update a release trigger
  method: PATCH
  name: release-triggers-update
  path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers/{id}
- description: Delete a single release trigger
  method: DELETE
  name: release-triggers-destroy
  path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers/{id}
personas: []
provider_name: Phrase
provider_slug: phrase
search_terms:
- custom metadata properties delete
- locale create
- create a new invitation
- locales list
- release triggers list
- list locale reports
- create a figma attachment
- list release triggers
- update a member's invitation access
- screenshot markers list
- distribution update
- invitation show
- invitation delete
- invitation create
- delete a distribution
- screenshot marker delete
- content management
- releases list
- update an invitation
- distribution show
- screenshot marker show
- get a single figma attachment
- delete a single release trigger
- release update
- list invitations
- api
- update a style guide
- release publish
- get a single distribution
- create a locale
- figma attachment detach from key
- document delete
- custom metadata property update
- internationalization
- invitation update
- get a single screenshot marker
- figma attachment update
- account locales
- release triggers create
- update a figma attachment
- delete a style guide
- delete document
- build icu skeletons
- create a distribution
- create a release
- invitation update settings
- styleguide update
- strings
- custom metadata properties list
- get a single invitation
- figma attachment attach to key
- detach the figma attachment from a key
- distribution create
- release create
- list locales
- update a release
- styleguide create
- styleguide show
- distributions list
- list figma attachments
- show status of an async locale download
- update a property
- translation
- custom metadata property create
- publish a release
- release triggers show
- delete a locale
- create a property
- get a single style guide
- locale show
- invitation resend
- create a release trigger
- styleguide delete
- figma attachment show
- attach the figma attachment to a key
- list properties
- locale delete
- list documents
- figma attachment delete
- release triggers update
- create a screenshot marker
- list screenshot markers
- get a single release
- report locales list
- get project report
- styleguides list
- phrase
- resend an invitation
- get a single property
- delete a release
- update a release trigger
- locale download create
- download a locale
- list style guides
- documents list
- destroy property
- invitations list
- formats list
- list releases
- locale download
- locale download show
- icu skeleton
- release delete
- update a screenshot marker
- list formats
- list locales used in account
- get a single release trigger
- release triggers destroy
- delete a figma attachment
- report show
- figma attachment create
- locale update
- update a locale
- delete an invitation
- screenshot marker update
- initiate async download of a locale
- distribution delete
- list distributions
- figma attachments list
- custom metadata property show
- delete a screenshot marker
- update a distribution
- create a style guide
- release show
- get a single locale
- screenshot marker create
- localization
slug: phrase-capability
source_filename: phrase-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Phrase Strings API Reference\n  description: Phrase Strings is a translation management platform for software projects. You can collaborate on language\n    file translation with your team or order translations through our platform. The API allows you to import locale files,\n    download locale files, tag keys or interact in other ways with the localization data stored in Phrase Strings for your\n    account.\n  tags:\n  - Phrase\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: phrase\n    baseUri: https://api.phrase.com/v2\n    description: Phrase Strings API Reference HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: Authorization\n      value: '{{PHRASE_TOKEN}}'\n    resources:\n    - name: icu-skeleton\n      path: /icu/skeleton\n      operations:\n      - name: icu-skeleton\n        method: POST\n        description: Build ICU skeletons\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: formats\n      path: /formats\n      operations:\n      - name: formats-list\n        method: GET\n        description: List formats\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-documents\n      path: /projects/{project_id}/documents\n      operations:\n      - name: documents-list\n        method: GET\n        description: List documents\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-documents-id\n      path: /projects/{project_id}/documents/{id}\n      operations:\n      - name: document-delete\n        method: DELETE\n        description: Delete document\n        outputRawFormat: json\n        outputParameters:\n        -\
  \ name: result\n          type: object\n          value: $.\n    - name: projects-project-id-report\n      path: /projects/{project_id}/report\n      operations:\n      - name: report-show\n        method: GET\n        description: Get Project Report\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-report-locales\n      path: /projects/{project_id}/report/locales\n      operations:\n      - name: report-locales-list\n        method: GET\n        description: List Locale Reports\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n    - name: projects-project-id-figma-attachments\n      path: /projects/{project_id}/figma_attachments\n      operations:\n      - name: figma-attachments-list\n        method: GET\n        description: List Figma attachments\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: figma-attachment-create\n        method: POST\n        description: Create a Figma attachment\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-figma-attachments-id\n      path: /projects/{project_id}/figma_attachments/{id}\n\
  \      operations:\n      - name: figma-attachment-show\n        method: GET\n        description: Get a single Figma attachment\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: figma-attachment-update\n        method: PATCH\n        description: Update a Figma attachment\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: figma-attachment-delete\n        method: DELETE\n        description: Delete a Figma attachment\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n         \
  \ description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-figma-attachments-figma-atta\n      path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys\n      operations:\n      - name: figma-attachment-attach-to-key\n        method: POST\n        description: Attach the Figma attachment to a key\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-figma-attachments-figma-atta\n      path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys/{id}\n      operations:\n      - name: figma-attachment-detach-from-key\n        method: DELETE\n        description: Detach the\
  \ Figma attachment from a key\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-styleguides\n      path: /projects/{project_id}/styleguides\n      operations:\n      - name: styleguides-list\n        method: GET\n        description: List style guides\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: styleguide-create\n        method: POST\n        description: Create a style guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-styleguides-id\n      path: /projects/{project_id}/styleguides/{id}\n      operations:\n      - name: styleguide-show\n\
  \        method: GET\n        description: Get a single style guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: styleguide-update\n        method: PATCH\n        description: Update a style guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: styleguide-delete\n        method: DELETE\n        description: Delete a style guide\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-custom-metadata-properties\n      path: /accounts/{account_id}/custom_metadata/properties\n      operations:\n      - name: custom-metadata-properties-list\n        method: GET\n        description: List properties\n        inputParameters:\n        - name: project_id\n          in: query\n          type: string\n   \
  \       description: id of project that the properties belong to\n        - name: q\n          in: query\n          type: string\n          description: query to find a property by name\n        - name: sort\n          in: query\n          type: string\n          description: 'Sort criteria. Can be one of: name, data_type, created_at.'\n        - name: order\n          in: query\n          type: string\n          description: 'Order direction. Can be one of: asc, desc.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: custom-metadata-property-create\n        method: POST\n        description: Create a property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-custom-metadata-properties-i\n      path: /accounts/{account_id}/custom_metadata/properties/{id}\n      operations:\n      - name:\
  \ custom-metadata-property-show\n        method: GET\n        description: Get a single property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: custom-metadata-property-update\n        method: PATCH\n        description: Update a property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: custom-metadata-properties-delete\n        method: DELETE\n        description: Destroy property\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-invitations\n      path: /accounts/{account_id}/invitations\n      operations:\n      - name: invitations-list\n        method: GET\n        description: List invitations\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: invitation-create\n        method: POST\n        description: Create a new invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-invitations-id\n      path: /accounts/{account_id}/invitations/{id}\n      operations:\n      - name: invitation-show\n        method: GET\n        description: Get a single invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invitation-update\n        method: PATCH\n        description: Update an invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: invitation-delete\n        method: DELETE\n        description: Delete an invitation\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: accounts-account-id-invitations-id-resend\n      path: /accounts/{account_id}/invitations/{id}/resend\n      operations:\n      - name: invitation-resend\n        method: POST\n        description: Resend an invitation\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-invitations-id\n      path: /projects/{project_id}/invitations/{id}\n      operations:\n      - name: invitation-update-settings\n        method: PATCH\n        description: Update a member's invitation access\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-screenshots-id-markers\n      path: /projects/{project_id}/screenshots/{id}/markers\n      operations:\n      - name: screenshot-markers-list\n        method: GET\n        description:\
  \ List screenshot markers\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-screenshots-screenshot-id-ma\n      path: /projects/{project_id}/screenshots/{screenshot_id}/markers/{id}\n      operations:\n      - name: screenshot-marker-show\n        method: GET\n        description: Get a single screenshot marker\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-screenshots-screenshot-id-ma\n      path: /projects/{project_id}/screenshots/{screenshot_id}/markers\n      operations:\n     \
  \ - name: screenshot-marker-create\n        method: POST\n        description: Create a screenshot marker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: screenshot-marker-update\n        method: PATCH\n        description: Update a screenshot marker\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: screenshot-marker-delete\n        method: DELETE\n        description: Delete a screenshot marker\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-id-locales\n      path: /accounts/{id}/locales\n      operations:\n      - name: account-locales\n        method: GET\n \
  \       description: List locales used in account\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-locales\n      path: /projects/{project_id}/locales\n      operations:\n      - name: locales-list\n        method: GET\n        description: List locales\n        inputParameters:\n        - name: sort_by\n          in: query\n          type: string\n          description: Sort locales. Valid options are \"name_asc\", \"name_desc\", \"default_asc\", \"default_desc\".\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: locale-create\n        method: POST\n        description: Create a locale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: projects-project-id-locales-id\n      path: /projects/{project_id}/locales/{id}\n      operations:\n      - name: locale-show\n        method: GET\n        description: Get a single locale\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: locale-update\n        method: PATCH\n        description: Update a locale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: locale-delete\n        method: DELETE\n        description: Delete a locale\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-locales-id-download\n      path: /projects/{project_id}/locales/{id}/download\n      operations:\n      - name: locale-download\n        method: GET\n        description: Download a locale\n        inputParameters:\n        - name: branch\n          in: query\n          type: string\n          description: specify the branch to use\n        - name: file_format\n          in: query\n          type: string\n          description: File format name. See the [format guide](https://support.phrase.com/hc/en-us/sections/6111343326364)\n            for all supported file formats.\n        - name: tags\n          in: query\n          type: string\n          description: Limit results to keys tagged with a list of comma separated tag names.\n        - name: tag\n          in: query\n          type: string\n          description: Limit download to tagged keys. This parameter\
  \ is deprecated. Please use the \"tags\" parameter instead\n        - name: include_empty_translations\n          in: query\n          type: boolean\n          description: Indicates whether keys without translations should be included in the output as well.\n        - name: exclude_empty_zero_forms\n          in: query\n          type: boolean\n          description: Indicates whether zero forms should be included when empty in pluralized keys.\n        - name: include_translated_keys\n          in: query\n          type: boolean\n          description: Include translated keys in the locale file. Use in combination with include_empty_translations to obtain\n            only untranslated keys.\n        - name: keep_notranslate_tags\n          in: query\n          type: boolean\n          description: Indicates whether [NOTRANSLATE] tags should be kept.\n        - name: convert_emoji\n          in: query\n          type: boolean\n          description: 'This option is obsolete. Projects\
  \ that were created on or after Nov 29th 2019 or that did not contain\n            emoji by then will not require this flag any longer since '\n        - name: format_options\n          in: query\n          type: object\n          description: Additional formatting and render options. See the [format guide](https://support.phrase.com/hc/en-us/sections/6111343326364)\n            for a list of options available for\n        - name: encoding\n          in: query\n          type: string\n          description: Enforces a specific encoding on the file contents. Valid options are \"UTF-8\", \"UTF-16\" and \"ISO-8859-1\".\n        - name: skip_unverified_translations\n          in: query\n          type: boolean\n          description: Indicates whether the locale file should skip all unverified translations. This parameter is deprecated\n            and should be replaced with `include_unverified_translat\n        - name: include_unverified_translations\n          in: query\n          type:\
  \ boolean\n          description: if set to false unverified translations are excluded\n        - name: use_last_reviewed_version\n          in: query\n          type: boolean\n          description: If set to true the last reviewed version of a translation is used. This is only available if the review\n            workflow is enabled for the project.\n        - name: fallback_locale_id\n          in: query\n          type: string\n          description: If a key has no translation in the locale being downloaded, the translation in the fallback locale\n            will be used. Provide the ID of the locale that should be use\n        - name: use_locale_fallback\n          in: query\n          type: boolean\n          description: If a key has no translation in the locale being downloaded, the translation in the fallback locale\n            will be used. Fallback locale is defined in [locale's setting\n        - name: source_locale_id\n          in: query\n          type: string\n     \
  \     description: Provides the source language of a corresponding job as the source language of the generated locale\n            file. This parameter will be ignored unless used in combinati\n        - name: translation_key_prefix\n          in: query\n          type: string\n          description: 'Download all translation keys, and remove the specified prefix where possible. Warning: this may create\n            duplicate key names if other keys share the same name af'\n        - name: filter_by_prefix\n          in: query\n          type: boolean\n          description: Only download translation keys containing the specified prefix, and remove the prefix from the generated\n            file.\n        - name: custom_metadata_filters\n          in: query\n          type: object\n          description: Custom metadata filters. Provide the name of the metadata field and the value to filter by. Only keys\n            with matching metadata will be included in the download.\n        - name:\
  \ locale_ids\n          in: query\n          type: array\n          description: Locale IDs or locale names\n        - name: updated_since\n          in: query\n          type: string\n          description: Only include translations and keys that have been updated since the given date. The date must be in\n            ISO 8601 format (e.g., `2023-01-01T00:00:00Z`).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-locales-locale-id-downloads\n      path: /projects/{project_id}/locales/{locale_id}/downloads\n      operations:\n      - name: locale-download-create\n        method: POST\n        description: Initiate async download of a locale\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: projects-project-id-locales-locale-id-downloads-\n      path: /projects/{project_id}/locales/{locale_id}/downloads/{id}\n\
  \      operations:\n      - name: locale-download-show\n        method: GET\n        description: Show status of an async locale download\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions\n      path: /accounts/{account_id}/distributions\n      operations:\n      - name: distributions-list\n        method: GET\n        description: List distributions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: distribution-create\n        method: POST\n        description: Create a distribution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-id\n      path: /accounts/{account_id}/distributions/{id}\n      operations:\n      - name: distribution-show\n        method:\
  \ GET\n        description: Get a single distribution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: distribution-update\n        method: PATCH\n        description: Update a distribution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: distribution-delete\n        method: DELETE\n        description: Delete a distribution\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-distribution-i\n      path: /accounts/{account_id}/distributions/{distribution_id}/releases\n      operations:\n      - name: releases-list\n        method: GET\n        description: List releases\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: release-create\n        method: POST\n        description: Create a release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-distribution-i\n      path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}\n      operations:\n      - name: release-show\n        method: GET\n        description: Get a single release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-update\n        method: PATCH\n        description: Update a release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-delete\n        method: DELETE\n        description: Delete a release\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-distribution-i\n      path: /accounts/{account_id}/distributions/{distribution_id}/releases/{id}/publish\n      operations:\n      - name: release-publish\n        method: POST\n        description: Publish a release\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-distribution-i\n      path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers\n      operations:\n      - name: release-triggers-list\n        method: GET\n        description: List release triggers\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-triggers-create\n        method: POST\n        description: Create a release trigger\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: accounts-account-id-distributions-distribution-i\n      path: /accounts/{account_id}/distributions/{distribution_id}/release_triggers/{id}\n      operations:\n      - name: release-triggers-show\n        method: GET\n        description: Get a single release trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-triggers-update\n        method: PATCH\n        description: Update a release trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: release-triggers-destroy\n        method: DELETE\n        description: Delete a single release trigger\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n\
  \    namespace: phrase-rest\n    description: REST adapter for Phrase Strings API Reference.\n    resources:\n    - path: /icu/skeleton\n      name: icu-skeleton\n      operations:\n      - method: POST\n        name: icu-skeleton\n        description: Build ICU skeletons\n        call: phrase.icu-skeleton\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /formats\n      name: formats-list\n      operations:\n      - method: GET\n        name: formats-list\n        description: List formats\n        call: phrase.formats-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/documents\n      name: documents-list\n      operations:\n      - method: GET\n        name: documents-list\n        description: List documents\n        call: phrase.documents-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/documents/{id}\n      name: document-delete\n\
  \      operations:\n      - method: DELETE\n        name: document-delete\n        description: Delete document\n        call: phrase.document-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/report\n      name: report-show\n      operations:\n      - method: GET\n        name: report-show\n        description: Get Project Report\n        call: phrase.report-show\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/report/locales\n      name: report-locales-list\n      operations:\n      - method: GET\n        name: report-locales-list\n        description: List Locale Reports\n        call: phrase.report-locales-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments\n      name: figma-attachments-list\n      operations:\n      - method: GET\n        name: figma-attachments-list\n     \
  \   description: List Figma attachments\n        call: phrase.figma-attachments-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments\n      name: figma-attachment-create\n      operations:\n      - method: POST\n        name: figma-attachment-create\n        description: Create a Figma attachment\n        call: phrase.figma-attachment-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments/{id}\n      name: figma-attachment-show\n      operations:\n      - method: GET\n        name: figma-attachment-show\n        description: Get a single Figma attachment\n        call: phrase.figma-attachment-show\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments/{id}\n      name: figma-attachment-update\n      operations:\n      - method: PATCH\n        name: figma-attachment-update\n\
  \        description: Update a Figma attachment\n        call: phrase.figma-attachment-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments/{id}\n      name: figma-attachment-delete\n      operations:\n      - method: DELETE\n        name: figma-attachment-delete\n        description: Delete a Figma attachment\n        call: phrase.figma-attachment-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys\n      name: figma-attachment-attach-to-key\n      operations:\n      - method: POST\n        name: figma-attachment-attach-to-key\n        description: Attach the Figma attachment to a key\n        call: phrase.figma-attachment-attach-to-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/figma_attachments/{figma_attachment_id}/keys/{id}\n\
  \      name: figma-attachment-detach-from-key\n      operations:\n      - method: DELETE\n        name: figma-attachment-detach-from-key\n        description: Detach the Figma attachment from a key\n        call: phrase.figma-attachment-detach-from-key\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/styleguides\n      name: styleguides-list\n      operations:\n      - method: GET\n        name: styleguides-list\n        description: List style guides\n        call: phrase.styleguides-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/styleguides\n      name: styleguide-create\n      operations:\n      - method: POST\n        name: styleguide-create\n        description: Create a style guide\n        call: phrase.styleguide-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/styleguides/{id}\n     \
  \ name: styleguide-show\n      operations:\n      - method: GET\n        name: styleguide-show\n        description: Get a single style guide\n        call: phrase.styleguide-show\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/styleguides/{id}\n      name: styleguide-update\n      operations:\n      - method: PATCH\n        name: styleguide-update\n        description: Update a style guide\n        call: phrase.styleguide-update\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /projects/{project_id}/styleguides/{id}\n      name: styleguide-delete\n      operations:\n      - method: DELETE\n        name: styleguide-delete\n        description: Delete a style guide\n        call: phrase.styleguide-delete\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{account_id}/custom_metadata/properties\n      name: custom-metadata-properties-list\n   \
  \   operations:\n      - method: GET\n        name: custom-metadata-properties-list\n        description: List properties\n        call: phrase.custom-metadata-properties-list\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{account_id}/custom_metadata/properties\n      name: custom-metadata-property-create\n      operations:\n      - method: POST\n        name: custom-metadata-property-create\n        description: Create a property\n        call: phrase.custom-metadata-property-create\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /accounts/{account_id}/custom_metadata/properties/{id}\n      name: custom-metadata-property-show\n      operations\n\n# --- truncated at 32 KB (68 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/phrase/refs/heads/main/capabilities/phrase-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/phrase/refs/heads/main/capabilities/phrase-capability.yaml
tags:
- Phrase
- API
tools:
- description: Build ICU skeletons
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: icu-skeleton
- description: List formats
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: formats-list
- description: List documents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: documents-list
- description: Delete document
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: document-delete
- description: Get Project Report
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: report-show
- description: List Locale Reports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: report-locales-list
- description: List Figma attachments
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: figma-attachments-list
- description: Create a Figma attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: figma-attachment-create
- description: Get a single Figma attachment
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: figma-attachment-show
- description: Update a Figma attachment
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: figma-attachment-update
- description: Delete a Figma attachment
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: figma-attachment-delete
- description: Attach the Figma attachment to a key
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: figma-attachment-attach-to-key
- description: Detach the Figma attachment from a key
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: figma-attachment-detach-from-key
- description: List style guides
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: styleguides-list
- description: Create a style guide
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: styleguide-create
- description: Get a single style guide
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: styleguide-show
- description: Update a style guide
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: styleguide-update
- description: Delete a style guide
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: styleguide-delete
- description: List properties
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: custom-metadata-properties-list
- description: Create a property
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: custom-metadata-property-create
- description: Get a single property
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: custom-metadata-property-show
- description: Update a property
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: custom-metadata-property-update
- description: Destroy property
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: custom-metadata-properties-delete
- description: List invitations
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invitations-list
- description: Create a new invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitation-create
- description: Get a single invitation
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: invitation-show
- description: Update an invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitation-update
- description: Delete an invitation
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: invitation-delete
- description: Resend an invitation
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitation-resend
- description: Update a member's invitation access
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: invitation-update-settings
- description: List screenshot markers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: screenshot-markers-list
- description: Get a single screenshot marker
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: screenshot-marker-show
- description: Create a screenshot marker
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screenshot-marker-create
- description: Update a screenshot marker
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: screenshot-marker-update
- description: Delete a screenshot marker
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: screenshot-marker-delete
- description: List locales used in account
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: account-locales
- description: List locales
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locales-list
- description: Create a locale
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: locale-create
- description: Get a single locale
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locale-show
- description: Update a locale
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: locale-update
- description: Delete a locale
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: locale-delete
- description: Download a locale
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locale-download
- description: Initiate async download of a locale
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: locale-download-create
- description: Show status of an async locale download
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: locale-download-show
- description: List distributions
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: distributions-list
- description: Create a distribution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: distribution-create
- description: Get a single distribution
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: distribution-show
- description: Update a distribution
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: distribution-update
- description: Delete a distribution
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: distribution-delete
- description: List releases
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: releases-list
- description: Create a release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: release-create
- description: Get a single release
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: release-show
- description: Update a release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: release-update
- description: Delete a release
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: release-delete
- description: Publish a release
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: release-publish
- description: List release triggers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: release-triggers-list
- description: Create a release trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: release-triggers-create
- description: Get a single release trigger
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: release-triggers-show
- description: Update a release trigger
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: release-triggers-update
- description: Delete a single release trigger
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: release-triggers-destroy
---
