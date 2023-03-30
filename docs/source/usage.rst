Trade
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

.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - Heading row 1, column 1
     - Heading row 1, column 2
     - Heading row 1, column 3
   * - Row 1, column 1
     -
     - Row 1, column 3
   * - Row 2, column 1
     - Row 2, column 2
     - Row 2, column 3

Example
**********

Get market data for all tickers and all market pairs

.. example-code::
  .. code-block:: JSON
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


Creating recipes
----------------

To retrieve a list of random ingredients,
you can use the ``lumache.get_random_ingredients()`` function:

.. autofunction:: lumache.get_random_ingredients

The ``kind`` parameter should be either ``"meat"``, ``"fish"``,
or ``"veggies"``. Otherwise, :py:func:`lumache.get_random_ingredients`
will raise an exception.

.. autoexception:: lumache.InvalidKindError

For example:

>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

