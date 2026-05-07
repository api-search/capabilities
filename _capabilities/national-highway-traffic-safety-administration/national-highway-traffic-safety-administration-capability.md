---
categories: []
consumed_apis: []
description: The NHTSA Product Information Catalog Vehicle Listing (vPIC) API provides endpoints to gather information on vehicles and their specifications, including decoding Vehicle Identification Numbers (VINs), accessing manufacturer details, and retrieving make, model, and equipment data. The vPIC dataset is populated using information submitted by motor vehicle manufacturers through the Part 565 submittals.
layout: capability
name: NHTSA vPIC Vehicle API
operations:
- description: Decode a VIN
  method: GET
  name: get-decodevin-vin
  path: /DecodeVin/{vin}
- description: Decode a VIN (flat values)
  method: GET
  name: get-decodevinvalues-vin
  path: /DecodeVinValues/{vin}
- description: Decode a VIN with extended details
  method: GET
  name: get-decodevinextended-vin
  path: /DecodeVinExtended/{vin}
- description: Decode a VIN with extended details (flat values)
  method: GET
  name: get-decodevinvaluesextended-vin
  path: /DecodeVinValuesExtended/{vin}
- description: Batch decode multiple VINs
  method: POST
  name: post-decodevinvaluesbatch
  path: /DecodeVINValuesBatch/
- description: Decode a World Manufacturer Identifier
  method: GET
  name: get-decodewmi-wmi
  path: /DecodeWMI/{wmi}
- description: Get WMIs for a manufacturer
  method: GET
  name: get-getwmisformanufacturer-manufacturer
  path: /GetWMIsForManufacturer/{manufacturer}
- description: Get all manufacturers
  method: GET
  name: get-getallmanufacturers
  path: /GetAllManufacturers
- description: Get manufacturer details
  method: GET
  name: get-getmanufacturerdetails-manufacturer
  path: /GetManufacturerDetails/{manufacturer}
- description: Get all makes
  method: GET
  name: get-getallmakes
  path: /GetAllMakes
- description: Get makes for a manufacturer
  method: GET
  name: get-getmakeformanufacturer-manufacturer
  path: /GetMakeForManufacturer/{manufacturer}
- description: Get makes for a manufacturer and year
  method: GET
  name: get-getmakesformanufacturerandyear-manufacturer
  path: /GetMakesForManufacturerAndYear/{manufacturer}
- description: Get makes for a vehicle type
  method: GET
  name: get-getmakesforvehicletype-vehicletype
  path: /GetMakesForVehicleType/{vehicleType}
- description: Get models for a make
  method: GET
  name: get-getmodelsformake-makename
  path: /GetModelsForMake/{makeName}
- description: Get models for a make ID
  method: GET
  name: get-getmodelsformakeid-makeid
  path: /GetModelsForMakeId/{makeId}
- description: Get models for a make and model year
  method: GET
  name: get-getmodelsformakeyear-make-make-modelyear-mod
  path: /GetModelsForMakeYear/make/{make}/modelyear/{modelyear}
- description: Get models for a make ID and model year
  method: GET
  name: get-getmodelsformakeidyear-makeid-makeid-modelye
  path: /GetModelsForMakeIdYear/makeId/{makeId}/modelyear/{modelyear}
- description: Get vehicle types for a make
  method: GET
  name: get-getvehicletypesformake-makename
  path: /GetVehicleTypesForMake/{makeName}
- description: Get vehicle types for a make ID
  method: GET
  name: get-getvehicletypesformakeid-makeid
  path: /GetVehicleTypesForMakeId/{makeId}
- description: Get list of vehicle variables
  method: GET
  name: get-getvehiclevariablelist
  path: /GetVehicleVariableList
- description: Get values for a vehicle variable
  method: GET
  name: get-getvehiclevariablevalueslist-variable
  path: /GetVehicleVariableValuesList/{variable}
- description: Get equipment plant codes
  method: GET
  name: get-getequipmentplantcodes
  path: /GetEquipmentPlantCodes
- description: Get parts
  method: GET
  name: get-getparts
  path: /GetParts
- description: Get Canadian vehicle specifications
  method: GET
  name: get-getcanadianvehiclespecifications
  path: /GetCanadianVehicleSpecifications/
personas: []
provider_name: National Highway Traffic Safety Administration
provider_slug: national-highway-traffic-safety-administration
search_terms:
- get decodevin vin
- get vehicle types for a make id
- get decodevinvaluesextended vin
- get all manufacturers
- get parts
- get list of vehicle variables
- get decodevinvalues vin
- decode a vin with extended details (flat values)
- get getmodelsformake makename
- decode a vin (flat values)
- get wmis for a manufacturer
- api
- get models for a make id
- get decodevinextended vin
- get decodewmi wmi
- safety
- vehicles
- get getparts
- get getvehicletypesformake makename
- decode a world manufacturer identifier
- get makes for a manufacturer and year
- get models for a make
- get getmodelsformakeidyear makeid makeid modelye
- administration
- get getvehiclevariablelist
- transportation
- get makes for a vehicle type
- highway
- get makes for a manufacturer
- traffic
- get getmakesforvehicletype vehicletype
- get models for a make and model year
- get values for a vehicle variable
- get getmanufacturerdetails manufacturer
- get getvehicletypesformakeid makeid
- get getallmakes
- get getwmisformanufacturer manufacturer
- decode a vin
- get all makes
- get getequipmentplantcodes
- get equipment plant codes
- batch decode multiple vins
- get manufacturer details
- get getvehiclevariablevalueslist variable
- get getmakeformanufacturer manufacturer
- post decodevinvaluesbatch
- get getcanadianvehiclespecifications
- get getmakesformanufacturerandyear manufacturer
- get getmodelsformakeid makeid
- get canadian vehicle specifications
- get vehicle types for a make
- get getallmanufacturers
- get models for a make id and model year
- federal government
- get getmodelsformakeyear make make modelyear mod
- decode a vin with extended details
- national
slug: national-highway-traffic-safety-administration-capability
source_filename: national-highway-traffic-safety-administration-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: NHTSA vPIC Vehicle API\n  description: The NHTSA Product Information Catalog Vehicle Listing (vPIC) API provides endpoints to gather information on\n    vehicles and their specifications, including decoding Vehicle Identification Numbers (VINs), accessing manufacturer details,\n    and retrieving make, model, and equipment data. The vPIC dataset is populated using information submitted by motor vehicle\n    manufacturers through the Part 565 submittals.\n  tags:\n  - National\n  - Highway\n  - Traffic\n  - Safety\n  - Administration\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: national-highway-traffic-safety-administration\n    baseUri: https://vpic.nhtsa.dot.gov/api/vehicles\n    description: NHTSA vPIC Vehicle API HTTP API.\n    resources:\n    - name: decodevin-vin\n      path: /DecodeVin/{vin}\n      operations:\n      - name: get-decodevin-vin\n        method:\
  \ GET\n        description: Decode a VIN\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decodevinvalues-vin\n      path: /DecodeVinValues/{vin}\n      operations:\n      - name: get-decodevinvalues-vin\n        method: GET\n        description: Decode a VIN (flat values)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decodevinextended-vin\n      path: /DecodeVinExtended/{vin}\n      operations:\n      - name: get-decodevinextended-vin\n        method: GET\n        description: Decode a VIN with extended details\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decodevinvaluesextended-vin\n      path: /DecodeVinValuesExtended/{vin}\n      operations:\n      - name: get-decodevinvaluesextended-vin\n        method: GET\n\
  \        description: Decode a VIN with extended details (flat values)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decodevinvaluesbatch\n      path: /DecodeVINValuesBatch/\n      operations:\n      - name: post-decodevinvaluesbatch\n        method: POST\n        description: Batch decode multiple VINs\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: decodewmi-wmi\n      path: /DecodeWMI/{wmi}\n      operations:\n      - name: get-decodewmi-wmi\n        method: GET\n        description: Decode a World Manufacturer Identifier\n        inputParameters:\n        - name: wmi\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getwmisformanufacturer-manufacturer\n\
  \      path: /GetWMIsForManufacturer/{manufacturer}\n      operations:\n      - name: get-getwmisformanufacturer-manufacturer\n        method: GET\n        description: Get WMIs for a manufacturer\n        inputParameters:\n        - name: manufacturer\n          in: path\n          type: string\n          required: true\n        - name: vehicleType\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getallmanufacturers\n      path: /GetAllManufacturers\n      operations:\n      - name: get-getallmanufacturers\n        method: GET\n        description: Get all manufacturers\n        inputParameters:\n        - name: ManufacturerType\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n     \
  \     value: $.\n    - name: getmanufacturerdetails-manufacturer\n      path: /GetManufacturerDetails/{manufacturer}\n      operations:\n      - name: get-getmanufacturerdetails-manufacturer\n        method: GET\n        description: Get manufacturer details\n        inputParameters:\n        - name: manufacturer\n          in: path\n          type: string\n          required: true\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getallmakes\n      path: /GetAllMakes\n      operations:\n      - name: get-getallmakes\n        method: GET\n        description: Get all makes\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getmakeformanufacturer-manufacturer\n      path: /GetMakeForManufacturer/{manufacturer}\n      operations:\n      - name:\
  \ get-getmakeformanufacturer-manufacturer\n        method: GET\n        description: Get makes for a manufacturer\n        inputParameters:\n        - name: manufacturer\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getmakesformanufacturerandyear-manufacturer\n      path: /GetMakesForManufacturerAndYear/{manufacturer}\n      operations:\n      - name: get-getmakesformanufacturerandyear-manufacturer\n        method: GET\n        description: Get makes for a manufacturer and year\n        inputParameters:\n        - name: manufacturer\n          in: path\n          type: string\n          required: true\n        - name: year\n          in: query\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    -\
  \ name: getmakesforvehicletype-vehicletype\n      path: /GetMakesForVehicleType/{vehicleType}\n      operations:\n      - name: get-getmakesforvehicletype-vehicletype\n        method: GET\n        description: Get makes for a vehicle type\n        inputParameters:\n        - name: vehicleType\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getmodelsformake-makename\n      path: /GetModelsForMake/{makeName}\n      operations:\n      - name: get-getmodelsformake-makename\n        method: GET\n        description: Get models for a make\n        inputParameters:\n        - name: makeName\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getmodelsformakeid-makeid\n      path:\
  \ /GetModelsForMakeId/{makeId}\n      operations:\n      - name: get-getmodelsformakeid-makeid\n        method: GET\n        description: Get models for a make ID\n        inputParameters:\n        - name: makeId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getmodelsformakeyear-make-make-modelyear-modelye\n      path: /GetModelsForMakeYear/make/{make}/modelyear/{modelyear}\n      operations:\n      - name: get-getmodelsformakeyear-make-make-modelyear-mod\n        method: GET\n        description: Get models for a make and model year\n        inputParameters:\n        - name: make\n          in: path\n          type: string\n          required: true\n        - name: modelyear\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n\
  \          type: object\n          value: $.\n    - name: getmodelsformakeidyear-makeid-makeid-modelyear-m\n      path: /GetModelsForMakeIdYear/makeId/{makeId}/modelyear/{modelyear}\n      operations:\n      - name: get-getmodelsformakeidyear-makeid-makeid-modelye\n        method: GET\n        description: Get models for a make ID and model year\n        inputParameters:\n        - name: makeId\n          in: path\n          type: integer\n          required: true\n        - name: modelyear\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getvehicletypesformake-makename\n      path: /GetVehicleTypesForMake/{makeName}\n      operations:\n      - name: get-getvehicletypesformake-makename\n        method: GET\n        description: Get vehicle types for a make\n        inputParameters:\n        - name: makeName\n          in: path\n\
  \          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getvehicletypesformakeid-makeid\n      path: /GetVehicleTypesForMakeId/{makeId}\n      operations:\n      - name: get-getvehicletypesformakeid-makeid\n        method: GET\n        description: Get vehicle types for a make ID\n        inputParameters:\n        - name: makeId\n          in: path\n          type: integer\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getvehiclevariablelist\n      path: /GetVehicleVariableList\n      operations:\n      - name: get-getvehiclevariablelist\n        method: GET\n        description: Get list of vehicle variables\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n \
  \   - name: getvehiclevariablevalueslist-variable\n      path: /GetVehicleVariableValuesList/{variable}\n      operations:\n      - name: get-getvehiclevariablevalueslist-variable\n        method: GET\n        description: Get values for a vehicle variable\n        inputParameters:\n        - name: variable\n          in: path\n          type: string\n          required: true\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getequipmentplantcodes\n      path: /GetEquipmentPlantCodes\n      operations:\n      - name: get-getequipmentplantcodes\n        method: GET\n        description: Get equipment plant codes\n        inputParameters:\n        - name: year\n          in: query\n          type: integer\n          required: true\n        - name: equipmentType\n          in: query\n          type: integer\n        - name: reportType\n          in: query\n          type: string\n        outputRawFormat:\
  \ json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getparts\n      path: /GetParts\n      operations:\n      - name: get-getparts\n        method: GET\n        description: Get parts\n        inputParameters:\n        - name: type\n          in: query\n          type: integer\n        - name: fromDate\n          in: query\n          type: string\n        - name: toDate\n          in: query\n          type: string\n        - name: manufacturer\n          in: query\n          type: string\n        - name: page\n          in: query\n          type: integer\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: getcanadianvehiclespecifications\n      path: /GetCanadianVehicleSpecifications/\n      operations:\n      - name: get-getcanadianvehiclespecifications\n        method: GET\n        description: Get Canadian vehicle specifications\n  \
  \      inputParameters:\n        - name: year\n          in: query\n          type: integer\n          required: true\n        - name: make\n          in: query\n          type: string\n          required: true\n        - name: model\n          in: query\n          type: string\n        - name: units\n          in: query\n          type: string\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: national-highway-traffic-safety-administration-rest\n    description: REST adapter for NHTSA vPIC Vehicle API.\n    resources:\n    - path: /DecodeVin/{vin}\n      name: get-decodevin-vin\n      operations:\n      - method: GET\n        name: get-decodevin-vin\n        description: Decode a VIN\n        call: national-highway-traffic-safety-administration.get-decodevin-vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DecodeVinValues/{vin}\n\
  \      name: get-decodevinvalues-vin\n      operations:\n      - method: GET\n        name: get-decodevinvalues-vin\n        description: Decode a VIN (flat values)\n        call: national-highway-traffic-safety-administration.get-decodevinvalues-vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DecodeVinExtended/{vin}\n      name: get-decodevinextended-vin\n      operations:\n      - method: GET\n        name: get-decodevinextended-vin\n        description: Decode a VIN with extended details\n        call: national-highway-traffic-safety-administration.get-decodevinextended-vin\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DecodeVinValuesExtended/{vin}\n      name: get-decodevinvaluesextended-vin\n      operations:\n      - method: GET\n        name: get-decodevinvaluesextended-vin\n        description: Decode a VIN with extended details (flat values)\n        call: national-highway-traffic-safety-administration.get-decodevinvaluesextended-vin\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DecodeVINValuesBatch/\n      name: post-decodevinvaluesbatch\n      operations:\n      - method: POST\n        name: post-decodevinvaluesbatch\n        description: Batch decode multiple VINs\n        call: national-highway-traffic-safety-administration.post-decodevinvaluesbatch\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /DecodeWMI/{wmi}\n      name: get-decodewmi-wmi\n      operations:\n      - method: GET\n        name: get-decodewmi-wmi\n        description: Decode a World Manufacturer Identifier\n        call: national-highway-traffic-safety-administration.get-decodewmi-wmi\n        with:\n          wmi: rest.wmi\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetWMIsForManufacturer/{manufacturer}\n      name: get-getwmisformanufacturer-manufacturer\n      operations:\n      - method: GET\n        name: get-getwmisformanufacturer-manufacturer\n\
  \        description: Get WMIs for a manufacturer\n        call: national-highway-traffic-safety-administration.get-getwmisformanufacturer-manufacturer\n        with:\n          manufacturer: rest.manufacturer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetAllManufacturers\n      name: get-getallmanufacturers\n      operations:\n      - method: GET\n        name: get-getallmanufacturers\n        description: Get all manufacturers\n        call: national-highway-traffic-safety-administration.get-getallmanufacturers\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetManufacturerDetails/{manufacturer}\n      name: get-getmanufacturerdetails-manufacturer\n      operations:\n      - method: GET\n        name: get-getmanufacturerdetails-manufacturer\n        description: Get manufacturer details\n        call: national-highway-traffic-safety-administration.get-getmanufacturerdetails-manufacturer\n        with:\n\
  \          manufacturer: rest.manufacturer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetAllMakes\n      name: get-getallmakes\n      operations:\n      - method: GET\n        name: get-getallmakes\n        description: Get all makes\n        call: national-highway-traffic-safety-administration.get-getallmakes\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetMakeForManufacturer/{manufacturer}\n      name: get-getmakeformanufacturer-manufacturer\n      operations:\n      - method: GET\n        name: get-getmakeformanufacturer-manufacturer\n        description: Get makes for a manufacturer\n        call: national-highway-traffic-safety-administration.get-getmakeformanufacturer-manufacturer\n        with:\n          manufacturer: rest.manufacturer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetMakesForManufacturerAndYear/{manufacturer}\n      name: get-getmakesformanufacturerandyear-manufacturer\n\
  \      operations:\n      - method: GET\n        name: get-getmakesformanufacturerandyear-manufacturer\n        description: Get makes for a manufacturer and year\n        call: national-highway-traffic-safety-administration.get-getmakesformanufacturerandyear-manufacturer\n        with:\n          manufacturer: rest.manufacturer\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetMakesForVehicleType/{vehicleType}\n      name: get-getmakesforvehicletype-vehicletype\n      operations:\n      - method: GET\n        name: get-getmakesforvehicletype-vehicletype\n        description: Get makes for a vehicle type\n        call: national-highway-traffic-safety-administration.get-getmakesforvehicletype-vehicletype\n        with:\n          vehicleType: rest.vehicleType\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetModelsForMake/{makeName}\n      name: get-getmodelsformake-makename\n      operations:\n      - method:\
  \ GET\n        name: get-getmodelsformake-makename\n        description: Get models for a make\n        call: national-highway-traffic-safety-administration.get-getmodelsformake-makename\n        with:\n          makeName: rest.makeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetModelsForMakeId/{makeId}\n      name: get-getmodelsformakeid-makeid\n      operations:\n      - method: GET\n        name: get-getmodelsformakeid-makeid\n        description: Get models for a make ID\n        call: national-highway-traffic-safety-administration.get-getmodelsformakeid-makeid\n        with:\n          makeId: rest.makeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetModelsForMakeYear/make/{make}/modelyear/{modelyear}\n      name: get-getmodelsformakeyear-make-make-modelyear-mod\n      operations:\n      - method: GET\n        name: get-getmodelsformakeyear-make-make-modelyear-mod\n        description: Get\
  \ models for a make and model year\n        call: national-highway-traffic-safety-administration.get-getmodelsformakeyear-make-make-modelyear-mod\n        with:\n          make: rest.make\n          modelyear: rest.modelyear\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetModelsForMakeIdYear/makeId/{makeId}/modelyear/{modelyear}\n      name: get-getmodelsformakeidyear-makeid-makeid-modelye\n      operations:\n      - method: GET\n        name: get-getmodelsformakeidyear-makeid-makeid-modelye\n        description: Get models for a make ID and model year\n        call: national-highway-traffic-safety-administration.get-getmodelsformakeidyear-makeid-makeid-modelye\n        with:\n          makeId: rest.makeId\n          modelyear: rest.modelyear\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetVehicleTypesForMake/{makeName}\n      name: get-getvehicletypesformake-makename\n      operations:\n      - method:\
  \ GET\n        name: get-getvehicletypesformake-makename\n        description: Get vehicle types for a make\n        call: national-highway-traffic-safety-administration.get-getvehicletypesformake-makename\n        with:\n          makeName: rest.makeName\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetVehicleTypesForMakeId/{makeId}\n      name: get-getvehicletypesformakeid-makeid\n      operations:\n      - method: GET\n        name: get-getvehicletypesformakeid-makeid\n        description: Get vehicle types for a make ID\n        call: national-highway-traffic-safety-administration.get-getvehicletypesformakeid-makeid\n        with:\n          makeId: rest.makeId\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetVehicleVariableList\n      name: get-getvehiclevariablelist\n      operations:\n      - method: GET\n        name: get-getvehiclevariablelist\n        description: Get list of vehicle variables\n\
  \        call: national-highway-traffic-safety-administration.get-getvehiclevariablelist\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetVehicleVariableValuesList/{variable}\n      name: get-getvehiclevariablevalueslist-variable\n      operations:\n      - method: GET\n        name: get-getvehiclevariablevalueslist-variable\n        description: Get values for a vehicle variable\n        call: national-highway-traffic-safety-administration.get-getvehiclevariablevalueslist-variable\n        with:\n          variable: rest.variable\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetEquipmentPlantCodes\n      name: get-getequipmentplantcodes\n      operations:\n      - method: GET\n        name: get-getequipmentplantcodes\n        description: Get equipment plant codes\n        call: national-highway-traffic-safety-administration.get-getequipmentplantcodes\n        outputParameters:\n        - type: object\n\
  \          mapping: $.\n    - path: /GetParts\n      name: get-getparts\n      operations:\n      - method: GET\n        name: get-getparts\n        description: Get parts\n        call: national-highway-traffic-safety-administration.get-getparts\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /GetCanadianVehicleSpecifications/\n      name: get-getcanadianvehiclespecifications\n      operations:\n      - method: GET\n        name: get-getcanadianvehiclespecifications\n        description: Get Canadian vehicle specifications\n        call: national-highway-traffic-safety-administration.get-getcanadianvehiclespecifications\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: national-highway-traffic-safety-administration-mcp\n    transport: http\n    description: MCP adapter for NHTSA vPIC Vehicle API for AI agent use.\n    tools:\n    - name: get-decodevin-vin\n      description: Decode\
  \ a VIN\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-decodevin-vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-decodevinvalues-vin\n      description: Decode a VIN (flat values)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-decodevinvalues-vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-decodevinextended-vin\n      description: Decode a VIN with extended details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-decodevinextended-vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-decodevinvaluesextended-vin\n      description: Decode a VIN with extended\
  \ details (flat values)\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-decodevinvaluesextended-vin\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: post-decodevinvaluesbatch\n      description: Batch decode multiple VINs\n      hints:\n        readOnly: false\n        destructive: false\n        idempotent: false\n      call: national-highway-traffic-safety-administration.post-decodevinvaluesbatch\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-decodewmi-wmi\n      description: Decode a World Manufacturer Identifier\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-decodewmi-wmi\n      with:\n        wmi: tools.wmi\n      inputParameters:\n      - name: wmi\n        type: string\n        description: wmi\n\
  \        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getwmisformanufacturer-manufacturer\n      description: Get WMIs for a manufacturer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getwmisformanufacturer-manufacturer\n      with:\n        manufacturer: tools.manufacturer\n        vehicleType: tools.vehicleType\n      inputParameters:\n      - name: manufacturer\n        type: string\n        description: manufacturer\n        required: true\n      - name: vehicleType\n        type: string\n        description: vehicleType\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getallmanufacturers\n      description: Get all manufacturers\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getallmanufacturers\n\
  \      with:\n        ManufacturerType: tools.ManufacturerType\n        page: tools.page\n      inputParameters:\n      - name: ManufacturerType\n        type: string\n        description: ManufacturerType\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmanufacturerdetails-manufacturer\n      description: Get manufacturer details\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmanufacturerdetails-manufacturer\n      with:\n        manufacturer: tools.manufacturer\n        page: tools.page\n      inputParameters:\n      - name: manufacturer\n        type: string\n        description: manufacturer\n        required: true\n      - name: page\n        type: integer\n        description: page\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getallmakes\n\
  \      description: Get all makes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getallmakes\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmakeformanufacturer-manufacturer\n      description: Get makes for a manufacturer\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmakeformanufacturer-manufacturer\n      with:\n        manufacturer: tools.manufacturer\n      inputParameters:\n      - name: manufacturer\n        type: string\n        description: manufacturer\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmakesformanufacturerandyear-manufacturer\n      description: Get makes for a manufacturer and year\n      hints:\n        readOnly: true\n        destructive: false\n\
  \        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmakesformanufacturerandyear-manufacturer\n      with:\n        manufacturer: tools.manufacturer\n        year: tools.year\n      inputParameters:\n      - name: manufacturer\n        type: string\n        description: manufacturer\n        required: true\n      - name: year\n        type: integer\n        description: year\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmakesforvehicletype-vehicletype\n      description: Get makes for a vehicle type\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmakesforvehicletype-vehicletype\n      with:\n        vehicleType: tools.vehicleType\n      inputParameters:\n      - name: vehicleType\n        type: string\n        description: vehicleType\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-getmodelsformake-makename\n      description: Get models for a make\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmodelsformake-makename\n      with:\n        makeName: tools.makeName\n      inputParameters:\n      - name: makeName\n        type: string\n        description: makeName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmodelsformakeid-makeid\n      description: Get models for a make ID\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmodelsformakeid-makeid\n      with:\n        makeId: tools.makeId\n      inputParameters:\n      - name: makeId\n        type: integer\n        description: makeId\n        required: true\n      outputParameters:\n\
  \      - type: object\n        mapping: $.\n    - name: get-getmodelsformakeyear-make-make-modelyear-mod\n      description: Get models for a make and model year\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmodelsformakeyear-make-make-modelyear-mod\n      with:\n        make: tools.make\n        modelyear: tools.modelyear\n      inputParameters:\n      - name: make\n        type: string\n        description: make\n        required: true\n      - name: modelyear\n        type: integer\n        description: modelyear\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getmodelsformakeidyear-makeid-makeid-modelye\n      description: Get models for a make ID and model year\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getmodelsformakeidyear-makeid-makeid-modelye\n\
  \      with:\n        makeId: tools.makeId\n        modelyear: tools.modelyear\n      inputParameters:\n      - name: makeId\n        type: integer\n        description: makeId\n        required: true\n      - name: modelyear\n        type: integer\n        description: modelyear\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getvehicletypesformake-makename\n      description: Get vehicle types for a make\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getvehicletypesformake-makename\n      with:\n        makeName: tools.makeName\n      inputParameters:\n      - name: makeName\n        type: string\n        description: makeName\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getvehicletypesformakeid-makeid\n      description: Get vehicle types for a make ID\n\
  \      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getvehicletypesformakeid-makeid\n      with:\n        makeId: tools.makeId\n      inputParameters:\n      - name: makeId\n        type: integer\n        description: makeId\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getvehiclevariablelist\n      description: Get list of vehicle variables\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getvehiclevariablelist\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getvehiclevariablevalueslist-variable\n      description: Get values for a vehicle variable\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getvehiclevariablevalueslist-variable\n\
  \      with:\n        variable: tools.variable\n      inputParameters:\n      - name: variable\n        type: string\n        description: variable\n        required: true\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: get-getequipmentplantcodes\n      description: Get equipment plant codes\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: national-highway-traffic-safety-administration.get-getequipmentp\n\n# --- truncated at 32 KB (34 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/national-highway-traffic-safety-administration/refs/heads/main/capabilities/national-highway-traffic-safety-administration-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/national-highway-traffic-safety-administration/refs/heads/main/capabilities/national-highway-traffic-safety-administration-capability.yaml
tags:
- National
- Highway
- Traffic
- Safety
- Administration
- API
tools:
- description: Decode a VIN
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-decodevin-vin
- description: Decode a VIN (flat values)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-decodevinvalues-vin
- description: Decode a VIN with extended details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-decodevinextended-vin
- description: Decode a VIN with extended details (flat values)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-decodevinvaluesextended-vin
- description: Batch decode multiple VINs
  hints:
    destructive: false
    idempotent: false
    readOnly: false
  name: post-decodevinvaluesbatch
- description: Decode a World Manufacturer Identifier
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-decodewmi-wmi
- description: Get WMIs for a manufacturer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getwmisformanufacturer-manufacturer
- description: Get all manufacturers
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getallmanufacturers
- description: Get manufacturer details
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmanufacturerdetails-manufacturer
- description: Get all makes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getallmakes
- description: Get makes for a manufacturer
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmakeformanufacturer-manufacturer
- description: Get makes for a manufacturer and year
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmakesformanufacturerandyear-manufacturer
- description: Get makes for a vehicle type
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmakesforvehicletype-vehicletype
- description: Get models for a make
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmodelsformake-makename
- description: Get models for a make ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmodelsformakeid-makeid
- description: Get models for a make and model year
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmodelsformakeyear-make-make-modelyear-mod
- description: Get models for a make ID and model year
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getmodelsformakeidyear-makeid-makeid-modelye
- description: Get vehicle types for a make
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getvehicletypesformake-makename
- description: Get vehicle types for a make ID
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getvehicletypesformakeid-makeid
- description: Get list of vehicle variables
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getvehiclevariablelist
- description: Get values for a vehicle variable
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getvehiclevariablevalueslist-variable
- description: Get equipment plant codes
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getequipmentplantcodes
- description: Get parts
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getparts
- description: Get Canadian vehicle specifications
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: get-getcanadianvehiclespecifications
---
