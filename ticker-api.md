# Tickers API

Get 24 hours trading activity for all trading pairs.

HTTP Request:

```
GET https://www.coindelta.com/api/v2/public/pricetickers/
```

Response:

A JSON of price data objects for all trading pairs

|Fields        |Description                                     |
|-------------:|:-----------------------------------------------|
|id            |Unique ID of the trading pair                   |
|isFrozen      |Status of the trading pair; 0 means active      |
|quoteVolume   |24 hrs trading volume in INR                    |
|baseVolume    |24 hrs trading volume in secondary currency     |
|highestBid    |Best bid price                                  |
|lowestAsk     |Best ask price                                  |
|last          |last traded price                               |
|high24hr      |Highest traded price in last 24 hrs             |
|low24hr       |Lowest traded price in last 24 hrs              |
|percentChange | Percentage change in price from the last 24 hrs|

## Example

> curl https://www.coindelta.com/api/v2/public/pricetickers/

Response (200):

```
{
  "INR_BTC": {
    "id":1,                             //type <int>
    "isFrozen":"0",
    "quoteVolume":"10166385.8891",      // in INR (Rs.)
    "baseVolume":"25.08366882"          // in BTC
    "highestBid":"412000.0",            // in INR
    "lowestAsk":"419000.0",             // in INR
    "last":"405299.0",                  // in INR
    "high24hr":"426894.46",             // in INR
    "low24hr":"405100.0",               // in INR
    "percentChange":"-3.54831717",      // in %
  },
  "INR_XRP": {
    "id":11,
    "isFrozen":"0",
    "quoteVolume":"2219830.70702",      // in INR (Rs.)
    "baseVolume":"59592.7706582"        // in XRP
    "highestBid":"37.5",                // in INR
    "lowestAsk":"37.93",
    "last":"37.25",
    "high24hr":"38.8",
    "low24hr":"36.21",
    "percentChange":"-3.77260982",
  },
}
```

#### Explaination:

* In the last 24 hours, the trading volume of the BTC-INR market was Rs. 10,166,385 which is equivalent to 25.08366882 BTC. 
* The best bid is placed at Rs. 412,000 and the best ask is placed at Rs. 419,000. 
* The last traded price of BTC was Rs. 405,299. 
* The market touched the highest price of Rs. 426894 while the lowest was Rs. 405100.
* Bitcoin price fell by -3.54% in the last 24 hrs.