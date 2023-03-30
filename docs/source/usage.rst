Market
=====

.. _summary:

Market Overview
------------

Get market data for all tickers and all market pairs

Request method
**********
  
* Endpoint: https://api.ultorex.io/api/coinmarketcap/summary
* Method: GET

Responses
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - trading_pairs
     - string
     - Currency pair
   * - base_currency
     - string
     - Symbol/currency code of base pair, eg. BTC
   * - quote_currency
     - array
     - Symbol/currency code of target pair, eg. ETH
   * - last_price
     - number
     - Last transacted price of base currency based on given target currency
   * - lowest_ask
     - number
     - Current lowest ask price
   * - highest_bid
     - number
     - Current highest bid price
   * - base_volume
     - number
     - Transaction amount in base pair volume.
   * - quote_volume
     - number
     - Transaction amount in quote pair volume.
   * - price_change_percent_24h
     - number
     - Price change percent 24h
   * - highest_price_24h
     - number
     - Rolling 24-hours highest transaction price
   * - lowest_price_24h
     - number
     - Rolling 24-hours lowest transaction price.

Example
**********

Get market data for all tickers and all market pairs

.. code-block:: json
  :linenos:

   {
    "code": 0,
    "data": [
        {
            "trading_pairs": "AVAX_BTC",
            "base_currency": "AVAX",
            "quote_currency": "BTC",
            "last_price": "0.0008005",
            "lowest_ask": "0.0008005",
            "highest_bid": "0.0008004",
            "base_volume": "7953.7300000",
            "quote_volume": "6.3956518",
            "price_change_percent_24h": "-0.95",
            "highest_price_24h": "0.0008208",
            "lowest_price_24h": "0.0007844"
        },
        {
            "trading_pairs": "AVAX_USDT",
            "base_currency": "AVAX",
            "quote_currency": "USDT",
            "last_price": "24.45",
            "lowest_ask": "24.44",
            "highest_bid": "24.43",
            "base_volume": "7998.72",
            "quote_volume": "195019.53",
            "price_change_percent_24h": "2.30",
            "highest_price_24h": "25.87",
            "lowest_price_24h": "23.41"
        },
    ]
   }



Market Info
----------------

Get detailed summary for each currency available on the exchange

Request method
**********
  
* Endpoint: https://api.ultorex.io/api/coinmarketcap/assets
* Method: GET

Responses
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - name
     - string
     - Chain Name
   * - can_withdraw
     - boolean
     - Enable Withdraw
   * - can_deposit
     - boolean
     - Enable Deposit
   * - min_withdraw
     - string
     - Min Withdraw
   * - max_withdraw
     - string
     - Max Withdraw
   * - unified_cryptoasset_id
     - string
     - Unified cryptoasset id

Example
**********

.. code-block:: json
  :linenos:

   {
    "code": 0,
    "data": {
       "BTC": {
            "name": "bitcoin",
            "can_withdraw": true,
            "can_deposit": true,
            "min_withdraw": "0.000011",
            "max_withdraw": "0.00",
            "unified_cryptoasset_id": "1"
        },
        "XRP": {
            "name": "xrp",
            "can_withdraw": true,
            "can_deposit": true,
            "min_withdraw": "0.62",
            "max_withdraw": "0.00",
            "unified_cryptoasset_id": "52"
        },
      }
   }
   
Ticker
----------------

Get 24-hour pricing and volume summary for each market pair

Request method
**********
  
* Endpoint: https://api.ultorex.io/api/coinmarketcap/ticker
* Method: GET

Responses
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - last_price
     - string
     - Last transacted price of base currency based on given target currency (unit in base or target)
   * - base_volume
     - string
     - 24 hour trading volume for the pair (unit in base)
   * - quote_volume
     - string
     - 24 hour trading volume for the pair (unit in target)
   * - base_id
     - string
     - Base id
   * - isFrozen
     - string
     - Is Frozen

Example
**********

.. code-block:: json
  :linenos:

   {
    "code": 0,
    "data": {
        "ORBS_USD": {
            "last_price": "0.05329",
            "base_volume": "68863.00000",
            "quote_volume": "3675.26662",
            "base_id": "3835",
            "isFrozen": "0"
        },
        "FTM_BTC": {
            "last_price": "0.00001140",
            "base_volume": "164801.00000000",
            "quote_volume": "1.89923943",
            "base_id": "3513",
            "quote_id": "1",
            "isFrozen": "0"
        },
      }
   }
   
Historical Trades
----------------
Get a complete level 2 order book

Request method
**********
  
* Endpoint: https://api.ultorex.io/api/coinmarketcap/orderbook/{market_pair}
* Method: GET

Parameter
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - market_pair
     - String
     - Market Pair
   * - depth
     - Number
     - Orders depth quantity: [0, 100, 200, 500...]. 0 returns full depth. Depth = 100 means 50 for each bid/ask side
   * - level
     - Number
     - Level

Responses
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - timestamp
     - string
     - Unix timestamp in milliseconds for when the last updated time occurred.
   * - asks
     - array
     - An array containing 2 elements. The ask price and quantity for each ask order
   * - bids
     - array
     - An array containing 2 elements. The offer price and quantity for each bid order

Example
**********

.. code-block:: json
  :linenos:

   {
    "code": 0,
    "data": {
        "timestamp": "1654675049562",
        "asks": [
            [
                "0.0020510",
                "0.17"
            ],
            [
                "0.0020512",
                "0.34"
            ],
        ],
       "bids":[
           [
                "0.0020331",
                "0.69"
            ],
            [
                "0.0020330",
                "0.58"
            ],
        ]
      }
   }

Historical Data
----------------
Get data on all recently completed trades

Request method
**********
  
* Endpoint: https://api.ultorex.io/api/coinmarketcap/trades/{market_pair}
* Method: GET

Parameter
**********

.. list-table:: 
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - market_pair
     - String
     - Market Pair

Responses
**********

.. list-table::
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - Type
     - Description
   * - trade_id
     - string
     - A unique ID associated with the trade for the currency pair transaction
   * - price
     - string
     - Transaction price in base pair volume
   * - base_volume
     - string
     - Transaction amount in base pair volume.
   * - quote_volume
     - string
     - Transaction amount in target pair volume.
   * - timestamp
     - string
     - Unix timestamp in milliseconds for when the transaction occurred.
   * - type
     - string
     - Used to determine the type of the transaction that was completed.

Example
**********

.. code-block:: json
  :linenos:

   {
    "code": 0,
    "data": [
        {
            "trade_id": "984127582519715840",
            "price": "0.0020414",
            "base_volume": "0.15",
            "quote_volume": "0.00030621",
            "timestamp": "1654675899879",
            "type": "buy"
        },
         {
            "trade_id": "984163011327453184",
            "price": "0.0020433",
            "base_volume": "0.02",
            "quote_volume": "0.00004086",
            "timestamp": "1654684346765",
            "type": "buy"
        }
      ]
   }
