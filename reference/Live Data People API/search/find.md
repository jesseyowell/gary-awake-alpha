---
title: Find people
excerpt: >-
  Find people in Live Data that match the given criteria. For people finding,
  the following fields are supported: `name`, `title`, `linkedin`,
  `company.name`, `company.linkedin`, `email_address`, `company.ticker`,
  `company.domain`, `education.school`. The `matches` array has a max size of
  100. For each item in the match array, the response will contain all people
  that match the provided fields with a `score` of how well the person matches
  the input fields, with a maximum 5 hits per match. For queries where the
  number of results is expected to be higher than 5, try the `/search` endpoint.
api:
  file: livedata-people-api.json
  operationId: find
hidden: false
---