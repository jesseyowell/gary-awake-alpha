---
title: Get person deletion status
excerpt: |
  Check on the status of a person deletion request.

  The response will include a status, e.g.
  ```
  {
    "err": 0,
    "result": {
      "state": "success", // possible values are "new","running","paused","success","cancelled","failed"
      "id": 3
    }
  }
  ```
api:
  file: rollbar-api-new.json
  operationId: get-person-deletion-status
hidden: false
---