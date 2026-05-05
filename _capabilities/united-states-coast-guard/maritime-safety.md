---
api_specs:
- filename: cgmix-maritime-information-exchange-openapi.yml
  format: yaml
  label: cgmix
  slug: cgmix
  spec_type: OpenAPI
  url: https://raw.githubusercontent.com/api-evangelist/united-states-coast-guard/refs/heads/main/openapi/cgmix-maritime-information-exchange-openapi.yml
categories: []
consumed_apis:
- cgmix
description: Unified capability for maritime safety compliance workflows combining USCG CGMIX vessel documentation, Port State Control inspection records, equipment certifications, and incident investigation data. Used by port agents, marine surveyors, vessel operators, and compliance professionals to verify vessel compliance with U.S. Coast Guard regulations.
layout: capability
name: USCG Maritime Safety and Compliance
operations:
- description: Get comprehensive vessel information by official number
  method: GET
  name: get-vessel
  path: /v1/vessels/{vesselId}
- description: Get vessel dimensions, tonnage, and technical details
  method: GET
  name: get-vessel-particulars
  path: /v1/vessels/{vesselId}/particulars
- description: List all Port State Control inspection cases for a vessel
  method: GET
  name: list-vessel-inspections
  path: /v1/vessels/{vesselId}/inspections
- description: List all inspection deficiencies for a vessel
  method: GET
  name: list-vessel-deficiencies
  path: /v1/vessels/{vesselId}/deficiencies
- description: List all certificates and documents for a vessel
  method: GET
  name: list-vessel-certificates
  path: /v1/vessels/{vesselId}/certificates
- description: Get USCG marine equipment approval and certification details
  method: GET
  name: get-equipment-certification
  path: /v1/equipment/{equipmentId}
- description: Get incident investigation report and enforcement referral data
  method: GET
  name: get-incident-investigation
  path: /v1/incidents/{activityId}
personas: []
provider_name: United States Coast Guard
provider_slug: united-states-coast-guard
search_terms:
- port state control
- federal government
- list vessel certificates
- retrieve summary information for a u.s. coast guard documented vessel by official number
- vessel certificates and statutory documents
- vessel summary and profile information
- get equipment certification
- get incident investigation
- get comprehensive vessel information by official number
- emergency response
- maritime safety
- list all port state control inspection cases for a vessel
- get vessel summary
- retrieve marine casualty incident investigation referral and enforcement action data
- list all regulatory certificates and statutory documents for a vessel
- list vessel deficiencies
- vessel technical specifications and dimensions
- get vessel particulars
- uscg approved marine equipment certifications
- get uscg marine equipment approval and certification details
- marine casualty incident investigation records
- get incident investigation report and enforcement referral data
- list all inspection deficiencies for a vessel
- get vessel
- get vessel dimensions, tonnage, and technical details
- list vessel inspections
- list all certificates and documents for a vessel
- vessel inspection deficiencies and operational controls
- law enforcement
- list all safety deficiencies found during vessel inspections
- retrieve vessel technical specifications including dimensions, tonnage, and propulsion
- port state control inspection history
- look up uscg approval status for marine safety equipment by certification id
- coast guard
- list port state control inspection history for a vessel
- vessel compliance
- vessel documentation
slug: maritime-safety
source_filename: maritime-safety.yaml
source_heading: Capability Spec
source_yaml: "naftiko: \"1.0.0-alpha1\"\n\ninfo:\n  label: \"USCG Maritime Safety and Compliance\"\n  description: >-\n    Unified capability for maritime safety compliance workflows combining USCG\n    CGMIX vessel documentation, Port State Control inspection records, equipment\n    certifications, and incident investigation data. Used by port agents, marine\n    surveyors, vessel operators, and compliance professionals to verify vessel\n    compliance with U.S. Coast Guard regulations.\n  tags:\n    - Maritime Safety\n    - Port State Control\n    - Vessel Compliance\n    - Coast Guard\n    - Federal Government\n  created: \"2026-05-03\"\n  modified: \"2026-05-03\"\n\nbinds:\n  - namespace: env\n    keys: {}\n\ncapability:\n  consumes:\n    - import: cgmix\n      location: ./shared/cgmix-maritime-information-exchange.yaml\n\n  exposes:\n    - type: rest\n      port: 8080\n      namespace: maritime-safety-api\n      description: \"Unified REST API for USCG maritime safety and vessel compliance\
  \ workflows.\"\n      resources:\n        - path: /v1/vessels/{vesselId}\n          name: vessels\n          description: \"Vessel summary and profile information\"\n          operations:\n            - method: GET\n              name: get-vessel\n              description: \"Get comprehensive vessel information by official number\"\n              call: \"cgmix.get-vessel-summary\"\n              with:\n                VesselID: \"rest.vesselId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vessels/{vesselId}/particulars\n          name: vessel-particulars\n          description: \"Vessel technical specifications and dimensions\"\n          operations:\n            - method: GET\n              name: get-vessel-particulars\n              description: \"Get vessel dimensions, tonnage, and technical details\"\n              call: \"cgmix.get-vessel-particulars\"\n              with:\n                VesselID: \"\
  rest.vesselId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vessels/{vesselId}/inspections\n          name: vessel-inspections\n          description: \"Port State Control inspection history\"\n          operations:\n            - method: GET\n              name: list-vessel-inspections\n              description: \"List all Port State Control inspection cases for a vessel\"\n              call: \"cgmix.get-vessel-cases\"\n              with:\n                VesselID: \"rest.vesselId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vessels/{vesselId}/deficiencies\n          name: vessel-deficiencies\n          description: \"Vessel inspection deficiencies and operational controls\"\n          operations:\n            - method: GET\n              name: list-vessel-deficiencies\n              description: \"List all inspection deficiencies\
  \ for a vessel\"\n              call: \"cgmix.get-vessel-deficiencies\"\n              with:\n                VesselID: \"rest.vesselId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/vessels/{vesselId}/certificates\n          name: vessel-certificates\n          description: \"Vessel certificates and statutory documents\"\n          operations:\n            - method: GET\n              name: list-vessel-certificates\n              description: \"List all certificates and documents for a vessel\"\n              call: \"cgmix.get-vessel-documents\"\n              with:\n                VesselID: \"rest.vesselId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/equipment/{equipmentId}\n          name: equipment\n          description: \"USCG approved marine equipment certifications\"\n          operations:\n            - method: GET\n   \
  \           name: get-equipment-certification\n              description: \"Get USCG marine equipment approval and certification details\"\n              call: \"cgmix.get-equipment-details\"\n              with:\n                EquipmentId: \"rest.equipmentId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n        - path: /v1/incidents/{activityId}\n          name: incidents\n          description: \"Marine casualty incident investigation records\"\n          operations:\n            - method: GET\n              name: get-incident-investigation\n              description: \"Get incident investigation report and enforcement referral data\"\n              call: \"cgmix.get-incident-investigation-referral\"\n              with:\n                ActivityId: \"rest.activityId\"\n              outputParameters:\n                - type: object\n                  mapping: \"$.\"\n\n    - type: mcp\n      port: 9090\n      namespace: maritime-safety-mcp\n\
  \      transport: http\n      description: \"MCP server for AI-assisted maritime safety compliance and vessel research.\"\n      tools:\n        - name: get-vessel-summary\n          description: \"Retrieve summary information for a U.S. Coast Guard documented vessel by official number\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-vessel-summary\"\n          with:\n            VesselID: \"tools.vessel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-vessel-particulars\n          description: \"Retrieve vessel technical specifications including dimensions, tonnage, and propulsion\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-vessel-particulars\"\n          with:\n            VesselID: \"tools.vessel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n      \
  \  - name: list-vessel-inspections\n          description: \"List Port State Control inspection history for a vessel\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-vessel-cases\"\n          with:\n            VesselID: \"tools.vessel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vessel-deficiencies\n          description: \"List all safety deficiencies found during vessel inspections\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-vessel-deficiencies\"\n          with:\n            VesselID: \"tools.vessel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: list-vessel-certificates\n          description: \"List all regulatory certificates and statutory documents for a vessel\"\n          hints:\n            readOnly: true\n            idempotent:\
  \ true\n          call: \"cgmix.get-vessel-documents\"\n          with:\n            VesselID: \"tools.vessel_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-equipment-certification\n          description: \"Look up USCG approval status for marine safety equipment by certification ID\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-equipment-details\"\n          with:\n            EquipmentId: \"tools.equipment_id\"\n          outputParameters:\n            - type: object\n              mapping: \"$.\"\n\n        - name: get-incident-investigation\n          description: \"Retrieve marine casualty incident investigation referral and enforcement action data\"\n          hints:\n            readOnly: true\n            idempotent: true\n          call: \"cgmix.get-incident-investigation-referral\"\n          with:\n            ActivityId: \"tools.activity_id\"\n  \
  \        outputParameters:\n            - type: object\n              mapping: \"$.\"\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/united-states-coast-guard/refs/heads/main/capabilities/maritime-safety.yaml
tags:
- Maritime Safety
- Port State Control
- Vessel Compliance
- Coast Guard
- Federal Government
tools:
- description: Retrieve summary information for a U.S. Coast Guard documented vessel by official number
  hints:
    idempotent: true
    readOnly: true
  name: get-vessel-summary
- description: Retrieve vessel technical specifications including dimensions, tonnage, and propulsion
  hints:
    idempotent: true
    readOnly: true
  name: get-vessel-particulars
- description: List Port State Control inspection history for a vessel
  hints:
    idempotent: true
    readOnly: true
  name: list-vessel-inspections
- description: List all safety deficiencies found during vessel inspections
  hints:
    idempotent: true
    readOnly: true
  name: list-vessel-deficiencies
- description: List all regulatory certificates and statutory documents for a vessel
  hints:
    idempotent: true
    readOnly: true
  name: list-vessel-certificates
- description: Look up USCG approval status for marine safety equipment by certification ID
  hints:
    idempotent: true
    readOnly: true
  name: get-equipment-certification
- description: Retrieve marine casualty incident investigation referral and enforcement action data
  hints:
    idempotent: true
    readOnly: true
  name: get-incident-investigation
---
