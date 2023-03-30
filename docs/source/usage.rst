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

.. list-table:: Responses
   :widths: 25 25 50
   :header-rows: 1

   * 	- Key
		- Type
		- Description
	* 	- trading_pairs
		- string
		- Currency pair
	* 	- base_currency
		- string
		- Symbol/currency code of base pair, eg. BTC
	* 	- quote_currency
		- string
		- Symbol/currency code of target pair, eg. ETH
	* 	- last_price
		- number
		- Last transacted price of base currency based on given target currency
	* 	- lowest_ask
		- number
		- Current lowest ask price
	* 	- highest_bid
		- number
		- Current highest bid price
	* 	- base_volume
		- number
		- Transaction amount in base pair volume.
	* 	- quote_volume
		- number
		- Transaction amount in quote pair volume.
	* 	- price_change_percent_24h
		- number
		- Price change percent 24h
	* 	- highest_price_24h
		- number
		- Rolling 24-hours highest transaction price
	* 	- lowest_price_24h
		- number
		- Rolling 24-hours lowest transaction price.

Example
**********

đđđd

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

