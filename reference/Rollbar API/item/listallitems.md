---
title: List all items
excerpt: >
  # Examples

  Get the 101st through 199th active items:

  ```curl

  curl -H "X-Rollbar-Access-Token: YOUR_ACCESS_TOKEN"
  'https://api.rollbar.com/api/1/items/?status=active&page=2'

  ```

  Get the first page of items that are error or critical, in the production
  environment:

  ```curl

  curl -H "X-Rollbar-Access-Token: YOUR_ACCESS_TOKEN"
  'https://api.rollbar.com/api/1/items/?level=error&level=critical&environment=production'

  ```


  Note that the `total_count` in the `result` will return `null` if your project
  has more than 100,000 unique items.
api:
  file: rollbar-api-new.json
  operationId: list-all-items
hidden: false
---