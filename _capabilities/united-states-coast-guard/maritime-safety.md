---
categories: []
consumed_apis: []
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
- get incident investigation
- law enforcement
- vessel compliance
- list all port state control inspection cases for a vessel
- list all regulatory certificates and statutory documents for a vessel
- port state control inspection history
- list vessel deficiencies
- retrieve vessel technical specifications including dimensions, tonnage, and propulsion
- uscg approved marine equipment certifications
- get comprehensive vessel information by official number
- get equipment certification
- marine casualty incident investigation records
- list all inspection deficiencies for a vessel
- list all certificates and documents for a vessel
- look up uscg approval status for marine safety equipment by certification id
- get incident investigation report and enforcement referral data
- retrieve summary information for a u.s. coast guard documented vessel by official number
- list vessel inspections
- vessel certificates and statutory documents
- get vessel particulars
- get vessel
- vessel inspection deficiencies and operational controls
- list all safety deficiencies found during vessel inspections
- emergency response
- vessel summary and profile information
- get uscg marine equipment approval and certification details
- vessel technical specifications and dimensions
- list port state control inspection history for a vessel
- retrieve marine casualty incident investigation referral and enforcement action data
- maritime safety
- vessel documentation
- federal government
- coast guard
- get vessel summary
- port state control
- list vessel certificates
- get vessel dimensions, tonnage, and technical details
slug: maritime-safety
source_filename: maritime-safety.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: USCG Maritime Safety and Compliance\n  description: Unified capability for maritime safety compliance workflows combining USCG CGMIX vessel documentation, Port\n    State Control inspection records, equipment certifications, and incident investigation data. Used by port agents, marine\n    surveyors, vessel operators, and compliance professionals to verify vessel compliance with U.S. Coast Guard regulations.\n  tags:\n  - Maritime Safety\n  - Port State Control\n  - Vessel Compliance\n  - Coast Guard\n  - Federal Government\n  created: '2026-05-03'\n  modified: '2026-05-06'\nbinds:\n- namespace: env\n  keys: {}\ncapability:\n  consumes:\n  - type: http\n    namespace: cgmix\n    baseUri: https://cgmix.uscg.mil\n    description: CGMIX Maritime Information Exchange XML and web services\n    resources:\n    - name: vessel-summary\n      path: /xml/PSIXData.asmx/getVesselSummaryXMLString\n      description: Port State Information Exchange\
  \ vessel summary records\n      operations:\n      - name: get-vessel-summary\n        method: GET\n        description: Get Vessel Summary\n        inputParameters:\n        - name: VesselID\n          in: query\n          type: string\n          required: true\n          description: Official vessel number\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-particulars\n      path: /xml/PSIXData.asmx/getVesselParticularsXMLString\n      description: Vessel dimensions, tonnage, and technical specifications\n      operations:\n      - name: get-vessel-particulars\n        method: GET\n        description: Get Vessel Particulars\n        inputParameters:\n        - name: VesselID\n          in: query\n          type: string\n          required: true\n          description: Official vessel number\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: vessel-cases\n      path: /xml/PSIXData.asmx/getVesselCasesXMLString\n      description: Port State Control inspection cases\n      operations:\n      - name: get-vessel-cases\n        method: GET\n        description: Get Vessel Inspection Cases\n        inputParameters:\n        - name: VesselID\n          in: query\n          type: string\n          required: true\n          description: Official vessel number\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-deficiencies\n      path: /xml/PSIXData.asmx/getVesselDeficienciesXMLString\n      description: Vessel inspection deficiency records\n      operations:\n      - name: get-vessel-deficiencies\n        method: GET\n        description: Get Vessel Deficiencies\n        inputParameters:\n        - name: VesselID\n          in: query\n          type: string\n          required: true\n          description:\
  \ Official vessel number\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: vessel-documents\n      path: /xml/PSIXData.asmx/getVesselDocumentsXMLString\n      description: Vessel certificates and statutory documents\n      operations:\n      - name: get-vessel-documents\n        method: GET\n        description: Get Vessel Certificates and Documents\n        inputParameters:\n        - name: VesselID\n          in: query\n          type: string\n          required: true\n          description: Official vessel number\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: equipment\n      path: /xml/EquipmentData.asmx/getEquipmentDetails\n      description: USCG approved marine equipment certifications\n      operations:\n      - name: get-equipment-details\n        method: GET\n        description: Get Equipment Certification\
  \ Details\n        inputParameters:\n        - name: EquipmentId\n          in: query\n          type: string\n          required: true\n          description: USCG equipment certification ID\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: incident-reports\n      path: /xml/IIRData.asmx/getIIRReferralForEnforcementActionXMLString\n      description: Incident Investigation Report enforcement referrals\n      operations:\n      - name: get-incident-investigation-referral\n        method: GET\n        description: Get Incident Investigation Referral\n        inputParameters:\n        - name: ActivityId\n          in: query\n          type: string\n          required: true\n          description: Marine casualty investigation activity identifier\n        outputRawFormat: xml\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n \
  \   port: 8080\n    namespace: maritime-safety-api\n    description: Unified REST API for USCG maritime safety and vessel compliance workflows.\n    resources:\n    - path: /v1/vessels/{vesselId}\n      name: vessels\n      description: Vessel summary and profile information\n      operations:\n      - method: GET\n        name: get-vessel\n        description: Get comprehensive vessel information by official number\n        call: cgmix.get-vessel-summary\n        with:\n          VesselID: rest.vesselId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vessels/{vesselId}/particulars\n      name: vessel-particulars\n      description: Vessel technical specifications and dimensions\n      operations:\n      - method: GET\n        name: get-vessel-particulars\n        description: Get vessel dimensions, tonnage, and technical details\n        call: cgmix.get-vessel-particulars\n        with:\n          VesselID: rest.vesselId\n        outputParameters:\n\
  \        - type: object\n          mapping: $.\n    - path: /v1/vessels/{vesselId}/inspections\n      name: vessel-inspections\n      description: Port State Control inspection history\n      operations:\n      - method: GET\n        name: list-vessel-inspections\n        description: List all Port State Control inspection cases for a vessel\n        call: cgmix.get-vessel-cases\n        with:\n          VesselID: rest.vesselId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vessels/{vesselId}/deficiencies\n      name: vessel-deficiencies\n      description: Vessel inspection deficiencies and operational controls\n      operations:\n      - method: GET\n        name: list-vessel-deficiencies\n        description: List all inspection deficiencies for a vessel\n        call: cgmix.get-vessel-deficiencies\n        with:\n          VesselID: rest.vesselId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/vessels/{vesselId}/certificates\n\
  \      name: vessel-certificates\n      description: Vessel certificates and statutory documents\n      operations:\n      - method: GET\n        name: list-vessel-certificates\n        description: List all certificates and documents for a vessel\n        call: cgmix.get-vessel-documents\n        with:\n          VesselID: rest.vesselId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/equipment/{equipmentId}\n      name: equipment\n      description: USCG approved marine equipment certifications\n      operations:\n      - method: GET\n        name: get-equipment-certification\n        description: Get USCG marine equipment approval and certification details\n        call: cgmix.get-equipment-details\n        with:\n          EquipmentId: rest.equipmentId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /v1/incidents/{activityId}\n      name: incidents\n      description: Marine casualty incident investigation\
  \ records\n      operations:\n      - method: GET\n        name: get-incident-investigation\n        description: Get incident investigation report and enforcement referral data\n        call: cgmix.get-incident-investigation-referral\n        with:\n          ActivityId: rest.activityId\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: maritime-safety-mcp\n    transport: http\n    description: MCP server for AI-assisted maritime safety compliance and vessel research.\n    tools:\n    - name: get-vessel-summary\n      description: Retrieve summary information for a U.S. Coast Guard documented vessel by official number\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-vessel-summary\n      with:\n        VesselID: tools.vessel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-vessel-particulars\n      description: Retrieve vessel technical specifications\
  \ including dimensions, tonnage, and propulsion\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-vessel-particulars\n      with:\n        VesselID: tools.vessel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vessel-inspections\n      description: List Port State Control inspection history for a vessel\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-vessel-cases\n      with:\n        VesselID: tools.vessel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vessel-deficiencies\n      description: List all safety deficiencies found during vessel inspections\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-vessel-deficiencies\n      with:\n        VesselID: tools.vessel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: list-vessel-certificates\n      description: List\
  \ all regulatory certificates and statutory documents for a vessel\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-vessel-documents\n      with:\n        VesselID: tools.vessel_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-equipment-certification\n      description: Look up USCG approval status for marine safety equipment by certification ID\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-equipment-details\n      with:\n        EquipmentId: tools.equipment_id\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-incident-investigation\n      description: Retrieve marine casualty incident investigation referral and enforcement action data\n      hints:\n        readOnly: true\n        idempotent: true\n      call: cgmix.get-incident-investigation-referral\n      with:\n        ActivityId: tools.activity_id\n      outputParameters:\n     \
  \ - type: object\n        mapping: $.\n"
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
