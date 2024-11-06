---
title: Verify record
excerpt: >-
  Takes an array of queries and responds with a corresponding array of results.
  The response array will always be the same size as the request array and the
  elements will be in the same order as the request. For each item in the input
  array:


  Given a unique person ID (in the form of a LinkedIn URL) and a Company (either
  name or linkedin URL), validates whether this person still works at the given
  company. 


  Since only a company name string is provided and there can be variations of
  company names, this endpoint implements unique logic to determine if the
  company is the same and does not guarantee the provided name matches exactly.


  The `ldt_status` return field is an enumerated field with the values:

  * `same_co` - the person is at the same company as the provided input company

  * `new_co` - the person is at a different company than the one provided

  * `no_current_company` - the person is currently not associated with a company

  * `not_found` - the person was not found in the Live Data system


  In all cases, the `current_position` object provides the latest information
  from the Live Data system.
api:
  file: livedata-people-api.json
  operationId: verify
hidden: false
---