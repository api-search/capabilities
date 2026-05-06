---
categories: []
consumed_apis: []
description: Marketo exposes a REST API which allows for remote execution of many of the systems capabilities. From creating programs to bulk lead import, there are many options which allow fine-grained control of a Marketo instance.
layout: capability
name: Marketo Engage Rest API
operations:
- description: Marketo Get Channel by Name
  method: GET
  name: getchannelbynameusingget
  path: /rest/asset/v1/channel/byName.json
- description: Marketo Get Channels
  method: GET
  name: getallchannelsusingget
  path: /rest/asset/v1/channels.json
- description: Marketo Get Email by Name
  method: GET
  name: getemailbynameusingget
  path: /rest/asset/v1/email/byName.json
- description: Marketo Get Email By Id
  method: GET
  name: getemailbyidusingget
  path: /rest/asset/v1/email/{id}.json
- description: Marketo Update Email Metadata
  method: POST
  name: updateemailusingpost
  path: /rest/asset/v1/email/{id}.json
- description: Marketo Approve Email Draft
  method: POST
  name: approvedraftusingpost
  path: /rest/asset/v1/email/{id}/approveDraft.json
- description: Marketo Clone Email
  method: POST
  name: cloneemailusingpost
  path: /rest/asset/v1/email/{id}/clone.json
- description: Marketo Get Email Content
  method: GET
  name: getemailcontentbyidusingget
  path: /rest/asset/v1/email/{id}/content.json
- description: Marketo Update Email Content
  method: POST
  name: updateemailcontentusingpost
  path: /rest/asset/v1/email/{id}/content.json
- description: Marketo Rearrange Email Modules
  method: POST
  name: rearrangemodulesusingpost
  path: /rest/asset/v1/email/{id}/content/rearrange.json
- description: Marketo Update Email Content Section
  method: POST
  name: updateemailcomponentcontentusingpost
  path: /rest/asset/v1/email/{id}/content/{htmlId}.json
- description: Marketo Add Email Module
  method: POST
  name: addmoduleusingpost
  path: /rest/asset/v1/email/{id}/content/{moduleId}/add.json
- description: Marketo Delete Module
  method: POST
  name: deletemoduleusingpost
  path: /rest/asset/v1/email/{id}/content/{moduleId}/delete.json
- description: Marketo Duplicate Email Module
  method: POST
  name: duplicatemoduleusingpost
  path: /rest/asset/v1/email/{id}/content/{moduleId}/duplicate.json
- description: Marketo Rename Email Module
  method: POST
  name: renameusingpost
  path: /rest/asset/v1/email/{id}/content/{moduleId}/rename.json
- description: Marketo Delete Email
  method: POST
  name: deleteemailusingpost
  path: /rest/asset/v1/email/{id}/delete.json
- description: Marketo Discard Email Draft
  method: POST
  name: discarddraftusingpost
  path: /rest/asset/v1/email/{id}/discardDraft.json
- description: Marketo Get Email Dynamic Content
  method: GET
  name: getemaildynamiccontentusingget
  path: /rest/asset/v1/email/{id}/dynamicContent/{contentId}.json
- description: Marketo Update Email Dynamic Content Section
  method: POST
  name: updateemaildynamiccontentusingpost
  path: /rest/asset/v1/email/{id}/dynamicContent/{contentId}.json
- description: Marketo Send Sample Email
  method: POST
  name: sendsampleemailusingpost
  path: /rest/asset/v1/email/{id}/sendSample.json
- description: Marketo Unapprove Email
  method: POST
  name: unapprovedraftusingpost
  path: /rest/asset/v1/email/{id}/unapprove.json
- description: Marketo Update Email Variable
  method: POST
  name: updatevariableusingpost
  path: /rest/asset/v1/email/{id}/variable/{name}.json
- description: Marketo Get Email Variables
  method: GET
  name: getemailvariablesusingget
  path: /rest/asset/v1/email/{id}/variables.json
- description: Marketo Get Email CC Fields
  method: GET
  name: getemailccfieldsusingget
  path: /rest/asset/v1/email/ccFields.json
- description: Marketo Get Email Template by Name
  method: GET
  name: gettemplatebynameusingget
  path: /rest/asset/v1/emailTemplate/byName.json
- description: Marketo Get Email Template by Id
  method: GET
  name: gettemplatebyidusingget
  path: /rest/asset/v1/emailTemplate/{id}.json
- description: Marketo Update Email Template Metadata
  method: POST
  name: updateemailtemplateusingpost
  path: /rest/asset/v1/emailTemplate/{id}.json
- description: Marketo Approve Email Template Draft
  method: POST
  name: approvedraftusingpost-1
  path: /rest/asset/v1/emailTemplate/{id}/approveDraft.json
- description: Marketo Clone Email Template
  method: POST
  name: clonetemplateusingpost
  path: /rest/asset/v1/emailTemplate/{id}/clone.json
- description: Marketo Get Email Template Content by Id
  method: GET
  name: gettemplatecontentbyidusingget
  path: /rest/asset/v1/emailTemplate/{id}/content
- description: Marketo Update Email Template Content
  method: POST
  name: updateemailtemplatecontentusingpost
  path: /rest/asset/v1/emailTemplate/{id}/content.json
- description: Marketo Delete Email Template
  method: POST
  name: deletetemplateusingpost
  path: /rest/asset/v1/emailTemplate/{id}/delete.json
- description: Marketo Discard Email Template Draft
  method: POST
  name: discarddraftusingpost-1
  path: /rest/asset/v1/emailTemplate/{id}/discardDraft.json
- description: Marketo Unapprove Email Template Draft
  method: POST
  name: unapprovedraftusingpost-1
  path: /rest/asset/v1/emailTemplate/{id}/unapprove.json
- description: Marketo Get Email Templates
  method: GET
  name: getemailtemplatesusingget
  path: /rest/asset/v1/emailTemplates.json
- description: Marketo Create Email Template
  method: POST
  name: createemailtemplateusingpost
  path: /rest/asset/v1/emailTemplates.json
- description: Marketo Get Email Template Used By
  method: GET
  name: getemailtemplateusedbyusingget
  path: /rest/asset/v1/emailTemplates/{id}/usedBy.json
- description: Marketo Get Emails
  method: GET
  name: getemailusingget
  path: /rest/asset/v1/emails.json
- description: Marketo Create Email
  method: POST
  name: createemailusingpost
  path: /rest/asset/v1/emails.json
- description: Marketo Get Email Full Content
  method: GET
  name: getemailfullcontentusingget
  path: /rest/asset/v1/email/{id}/fullContent.json
- description: Marketo Update Email Full Content
  method: POST
  name: createemailfullcontentusingpost
  path: /rest/asset/v1/email/{id}/fullContent.json
- description: Marketo Get File by Name
  method: GET
  name: getfilebynameusingget
  path: /rest/asset/v1/file/byName.json
- description: Marketo Get File by Id
  method: GET
  name: getfilebyidusingget
  path: /rest/asset/v1/file/{id}.json
- description: Marketo Update File Content
  method: POST
  name: updatecontentusingpost
  path: /rest/asset/v1/file/{id}/content.json
- description: Marketo Get Files
  method: GET
  name: getfilesusingget
  path: /rest/asset/v1/files.json
- description: Marketo Create File
  method: POST
  name: createfileusingpost
  path: /rest/asset/v1/files.json
- description: Marketo Get Folder by Name
  method: GET
  name: getfolderbynameusingget
  path: /rest/asset/v1/folder/byName.json
- description: Marketo Get Folder by Id
  method: GET
  name: getfolderbyidusingget
  path: /rest/asset/v1/folder/{id}.json
- description: Marketo Update Folder Metadata
  method: POST
  name: updatefolderusingpost
  path: /rest/asset/v1/folder/{id}.json
- description: Marketo Get Folder Contents
  method: GET
  name: getfoldercontentusingget
  path: /rest/asset/v1/folder/{id}/content.json
- description: Marketo Delete Folder
  method: POST
  name: deletefolderusingpost
  path: /rest/asset/v1/folder/{id}/delete.json
- description: Marketo Get Tokens by Folder Id
  method: GET
  name: gettokensbyfolderidusingget
  path: /rest/asset/v1/folder/{id}/tokens.json
- description: Marketo Create Token
  method: POST
  name: addtokentofolderusingpost
  path: /rest/asset/v1/folder/{id}/tokens.json
- description: Marketo Delete Token by Name
  method: POST
  name: deletetokenbynameusingpost
  path: /rest/asset/v1/folder/{id}/tokens/delete.json
- description: Marketo Get Folders
  method: GET
  name: getfolderusingget
  path: /rest/asset/v1/folders.json
- description: Marketo Create Folder
  method: POST
  name: createfolderusingpost
  path: /rest/asset/v1/folders.json
- description: Marketo Get Form by Name
  method: GET
  name: getlpformbynameusingget
  path: /rest/asset/v1/form/byName.json
- description: Marketo Get Available Form Fields
  method: GET
  name: getallfieldsusingget
  path: /rest/asset/v1/form/fields.json
- description: Marketo Get Available Form Program Member Fields
  method: GET
  name: getallprogrammemberfieldsusingget
  path: /rest/asset/v1/form/programMemberFields.json
- description: Marketo Add Form Field Visibility Rules
  method: POST
  name: addformfieldvisibilityruleusingpost
  path: /rest/asset/v1/form/{formId}/field/{fieldId}/visibility.json
personas: []
provider_name: Marketo
provider_slug: marketo
search_terms:
- getfilesusingget
- marketo get email template used by
- marketo update email content section
- marketo delete module
- marketo get folder contents
- marketo update email metadata
- unapprovedraftusingpost 1
- discarddraftusingpost
- createemailfullcontentusingpost
- marketo create email template
- updateemailtemplateusingpost
- api
- marketo unapprove email template draft
- marketo delete folder
- unapprovedraftusingpost
- marketo approve email template draft
- getchannelbynameusingget
- createemailtemplateusingpost
- marketo unapprove email
- marketo discard email template draft
- marketo get email content
- marketo delete email template
- addtokentofolderusingpost
- marketo get email template content by id
- automation
- getemaildynamiccontentusingget
- marketo clone email template
- getemailbynameusingget
- createfolderusingpost
- marketo update email content
- marketo get email by name
- marketo add form field visibility rules
- marketo create token
- marketo delete token by name
- getlpformbynameusingget
- marketo get email cc fields
- updateemailtemplatecontentusingpost
- renameusingpost
- getallfieldsusingget
- getemailbyidusingget
- deletetemplateusingpost
- getemailtemplatesusingget
- rearrangemodulesusingpost
- marketo update email full content
- getemailccfieldsusingget
- getfolderbyidusingget
- deletemoduleusingpost
- getfoldercontentusingget
- marketo get available form program member fields
- updateemailcomponentcontentusingpost
- marketing automation
- marketo get file by name
- marketo get channels
- marketo discard email draft
- marketo clone email
- updateemailusingpost
- getallchannelsusingget
- marketo
- marketo get files
- marketo update email dynamic content section
- marketo add email module
- marketo get email template by id
- getfolderbynameusingget
- marketo get channel by name
- createfileusingpost
- marketo rearrange email modules
- updatevariableusingpost
- getfilebyidusingget
- marketo get email full content
- marketo delete email
- updateemailcontentusingpost
- marketo get email template by name
- marketo get email templates
- updateemaildynamiccontentusingpost
- gettemplatebynameusingget
- marketo get email by id
- addformfieldvisibilityruleusingpost
- createemailusingpost
- marketo create folder
- approvedraftusingpost
- marketo get email dynamic content
- marketo update email template metadata
- gettemplatebyidusingget
- adobe
- marketo get emails
- marketo get form by name
- getemailvariablesusingget
- getfolderusingget
- cloneemailusingpost
- marketo create email
- marketo send sample email
- updatecontentusingpost
- gettokensbyfolderidusingget
- marketo get email variables
- gettemplatecontentbyidusingget
- marketo get folder by id
- getemailcontentbyidusingget
- marketo update email variable
- deleteemailusingpost
- approvedraftusingpost 1
- marketing
- clonetemplateusingpost
- deletetokenbynameusingpost
- marketo get file by id
- marketo create file
- deletefolderusingpost
- marketo get folders
- getallprogrammemberfieldsusingget
- marketo update email template content
- marketo approve email draft
- getemailfullcontentusingget
- marketo get tokens by folder id
- updatefolderusingpost
- getemailusingget
- marketo get folder by name
- marketo get available form fields
- marketo update folder metadata
- marketo update file content
- duplicatemoduleusingpost
- addmoduleusingpost
- marketo rename email module
- discarddraftusingpost 1
- marketo duplicate email module
- sendsampleemailusingpost
- getfilebynameusingget
- getemailtemplateusedbyusingget
slug: marketo-capability
source_filename: marketo-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Marketo Engage Rest API\n  description: Marketo exposes a REST API which allows for remote execution of many of the systems capabilities. From creating\n    programs to bulk lead import, there are many options which allow fine-grained control of a Marketo instance.\n  tags:\n  - Marketo\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: marketo\n    baseUri: https://localhost:8080\n    description: Marketo Engage Rest API HTTP API.\n    resources:\n    - name: rest-asset-v1-channel-byname-json\n      path: /rest/asset/v1/channel/byName.json\n      operations:\n      - name: getchannelbynameusingget\n        method: GET\n        description: Marketo Get Channel by Name\n        inputParameters:\n        - name: Name\n          in: query\n          type: string\n          required: true\n          description: Name of channel to retrieve\n        outputRawFormat: json\n \
  \       outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-channels-json\n      path: /rest/asset/v1/channels.json\n      operations:\n      - name: getallchannelsusingget\n        method: GET\n        description: Marketo Get Channels\n        inputParameters:\n        - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of channels to return. Max 200, default 20\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-byname-json\n      path: /rest/asset/v1/email/byName.json\n      operations:\n      - name: getemailbynameusingget\n        method: GET\n        description: Marketo Get Email by Name\n        inputParameters:\n        - name: name\n      \
  \    in: query\n          type: string\n          required: true\n          description: Name of the email\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions\n        - name: folder\n          in: query\n          type: string\n          description: JSON representation of parent folder, with members 'id', and 'type' which may be 'Folder' or 'Program'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-json\n      path: /rest/asset/v1/email/{id}.json\n      operations:\n      - name: getemailbyidusingget\n        method: GET\n        description: Marketo Get Email By Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: status\n          in: query\n          type: string\n          description:\
  \ Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateemailusingpost\n        method: POST\n        description: Marketo Update Email Metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-approvedraft-json\n      path: /rest/asset/v1/email/{id}/approveDraft.json\n      operations:\n      - name: approvedraftusingpost\n        method: POST\n        description: Marketo Approve Email Draft\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-clone-json\n      path: /rest/asset/v1/email/{id}/clone.json\n      operations:\n      - name: cloneemailusingpost\n        method: POST\n        description: Marketo Clone Email\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-json\n      path: /rest/asset/v1/email/{id}/content.json\n      operations:\n      - name: getemailcontentbyidusingget\n        method: GET\n        description: Marketo Get Email Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: status\n          in: query\n          type: string\n\
  \          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateemailcontentusingpost\n        method: POST\n        description: Marketo Update Email Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-rearrange-json\n      path: /rest/asset/v1/email/{id}/content/rearrange.json\n      operations:\n      - name: rearrangemodulesusingpost\n        method: POST\n        description: Marketo Rearrange Email Modules\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-htmlid-json\n      path: /rest/asset/v1/email/{id}/content/{htmlId}.json\n      operations:\n      - name: updateemailcomponentcontentusingpost\n        method: POST\n        description: Marketo Update Email Content Section\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: htmlId\n          in: path\n          type: string\n          required: true\n          description: htmlId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-moduleid-add-json\n      path: /rest/asset/v1/email/{id}/content/{moduleId}/add.json\n      operations:\n      - name: addmoduleusingpost\n        method: POST\n        description: Marketo\
  \ Add Email Module\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: moduleId\n          in: path\n          type: string\n          required: true\n          description: moduleId\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Name of the module\n        - name: index\n          in: query\n          type: integer\n          required: true\n          description: Index of the module. Determines the order of the module in the email.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-moduleid-delete-j\n      path: /rest/asset/v1/email/{id}/content/{moduleId}/delete.json\n      operations:\n      - name: deletemoduleusingpost\n        method: POST\n        description: Marketo Delete Module\n\
  \        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: moduleId\n          in: path\n          type: string\n          required: true\n          description: moduleId\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-moduleid-duplicat\n      path: /rest/asset/v1/email/{id}/content/{moduleId}/duplicate.json\n      operations:\n      - name: duplicatemoduleusingpost\n        method: POST\n        description: Marketo Duplicate Email Module\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: moduleId\n          in: path\n          type: string\n          required: true\n          description: moduleId\n        - name: name\n          in: query\n          type:\
  \ string\n          required: true\n          description: Name of the new module\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-content-moduleid-rename-j\n      path: /rest/asset/v1/email/{id}/content/{moduleId}/rename.json\n      operations:\n      - name: renameusingpost\n        method: POST\n        description: Marketo Rename Email Module\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: moduleId\n          in: path\n          type: string\n          required: true\n          description: moduleId\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: New module name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  \
  \  - name: rest-asset-v1-email-id-delete-json\n      path: /rest/asset/v1/email/{id}/delete.json\n      operations:\n      - name: deleteemailusingpost\n        method: POST\n        description: Marketo Delete Email\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-discarddraft-json\n      path: /rest/asset/v1/email/{id}/discardDraft.json\n      operations:\n      - name: discarddraftusingpost\n        method: POST\n        description: Marketo Discard Email Draft\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: rest-asset-v1-email-id-dynamiccontent-contentid-\n      path: /rest/asset/v1/email/{id}/dynamicContent/{contentId}.json\n      operations:\n      - name: getemaildynamiccontentusingget\n        method: GET\n        description: Marketo Get Email Dynamic Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of email\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Id of email dynamic content section\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateemaildynamiccontentusingpost\n        method: POST\n        description: Marketo Update Email Dynamic Content Section\n        inputParameters:\n\
  \        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of email\n        - name: contentId\n          in: path\n          type: string\n          required: true\n          description: Id of email dynamic content section\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-sendsample-json\n      path: /rest/asset/v1/email/{id}/sendSample.json\n      operations:\n      - name: sendsampleemailusingpost\n        method: POST\n        description: Marketo Send Sample Email\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-unapprove-json\n      path: /rest/asset/v1/email/{id}/unapprove.json\n\
  \      operations:\n      - name: unapprovedraftusingpost\n        method: POST\n        description: Marketo Unapprove Email\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-id-variable-name-json\n      path: /rest/asset/v1/email/{id}/variable/{name}.json\n      operations:\n      - name: updatevariableusingpost\n        method: POST\n        description: Marketo Update Email Variable\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: name\n          in: path\n          type: string\n          required: true\n          description: name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n       \
  \   type: object\n          value: $.\n    - name: rest-asset-v1-email-id-variables-json\n      path: /rest/asset/v1/email/{id}/variables.json\n      operations:\n      - name: getemailvariablesusingget\n        method: GET\n        description: Marketo Get Email Variables\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-email-ccfields-json\n      path: /rest/asset/v1/email/ccFields.json\n      operations:\n      - name: getemailccfieldsusingget\n        method: GET\n        description: Marketo Get Email CC Fields\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-byname-json\n      path: /rest/asset/v1/emailTemplate/byName.json\n\
  \      operations:\n      - name: gettemplatebynameusingget\n        method: GET\n        description: Marketo Get Email Template by Name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: name\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-json\n      path: /rest/asset/v1/emailTemplate/{id}.json\n      operations:\n      - name: gettemplatebyidusingget\n        method: GET\n        description: Marketo Get Email Template by Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: status\n          in: query\n          type: string\n\
  \          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateemailtemplateusingpost\n        method: POST\n        description: Marketo Update Email Template Metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-approvedraft-json\n      path: /rest/asset/v1/emailTemplate/{id}/approveDraft.json\n      operations:\n      - name: approvedraftusingpost-1\n        method: POST\n        description: Marketo Approve Email Template Draft\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description:\
  \ id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-clone-json\n      path: /rest/asset/v1/emailTemplate/{id}/clone.json\n      operations:\n      - name: clonetemplateusingpost\n        method: POST\n        description: Marketo Clone Email Template\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-content\n      path: /rest/asset/v1/emailTemplate/{id}/content\n      operations:\n      - name: gettemplatecontentbyidusingget\n        method: GET\n        description: Marketo Get Email Template Content by Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n     \
  \     required: true\n          description: id\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-content-json\n      path: /rest/asset/v1/emailTemplate/{id}/content.json\n      operations:\n      - name: updateemailtemplatecontentusingpost\n        method: POST\n        description: Marketo Update Email Template Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-delete-json\n      path: /rest/asset/v1/emailTemplate/{id}/delete.json\n      operations:\n      - name:\
  \ deletetemplateusingpost\n        method: POST\n        description: Marketo Delete Email Template\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-discarddraft-json\n      path: /rest/asset/v1/emailTemplate/{id}/discardDraft.json\n      operations:\n      - name: discarddraftusingpost-1\n        method: POST\n        description: Marketo Discard Email Template Draft\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplate-id-unapprove-json\n      path: /rest/asset/v1/emailTemplate/{id}/unapprove.json\n\
  \      operations:\n      - name: unapprovedraftusingpost-1\n        method: POST\n        description: Marketo Unapprove Email Template Draft\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplates-json\n      path: /rest/asset/v1/emailTemplates.json\n      operations:\n      - name: getemailtemplatesusingget\n        method: GET\n        description: Marketo Get Email Templates\n        inputParameters:\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging\n        - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of channels to return. Max 200, default 20\n        - name: status\n          in: query\n          type:\
  \ string\n          description: Status filter for draft or approved versions\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createemailtemplateusingpost\n        method: POST\n        description: Marketo Create Email Template\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emailtemplates-id-usedby-json\n      path: /rest/asset/v1/emailTemplates/{id}/usedBy.json\n      operations:\n      - name: getemailtemplateusedbyusingget\n        method: GET\n        description: Marketo Get Email Template Used By\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the email template\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging\n  \
  \      - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of channels to return. Max 200, default 20\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-emails-json\n      path: /rest/asset/v1/emails.json\n      operations:\n      - name: getemailusingget\n        method: GET\n        description: Marketo Get Emails\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions\n        - name: folder\n          in: query\n          type: string\n          description: JSON representation of parent folder, with members 'id', and 'type' which may be 'Folder' or 'Program'\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging\n        - name: maxReturn\n          in: query\n\
  \          type: integer\n          description: Maximum number of emails to return. Max 200, default 20\n        - name: earliestUpdatedAt\n          in: query\n          type: string\n          description: Exclude emails prior to this date. Must be valid ISO-8601 string. See <a href=\"http://developers.marketo.com/rest-api/lead-database/fields/field-types/\">Datetim\n        - name: latestUpdatedAt\n          in: query\n          type: string\n          description: Exclude emails after this date. Must be valid ISO-8601 string. See <a href=\"http://developers.marketo.com/rest-api/lead-database/fields/field-types/\">Datetime</\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createemailusingpost\n        method: POST\n        description: Marketo Create Email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ rest-asset-v1-email-id-fullcontent-json\n      path: /rest/asset/v1/email/{id}/fullContent.json\n      operations:\n      - name: getemailfullcontentusingget\n        method: GET\n        description: Marketo Get Email Full Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the email\n        - name: status\n          in: query\n          type: string\n          description: Status filter for draft or approved versions. Defaults to approved if asset is approved, draft if not.\n        - name: leadId\n          in: query\n          type: integer\n          description: The lead id to impersonate. Email is rendered as though it was received by this lead.\n        - name: type\n          in: query\n          type: string\n          description: Email content type to return. Default is HTML.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n      - name: createemailfullcontentusingpost\n        method: POST\n        description: Marketo Update Email Full Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the email\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-file-byname-json\n      path: /rest/asset/v1/file/byName.json\n      operations:\n      - name: getfilebynameusingget\n        method: GET\n        description: Marketo Get File by Name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Name of the file\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-file-id-json\n      path: /rest/asset/v1/file/{id}.json\n\
  \      operations:\n      - name: getfilebyidusingget\n        method: GET\n        description: Marketo Get File by Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id for file in database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-file-id-content-json\n      path: /rest/asset/v1/file/{id}/content.json\n      operations:\n      - name: updatecontentusingpost\n        method: POST\n        description: Marketo Update File Content\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id for file in database\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-files-json\n      path: /rest/asset/v1/files.json\n\
  \      operations:\n      - name: getfilesusingget\n        method: GET\n        description: Marketo Get Files\n        inputParameters:\n        - name: folder\n          in: query\n          type: string\n          description: JSON representation of parent folder, with members 'id', and 'type' which may be 'Folder' or 'Program'\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging. Default 0\n        - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of files to return. Max 200, default 20\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createfileusingpost\n        method: POST\n        description: Marketo Create File\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-byname-json\n\
  \      path: /rest/asset/v1/folder/byName.json\n      operations:\n      - name: getfolderbynameusingget\n        method: GET\n        description: Marketo Get Folder by Name\n        inputParameters:\n        - name: name\n          in: query\n          type: string\n          required: true\n          description: Name of the folder. Not applicable for Programs\n        - name: type\n          in: query\n          type: string\n          description: Type of folder. 'Folder' or 'Program'\n        - name: root\n          in: query\n          type: string\n          description: Parent folder reference\n        - name: workSpace\n          in: query\n          type: string\n          description: Name of the workspace\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-id-json\n      path: /rest/asset/v1/folder/{id}.json\n      operations:\n      - name: getfolderbyidusingget\n\
  \        method: GET\n        description: Marketo Get Folder by Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the folder to retrieve\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: Type of folder. 'Folder' or 'Program'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatefolderusingpost\n        method: POST\n        description: Marketo Update Folder Metadata\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the folder to update\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-id-content-json\n      path: /rest/asset/v1/folder/{id}/content.json\n\
  \      operations:\n      - name: getfoldercontentusingget\n        method: GET\n        description: Marketo Get Folder Contents\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the folder to retrieve\n        - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of channels to return. Max 200, default 20\n        - name: offset\n          in: query\n          type: integer\n          description: Integer offset for paging\n        - name: type\n          in: query\n          type: string\n          required: true\n          description: Type of folder. 'Folder' or 'Program'. Default is 'Folder'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-id-delete-json\n      path: /rest/asset/v1/folder/{id}/delete.json\n      operations:\n\
  \      - name: deletefolderusingpost\n        method: POST\n        description: Marketo Delete Folder\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the folder to delete\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-id-tokens-json\n      path: /rest/asset/v1/folder/{id}/tokens.json\n      operations:\n      - name: gettokensbyfolderidusingget\n        method: GET\n        description: Marketo Get Tokens by Folder Id\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        - name: folderType\n          in: query\n          type: string\n          description: Type of folder. 'Folder' or 'Program'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n \
  \         type: object\n          value: $.\n      - name: addtokentofolderusingpost\n        method: POST\n        description: Marketo Create Token\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: Id of the folder to which the token will be associated with\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: rest-asset-v1-folder-id-tokens-delete-json\n      path: /rest/asset/v1/folder/{id}/tokens/delete.json\n      operations:\n      - name: deletetokenbynameusingpost\n        method: POST\n        description: Marketo Delete Token by Name\n        inputParameters:\n        - name: id\n          in: path\n          type: integer\n          required: true\n          description: id\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: rest-asset-v1-folders-json\n      path: /rest/asset/v1/folders.json\n      operations:\n      - name: getfolderusingget\n        method: GET\n        description: Marketo Get Folders\n        inputParameters:\n        - name: root\n          in: query\n          type: string\n          description: Parent folder reference\n        - name: maxDepth\n          in: query\n          type: integer\n          description: Maximum folder depth to traverse, Default 2\n        - name: maxReturn\n          in: query\n          type: integer\n          description: Maximum number of folders to return. Default 20, maximum 200\n        - name: offset\n          in: query\n          type: integer\n        \n\n# --- truncated at 32 KB (89 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/marketo/refs/heads/main/capabilities/marketo-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/marketo/refs/heads/main/capabilities/marketo-capability.yaml
tags:
- Marketo
- API
tools:
- description: Marketo Get Channel by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getchannelbynameusingget
- description: Marketo Get Channels
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallchannelsusingget
- description: Marketo Get Email by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailbynameusingget
- description: Marketo Get Email By Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailbyidusingget
- description: Marketo Update Email Metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemailusingpost
- description: Marketo Approve Email Draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approvedraftusingpost
- description: Marketo Clone Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: cloneemailusingpost
- description: Marketo Get Email Content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailcontentbyidusingget
- description: Marketo Update Email Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemailcontentusingpost
- description: Marketo Rearrange Email Modules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: rearrangemodulesusingpost
- description: Marketo Update Email Content Section
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemailcomponentcontentusingpost
- description: Marketo Add Email Module
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addmoduleusingpost
- description: Marketo Delete Module
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletemoduleusingpost
- description: Marketo Duplicate Email Module
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: duplicatemoduleusingpost
- description: Marketo Rename Email Module
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: renameusingpost
- description: Marketo Delete Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deleteemailusingpost
- description: Marketo Discard Email Draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: discarddraftusingpost
- description: Marketo Get Email Dynamic Content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemaildynamiccontentusingget
- description: Marketo Update Email Dynamic Content Section
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemaildynamiccontentusingpost
- description: Marketo Send Sample Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: sendsampleemailusingpost
- description: Marketo Unapprove Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unapprovedraftusingpost
- description: Marketo Update Email Variable
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatevariableusingpost
- description: Marketo Get Email Variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailvariablesusingget
- description: Marketo Get Email CC Fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailccfieldsusingget
- description: Marketo Get Email Template by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplatebynameusingget
- description: Marketo Get Email Template by Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplatebyidusingget
- description: Marketo Update Email Template Metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemailtemplateusingpost
- description: Marketo Approve Email Template Draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: approvedraftusingpost-1
- description: Marketo Clone Email Template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: clonetemplateusingpost
- description: Marketo Get Email Template Content by Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettemplatecontentbyidusingget
- description: Marketo Update Email Template Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateemailtemplatecontentusingpost
- description: Marketo Delete Email Template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletetemplateusingpost
- description: Marketo Discard Email Template Draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: discarddraftusingpost-1
- description: Marketo Unapprove Email Template Draft
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: unapprovedraftusingpost-1
- description: Marketo Get Email Templates
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailtemplatesusingget
- description: Marketo Create Email Template
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createemailtemplateusingpost
- description: Marketo Get Email Template Used By
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailtemplateusedbyusingget
- description: Marketo Get Emails
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailusingget
- description: Marketo Create Email
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createemailusingpost
- description: Marketo Get Email Full Content
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getemailfullcontentusingget
- description: Marketo Update Email Full Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createemailfullcontentusingpost
- description: Marketo Get File by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfilebynameusingget
- description: Marketo Get File by Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfilebyidusingget
- description: Marketo Update File Content
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatecontentusingpost
- description: Marketo Get Files
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfilesusingget
- description: Marketo Create File
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfileusingpost
- description: Marketo Get Folder by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolderbynameusingget
- description: Marketo Get Folder by Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolderbyidusingget
- description: Marketo Update Folder Metadata
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatefolderusingpost
- description: Marketo Get Folder Contents
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfoldercontentusingget
- description: Marketo Delete Folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletefolderusingpost
- description: Marketo Get Tokens by Folder Id
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: gettokensbyfolderidusingget
- description: Marketo Create Token
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addtokentofolderusingpost
- description: Marketo Delete Token by Name
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: deletetokenbynameusingpost
- description: Marketo Get Folders
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getfolderusingget
- description: Marketo Create Folder
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createfolderusingpost
- description: Marketo Get Form by Name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getlpformbynameusingget
- description: Marketo Get Available Form Fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallfieldsusingget
- description: Marketo Get Available Form Program Member Fields
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getallprogrammemberfieldsusingget
- description: Marketo Add Form Field Visibility Rules
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: addformfieldvisibilityruleusingpost
---
