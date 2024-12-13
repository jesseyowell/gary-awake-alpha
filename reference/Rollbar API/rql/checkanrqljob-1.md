---
title: Check an RQL job
excerpt: |
  # Response
  The response will be a RQL Job resource, example:
  ```json
  {
    "err" 0,
    "result": {
      "id": 123,  // job id
      "project_id": 456,
      "query_string": "show tables",
      "status": "new", // One of "new", "running", "success", "failed", "cancelled", or "timed_out"
      "job_hash": "abcdefabcdefabcdef",
      "date_created": 1446598885,
      "date_modified": 1446598885,
      "result": {...} // A RQL job resource if expand=result is used in query string
    }
  }``
api:
  file: dupe-rollbar-api.json
  operationId: check-an-rql-job
hidden: false
---