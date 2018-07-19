---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - r

toc_footers:
  - <a href='https://www.disarm.io'>Read more about DiSARM</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the DiSARM API! You can use our API to access some of our spatial analysis models written by our data scientists.

All of our examples are in cURL, but can be used from any programming language with an HTTP library. Some examples are given, e.g. for accessing using R.

# space_time_forecast

## Overview

Given a set of counts at locations per n time periods, the algorithm
will forecast the number at time n+1

### Applicable Scenarios and Problems

Forecasting counts of an event (e.g. numbers of disease cases, numbers
of tests used) where locations are known and data are available for
multiple time periods.

## Usage

### Input

Requires nested json of 2 tables.

The first table should be named 'count\_data' and should contain 3
fields:

1.  'site' a numeric or character ID for each site
2.  'count' the number of the outcome/events
3.  'time' the time period in whole integers. These donâ€™t have to be
    equally spaced.

The second table should be named 'coordinates' and should contain 3
fields:

1.  'site' a numeric or character ID for each site. Must contain all the
    sites present in the 'count\_data' table
2.  'lng' the longitude of each site
3.  'lat' the latitude of each site

### Output

A json containing 2 fields

1.  'site' the site ID
2.  'forecast' the predicted number of events in time n+1

## Examples


```r
[[][[],[[][1,]][[[3,[[[[][[][[]]]]]]],],],],],,],
```

```shell
curl -X POST -d '{"name": "bob"}' -H 'Content-Type: application/json' https://algo-api-demo.disarm.io/v1/algo/locational/testalgo1/0.1.0
```

Greet Bob...

> The above command sends back

```json
"Hello bob"
```


# Authentication

> To authorize, use this code:

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Sample docs for 'Kittens'

Leaving these in for reference only.

## Get All Kittens

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete


