---
categories: []
consumed_apis: []
description: Unified workflow capability for industrial operations monitoring and control using FactoryTalk Optix REST API. Enables plant operators, process engineers, and maintenance teams to monitor real-time process variables, manage alarms, analyze historical trends, and apply production recipes across manufacturing operations.
layout: capability
name: Rockwell FactoryTalk Industrial Operations
operations:
- description: List all process variable tags defined in the project
  method: GET
  name: list-tags
  path: /v1/tags
- description: Read current values for one or more tags
  method: GET
  name: read-tag-values
  path: /v1/tag-values
- description: Write values to one or more process variable tags
  method: POST
  name: write-tag-values
  path: /v1/tag-values
- description: List active and unacknowledged alarms
  method: GET
  name: list-alarms
  path: /v1/alarms
- description: Acknowledge an active alarm with optional comment
  method: POST
  name: acknowledge-alarm
  path: /v1/alarms/{alarmId}/acknowledge
- description: Get alarm history within a time range
  method: GET
  name: get-alarm-history
  path: /v1/alarm-history
- description: Get historical trend data for a tag
  method: GET
  name: get-trend-data
  path: /v1/trends/{tagName}
- description: List all available production recipes
  method: GET
  name: list-recipes
  path: /v1/recipes
- description: Apply a recipe to write configured tag values to a machine
  method: POST
  name: apply-recipe
  path: /v1/recipes/{recipeName}/apply
personas: []
provider_name: rockwell-factorytalk
provider_slug: rockwell-factorytalk
search_terms:
- list recipes
- get metadata and current value for a specific process variable tag
- list active alarms
- list tags
- list all available production recipes and their parameters
- real-time tag value read and write operations
- acknowledge alarm
- apply a production recipe to a machine or unit, writing all configured tag values
- get alarm history
- scada
- get alarm history within a time range
- retrieve alarm event history for a time range to investigate recurring issues
- list all available production recipes
- list alarms
- acknowledge an active alarm with optional comment
- acknowledge an active alarm with an operator comment
- get trend data
- historical trend data for process variables
- get historical trend data for a tag
- write values to one or more process variable tags
- manufacturing
- rockwell automation
- process variable tag monitoring
- list all process variable tags defined in the project
- apply recipe
- list active and unacknowledged alarms
- read current values for one or more process variable tags in real-time
- get historical trend data for a process variable tag over a time range
- apply a recipe to write configured tag values to a machine
- list all process variable tags defined in the factorytalk optix project
- write values to one or more process variable tags to control machine state
- read current values for one or more tags
- alarm monitoring and management
- industrial automation
- apply a recipe to a production unit
- historical alarm event data
- write tag values
- production recipe management
- alarm acknowledgment operations
- get tag metadata
- process control
- hmi
- read tag values
- list currently active and unacknowledged alarms on the production line
slug: industrial-operations
source_filename: industrial-operations.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Rockwell FactoryTalk Industrial Operations\n  description: Unified workflow capability for industrial operations monitoring and control using FactoryTalk Optix REST API.\n    Enables plant operators, process engineers, and maintenance teams to monitor real-time process variables, manage alarms,\n    analyze historical trends, and apply production recipes across manufacturing operations.\n  tags:\n  - Industrial Automation\n  - Manufacturing\n  - SCADA\n  - HMI\n  - Process Control\n  - Rockwell Automation\n  created: '2026-05-02'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys:\n    FACTORYTALK_OPTIX_API_KEY: FACTORYTALK_OPTIX_API_KEY\ncapability:\n  consumes:\n  - type: http\n    namespace: factorytalk-optix\n    baseUri: https://{host}/api/v1\n    description: FactoryTalk Optix REST API for HMI/SCADA integration\n    authentication:\n      type: apikey\n      key: X-Api-Key\n      value: '{{FACTORYTALK_OPTIX_API_KEY}}'\n\
  \      placement: header\n    resources:\n    - name: tags\n      path: /tags\n      description: Tag (process variable) management and monitoring\n      operations:\n      - name: list-tags\n        method: GET\n        description: Returns all tags (variables) defined in the FactoryTalk Optix project\n        inputParameters:\n        - name: nameFilter\n          in: query\n          type: string\n          required: false\n          description: Wildcard filter for tag names\n        - name: tagType\n          in: query\n          type: string\n          required: false\n          description: Filter by tag data type\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        - name: offset\n          in: query\n          type: integer\n          required: false\n          description: Pagination offset\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n  \
  \        type: object\n          value: $.\n      - name: read-tag-values\n        method: GET\n        description: Read current values for a list of tags in a single request\n        inputParameters:\n        - name: names\n          in: query\n          type: string\n          required: true\n          description: Comma-separated list of tag names to read\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: write-tag-values\n        method: POST\n        description: Write values to one or more tags\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            writes: '{{tools.writes}}'\n      - name: get-tag\n        method: GET\n        description: Returns metadata and current value for a specific tag\n        inputParameters:\n        - name: tagName\n        \
  \  in: path\n          type: string\n          required: true\n          description: Tag name (may use dot notation)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: alarms\n      path: /alarms\n      description: Alarm and event management\n      operations:\n      - name: list-alarms\n        method: GET\n        description: Returns currently active and unacknowledged alarms\n        inputParameters:\n        - name: status\n          in: query\n          type: string\n          required: false\n          description: Filter by alarm status (ACTIVE, ACKNOWLEDGED, NORMAL)\n        - name: severity\n          in: query\n          type: string\n          required: false\n          description: Minimum severity (LOW, MEDIUM, HIGH, CRITICAL)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: acknowledge-alarm\n        method: POST\n        description: Acknowledges an active alarm, optionally with a comment\n        inputParameters:\n        - name: alarmId\n          in: path\n          type: string\n          required: true\n          description: Alarm identifier\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n        body:\n          type: json\n          data:\n            comment: '{{tools.comment}}'\n      - name: get-alarm-history\n        method: GET\n        description: Returns historical alarm events within a time range\n        inputParameters:\n        - name: startTime\n          in: query\n          type: string\n          required: true\n          description: Start of time range (ISO 8601)\n        - name: endTime\n          in: query\n          type: string\n\
  \          required: true\n          description: End of time range (ISO 8601)\n        - name: tagName\n          in: query\n          type: string\n          required: false\n          description: Filter to specific tag\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum records to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: trends\n      path: /trends\n      description: Historical trend data retrieval\n      operations:\n      - name: get-trend-data\n        method: GET\n        description: Returns historical trending data for a tag within a time range\n        inputParameters:\n        - name: tagName\n          in: path\n          type: string\n          required: true\n          description: Tag name to retrieve trend data for\n        - name: startTime\n          in: query\n          type: string\n \
  \         required: true\n          description: Start of time range (ISO 8601)\n        - name: endTime\n          in: query\n          type: string\n          required: true\n          description: End of time range (ISO 8601)\n        - name: resolution\n          in: query\n          type: string\n          required: false\n          description: Data resolution (e.g., 1s, 1m, 1h)\n        - name: limit\n          in: query\n          type: integer\n          required: false\n          description: Maximum data points to return\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: recipes\n      path: /recipes\n      description: Recipe management\n      operations:\n      - name: list-recipes\n        method: GET\n        description: Returns recipes defined in the FactoryTalk Optix project\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: apply-recipe\n        method: POST\n        description: Applies a recipe to a machine or unit, writing configured tag values\n        inputParameters:\n        - name: recipeName\n          in: path\n          type: string\n          required: true\n          description: Recipe name to apply\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: factorytalk-operations-api\n    description: Unified REST API for FactoryTalk industrial operations monitoring and control.\n    resources:\n    - path: /v1/tags\n      name: tags\n      description: Process variable tag monitoring\n      operations:\n      - method: GET\n        name: list-tags\n        description: List all process variable tags defined in the project\n        call: factorytalk-optix.list-tags\n        with:\n          nameFilter: rest.nameFilter\n          tagType:\
  \ rest.tagType\n          limit: rest.limit\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/tag-values\n      name: tag-values\n      description: Real-time tag value read and write operations\n      operations:\n      - method: GET\n        name: read-tag-values\n        description: Read current values for one or more tags\n        call: factorytalk-optix.read-tag-values\n        with:\n          names: rest.names\n        outputParameters:\n        - type: object\n          mapping: $.\n      - method: POST\n        name: write-tag-values\n        description: Write values to one or more process variable tags\n        call: factorytalk-optix.write-tag-values\n        with:\n          writes: rest.writes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alarms\n      name: alarms\n      description: Alarm monitoring and management\n      operations:\n      - method: GET\n        name: list-alarms\n  \
  \      description: List active and unacknowledged alarms\n        call: factorytalk-optix.list-alarms\n        with:\n          status: rest.status\n          severity: rest.severity\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alarms/{alarmId}/acknowledge\n      name: alarm-acknowledgment\n      description: Alarm acknowledgment operations\n      operations:\n      - method: POST\n        name: acknowledge-alarm\n        description: Acknowledge an active alarm with optional comment\n        call: factorytalk-optix.acknowledge-alarm\n        with:\n          alarmId: rest.alarmId\n          comment: rest.comment\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/alarm-history\n      name: alarm-history\n      description: Historical alarm event data\n      operations:\n      - method: GET\n        name: get-alarm-history\n        description: Get alarm history within a time range\n        call: factorytalk-optix.get-alarm-history\n\
  \        with:\n          startTime: rest.startTime\n          endTime: rest.endTime\n          tagName: rest.tagName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/trends/{tagName}\n      name: trends\n      description: Historical trend data for process variables\n      operations:\n      - method: GET\n        name: get-trend-data\n        description: Get historical trend data for a tag\n        call: factorytalk-optix.get-trend-data\n        with:\n          tagName: rest.tagName\n          startTime: rest.startTime\n          endTime: rest.endTime\n          resolution: rest.resolution\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/recipes\n      name: recipes\n      description: Production recipe management\n      operations:\n      - method: GET\n        name: list-recipes\n        description: List all available production recipes\n        call: factorytalk-optix.list-recipes\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/recipes/{recipeName}/apply\n      name: recipe-application\n      description: Apply a recipe to a production unit\n      operations:\n      - method: POST\n        name: apply-recipe\n        description: Apply a recipe to write configured tag values to a machine\n        call: factorytalk-optix.apply-recipe\n        with:\n          recipeName: rest.recipeName\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9080\n    namespace: factorytalk-operations-mcp\n    transport: http\n    description: MCP server for AI-assisted industrial operations monitoring and control.\n    tools:\n    - name: list-tags\n      description: List all process variable tags defined in the FactoryTalk Optix project\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factorytalk-optix.list-tags\n      with:\n        nameFilter: tools.nameFilter\n        tagType: tools.tagType\n\
  \      outputParameters:\n      - type: object\n        mapping: $.\n    - name: read-tag-values\n      description: Read current values for one or more process variable tags in real-time\n      hints:\n        readOnly: true\n        openWorld: false\n      call: factorytalk-optix.read-tag-values\n      with:\n        names: tools.names\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: write-tag-values\n      description: Write values to one or more process variable tags to control machine state\n      hints:\n        readOnly: false\n        destructive: false\n      call: factorytalk-optix.write-tag-values\n      with:\n        writes: tools.writes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-tag-metadata\n      description: Get metadata and current value for a specific process variable tag\n      hints:\n        readOnly: true\n        openWorld: false\n      call: factorytalk-optix.get-tag\n      with:\n      \
  \  tagName: tools.tagName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-active-alarms\n      description: List currently active and unacknowledged alarms on the production line\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factorytalk-optix.list-alarms\n      with:\n        status: ACTIVE\n        severity: tools.severity\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: acknowledge-alarm\n      description: Acknowledge an active alarm with an operator comment\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: true\n      call: factorytalk-optix.acknowledge-alarm\n      with:\n        alarmId: tools.alarmId\n        comment: tools.comment\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-alarm-history\n      description: Retrieve alarm event history for a time range to investigate recurring issues\n      hints:\n  \
  \      readOnly: true\n        openWorld: false\n      call: factorytalk-optix.get-alarm-history\n      with:\n        startTime: tools.startTime\n        endTime: tools.endTime\n        tagName: tools.tagName\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-trend-data\n      description: Get historical trend data for a process variable tag over a time range\n      hints:\n        readOnly: true\n        openWorld: false\n      call: factorytalk-optix.get-trend-data\n      with:\n        tagName: tools.tagName\n        startTime: tools.startTime\n        endTime: tools.endTime\n        resolution: tools.resolution\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-recipes\n      description: List all available production recipes and their parameters\n      hints:\n        readOnly: true\n        openWorld: true\n      call: factorytalk-optix.list-recipes\n      outputParameters:\n      - type: object\n        mapping:\
  \ $.\n    - name: apply-recipe\n      description: Apply a production recipe to a machine or unit, writing all configured tag values\n      hints:\n        readOnly: false\n        destructive: false\n      call: factorytalk-optix.apply-recipe\n      with:\n        recipeName: tools.recipeName\n      outputParameters:\n      - type: object\n        mapping: $.\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/rockwell-factorytalk/refs/heads/main/capabilities/industrial-operations.yaml
tags:
- Industrial Automation
- Manufacturing
- SCADA
- HMI
- Process Control
- Rockwell Automation
tools:
- description: List all process variable tags defined in the FactoryTalk Optix project
  hints:
    openWorld: true
    readOnly: true
  name: list-tags
- description: Read current values for one or more process variable tags in real-time
  hints:
    openWorld: false
    readOnly: true
  name: read-tag-values
- description: Write values to one or more process variable tags to control machine state
  hints:
    destructive: false
    readOnly: false
  name: write-tag-values
- description: Get metadata and current value for a specific process variable tag
  hints:
    openWorld: false
    readOnly: true
  name: get-tag-metadata
- description: List currently active and unacknowledged alarms on the production line
  hints:
    openWorld: true
    readOnly: true
  name: list-active-alarms
- description: Acknowledge an active alarm with an operator comment
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: acknowledge-alarm
- description: Retrieve alarm event history for a time range to investigate recurring issues
  hints:
    openWorld: false
    readOnly: true
  name: get-alarm-history
- description: Get historical trend data for a process variable tag over a time range
  hints:
    openWorld: false
    readOnly: true
  name: get-trend-data
- description: List all available production recipes and their parameters
  hints:
    openWorld: true
    readOnly: true
  name: list-recipes
- description: Apply a production recipe to a machine or unit, writing all configured tag values
  hints:
    destructive: false
    readOnly: false
  name: apply-recipe
---
