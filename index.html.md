---
title: Alpha5 Documentation v1.0.0
language_tabs:
  - ruby: Ruby
  - python: Python
language_clients:
  - ruby: ""
  - python: ""
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="alpha5-documentation">Alpha5 Documentation v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Rest api spec

Base URLs:

* <a href="https://testing-api.alpha5.com/v1">https://testing-api.alpha5.com/v1</a>

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="alpha5-documentation-public">public</h1>

## Retrieves all available assets

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/get_assets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/get_assets', headers = headers)

print(r.json())

```

`GET /public/get_assets`

> Example responses

> 200 Response

```json
[
  {
    "symbol": "USDT",
    "name": "Ethereum",
    "precision": 8
  }
]
```

<h3 id="retrieves-all-available-assets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="retrieves-all-available-assets-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Asset](#schemaasset)]|false|none|none|
|» symbol|[AssetSymbol](#schemaassetsymbol)|false|none|Unique asset identifier|
|» name|string|false|none|none|
|» precision|number|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Gets all available trading contracts.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/get_live_contracts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/get_live_contracts', headers = headers)

print(r.json())

```

`GET /public/get_live_contracts`

<h3 id="gets-all-available-trading-contracts.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|[AssetSymbol](#schemaassetsymbol)|false|The asset symbol|
|type|query|[ContractType](#schemacontracttype)|false|Contrat type|
|expired|query|boolean|false|Set to true to show expired instruments instead of active ones.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|future|
|type|perpetual|

> Example responses

> 200 Response

```json
[
  {
    "symbol": "BTC-M20",
    "name": "BTC-June",
    "contract_type": "future",
    "settle_at": "2020-06-22T16:17:45Z",
    "launch_at": "2020-06-22T16:17:45Z",
    "tick_size": "0.5",
    "status": "operational",
    "initial_margin": "0.04",
    "maintainance_margin": "0.02",
    "maximum_position_limit": 1000,
    "quoting_asset": {
      "symbol": "USDT",
      "name": "Ethereum",
      "precision": 8
    },
    "settling_asset": {
      "symbol": "USDT",
      "name": "Ethereum",
      "precision": 8
    }
  }
]
```

<h3 id="gets-all-available-trading-contracts.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="gets-all-available-trading-contracts.-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Contract](#schemacontract)]|false|none|none|
|» symbol|[ContractSymbol](#schemacontractsymbol)|false|none|Unique contract identifier|
|» name|string|false|none|none|
|» contract_type|[ContractType](#schemacontracttype)|false|none|Type of contract|
|» settle_at|string(date-time)|false|none|Settle time|
|» launch_at|[DateTime](#schemadatetime)(date-time)|false|none|Launch time|
|» tick_size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» status|[ContractStatus](#schemacontractstatus)|false|none|Status of contract|
|» initial_margin|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» maintainance_margin|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» maximum_position_limit|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» quoting_asset|[Asset](#schemaasset)|false|none|none|
|»» symbol|[AssetSymbol](#schemaassetsymbol)|false|none|Unique asset identifier|
|»» name|string|false|none|none|
|»» precision|number|false|none|none|
|» settling_asset|[Asset](#schemaasset)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|contract_type|future|
|contract_type|perpetual|
|status|operational|
|status|disrupted|
|status|disrupted_post_only|
|status|expired|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Get ticker for an instrument.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/ticker',
  params: {
  'contract_symbol' => '[ContractSymbol](#schemacontractsymbol)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/ticker', params={
  'contract_symbol': 'BTC-M20'
}, headers = headers)

print(r.json())

```

`GET /public/ticker`

<h3 id="get-ticker-for-an-instrument.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contract_symbol|query|[ContractSymbol](#schemacontractsymbol)|true|Contract symbol|

> Example responses

> 200 Response

```json
{
  "open": "10.000",
  "high": "10.000",
  "low": "10.000",
  "close": "10.000",
  "timestamp": 1592828815073
}
```

<h3 id="get-ticker-for-an-instrument.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A contract ticker|[Ticker](#schematicker)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieves the order book

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/order_book',
  params: {
  'contract_symbol' => '[ContractSymbol](#schemacontractsymbol)'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/order_book', params={
  'contract_symbol': 'BTC-M20'
}, headers = headers)

print(r.json())

```

`GET /public/order_book`

<h3 id="retrieves-the-order-book-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contract_symbol|query|[ContractSymbol](#schemacontractsymbol)|true|Symbol of contract|
|depth|query|number|false|The number of entries to return for buy and sell side|

> Example responses

> 200 Response

```json
{
  "depth": 20,
  "buy": [
    {
      "price": "9200.23",
      "size": "779"
    }
  ],
  "sell": [
    {
      "price": "9200.23",
      "size": "779"
    }
  ]
}
```

<h3 id="retrieves-the-order-book-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A state of contract orderbook|[Orderbook](#schemaorderbook)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieves latest trades for an intrument

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/recent_trades',
  params: {
  'asset' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/recent_trades', params={
  'asset': 'string'
}, headers = headers)

print(r.json())

```

`GET /public/recent_trades`

<h3 id="retrieves-latest-trades-for-an-intrument-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|string|true|The asset symbol|
|count|query|number|false|Number of requested items, default - `10`|

> Example responses

> 200 Response

```json
[
  {
    "side": "buy",
    "price": "10.000",
    "size": "10.000",
    "timestamp": 1592828815073
  }
]
```

<h3 id="retrieves-latest-trades-for-an-intrument-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of trades|Inline|

<h3 id="retrieves-latest-trades-for-an-intrument-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[RecentTrade](#schemarecenttrade)]|false|none|none|
|» side|[Side](#schemaside)|false|none|Side of trade|
|» price|any|false|none|Price of trade|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» size|any|false|none|Size of trade|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» timestamp|number|false|none|Trade timestamp|

#### Enumerated Values

|Property|Value|
|---|---|
|side|buy|
|side|sell|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

<h1 id="alpha5-documentation-trading">trading</h1>

## Places an order for a contract.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/place_order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/place_order', headers = headers)

print(r.json())

```

`POST /account/place_order`

> Body parameter

```json
{
  "contract_symbol": "BTC-M20",
  "type": "limit",
  "size": "2.3",
  "price": "9412.22",
  "stop_price": "9522.12",
  "time_in_force": "good_til_cancelled",
  "post_only": false,
  "reduce_only": false,
  "trigger": "mark_price"
}
```

<h3 id="places-an-order-for-a-contract.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» contract_symbol|body|[ContractSymbol](#schemacontractsymbol)|true|Unique contract identifier|
|» type|body|string|false|none|
|»» *anonymous*|body|[OrderType](#schemaordertype)|false|Type of order|
|»» *anonymous*|body|[StopOrderType](#schemastopordertype)|false|Type of stop order|
|» size|body|any|true|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|
|» price|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|
|» stop_price|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|
|» time_in_force|body|[TimeInForce](#schematimeinforce)|false|none|
|» post_only|body|boolean|false|<p>If true, the order is considered post-only. If the new price would cause the order to be filled immediately (as taker), the price will be changed to be just below the bid.</p> <p>Only valid in combination with time_in_force=`"good_til_cancelled"`</p>|
|» reduce_only|body|boolean|false|If `true`, the order is considered reduce-only which is intended to only reduce a current position|
|» trigger|body|[StopOrderTrigger](#schemastopordertrigger)|false|Trigger type (Only for stop orders)|

#### Enumerated Values

|Parameter|Value|
|---|---|
|»» *anonymous*|limit|
|»» *anonymous*|market|
|»» *anonymous*|stop_limit|
|»» *anonymous*|stop_market|
|» time_in_force|good_til_cancelled|
|» time_in_force|fill_or_kill|
|» time_in_force|immediate_or_cancel|
|» trigger|index_price|
|» trigger|mark_price|
|» trigger|last_price|

> Example responses

> 200 Response

```json
{
  "id": "d25c9454-b488-11ea-b3de-0242ac130004",
  "type": "limit",
  "side": "buy",
  "status": "limit",
  "limit_price": "7891.33",
  "stop_price": "7891.30",
  "size": "1.33",
  "filled_size": "0.771",
  "cancelled_size": "0.12",
  "time_in_force": "good_til_cancelled",
  "contract": {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "symbol": "BTC-M20"
  }
}
```

<h3 id="places-an-order-for-a-contract.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|An order response|[Order](#schemaorder)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Cancel remaining size of the order and place a new one

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/edit_order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/edit_order', headers = headers)

print(r.json())

```

`POST /account/edit_order`

> Body parameter

```json
{
  "order_id": "d25c9454-b488-11ea-b3de-0242ac130004",
  "size": "2.3",
  "price": "9412.22"
}
```

<h3 id="cancel-remaining-size-of-the-order-and-place-a-new-one-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» order_id|body|[UUID](#schemauuid)|true|Unique identifier|
|» size|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|
|» price|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "id": "d25c9454-b488-11ea-b3de-0242ac130004",
  "type": "limit",
  "side": "buy",
  "status": "limit",
  "limit_price": "7891.33",
  "stop_price": "7891.30",
  "size": "1.33",
  "filled_size": "0.771",
  "cancelled_size": "0.12",
  "time_in_force": "good_til_cancelled",
  "contract": {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "symbol": "BTC-M20"
  }
}
```

<h3 id="cancel-remaining-size-of-the-order-and-place-a-new-one-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|An edit order response|[Order](#schemaorder)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieves list of user's open orders.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_open_orders',
  params: {
  'contract_symbol' => 'any'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_open_orders', params={
  'contract_symbol': 'BTC-M20'
}, headers = headers)

print(r.json())

```

`GET /account/get_open_orders`

<h3 id="retrieves-list-of-user's-open-orders.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|any|false|The asset symbol|
|contract_symbol|query|any|true|Contract unique symbol|
|contract_type|query|any|false|Contract types|
|page_size|query|integer(int32)|false|Size of page|
|current_page|query|integer(int32)|false|Limits the number of returned results|

> Example responses

> 200 Response

```json
[
  {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "type": "limit",
    "side": "buy",
    "status": "limit",
    "limit_price": "7891.33",
    "stop_price": "7891.30",
    "size": "1.33",
    "filled_size": "0.771",
    "cancelled_size": "0.12",
    "time_in_force": "good_til_cancelled",
    "contract": {
      "id": "d25c9454-b488-11ea-b3de-0242ac130004",
      "symbol": "BTC-M20"
    }
  }
]
```

<h3 id="retrieves-list-of-user's-open-orders.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of orders|Inline|

<h3 id="retrieves-list-of-user's-open-orders.-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Order](#schemaorder)]|false|none|none|
|» id|[UUID](#schemauuid)|false|none|Unique order identifier|
|» type|[OrderType](#schemaordertype)|false|none|Type of order|
|» side|[Side](#schemaside)|false|none|Side|
|» status|[OrderStatus](#schemaorderstatus)|false|none|Type of order|
|» limit_price|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» stop_price|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» filled_size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» cancelled_size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» time_in_force|[TimeInForce](#schematimeinforce)|false|none|none|
|» contract|object|false|none|none|
|»» id|string|false|none|Unique contract identifier|
|»» symbol|[ContractSymbol](#schemacontractsymbol)|false|none|Unique contract identifier|

#### Enumerated Values

|Property|Value|
|---|---|
|type|limit|
|type|market|
|side|buy|
|side|sell|
|status|open|
|status|filled|
|time_in_force|good_til_cancelled|
|time_in_force|fill_or_kill|
|time_in_force|immediate_or_cancel|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|X-Pagination-Current-Page|integer||Current page of pagination|
|200|X-Pagination-Page-Size|integer||Current page size|
|200|X-Pagination-Total-Count|integer||Total count of itmes|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Cancel all orders by the param

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/cancel_all_open_orders',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/cancel_all_open_orders', headers = headers)

print(r.json())

```

`POST /account/cancel_all_open_orders`

> Body parameter

```json
{
  "asset": "USDT",
  "contract_symbol": "BTC-M20",
  "contract_type": "future"
}
```

<h3 id="cancel-all-orders-by-the-param-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» asset|body|[AssetSymbol](#schemaassetsymbol)|false|Unique asset identifier|
|» contract_symbol|body|[ContractSymbol](#schemacontractsymbol)|false|Unique contract identifier|
|» contract_type|body|[ContractType](#schemacontracttype)|false|Type of contract|

#### Enumerated Values

|Parameter|Value|
|---|---|
|» contract_type|future|
|» contract_type|perpetual|

<h3 id="cancel-all-orders-by-the-param-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A cancellation response|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Cancel an order, specified by order id

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/cancel_order',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/cancel_order', headers = headers)

print(r.json())

```

`POST /account/cancel_order`

> Body parameter

```json
{
  "order_id": "d25c9454-b488-11ea-b3de-0242ac130004"
}
```

<h3 id="cancel-an-order,-specified-by-order-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» order_id|body|[UUID](#schemauuid)|true|Unique identifier|

> Example responses

> 200 Response

```json
{
  "id": "d25c9454-b488-11ea-b3de-0242ac130004",
  "type": "limit",
  "side": "buy",
  "status": "limit",
  "limit_price": "7891.33",
  "stop_price": "7891.30",
  "size": "1.33",
  "filled_size": "0.771",
  "cancelled_size": "0.12",
  "time_in_force": "good_til_cancelled",
  "contract": {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "symbol": "BTC-M20"
  }
}
```

<h3 id="cancel-an-order,-specified-by-order-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|An order cancellation response|[Order](#schemaorder)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieve user positions.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_positions',
  params: {
  'asset' => 'string',
'contract_symbol' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_positions', params={
  'asset': 'string',  'contract_symbol': 'string'
}, headers = headers)

print(r.json())

```

`GET /account/get_positions`

<h3 id="retrieve-user-positions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|string|true|The asset symbol|
|contract_symbol|query|string|true|Contract unique symbol|

> Example responses

> 200 Response

```json
[
  {
    "side": "buy",
    "price": "10.000",
    "contract_id": "d25c9454-b488-11ea-b3de-0242ac130004"
  }
]
```

<h3 id="retrieve-user-positions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of positions|Inline|

<h3 id="retrieve-user-positions.-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Position](#schemaposition)]|false|none|none|
|» side|[Side](#schemaside)|false|none|Side of trade|
|» price|any|false|none|Price of trade|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» contract_id|[UUID](#schemauuid)|false|none|Unique identifier|

#### Enumerated Values

|Property|Value|
|---|---|
|side|buy|
|side|sell|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Close an open position

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/close_position',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/close_position', headers = headers)

print(r.json())

```

`POST /account/close_position`

> Body parameter

```json
{
  "contract_symbol": "BTC-M20",
  "price": "10.000"
}
```

<h3 id="close-an-open-position-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» contract_symbol|body|[ContractSymbol](#schemacontractsymbol)|true|Unique contract identifier|
|» price|body|any|false|none|
|»» *anonymous*|body|number|false|none|
|»» *anonymous*|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "side": "buy",
  "price": "10.000",
  "contract_id": "d25c9454-b488-11ea-b3de-0242ac130004"
}
```

<h3 id="close-an-open-position-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A close position response|[Position](#schemaposition)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieve the list of user trades. Pagination supported.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_user_trades',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_user_trades', headers = headers)

print(r.json())

```

`GET /account/get_user_trades`

<h3 id="retrieve-the-list-of-user-trades.-pagination-supported.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_id|query|[UUID](#schemauuid)|false|The order id|

<h3 id="retrieve-the-list-of-user-trades.-pagination-supported.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of trades|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

## Retrieves history of orders that have been partially or fully filled.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_order_history',
  params: {
  'asset' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_order_history', params={
  'asset': 'string'
}, headers = headers)

print(r.json())

```

`GET /account/get_order_history`

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|string|true|The asset symbol|
|contract_type|query|any|false|Contract types|
|page_size|query|integer(int32)|false|Size of page|
|current_page|query|integer(int32)|false|Limits the number of returned results|

> Example responses

> 200 Response

```json
[
  {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "type": "limit",
    "side": "buy",
    "status": "limit",
    "limit_price": "7891.33",
    "stop_price": "7891.30",
    "size": "1.33",
    "filled_size": "0.771",
    "cancelled_size": "0.12",
    "time_in_force": "good_til_cancelled",
    "contract": {
      "id": "d25c9454-b488-11ea-b3de-0242ac130004",
      "symbol": "BTC-M20"
    }
  }
]
```

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A list of orders|Inline|

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Order](#schemaorder)]|false|none|none|
|» id|[UUID](#schemauuid)|false|none|Unique order identifier|
|» type|[OrderType](#schemaordertype)|false|none|Type of order|
|» side|[Side](#schemaside)|false|none|Side|
|» status|[OrderStatus](#schemaorderstatus)|false|none|Type of order|
|» limit_price|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» stop_price|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» filled_size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» cancelled_size|any|false|none|none|

*oneOf*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|number|false|none|none|

*xor*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|»» *anonymous*|string|false|none|none|

*continued*

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» time_in_force|[TimeInForce](#schematimeinforce)|false|none|none|
|» contract|object|false|none|none|
|»» id|string|false|none|Unique contract identifier|
|»» symbol|[ContractSymbol](#schemacontractsymbol)|false|none|Unique contract identifier|

#### Enumerated Values

|Property|Value|
|---|---|
|type|limit|
|type|market|
|side|buy|
|side|sell|
|status|open|
|status|filled|
|time_in_force|good_til_cancelled|
|time_in_force|fill_or_kill|
|time_in_force|immediate_or_cancel|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|X-Pagination-Current-Page|integer||Current page of pagination|
|200|X-Pagination-Page-Size|integer||Current page size|
|200|X-Pagination-Total-Count|integer||Total count of itmes|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BearerAuth
</aside>

# Schemas

<h2 id="tocS_UUID">UUID</h2>
<!-- backwards compatibility -->
<a id="schemauuid"></a>
<a id="schema_UUID"></a>
<a id="tocSuuid"></a>
<a id="tocsuuid"></a>

```json
"d25c9454-b488-11ea-b3de-0242ac130004"

```

Unique identifier

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Unique identifier|

<h2 id="tocS_Decimal">Decimal</h2>
<!-- backwards compatibility -->
<a id="schemadecimal"></a>
<a id="schema_Decimal"></a>
<a id="tocSdecimal"></a>
<a id="tocsdecimal"></a>

```json
"10.000"

```

### Properties

oneOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|number|false|none|none|

xor

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

<h2 id="tocS_DateTime">DateTime</h2>
<!-- backwards compatibility -->
<a id="schemadatetime"></a>
<a id="schema_DateTime"></a>
<a id="tocSdatetime"></a>
<a id="tocsdatetime"></a>

```json
"2020-06-22T16:17:45Z"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string(date-time)|false|none|none|

<h2 id="tocS_AssetSymbol">AssetSymbol</h2>
<!-- backwards compatibility -->
<a id="schemaassetsymbol"></a>
<a id="schema_AssetSymbol"></a>
<a id="tocSassetsymbol"></a>
<a id="tocsassetsymbol"></a>

```json
"USDT"

```

Unique asset identifier

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Unique asset identifier|

<h2 id="tocS_SpotSymbol">SpotSymbol</h2>
<!-- backwards compatibility -->
<a id="schemaspotsymbol"></a>
<a id="schema_SpotSymbol"></a>
<a id="tocSspotsymbol"></a>
<a id="tocsspotsymbol"></a>

```json
"ETHUSDT"

```

Unique spot market identifier

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Unique spot market identifier|

<h2 id="tocS_ContractSymbol">ContractSymbol</h2>
<!-- backwards compatibility -->
<a id="schemacontractsymbol"></a>
<a id="schema_ContractSymbol"></a>
<a id="tocScontractsymbol"></a>
<a id="tocscontractsymbol"></a>

```json
"BTC-M20"

```

Unique contract identifier

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Unique contract identifier|

<h2 id="tocS_Side">Side</h2>
<!-- backwards compatibility -->
<a id="schemaside"></a>
<a id="schema_Side"></a>
<a id="tocSside"></a>
<a id="tocsside"></a>

```json
"buy"

```

Side

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Side|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|buy|
|*anonymous*|sell|

<h2 id="tocS_ContractType">ContractType</h2>
<!-- backwards compatibility -->
<a id="schemacontracttype"></a>
<a id="schema_ContractType"></a>
<a id="tocScontracttype"></a>
<a id="tocscontracttype"></a>

```json
"future"

```

Type of contract

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Type of contract|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|future|
|*anonymous*|perpetual|

<h2 id="tocS_ContractStatus">ContractStatus</h2>
<!-- backwards compatibility -->
<a id="schemacontractstatus"></a>
<a id="schema_ContractStatus"></a>
<a id="tocScontractstatus"></a>
<a id="tocscontractstatus"></a>

```json
"operational"

```

Status of contract

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Status of contract|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|operational|
|*anonymous*|disrupted|
|*anonymous*|disrupted_post_only|
|*anonymous*|expired|

<h2 id="tocS_OrderType">OrderType</h2>
<!-- backwards compatibility -->
<a id="schemaordertype"></a>
<a id="schema_OrderType"></a>
<a id="tocSordertype"></a>
<a id="tocsordertype"></a>

```json
"limit"

```

Type of order

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Type of order|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|limit|
|*anonymous*|market|

<h2 id="tocS_OrderStatus">OrderStatus</h2>
<!-- backwards compatibility -->
<a id="schemaorderstatus"></a>
<a id="schema_OrderStatus"></a>
<a id="tocSorderstatus"></a>
<a id="tocsorderstatus"></a>

```json
"limit"

```

Type of order

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Type of order|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|open|
|*anonymous*|filled|

<h2 id="tocS_StopOrderType">StopOrderType</h2>
<!-- backwards compatibility -->
<a id="schemastopordertype"></a>
<a id="schema_StopOrderType"></a>
<a id="tocSstopordertype"></a>
<a id="tocsstopordertype"></a>

```json
"stop_limit"

```

Type of stop order

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Type of stop order|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|stop_limit|
|*anonymous*|stop_market|

<h2 id="tocS_StopOrderTrigger">StopOrderTrigger</h2>
<!-- backwards compatibility -->
<a id="schemastopordertrigger"></a>
<a id="schema_StopOrderTrigger"></a>
<a id="tocSstopordertrigger"></a>
<a id="tocsstopordertrigger"></a>

```json
"mark_price"

```

Trigger for stop order

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|Trigger for stop order|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|index_price|
|*anonymous*|mark_price|
|*anonymous*|last_price|

<h2 id="tocS_TimeInForce">TimeInForce</h2>
<!-- backwards compatibility -->
<a id="schematimeinforce"></a>
<a id="schema_TimeInForce"></a>
<a id="tocStimeinforce"></a>
<a id="tocstimeinforce"></a>

```json
"good_til_cancelled"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|good_til_cancelled|
|*anonymous*|fill_or_kill|
|*anonymous*|immediate_or_cancel|

<h2 id="tocS_PricePoint">PricePoint</h2>
<!-- backwards compatibility -->
<a id="schemapricepoint"></a>
<a id="schema_PricePoint"></a>
<a id="tocSpricepoint"></a>
<a id="tocspricepoint"></a>

```json
{
  "price": "9200.23",
  "size": "779"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|price|[Decimal](#schemadecimal)|false|none|none|
|size|[Decimal](#schemadecimal)|false|none|none|

<h2 id="tocS_Asset">Asset</h2>
<!-- backwards compatibility -->
<a id="schemaasset"></a>
<a id="schema_Asset"></a>
<a id="tocSasset"></a>
<a id="tocsasset"></a>

```json
{
  "symbol": "USDT",
  "name": "Ethereum",
  "precision": 8
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|symbol|[AssetSymbol](#schemaassetsymbol)|false|none|Unique asset identifier|
|name|string|false|none|none|
|precision|number|false|none|none|

<h2 id="tocS_Contract">Contract</h2>
<!-- backwards compatibility -->
<a id="schemacontract"></a>
<a id="schema_Contract"></a>
<a id="tocScontract"></a>
<a id="tocscontract"></a>

```json
{
  "symbol": "BTC-M20",
  "name": "BTC-June",
  "contract_type": "future",
  "settle_at": "2020-06-22T16:17:45Z",
  "launch_at": "2020-06-22T16:17:45Z",
  "tick_size": "0.5",
  "status": "operational",
  "initial_margin": "0.04",
  "maintainance_margin": "0.02",
  "maximum_position_limit": 1000,
  "quoting_asset": {
    "symbol": "USDT",
    "name": "Ethereum",
    "precision": 8
  },
  "settling_asset": {
    "symbol": "USDT",
    "name": "Ethereum",
    "precision": 8
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|symbol|[ContractSymbol](#schemacontractsymbol)|false|none|Unique contract identifier|
|name|string|false|none|none|
|contract_type|[ContractType](#schemacontracttype)|false|none|Type of contract|
|settle_at|string(date-time)|false|none|Settle time|
|launch_at|[DateTime](#schemadatetime)|false|none|Launch time|
|tick_size|[Decimal](#schemadecimal)|false|none|none|
|status|[ContractStatus](#schemacontractstatus)|false|none|Status of contract|
|initial_margin|[Decimal](#schemadecimal)|false|none|none|
|maintainance_margin|[Decimal](#schemadecimal)|false|none|none|
|maximum_position_limit|[Decimal](#schemadecimal)|false|none|none|
|quoting_asset|[Asset](#schemaasset)|false|none|none|
|settling_asset|[Asset](#schemaasset)|false|none|none|

<h2 id="tocS_Ticker">Ticker</h2>
<!-- backwards compatibility -->
<a id="schematicker"></a>
<a id="schema_Ticker"></a>
<a id="tocSticker"></a>
<a id="tocsticker"></a>

```json
{
  "open": "10.000",
  "high": "10.000",
  "low": "10.000",
  "close": "10.000",
  "timestamp": 1592828815073
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|open|[Decimal](#schemadecimal)|false|none|none|
|high|[Decimal](#schemadecimal)|false|none|none|
|low|[Decimal](#schemadecimal)|false|none|none|
|close|[Decimal](#schemadecimal)|false|none|none|
|timestamp|number|false|none|Trade timestamp|

<h2 id="tocS_Orderbook">Orderbook</h2>
<!-- backwards compatibility -->
<a id="schemaorderbook"></a>
<a id="schema_Orderbook"></a>
<a id="tocSorderbook"></a>
<a id="tocsorderbook"></a>

```json
{
  "depth": 20,
  "buy": [
    {
      "price": "9200.23",
      "size": "779"
    }
  ],
  "sell": [
    {
      "price": "9200.23",
      "size": "779"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|depth|integer|false|none|none|
|buy|[[PricePoint](#schemapricepoint)]|false|none|none|
|sell|[[PricePoint](#schemapricepoint)]|false|none|none|

<h2 id="tocS_RecentTrade">RecentTrade</h2>
<!-- backwards compatibility -->
<a id="schemarecenttrade"></a>
<a id="schema_RecentTrade"></a>
<a id="tocSrecenttrade"></a>
<a id="tocsrecenttrade"></a>

```json
{
  "side": "buy",
  "price": "10.000",
  "size": "10.000",
  "timestamp": 1592828815073
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|side|[Side](#schemaside)|false|none|Side of trade|
|price|[Decimal](#schemadecimal)|false|none|Price of trade|
|size|[Decimal](#schemadecimal)|false|none|Size of trade|
|timestamp|number|false|none|Trade timestamp|

<h2 id="tocS_Position">Position</h2>
<!-- backwards compatibility -->
<a id="schemaposition"></a>
<a id="schema_Position"></a>
<a id="tocSposition"></a>
<a id="tocsposition"></a>

```json
{
  "side": "buy",
  "price": "10.000",
  "contract_id": "d25c9454-b488-11ea-b3de-0242ac130004"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|side|[Side](#schemaside)|false|none|Side of trade|
|price|[Decimal](#schemadecimal)|false|none|Price of trade|
|contract_id|[UUID](#schemauuid)|false|none|Unique identifier|

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "id": "d25c9454-b488-11ea-b3de-0242ac130004",
  "type": "limit",
  "side": "buy",
  "status": "limit",
  "limit_price": "7891.33",
  "stop_price": "7891.30",
  "size": "1.33",
  "filled_size": "0.771",
  "cancelled_size": "0.12",
  "time_in_force": "good_til_cancelled",
  "contract": {
    "id": "d25c9454-b488-11ea-b3de-0242ac130004",
    "symbol": "BTC-M20"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|[UUID](#schemauuid)|false|none|Unique order identifier|
|type|[OrderType](#schemaordertype)|false|none|Type of order|
|side|[Side](#schemaside)|false|none|Side|
|status|[OrderStatus](#schemaorderstatus)|false|none|Type of order|
|limit_price|[Decimal](#schemadecimal)|false|none|none|
|stop_price|[Decimal](#schemadecimal)|false|none|none|
|size|[Decimal](#schemadecimal)|false|none|none|
|filled_size|[Decimal](#schemadecimal)|false|none|none|
|cancelled_size|[Decimal](#schemadecimal)|false|none|none|
|time_in_force|[TimeInForce](#schematimeinforce)|false|none|none|
|contract|object|false|none|none|
|» id|string|false|none|Unique contract identifier|
|» symbol|[ContractSymbol](#schemacontractsymbol)|false|none|Unique contract identifier|

