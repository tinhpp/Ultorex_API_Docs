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

.. list-table:: Title
   :widths: 25 25 50
   :header-rows: 1

   * - Key
     - detail
     - type
   * - name
     - Chain Name
     - string
   * - can_withdraw
     - Enable Withdraw
     - boolean
   * - can_deposit
     - Enable Deposit
     - boolean
   * - min_withdraw
     - Min Withdraw
     - string
   * - max_withdraw
     - Max Withdraw
     - string
   * - unified_cryptoasset_id
     - Unified cryptoasset id
     - string

Example
**********

Get market data for all tickers and all market pairs

.. example-code::

  .. code-block:: JSON

    {
      "key": "value"
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

