---
title: Alpha5 Documentation
language_tabs:
  - ruby: Ruby
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<h1 id="alpha5-documentation">Alpha5 Documentation v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Rest api spec

Base URLs:

* <a href="https://testing-api.alpha5.com/v1">https://testing-api.alpha5.com/v1</a>

<h1 id="alpha5-documentation-public">public</h1>

## Retrieves all live assets.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/get_assets',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/get_assets', params={

}, headers = headers)

print r.json()

```

`GET /public/get_assets`

> Example responses

```json
{}
```

<h3 id="retrieves-all-live-assets.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-all-live-assets.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Gets all available trading contracts.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/get_live_contracts',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/get_live_contracts', params={

}, headers = headers)

print r.json()

```

`GET /public/get_live_contracts`

<h3 id="gets-all-available-trading-contracts.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|string|false|The asset symbol|
|type|query|string|false|Contrat type|
|expired|query|boolean|false|Set to true to show expired instruments instead of active ones.|

> Example responses

```json
{}
```

<h3 id="gets-all-available-trading-contracts.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="gets-all-available-trading-contracts.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Get ticker for an instrument.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/ticker',
  params: {
  'contract_symbol' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/ticker', params={
  'contract_symbol': 'BTC-PERPETUAL'
}, headers = headers)

print r.json()

```

`GET /public/ticker`

<h3 id="get-ticker-for-an-instrument.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contract_symbol|query|string|true|Contract symbol|

> Example responses

```json
{}
```

<h3 id="get-ticker-for-an-instrument.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="get-ticker-for-an-instrument.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

<h1 id="alpha5-documentation-market_data">market_data</h1>

## Retrieves the order book

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/order_book',
  params: {
  'contract_symbol' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/order_book', params={
  'contract_symbol': 'string'
}, headers = headers)

print r.json()

```

`GET /public/order_book`

<h3 id="retrieves-the-order-book-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contract_symbol|query|string|true|contract unique identifier|
|depth|query|number|false|The number of entries to return for bids and asks.|

> Example responses

```json
{}
```

<h3 id="retrieves-the-order-book-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-the-order-book-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieves latest trades for an intrument

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/public/recent_trades',
  params: {
  'asset' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/public/recent_trades', params={
  'asset': undefined
}, headers = headers)

print r.json()

```

`GET /public/recent_trades`

<h3 id="retrieves-latest-trades-for-an-intrument-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|
|count|query|undefined|false|Number of requested items, default - `10`|

> Example responses

```json
{}
```

<h3 id="retrieves-latest-trades-for-an-intrument-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-latest-trades-for-an-intrument-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

<h1 id="alpha5-documentation-account">account</h1>

## Places an order for a contract.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/place_order',
  params: {
  'contract_symbol' => 'undefined',
'size' => 'number'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/place_order', params={
  'contract_symbol': undefined,  'size': '0'
}, headers = headers)

print r.json()

```

`POST /account/place_order`

<h3 id="places-an-order-for-a-contract.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|contract_symbol|query|undefined|true|Contract unique symbol|
|size|query|number|true|contract size|
|type|query|string|false|The order type, default: `"limit"`|
|price|query|number|false|price|
|time_in_force|query|string|false|Applies to limit order. Defaults to gtc(good till cancelled)|
|post_only|query|boolean|false|<p>If true, the order is considered post-only. If the new price would cause the order to be filled immediately (as taker), the price will be changed to be just below the bid.</p> <p>Only valid in combination with time_in_force=`"good_til_cancelled"`</p>|
|reduce_only|query|boolean|false|If `true`, the order is considered reduce-only which is intended to only reduce a current position|
|stop_price|query|undefined|false|Stop price, required for stop limit orders (Only for stop orders)|
|trigger|query|string|false|Defines trigger type, required for `"stop_limit"` order type|

#### Enumerated Values

|Parameter|Value|
|---|---|
|type|limit|
|type|stop_limit|
|type|market|
|type|stop_market|
|time_in_force|good_til_cancelled|
|time_in_force|fill_or_kill|
|time_in_force|immediate_or_cancel|
|trigger|index_price|
|trigger|mark_price|
|trigger|last_price|

> Example responses

```json
{}
```

<h3 id="places-an-order-for-a-contract.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="places-an-order-for-a-contract.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Cancel all orders by the param

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/cancel_all_open_orders',
  params: {
  'asset' => 'undefined',
'contract_symbol' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/cancel_all_open_orders', params={
  'asset': undefined,  'contract_symbol': undefined
}, headers = headers)

print r.json()

```

`GET /account/cancel_all_open_orders`

<h3 id="cancel-all-orders-by-the-param-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|
|contract_symbol|query|undefined|true|Contract unique symbol|
|contract_type|query|string|false|Contract types|

#### Enumerated Values

|Parameter|Value|
|---|---|
|contract_type|future|
|contract_type|spread|

> Example responses

```json
{}
```

<h3 id="cancel-all-orders-by-the-param-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="cancel-all-orders-by-the-param-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieve user positions.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_positions',
  params: {
  'asset' => 'undefined',
'contract_symbol' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_positions', params={
  'asset': undefined,  'contract_symbol': undefined
}, headers = headers)

print r.json()

```

`GET /account/get_positions`

<h3 id="retrieve-user-positions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|
|contract_symbol|query|undefined|true|Contract unique symbol|

> Example responses

> Returns open positions

```json
{}
```

<h3 id="retrieve-user-positions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Returns open positions|None|

<h3 id="retrieve-user-positions.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Close an open position

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/close_position',
  params: {
  'order_id' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/close_position', params={
  'order_id': undefined
}, headers = headers)

print r.json()

```

`GET /account/close_position`

<h3 id="close-an-open-position-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_id|query|undefined|true|The order id|
|price|query|undefined|false|Optional price for limit order.|

> Example responses

```json
{}
```

<h3 id="close-an-open-position-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="close-an-open-position-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

<h1 id="alpha5-documentation-trading">trading</h1>

## Retrieves list of user's open orders.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_open_orders',
  params: {
  'asset' => 'undefined',
'contract_symbol' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_open_orders', params={
  'asset': undefined,  'contract_symbol': 'BTC-PERPETUAL'
}, headers = headers)

print r.json()

```

`GET /account/get_open_orders`

<h3 id="retrieves-list-of-user's-open-orders.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|
|contract_symbol|query|string|true|Contract unique symbol|
|contract_type|query|string|false|Contract types|
|type|query|string|false|Order type, default - `all`|

#### Enumerated Values

|Parameter|Value|
|---|---|
|contract_type|future|
|contract_type|spread|
|type|all|
|type|limit|
|type|stop_all|
|type|stop_limit|
|type|stop_market|

> Example responses

```json
{}
```

<h3 id="retrieves-list-of-user's-open-orders.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-list-of-user's-open-orders.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Cancel an order, specified by order id

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/cancel_order',
  params: {
  'order_id' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/cancel_order', params={
  'order_id': undefined
}, headers = headers)

print r.json()

```

`GET /account/cancel_order`

<h3 id="cancel-an-order,-specified-by-order-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_id|query|undefined|true|The order id|

> Example responses

```json
{}
```

<h3 id="cancel-an-order,-specified-by-order-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="cancel-an-order,-specified-by-order-id-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieve the list of user trades. Pagination supported.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_user_trades',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_user_trades', params={

}, headers = headers)

print r.json()

```

`GET /account/get_user_trades`

<h3 id="retrieve-the-list-of-user-trades.-pagination-supported.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_id|query|undefined|false|The order id|

> Example responses

```json
{}
```

<h3 id="retrieve-the-list-of-user-trades.-pagination-supported.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieve-the-list-of-user-trades.-pagination-supported.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Change price, size and/or other properties of an order.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/edit_order',
  params: {
  'order_id' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/edit_order', params={
  'order_id': undefined
}, headers = headers)

print r.json()

```

`GET /account/edit_order`

<h3 id="change-price,-size-and/or-other-properties-of-an-order.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|order_id|query|undefined|true|The order id|
|size|query|undefined|false|It represents the requested order size. For perpetual and futures the amount is in USD units, for options it is amount of corresponding cryptocurrency contracts, e.g., BTC or ETH|
|price|query|undefined|false|The order price in base currency.|

> Example responses

```json
{}
```

<h3 id="change-price,-size-and/or-other-properties-of-an-order.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="change-price,-size-and/or-other-properties-of-an-order.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieves history of orders that have been partially or fully filled.

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_order_history',
  params: {
  'asset' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_order_history', params={
  'asset': undefined
}, headers = headers)

print r.json()

```

`GET /account/get_order_history`

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|
|contract_type|query|string|false|Contract types|

#### Enumerated Values

|Parameter|Value|
|---|---|
|contract_type|future|
|contract_type|spread|

> Example responses

```json
{}
```

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-history-of-orders-that-have-been-partially-or-fully-filled.-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

<h1 id="alpha5-documentation-wallet">wallet</h1>

## Retrieves deposit addresses

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_deposit_address',
  params: {
  'asset' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_deposit_address', params={
  'asset': undefined
}, headers = headers)

print r.json()

```

`GET /account/get_deposit_address`

<h3 id="retrieves-deposit-addresses-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|

> Example responses

<h3 id="retrieves-deposit-addresses-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-deposit-addresses-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieve the latest users deposits

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/get_deposits',
  params: {
  'asset' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/get_deposits', params={
  'asset': undefined
}, headers = headers)

print r.json()

```

`GET /account/get_deposits`

<h3 id="retrieve-the-latest-users-deposits-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|true|The asset symbol|

> Example responses

```json
{}
```

<h3 id="retrieve-the-latest-users-deposits-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieve-the-latest-users-deposits-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieves wallets and balances

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/account/wallet_balances',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/account/wallet_balances', params={

}, headers = headers)

print r.json()

```

`GET /account/wallet_balances`

<h3 id="retrieves-wallets-and-balances-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|false|The asset symbol|

> Example responses

```json
{}
```

<h3 id="retrieves-wallets-and-balances-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieves-wallets-and-balances-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Retrieve the latest users withdrawals

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://testing-api.alpha5.com/v1/acccount/get_withdrawals',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://testing-api.alpha5.com/v1/acccount/get_withdrawals', params={

}, headers = headers)

print r.json()

```

`GET /acccount/get_withdrawals`

<h3 id="retrieve-the-latest-users-withdrawals-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|false|The asset symbol|

> Example responses

```json
{}
```

<h3 id="retrieve-the-latest-users-withdrawals-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="retrieve-the-latest-users-withdrawals-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

## Creates a new withdrawal request

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://testing-api.alpha5.com/v1/account/withdraw',
  params: {
  'address' => 'undefined',
'amount' => 'undefined'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://testing-api.alpha5.com/v1/account/withdraw', params={
  'address': undefined,  'amount': undefined
}, headers = headers)

print r.json()

```

`POST /account/withdraw`

<h3 id="creates-a-new-withdrawal-request-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|asset|query|undefined|false|The asset symbol|
|address|query|undefined|true|Address in currency format, it must be in address book|
|amount|query|undefined|true|Amount of funds to be withdrawn|

> Example responses

```json
{}
```

<h3 id="creates-a-new-withdrawal-request-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

<h3 id="creates-a-new-withdrawal-request-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>

# Schemas

<h2 id="tocSasset">Asset</h2>

<a id="schemaasset"></a>

```json
{
  "symbol": "ETH",
  "name": "Ethereum",
  "precision": 8
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|symbol|string|false|none|Unique asset identifier|
|name|string|false|none|none|
|precision|number|false|none|none|

