# TRADE SERVICE #  

IBANFIRST provides a deliverable FX facility and deliverable FX liquidity via the IBANFIRST-REST API.
As a partner, you will be able to create quote and trade on the real-time forex market on behalf of your client (our counterparty).

The IBANFIRST-rest API supports online trading for the following contracts: TOD (Same-day), TOM (next-day), SPOT (T+2). 

## Route ##

| Route | Description |
|-------|-------------|
| [`POST /quotes/`](#post_quotes) | Create Quote (beta) |
| [`POST /trades/`](#post_trades) | Submit Trade (beta) |
| [`POST /trades/onQuote/-{idQuote}/`](#post_tradesOnQuote) | Submit Trade on Quote (beta) |


## Details ##

### <a id="post_quotes"></a> Create Quote (beta) ###

```
Method: POST
URL: /quotes/
```

The Create Quote service is a read-only service permitting to ask for a real-time rate.   

**Parameters:**

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| currencyPair | [CurrencyPair](../conventions/formattingConventions.md#type_currencypair) | Required | The currency cross of the quote you want to create. `EURUSD` |
| side | String | Required | The side is linked to the amount. With `S`, you are creating a quote in order to sell the indicated amount. With `B` to buy, you are creating a quote in order to buy the indicated amount. |
| amount | [Amount Object](../objects/objects.md#amount_object) | Required | [Amount Object](../objects/objects.md#amount_object) representing the amount to trade. |
| deliveryDate | [Date](../conventions/formattingConventions.md#type_date) | optional | Initial delivery date of the quote. `YYYY-MM-DD` |

**Example: Create Quote (1) - I want to buy USD (my principal is in USD)**
```js
POST /quotes/
{
    "currencyPair": "EURUSD",
    "side": "B",
    "amount": {
      "value": "1000",
      "currency": "USD"
    },
}

```

**Example: Create Quote (2) - I want to sell EUR (my principal is in EUR)**
```js
POST /quotes/
{
    "currencyPair": "EURUSD",
    "side": "S",
    "amount": {
      "value": "1000",
      "currency": "EUR"
    },
}

```

**Returns:**

| Field | Type | Description |
|-------|------|-------------|
| quote | [Quote object](../objects/objects.md#quote_object) | A [Quote object](../objects/objects.md#quote_object) representing the quote requested. |

**Example: Return Create Quote (1) - I want to know what's the rate to buy USD (my principal is in USD)**
```js
{
  "id": "Aa5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "903.34", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1000", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```

**Example: Return Create Quote (2) - I want to know what's the rate to sell EUR (my principal is in EUR)**
```js
{
  "id": "Ba5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "1000", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1107", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```
<hr />


### <a id="post_trades"></a> Execute Trade ###

```
Method: POST
URL: /trades/
```
This service allows you to execute trade on the real-time Forex market. 

**Parameters:**

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| currencyPair | [CurrencyPair](../conventions/formattingConventions.md#type_currencypair) | Required | A six-digit code representing the cross of currency requested. |
| side | String | Required | Action related to the nominal amount. To be bought or sold on the market, `S` to sell and `B` to buy. |
| amount | [Amount Object](../objects/objects.md#amount_object) | Required | Principal amount associated to the trade. |
| deliveryDate | [Date](../conventions/formattingConventions.md#type_date) | Optional | Execution date of your trade. |

**Example: Execute Trade (1) - I want to buy USD (my principal is in USD)**
```js
POST /trades/
{
    "currencyPair": "EURUSD",
    "side": "B",
    "amount": {
      "value": "1000",
      "currency": "USD"
    },
}

```

**Example: Execute Trade (2) - I want to sell EUR (my principal is in EUR)**
```js
POST /trades/
{
    "currencyPair": "EURUSD",
    "side": "S",
    "amount": {
      "value": "1000",
      "currency": "EUR"
    },
}

```
**Returns:**

| Field | Type | Description |
|-------|------|-------------|
| trade | [Trade object](../objects/objects.md#trade_object) | A [Trade object](../objects/objects.md#trade_object) representing the trade requested. |

**Example: Return Execute Trade (1) - I want to buy USD (my principal is in USD)**
```js
{
  "id": "Ca5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "903.34", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1000", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```

**Example: Return Execute Trade (2) - I want to sell EUR (my principal is in EUR)**
```js
{
  "id": "Da5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "1000", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1107", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```
<hr />

### <a id="post_trades"></a> Execute Trade on Quote ###

```
Method: POST
URL: /trades/onQuote/-{idQuote}/
```
This service allows you to execute a trade on the real-time Forex market based on a previous created quote.

**Parameters:**

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| id | [id quote](../conventions/formattingConventions.md#type_currencypair) | Required | A seven-digit code representing the id of the previous created Quote. |

**Example: Execute Trade on Quote (1)**
```js
POST /trades/onQuote/-Aa5Dv6E/
```

**Example: Execute Trade on Quote (2)**
```js
POST /trades/onQuote/-Ba5Dv6E/

```
**Returns:**

| Field | Type | Description |
|-------|------|-------------|
| trade | [Trade object](../objects/objects.md#trade_object) | A [Trade object](../objects/objects.md#trade_object) representing the trade requested. |

**Example: Return Execute Trade on Quote (1)**
```js
{
  "id": "Ea5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "903.34", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1000", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```

**Example: Return Execute Trade on Quote (2)**
```js
{
  "id": "Fa5Dv6E",
  "appliedRate": "1.1070",
  "currencyPair": "EURUSD",
  "sourceAmount": { 
    "value": "1000", 
    "currency": "EUR" 
  },
  "deliveredAmount": { 
    "value": "1107", 
    "currency": "USD" 
  },
  "createdDate": "2016-01-01 00:00:00", 
  "deliveryDate": "2016-01-01",
}
```
<hr />




