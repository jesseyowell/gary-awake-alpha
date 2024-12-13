---
title: Get activated item counts
excerpt: >
  Analogous to "Daily New/Reactivated Items" graph on the Project Dashboard.


  Returns an array of recent counts as `[timestamp, count]` pairs, where each
  count is the number of items that were first seen or reactivated in the time
  range `[timestamp, timestamp + bucket_size - 1]`.


  Timestamps are UNIX timestamps, in whole seconds.




  # Response

  ```json

  {
    "err": 0,
    "result": [
      [
        // timestamp
        1728561200,
        // count (number of occurrences from time 1728561200 until time 1728564799)
        0
      ],
      [
        1728564800,
        0
      ],
      [
        1728568400,
        0
      ],
      [
        1728572000,
        6
      ]
    ]
  }```
api:
  file: dupe-rollbar-api.json
  operationId: get-activated-item-counts
hidden: false
---