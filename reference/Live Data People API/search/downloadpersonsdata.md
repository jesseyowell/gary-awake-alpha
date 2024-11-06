---
title: Download person data
excerpt: >
  Download people as a CSV based on specified search criteria. This call returns
  a CSV file -- for JSON using the same filters, see `POST .../search`.


  Nested object names are exported using dot-notation, e.g.
  `position.company.name`.


  This endpoint will always download all records that match the provided
  criteria. Large results may take some time to download.


  Please note that including many past jobs and related fields will result in a
  lot of columns in the CSV, so consider limiting the results returned using the
  `past_jobs` and `return_fields` parameters.
api:
  file: livedata-people-api.json
  operationId: download-persons-data
hidden: false
---