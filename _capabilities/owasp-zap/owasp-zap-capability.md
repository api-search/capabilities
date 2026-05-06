---
categories: []
consumed_apis: []
description: The HTTP API for controlling and accessing ZAP.
layout: capability
name: ZAP API
operations:
- description: 'Starts an Access Control scan with the given context ID and user ID. (Optional parameters: user ID for Unauthenticated user, boolean identifying whether or not Alerts are raised, and the Risk level for the Alerts.) [This assumes the Access'
  method: GET
  name: accesscontrolactionscan
  path: /JSON/accessControl/action/scan/
- description: Generates an Access Control report for the given context ID and saves it based on the provided filename (path).
  method: GET
  name: accesscontrolactionwritehtmlreport
  path: /JSON/accessControl/action/writeHTMLreport/
- description: Gets the Access Control scan progress (percentage integer) for the given context ID.
  method: GET
  name: accesscontrolviewgetscanprogress
  path: /JSON/accessControl/view/getScanProgress/
- description: Gets the Access Control scan status (description string) for the given context ID.
  method: GET
  name: accesscontrolviewgetscanstatus
  path: /JSON/accessControl/view/getScanStatus/
- description: Adds an anti-CSRF token with the given name, enabled by default
  method: GET
  name: acsrfactionaddoptiontoken
  path: /JSON/acsrf/action/addOptionToken/
- description: Removes the anti-CSRF token with the given name
  method: GET
  name: acsrfactionremoveoptiontoken
  path: /JSON/acsrf/action/removeOptionToken/
- description: Define if ZAP should detect CSRF tokens by searching for partial matches.
  method: GET
  name: acsrfactionsetoptionpartialmatchingenabled
  path: /JSON/acsrf/action/setOptionPartialMatchingEnabled/
- description: Generate a form for testing lack of anti-CSRF tokens - typically invoked via ZAP
  method: GET
  name: acsrfothergenform
  path: /OTHER/acsrf/other/genForm/
- description: Define if ZAP should detect CSRF tokens by searching for partial matches
  method: GET
  name: acsrfviewoptionpartialmatchingenabled
  path: /JSON/acsrf/view/optionPartialMatchingEnabled/
- description: Lists the names of all anti-CSRF tokens
  method: GET
  name: acsrfviewoptiontokensnames
  path: /JSON/acsrf/view/optionTokensNames/
- description: Adds an allowed resource.
  method: GET
  name: ajaxspideractionaddallowedresource
  path: /JSON/ajaxSpider/action/addAllowedResource/
- description: Adds an excluded element to a context.
  method: GET
  name: ajaxspideractionaddexcludedelement
  path: /JSON/ajaxSpider/action/addExcludedElement/
- description: Modifies an excluded element of a context.
  method: GET
  name: ajaxspideractionmodifyexcludedelement
  path: /JSON/ajaxSpider/action/modifyExcludedElement/
- description: Removes an allowed resource.
  method: GET
  name: ajaxspideractionremoveallowedresource
  path: /JSON/ajaxSpider/action/removeAllowedResource/
- description: Removes an excluded element from a context.
  method: GET
  name: ajaxspideractionremoveexcludedelement
  path: /JSON/ajaxSpider/action/removeExcludedElement/
- description: Runs the AJAX Spider against a given target.
  method: GET
  name: ajaxspideractionscan
  path: /JSON/ajaxSpider/action/scan/
- description: Runs the AJAX Spider from the perspective of a User of the web application.
  method: GET
  name: ajaxspideractionscanasuser
  path: /JSON/ajaxSpider/action/scanAsUser/
- description: Sets whether or not an allowed resource is enabled.
  method: GET
  name: ajaxspideractionsetenabledallowedresource
  path: /JSON/ajaxSpider/action/setEnabledAllowedResource/
- description: Sets the configuration of the AJAX Spider to use one of the supported browsers.
  method: GET
  name: ajaxspideractionsetoptionbrowserid
  path: /JSON/ajaxSpider/action/setOptionBrowserId/
- description: Sets whether or not the AJAX Spider will only click on the default HTML elements.
  method: GET
  name: ajaxspideractionsetoptionclickdefaultelems
  path: /JSON/ajaxSpider/action/setOptionClickDefaultElems/
- description: When enabled, the crawler attempts to interact with each element (e.g., by clicking) only once.
  method: GET
  name: ajaxspideractionsetoptionclickelemsonce
  path: /JSON/ajaxSpider/action/setOptionClickElemsOnce/
- description: GET /JSON/ajaxSpider/action/setOptionEnableExtensions/
  method: GET
  name: ajaxspideractionsetoptionenableextensions
  path: /JSON/ajaxSpider/action/setOptionEnableExtensions/
- description: 'Sets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
  method: GET
  name: ajaxspideractionsetoptioneventwait
  path: /JSON/ajaxSpider/action/setOptionEventWait/
- description: Sets whether or not the AJAX Spider should avoid clicking logout elements.
  method: GET
  name: ajaxspideractionsetoptionlogoutavoidance
  path: /JSON/ajaxSpider/action/setOptionLogoutAvoidance/
- description: Sets the maximum depth that the crawler can reach.
  method: GET
  name: ajaxspideractionsetoptionmaxcrawldepth
  path: /JSON/ajaxSpider/action/setOptionMaxCrawlDepth/
- description: Sets the maximum number of states that the crawler should crawl.
  method: GET
  name: ajaxspideractionsetoptionmaxcrawlstates
  path: /JSON/ajaxSpider/action/setOptionMaxCrawlStates/
- description: The maximum time that the crawler is allowed to run.
  method: GET
  name: ajaxspideractionsetoptionmaxduration
  path: /JSON/ajaxSpider/action/setOptionMaxDuration/
- description: Sets the number of windows to be used by AJAX Spider.
  method: GET
  name: ajaxspideractionsetoptionnumberofbrowsers
  path: /JSON/ajaxSpider/action/setOptionNumberOfBrowsers/
- description: When enabled, inserts random values into form fields.
  method: GET
  name: ajaxspideractionsetoptionrandominputs
  path: /JSON/ajaxSpider/action/setOptionRandomInputs/
- description: Sets the time to wait after the page is loaded before interacting with it.
  method: GET
  name: ajaxspideractionsetoptionreloadwait
  path: /JSON/ajaxSpider/action/setOptionReloadWait/
- description: Sets the scope check.
  method: GET
  name: ajaxspideractionsetoptionscopecheck
  path: /JSON/ajaxSpider/action/setOptionScopeCheck/
- description: Stops the AJAX Spider.
  method: GET
  name: ajaxspideractionstop
  path: /JSON/ajaxSpider/action/stop/
- description: Gets the allowed resources. The allowed resources are always fetched even if out of scope, allowing to include necessary resources (e.g. scripts) from 3rd-parties.
  method: GET
  name: ajaxspiderviewallowedresources
  path: /JSON/ajaxSpider/view/allowedResources/
- description: Gets the excluded elements. The excluded elements are not clicked during crawling, for example, to prevent logging out.
  method: GET
  name: ajaxspiderviewexcludedelements
  path: /JSON/ajaxSpider/view/excludedElements/
- description: Gets the full crawled content detected by the AJAX Spider. Returns a set of values based on 'inScope' URLs, 'outOfScope' URLs, and 'errors' encountered during the last/current run of the AJAX Spider.
  method: GET
  name: ajaxspiderviewfullresults
  path: /JSON/ajaxSpider/view/fullResults/
- description: Gets the number of resources found.
  method: GET
  name: ajaxspiderviewnumberofresults
  path: /JSON/ajaxSpider/view/numberOfResults/
- description: Gets the configured browser to use for crawling.
  method: GET
  name: ajaxspiderviewoptionbrowserid
  path: /JSON/ajaxSpider/view/optionBrowserId/
- description: Gets the configured value for 'Click Default Elements Only', HTML elements such as 'a', 'button', 'input', all associated with some action or links on the page.
  method: GET
  name: ajaxspiderviewoptionclickdefaultelems
  path: /JSON/ajaxSpider/view/optionClickDefaultElems/
- description: Gets the value configured for the AJAX Spider to know if it should click on the elements only once.
  method: GET
  name: ajaxspiderviewoptionclickelemsonce
  path: /JSON/ajaxSpider/view/optionClickElemsOnce/
- description: GET /JSON/ajaxSpider/view/optionEnableExtensions/
  method: GET
  name: ajaxspiderviewoptionenableextensions
  path: /JSON/ajaxSpider/view/optionEnableExtensions/
- description: 'Gets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
  method: GET
  name: ajaxspiderviewoptioneventwait
  path: /JSON/ajaxSpider/view/optionEventWait/
- description: Gets the value of the Logout Avoidance option.
  method: GET
  name: ajaxspiderviewoptionlogoutavoidance
  path: /JSON/ajaxSpider/view/optionLogoutAvoidance/
- description: Gets the configured value for the max crawl depth.
  method: GET
  name: ajaxspiderviewoptionmaxcrawldepth
  path: /JSON/ajaxSpider/view/optionMaxCrawlDepth/
- description: Gets the configured value for the maximum crawl states allowed.
  method: GET
  name: ajaxspiderviewoptionmaxcrawlstates
  path: /JSON/ajaxSpider/view/optionMaxCrawlStates/
- description: Gets the configured max duration of the crawl, the value is in minutes.
  method: GET
  name: ajaxspiderviewoptionmaxduration
  path: /JSON/ajaxSpider/view/optionMaxDuration/
- description: Gets the configured number of browsers to be used.
  method: GET
  name: ajaxspiderviewoptionnumberofbrowsers
  path: /JSON/ajaxSpider/view/optionNumberOfBrowsers/
- description: Gets if the AJAX Spider will use random values in form fields when crawling, if set to true.
  method: GET
  name: ajaxspiderviewoptionrandominputs
  path: /JSON/ajaxSpider/view/optionRandomInputs/
- description: Gets the configured time to wait after reloading the page, this value is in milliseconds.
  method: GET
  name: ajaxspiderviewoptionreloadwait
  path: /JSON/ajaxSpider/view/optionReloadWait/
- description: Gets the configured scope check.
  method: GET
  name: ajaxspiderviewoptionscopecheck
  path: /JSON/ajaxSpider/view/optionScopeCheck/
- description: Gets the current results of the crawler.
  method: GET
  name: ajaxspiderviewresults
  path: /JSON/ajaxSpider/view/results/
- description: Gets the current status of the crawler. Actual values are Stopped and Running.
  method: GET
  name: ajaxspiderviewstatus
  path: /JSON/ajaxSpider/view/status/
- description: Add an alert associated with the given message ID, with the provided details. (The ID of the created alert is returned.)
  method: GET
  name: alertactionaddalert
  path: /JSON/alert/action/addAlert/
- description: Deletes the alert with the given ID.
  method: GET
  name: alertactiondeletealert
  path: /JSON/alert/action/deleteAlert/
- description: Deletes all the alerts optionally filtered by URL which fall within the Context with the provided name, risk, or base URL.
  method: GET
  name: alertactiondeletealerts
  path: /JSON/alert/action/deleteAlerts/
- description: Deletes all alerts of the current session.
  method: GET
  name: alertactiondeleteallalerts
  path: /JSON/alert/action/deleteAllAlerts/
- description: Update the alert with the given ID, with the provided details.
  method: GET
  name: alertactionupdatealert
  path: /JSON/alert/action/updateAlert/
- description: Update the confidence of the alerts.
  method: GET
  name: alertactionupdatealertsconfidence
  path: /JSON/alert/action/updateAlertsConfidence/
- description: Update the risk of the alerts.
  method: GET
  name: alertactionupdatealertsrisk
  path: /JSON/alert/action/updateAlertsRisk/
- description: Gets the alert with the given ID, the corresponding HTTP message can be obtained with the 'messageId' field and 'message' API method
  method: GET
  name: alertviewalert
  path: /JSON/alert/view/alert/
- description: Gets a count of the alerts, optionally filtered as per alertsPerRisk
  method: GET
  name: alertviewalertcountsbyrisk
  path: /JSON/alert/view/alertCountsByRisk/
personas: []
provider_name: OWASP ZAP
provider_slug: owasp-zap
search_terms:
- ajaxspideractionremoveallowedresource
- acsrfactionremoveoptiontoken
- alertactiondeleteallalerts
- gets the current results of the crawler.
- adds an anti-csrf token with the given name, enabled by default
- gets the configured number of browsers to be used.
- alertactiondeletealerts
- alertactionupdatealert
- when enabled, the crawler attempts to interact with each element (e.g., by clicking) only once.
- gets the value configured for the ajax spider to know if it should click on the elements only once.
- ajaxspideractionsetoptionrandominputs
- removes an excluded element from a context.
- update the confidence of the alerts.
- gets the number of resources found.
- deletes the alert with the given id.
- ajaxspiderviewoptionlogoutavoidance
- sets the time to wait after the page is loaded before interacting with it.
- ajaxspiderviewnumberofresults
- ajaxspiderviewoptionclickdefaultelems
- removes the anti-csrf token with the given name
- ajaxspiderviewoptionreloadwait
- ajaxspideractionsetoptionmaxcrawlstates
- api
- gets if the ajax spider will use random values in form fields when crawling, if set to true.
- sets whether or not the ajax spider should avoid clicking logout elements.
- zap
- add an alert associated with the given message id, with the provided details. (the id of the created alert is returned.)
- ajaxspideractionsetoptionlogoutavoidance
- ajaxspiderviewoptionclickelemsonce
- gets a count of the alerts, optionally filtered as per alertsperrisk
- ajaxspiderviewoptionscopecheck
- ajaxspideractionsetoptionmaxduration
- 'gets the time to wait after an event (in milliseconds). for example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
- acsrfactionaddoptiontoken
- sets the scope check.
- ajaxspiderviewallowedresources
- alertactiondeletealert
- accesscontrolactionscan
- ajaxspiderviewoptionnumberofbrowsers
- removes an allowed resource.
- ajaxspideractionsetoptionclickdefaultelems
- ajaxspiderviewoptionrandominputs
- acsrfothergenform
- ajaxspideractionsetenabledallowedresource
- ajaxspideractionsetoptioneventwait
- ajaxspideractionsetoptionmaxcrawldepth
- ajaxspiderviewstatus
- ajaxspiderviewoptioneventwait
- gets the configured value for the maximum crawl states allowed.
- open source
- update the risk of the alerts.
- update the alert with the given id, with the provided details.
- ajaxspiderviewoptionmaxcrawlstates
- accesscontrolviewgetscanprogress
- modifies an excluded element of a context.
- accesscontrolviewgetscanstatus
- ajaxspiderviewexcludedelements
- alertactionupdatealertsrisk
- ajaxspiderviewoptionmaxcrawldepth
- ajaxspiderviewresults
- gets the configured browser to use for crawling.
- sets the maximum depth that the crawler can reach.
- ajaxspideractionaddexcludedelement
- sets the configuration of the ajax spider to use one of the supported browsers.
- runs the ajax spider against a given target.
- ajaxspideractionsetoptionnumberofbrowsers
- vulnerability scanning
- acsrfviewoptionpartialmatchingenabled
- generate a form for testing lack of anti-csrf tokens - typically invoked via zap
- ajaxspideractionscan
- sets whether or not the ajax spider will only click on the default html elements.
- ajaxspiderviewoptionbrowserid
- accesscontrolactionwritehtmlreport
- gets the current status of the crawler. actual values are stopped and running.
- alertviewalert
- gets the excluded elements. the excluded elements are not clicked during crawling, for example, to prevent logging out.
- gets the configured max duration of the crawl, the value is in minutes.
- adds an excluded element to a context.
- ajaxspideractionsetoptionreloadwait
- ajaxspideractionsetoptionbrowserid
- gets the configured value for 'click default elements only', html elements such as 'a', 'button', 'input', all associated with some action or links on the page.
- when enabled, inserts random values into form fields.
- the maximum time that the crawler is allowed to run.
- alertviewalertcountsbyrisk
- adds an allowed resource.
- ajaxspiderviewoptionenableextensions
- gets the configured scope check.
- alertactionupdatealertsconfidence
- testing
- get /json/ajaxspider/action/setoptionenableextensions/
- ajaxspideractionsetoptionclickelemsonce
- gets the allowed resources. the allowed resources are always fetched even if out of scope, allowing to include necessary resources (e.g. scripts) from 3rd-parties.
- owasp
- deletes all the alerts optionally filtered by url which fall within the context with the provided name, risk, or base url.
- ajaxspiderviewoptionmaxduration
- sets the number of windows to be used by ajax spider.
- runs the ajax spider from the perspective of a user of the web application.
- gets the configured value for the max crawl depth.
- 'starts an access control scan with the given context id and user id. (optional parameters: user id for unauthenticated user, boolean identifying whether or not alerts are raised, and the risk level for the alerts.) [this assumes the access'
- ajaxspideractionsetoptionenableextensions
- lists the names of all anti-csrf tokens
- ajaxspideractionaddallowedresource
- 'sets the time to wait after an event (in milliseconds). for example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
- alertactionaddalert
- security testing
- get /json/ajaxspider/view/optionenableextensions/
- gets the configured time to wait after reloading the page, this value is in milliseconds.
- gets the access control scan status (description string) for the given context id.
- gets the alert with the given id, the corresponding http message can be obtained with the 'messageid' field and 'message' api method
- generates an access control report for the given context id and saves it based on the provided filename (path).
- stops the ajax spider.
- gets the full crawled content detected by the ajax spider. returns a set of values based on 'inscope' urls, 'outofscope' urls, and 'errors' encountered during the last/current run of the ajax spider.
- acsrfviewoptiontokensnames
- ajaxspideractionscanasuser
- sets the maximum number of states that the crawler should crawl.
- ajaxspiderviewfullresults
- define if zap should detect csrf tokens by searching for partial matches
- application security
- sets whether or not an allowed resource is enabled.
- ajaxspideractionmodifyexcludedelement
- gets the value of the logout avoidance option.
- ajaxspideractionsetoptionscopecheck
- acsrfactionsetoptionpartialmatchingenabled
- deletes all alerts of the current session.
- ajaxspideractionstop
- define if zap should detect csrf tokens by searching for partial matches.
- gets the access control scan progress (percentage integer) for the given context id.
- ajaxspideractionremoveexcludedelement
slug: owasp-zap-capability
source_filename: owasp-zap-capability.yaml
source_heading: Capability Spec
source_yaml: "naftiko: 1.0.0-alpha2\ninfo:\n  label: ZAP API\n  description: The HTTP API for controlling and accessing ZAP.\n  tags:\n  - Owasp\n  - Zap\n  - API\n  created: '2026-05-06'\n  modified: '2026-05-06'\ncapability:\n  consumes:\n  - type: http\n    namespace: owasp-zap\n    baseUri: http://zap\n    description: ZAP API HTTP API.\n    authentication:\n      type: apikey\n      in: header\n      name: X-ZAP-API-Key\n      value: '{{OWASP_ZAP_TOKEN}}'\n    resources:\n    - name: json-accesscontrol-action-scan\n      path: /JSON/accessControl/action/scan/\n      operations:\n      - name: accesscontrolactionscan\n        method: GET\n        description: 'Starts an Access Control scan with the given context ID and user ID. (Optional parameters: user ID for\n          Unauthenticated user, boolean identifying whether or not Alerts are raised, and the Risk level for the Alerts.)\n          [This assumes the Access '\n        outputRawFormat: json\n        outputParameters:\n     \
  \   - name: result\n          type: object\n          value: $.\n    - name: json-accesscontrol-action-writehtmlreport\n      path: /JSON/accessControl/action/writeHTMLreport/\n      operations:\n      - name: accesscontrolactionwritehtmlreport\n        method: GET\n        description: Generates an Access Control report for the given context ID and saves it based on the provided filename\n          (path).\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-accesscontrol-view-getscanprogress\n      path: /JSON/accessControl/view/getScanProgress/\n      operations:\n      - name: accesscontrolviewgetscanprogress\n        method: GET\n        description: Gets the Access Control scan progress (percentage integer) for the given context ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-accesscontrol-view-getscanstatus\n\
  \      path: /JSON/accessControl/view/getScanStatus/\n      operations:\n      - name: accesscontrolviewgetscanstatus\n        method: GET\n        description: Gets the Access Control scan status (description string) for the given context ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-acsrf-action-addoptiontoken\n      path: /JSON/acsrf/action/addOptionToken/\n      operations:\n      - name: acsrfactionaddoptiontoken\n        method: GET\n        description: Adds an anti-CSRF token with the given name, enabled by default\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-acsrf-action-removeoptiontoken\n      path: /JSON/acsrf/action/removeOptionToken/\n      operations:\n      - name: acsrfactionremoveoptiontoken\n        method: GET\n        description: Removes the anti-CSRF token with the\
  \ given name\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-acsrf-action-setoptionpartialmatchingenable\n      path: /JSON/acsrf/action/setOptionPartialMatchingEnabled/\n      operations:\n      - name: acsrfactionsetoptionpartialmatchingenabled\n        method: GET\n        description: Define if ZAP should detect CSRF tokens by searching for partial matches.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: other-acsrf-other-genform\n      path: /OTHER/acsrf/other/genForm/\n      operations:\n      - name: acsrfothergenform\n        method: GET\n        description: Generate a form for testing lack of anti-CSRF tokens - typically invoked via ZAP\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-acsrf-view-optionpartialmatchingenabled\n\
  \      path: /JSON/acsrf/view/optionPartialMatchingEnabled/\n      operations:\n      - name: acsrfviewoptionpartialmatchingenabled\n        method: GET\n        description: Define if ZAP should detect CSRF tokens by searching for partial matches\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-acsrf-view-optiontokensnames\n      path: /JSON/acsrf/view/optionTokensNames/\n      operations:\n      - name: acsrfviewoptiontokensnames\n        method: GET\n        description: Lists the names of all anti-CSRF tokens\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-addallowedresource\n      path: /JSON/ajaxSpider/action/addAllowedResource/\n      operations:\n      - name: ajaxspideractionaddallowedresource\n        method: GET\n        description: Adds an allowed resource.\n      \
  \  outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-addexcludedelement\n      path: /JSON/ajaxSpider/action/addExcludedElement/\n      operations:\n      - name: ajaxspideractionaddexcludedelement\n        method: GET\n        description: Adds an excluded element to a context.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-modifyexcludedelement\n      path: /JSON/ajaxSpider/action/modifyExcludedElement/\n      operations:\n      - name: ajaxspideractionmodifyexcludedelement\n        method: GET\n        description: Modifies an excluded element of a context.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-removeallowedresource\n      path: /JSON/ajaxSpider/action/removeAllowedResource/\n\
  \      operations:\n      - name: ajaxspideractionremoveallowedresource\n        method: GET\n        description: Removes an allowed resource.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-removeexcludedelement\n      path: /JSON/ajaxSpider/action/removeExcludedElement/\n      operations:\n      - name: ajaxspideractionremoveexcludedelement\n        method: GET\n        description: Removes an excluded element from a context.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-scan\n      path: /JSON/ajaxSpider/action/scan/\n      operations:\n      - name: ajaxspideractionscan\n        method: GET\n        description: Runs the AJAX Spider against a given target.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: json-ajaxspider-action-scanasuser\n      path: /JSON/ajaxSpider/action/scanAsUser/\n      operations:\n      - name: ajaxspideractionscanasuser\n        method: GET\n        description: Runs the AJAX Spider from the perspective of a User of the web application.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setenabledallowedresource\n      path: /JSON/ajaxSpider/action/setEnabledAllowedResource/\n      operations:\n      - name: ajaxspideractionsetenabledallowedresource\n        method: GET\n        description: Sets whether or not an allowed resource is enabled.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionbrowserid\n      path: /JSON/ajaxSpider/action/setOptionBrowserId/\n      operations:\n      - name:\
  \ ajaxspideractionsetoptionbrowserid\n        method: GET\n        description: Sets the configuration of the AJAX Spider to use one of the supported browsers.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionclickdefaultelem\n      path: /JSON/ajaxSpider/action/setOptionClickDefaultElems/\n      operations:\n      - name: ajaxspideractionsetoptionclickdefaultelems\n        method: GET\n        description: Sets whether or not the AJAX Spider will only click on the default HTML elements.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionclickelemsonce\n      path: /JSON/ajaxSpider/action/setOptionClickElemsOnce/\n      operations:\n      - name: ajaxspideractionsetoptionclickelemsonce\n        method: GET\n        description: When enabled, the\
  \ crawler attempts to interact with each element (e.g., by clicking) only once.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionenableextensions\n      path: /JSON/ajaxSpider/action/setOptionEnableExtensions/\n      operations:\n      - name: ajaxspideractionsetoptionenableextensions\n        method: GET\n        description: GET /JSON/ajaxSpider/action/setOptionEnableExtensions/\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptioneventwait\n      path: /JSON/ajaxSpider/action/setOptionEventWait/\n      operations:\n      - name: ajaxspideractionsetoptioneventwait\n        method: GET\n        description: 'Sets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor\n          hovers over an element, in order\
  \ for a menu to display, etc.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionlogoutavoidance\n      path: /JSON/ajaxSpider/action/setOptionLogoutAvoidance/\n      operations:\n      - name: ajaxspideractionsetoptionlogoutavoidance\n        method: GET\n        description: Sets whether or not the AJAX Spider should avoid clicking logout elements.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionmaxcrawldepth\n      path: /JSON/ajaxSpider/action/setOptionMaxCrawlDepth/\n      operations:\n      - name: ajaxspideractionsetoptionmaxcrawldepth\n        method: GET\n        description: Sets the maximum depth that the crawler can reach.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n   \
  \       value: $.\n    - name: json-ajaxspider-action-setoptionmaxcrawlstates\n      path: /JSON/ajaxSpider/action/setOptionMaxCrawlStates/\n      operations:\n      - name: ajaxspideractionsetoptionmaxcrawlstates\n        method: GET\n        description: Sets the maximum number of states that the crawler should crawl.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionmaxduration\n      path: /JSON/ajaxSpider/action/setOptionMaxDuration/\n      operations:\n      - name: ajaxspideractionsetoptionmaxduration\n        method: GET\n        description: The maximum time that the crawler is allowed to run.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionnumberofbrowsers\n      path: /JSON/ajaxSpider/action/setOptionNumberOfBrowsers/\n      operations:\n\
  \      - name: ajaxspideractionsetoptionnumberofbrowsers\n        method: GET\n        description: Sets the number of windows to be used by AJAX Spider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionrandominputs\n      path: /JSON/ajaxSpider/action/setOptionRandomInputs/\n      operations:\n      - name: ajaxspideractionsetoptionrandominputs\n        method: GET\n        description: When enabled, inserts random values into form fields.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionreloadwait\n      path: /JSON/ajaxSpider/action/setOptionReloadWait/\n      operations:\n      - name: ajaxspideractionsetoptionreloadwait\n        method: GET\n        description: Sets the time to wait after the page is loaded before interacting with it.\n \
  \       outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-setoptionscopecheck\n      path: /JSON/ajaxSpider/action/setOptionScopeCheck/\n      operations:\n      - name: ajaxspideractionsetoptionscopecheck\n        method: GET\n        description: Sets the scope check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-action-stop\n      path: /JSON/ajaxSpider/action/stop/\n      operations:\n      - name: ajaxspideractionstop\n        method: GET\n        description: Stops the AJAX Spider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-allowedresources\n      path: /JSON/ajaxSpider/view/allowedResources/\n      operations:\n      - name: ajaxspiderviewallowedresources\n\
  \        method: GET\n        description: Gets the allowed resources. The allowed resources are always fetched even if out of scope, allowing to\n          include necessary resources (e.g. scripts) from 3rd-parties.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-excludedelements\n      path: /JSON/ajaxSpider/view/excludedElements/\n      operations:\n      - name: ajaxspiderviewexcludedelements\n        method: GET\n        description: Gets the excluded elements. The excluded elements are not clicked during crawling, for example, to prevent\n          logging out.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-fullresults\n      path: /JSON/ajaxSpider/view/fullResults/\n      operations:\n      - name: ajaxspiderviewfullresults\n        method: GET\n        description:\
  \ Gets the full crawled content detected by the AJAX Spider. Returns a set of values based on 'inScope'\n          URLs, 'outOfScope' URLs, and 'errors' encountered during the last/current run of the AJAX Spider.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-numberofresults\n      path: /JSON/ajaxSpider/view/numberOfResults/\n      operations:\n      - name: ajaxspiderviewnumberofresults\n        method: GET\n        description: Gets the number of resources found.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionbrowserid\n      path: /JSON/ajaxSpider/view/optionBrowserId/\n      operations:\n      - name: ajaxspiderviewoptionbrowserid\n        method: GET\n        description: Gets the configured browser to use for crawling.\n        outputRawFormat: json\n\
  \        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionclickdefaultelems\n      path: /JSON/ajaxSpider/view/optionClickDefaultElems/\n      operations:\n      - name: ajaxspiderviewoptionclickdefaultelems\n        method: GET\n        description: Gets the configured value for 'Click Default Elements Only', HTML elements such as 'a', 'button', 'input',\n          all associated with some action or links on the page.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionclickelemsonce\n      path: /JSON/ajaxSpider/view/optionClickElemsOnce/\n      operations:\n      - name: ajaxspiderviewoptionclickelemsonce\n        method: GET\n        description: Gets the value configured for the AJAX Spider to know if it should click on the elements only once.\n        outputRawFormat: json\n        outputParameters:\n\
  \        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionenableextensions\n      path: /JSON/ajaxSpider/view/optionEnableExtensions/\n      operations:\n      - name: ajaxspiderviewoptionenableextensions\n        method: GET\n        description: GET /JSON/ajaxSpider/view/optionEnableExtensions/\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optioneventwait\n      path: /JSON/ajaxSpider/view/optionEventWait/\n      operations:\n      - name: ajaxspiderviewoptioneventwait\n        method: GET\n        description: 'Gets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor\n          hovers over an element, in order for a menu to display, etc.'\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name:\
  \ json-ajaxspider-view-optionlogoutavoidance\n      path: /JSON/ajaxSpider/view/optionLogoutAvoidance/\n      operations:\n      - name: ajaxspiderviewoptionlogoutavoidance\n        method: GET\n        description: Gets the value of the Logout Avoidance option.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionmaxcrawldepth\n      path: /JSON/ajaxSpider/view/optionMaxCrawlDepth/\n      operations:\n      - name: ajaxspiderviewoptionmaxcrawldepth\n        method: GET\n        description: Gets the configured value for the max crawl depth.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionmaxcrawlstates\n      path: /JSON/ajaxSpider/view/optionMaxCrawlStates/\n      operations:\n      - name: ajaxspiderviewoptionmaxcrawlstates\n        method: GET\n       \
  \ description: Gets the configured value for the maximum crawl states allowed.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionmaxduration\n      path: /JSON/ajaxSpider/view/optionMaxDuration/\n      operations:\n      - name: ajaxspiderviewoptionmaxduration\n        method: GET\n        description: Gets the configured max duration of the crawl, the value is in minutes.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionnumberofbrowsers\n      path: /JSON/ajaxSpider/view/optionNumberOfBrowsers/\n      operations:\n      - name: ajaxspiderviewoptionnumberofbrowsers\n        method: GET\n        description: Gets the configured number of browsers to be used.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type:\
  \ object\n          value: $.\n    - name: json-ajaxspider-view-optionrandominputs\n      path: /JSON/ajaxSpider/view/optionRandomInputs/\n      operations:\n      - name: ajaxspiderviewoptionrandominputs\n        method: GET\n        description: Gets if the AJAX Spider will use random values in form fields when crawling, if set to true.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionreloadwait\n      path: /JSON/ajaxSpider/view/optionReloadWait/\n      operations:\n      - name: ajaxspiderviewoptionreloadwait\n        method: GET\n        description: Gets the configured time to wait after reloading the page, this value is in milliseconds.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-optionscopecheck\n      path: /JSON/ajaxSpider/view/optionScopeCheck/\n\
  \      operations:\n      - name: ajaxspiderviewoptionscopecheck\n        method: GET\n        description: Gets the configured scope check.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-results\n      path: /JSON/ajaxSpider/view/results/\n      operations:\n      - name: ajaxspiderviewresults\n        method: GET\n        description: Gets the current results of the crawler.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-ajaxspider-view-status\n      path: /JSON/ajaxSpider/view/status/\n      operations:\n      - name: ajaxspiderviewstatus\n        method: GET\n        description: Gets the current status of the crawler. Actual values are Stopped and Running.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value:\
  \ $.\n    - name: json-alert-action-addalert\n      path: /JSON/alert/action/addAlert/\n      operations:\n      - name: alertactionaddalert\n        method: GET\n        description: Add an alert associated with the given message ID, with the provided details. (The ID of the created\n          alert is returned.)\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-action-deletealert\n      path: /JSON/alert/action/deleteAlert/\n      operations:\n      - name: alertactiondeletealert\n        method: GET\n        description: Deletes the alert with the given ID.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-action-deletealerts\n      path: /JSON/alert/action/deleteAlerts/\n      operations:\n      - name: alertactiondeletealerts\n        method: GET\n        description: Deletes all the\
  \ alerts optionally filtered by URL which fall within the Context with the provided name,\n          risk, or base URL.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-action-deleteallalerts\n      path: /JSON/alert/action/deleteAllAlerts/\n      operations:\n      - name: alertactiondeleteallalerts\n        method: GET\n        description: Deletes all alerts of the current session.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-action-updatealert\n      path: /JSON/alert/action/updateAlert/\n      operations:\n      - name: alertactionupdatealert\n        method: GET\n        description: Update the alert with the given ID, with the provided details.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n   \
  \ - name: json-alert-action-updatealertsconfidence\n      path: /JSON/alert/action/updateAlertsConfidence/\n      operations:\n      - name: alertactionupdatealertsconfidence\n        method: GET\n        description: Update the confidence of the alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-action-updatealertsrisk\n      path: /JSON/alert/action/updateAlertsRisk/\n      operations:\n      - name: alertactionupdatealertsrisk\n        method: GET\n        description: Update the risk of the alerts.\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-view-alert\n      path: /JSON/alert/view/alert/\n      operations:\n      - name: alertviewalert\n        method: GET\n        description: Gets the alert with the given ID, the corresponding HTTP message can be obtained with the 'messageId'\n\
  \          field and 'message' API method\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n    - name: json-alert-view-alertcountsbyrisk\n      path: /JSON/alert/view/alertCountsByRisk/\n      operations:\n      - name: alertviewalertcountsbyrisk\n        method: GET\n        description: Gets a count of the alerts, optionally filtered as per alertsPerRisk\n        outputRawFormat: json\n        outputParameters:\n        - name: result\n          type: object\n          value: $.\n  exposes:\n  - type: rest\n    port: 8080\n    namespace: owasp-zap-rest\n    description: REST adapter for ZAP API.\n    resources:\n    - path: /JSON/accessControl/action/scan/\n      name: accesscontrolactionscan\n      operations:\n      - method: GET\n        name: accesscontrolactionscan\n        description: 'Starts an Access Control scan with the given context ID and user ID. (Optional parameters: user ID for\n          Unauthenticated\
  \ user, boolean identifying whether or not Alerts are raised, and the Risk level for the Alerts.)\n          [This assumes the Access '\n        call: owasp-zap.accesscontrolactionscan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/accessControl/action/writeHTMLreport/\n      name: accesscontrolactionwritehtmlreport\n      operations:\n      - method: GET\n        name: accesscontrolactionwritehtmlreport\n        description: Generates an Access Control report for the given context ID and saves it based on the provided filename\n          (path).\n        call: owasp-zap.accesscontrolactionwritehtmlreport\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/accessControl/view/getScanProgress/\n      name: accesscontrolviewgetscanprogress\n      operations:\n      - method: GET\n        name: accesscontrolviewgetscanprogress\n        description: Gets the Access Control scan progress (percentage integer)\
  \ for the given context ID.\n        call: owasp-zap.accesscontrolviewgetscanprogress\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/accessControl/view/getScanStatus/\n      name: accesscontrolviewgetscanstatus\n      operations:\n      - method: GET\n        name: accesscontrolviewgetscanstatus\n        description: Gets the Access Control scan status (description string) for the given context ID.\n        call: owasp-zap.accesscontrolviewgetscanstatus\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/acsrf/action/addOptionToken/\n      name: acsrfactionaddoptiontoken\n      operations:\n      - method: GET\n        name: acsrfactionaddoptiontoken\n        description: Adds an anti-CSRF token with the given name, enabled by default\n        call: owasp-zap.acsrfactionaddoptiontoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/acsrf/action/removeOptionToken/\n\
  \      name: acsrfactionremoveoptiontoken\n      operations:\n      - method: GET\n        name: acsrfactionremoveoptiontoken\n        description: Removes the anti-CSRF token with the given name\n        call: owasp-zap.acsrfactionremoveoptiontoken\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/acsrf/action/setOptionPartialMatchingEnabled/\n      name: acsrfactionsetoptionpartialmatchingenabled\n      operations:\n      - method: GET\n        name: acsrfactionsetoptionpartialmatchingenabled\n        description: Define if ZAP should detect CSRF tokens by searching for partial matches.\n        call: owasp-zap.acsrfactionsetoptionpartialmatchingenabled\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /OTHER/acsrf/other/genForm/\n      name: acsrfothergenform\n      operations:\n      - method: GET\n        name: acsrfothergenform\n        description: Generate a form for testing lack of anti-CSRF tokens\
  \ - typically invoked via ZAP\n        call: owasp-zap.acsrfothergenform\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/acsrf/view/optionPartialMatchingEnabled/\n      name: acsrfviewoptionpartialmatchingenabled\n      operations:\n      - method: GET\n        name: acsrfviewoptionpartialmatchingenabled\n        description: Define if ZAP should detect CSRF tokens by searching for partial matches\n        call: owasp-zap.acsrfviewoptionpartialmatchingenabled\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/acsrf/view/optionTokensNames/\n      name: acsrfviewoptiontokensnames\n      operations:\n      - method: GET\n        name: acsrfviewoptiontokensnames\n        description: Lists the names of all anti-CSRF tokens\n        call: owasp-zap.acsrfviewoptiontokensnames\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/addAllowedResource/\n\
  \      name: ajaxspideractionaddallowedresource\n      operations:\n      - method: GET\n        name: ajaxspideractionaddallowedresource\n        description: Adds an allowed resource.\n        call: owasp-zap.ajaxspideractionaddallowedresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/addExcludedElement/\n      name: ajaxspideractionaddexcludedelement\n      operations:\n      - method: GET\n        name: ajaxspideractionaddexcludedelement\n        description: Adds an excluded element to a context.\n        call: owasp-zap.ajaxspideractionaddexcludedelement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/modifyExcludedElement/\n      name: ajaxspideractionmodifyexcludedelement\n      operations:\n      - method: GET\n        name: ajaxspideractionmodifyexcludedelement\n        description: Modifies an excluded element of a context.\n        call: owasp-zap.ajaxspideractionmodifyexcludedelement\n\
  \        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/removeAllowedResource/\n      name: ajaxspideractionremoveallowedresource\n      operations:\n      - method: GET\n        name: ajaxspideractionremoveallowedresource\n        description: Removes an allowed resource.\n        call: owasp-zap.ajaxspideractionremoveallowedresource\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/removeExcludedElement/\n      name: ajaxspideractionremoveexcludedelement\n      operations:\n      - method: GET\n        name: ajaxspideractionremoveexcludedelement\n        description: Removes an excluded element from a context.\n        call: owasp-zap.ajaxspideractionremoveexcludedelement\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/scan/\n      name: ajaxspideractionscan\n      operations:\n      - method: GET\n        name:\
  \ ajaxspideractionscan\n        description: Runs the AJAX Spider against a given target.\n        call: owasp-zap.ajaxspideractionscan\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/scanAsUser/\n      name: ajaxspideractionscanasuser\n      operations:\n      - method: GET\n        name: ajaxspideractionscanasuser\n        description: Runs the AJAX Spider from the perspective of a User of the web application.\n        call: owasp-zap.ajaxspideractionscanasuser\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/setEnabledAllowedResource/\n      name: ajaxspideractionsetenabledallowedresource\n      operations:\n      - method: GET\n        name: ajaxspideractionsetenabledallowedresource\n        description: Sets whether or not an allowed resource is enabled.\n        call: owasp-zap.ajaxspideractionsetenabledallowedresource\n        outputParameters:\n        -\
  \ type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/action/setOptionBrowserId/\n      name: ajaxspideractionsetoptionbrowserid\n      operations:\n      - method: GET\n        name: ajaxspideractionsetoptionbrowserid\n        description: Sets the configuration of the AJAX Spider to use one of the supported browsers.\n        call: owasp-zap.ajaxspideractionsetoptionbrowserid\n        outputParameters:\n        - type: object\n          mapping: $.\n    - path: /JSON/ajaxSpider/actio\n\n# --- truncated at 32 KB (68 KB total) ---\n# Full source: https://raw.githubusercontent.com/api-evangelist/owasp-zap/refs/heads/main/capabilities/owasp-zap-capability.yaml\n"
source_yaml_url: https://raw.githubusercontent.com/api-evangelist/owasp-zap/refs/heads/main/capabilities/owasp-zap-capability.yaml
tags:
- Owasp
- Zap
- API
tools:
- description: 'Starts an Access Control scan with the given context ID and user ID. (Optional parameters: user ID for Unauthenticated user, boolean identifying whether or not Alerts are raised, and the Risk level for the Alerts.) [This assumes the Access'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: accesscontrolactionscan
- description: Generates an Access Control report for the given context ID and saves it based on the provided filename (path).
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: accesscontrolactionwritehtmlreport
- description: Gets the Access Control scan progress (percentage integer) for the given context ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: accesscontrolviewgetscanprogress
- description: Gets the Access Control scan status (description string) for the given context ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: accesscontrolviewgetscanstatus
- description: Adds an anti-CSRF token with the given name, enabled by default
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfactionaddoptiontoken
- description: Removes the anti-CSRF token with the given name
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfactionremoveoptiontoken
- description: Define if ZAP should detect CSRF tokens by searching for partial matches.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfactionsetoptionpartialmatchingenabled
- description: Generate a form for testing lack of anti-CSRF tokens - typically invoked via ZAP
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfothergenform
- description: Define if ZAP should detect CSRF tokens by searching for partial matches
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfviewoptionpartialmatchingenabled
- description: Lists the names of all anti-CSRF tokens
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: acsrfviewoptiontokensnames
- description: Adds an allowed resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionaddallowedresource
- description: Adds an excluded element to a context.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionaddexcludedelement
- description: Modifies an excluded element of a context.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionmodifyexcludedelement
- description: Removes an allowed resource.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionremoveallowedresource
- description: Removes an excluded element from a context.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionremoveexcludedelement
- description: Runs the AJAX Spider against a given target.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionscan
- description: Runs the AJAX Spider from the perspective of a User of the web application.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionscanasuser
- description: Sets whether or not an allowed resource is enabled.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetenabledallowedresource
- description: Sets the configuration of the AJAX Spider to use one of the supported browsers.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionbrowserid
- description: Sets whether or not the AJAX Spider will only click on the default HTML elements.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionclickdefaultelems
- description: When enabled, the crawler attempts to interact with each element (e.g., by clicking) only once.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionclickelemsonce
- description: GET /JSON/ajaxSpider/action/setOptionEnableExtensions/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionenableextensions
- description: 'Sets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptioneventwait
- description: Sets whether or not the AJAX Spider should avoid clicking logout elements.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionlogoutavoidance
- description: Sets the maximum depth that the crawler can reach.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionmaxcrawldepth
- description: Sets the maximum number of states that the crawler should crawl.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionmaxcrawlstates
- description: The maximum time that the crawler is allowed to run.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionmaxduration
- description: Sets the number of windows to be used by AJAX Spider.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionnumberofbrowsers
- description: When enabled, inserts random values into form fields.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionrandominputs
- description: Sets the time to wait after the page is loaded before interacting with it.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionreloadwait
- description: Sets the scope check.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionsetoptionscopecheck
- description: Stops the AJAX Spider.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspideractionstop
- description: Gets the allowed resources. The allowed resources are always fetched even if out of scope, allowing to include necessary resources (e.g. scripts) from 3rd-parties.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewallowedresources
- description: Gets the excluded elements. The excluded elements are not clicked during crawling, for example, to prevent logging out.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewexcludedelements
- description: Gets the full crawled content detected by the AJAX Spider. Returns a set of values based on 'inScope' URLs, 'outOfScope' URLs, and 'errors' encountered during the last/current run of the AJAX Spider.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewfullresults
- description: Gets the number of resources found.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewnumberofresults
- description: Gets the configured browser to use for crawling.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionbrowserid
- description: Gets the configured value for 'Click Default Elements Only', HTML elements such as 'a', 'button', 'input', all associated with some action or links on the page.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionclickdefaultelems
- description: Gets the value configured for the AJAX Spider to know if it should click on the elements only once.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionclickelemsonce
- description: GET /JSON/ajaxSpider/view/optionEnableExtensions/
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionenableextensions
- description: 'Gets the time to wait after an event (in milliseconds). For example: the wait delay after the cursor hovers over an element, in order for a menu to display, etc.'
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptioneventwait
- description: Gets the value of the Logout Avoidance option.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionlogoutavoidance
- description: Gets the configured value for the max crawl depth.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionmaxcrawldepth
- description: Gets the configured value for the maximum crawl states allowed.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionmaxcrawlstates
- description: Gets the configured max duration of the crawl, the value is in minutes.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionmaxduration
- description: Gets the configured number of browsers to be used.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionnumberofbrowsers
- description: Gets if the AJAX Spider will use random values in form fields when crawling, if set to true.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionrandominputs
- description: Gets the configured time to wait after reloading the page, this value is in milliseconds.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionreloadwait
- description: Gets the configured scope check.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewoptionscopecheck
- description: Gets the current results of the crawler.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewresults
- description: Gets the current status of the crawler. Actual values are Stopped and Running.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: ajaxspiderviewstatus
- description: Add an alert associated with the given message ID, with the provided details. (The ID of the created alert is returned.)
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactionaddalert
- description: Deletes the alert with the given ID.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactiondeletealert
- description: Deletes all the alerts optionally filtered by URL which fall within the Context with the provided name, risk, or base URL.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactiondeletealerts
- description: Deletes all alerts of the current session.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactiondeleteallalerts
- description: Update the alert with the given ID, with the provided details.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactionupdatealert
- description: Update the confidence of the alerts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactionupdatealertsconfidence
- description: Update the risk of the alerts.
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertactionupdatealertsrisk
- description: Gets the alert with the given ID, the corresponding HTTP message can be obtained with the 'messageId' field and 'message' API method
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertviewalert
- description: Gets a count of the alerts, optionally filtered as per alertsPerRisk
  hints:
    destructive: false
    idempotent: true
    readOnly: true
  name: alertviewalertcountsbyrisk
---
