---
categories: []
consumed_apis: []
description: Microsoft Graph API for managing administrative resources in Microsoft Entra ID. This API enables administrators to manage Microsoft Edge browser settings, Internet Explorer mode configurations, site lists, shared browser sites, Microsoft 365 Apps installation options, people insights, service announcements, SharePoint settings, Copilot administration, directory administrative units, and admin consent policies.
layout: capability
name: Microsoft Graph Admin API
operations:
- description: Microsoft Graph Get admin singleton
  method: GET
  name: getadmin
  path: /admin
- description: Microsoft Graph Update admin singleton
  method: PATCH
  name: updateadmin
  path: /admin
- description: Microsoft Graph Get Edge settings
  method: GET
  name: getadminedge
  path: /admin/edge
- description: Microsoft Graph Update Edge settings
  method: PATCH
  name: updateadminedge
  path: /admin/edge
- description: Microsoft Graph Delete Edge settings
  method: DELETE
  name: deleteadminedge
  path: /admin/edge
- description: Microsoft Graph Get Internet Explorer mode settings
  method: GET
  name: getedgeinternetexplorermode
  path: /admin/edge/internetExplorerMode
- description: Microsoft Graph Update Internet Explorer mode settings
  method: PATCH
  name: updateedgeinternetexplorermode
  path: /admin/edge/internetExplorerMode
- description: Microsoft Graph Delete Internet Explorer mode settings
  method: DELETE
  name: deleteedgeinternetexplorermode
  path: /admin/edge/internetExplorerMode
- description: Microsoft Graph List browser site lists
  method: GET
  name: listbrowsersitelists
  path: /admin/edge/internetExplorerMode/siteLists
- description: Microsoft Graph Create browser site list
  method: POST
  name: createbrowsersitelist
  path: /admin/edge/internetExplorerMode/siteLists
- description: Microsoft Graph Get browser site list
  method: GET
  name: getbrowsersitelist
  path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}
- description: Microsoft Graph Update browser site list
  method: PATCH
  name: updatebrowsersitelist
  path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}
- description: Microsoft Graph Delete browser site list
  method: DELETE
  name: deletebrowsersitelist
  path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}
- description: Microsoft Graph Get Microsoft 365 Apps settings
  method: GET
  name: getmicrosoft365apps
  path: /admin/microsoft365Apps
- description: Microsoft Graph Update Microsoft 365 Apps settings
  method: PATCH
  name: updatemicrosoft365apps
  path: /admin/microsoft365Apps
- description: Microsoft Graph Get report settings
  method: GET
  name: getreportsettings
  path: /admin/reportSettings
- description: Microsoft Graph Update report settings
  method: PATCH
  name: updatereportsettings
  path: /admin/reportSettings
- description: Microsoft Graph Get service announcement
  method: GET
  name: getserviceannouncement
  path: /admin/serviceAnnouncement
- description: Microsoft Graph Get SharePoint settings
  method: GET
  name: getsharepointsettings
  path: /admin/sharepoint
- description: Microsoft Graph Update SharePoint settings
  method: PATCH
  name: updatesharepointsettings
  path: /admin/sharepoint
- description: Microsoft Graph Get Copilot admin settings
  method: GET
  name: getcopilotadmin
  path: /copilot/admin
- description: Microsoft Graph List administrative units
  method: GET
  name: listadministrativeunits
  path: /directory/administrativeUnits
- description: Microsoft Graph Create administrative unit
  method: POST
  name: createadministrativeunit
  path: /directory/administrativeUnits
- description: Microsoft Graph Get administrative unit
  method: GET
  name: getadministrativeunit
  path: /directory/administrativeUnits/{administrativeUnit-id}
- description: Microsoft Graph Update administrative unit
  method: PATCH
  name: updateadministrativeunit
  path: /directory/administrativeUnits/{administrativeUnit-id}
- description: Microsoft Graph Delete administrative unit
  method: DELETE
  name: deleteadministrativeunit
  path: /directory/administrativeUnits/{administrativeUnit-id}
- description: Microsoft Graph Get admin consent request policy
  method: GET
  name: getadminconsentrequestpolicy
  path: /policies/adminConsentRequestPolicy
- description: Microsoft Graph Update admin consent request policy
  method: PATCH
  name: updateadminconsentrequestpolicy
  path: /policies/adminConsentRequestPolicy
personas: []
provider_name: Microsoft Graph
provider_slug: microsoft-graph
search_terms:
- getmicrosoft365apps
- getserviceannouncement
- updateadmin
- microsoft graph delete edge settings
- getreportsettings
- getsharepointsettings
- microsoft graph update admin singleton
- presentations
- spreadsheets
- updatebrowsersitelist
- microsoft graph delete browser site list
- identity
- tasks
- createadministrativeunit
- getadminedge
- getadminconsentrequestpolicy
- listadministrativeunits
- microsoft graph get microsoft 365 apps settings
- microsoft graph get internet explorer mode settings
- deleteadministrativeunit
- microsoft graph get service announcement
- microsoft graph get browser site list
- contacts
- microsoft graph update browser site list
- microsoft graph create administrative unit
- createbrowsersitelist
- azure ad
- microsoft graph delete internet explorer mode settings
- microsoft graph update microsoft 365 apps settings
- graph
- microsoft graph get admin singleton
- updateadminedge
- microsoft graph update internet explorer mode settings
- microsoft graph update sharepoint settings
- updateadministrativeunit
- microsoft graph get sharepoint settings
- getedgeinternetexplorermode
- getbrowsersitelist
- updatereportsettings
- microsoft graph create browser site list
- updateedgeinternetexplorermode
- microsoft graph update report settings
- productivity
- getadministrativeunit
- getcopilotadmin
- deleteedgeinternetexplorermode
- microsoft graph get edge settings
- t1
- microsoft graph update administrative unit
- deletebrowsersitelist
- api
- updatesharepointsettings
- listbrowsersitelists
- microsoft graph delete administrative unit
- getadmin
- microsoft graph update admin consent request policy
- microsoft graph get administrative unit
- microsoft graph get copilot admin settings
- deleteadminedge
- email
- office 365
- microsoft graph get admin consent request policy
- microsoft graph list browser site lists
- updatemicrosoft365apps
- documents
- updateadminconsentrequestpolicy
- microsoft graph list administrative units
- microsoft
- collaboration
- microsoft graph get report settings
- microsoft graph update edge settings
slug: microsoft-graph-capability
source_filename: microsoft-graph-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Microsoft Graph Admin API\n  description: Microsoft Graph API for managing administrative resources in Microsoft Entra ID. This API enables administrators\n    to manage Microsoft Edge browser settings, Internet Explorer mode configurations, site lists, shared browser sites, Microsoft\n    365 Apps installation options, people insights, service announcements, SharePoint settings, Copilot administration, directory\n    administrative units, and admin consent policies.\n  tags:\n  - Microsoft\n  - Graph\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: microsoft-graph\n    baseUri: https://graph.microsoft.com/v1.0\n    description: Microsoft Graph Admin API HTTP API.\n    resources:\n    - name: admin\n      path: /admin\n      operations:\n      - name: getadmin\n        method: GET\n        description: Microsoft Graph Get admin singleton\n        inputParameters:\n  \
  \      - name: $select\n          in: query\n          type: array\n          description: Select properties to be returned\n        - name: $expand\n          in: query\n          type: array\n          description: Expand related entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadmin\n        method: PATCH\n        description: Microsoft Graph Update admin singleton\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-edge\n      path: /admin/edge\n      operations:\n      - name: getadminedge\n        method: GET\n        description: Microsoft Graph Get Edge settings\n        inputParameters:\n        - name: $select\n          in: query\n          type: array\n          description: Select properties to be returned\n        - name: $expand\n          in: query\n          type: array\n\
  \          description: Expand related entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadminedge\n        method: PATCH\n        description: Microsoft Graph Update Edge settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteadminedge\n        method: DELETE\n        description: Microsoft Graph Delete Edge settings\n        inputParameters:\n        - name: If-Match\n          in: header\n          type: string\n          description: ETag for optimistic concurrency control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-edge-internetexplorermode\n      path: /admin/edge/internetExplorerMode\n      operations:\n      - name: getedgeinternetexplorermode\n        method: GET\n      \
  \  description: Microsoft Graph Get Internet Explorer mode settings\n        inputParameters:\n        - name: $select\n          in: query\n          type: array\n          description: Select properties to be returned\n        - name: $expand\n          in: query\n          type: array\n          description: Expand related entities\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateedgeinternetexplorermode\n        method: PATCH\n        description: Microsoft Graph Update Internet Explorer mode settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteedgeinternetexplorermode\n        method: DELETE\n        description: Microsoft Graph Delete Internet Explorer mode settings\n        inputParameters:\n        - name: If-Match\n          in: header\n          type: string\n          description:\
  \ ETag for optimistic concurrency control\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-edge-internetexplorermode-sitelists\n      path: /admin/edge/internetExplorerMode/siteLists\n      operations:\n      - name: listbrowsersitelists\n        method: GET\n        description: Microsoft Graph List browser site lists\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createbrowsersitelist\n        method: POST\n        description: Microsoft Graph Create browser site list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-edge-internetexplorermode-sitelists-browse\n      path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}\n      operations:\n      - name: getbrowsersitelist\n        method:\
  \ GET\n        description: Microsoft Graph Get browser site list\n        inputParameters:\n        - name: $select\n          in: query\n          type: array\n          description: Select properties to be returned\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatebrowsersitelist\n        method: PATCH\n        description: Microsoft Graph Update browser site list\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletebrowsersitelist\n        method: DELETE\n        description: Microsoft Graph Delete browser site list\n        inputParameters:\n        - name: If-Match\n          in: header\n          type: string\n          description: ETag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-microsoft365apps\n\
  \      path: /admin/microsoft365Apps\n      operations:\n      - name: getmicrosoft365apps\n        method: GET\n        description: Microsoft Graph Get Microsoft 365 Apps settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatemicrosoft365apps\n        method: PATCH\n        description: Microsoft Graph Update Microsoft 365 Apps settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-reportsettings\n      path: /admin/reportSettings\n      operations:\n      - name: getreportsettings\n        method: GET\n        description: Microsoft Graph Get report settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatereportsettings\n        method: PATCH\n        description: Microsoft Graph Update\
  \ report settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-serviceannouncement\n      path: /admin/serviceAnnouncement\n      operations:\n      - name: getserviceannouncement\n        method: GET\n        description: Microsoft Graph Get service announcement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: admin-sharepoint\n      path: /admin/sharepoint\n      operations:\n      - name: getsharepointsettings\n        method: GET\n        description: Microsoft Graph Get SharePoint settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatesharepointsettings\n        method: PATCH\n        description: Microsoft Graph Update SharePoint settings\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: copilot-admin\n      path: /copilot/admin\n      operations:\n      - name: getcopilotadmin\n        method: GET\n        description: Microsoft Graph Get Copilot admin settings\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: directory-administrativeunits\n      path: /directory/administrativeUnits\n      operations:\n      - name: listadministrativeunits\n        method: GET\n        description: Microsoft Graph List administrative units\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createadministrativeunit\n        method: POST\n        description: Microsoft Graph Create administrative unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n\
  \    - name: directory-administrativeunits-administrativeunit\n      path: /directory/administrativeUnits/{administrativeUnit-id}\n      operations:\n      - name: getadministrativeunit\n        method: GET\n        description: Microsoft Graph Get administrative unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadministrativeunit\n        method: PATCH\n        description: Microsoft Graph Update administrative unit\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteadministrativeunit\n        method: DELETE\n        description: Microsoft Graph Delete administrative unit\n        inputParameters:\n        - name: If-Match\n          in: header\n          type: string\n          description: ETag\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n         \
  \ type: object\n          value: $.\n    - name: policies-adminconsentrequestpolicy\n      path: /policies/adminConsentRequestPolicy\n      operations:\n      - name: getadminconsentrequestpolicy\n        method: GET\n        description: Microsoft Graph Get admin consent request policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updateadminconsentrequestpolicy\n        method: PATCH\n        description: Microsoft Graph Update admin consent request policy\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: microsoft-graph-rest\n    description: REST adapter for Microsoft Graph Admin API.\n    resources:\n    - path: /admin\n      name: getadmin\n      operations:\n      - method: GET\n        name: getadmin\n        description: Microsoft Graph Get admin singleton\n\
  \        call: microsoft-graph.getadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin\n      name: updateadmin\n      operations:\n      - method: PATCH\n        name: updateadmin\n        description: Microsoft Graph Update admin singleton\n        call: microsoft-graph.updateadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge\n      name: getadminedge\n      operations:\n      - method: GET\n        name: getadminedge\n        description: Microsoft Graph Get Edge settings\n        call: microsoft-graph.getadminedge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge\n      name: updateadminedge\n      operations:\n      - method: PATCH\n        name: updateadminedge\n        description: Microsoft Graph Update Edge settings\n        call: microsoft-graph.updateadminedge\n        outputParameters:\n        - type: object\n          mapping:\
  \ $.\n    - path: /admin/edge\n      name: deleteadminedge\n      operations:\n      - method: DELETE\n        name: deleteadminedge\n        description: Microsoft Graph Delete Edge settings\n        call: microsoft-graph.deleteadminedge\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode\n      name: getedgeinternetexplorermode\n      operations:\n      - method: GET\n        name: getedgeinternetexplorermode\n        description: Microsoft Graph Get Internet Explorer mode settings\n        call: microsoft-graph.getedgeinternetexplorermode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode\n      name: updateedgeinternetexplorermode\n      operations:\n      - method: PATCH\n        name: updateedgeinternetexplorermode\n        description: Microsoft Graph Update Internet Explorer mode settings\n        call: microsoft-graph.updateedgeinternetexplorermode\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode\n      name: deleteedgeinternetexplorermode\n      operations:\n      - method: DELETE\n        name: deleteedgeinternetexplorermode\n        description: Microsoft Graph Delete Internet Explorer mode settings\n        call: microsoft-graph.deleteedgeinternetexplorermode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode/siteLists\n      name: listbrowsersitelists\n      operations:\n      - method: GET\n        name: listbrowsersitelists\n        description: Microsoft Graph List browser site lists\n        call: microsoft-graph.listbrowsersitelists\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode/siteLists\n      name: createbrowsersitelist\n      operations:\n      - method: POST\n        name: createbrowsersitelist\n        description:\
  \ Microsoft Graph Create browser site list\n        call: microsoft-graph.createbrowsersitelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}\n      name: getbrowsersitelist\n      operations:\n      - method: GET\n        name: getbrowsersitelist\n        description: Microsoft Graph Get browser site list\n        call: microsoft-graph.getbrowsersitelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}\n      name: updatebrowsersitelist\n      operations:\n      - method: PATCH\n        name: updatebrowsersitelist\n        description: Microsoft Graph Update browser site list\n        call: microsoft-graph.updatebrowsersitelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/edge/internetExplorerMode/siteLists/{browserSiteList-id}\n   \
  \   name: deletebrowsersitelist\n      operations:\n      - method: DELETE\n        name: deletebrowsersitelist\n        description: Microsoft Graph Delete browser site list\n        call: microsoft-graph.deletebrowsersitelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/microsoft365Apps\n      name: getmicrosoft365apps\n      operations:\n      - method: GET\n        name: getmicrosoft365apps\n        description: Microsoft Graph Get Microsoft 365 Apps settings\n        call: microsoft-graph.getmicrosoft365apps\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/microsoft365Apps\n      name: updatemicrosoft365apps\n      operations:\n      - method: PATCH\n        name: updatemicrosoft365apps\n        description: Microsoft Graph Update Microsoft 365 Apps settings\n        call: microsoft-graph.updatemicrosoft365apps\n        outputParameters:\n        - type: object\n          mapping: $.\n  \
  \  - path: /admin/reportSettings\n      name: getreportsettings\n      operations:\n      - method: GET\n        name: getreportsettings\n        description: Microsoft Graph Get report settings\n        call: microsoft-graph.getreportsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/reportSettings\n      name: updatereportsettings\n      operations:\n      - method: PATCH\n        name: updatereportsettings\n        description: Microsoft Graph Update report settings\n        call: microsoft-graph.updatereportsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/serviceAnnouncement\n      name: getserviceannouncement\n      operations:\n      - method: GET\n        name: getserviceannouncement\n        description: Microsoft Graph Get service announcement\n        call: microsoft-graph.getserviceannouncement\n        outputParameters:\n        - type: object\n          mapping: $.\n \
  \   - path: /admin/sharepoint\n      name: getsharepointsettings\n      operations:\n      - method: GET\n        name: getsharepointsettings\n        description: Microsoft Graph Get SharePoint settings\n        call: microsoft-graph.getsharepointsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /admin/sharepoint\n      name: updatesharepointsettings\n      operations:\n      - method: PATCH\n        name: updatesharepointsettings\n        description: Microsoft Graph Update SharePoint settings\n        call: microsoft-graph.updatesharepointsettings\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /copilot/admin\n      name: getcopilotadmin\n      operations:\n      - method: GET\n        name: getcopilotadmin\n        description: Microsoft Graph Get Copilot admin settings\n        call: microsoft-graph.getcopilotadmin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path:\
  \ /directory/administrativeUnits\n      name: listadministrativeunits\n      operations:\n      - method: GET\n        name: listadministrativeunits\n        description: Microsoft Graph List administrative units\n        call: microsoft-graph.listadministrativeunits\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directory/administrativeUnits\n      name: createadministrativeunit\n      operations:\n      - method: POST\n        name: createadministrativeunit\n        description: Microsoft Graph Create administrative unit\n        call: microsoft-graph.createadministrativeunit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directory/administrativeUnits/{administrativeUnit-id}\n      name: getadministrativeunit\n      operations:\n      - method: GET\n        name: getadministrativeunit\n        description: Microsoft Graph Get administrative unit\n        call: microsoft-graph.getadministrativeunit\n   \
  \     outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directory/administrativeUnits/{administrativeUnit-id}\n      name: updateadministrativeunit\n      operations:\n      - method: PATCH\n        name: updateadministrativeunit\n        description: Microsoft Graph Update administrative unit\n        call: microsoft-graph.updateadministrativeunit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /directory/administrativeUnits/{administrativeUnit-id}\n      name: deleteadministrativeunit\n      operations:\n      - method: DELETE\n        name: deleteadministrativeunit\n        description: Microsoft Graph Delete administrative unit\n        call: microsoft-graph.deleteadministrativeunit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/adminConsentRequestPolicy\n      name: getadminconsentrequestpolicy\n      operations:\n      - method: GET\n        name: getadminconsentrequestpolicy\n\
  \        description: Microsoft Graph Get admin consent request policy\n        call: microsoft-graph.getadminconsentrequestpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /policies/adminConsentRequestPolicy\n      name: updateadminconsentrequestpolicy\n      operations:\n      - method: PATCH\n        name: updateadminconsentrequestpolicy\n        description: Microsoft Graph Update admin consent request policy\n        call: microsoft-graph.updateadminconsentrequestpolicy\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: microsoft-graph-mcp\n    transport: http\n    description: MCP adapter for Microsoft Graph Admin API for AI agent use.\n    tools:\n    - name: getadmin\n      description: Microsoft Graph Get admin singleton\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getadmin\n      with:\n\
  \        $select: tools.$select\n        $expand: tools.$expand\n      inputParameters:\n      - name: $select\n        type: array\n        description: Select properties to be returned\n      - name: $expand\n        type: array\n        description: Expand related entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadmin\n      description: Microsoft Graph Update admin singleton\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updateadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadminedge\n      description: Microsoft Graph Get Edge settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getadminedge\n      with:\n        $select: tools.$select\n        $expand: tools.$expand\n      inputParameters:\n      - name: $select\n        type: array\n       \
  \ description: Select properties to be returned\n      - name: $expand\n        type: array\n        description: Expand related entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadminedge\n      description: Microsoft Graph Update Edge settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updateadminedge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteadminedge\n      description: Microsoft Graph Delete Edge settings\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-graph.deleteadminedge\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getedgeinternetexplorermode\n      description: Microsoft Graph Get Internet Explorer mode settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n   \
  \   call: microsoft-graph.getedgeinternetexplorermode\n      with:\n        $select: tools.$select\n        $expand: tools.$expand\n      inputParameters:\n      - name: $select\n        type: array\n        description: Select properties to be returned\n      - name: $expand\n        type: array\n        description: Expand related entities\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateedgeinternetexplorermode\n      description: Microsoft Graph Update Internet Explorer mode settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updateedgeinternetexplorermode\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteedgeinternetexplorermode\n      description: Microsoft Graph Delete Internet Explorer mode settings\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-graph.deleteedgeinternetexplorermode\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listbrowsersitelists\n      description: Microsoft Graph List browser site lists\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.listbrowsersitelists\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createbrowsersitelist\n      description: Microsoft Graph Create browser site list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.createbrowsersitelist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getbrowsersitelist\n      description: Microsoft Graph Get browser site list\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getbrowsersitelist\n      with:\n        $select: tools.$select\n      inputParameters:\n      - name: $select\n\
  \        type: array\n        description: Select properties to be returned\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatebrowsersitelist\n      description: Microsoft Graph Update browser site list\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updatebrowsersitelist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deletebrowsersitelist\n      description: Microsoft Graph Delete browser site list\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-graph.deletebrowsersitelist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getmicrosoft365apps\n      description: Microsoft Graph Get Microsoft 365 Apps settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getmicrosoft365apps\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatemicrosoft365apps\n      description: Microsoft Graph Update Microsoft 365 Apps settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updatemicrosoft365apps\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getreportsettings\n      description: Microsoft Graph Get report settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getreportsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatereportsettings\n      description: Microsoft Graph Update report settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updatereportsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name:\
  \ getserviceannouncement\n      description: Microsoft Graph Get service announcement\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getserviceannouncement\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getsharepointsettings\n      description: Microsoft Graph Get SharePoint settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getsharepointsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updatesharepointsettings\n      description: Microsoft Graph Update SharePoint settings\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updatesharepointsettings\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getcopilotadmin\n      description: Microsoft Graph Get Copilot admin\
  \ settings\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.getcopilotadmin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: listadministrativeunits\n      description: Microsoft Graph List administrative units\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: microsoft-graph.listadministrativeunits\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: createadministrativeunit\n      description: Microsoft Graph Create administrative unit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.createadministrativeunit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadministrativeunit\n      description: Microsoft Graph Get administrative unit\n      hints:\n        readOnly: true\n        destructive:\
  \ false\n        idempotent: true\n      call: microsoft-graph.getadministrativeunit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadministrativeunit\n      description: Microsoft Graph Update administrative unit\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updateadministrativeunit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: deleteadministrativeunit\n      description: Microsoft Graph Delete administrative unit\n      hints:\n        readOnly: false\n        destructive: true\n        idempotent: true\n      call: microsoft-graph.deleteadministrativeunit\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: getadminconsentrequestpolicy\n      description: Microsoft Graph Get admin consent request policy\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call:\
  \ microsoft-graph.getadminconsentrequestpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: updateadminconsentrequestpolicy\n      description: Microsoft Graph Update admin consent request policy\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: microsoft-graph.updateadminconsentrequestpolicy\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/microsoft-graph/refs/heads/main/capabilities/microsoft-graph-capability.yaml
tags:
- Microsoft
- Graph
- API
tools:
- description: Microsoft Graph Get admin singleton
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadmin
- description: Microsoft Graph Update admin singleton
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadmin
- description: Microsoft Graph Get Edge settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadminedge
- description: Microsoft Graph Update Edge settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadminedge
- description: Microsoft Graph Delete Edge settings
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteadminedge
- description: Microsoft Graph Get Internet Explorer mode settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getedgeinternetexplorermode
- description: Microsoft Graph Update Internet Explorer mode settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateedgeinternetexplorermode
- description: Microsoft Graph Delete Internet Explorer mode settings
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteedgeinternetexplorermode
- description: Microsoft Graph List browser site lists
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listbrowsersitelists
- description: Microsoft Graph Create browser site list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createbrowsersitelist
- description: Microsoft Graph Get browser site list
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getbrowsersitelist
- description: Microsoft Graph Update browser site list
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatebrowsersitelist
- description: Microsoft Graph Delete browser site list
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletebrowsersitelist
- description: Microsoft Graph Get Microsoft 365 Apps settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getmicrosoft365apps
- description: Microsoft Graph Update Microsoft 365 Apps settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatemicrosoft365apps
- description: Microsoft Graph Get report settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getreportsettings
- description: Microsoft Graph Update report settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatereportsettings
- description: Microsoft Graph Get service announcement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getserviceannouncement
- description: Microsoft Graph Get SharePoint settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getsharepointsettings
- description: Microsoft Graph Update SharePoint settings
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updatesharepointsettings
- description: Microsoft Graph Get Copilot admin settings
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getcopilotadmin
- description: Microsoft Graph List administrative units
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: listadministrativeunits
- description: Microsoft Graph Create administrative unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createadministrativeunit
- description: Microsoft Graph Get administrative unit
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadministrativeunit
- description: Microsoft Graph Update administrative unit
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadministrativeunit
- description: Microsoft Graph Delete administrative unit
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteadministrativeunit
- description: Microsoft Graph Get admin consent request policy
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: getadminconsentrequestpolicy
- description: Microsoft Graph Update admin consent request policy
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: updateadminconsentrequestpolicy
---
