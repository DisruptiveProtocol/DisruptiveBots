<a name="top"></a>
# Bot API v1.0.0

Bot API Documentation

# Table of contents

- [Bot](#Bot)
  - [Create Bot](#Create-Bot)
  - [Generate payment QR](#Generate-payment-QR)
  - [Get active coins](#Get-active-coins)
  - [Get active nanobots number](#Get-active-nanobots-number)
  - [Get all](#Get-all)
  - [Get bot best sell](#Get-bot-best-sell)
  - [Get completed operations](#Get-completed-operations)
  - [Get minimum budget for bot creations](#Get-minimum-budget-for-bot-creations)
  - [Get open trades](#Get-open-trades)
  - [Get profits](#Get-profits)
  - [Get profits by coins](#Get-profits-by-coins)
  - [Get symbol to buy](#Get-symbol-to-buy)
  - [Get transaction amounts](#Get-transaction-amounts)
  - [Get user active bots](#Get-user-active-bots)
  - [Get user origin bots](#Get-user-origin-bots)
  - [Stop](#Stop)
  - [Stop bots by origin hash](#Stop-bots-by-origin-hash)
  - [Stop bots by user](#Stop-bots-by-user)
- [Explorer](#Explorer)
  - [Get all bots](#Get-all-bots)
  - [Get average profits by periods](#Get-average-profits-by-periods)
  - [Get bots by status](#Get-bots-by-status)
  - [Get profits by quotes](#Get-profits-by-quotes)
  - [Get system requests](#Get-system-requests)
  - [Get total inveted budget](#Get-total-inveted-budget)
  - [Get total users](#Get-total-users)
  - [Get transactions balance by status](#Get-transactions-balance-by-status)
  - [Get user earnings by bot](#Get-user-earnings-by-bot)
- [Orders](#Orders)
  - [Get all user orders](#Get-all-user-orders)
  - [Get today orders](#Get-today-orders)
  - [Get user orders](#Get-user-orders)
- [Summaries](#Summaries)
  - [Get summaries](#Get-summaries)
  - [Get summary orders](#Get-summary-orders)
  - [Stop summary](#Stop-summary)

___


# <a name='Bot'></a> Bot

## <a name='Create-Bot'></a> Create Bot
[Back to top](#top)

<p>Create bot</p>

```
POST /bots
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| name | `String` | <p>bot name</p> |
| nameBotPlan | `String` | <p>Your plan</p> |
| budget | `Number` | <p>Budget</p> |
| user | `String` | <p>Username</p> |
| exchangeId | `String` | <p>Exchange ID</p> |
| quoteAsset | `String` | <p>Quote asset</p> |
| trailing | `Boolean` | <p>Activates trailing</p> |
| selectedTrend | `String` | <p>Selected trends</p> |
| selectedRisk | `String` | <p>Selected risk</p> |
| selectedStrategy | `String` | <p>Selected strategy</p> |
| getSymbolsBy | `String` | <p>Get symbols mode</p> |
| trailingShield | `String` | <p>Activates Trailing Shield</p> |
| invalidSymbols | `String[]` | <p>Invalid symbols for this bot</p> |
| baseAssets | `String[]` | <p>List of base assets</p> |
| budgetPercents | `Object` | **optional** <p>Budget assigment per order</p> |
| budgetPercents.B1 | `String` | <p>Budget percentage in buy order 1</p> |
| budgetPercents.B2 | `Number` | <p>Budget percentage in buy order 2</p> |
| budgetPercents.B3 | `Number` | <p>Budget percentage in buy order 3</p> |
| budgetPercents.B4 | `Number` | <p>Budget percentage in buy order 4</p> |
| budgetPercents.B5 | `Number` | <p>Budget percentage in buy order 5</p> |
| budgetPercents.B6 | `Number` | <p>Budget percentage in buy order 6</p> |
| purchasePercents | `Object` | <p>Buy orders percentages</p> |
| purchasePercents.O1 | `Number` | <p>Buy order 1 percentage</p> |
| purchasePercents.O2 | `Number` | <p>Buy order 2 percentage</p> |
| purchasePercents.O3 | `Number` | <p>Buy order 3 percentage</p> |
| purchasePercents.O4 | `Number` | <p>Buy order 4 percentage</p> |
| purchasePercents.O5 | `Number` | <p>Buy order 5 percentage</p> |
| purchasePercents.O6 | `Number` | <p>Buy order 6 percentage</p> |
| risePricePercents | `Object` | <p>Sell order percentages</p> |
| risePricePercents.S1 | `Number` | <p>Sell order 1 percentage</p> |
| risePricePercents.S2 | `Number` | <p>Sell order 2 percentage</p> |
| risePricePercents.S3 | `Number` | <p>Sell order 3 percentage</p> |
| risePricePercents.S4 | `Number` | <p>Sell order 4 percentage</p> |
| risePricePercents.S5 | `Number` | <p>Sell order 5 percentage</p> |
| risePricePercents.S6 | `Number` | <p>Sell order 6 percentage</p> |
| typeRisk | `String` | <p>Risk type</p> |
| investEarnings | `String` | <p>Invest earnings</p> |
| trailingShield | `String` | <p>Trailing shield</p> |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message | `String` | <p>Message</p> |
| nameBotPlan | `String` | <p>Bot plan name</p> |
| budget | `String` | <p>Bot budget</p> |
| hash | `String` | <p>Hash bot</p> |
| user | `String` | <p>Bot user</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Generate-payment-QR'></a> Generate payment QR
[Back to top](#top)

<p>Generate payment QR</p>

```
POST /bots/generatePaymentQr
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| numUsers | `Number` |  |
| budgetAvg | `Number` |  |
| botsAvg | `Number` |  |
| licenseTime | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| address | `String` | <p>Wallet address</p> |
| taken | `Boolean` |  |
| usedBy | `String` |  |
| expectedPayment | `Number` |  |
| expectedDISR | `Number` |  |
| incomplete | `Boolean` |  |
| status | `String` |  |
| paid | `Number` |  |
| payDayLimit | `Number` |  |
| assignedAt | `String` |  |
| createdAt | `Number` |  |
| updatedAt | `Number` |  |
| lastCheck | `Number` |  |
| requestedQty | `Number` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-active-coins'></a> Get active coins
[Back to top](#top)

<p>Get active coins</p>

```
GET /bots/getMyCoins
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| page | `Number` |  |
| limit | `Number` |  |
| sortBy | `String` |  |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
[
   "BTC",
   "ETH"
]
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-active-nanobots-number'></a> Get active nanobots number
[Back to top](#top)

<p>Get active nanobots number</p>

```
POST /bots/nanobotsByPeriod
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| startDate | `Number` |  |
| endDate | `Number` |  |
| originHash | `String` |  |
| userId | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| activeNanobots | `Number` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-all'></a> Get all
[Back to top](#top)

<p>Get all</p>

```
GET /bots
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| performance | `Boolean` |  |
| selectBy | `String` |  |
| searchBy | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Bot ID</p> |
| name | `String` | <p>Bot name</p> |
| nameBotPlan | `String` | <p>Plan name</p> |
| budgetHash | `String` | <p>Bot hash</p> |
| parentBot | `String` | <p>Parent bot ID</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| parentHash | `String` | <p>Parent bot hash</p> |
| parentOrder | `String` | <p>Order that originates this bot</p> |
| status | `String` | <p>Bot Status</p> |
| user | `String` | <p>Bot user</p> |
| budget | `Number` | <p>Bot budget</p> |
| extraBudget | `Number` |  |
| unusedBudget | `Number` |  |
| unusedBudgetUsed | `Boolean` |  |
| exchange | `String` |  |
| exchangeAuth | `String` |  |
| expireAt | `Number` | <p>Expiration timestamp</p> |
| profit | `Number` | <p>Bot profits</p> |
| profitPercent | `Number` | <p>Bot profit percentage</p> |
| profitGeneral | `Number` | <p>Bot and nanobots profits</p> |
| profitGeneralPercent | `Number` | <p>Bot and nanobots profits percentage</p> |
| stopLoss | `Number` | <p>Stoploss price</p> |
| purchasePercents | `Object` | <p>Buy orders percentages</p> |
| purchasePercents.O1 | `Number` | <p>Buy order 1 percentage</p> |
| purchasePercents.O2 | `Number` | <p>Buy order 2 percentage</p> |
| purchasePercents.O3 | `Number` | <p>Buy order 3 percentage</p> |
| purchasePercents.O4 | `Number` | <p>Buy order 4 percentage</p> |
| purchasePercents.O5 | `Number` | <p>Buy order 5 percentage</p> |
| purchasePercents.O6 | `Number` | <p>Buy order 6 percentage</p> |
| risePricePercents | `Object` | <p>Sell order percentages</p> |
| risePricePercents.S1 | `Number` | <p>Sell order 1 percentage</p> |
| risePricePercents.S2 | `Number` | <p>Sell order 2 percentage</p> |
| risePricePercents.S3 | `Number` | <p>Sell order 3 percentage</p> |
| risePricePercents.S4 | `Number` | <p>Sell order 4 percentage</p> |
| risePricePercents.S5 | `Number` | <p>Sell order 5 percentage</p> |
| risePricePercents.S6 | `Number` | <p>Sell order 6 percentage</p> |
| budgetPercents | `Object` | <p>Budget assigment per order</p> |
| budgetPercents.B1 | `Number` | <p>Budget percentage in buy order 1</p> |
| budgetPercents.B2 | `Number` | <p>Budget percentage in buy order 2</p> |
| budgetPercents.B3 | `Number` | <p>Budget percentage in buy order 3</p> |
| budgetPercents.B4 | `Number` | <p>Budget percentage in buy order 4</p> |
| budgetPercents.B5 | `Number` | <p>Budget percentage in buy order 5</p> |
| budgetPercents.B6 | `Number` | <p>Budget percentage in buy order 6</p> |
| typeRisk | `String` | <p>Risk type</p> |
| baseAssets | `Object[]` | <p>Base assets bought.</p> |
| getSymbolsBy | `String` | <p>Symbols selection type</p> |
| remainderBudget | `Number` | <p>Reaminder budget</p> |
| remainderUsed | `Boolean` | <p>Is remainder budget used?</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| investEarnings | `Boolean` | <p>Invest earnings?</p> |
| needKeys | `Boolean` | <p>This bot exchange keys needs to be updated?</p> |
| invalidSymbols | `String[]` |  |
| useUnusedBudget | `Boolean` |  |
| selectedRisk | `String` |  |
| selectedTrend | `String` |  |
| selectedStrategy | `String` |  |
| tradingShield | `Boolean` |  |
| stopBuyBack | `Boolean` |  |
| smartTrend | `Boolean` |  |
| finishedReadon | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-bot-best-sell'></a> Get bot best sell
[Back to top](#top)

<p>Get bot best sell</p>

```
GET /bots/getBestSell
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| botId | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Summary ID</p> |
| user | `String` | <p>Summary user</p> |
| token | `String` | <p>Summary token asset</p> |
| quote | `String` | <p>Summary quote asset</p> |
| symbol | `String` | <p>Summary symbol</p> |
| budgetPercentage | `Number` | <p>Bot budget percentage in this summary</p> |
| purchase | `Number` | <p>Budget executed</p> |
| sale | `Number` | <p>Summary sold amount</p> |
| profit | `Number` | <p>Summary profits</p> |
| profitPercent | `Number` | <p>Summary profits percent</p> |
| hash | `String` | <p>Summary hash</p> |
| plan | `String` | <p>Summary plan</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| budget | `Number` | <p>Budget invested</p> |
| status | `String` | <p>Summary status</p> |
| trailing | `Boolean` | <p>Trailing</p> |
| needKeys | `Boolean` | <p>Invalid current summary keys</p> |
| finishedAt | `Number` | <p>Finished timestamp</p> |
| profitPercentBot | `Number` | <p>Profits percent compared to bot</p> |
| accounted | `Boolean` |  |
| hasSellMarket | `Boolean` | <p>Has a sell market completed</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| stop | `Boolean` | <p>Summary stopped by user</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-completed-operations'></a> Get completed operations
[Back to top](#top)

<p>Get completed operations endpoint</p>

```
GET /bots/getCompletedOperations
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| originHash | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| completedOperations | `Number` | <p>Completed operations</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
{
   "completedOperations": 10
}
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-minimum-budget-for-bot-creations'></a> Get minimum budget for bot creations
[Back to top](#top)

<p>Get bot historical earnings</p>

```
GET /bots/get-origin-bot-historical-earnings
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| originHash | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| originHash | `String` |  |
| date | `Number` |  |
| initialTimestamp | `Number` |  |
| endingTimestamp | `Number` |  |
| profitPercentage | `Number` |  |
| profit | `Number` |  |
| createdAt | `Number` |  |
| updatedAt | `Number` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-open-trades'></a> Get open trades
[Back to top](#top)

<p>Get open trades endpoint</p>

```
GET /bots/getOpenTrades
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| originHash | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| openTrades | `String` |  |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
{
   "openTrades": 10
}
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-profits'></a> Get profits
[Back to top](#top)

<p>Get profits</p>

```
GET /bots/getProfits
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| name | `String` |  |
| quote | `String` |  |
| hash | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| lifeimeEarnings | `Number` |  |
| earnedPercent | `Number` |  |
| budgetOrigin | `Number` |  |
| quote | `String` |  |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
{
   "lifetimeEarnings": 500.00,
   "earnedPercent": 10,
   "budgetOrigin": 5000,
   "quote": "USDT"
}
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-profits-by-coins'></a> Get profits by coins
[Back to top](#top)

<p>Get profits by coins</p>

```
GET /bots/getProfitsByCoins
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| botId | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
| nanobots | `Boolean` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Token</p> |
| sum | `String` | <p>Total profits</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-symbol-to-buy'></a> Get symbol to buy
[Back to top](#top)

<p>Get symbol to buy endpoint</p>

```
POST /bots/symbols-to-buy
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| exchange | `String` |  |
| budget | `Number` |  |
| quoteAsset | `String` |  |
| getSymbolsBy | `String` |  |
| filterSymbolsRunning | `Boolean` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| numSymbols | `Number` | <p>Symbols to buy quantity</p> |
| symbols | `String[]` | <p>Symbols to buy list</p> |
| baseAssets | `Object[]` | <p>Tokens to buy</p> |
| baseAssets.base | `String` | <p>Token</p> |
| baseAssets.percentBudget | `Number` | <p>Percentage to buy</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-transaction-amounts'></a> Get transaction amounts
[Back to top](#top)

<p>Get transaction amounts</p>

```
GET /bots/getTransactionAmounts
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| originHash | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Summary ID</p> |
| user | `String` | <p>Summary user</p> |
| token | `String` | <p>Summary token asset</p> |
| quote | `String` | <p>Summary quote asset</p> |
| symbol | `String` | <p>Summary symbol</p> |
| budgetPercentage | `Number` | <p>Bot budget percentage in this summary</p> |
| purchase | `Number` | <p>Budget executed</p> |
| sale | `Number` | <p>Summary sold amount</p> |
| profit | `Number` | <p>Summary profits</p> |
| profitPercent | `Number` | <p>Summary profits percent</p> |
| hash | `String` | <p>Summary hash</p> |
| plan | `String` | <p>Summary plan</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| budget | `Number` | <p>Budget invested</p> |
| status | `String` | <p>Summary status</p> |
| trailing | `Boolean` | <p>Trailing</p> |
| needKeys | `Boolean` | <p>Invalid current summary keys</p> |
| finishedAt | `Number` | <p>Finished timestamp</p> |
| profitPercentBot | `Number` | <p>Profits percent compared to bot</p> |
| accounted | `Boolean` |  |
| hasSellMarket | `Boolean` | <p>Has a sell market completed</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| stop | `Boolean` | <p>Summary stopped by user</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-user-active-bots'></a> Get user active bots
[Back to top](#top)

<p>Get user active bots</p>

```
GET /bots/getActiveBots/:user
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Bot ID</p> |
| name | `String` | <p>Bot name</p> |
| nameBotPlan | `String` | <p>Plan name</p> |
| budgetHash | `String` | <p>Bot hash</p> |
| parentBot | `String` | <p>Parent bot ID</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| parentHash | `String` | <p>Parent bot hash</p> |
| parentOrder | `String` | <p>Order that originates this bot</p> |
| status | `String` | <p>Bot Status</p> |
| user | `String` | <p>Bot user</p> |
| budget | `Number` | <p>Bot budget</p> |
| extraBudget | `Number` |  |
| unusedBudget | `Number` |  |
| unusedBudgetUsed | `Boolean` |  |
| exchange | `String` |  |
| exchangeAuth | `String` |  |
| expireAt | `Number` | <p>Expiration timestamp</p> |
| profit | `Number` | <p>Bot profits</p> |
| profitPercent | `Number` | <p>Bot profit percentage</p> |
| profitGeneral | `Number` | <p>Bot and nanobots profits</p> |
| profitGeneralPercent | `Number` | <p>Bot and nanobots profits percentage</p> |
| stopLoss | `Number` | <p>Stoploss price</p> |
| purchasePercents | `Object` | <p>Buy orders percentages</p> |
| purchasePercents.O1 | `Number` | <p>Buy order 1 percentage</p> |
| purchasePercents.O2 | `Number` | <p>Buy order 2 percentage</p> |
| purchasePercents.O3 | `Number` | <p>Buy order 3 percentage</p> |
| purchasePercents.O4 | `Number` | <p>Buy order 4 percentage</p> |
| purchasePercents.O5 | `Number` | <p>Buy order 5 percentage</p> |
| purchasePercents.O6 | `Number` | <p>Buy order 6 percentage</p> |
| risePricePercents | `Object` | <p>Sell order percentages</p> |
| risePricePercents.S1 | `Number` | <p>Sell order 1 percentage</p> |
| risePricePercents.S2 | `Number` | <p>Sell order 2 percentage</p> |
| risePricePercents.S3 | `Number` | <p>Sell order 3 percentage</p> |
| risePricePercents.S4 | `Number` | <p>Sell order 4 percentage</p> |
| risePricePercents.S5 | `Number` | <p>Sell order 5 percentage</p> |
| risePricePercents.S6 | `Number` | <p>Sell order 6 percentage</p> |
| budgetPercents | `Object` | <p>Budget assigment per order</p> |
| budgetPercents.B1 | `Number` | <p>Budget percentage in buy order 1</p> |
| budgetPercents.B2 | `Number` | <p>Budget percentage in buy order 2</p> |
| budgetPercents.B3 | `Number` | <p>Budget percentage in buy order 3</p> |
| budgetPercents.B4 | `Number` | <p>Budget percentage in buy order 4</p> |
| budgetPercents.B5 | `Number` | <p>Budget percentage in buy order 5</p> |
| budgetPercents.B6 | `Number` | <p>Budget percentage in buy order 6</p> |
| typeRisk | `String` | <p>Risk type</p> |
| baseAssets | `Object[]` | <p>Base assets bought.</p> |
| getSymbolsBy | `String` | <p>Symbols selection type</p> |
| remainderBudget | `Number` | <p>Reaminder budget</p> |
| remainderUsed | `Boolean` | <p>Is remainder budget used?</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| investEarnings | `Boolean` | <p>Invest earnings?</p> |
| needKeys | `Boolean` | <p>This bot exchange keys needs to be updated?</p> |
| invalidSymbols | `String[]` |  |
| useUnusedBudget | `Boolean` |  |
| selectedRisk | `String` |  |
| selectedTrend | `String` |  |
| selectedStrategy | `String` |  |
| tradingShield | `Boolean` |  |
| stopBuyBack | `Boolean` |  |
| smartTrend | `Boolean` |  |
| finishedReadon | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-user-origin-bots'></a> Get user origin bots
[Back to top](#top)

<p>Get user origin bots endpoint</p>

```
GET /bots/origins
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Bot ID</p> |
| name | `String` | <p>Bot name</p> |
| nameBotPlan | `String` | <p>Plan name</p> |
| budgetHash | `String` | <p>Bot hash</p> |
| parentBot | `String` | <p>Parent bot ID</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| parentHash | `String` | <p>Parent bot hash</p> |
| parentOrder | `String` | <p>Order that originates this bot</p> |
| status | `String` | <p>Bot Status</p> |
| user | `String` | <p>Bot user</p> |
| budget | `Number` | <p>Bot budget</p> |
| extraBudget | `Number` |  |
| unusedBudget | `Number` |  |
| unusedBudgetUsed | `Boolean` |  |
| exchange | `String` |  |
| exchangeAuth | `String` |  |
| expireAt | `Number` | <p>Expiration timestamp</p> |
| profit | `Number` | <p>Bot profits</p> |
| profitPercent | `Number` | <p>Bot profit percentage</p> |
| profitGeneral | `Number` | <p>Bot and nanobots profits</p> |
| profitGeneralPercent | `Number` | <p>Bot and nanobots profits percentage</p> |
| stopLoss | `Number` | <p>Stoploss price</p> |
| purchasePercents | `Object` | <p>Buy orders percentages</p> |
| purchasePercents.O1 | `Number` | <p>Buy order 1 percentage</p> |
| purchasePercents.O2 | `Number` | <p>Buy order 2 percentage</p> |
| purchasePercents.O3 | `Number` | <p>Buy order 3 percentage</p> |
| purchasePercents.O4 | `Number` | <p>Buy order 4 percentage</p> |
| purchasePercents.O5 | `Number` | <p>Buy order 5 percentage</p> |
| purchasePercents.O6 | `Number` | <p>Buy order 6 percentage</p> |
| risePricePercents | `Object` | <p>Sell order percentages</p> |
| risePricePercents.S1 | `Number` | <p>Sell order 1 percentage</p> |
| risePricePercents.S2 | `Number` | <p>Sell order 2 percentage</p> |
| risePricePercents.S3 | `Number` | <p>Sell order 3 percentage</p> |
| risePricePercents.S4 | `Number` | <p>Sell order 4 percentage</p> |
| risePricePercents.S5 | `Number` | <p>Sell order 5 percentage</p> |
| risePricePercents.S6 | `Number` | <p>Sell order 6 percentage</p> |
| budgetPercents | `Object` | <p>Budget assigment per order</p> |
| budgetPercents.B1 | `Number` | <p>Budget percentage in buy order 1</p> |
| budgetPercents.B2 | `Number` | <p>Budget percentage in buy order 2</p> |
| budgetPercents.B3 | `Number` | <p>Budget percentage in buy order 3</p> |
| budgetPercents.B4 | `Number` | <p>Budget percentage in buy order 4</p> |
| budgetPercents.B5 | `Number` | <p>Budget percentage in buy order 5</p> |
| budgetPercents.B6 | `Number` | <p>Budget percentage in buy order 6</p> |
| typeRisk | `String` | <p>Risk type</p> |
| baseAssets | `Object[]` | <p>Base assets bought.</p> |
| getSymbolsBy | `String` | <p>Symbols selection type</p> |
| remainderBudget | `Number` | <p>Reaminder budget</p> |
| remainderUsed | `Boolean` | <p>Is remainder budget used?</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| investEarnings | `Boolean` | <p>Invest earnings?</p> |
| needKeys | `Boolean` | <p>This bot exchange keys needs to be updated?</p> |
| invalidSymbols | `String[]` |  |
| useUnusedBudget | `Boolean` |  |
| selectedRisk | `String` |  |
| selectedTrend | `String` |  |
| selectedStrategy | `String` |  |
| tradingShield | `Boolean` |  |
| stopBuyBack | `Boolean` |  |
| smartTrend | `Boolean` |  |
| finishedReadon | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Stop'></a> Stop
[Back to top](#top)

<p>Stop bot endpoint</p>

```
POST /bots/stopBot
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| botId | `String` | <p>Bot ID</p> |
| cancelOption | `String` | <p>Cancel option: [<code>MARKET</code>, <code>NONE</code>, <code>SMART</code>]</p>_Default value: None_<br> |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` | <p>Bot ID</p> |
| name | `String` | <p>Bot name</p> |
| nameBotPlan | `String` | <p>Plan name</p> |
| budgetHash | `String` | <p>Bot hash</p> |
| parentBot | `String` | <p>Parent bot ID</p> |
| originHash | `String` | <p>Origin bot hash</p> |
| parentHash | `String` | <p>Parent bot hash</p> |
| parentOrder | `String` | <p>Order that originates this bot</p> |
| status | `String` | <p>Bot Status</p> |
| user | `String` | <p>Bot user</p> |
| budget | `Number` | <p>Bot budget</p> |
| extraBudget | `Number` |  |
| unusedBudget | `Number` |  |
| unusedBudgetUsed | `Boolean` |  |
| exchange | `String` |  |
| exchangeAuth | `String` |  |
| expireAt | `Number` | <p>Expiration timestamp</p> |
| profit | `Number` | <p>Bot profits</p> |
| profitPercent | `Number` | <p>Bot profit percentage</p> |
| profitGeneral | `Number` | <p>Bot and nanobots profits</p> |
| profitGeneralPercent | `Number` | <p>Bot and nanobots profits percentage</p> |
| stopLoss | `Number` | <p>Stoploss price</p> |
| purchasePercents | `Object` | <p>Buy orders percentages</p> |
| purchasePercents.O1 | `Number` | <p>Buy order 1 percentage</p> |
| purchasePercents.O2 | `Number` | <p>Buy order 2 percentage</p> |
| purchasePercents.O3 | `Number` | <p>Buy order 3 percentage</p> |
| purchasePercents.O4 | `Number` | <p>Buy order 4 percentage</p> |
| purchasePercents.O5 | `Number` | <p>Buy order 5 percentage</p> |
| purchasePercents.O6 | `Number` | <p>Buy order 6 percentage</p> |
| risePricePercents | `Object` | <p>Sell order percentages</p> |
| risePricePercents.S1 | `Number` | <p>Sell order 1 percentage</p> |
| risePricePercents.S2 | `Number` | <p>Sell order 2 percentage</p> |
| risePricePercents.S3 | `Number` | <p>Sell order 3 percentage</p> |
| risePricePercents.S4 | `Number` | <p>Sell order 4 percentage</p> |
| risePricePercents.S5 | `Number` | <p>Sell order 5 percentage</p> |
| risePricePercents.S6 | `Number` | <p>Sell order 6 percentage</p> |
| budgetPercents | `Object` | <p>Budget assigment per order</p> |
| budgetPercents.B1 | `Number` | <p>Budget percentage in buy order 1</p> |
| budgetPercents.B2 | `Number` | <p>Budget percentage in buy order 2</p> |
| budgetPercents.B3 | `Number` | <p>Budget percentage in buy order 3</p> |
| budgetPercents.B4 | `Number` | <p>Budget percentage in buy order 4</p> |
| budgetPercents.B5 | `Number` | <p>Budget percentage in buy order 5</p> |
| budgetPercents.B6 | `Number` | <p>Budget percentage in buy order 6</p> |
| typeRisk | `String` | <p>Risk type</p> |
| baseAssets | `Object[]` | <p>Base assets bought.</p> |
| getSymbolsBy | `String` | <p>Symbols selection type</p> |
| remainderBudget | `Number` | <p>Reaminder budget</p> |
| remainderUsed | `Boolean` | <p>Is remainder budget used?</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |
| investEarnings | `Boolean` | <p>Invest earnings?</p> |
| needKeys | `Boolean` | <p>This bot exchange keys needs to be updated?</p> |
| invalidSymbols | `String[]` |  |
| useUnusedBudget | `Boolean` |  |
| selectedRisk | `String` |  |
| selectedTrend | `String` |  |
| selectedStrategy | `String` |  |
| tradingShield | `Boolean` |  |
| stopBuyBack | `Boolean` |  |
| smartTrend | `Boolean` |  |
| finishedReadon | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Stop-bots-by-origin-hash'></a> Stop bots by origin hash
[Back to top](#top)

<p>Stop bots by origin hash</p>

```
POST /bots/stop-bots-by-origin-hash
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| originHash | `String` |  |
| cancelOption | `String` |  |
| user | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Stop-bots-by-user'></a> Stop bots by user
[Back to top](#top)

<p>Stop bots by user endpoint</p>

```
POST /bots/deat-bots-by-user
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| cancelOption | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message | `String` | <p>Message</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

# <a name='Explorer'></a> Explorer

## <a name='Get-all-bots'></a> Get all bots
[Back to top](#top)

<p>Get all bots</p>

```
GET /explorer-api/bots
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| selectBy |  |  |
| limit |  |  |
| page |  |  |
| sortBy |  |  |
| performance |  |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| items | `Object[]` | <p>Bots list</p> |
| _id | `String` | <p>Bot ID</p> |
| originHash | `String` | <p>Bot origin hash</p> |
| name | `String` | <p>Bot name</p> |
| profit | `Number` | <p>Bot profit</p> |
| quoteAsset | `String` | <p>Quote asset</p> |
| status | `String` | <p>Bot status</p> |
| expireAt | `Number` | <p>Expiration timestamp</p> |
| createdAt | `Number` | <p>Creation timestamp</p> |
| updatedAt | `Number` | <p>Update timestamp</p> |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-average-profits-by-periods'></a> Get average profits by periods
[Back to top](#top)

<p>Get average profits by periods</p>

```
GET /explorer-api/bots/getAvgProfitWidgets
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| sortBy | `String` |  |
| page | `Number` |  |
| limit | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| lastMonthProfits | `Number` |  |
| lastSixMonthsProfits | `Number` |  |
| lastThreeMonthsProfits | `Number` |  |
| lastWeekProfits | `Number` |  |
| lastYearAvgProfits | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-bots-by-status'></a> Get bots by status
[Back to top](#top)

<p>Get bots by status</p>

```
GET /explorer-api/bots/getBotsByStatus
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| type |  | <p>Bot type: <code>nanobots</code> or null</p> |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| on | `Number` |  |
| off | `Number` |  |
| total | `Number` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-profits-by-quotes'></a> Get profits by quotes
[Back to top](#top)

<p>Get profits by quotes</p>

```
GET /explorer-api/bots/getProfitsByQuotes
```
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| _id | `String` |  |
| total | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-system-requests'></a> Get system requests
[Back to top](#top)

<p>Get bot by originHash</p>

```
GET /explorer-api/bots/my-origin-hash
```

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-total-inveted-budget'></a> Get total inveted budget
[Back to top](#top)

<p>Get total inveted budget</p>

```
GET /explorer-api/bots/total-budget
```
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| totalInUSDT | `Number` |  |
| quotes | `Object` |  |
| BNB | `Number` |  |
| BTC | `Number` |  |
| ETH | `Number` |  |
| USDT | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-total-users'></a> Get total users
[Back to top](#top)

<p>Get total users</p>

```
GET /explorer-api/bots/totalUsers
```
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| totalUsers | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-transactions-balance-by-status'></a> Get transactions balance by status
[Back to top](#top)

<p>Get transactions balance by status</p>

```
GET /explorer-api/bots/getTransactionsBalance
```
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| closedTransacions | `Number` |  |
| openTransactions | `Object` |  |
| totalTransactions | `Number` |  |
| transactionsLosses | `Number` |  |
| transactionsWins | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-user-earnings-by-bot'></a> Get user earnings by bot
[Back to top](#top)

<p>Get user earnings by bot</p>

```
GET /explorer-api/bots/get-user-earnings-by-bot
```

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| userEarnings | `Object[]` |  |
| userEarnings.originBot | `String` |  |
| userEarnings.quote | `Number` |  |

### Error response

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

# <a name='Orders'></a> Orders

## <a name='Get-all-user-orders'></a> Get all user orders
[Back to top](#top)

<p>Get all user orders endpoint</p>

```
GET /bots/getAllUserOrders
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| quote | `String` |  |
| botId | `String` |  |
| startDate | `Number` |  |
| endDate | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| numOrders | `String` |  |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
{
   "numOrders": 10
}
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-today-orders'></a> Get today orders
[Back to top](#top)

<p>Get today orders endpoint</p>

```
GET /bots/getTodayOrders
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| userId | `String` |  |
| originHash | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| numOrders | `Number` | <p>Total de ordenes</p> |
| todayOrder | `Number` | <p>Ordenes creadas el día de hoy</p> |

### Success response example

#### Success response example - `Success-Response:`

```json
HTTP/1.1 200 OK
{
   "numOrders": 1000,
   "todayOrder": 20
}
```

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-user-orders'></a> Get user orders
[Back to top](#top)

<p>Get user orders endpoint</p>

```
GET /bots/getOrders
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| query | `String` |  |
| limit | `Number` |  |
| page | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| items | `Object[]` | <p>Orders list</p> |
| items._id | `String` | <p>Order</p> |
| items.user | `String` | <p>Order user</p> |
| items.hash | `String` | <p>Order hash</p> |
| items.originHash | `String` | <p>Origin bot hash</p> |
| items.plan | `String` | <p>User plan</p> |
| items.exchange | `String` | <p>order exchange</p> |
| items.orderExchange | `Object` | <p>Order exchange information</p> |
| items.orderExchange.orderId | `Number` | **optional**<p>Order ID</p> |
| items.orderExchange.symbol | `String` | **optional**<p>Order symbol</p> |
| items.orderExchange.orderListId | `Number` | **optional** |
| items.orderExchange.clientOrderId | `String` | **optional**<p>Client order ID</p> |
| items.orderExchange.price | `String` | **optional**<p>Price</p> |
| items.orderExchange.origQty | `String` | **optional** |
| items.orderExchange.executedQty | `String` | **optional**<p>Executed quantity</p> |
| items.orderExchange.cummulativeQuoteQty | `String` | **optional**<p>Cummulative quote quantity</p> |
| items.orderExxchange.status | `String` | **optional**<p>Order status</p> |
| items.orderExchange.timeInForce | `String` | **optional**<p>Order quantity</p> |
| items.orderExchange.type | `String` | **optional**<p>Order type</p> |
| items.orderExchange.side | `String` | **optional**<p>Order side: <code>BUY</code> or <code>SELL</code></p> |
| items.orderExchange.stopPrice | `String` | **optional**<p>Stop price</p> |
| items.orderExchange.icebergQty | `String` | **optional** |
| items.orderExchange.time | `Number` | **optional**<p>Creation timestamp</p> |
| items.orderExchange.isWorking | `Boolean` | **optional** |
| items.orderExchange.origQuoteOrderQty | `String` | **optional** |
| items.orderExchange.quoteOrderQtyReal | `Number` | **optional** |
| items.node | `String` | <p>Order node</p> |
| items.memory | `String` | <p>Order memory</p> |
| items.name | `String` | <p>Order name</p> |
| items.side | `String` | <p>Order side: <code>BUY</code> o <code>SELL</code></p> |
| items.symbol | `String` | <p>Order symbol</p> |
| items.base | `String` | <p>Base asset</p> |
| items.quote | `String` | <p>Quote asset</p> |
| items.price | `Number` | <p>Price</p> |
| items.amount | `Number` | <p>Amount</p> |
| items.iteration | `Number` | <p>Iteration</p> |
| items.processed | `Boolean` | <p>Processed</p> |
| items.stopLoss | `String` | <p>Stop loss</p> |
| items.triggerStopLoss | `Number` | <p>Stop loss price</p> |
| items.firstOrder | `firstOrder` | <p>Summary first order</p> |
| items.status | `String` | <p>Order status</p> |
| items.quoteOrderQtyReal | `Number` | <p>Quote order quantity</p> |
| items.amountForced | `Boolean` |  |
| items.pendingCancel | `Boolean` | <p>Pending cancel in exchange</p> |
| items.amountSellOrder | `Number` | <p>Sold amount</p> |
| items.needKeys | `Boolen` | <p>Need keys update</p> |
| items.finishedAt | `Number` | <p>Finished timestamp</p> |
| items.createdAt | `Number` | <p>Creation timestamp</p> |
| items.updatedAt | `Number` | <p>Update timestamp</p> |
| totalItems | `Number` | <p>Total items</p> |
| totalPages | `Number` | <p>Total pages</p> |
| page | `Number` | <p>Current page</p> |
| limit | `Number` | <p>Current elements</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

# <a name='Summaries'></a> Summaries

## <a name='Get-summaries'></a> Get summaries
[Back to top](#top)

<p>Get summaries</p>

```
GET /bots/get-summaries
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| hash | `String` |  |
| startDate | `Number` |  |
| nanobots | `Boolean` |  |
| page | `Number` |  |
| limit | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| items | `Object[]` | <p>Summary list</p> |
| items._id | `String` | <p>Summary ID</p> |
| items.user | `String` | <p>Summary user</p> |
| items.token | `String` | <p>Summary token asset</p> |
| items.quote | `String` | <p>Summary quote asset</p> |
| items.symbol | `String` | <p>Summary symbol</p> |
| items.budgetPercentage | `Number` | <p>Bot budget percentage in this summary</p> |
| items.purchase | `Number` | <p>Budget executed</p> |
| items.sale | `Number` | <p>Summary sold amount</p> |
| items.profit | `Number` | <p>Summary profits</p> |
| items.profitPercent | `Number` | <p>Summary profits percent</p> |
| items.hash | `String` | <p>Summary hash</p> |
| items.plan | `String` | <p>Summary plan</p> |
| items.originHash | `String` | <p>Origin bot hash</p> |
| items.budget | `Number` | <p>Budget invested</p> |
| items.status | `String` | <p>Summary status</p> |
| items.trailing | `Boolean` | <p>Trailing</p> |
| items.needKeys | `Boolean` | <p>Invalid current summary keys</p> |
| items.finishedAt | `Number` | <p>Finished timestamp</p> |
| items.profitPercentBot | `Number` | <p>Profits percent compared to bot</p> |
| items.accounted | `Boolean` |  |
| items.hasSellMarket | `Boolean` | <p>Has a sell market completed</p> |
| items.createdAt | `Number` | <p>Creation timestamp</p> |
| items.updatedAt | `Number` | <p>Update timestamp</p> |
| items.stop | `Boolean` | <p>Summary stopped by user</p> |
| totalItems | `Number` | <p>Total items</p> |
| limit | `Number` | <p>Items returned in this query</p> |
| page | `Number` | <p>Current page</p> |
| totalPages | `Number` | <p>Total pages</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Get-summary-orders'></a> Get summary orders
[Back to top](#top)

<p>Get summary orders endpoint</p>

```
GET /bots/summaryOrders/:summaryId
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Parameters - `Parameter`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| summaryId | `String` | <p>ID del summary</p> |

### Query Parameters

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| user | `String` |  |
| query | `String` |  |
| limit | `Number` |  |
| page | `Number` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| items | `Object[]` | <p>Orders list</p> |
| items._id | `String` | <p>Order</p> |
| items.user | `String` | <p>Order user</p> |
| items.hash | `String` | <p>Order hash</p> |
| items.originHash | `String` | <p>Origin bot hash</p> |
| items.plan | `String` | <p>User plan</p> |
| items.exchange | `String` | <p>order exchange</p> |
| items.orderExchange | `Object` | <p>Order exchange information</p> |
| items.orderExchange.orderId | `Number` | **optional**<p>Order ID</p> |
| items.orderExchange.symbol | `String` | **optional**<p>Order symbol</p> |
| items.orderExchange.orderListId | `Number` | **optional** |
| items.orderExchange.clientOrderId | `String` | **optional**<p>Client order ID</p> |
| items.orderExchange.price | `String` | **optional**<p>Price</p> |
| items.orderExchange.origQty | `String` | **optional** |
| items.orderExchange.executedQty | `String` | **optional**<p>Executed quantity</p> |
| items.orderExchange.cummulativeQuoteQty | `String` | **optional**<p>Cummulative quote quantity</p> |
| items.orderExxchange.status | `String` | **optional**<p>Order status</p> |
| items.orderExchange.timeInForce | `String` | **optional**<p>Order quantity</p> |
| items.orderExchange.type | `String` | **optional**<p>Order type</p> |
| items.orderExchange.side | `String` | **optional**<p>Order side: <code>BUY</code> or <code>SELL</code></p> |
| items.orderExchange.stopPrice | `String` | **optional**<p>Stop price</p> |
| items.orderExchange.icebergQty | `String` | **optional** |
| items.orderExchange.time | `Number` | **optional**<p>Creation timestamp</p> |
| items.orderExchange.isWorking | `Boolean` | **optional** |
| items.orderExchange.origQuoteOrderQty | `String` | **optional** |
| items.orderExchange.quoteOrderQtyReal | `Number` | **optional** |
| items.node | `String` | <p>Order node</p> |
| items.memory | `String` | <p>Order memory</p> |
| items.name | `String` | <p>Order name</p> |
| items.side | `String` | <p>Order side: <code>BUY</code> o <code>SELL</code></p> |
| items.symbol | `String` | <p>Order symbol</p> |
| items.base | `String` | <p>Base asset</p> |
| items.quote | `String` | <p>Quote asset</p> |
| items.price | `Number` | <p>Price</p> |
| items.amount | `Number` | <p>Amount</p> |
| items.iteration | `Number` | <p>Iteration</p> |
| items.processed | `Boolean` | <p>Processed</p> |
| items.stopLoss | `String` | <p>Stop loss</p> |
| items.triggerStopLoss | `Number` | <p>Stop loss price</p> |
| items.firstOrder | `firstOrder` | <p>Summary first order</p> |
| items.status | `String` | <p>Order status</p> |
| items.quoteOrderQtyReal | `Number` | <p>Quote order quantity</p> |
| items.amountForced | `Boolean` |  |
| items.pendingCancel | `Boolean` | <p>Pending cancel in exchange</p> |
| items.amountSellOrder | `Number` | <p>Sold amount</p> |
| items.needKeys | `Boolen` | <p>Need keys update</p> |
| items.finishedAt | `Number` | <p>Finished timestamp</p> |
| items.createdAt | `Number` | <p>Creation timestamp</p> |
| items.updatedAt | `Number` | <p>Update timestamp</p> |
| totalItems | `Number` | <p>Total items</p> |
| totalPages | `Number` | <p>Total pages</p> |
| page | `Number` | <p>Current page</p> |
| limit | `Number` | <p>Current elements</p> |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

## <a name='Stop-summary'></a> Stop summary
[Back to top](#top)

<p>Stop summary</p>

```
POST /bots/stop-by-summary
```

### Headers - `Header`

| Name    | Type      | Description                          |
|---------|-----------|--------------------------------------|
| Authorization | `String` | <p>Authorization token. Ex: <code>Bearer [token]</code></p> |
| x-webclient-key | `String` | <p>Web client API key</p> |

### Request Body

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| summaryId | `String` |  |
### Success response

#### Success response - `Success 200`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message | `String` |  |

### Error response

#### Error response - `401 Unauthorized`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Unauthorized</p> |

#### Error response - `500 Internal Server Error`

| Name     | Type       | Description                           |
|----------|------------|---------------------------------------|
| message |  | <p>Internal server error</p> |

