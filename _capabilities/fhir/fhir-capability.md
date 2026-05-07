---
categories: []
consumed_apis: []
description: This Section describes the expected capabilities of the US Core Server actor which is responsible for providing responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations, and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should meet the ONC 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application Access - Data Category Request 170.315(g)(8) and the ONC [U.S. Core Data for Interoperability (USCDI) Version 4 July 2023](https://
layout: capability
name: Fast Healthcare Interoperability Resources (FHIR)
operations:
- description: Fast Healthcare Interoperability Resources Return the server's capability statement
  method: GET
  name: metadata
  path: /metadata
- description: Fast Healthcare Interoperability Resources Search all resources of type AllergyIntolerance based on a set of criteria
  method: GET
  name: searchallergyintolerance
  path: /AllergyIntolerance
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createallergyintolerance
  path: /AllergyIntolerance
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readallergyintolerance
  path: /AllergyIntolerance/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updateallergyintolerance
  path: /AllergyIntolerance/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchallergyintolerance
  path: /AllergyIntolerance/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deleteallergyintolerance
  path: /AllergyIntolerance/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstallergyintolerance
  path: /AllergyIntolerance/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreadallergyintolerance
  path: /AllergyIntolerance/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypeallergyintolerance
  path: /AllergyIntolerance/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type CarePlan based on a set of criteria
  method: GET
  name: searchcareplan
  path: /CarePlan
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createcareplan
  path: /CarePlan
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readcareplan
  path: /CarePlan/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatecareplan
  path: /CarePlan/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchcareplan
  path: /CarePlan/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deletecareplan
  path: /CarePlan/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstcareplan
  path: /CarePlan/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreadcareplan
  path: /CarePlan/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypecareplan
  path: /CarePlan/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type CareTeam based on a set of criteria
  method: GET
  name: searchcareteam
  path: /CareTeam
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createcareteam
  path: /CareTeam
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readcareteam
  path: /CareTeam/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatecareteam
  path: /CareTeam/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchcareteam
  path: /CareTeam/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deletecareteam
  path: /CareTeam/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstcareteam
  path: /CareTeam/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreadcareteam
  path: /CareTeam/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypecareteam
  path: /CareTeam/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type Condition based on a set of criteria
  method: GET
  name: searchcondition
  path: /Condition
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createcondition
  path: /Condition
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readcondition
  path: /Condition/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatecondition
  path: /Condition/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchcondition
  path: /Condition/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deletecondition
  path: /Condition/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstcondition
  path: /Condition/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreadcondition
  path: /Condition/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypecondition
  path: /Condition/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type Coverage based on a set of criteria
  method: GET
  name: searchcoverage
  path: /Coverage
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createcoverage
  path: /Coverage
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readcoverage
  path: /Coverage/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatecoverage
  path: /Coverage/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchcoverage
  path: /Coverage/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deletecoverage
  path: /Coverage/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstcoverage
  path: /Coverage/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreadcoverage
  path: /Coverage/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypecoverage
  path: /Coverage/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type Device based on a set of criteria
  method: GET
  name: searchdevice
  path: /Device
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: createdevice
  path: /Device
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readdevice
  path: /Device/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatedevice
  path: /Device/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchdevice
  path: /Device/{rid}
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  method: DELETE
  name: deletedevice
  path: /Device/{rid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histinstdevice
  path: /Device/{rid}/_history
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  method: GET
  name: vreaddevice
  path: /Device/{rid}/_history/{hid}
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  method: GET
  name: histtypedevice
  path: /Device/_history
- description: Fast Healthcare Interoperability Resources Search all resources of type DiagnosticReport based on a set of criteria
  method: GET
  name: searchdiagnosticreport
  path: /DiagnosticReport
- description: Fast Healthcare Interoperability Resources Create a new resource
  method: POST
  name: creatediagnosticreport
  path: /DiagnosticReport
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  method: GET
  name: readdiagnosticreport
  path: /DiagnosticReport/{rid}
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  method: PUT
  name: updatediagnosticreport
  path: /DiagnosticReport/{rid}
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  method: PATCH
  name: patchdiagnosticreport
  path: /DiagnosticReport/{rid}
personas: []
provider_name: Fast Healthcare Interoperability Resources
provider_slug: fhir
search_terms:
- api
- vreadcareplan
- histtypecoverage
- histinstcoverage
- fast healthcare interoperability resources return the server's capability statement
- patchcareplan
- updatediagnosticreport
- interoperability
- patchdevice
- deletecoverage
- deletecareteam
- readdiagnosticreport
- searchcoverage
- updateallergyintolerance
- patchdiagnosticreport
- fast healthcare interoperability resources read the current state of the resource
- patchcareteam
- updatedevice
- readcondition
- patchallergyintolerance
- metadata
- updatecareplan
- histtypeallergyintolerance
- fast healthcare interoperability resources search all resources of type condition based on a set of criteria
- fhir
- histinstcareplan
- updatecareteam
- vreaddevice
- deletecareplan
- createdevice
- fast healthcare interoperability resources search all resources of type diagnosticreport based on a set of criteria
- deletecondition
- histinstallergyintolerance
- fast healthcare interoperability resources delete the resource so that it no exists (no read, search etc)
- searchcareplan
- histinstcareteam
- histtypecareplan
- histinstcondition
- patchcondition
- deletedevice
- fast healthcare interoperability resources search all resources of type device based on a set of criteria
- createcondition
- readdevice
- histtypecareteam
- searchcareteam
- patchcoverage
- fast healthcare interoperability resources read a past state of the resource
- vreadallergyintolerance
- readcareteam
- searchdiagnosticreport
- createcoverage
- histtypedevice
- fast healthcare interoperability resources create a new resource
- creatediagnosticreport
- fast healthcare interoperability resources change the current state of the resource by providing a patch - a series of change commands
- readallergyintolerance
- fast healthcare interoperability resources update the current state of the resource
- histtypecondition
- createcareteam
- updatecondition
- vreadcondition
- fast healthcare interoperability resources search all resources of type careteam based on a set of criteria
- histinstdevice
- fast healthcare interoperability resources search all resources of type coverage based on a set of criteria
- fast healthcare interoperability resources search all resources of type allergyintolerance based on a set of criteria
- searchcondition
- vreadcareteam
- standards
- createcareplan
- searchdevice
- healthcare
- vreadcoverage
- readcoverage
- fast healthcare interoperability resources search all resources of type careplan based on a set of criteria
- fast healthcare interoperability resources read the past states of the resource
- searchallergyintolerance
- createallergyintolerance
- deleteallergyintolerance
- updatecoverage
- readcareplan
slug: fhir-capability
source_filename: fhir-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Fast Healthcare Interoperability Resources (FHIR)\n  description: This Section describes the expected capabilities of the US Core Server actor which is responsible for providing\n    responses to the queries submitted by the US Core Requestors. The complete list of FHIR profiles, RESTful operations,\n    and search parameters supported by US Core Servers are defined. Systems implementing this capability statement should\n    meet the ONC 2015 Common Clinical Data Set (CCDS) access requirement for Patient Selection 170.315(g)(7) and Application\n    Access - Data Category Request 170.315(g)(8) and the ONC [U.S. Core Data for Interoperability (USCDI) Version 4 July 2023](https://\n  tags:\n  - Fhir\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: fhir\n    baseUri: https://api.example.com\n    description: Fast Healthcare Interoperability Resources (FHIR) HTTP API.\n  \
  \  resources:\n    - name: metadata\n      path: /metadata\n      operations:\n      - name: metadata\n        method: GET\n        description: Fast Healthcare Interoperability Resources Return the server's capability statement\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance\n      path: /AllergyIntolerance\n      operations:\n      - name: searchallergyintolerance\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type AllergyIntolerance based on a\n          set of criteria\n        inputParameters:\n        - name: clinical-status\n          in: query\n          type: string\n          description: '**active | inactive | resolved** **NOTE**: This US Core SearchParameter definition extends the usage\n            context of the [Conformance expectation extension](http://h'\n        - name: patient\n          in: query\n\
  \          type: string\n          description: '**Who the sensitivity is for** **NOTE**: This US Core SearchParameter definition extends the usage\n            context of the [Conformance expectation extension](http://hl7'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createallergyintolerance\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance-rid\n      path: /AllergyIntolerance/{rid}\n      operations:\n      - name: readallergyintolerance\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n        \
  \  value: $.\n      - name: updateallergyintolerance\n        method: PUT\n        description: Fast Healthcare Interoperability Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchallergyintolerance\n        method: PATCH\n        description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deleteallergyintolerance\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: allergyintolerance-rid-history\n      path: /AllergyIntolerance/{rid}/_history\n      operations:\n      - name: histinstallergyintolerance\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance-rid-history-hid\n      path: /AllergyIntolerance/{rid}/_history/{hid}\n      operations:\n      - name: vreadallergyintolerance\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: allergyintolerance-history\n      path: /AllergyIntolerance/_history\n      operations:\n      - name: histtypeallergyintolerance\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n        \
  \  type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan\n      path: /CarePlan\n      operations:\n      - name: searchcareplan\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type CarePlan based on a set of criteria\n        inputParameters:\n        - name: category\n          in: query\n          type: string\n          description: '**Type of plan** **NOTE**: This US Core SearchParameter definition extends the usage\
  \ context of the\n            [Conformance expectation extension](http://hl7.org/fhir/R4/e'\n        - name: date\n          in: query\n          type: string\n          description: '**Time period plan covers** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.or'\n        - name: patient\n          in: query\n          type: string\n          description: '**Who the care plan is for** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.o'\n        - name: status\n          in: query\n          type: string\n          description: '**draft | active | on-hold | revoked | completed | entered-in-error | unknown** **NOTE**: This US\n            Core SearchParameter definition extends the usage context of t'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n      - name: createcareplan\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan-rid\n      path: /CarePlan/{rid}\n      operations:\n      - name: readcareplan\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecareplan\n        method: PUT\n        description: Fast Healthcare Interoperability Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchcareplan\n        method: PATCH\n        description: Fast\
  \ Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecareplan\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan-rid-history\n      path: /CarePlan/{rid}/_history\n      operations:\n      - name: histinstcareplan\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created\
  \ at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careplan-rid-history-hid\n      path: /CarePlan/{rid}/_history/{hid}\n      operations:\n      - name: vreadcareplan\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n\
  \          value: $.\n    - name: careplan-history\n      path: /CarePlan/_history\n      operations:\n      - name: histtypecareplan\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n  \
  \      - name: result\n          type: object\n          value: $.\n    - name: careteam\n      path: /CareTeam\n      operations:\n      - name: searchcareteam\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type CareTeam based on a set of criteria\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: '**Who care team is for** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.org/f'\n        - name: role\n          in: query\n          type: string\n          description: Returns CareTeam resources with a participant role matching the specified code.\n        - name: status\n          in: query\n          type: string\n          description: '**proposed | active | suspended | inactive | entered-in-error** **NOTE**: This US Core SearchParameter\n            definition\
  \ extends the usage context of the [Conformance '\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcareteam\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careteam-rid\n      path: /CareTeam/{rid}\n      operations:\n      - name: readcareteam\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecareteam\n        method: PUT\n        description: Fast Healthcare Interoperability Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n      - name: patchcareteam\n        method: PATCH\n        description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecareteam\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careteam-rid-history\n      path: /CareTeam/{rid}/_history\n      operations:\n      - name: histinstcareteam\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n\
  \        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careteam-rid-history-hid\n      path: /CareTeam/{rid}/_history/{hid}\n      operations:\n      - name: vreadcareteam\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read\
  \ a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: careteam-history\n      path: /CareTeam/_history\n      operations:\n      - name: histtypecareteam\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced\
  \ in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition\n      path: /Condition\n      operations:\n      - name: searchcondition\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type Condition based on a set of criteria\n        inputParameters:\n        - name: abatement-date\n          in: query\n          type: string\n          description: '**Date-related abatements (dateTime and period)** **NOTE**: This US Core SearchParameter definition\n            extends the usage context of the [Conformance expectation ex'\n        - name: asserted-date\n          in: query\n          type: string\n          description: Returns conditions with an [assertedDate extension](http://hl7.org/fhir/StructureDefinition/condition-assertedDate)\n            matching the specified\
  \ date (dateTime).\n        - name: category\n          in: query\n          type: string\n          description: '**The category of the condition** **NOTE**: This US Core SearchParameter definition extends the usage\n            context of the [Conformance expectation extension](http://'\n        - name: clinical-status\n          in: query\n          type: string\n          description: '**The clinical status of the condition** **NOTE**: This US Core SearchParameter definition extends\n            the usage context of the [Conformance expectation extension]('\n        - name: code\n          in: query\n          type: string\n          description: '**Code for the condition** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.org'\n        - name: encounter\n          in: query\n          type: string\n          description: '**Encounter created as part of** **NOTE**: This US Core SearchParameter\
  \ definition extends the usage\n            context of the [Conformance expectation extension](http://h'\n        - name: onset-date\n          in: query\n          type: string\n          description: '**Date related onsets (dateTime and Period)** **NOTE**: This US Core SearchParameter definition extends\n            the usage context of the [Conformance expectation extens'\n        - name: patient\n          in: query\n          type: string\n          description: '**Who has the condition?** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.org'\n        - name: recorded-date\n          in: query\n          type: string\n          description: '**Date record was first recorded** **NOTE**: This US Core SearchParameter definition extends the usage\n            context of the [Conformance expectation extension](http:/'\n        - name: _lastUpdated\n          in: query\n          type: string\n\
  \          description: '**When the resource version last changed** **NOTE**: This US Core SearchParameter definition extends\n            the usage context of the [Conformance expectation extension'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createcondition\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition-rid\n      path: /Condition/{rid}\n      operations:\n      - name: readcondition\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecondition\n        method: PUT\n\
  \        description: Fast Healthcare Interoperability Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchcondition\n        method: PATCH\n        description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecondition\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition-rid-history\n      path: /Condition/{rid}/_history\n      operations:\n   \
  \   - name: histinstcondition\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition-rid-history-hid\n\
  \      path: /Condition/{rid}/_history/{hid}\n      operations:\n      - name: vreadcondition\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: condition-history\n      path: /Condition/_history\n      operations:\n      - name: histtypecondition\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time\
  \ value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage\n      path: /Coverage\n      operations:\n      - name: searchcoverage\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type Coverage based on a set of criteria\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: '**Retrieve coverages for a patient** **NOTE**: This US Core SearchParameter definition extends the\n            usage context of the [Conformance expectation extension](http'\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n      - name: createcoverage\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage-rid\n      path: /Coverage/{rid}\n      operations:\n      - name: readcoverage\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatecoverage\n        method: PUT\n        description: Fast Healthcare Interoperability Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchcoverage\n        method:\
  \ PATCH\n        description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletecoverage\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage-rid-history\n      path: /Coverage/{rid}/_history\n      operations:\n      - name: histinstcoverage\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include\
  \ resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: coverage-rid-history-hid\n      path: /Coverage/{rid}/_history/{hid}\n      operations:\n      - name: vreadcoverage\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name:\
  \ result\n          type: object\n          value: $.\n    - name: coverage-history\n      path: /Coverage/_history\n      operations:\n      - name: histtypecoverage\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device\n      path: /Device\n      operations:\n      - name: searchdevice\n        method: GET\n        description: Fast Healthcare Interoperability Resources Search all resources of type Device based on a set of criteria\n        inputParameters:\n        - name: patient\n          in: query\n          type: string\n          description: '**Patient information, if the resource is affixed to a person** **NOTE**: This US Core SearchParameter\n            definition extends the usage context of the [Conformance '\n        - name: status\n          in: query\n          type: string\n          description: '**active | inactive | entered-in-error | unknown** **NOTE**: This US Core SearchParameter definition\n            extends the usage context of the [Conformance expectation e'\n        - name: type\n          in: query\n          type: string\n          description: '**The type\
  \ of the device** **NOTE**: This US Core SearchParameter definition extends the usage context\n            of the [Conformance expectation extension](http://hl7.org'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: createdevice\n        method: POST\n        description: Fast Healthcare Interoperability Resources Create a new resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-rid\n      path: /Device/{rid}\n      operations:\n      - name: readdevice\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: updatedevice\n        method: PUT\n        description: Fast Healthcare Interoperability\
  \ Resources Update the current state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: patchdevice\n        method: PATCH\n        description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch\n          - a series of change commands\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n      - name: deletedevice\n        method: DELETE\n        description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search\n          etc)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-rid-history\n      path: /Device/{rid}/_history\n      operations:\n      - name: histinstdevice\n        method: GET\n        description:\
  \ Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: string\n          description: Only include resource versions that were created at or after the given instant in time\n        - name: _at\n          in: query\n          type: string\n          description: Only include resource versions that were current at some point during the time period specified in\n            the date time value (see Search notes on date searching)\n        - name: _list\n          in: query\n          type: string\n          description: Only include resource versions that are referenced in the specified list (current list references are\n            allowed)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-rid-history-hid\n      path: /Device/{rid}/_history/{hid}\n      operations:\n      - name:\
  \ vreaddevice\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read a past state of the resource\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: device-history\n      path: /Device/_history\n      operations:\n      - name: histtypedevice\n        method: GET\n        description: Fast Healthcare Interoperability Resources Read the past states of the resource\n        inputParameters:\n        - name: _since\n          in: query\n          type: s\n\n# --- truncated at 32 KB (91 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/fhir/refs/heads/main/capabilities/fhir-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/fhir/refs/heads/main/capabilities/fhir-capability.yaml
tags:
- Fhir
- API
tools:
- description: Fast Healthcare Interoperability Resources Return the server's capability statement
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: metadata
- description: Fast Healthcare Interoperability Resources Search all resources of type AllergyIntolerance based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchallergyintolerance
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createallergyintolerance
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readallergyintolerance
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updateallergyintolerance
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchallergyintolerance
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deleteallergyintolerance
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstallergyintolerance
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreadallergyintolerance
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypeallergyintolerance
- description: Fast Healthcare Interoperability Resources Search all resources of type CarePlan based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcareplan
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcareplan
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readcareplan
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecareplan
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcareplan
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecareplan
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstcareplan
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreadcareplan
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypecareplan
- description: Fast Healthcare Interoperability Resources Search all resources of type CareTeam based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcareteam
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcareteam
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readcareteam
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecareteam
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcareteam
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecareteam
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstcareteam
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreadcareteam
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypecareteam
- description: Fast Healthcare Interoperability Resources Search all resources of type Condition based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcondition
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcondition
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readcondition
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecondition
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcondition
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecondition
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstcondition
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreadcondition
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypecondition
- description: Fast Healthcare Interoperability Resources Search all resources of type Coverage based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchcoverage
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createcoverage
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readcoverage
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatecoverage
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchcoverage
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletecoverage
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstcoverage
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreadcoverage
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypecoverage
- description: Fast Healthcare Interoperability Resources Search all resources of type Device based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdevice
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: createdevice
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readdevice
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatedevice
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdevice
- description: Fast Healthcare Interoperability Resources Delete the resource so that it no exists (no read, search etc)
  hints:
    destructive: true
    idempotent: true
    readOnly: false
  name: deletedevice
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histinstdevice
- description: Fast Healthcare Interoperability Resources Read a past state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: vreaddevice
- description: Fast Healthcare Interoperability Resources Read the past states of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: histtypedevice
- description: Fast Healthcare Interoperability Resources Search all resources of type DiagnosticReport based on a set of criteria
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: searchdiagnosticreport
- description: Fast Healthcare Interoperability Resources Create a new resource
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: creatediagnosticreport
- description: Fast Healthcare Interoperability Resources Read the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: readdiagnosticreport
- description: Fast Healthcare Interoperability Resources Update the current state of the resource
  hints:
    destructive: false
    idempotent: true
    readOnly: false
  name: updatediagnosticreport
- description: Fast Healthcare Interoperability Resources Change the current state of the resource by providing a patch - a series of change commands
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: patchdiagnosticreport
---
