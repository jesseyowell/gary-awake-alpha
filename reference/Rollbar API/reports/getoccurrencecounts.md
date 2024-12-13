---
title: Get active occurrence counts
excerpt: >
  Analogous to "Hourly Error/Critical Occurrences" and "Daily Error/Critical
  Occurrences" on the Project Dashboard.


  Returns an array of recent counts as `[timestamp, count]` pairs, where each
  count is the number of matching active occurrences in the time range
  `[timestamp, timestamp + bucket_size - 1]`.


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
  file: rollbar-api-new.json
  operationId: get-occurrence-counts
hidden: false
---