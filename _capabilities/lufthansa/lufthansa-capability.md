---
categories: []
consumed_apis: []
description: Lufthansa LH Public API API capability.
layout: capability
name: Lufthansa LH Public API
operations:
- description: Lufthansa Countries
  method: GET
  name: referencescountriesbycountrycodeget
  path: /references/countries/{countryCode}
- description: Lufthansa Cities
  method: GET
  name: referencescitiesbycitycodeget
  path: /references/cities/{cityCode}
- description: Lufthansa Airports
  method: GET
  name: referencesairportsbyairportcodeget
  path: /references/airports/{airportCode}
- description: Lufthansa Nearest Airports
  method: GET
  name: referencesairportsnearestbylatitudeandlongitudeg
  path: /references/airports/nearest/{latitude},{longitude}
- description: Lufthansa Airlines
  method: GET
  name: referencesairlinesbyairlinecodeget
  path: /references/airlines/{airlineCode}
- description: Lufthansa Aircraft
  method: GET
  name: referencesaircraftbyaircraftcodeget
  path: /references/aircraft/{aircraftCode}
- description: Lufthansa Seat Maps
  method: GET
  name: offersseatmapsdestinationdatecabinclassbyflightn
  path: /offers/seatmaps/{flightNumber}/{origin}/{destination}/{date}/{cabinClass}
- description: Lufthansa Lounges
  method: GET
  name: offersloungesbylocationget
  path: /offers/lounges/{location}
- description: Lufthansa Flight Status
  method: GET
  name: operationsflightstatusbyflightnumberanddateget
  path: /operations/flightstatus/{flightNumber}/{date}
- description: Lufthansa Flight Status by Route
  method: GET
  name: operationsflightstatusroutedatebyoriginanddestin
  path: /operations/flightstatus/route/{origin}/{destination}/{date}
- description: Lufthansa Flight Status at Arrival Airport
  method: GET
  name: operationsflightstatusarrivalsbyairportcodeandfr
  path: /operations/flightstatus/arrivals/{airportCode}/{fromDateTime}
- description: Lufthansa Flight Status at Departure Airport
  method: GET
  name: operationsflightstatusdeparturesbyairportcodeand
  path: /operations/flightstatus/departures/{airportCode}/{fromDateTime}
- description: Lufthansa Flight Schedules
  method: GET
  name: operationsschedulesfromdatetimebyoriginanddestin
  path: /operations/schedules/{origin}/{destination}/{fromDateTime}
- description: Lufthansa Shipment Tracking
  method: GET
  name: cargoshipmenttrackingbyawbprefixandawbnumberget
  path: /cargo/shipmentTracking/{aWBPrefix}-{aWBNumber}
- description: Lufthansa Retrieve all flights
  method: GET
  name: cargogetroutefromdateproductcodebyoriginanddesti
  path: /cargo/getRoute/{origin}-{destination}/{fromDate}/{productCode}
personas: []
provider_name: Lufthansa
provider_slug: lufthansa
search_terms:
- referencesairlinesbyairlinecodeget
- lufthansa aircraft
- travel
- operationsflightstatusroutedatebyoriginanddestin
- aviation
- flights
- referencesaircraftbyaircraftcodeget
- operationsflightstatusbyflightnumberanddateget
- lufthansa flight status at departure airport
- referencescitiesbycitycodeget
- referencesairportsnearestbylatitudeandlongitudeg
- lufthansa shipment tracking
- cargogetroutefromdateproductcodebyoriginanddesti
- lufthansa airports
- lufthansa nearest airports
- lufthansa airlines
- cargoshipmenttrackingbyawbprefixandawbnumberget
- lufthansa countries
- offersseatmapsdestinationdatecabinclassbyflightn
- lufthansa flight schedules
- lufthansa flight status by route
- lufthansa cities
- operationsflightstatusarrivalsbyairportcodeandfr
- api
- lufthansa flight status at arrival airport
- referencesairportsbyairportcodeget
- lufthansa
- lufthansa seat maps
- lufthansa lounges
- lufthansa flight status
- airlines
- operationsschedulesfromdatetimebyoriginanddestin
- referencescountriesbycountrycodeget
- lufthansa retrieve all flights
- offersloungesbylocationget
- operationsflightstatusdeparturesbyairportcodeand
slug: lufthansa-capability
source_filename: lufthansa-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: Lufthansa LH Public API\n  description: Lufthansa LH Public API API capability.\n  tags:\n  - Lufthansa\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: lufthansa\n    baseUri: https://api.lufthansa.com/v1\n    description: Lufthansa LH Public API HTTP API.\n    authentication:\n      type: bearer\n      token: '{{LUFTHANSA_TOKEN}}'\n    resources:\n    - name: references-countries-countrycode\n      path: /references/countries/{countryCode}\n      operations:\n      - name: referencescountriesbycountrycodeget\n        method: GET\n        description: Lufthansa Countries\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: countryCode\n      \
  \    in: path\n          type: string\n          required: true\n          description: 2-letter ISO 3166-1 country code\n        - name: lang\n          in: query\n          type: string\n          description: 2 letter ISO 3166-1 language code\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references-cities-citycode\n      path: /references/cities/{cityCode}\n      operations:\n      - name: referencescitiesbycitycodeget\n        method: GET\n        description: Lufthansa Cities\n        inputParameters:\n        - name: Accept\n \
  \         in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: cityCode\n          in: path\n          type: string\n          required: true\n          description: 3-letter IATA city code\n        - name: lang\n          in: query\n          type: string\n          description: 2 letter ISO 3166-1 language code\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references-airports-airportcode\n\
  \      path: /references/airports/{airportCode}\n      operations:\n      - name: referencesairportsbyairportcodeget\n        method: GET\n        description: Lufthansa Airports\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: airportCode\n          in: path\n          type: string\n          required: true\n          description: 3-letter IATA airport code\n        - name: lang\n          in: query\n          type: string\n          description: 2-letter ISO 3166-1 language code\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n  \
  \        type: string\n          description: Number of records skipped. Defaults to 0\n        - name: LHoperated\n          in: query\n          type: boolean\n          description: Restrict the results to locations with flights operated by LH (false=0, true=1)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references-airports-nearest-latitude-longitude\n      path: /references/airports/nearest/{latitude},{longitude}\n      operations:\n      - name: referencesairportsnearestbylatitudeandlongitudeg\n        method: GET\n        description: Lufthansa Nearest Airports\n        inputParameters:\n        - name: latitude\n          in: path\n          type: integer\n          required: true\n          description: Latitude in decimal format to at most 3 decimal places\n        - name: longitude\n          in: path\n          type: integer\n          required: true\n          description: Longitude\
  \ in decimal format to at most 3 decimal places\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: lang\n          in: query\n          type: string\n          description: 2 letter ISO 3166-1 language code\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references-airlines-airlinecode\n      path: /references/airlines/{airlineCode}\n      operations:\n      - name: referencesairlinesbyairlinecodeget\n        method: GET\n        description: Lufthansa Airlines\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\"\
  , \"application/xml\")'\n        - name: airlineCode\n          in: path\n          type: string\n          required: true\n          description: 2-character IATA airline/carrier code\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: references-aircraft-aircraftcode\n      path: /references/aircraft/{aircraftCode}\n      operations:\n      - name: referencesaircraftbyaircraftcodeget\n        method: GET\n        description: Lufthansa Aircraft\n        inputParameters:\n        - name: Accept\n          in: header\n          type: string\n\
  \          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: aircraftCode\n          in: path\n          type: string\n          required: true\n          description: 3-character IATA aircraft code\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers-seatmaps-flightnumber-origin-destination-\n      path: /offers/seatmaps/{flightNumber}/{origin}/{destination}/{date}/{cabinClass}\n      operations:\n      - name:\
  \ offersseatmapsdestinationdatecabinclassbyflightn\n        method: GET\n        description: Lufthansa Seat Maps\n        inputParameters:\n        - name: flightNumber\n          in: path\n          type: string\n          required: true\n          description: Flight number including carrier code and any suffix (e.g. 'LH2037')\n        - name: origin\n          in: path\n          type: string\n          required: true\n          description: Departure airport. 3-letter IATA airport code (e.g. 'TXL')\n        - name: destination\n          in: path\n          type: string\n          required: true\n          description: Destination airport. 3-letter IATA airport code (e.g. 'MUC')\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: Departure date (YYYY-MM-DD)\n        - name: cabinClass\n          in: path\n          type: string\n          required: true\n          description: 'Cabin class: ''M'', ''E'', ''C'', ''F''.\
  \ Some flights have fewer classes (Acceptable values are: \"M\",\n            \"E\", \"C\", \"F\")'\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: offers-lounges-location\n      path: /offers/lounges/{location}\n      operations:\n      - name: offersloungesbylocationget\n        method: GET\n        description: Lufthansa Lounges\n        inputParameters:\n        - name: location\n          in: path\n          type: string\n          required: true\n          description: 3-leter IATA airport or city code (e.g. 'ZRH')\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json\
  \ or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: cabinClass\n          in: query\n          type: string\n          description: 'Cabin class: ''M'', ''E'', ''C'', ''F'' (Acceptable values are: \"\", \"M\", \"E\", \"C\", \"F\")'\n        - name: tierCode\n          in: query\n          type: string\n          description: 'Frequent flyer level (''FTL'', ''SGC'', ''SEN'', ''HON'') (Acceptable values are: \"\", \"FTL\", \"SGC\",\n            \"SEN\", \"HON\")'\n        - name: lang\n          in: query\n          type: string\n          description: Language code.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-flightstatus-flightnumber-date\n      path: /operations/flightstatus/{flightNumber}/{date}\n      operations:\n      - name: operationsflightstatusbyflightnumberanddateget\n        method: GET\n        description: Lufthansa\
  \ Flight Status\n        inputParameters:\n        - name: flightNumber\n          in: path\n          type: string\n          required: true\n          description: Flight number including carrier code and any suffix (e.g. 'LH400')\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: The departure date (YYYY-MM-DD) in the local time of the departure airport\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records\
  \ skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-flightstatus-route-origin-destination\n      path: /operations/flightstatus/route/{origin}/{destination}/{date}\n      operations:\n      - name: operationsflightstatusroutedatebyoriginanddestin\n        method: GET\n        description: Lufthansa Flight Status by Route\n        inputParameters:\n        - name: origin\n          in: path\n          type: string\n          required: true\n          description: 3-letter IATA airport (e.g. 'FRA')\n        - name: destination\n          in: path\n          type: string\n          required: true\n          description: 3-letter IATA airport code (e.g. 'JFK')\n        - name: date\n          in: path\n          type: string\n          required: true\n          description: Departure date (YYYY-MM-DD) in local time of departure airport\n        - name: Accept\n      \
  \    in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-flightstatus-arrivals-airportcode-fro\n      path: /operations/flightstatus/arrivals/{airportCode}/{fromDateTime}\n      operations:\n      - name: operationsflightstatusarrivalsbyairportcodeandfr\n        method: GET\n        description: Lufthansa Flight Status at Arrival\
  \ Airport\n        inputParameters:\n        - name: airportCode\n          in: path\n          type: string\n          required: true\n          description: 3-letter IATA aiport code (e.g. 'ZRH')\n        - name: fromDateTime\n          in: path\n          type: string\n          required: true\n          description: Start of time range in local time of arrival airport (YYYY-MM-DDTHH:mm)\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n\
  \        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-flightstatus-departures-airportcode-f\n      path: /operations/flightstatus/departures/{airportCode}/{fromDateTime}\n      operations:\n      - name: operationsflightstatusdeparturesbyairportcodeand\n        method: GET\n        description: Lufthansa Flight Status at Departure Airport\n        inputParameters:\n        - name: airportCode\n          in: path\n          type: string\n          required: true\n          description: Departure airport. 3-letter IATA airport code (e.g. 'HAM')\n        - name: fromDateTime\n          in: path\n          type: string\n          required: true\n          description: Start of time range in local time of departure airport (YYYY-MM-DDTHH:mm)\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml\
  \ (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: limit\n          in: query\n          type: string\n          description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: operations-schedules-origin-destination-fromdate\n      path: /operations/schedules/{origin}/{destination}/{fromDateTime}\n      operations:\n      - name: operationsschedulesfromdatetimebyoriginanddestin\n        method: GET\n        description: Lufthansa Flight Schedules\n        inputParameters:\n        - name: origin\n          in: path\n          type: string\n          required: true\n          description: Departure\
  \ airport. 3-letter IATA airport code (e.g. 'ZRH')\n        - name: destination\n          in: path\n          type: string\n          required: true\n          description: Destination airport. 3-letter IATA airport code (e.g. 'FRA')\n        - name: fromDateTime\n          in: path\n          type: string\n          required: true\n          description: Local departure date and optionally departure time (YYYY-MM-DD or YYYY-MM-DDTHH:mm). When not provided,\n            time is assumed to be 00:01\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        - name: directFlights\n          in: query\n          type: boolean\n          description: Show only direct flights (false=0, true=1). Default is false\n        - name: limit\n          in: query\n          type: string\n          description: Number\
  \ of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100\n            is given, 100 will be taken)\n        - name: offset\n          in: query\n          type: string\n          description: Number of records skipped. Defaults to 0\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cargo-shipmenttracking-awbprefix-awbnumber\n      path: /cargo/shipmentTracking/{aWBPrefix}-{aWBNumber}\n      operations:\n      - name: cargoshipmenttrackingbyawbprefixandawbnumberget\n        method: GET\n        description: Lufthansa Shipment Tracking\n        inputParameters:\n        - name: aWBPrefix\n          in: path\n          type: string\n          required: true\n          description: 'aWBPrefix : Represents the airline that is the owner of this AWB, i.e. \"020\" = Lufthansa Cargo, format\n            : [0-9]{3} e.g. 020'\n        - name: aWBNumber\n          in: path\n\
  \          type: string\n          required: true\n          description: 'aWBNumber : The Air Waybill Number , format : [0-9]{8} e.g. 08002050'\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: cargo-getroute-origin-destination-fromdate-produ\n      path: /cargo/getRoute/{origin}-{destination}/{fromDate}/{productCode}\n      operations:\n      - name: cargogetroutefromdateproductcodebyoriginanddesti\n        method: GET\n        description: Lufthansa Retrieve all flights\n        inputParameters:\n        - name: origin\n          in: path\n          type: string\n          required: true\n          description: 'Departure Airport : 3-letter IATA airport code, e.g.\
  \ FRA.'\n        - name: destination\n          in: path\n          type: string\n          required: true\n          description: 'Arrival airport : 3-letter IATA airport code, e.g. HKG.'\n        - name: fromDate\n          in: path\n          type: string\n          required: true\n          description: 'Departure date in the local time of the departure airport. Based on LAT (Latest Acceptance Time).\n            format : yyyy-MM-dd eg : 2017-07-15'\n        - name: productCode\n          in: path\n          type: string\n          required: true\n          description: 'Product code for requested service and specials : 3-letter eg: YNZ'\n        - name: Accept\n          in: header\n          type: string\n          required: true\n          description: 'http header: application/json or application/xml (Acceptable values are: \"application/json\", \"application/xml\")'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n    \
  \      value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: lufthansa-rest\n    description: REST adapter for Lufthansa LH Public API.\n    resources:\n    - path: /references/countries/{countryCode}\n      name: referencescountriesbycountrycodeget\n      operations:\n      - method: GET\n        name: referencescountriesbycountrycodeget\n        description: Lufthansa Countries\n        call: lufthansa.referencescountriesbycountrycodeget\n        with:\n          countryCode: rest.countryCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /references/cities/{cityCode}\n      name: referencescitiesbycitycodeget\n      operations:\n      - method: GET\n        name: referencescitiesbycitycodeget\n        description: Lufthansa Cities\n        call: lufthansa.referencescitiesbycitycodeget\n        with:\n          cityCode: rest.cityCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /references/airports/{airportCode}\n\
  \      name: referencesairportsbyairportcodeget\n      operations:\n      - method: GET\n        name: referencesairportsbyairportcodeget\n        description: Lufthansa Airports\n        call: lufthansa.referencesairportsbyairportcodeget\n        with:\n          airportCode: rest.airportCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /references/airports/nearest/{latitude},{longitude}\n      name: referencesairportsnearestbylatitudeandlongitudeg\n      operations:\n      - method: GET\n        name: referencesairportsnearestbylatitudeandlongitudeg\n        description: Lufthansa Nearest Airports\n        call: lufthansa.referencesairportsnearestbylatitudeandlongitudeg\n        with:\n          latitude: rest.latitude\n          longitude: rest.longitude\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /references/airlines/{airlineCode}\n      name: referencesairlinesbyairlinecodeget\n      operations:\n\
  \      - method: GET\n        name: referencesairlinesbyairlinecodeget\n        description: Lufthansa Airlines\n        call: lufthansa.referencesairlinesbyairlinecodeget\n        with:\n          airlineCode: rest.airlineCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /references/aircraft/{aircraftCode}\n      name: referencesaircraftbyaircraftcodeget\n      operations:\n      - method: GET\n        name: referencesaircraftbyaircraftcodeget\n        description: Lufthansa Aircraft\n        call: lufthansa.referencesaircraftbyaircraftcodeget\n        with:\n          aircraftCode: rest.aircraftCode\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/seatmaps/{flightNumber}/{origin}/{destination}/{date}/{cabinClass}\n      name: offersseatmapsdestinationdatecabinclassbyflightn\n      operations:\n      - method: GET\n        name: offersseatmapsdestinationdatecabinclassbyflightn\n        description:\
  \ Lufthansa Seat Maps\n        call: lufthansa.offersseatmapsdestinationdatecabinclassbyflightn\n        with:\n          flightNumber: rest.flightNumber\n          origin: rest.origin\n          destination: rest.destination\n          date: rest.date\n          cabinClass: rest.cabinClass\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /offers/lounges/{location}\n      name: offersloungesbylocationget\n      operations:\n      - method: GET\n        name: offersloungesbylocationget\n        description: Lufthansa Lounges\n        call: lufthansa.offersloungesbylocationget\n        with:\n          location: rest.location\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/flightstatus/{flightNumber}/{date}\n      name: operationsflightstatusbyflightnumberanddateget\n      operations:\n      - method: GET\n        name: operationsflightstatusbyflightnumberanddateget\n        description: Lufthansa Flight\
  \ Status\n        call: lufthansa.operationsflightstatusbyflightnumberanddateget\n        with:\n          flightNumber: rest.flightNumber\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/flightstatus/route/{origin}/{destination}/{date}\n      name: operationsflightstatusroutedatebyoriginanddestin\n      operations:\n      - method: GET\n        name: operationsflightstatusroutedatebyoriginanddestin\n        description: Lufthansa Flight Status by Route\n        call: lufthansa.operationsflightstatusroutedatebyoriginanddestin\n        with:\n          origin: rest.origin\n          destination: rest.destination\n          date: rest.date\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/flightstatus/arrivals/{airportCode}/{fromDateTime}\n      name: operationsflightstatusarrivalsbyairportcodeandfr\n      operations:\n      - method: GET\n        name: operationsflightstatusarrivalsbyairportcodeandfr\n\
  \        description: Lufthansa Flight Status at Arrival Airport\n        call: lufthansa.operationsflightstatusarrivalsbyairportcodeandfr\n        with:\n          airportCode: rest.airportCode\n          fromDateTime: rest.fromDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/flightstatus/departures/{airportCode}/{fromDateTime}\n      name: operationsflightstatusdeparturesbyairportcodeand\n      operations:\n      - method: GET\n        name: operationsflightstatusdeparturesbyairportcodeand\n        description: Lufthansa Flight Status at Departure Airport\n        call: lufthansa.operationsflightstatusdeparturesbyairportcodeand\n        with:\n          airportCode: rest.airportCode\n          fromDateTime: rest.fromDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /operations/schedules/{origin}/{destination}/{fromDateTime}\n      name: operationsschedulesfromdatetimebyoriginanddestin\n\
  \      operations:\n      - method: GET\n        name: operationsschedulesfromdatetimebyoriginanddestin\n        description: Lufthansa Flight Schedules\n        call: lufthansa.operationsschedulesfromdatetimebyoriginanddestin\n        with:\n          origin: rest.origin\n          destination: rest.destination\n          fromDateTime: rest.fromDateTime\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cargo/shipmentTracking/{aWBPrefix}-{aWBNumber}\n      name: cargoshipmenttrackingbyawbprefixandawbnumberget\n      operations:\n      - method: GET\n        name: cargoshipmenttrackingbyawbprefixandawbnumberget\n        description: Lufthansa Shipment Tracking\n        call: lufthansa.cargoshipmenttrackingbyawbprefixandawbnumberget\n        with:\n          aWBPrefix: rest.aWBPrefix\n          aWBNumber: rest.aWBNumber\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /cargo/getRoute/{origin}-{destination}/{fromDate}/{productCode}\n\
  \      name: cargogetroutefromdateproductcodebyoriginanddesti\n      operations:\n      - method: GET\n        name: cargogetroutefromdateproductcodebyoriginanddesti\n        description: Lufthansa Retrieve all flights\n        call: lufthansa.cargogetroutefromdateproductcodebyoriginanddesti\n        with:\n          origin: rest.origin\n          destination: rest.destination\n          fromDate: rest.fromDate\n          productCode: rest.productCode\n        outputParameters:\n        - type: object\n          mapping: $.\n  - type: mcp\n    port: 9090\n    namespace: lufthansa-mcp\n    transport: http\n    description: MCP adapter for Lufthansa LH Public API for AI agent use.\n    tools:\n    - name: referencescountriesbycountrycodeget\n      description: Lufthansa Countries\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lufthansa.referencescountriesbycountrycodeget\n      with:\n        countryCode: tools.countryCode\n     \
  \   lang: tools.lang\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: countryCode\n        type: string\n        description: 2-letter ISO 3166-1 country code\n        required: true\n      - name: lang\n        type: string\n        description: 2 letter ISO 3166-1 language code\n      - name: limit\n        type: string\n        description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is\n          given, 100 will be taken)\n      - name: offset\n        type: string\n        description: Number of records skipped. Defaults to 0\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: referencescitiesbycitycodeget\n      description: Lufthansa Cities\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lufthansa.referencescitiesbycitycodeget\n      with:\n        cityCode: tools.cityCode\n        lang: tools.lang\n\
  \        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: cityCode\n        type: string\n        description: 3-letter IATA city code\n        required: true\n      - name: lang\n        type: string\n        description: 2 letter ISO 3166-1 language code\n      - name: limit\n        type: string\n        description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is\n          given, 100 will be taken)\n      - name: offset\n        type: string\n        description: Number of records skipped. Defaults to 0\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: referencesairportsbyairportcodeget\n      description: Lufthansa Airports\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lufthansa.referencesairportsbyairportcodeget\n      with:\n        airportCode: tools.airportCode\n        lang: tools.lang\n       \
  \ limit: tools.limit\n        offset: tools.offset\n        LHoperated: tools.LHoperated\n      inputParameters:\n      - name: airportCode\n        type: string\n        description: 3-letter IATA airport code\n        required: true\n      - name: lang\n        type: string\n        description: 2-letter ISO 3166-1 language code\n      - name: limit\n        type: string\n        description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is\n          given, 100 will be taken)\n      - name: offset\n        type: string\n        description: Number of records skipped. Defaults to 0\n      - name: LHoperated\n        type: boolean\n        description: Restrict the results to locations with flights operated by LH (false=0, true=1)\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: referencesairportsnearestbylatitudeandlongitudeg\n      description: Lufthansa Nearest Airports\n      hints:\n        readOnly:\
  \ true\n        destructive: false\n        idempotent: true\n      call: lufthansa.referencesairportsnearestbylatitudeandlongitudeg\n      with:\n        latitude: tools.latitude\n        longitude: tools.longitude\n        lang: tools.lang\n      inputParameters:\n      - name: latitude\n        type: integer\n        description: Latitude in decimal format to at most 3 decimal places\n        required: true\n      - name: longitude\n        type: integer\n        description: Longitude in decimal format to at most 3 decimal places\n        required: true\n      - name: lang\n        type: string\n        description: 2 letter ISO 3166-1 language code\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: referencesairlinesbyairlinecodeget\n      description: Lufthansa Airlines\n      hints:\n        readOnly: true\n        destructive: false\n        idempotent: true\n      call: lufthansa.referencesairlinesbyairlinecodeget\n      with:\n        airlineCode:\
  \ tools.airlineCode\n        limit: tools.limit\n        offset: tools.offset\n      inputParameters:\n      - name: airlineCode\n        type: string\n        description: 2-character IATA airline/carrier code\n        required: true\n      - name: limit\n        type: string\n        description: Number of records returned per request. Defaults to 20, maximum is 100 (if a value bigger than 100 is\n          given, 100 will be taken)\n      - name: offset\n        type: string\n        description: Number of records skipped. Defaults to 0\n      outputParameters:\n      - type: object\n        mapping: $.\n    - name: referencesaircraft\n\n# --- truncated at 32 KB (43 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/lufthansa/refs/heads/main/capabilities/lufthansa-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/lufthansa/refs/heads/main/capabilities/lufthansa-capability.yaml
tags:
- Lufthansa
- API
tools:
- description: Lufthansa Countries
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencescountriesbycountrycodeget
- description: Lufthansa Cities
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencescitiesbycitycodeget
- description: Lufthansa Airports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencesairportsbyairportcodeget
- description: Lufthansa Nearest Airports
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencesairportsnearestbylatitudeandlongitudeg
- description: Lufthansa Airlines
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencesairlinesbyairlinecodeget
- description: Lufthansa Aircraft
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: referencesaircraftbyaircraftcodeget
- description: Lufthansa Seat Maps
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: offersseatmapsdestinationdatecabinclassbyflightn
- description: Lufthansa Lounges
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: offersloungesbylocationget
- description: Lufthansa Flight Status
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsflightstatusbyflightnumberanddateget
- description: Lufthansa Flight Status by Route
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsflightstatusroutedatebyoriginanddestin
- description: Lufthansa Flight Status at Arrival Airport
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsflightstatusarrivalsbyairportcodeandfr
- description: Lufthansa Flight Status at Departure Airport
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsflightstatusdeparturesbyairportcodeand
- description: Lufthansa Flight Schedules
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: operationsschedulesfromdatetimebyoriginanddestin
- description: Lufthansa Shipment Tracking
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cargoshipmenttrackingbyawbprefixandawbnumberget
- description: Lufthansa Retrieve all flights
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: cargogetroutefromdateproductcodebyoriginanddesti
---
