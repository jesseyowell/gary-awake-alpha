---
title: Occurrences over a span of time
excerpt: >
  Get occurrences metrics over a span of time by filtering, grouping, and
  aggregating. The endpoint follows search/query semantics as a POST request
  using project read access token.


  List of **columns/fields** that can be used with some components of your
  query:

  * `project_id`

  * `item_id`

  * `environment`

  * `browser_family`

  * `browser_version`

  * `os_family`

  * `os_version`

  * `device_brand`

  * `device_model`

  * `ip_address`

  * `item_status`

  * `item_level`

  * `item_group_item_id`

  * `item_title`

  * `item_counter`

  * `person_username`

  * `person_email`

  * `person_id`

  * `code_version`

  * `count`

  * `occurrence_id`

  * `uuid`

  * `context`

  * `platform`

  * `framework`

  * `platform_canonical`

  * `framework_canonical`

  * `language`

  * `language_name`

  * `notifier_name`

  * `notifier_version`

  * `occurrence_count`

  * `message_body`

  * `timestamp`

  * `fingerprint`

  * `server_host`

  * `server_root`

  * `server_pid`

  * `server_cpu`

  * `scm_branch`

  * `request_url`

  * `request_method`

  * `request_query_string`

  * `request_body`
api:
  file: rollbar-api-new.json
  operationId: post_api-1-metrics-occurrences
hidden: false
---