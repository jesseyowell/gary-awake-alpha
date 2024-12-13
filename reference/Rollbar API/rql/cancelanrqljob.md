---
title: Cancel an RQL job
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
      "status": "cancelled", // One of "new", "running", "success", "failed", "cancelled", or "timed_out"
      "job_hash": "abcdefabcdefabcdef",
      "date_created": 1446598885,
      "date_modified": 1446598885
    }
  }```
api:
  file: Usersjyowelloasrollbar-api-new.json
  operationId: cancel-an-rql-job
hidden: false
---