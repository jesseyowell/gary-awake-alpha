---
title: Get an occurrence
excerpt: >
  Returns a JSON object describing the occurrence. This is similar to the "Raw
  JSON" section of the occurrence detail page.


  `instance_id` must be an Occurrence ID for an occurrence in the project. These
  IDs are returned as the `id`

  field in other occurrence API calls, and can be found in the Rollbar UI on
  URLs like

  `https://rollbar.com/Rollbar/demo/items/54/occurrences/3209095494/`
  (`3209095494` is the Occurrence ID).
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: get_api-1-instance-instance-id
hidden: false
---