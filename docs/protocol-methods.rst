==================
 Protocol Methods
==================

blockchain.tag.qualifier.list
========================================

Returns a dictionary with information regarding all of the tags associated with a qualifier.

**Signature**

    .. function:: blockchain.tag.qualifier.list(asset, include_mempool=True)
    .. versionadded:: 1.11

    *asset*

      The name of the asset as an ascii compliant string.

    *include_mempool*

      Whether or not to overwrite information with relevant information from the mempool


**Result**

    A dictionary of tags and chain location information.

**Example Results**

    {
      "3baebe536ebb14776b456c68425fea8ce06e9732": {
          "flag": true,
          "height": 361894,
          "tx_hash": "57c6ff965de70d51c5f4235f7adcee96e872ab3b5ca64497f655260e49a62b15",
          "tx_pos": 2
      },
      "4dfab22bfc28d7f9849512161c020e834897fbda": {
          "flag": false,
          "height": 361944,
          "tx_hash": "cd8c9477688e4215edaf0560e06adf07bc794d4c18d83a23dc0e7581d95e59bb",
          "tx_pos": 1
      }
    }


blockchain.tag.qualifier.subscribe
===============================

Subscribe a qualifier asset's tags

**Signature**

  .. function:: blockchain.tag.qualifier.subscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  The :ref:`status <qualifier_tags_status>` of the qualifier asset.

**Notifications**

  The client will receive a notification when the :ref:`status <qualifier_tags_status>` of the asset
  changes. The status uses mempool tags. Its signature is

    .. function:: blockchain.asset.broadcasts.subscribe(asset, status)
       :noindex:

blockchain.tag.h160.subscribe
===============================

Subscribe an `h160`'s qualifications

**Signature**

  .. function:: blockchain.tag.h160.subscribe(h160)
  .. versionadded:: 1.11

  *h160*

    The h160 of a public key as a hex string

**Result**

  The :ref:`status <h160_tags_status>` of the `h160`.

**Notifications**

  The client will receive a notification when the :ref:`status <h160_tags_status>` of the `h160`
  changes. The status uses mempool tags. Its signature is

    .. function:: blockchain.tag.h160.subscribe(h160, status)
       :noindex:

blockchain.asset.broadcasts.subscribe
===============================

Subscribe an asset's broadcasts

**Signature**

  .. function:: blockchain.asset.broadcasts.subscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  The :ref:`status <broadcast_messages_status>` of the qualifier asset.

**Notifications**

  The client will receive a notification when the :ref:`status <broadcast_messages_status>` of the asset
  changes.  Its signature is

    .. function:: blockchain.asset.broadcasts.subscribe(asset, status)
       :noindex:

blockchain.asset.is_frozen.subscribe
===============================

Subscribe to a restricted asset's frozen status

**Signature**

  .. function:: blockchain.asset.is_frozen.subscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the restricted asset as an ascii compliant string.

**Result**

  The same as `blockchain.asset.is_frozen` (using the mempool)

**Notifications**

  The client will receive a notification when the result of `blockchain.asset.is_frozen` changes.
  Its signature is

    .. function:: blockchain.asset.is_frozen.subscribe(asset, result)
       :noindex:

blockchain.asset.verifier_string.subscribe
===============================

Subscribe to a restricted asset's verifier string

**Signature**

  .. function:: blockchain.asset.verifier_string.subscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the restricted asset as an ascii compliant string.

**Result**

  The same as `blockchain.asset.verifier_string` (using the mempool)

**Notifications**

  The client will receive a notification when the result of `blockchain.asset.verifier_string` changes.
  Its signature is

    .. function:: blockchain.asset.verifier_string.subscribe(asset, result)
       :noindex:

blockchain.asset.restricted_associations.subscribe
===============================

Subscribe to restricted assets that have this qualifier in their
verifier string.

**Signature**

  .. function:: blockchain.asset.restricted_associations.subscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the qualifier asset as an ascii compliant string.

**Result**

  The :ref:`status <qualifier_restricted_status>` of the qualifier asset.

**Notifications**

  The client will receive a notification when the :ref:`status <qualifier_restricted_status>` of the qualifier
  changes. The status uses mempool verifier strings. Its signature is

    .. function:: blockchain.asset.restricted_associations.subscribe(asset, status)
       :noindex:

blockchain.tag.qualifier.unsubscribe
=================================

Unsubscribe from a qualifier asset, preventing future notifications if its :ref:`status
<qualifier_tags_status>` changes.

**Signature**

  .. function:: blockchain.tag.qualifier.unsubscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.tag.h160.unsubscribe
=================================

Unsubscribe from an `h160`, preventing future notifications if its :ref:`status
<h160_tags_status>` changes.

**Signature**

  .. function:: blockchain.tag.h160.unsubscribe(h160)
  .. versionadded:: 1.11

  *h160*

    The h160 of a public key as a hex string

**Result**

  Returns :const:`True` if the `h160` was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.asset.broadcasts.unsubscribe
=================================

Unsubscribe from an asset, preventing future notifications if its :ref:`status
<broadcast_messages_status>` changes.

**Signature**

  .. function:: blockchain.asset.broadcasts.unsubscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.asset.is_frozen.unsubscribe
=================================

Unsubscribe from a restricted asset, preventing future notifications if its 
frozen status changes.

**Signature**

  .. function:: blockchain.asset.is_frozen.unsubscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the restricted asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.asset.verifier_string.unsubscribe
=================================

Unsubscribe from a restricted asset, preventing future notifications if its 
verifier string changes.

**Signature**

  .. function:: blockchain.asset.verifier_string.unsubscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the restricted asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.asset.restricted_associations.unsubscribe
=================================

Unsubscribe from a qualifier asset, preventing future notifications if its :ref:`status
<qualifier_restricted_status>` changes.

**Signature**

  .. function:: blockchain.asset.restricted_associations.unsubscribe(asset)
  .. versionadded:: 1.11

  *asset*

    The name of the qualifier asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.tag.check
========================================

Returns a dictionary with information regarding a tagged address's h160.

**Signature**

    .. function:: blockchain.tag.check(h160, asset)
    .. versionchanged:: 1.11
      renamed function
    .. versionadded:: 1.10

    *h160*

      The h160 of a public key as a hex string

    *asset*

      A restricted or qualifing asset as an ascii-compliant string

**Result**

    A dictionary containing a flag. If there is no on-chain data, this defaults to :const:`false`. Otherwise chain location information is included.

    If *asset* is a qualifing asset, a :const:`true` flag denotes that this public key is tagged by qualifier.

    If *asset* is a restricted asset, a :const:`true` flag denotes that this public key is frozen from spending the restricted asset.

**Example Results**

    {
      "flag": true,
      "height": 1047144,
      "tx_hash": "7e176ed933db1d57b81d939b5ee328bbd483d62f896c2bf0f0c709c44d7790b1",
      "tx_pos": 1
    }

blockchain.tag.h160.list
========================================

Returns a dictionary with information regarding all of the tags associated with a h160.

**Signature**

    .. function:: blockchain.tag.h160.list(h160, include_mempool=True)
    .. versionchanged:: 1.11
      renamed function
    .. versionadded:: 1.10

    *h160*

      The h160 of a public key as a hex string

    *include_mempool*

      Whether or not to overwrite information with relevant information from the mempool


**Result**

    A dictionary of tags and chain location information.

**Example Results**

    {
      "#QUALTEST": {
          "flag": true,
          "height": 1047144,
          "tx_hash": "7e176ed933db1d57b81d939b5ee328bbd483d62f896c2bf0f0c709c44d7790b1",
          "tx_pos": 1
      },
      "$TESTASSET1": {
          "flag": true,
          "height": 1047145,
          "tx_hash": "a93d7bd4cbc83ba334b48658a9b94a4718c497c0d7c39cba8281a07249fc1431",
          "tx_pos": 1
      }
    }

blockchain.asset.is_frozen
========================================

Returns a dictionary with information regarding whether a restricted asset is globally frozen.

**Signature**

    .. function:: blockchain.asset.is_frozen(asset, include_mempool=True)
    .. versionadded:: 1.10

    *asset*

      A restricted asset as an ascii-compliant string

    *include_mempool*

      Whether or not to overwrite information with relevant information from the mempool


**Result**

    A dictionary containing a *frozen* booelean. If there is no on-chain data, this defaults to :const:`false`. Otherwise chain location information is included.

**Example Results**

    {
      "frozen": false,
      "height": 1047127,
      "tx_hash": "41ac251f352ba497c8b3af9e28aa0db889da287423a01e611c6169cc43b8596b",
      "tx_pos": 1
    }

blockchain.asset.verifier_string
========================================

Returns a dictionary with information about a restricted asset's qualifications

**Signature**

    .. function:: blockchain.asset.verifier_string(asset, include_mempool=True)
    .. versionchanged:: 1.11
      renamed function
    .. versionadded:: 1.10

    *asset*

      A restricted asset as an ascii-compliant string

    *include_mempool*

      Whether or not to overwrite information with relevant information from the mempool


**Result**

    A dictionary containing a qualifier boolean logic string to show what qualifier tags an address needs to recieve this asset.

**Example Results**

    {
      "height": 1047149,
      "qualifying_tx_pos": 1,
      "restricted_tx_pos": 4,
      "string": "QUALTEST|QUALTEST",
      "tx_hash": "db27e9b9471f5695685fb018889ac4601720655f68194bfbbc5a835fb35b4369"
    }

blockchain.asset.restricted_associations
========================================

Returns a list of restricted assets of who's qualifing string contains the qualifier asset in some form

**Signature**

    .. function:: blockchain.asset.restricted_associations(asset, include_mempool=True)
    .. versionchanged:: 1.11
    .. versionadded:: 1.10

    *asset*

      A qualifying asset as an ascii-compliant string

    *include_mempool*

      Whether or not to overwrite information with relevant information from the mempool


**Result**

    A dictionary containing restricted assets and on-chain location data

**Example Results**

    {
      "$SWAP": {
          "associated": true,
          "height": 756895,
          "qualifying_tx_pos": 0,
          "restricted_tx_pos": 4,
          "tx_hash": "a2b634e160974348647484302501a64bc80a841d4a9ea833498a47e72e987628"
      }
    }

blockchain.asset.list_addresses_by_asset
========================================

An **optional** method. Requires --assetindex=1 in frend. Returns an error if unavaliable. Returns a dictionary with information about what address(es) hold an asset.

**Signature**

  .. function:: blockchain.asset.list_addresses_by_asset(asset, onlytotal=false, count=1000, start=0)
  .. versionadded:: 1.9

  *asset*

    An ascii-compliant asset name

  *onlytotal*

    If :const:`True`, only the number of addresses holding this asset is returned.
    Otherwise, addresses with values are returned.

  *count*

    Only matters if :const:`onlytotal` is :const:`True`.
    Truncates the results to this number. Maximum of 1000 and must be at least 1.

  *start*

    Only matters if :const:`onlytotal` is :const:`True`.
    Result skips over this many addresses and returns the next :const:`count`. Must be
    0 or greater.

**Result**

    If *onlytotal* is :const:`false`:

       A dictionary mapping addresses to their asset count

    If *onlytotal* is :const:`true`:

       A dictionary denoting how many addresses total hold this asset

**Example Results**

When *onlytotal* is :const:`false`::

 {
    "R9HC7XkCwnQA5dQZ18BntXgUe9ESuALU3J": 2,
    "R9HCY7PtFZb6RkvdnpDjDhguRTWMTEYW6q": 1,
    "R9HCbhPSLkPtnESx2FSSUEdAxK6CfVQKJ3": 1,
    "R9HCeygiyUGSuB2njMEy3P5NDNdL2zuCDv": 1,
    "R9HCgctF8nRUfR7Liy2WJw6nN6naeihYDa": 1,
    "R9HCmJtzYdCJ4Zw2ziaSgwWzwQPqsopRWA": 1,
    "R9HCsMj7kCMatpR6sWo9dwNUA3caLf4G6F": 1,
    "R9HD36FUXbF1Eq6ZU4ukQAHKXrUcB5zz6n": 1,
    "R9HD7HTST7SshLdbHdGpFXNpXWab1iRQEF": 1,
    "R9HDH3ZDuLRVF8ivzUwnojZa7thtRXQooM": 1
 }

When *onlytotal* is :const:`true`::

 {
    "unique_addresses": 91570
 }

blockchain.asset.get_assets_with_prefix
=======================================

Returns a list of assets that begin with the prefix. Comparable to the regex
\^{{prefix}}.*\.

**Signature**

  .. function:: blockchain.asset.get_assets_with_prefix(prefix)
  .. versionadded:: 1.9

  *prefix*

    What the asset should begin with.

**Result**

  A list of assets that begin with the prefix.

**Result Example**

::

  [AN_ASSET, ANT, AN_ASSET/SUB_ASSET, ANT#UNIQUE]

blockchain.asset.broadcasts
=======================================

Return the messages broadcast from a (message channel) asset broadcast.

**Signature**

  .. function:: blockchain.asset.broadcasts(message_channel)
  .. versionadded:: 1.9

  *message_channel*

    The message channel asset.

**Result**

  A list containing a history of all broadcasts made from this message
  channel sorted by height. The values are txid, the broadcast
  data, the transaction height, and position in the transactions of the broadcast.

**Result Example**

::

  [
    {
      "tx_hash": "d5948b8df75c2590bcf4cc2c73abccdfd13ad5afbe37f4445abcc0a048392782",
      "data": "Qme7ss3ARVgxv6rXqVPiikMJ8u2NLgmgszg13pYrDKEoiu",
      "height": 1830170,
      "tx_pos": 1
    }
  ]

blockchain.asset.get_meta
=================================

Return metadata associated with a certain asset.

**Signature**

  .. function:: blockchain.asset.get_meta(asset, include_mempool=True)
  .. versionchanged:: 1.11
  .. versionadded:: 1.8

  *asset*

    The name of the asset as an ascii compliant string.

  *include_mempool*

    Whether or not to overwrite information with relevant information from the mempool

**Result**

  Each result is a dictionary with the following keys:

  * *sats_in_circulation*

    A number from 1-21,000,000,000*100,000,000.
    The number of this asset currently in circulation. (The total number of this asset created.)

  * *divisions*

    A number from 0-8.
    The number of sub-divisions this asset can be split into.
    0 means whole numbers, 1 means tenths, 2 means hundredths, etc.

  * *reissuable*

    A boolean.
    Whether the owner of this asset's ownership asset can change its
    metadata.

  * *has_ipfs*

    A boolean.
    Whether this asset has an associated IPFS hash.

  * *ipfs*

    Only if *has_ipfs* is *true*.
    The base58 encoded IPFS hash associated with this asset.

  * *source*

    The source of this metadata on-chain.

  * *source_divisions*

    The previous source of this metadata on-chain that has divisions. (Only if this asset has been reissued with an divisions value of 0xFF.)

  * *source_ipfs*

    The previous source of this metadata on-chain that has the ipfs. (Only if this asset has been reissued with no asset change.)

**Result Example**

::

  {
    "sats_in_circulation": 100000000,
    "divisions": 0,
    "has_ipfs": 1,
    "ipfs": "QmeGgd16sWq6TNfXy8xzwQWRhv1vZUjP1LBxVnfaHaoV25",
    "reissuable": 0,
    "source":
        {
        "tx_hash": "9f2c45a12db0144909b5db269415f7319179105982ac70ed80d76ea79d923ebf",
        "tx_pos": 0,
        "height": 203500
        },
    "source_prev":
        {
        "tx_hash": "2c9f45a12db0144909b5db269415f7319179105982ac70ed80d76ea79d92bf3e",
        "tx_pos": 1,
        "height": 104501
        }
  }

blockchain.asset.subscribe
===============================

Subscribe to an asset.

**Signature**

  .. function:: blockchain.asset.subscribe(asset)
  .. versionadded:: 1.8

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  The :ref:`status <asset_status>` of the asset.

**Notifications**

  The client will receive a notification when the :ref:`status <asset_status>` of the asset
  changes.  Its signature is

    .. function:: blockchain.asset.subscribe(asset, status)
       :noindex:

blockchain.asset.unsubscribe
=================================

Unsubscribe from an asset, preventing future notifications if its :ref:`status
<asset_status>` changes.

**Signature**

  .. function:: blockchain.asset.subscribe(asset)
  .. versionadded:: 1.8

  *asset*

    The name of the asset as an ascii compliant string.

**Result**

  Returns :const:`True` if the asset was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.block.header
=======================

Return the block header at the given height.

**Signature**

  .. function:: blockchain.block.header(height, cp_height=0)
  .. versionadded:: 1.3
  .. versionchanged:: 1.4
     *cp_height* parameter added
  .. versionchanged:: 1.4.1

  *height*

    The height of the block, a non-negative integer.

  *cp_height*

    Checkpoint height, a non-negative integer.  Ignored if zero,
    otherwise the following must hold:

      *height* <= *cp_height*

**Result**

  If *cp_height* is zero, the raw block header as a hexadecimal
  string.

  Otherwise a dictionary with the following keys.  This provides a
  proof that the given header is present in the blockchain; presumably
  the client has the merkle root hard-coded as a checkpoint.

  * *branch*

    The merkle branch of *header* up to *root*, deepest pairing first.

  * *header*

    The raw block header as a hexadecimal string.  Starting with version 1.4.1,
    AuxPoW data (if present in the original header) is truncated.

  * *root*

    The merkle root of all blockchain headers up to and including
    *cp_height*.


**Example Result**

With *height* 5 and *cp_height* 0 on the Bitcoin Cash chain:

::

   "0100000085144a84488ea88d221c8bd6c059da090e88f8a2c99690ee55dbba4e00000000e11c48fecdd9e72510ca84f023370c9a38bf91ac5cae88019bee94d24528526344c36649ffff001d1d03e477"

.. _cp_height example:

With *cp_height* 8::

  {
    "branch": [
       "000000004ebadb55ee9096c9a2f8880e09da59c0d68b1c228da88e48844a1485",
       "96cbbc84783888e4cc971ae8acf86dd3c1a419370336bb3c634c97695a8c5ac9",
       "965ac94082cebbcffe458075651e9cc33ce703ab0115c72d9e8b1a9906b2b636",
       "89e5daa6950b895190716dd26054432b564ccdc2868188ba1da76de8e1dc7591"
       ],
    "header": "0100000085144a84488ea88d221c8bd6c059da090e88f8a2c99690ee55dbba4e00000000e11c48fecdd9e72510ca84f023370c9a38bf91ac5cae88019bee94d24528526344c36649ffff001d1d03e477",
    "root": "e347b1c43fd9b5415bf0d92708db8284b78daf4d0e24f9c3405f45feb85e25db"
  }

blockchain.block.headers
========================

Return a concatenated chunk of block headers from the main chain.

**Signature**

  .. function:: blockchain.block.headers(start_height, count, cp_height=0)
  .. versionadded:: 1.2
  .. versionchanged:: 1.4
     *cp_height* parameter added
  .. versionchanged:: 1.4.1

  *start_height*

    The height of the first header requested, a non-negative integer.

  *count*

    The number of headers requested, a non-negative integer.

  *cp_height*

    Checkpoint height, a non-negative integer.  Ignored if zero,
    otherwise the following must hold:

      *start_height* + (*count* - 1) <= *cp_height*

**Result**

  A dictionary with the following members:

  * *count*

    The number of headers returned, between zero and the number
    requested.  If the chain has not extended sufficiently far, only
    the available headers will be returned.  If more headers than
    *max* were requested at most *max* will be returned.

  * *hex*

    The binary block headers concatenated together in-order as a
    hexadecimal string.  Starting with version 1.4.1, AuxPoW data (if present
    in the original header) is truncated if *cp_height* is nonzero.

  * *max*

    The maximum number of headers the server will return in a single
    request.

  The dictionary additionally has the following keys if *count* and
  *cp_height* are not zero.  This provides a proof that all the given
  headers are present in the blockchain; presumably the client has the
  merkle root hard-coded as a checkpoint.

  * *root*

    The merkle root of all blockchain headers up to and including
    *cp_height*.

  * *branch*

    The merkle branch of the last returned header up to *root*,
    deepest pairing first.


**Example Response**

See :ref:`here <cp_height example>` for an example of *root* and
*branch* keys.

::

  {
    "count": 2,
    "hex": "0100000000000000000000000000000000000000000000000000000000000000000000003ba3edfd7a7b12b27ac72c3e67768f617fc81bc3888a51323a9fb8aa4b1e5e4a29ab5f49ffff001d1dac2b7c010000006fe28c0ab6f1b372c1a6a246ae63f74f931e8365e15a089c68d6190000000000982051fd1e4ba744bbbe680e1fee14677ba1a3c3540bf7b1cdb606e857233e0e61bc6649ffff001d01e36299"
    "max": 2016
  }

blockchain.estimatefee
======================

Return the estimated transaction fee per kilobyte for a transaction to
be confirmed within a certain number of blocks.

**Signature**

  .. function:: blockchain.estimatefee(number)

  *number*

    The number of blocks to target for confirmation.

**Result**

  The estimated transaction fee in coin units per kilobyte, as a
  floating point number.  If the daemon does not have enough
  information to make an estimate, the integer ``-1`` is returned.

**Example Result**

::

  0.00001


blockchain.headers.subscribe
============================

Subscribe to receive block headers when a new block is found.

**Signature**

  .. function:: blockchain.headers.subscribe()

**Result**

  The header of the current block chain tip.  The result is a dictionary with two members:

  * *hex*

    The binary header as a hexadecimal string.

  * *height*

    The height of the header, an integer.

**Example Result**

::

   {
     "height": 520481,
     "hex": "00000020890208a0ae3a3892aa047c5468725846577cfcd9b512b50000000000000000005dc2b02f2d297a9064ee103036c14d678f9afc7e3d9409cf53fd58b82e938e8ecbeca05a2d2103188ce804c4"
   }

**Notifications**

  As this is a subscription, the client will receive a notification
  when a new block is found.  The notification's signature is:

    .. function:: blockchain.headers.subscribe(header)
       :noindex:

    * *header*

      See **Result** above.

.. note:: should a new block arrive quickly, perhaps while the server
  is still processing prior blocks, the server may only notify of the
  most recent chain tip.  The protocol does not guarantee notification
  of all intermediate block headers.

  In a similar way the client must be prepared to handle chain
  reorganisations.  Should a re-org happen the new chain tip will not
  sit directly on top of the prior chain tip.  The client must be able
  to figure out the common ancestor block and request any missing
  block headers to acquire a consistent view of the chain state.


blockchain.relayfee
===================

Return the minimum fee a low-priority transaction must pay in order to
be accepted to the daemon's memory pool.

**Signature**

  .. function:: blockchain.relayfee()

**Result**

  The fee in whole coin units as a floating point number.

**Example Results**

::

   0.000001

blockchain.scripthash.get_balance
=================================

Return the confirmed and unconfirmed balances of a :ref:`script hash
<script hashes>`.

**Signature**

  .. function:: blockchain.scripthash.get_balance(scripthash, asset=False)
  .. versionadded:: 1.1

  *scripthash*

    The script hash as a hexadecimal string.

  *asset*

    An optional value that can be: :const:`False` to return only the Frencoin balance, :const:`True` to 
    return all balances, an asset name to return the balance for the asset, or a list of assets to return
    the balances for those assets (a value of null indicates Frencoin outputs).

**Result**

  A dictionary with keys `confirmed` and `unconfirmed`.  The value of
  each is the appropriate balance in minimum coin units (satoshis).

  If more than one set of balances is to be returned, the result will
  be a dictionary of asset names whose value is the above. Frencoin values
  will be denoted as "fren".

**Result Example**

::

  {
    "confirmed": 103873966,
    "unconfirmed": 23684400
  }

::

  {
    "fren": {
      "confirmed": 103873966,
      "unconfirmed": 23684400
    },
    "TEST": {
      "confirmed": 1000000,
      "unconfirmed": 0
    }
  }

blockchain.scripthash.get_history
=================================

Return the confirmed and unconfirmed history of a :ref:`script hash
<script hashes>`.

**Signature**

  .. function:: blockchain.scripthash.get_history(scripthash)
  .. versionadded:: 1.1

  *scripthash*

    The script hash as a hexadecimal string.

**Result**

  A list of confirmed transactions in blockchain order, with the
  output of :func:`blockchain.scripthash.get_mempool` appended to the
  list.  Each confirmed transaction is a dictionary with the following
  keys:

  * *height*

    The integer height of the block the transaction was confirmed in.

  * *tx_hash*

    The transaction hash in hexadecimal.

  See :func:`blockchain.scripthash.get_mempool` for how mempool
  transactions are returned.

**Result Examples**

::

  [
    {
      "height": 200004,
      "tx_hash": "acc3758bd2a26f869fcc67d48ff30b96464d476bca82c1cd6656e7d506816412"
    },
    {
      "height": 215008,
      "tx_hash": "f3e1bf48975b8d6060a9de8884296abb80be618dc00ae3cb2f6cee3085e09403"
    }
  ]

::

  [
    {
      "fee": 20000,
      "height": 0,
      "tx_hash": "9fbed79a1e970343fcd39f4a2d830a6bde6de0754ed2da70f489d0303ed558ec"
    }
  ]

blockchain.scripthash.get_mempool
=================================

Return the unconfirmed transactions of a :ref:`script hash <script
hashes>`.

**Signature**

  .. function:: blockchain.scripthash.get_mempool(scripthash)
  .. versionadded:: 1.1

  *scripthash*

    The script hash as a hexadecimal string.

**Result**

  A list of mempool transactions in arbitrary order.  Each mempool
  transaction is a dictionary with the following keys:

  * *height*

    ``0`` if all inputs are confirmed, and ``-1`` otherwise.

  * *tx_hash*

    The transaction hash in hexadecimal.

  * *fee*

    The transaction fee in minimum coin units (satoshis).

**Result Example**

::

  [
    {
      "tx_hash": "45381031132c57b2ff1cbe8d8d3920cf9ed25efd9a0beb764bdb2f24c7d1c7e3",
      "height": 0,
      "fee": 24310
    }
  ]


blockchain.scripthash.listunspent
=================================

Return an ordered list of UTXOs sent to a script hash.

**Signature**

  .. function:: blockchain.scripthash.listunspent(scripthash, asset=False)
  .. versionadded:: 1.1

  *scripthash*

    The script hash as a hexadecimal string.

  *asset*

    An optional value that can be: :const:`False` to return only Frencoin outputs, :const:`True` to 
    return all utxos, an asset name to return outputs for the asset, or a list of assets to return
    outputs for those assets (a value of null indicates Frencoin outputs).

**Result**

  A list of unspent outputs in blockchain order.  This function takes
  the mempool into account.  Mempool transactions paying to the
  address are included at the end of the list in an undefined order.
  Any output that is spent in the mempool does not appear.  Each
  output is a dictionary with the following keys:

  * *height*

    The integer height of the block the transaction was confirmed in.
    ``0`` if the transaction is in the mempool.

  * *tx_pos*

    The zero-based index of the output in the transaction's list of
    outputs.

  * *tx_hash*

    The output's transaction hash as a hexadecimal string.

  * *asset*

    The output's asset if any (can be null).

  * *value*

    The output's value in minimum coin units (satoshis).

**Result Example**

::

  [
    {
      "asset": null,
      "tx_pos": 0,
      "value": 45318048,
      "tx_hash": "9f2c45a12db0144909b5db269415f7319179105982ac70ed80d76ea79d923ebf",
      "height": 437146
    },
    {
      "asset": "TEST",
      "tx_pos": 0,
      "value": 919195,
      "tx_hash": "3d2290c93436a3e964cfc2f0950174d8847b1fbe3946432c4784e168da0f019f",
      "height": 441696
    }
  ]

.. _subscribed:

blockchain.scripthash.subscribe
===============================

Subscribe to a script hash.

**Signature**

  .. function:: blockchain.scripthash.subscribe(scripthash)
  .. versionadded:: 1.1

  *scripthash*

    The script hash as a hexadecimal string.

**Result**

  The :ref:`status <status>` of the script hash.

**Notifications**

  The client will receive a notification when the :ref:`status <status>` of the script
  hash changes.  Its signature is

    .. function:: blockchain.scripthash.subscribe(scripthash, status)
       :noindex:

blockchain.scripthash.unsubscribe
=================================

Unsubscribe from a script hash, preventing future notifications if its :ref:`status
<status>` changes.

**Signature**

  .. function:: blockchain.scripthash.unsubscribe(scripthash)
  .. versionadded:: 1.4.2

  *scripthash*

    The script hash as a hexadecimal string.

**Result**

  Returns :const:`True` if the scripthash was subscribed to, otherwise :const:`False`.
  Note that :const:`False` might be returned even for something subscribed to earlier,
  because the server can drop subscriptions in rare circumstances.

blockchain.transaction.broadcast
================================

Broadcast a transaction to the network.

**Signature**

  .. function:: blockchain.transaction.broadcast(raw_tx)
  .. versionchanged:: 1.1
     errors returned as JSON RPC errors rather than as a result.

  *raw_tx*

    The raw transaction as a hexadecimal string.

**Result**

  The transaction hash as a hexadecimal string.

  **Note** protocol version 1.0 (only) does not respond according to
  the JSON RPC specification if an error occurs.  If the daemon
  rejects the transaction, the result is the error message string from
  the daemon, as if the call were successful.  The client needs to
  determine if an error occurred by comparing the result to the
  expected transaction hash.

**Result Examples**

::

   "a76242fce5753b4212f903ff33ac6fe66f2780f34bdb4b33b175a7815a11a98e"

Protocol version 1.0 returning an error as the result:

::

  "258: txn-mempool-conflict"

blockchain.transaction.get
==========================

Return a raw transaction.

**Signature**

  .. function:: blockchain.transaction.get(tx_hash, verbose=false)
  .. versionchanged:: 1.1
     ignored argument *height* removed
  .. versionchanged:: 1.2
     *verbose* argument added

  *tx_hash*

    The transaction hash as a hexadecimal string.

  *verbose*

    Whether a verbose coin-specific response is required.

**Result**

    If *verbose* is :const:`false`:

       The raw transaction as a hexadecimal string.

    If *verbose* is :const:`true`:

       The result is a coin-specific dictionary -- whatever the coin
       daemon returns when asked for a verbose form of the raw
       transaction.

**Example Results**

When *verbose* is :const:`false`::

  "01000000015bb9142c960a838329694d3fe9ba08c2a6421c5158d8f7044cb7c48006c1b48"
  "4000000006a4730440220229ea5359a63c2b83a713fcc20d8c41b20d48fe639a639d2a824"
  "6a137f29d0fc02201de12de9c056912a4e581a62d12fb5f43ee6c08ed0238c32a1ee76921"
  "3ca8b8b412103bcf9a004f1f7a9a8d8acce7b51c983233d107329ff7c4fb53e44c855dbe1"
  "f6a4feffffff02c6b68200000000001976a9141041fb024bd7a1338ef1959026bbba86006"
  "4fe5f88ac50a8cf00000000001976a91445dac110239a7a3814535c15858b939211f85298"
  "88ac61ee0700"

When *verbose* is :const:`true`::

 {
   "blockhash": "0000000000000000015a4f37ece911e5e3549f988e855548ce7494a0a08b2ad6",
   "blocktime": 1520074861,
   "confirmations": 679,
   "hash": "36a3692a41a8ac60b73f7f41ee23f5c917413e5b2fad9e44b34865bd0d601a3d",
   "hex": "01000000015bb9142c960a838329694d3fe9ba08c2a6421c5158d8f7044cb7c48006c1b484000000006a4730440220229ea5359a63c2b83a713fcc20d8c41b20d48fe639a639d2a8246a137f29d0fc02201de12de9c056912a4e581a62d12fb5f43ee6c08ed0238c32a1ee769213ca8b8b412103bcf9a004f1f7a9a8d8acce7b51c983233d107329ff7c4fb53e44c855dbe1f6a4feffffff02c6b68200000000001976a9141041fb024bd7a1338ef1959026bbba860064fe5f88ac50a8cf00000000001976a91445dac110239a7a3814535c15858b939211f8529888ac61ee0700",
   "locktime": 519777,
   "size": 225,
   "time": 1520074861,
   "txid": "36a3692a41a8ac60b73f7f41ee23f5c917413e5b2fad9e44b34865bd0d601a3d",
   "version": 1,
   "vin": [ {
     "scriptSig": {
       "asm": "30440220229ea5359a63c2b83a713fcc20d8c41b20d48fe639a639d2a8246a137f29d0fc02201de12de9c056912a4e581a62d12fb5f43ee6c08ed0238c32a1ee769213ca8b8b[ALL|FORKID] 03bcf9a004f1f7a9a8d8acce7b51c983233d107329ff7c4fb53e44c855dbe1f6a4",
       "hex": "4730440220229ea5359a63c2b83a713fcc20d8c41b20d48fe639a639d2a8246a137f29d0fc02201de12de9c056912a4e581a62d12fb5f43ee6c08ed0238c32a1ee769213ca8b8b412103bcf9a004f1f7a9a8d8acce7b51c983233d107329ff7c4fb53e44c855dbe1f6a4"
     },
     "sequence": 4294967294,
     "txid": "84b4c10680c4b74c04f7d858511c42a6c208bae93f4d692983830a962c14b95b",
     "vout": 0}],
   "vout": [ { "n": 0,
              "scriptPubKey": { "addresses": [ "12UxrUZ6tyTLoR1rT1N4nuCgS9DDURTJgP"],
                                "asm": "OP_DUP OP_HASH160 1041fb024bd7a1338ef1959026bbba860064fe5f OP_EQUALVERIFY OP_CHECKSIG",
                                "hex": "76a9141041fb024bd7a1338ef1959026bbba860064fe5f88ac",
                                "reqSigs": 1,
                                "type": "pubkeyhash"},
              "value": 0.0856647},
            { "n": 1,
              "scriptPubKey": { "addresses": [ "17NMgYPrguizvpJmB1Sz62ZHeeFydBYbZJ"],
                                "asm": "OP_DUP OP_HASH160 45dac110239a7a3814535c15858b939211f85298 OP_EQUALVERIFY OP_CHECKSIG",
                                "hex": "76a91445dac110239a7a3814535c15858b939211f8529888ac",
                                "reqSigs": 1,
                                "type": "pubkeyhash"},
              "value": 0.1360904}]}

blockchain.transaction.get_merkle
=================================

Return the merkle branch to a confirmed transaction given its hash
and height.

**Signature**

  .. function:: blockchain.transaction.get_merkle(tx_hash, height)

  *tx_hash*

    The transaction hash as a hexadecimal string.

  *height*

    The height at which it was confirmed, an integer.

**Result**

  A dictionary with the following keys:

  * *block_height*

    The height of the block the transaction was confirmed in.

  * *merkle*

    A list of transaction hashes the current hash is paired with,
    recursively, in order to trace up to obtain merkle root of the
    block, deepest pairing first.

  * *pos*

    The 0-based index of the position of the transaction in the
    ordered list of transactions in the block.

**Result Example**

::

  {
    "merkle":
    [
      "713d6c7e6ce7bbea708d61162231eaa8ecb31c4c5dd84f81c20409a90069cb24",
      "03dbaec78d4a52fbaf3c7aa5d3fccd9d8654f323940716ddf5ee2e4bda458fde",
      "e670224b23f156c27993ac3071940c0ff865b812e21e0a162fe7a005d6e57851",
      "369a1619a67c3108a8850118602e3669455c70cdcdb89248b64cc6325575b885",
      "4756688678644dcb27d62931f04013254a62aeee5dec139d1aac9f7b1f318112",
      "7b97e73abc043836fd890555bfce54757d387943a6860e5450525e8e9ab46be5",
      "61505055e8b639b7c64fd58bce6fc5c2378b92e025a02583303f69930091b1c3",
      "27a654ff1895385ac14a574a0415d3bbba9ec23a8774f22ec20d53dd0b5386ff",
      "5312ed87933075e60a9511857d23d460a085f3b6e9e5e565ad2443d223cfccdc",
      "94f60b14a9f106440a197054936e6fb92abbd69d6059b38fdf79b33fc864fca0",
      "2d64851151550e8c4d337f335ee28874401d55b358a66f1bafab2c3e9f48773d"
    ],
    "block_height": 450538,
    "pos": 710
  }


blockchain.transaction.get_tsc_merkle
=====================================

Return the TSC Bitcoin Association merkle proof in standardised format for a confirmed
transaction given its hash and height. Additional options include: txid_or_tx and target_type.

See: https://tsc.bitcoinassociation.net/standards/merkle-proof-standardised-format/

**Signature**

  .. function:: blockchain.transaction.get_tsc_merkle(tx_hash, height, txid_or_tx="txid", target_type="block_hash")

  *tx_hash*

    The transaction hash as a hexadecimal string.

  *height*

    The height at which it was confirmed, an integer.

  *txid_or_tx*

    Takes two possible values: "txid" or "tx".
    Selects whether to return the transaction hash or the full transaction as a hexadecimal string.

  *target_type*

    Takes three possible values: "block_hash", "block_header", "merkle_root"
    The selected target is returned as a hexidecimal string in the response.


**Result**

  A dictionary with the following keys:

  * *composite*

    Included for completeness. Whether or not this is a composite merkle proof (for two or more
    transactions). ElectrumX does not support composite proofs at this time (always False).

  * *index*

    The 0-based position index of the transaction in the block.

  * *nodes*

    The list of hash pairs making up the merkle branch. "Duplicate" hashes (see TSC merkle proof
    format spec.) are replaced with asterixes as they can be derived by the client.

  * *proofType*

    Included for completeness. Specifies the proof type as either 'branch' or 'tree' type.
    ElectrumX only supports 'branch' proof types.

  * *target*

    Either the block_hash, block_header or merkle_root as a hexidecimal string.

  * *targetType*

    Takes three possible values: "block_hash", "block_header", "merkle_root"

  * *txOrId*

    Either a 32 byte tx hash or a full transaction as a hexidecimal string.

**Result Example**

::

    {
        'composite': False,
        'index': 4,
        'nodes': [
            '*',
            '*',
            '80c0100bc080eb0d2e205dc687056dc13c2079d0959c70cad8856fea88c74aba'],
        'proofType': 'branch',
        'target': '29442cb6e2ee547fcf5200dfb1b4018f4fc5ce5a220bb5ec3729a686885692fc',
        'targetType': 'block_hash',
        'txOrId': 'ed5a81e439e1cd9139ddb81da80bfa7cfc31e323aea544ca92a9ee1d84b9fb2f'
    }

blockchain.transaction.id_from_pos
==================================

Return a transaction hash and optionally a merkle proof,
given a block height and a position in the block.

**Signature**

  .. function:: blockchain.transaction.id_from_pos(height, tx_pos, merkle=false)
  .. versionadded:: 1.4

  *height*

    The main chain block height, a non-negative integer.

  *tx_pos*

    A zero-based index of the transaction in the given block, an integer.

  *merkle*

    Whether a merkle proof should also be returned, a boolean.

**Result**

  If *merkle* is :const:`false`, the transaction hash as a hexadecimal string.
  If :const:`true`, a dictionary with the following keys:

  * *tx_hash*

    The transaction hash as a hexadecimal string.

  * *merkle*

    A list of transaction hashes the current hash is paired with,
    recursively, in order to trace up to obtain merkle root of the
    block, deepest pairing first.

**Example Results**

When *merkle* is :const:`false`::

  "fc12dfcb4723715a456c6984e298e00c479706067da81be969e8085544b0ba08"

When *merkle* is :const:`true`::

  {
    "tx_hash": "fc12dfcb4723715a456c6984e298e00c479706067da81be969e8085544b0ba08",
    "merkle":
    [
      "928c4275dfd6270349e76aa5a49b355eefeb9e31ffbe95dd75fed81d219a23f8",
      "5f35bfb3d5ef2ba19e105dcd976928e675945b9b82d98a93d71cbad0e714d04e",
      "f136bcffeeed8844d54f90fc3ce79ce827cd8f019cf1d18470f72e4680f99207",
      "6539b8ab33cedf98c31d4e5addfe40995ff96c4ea5257620dfbf86b34ce005ab",
      "7ecc598708186b0b5bd10404f5aeb8a1a35fd91d1febbb2aac2d018954885b1e",
      "a263aae6c470b9cde03b90675998ff6116f3132163911fafbeeb7843095d3b41",
      "c203983baffe527edb4da836bc46e3607b9a36fa2c6cb60c1027f0964d971b29",
      "306d89790df94c4632d652d142207f53746729a7809caa1c294b895a76ce34a9",
      "c0b4eff21eea5e7974fe93c62b5aab51ed8f8d3adad4583c7a84a98f9e428f04",
      "f0bd9d2d4c4cf00a1dd7ab3b48bbbb4218477313591284dcc2d7ca0aaa444e8d",
      "503d3349648b985c1b571f59059e4da55a57b0163b08cc50379d73be80c4c8f3"
    ]
  }

mempool.get_fee_histogram
=========================

Return a histogram of the fee rates paid by transactions in the memory
pool, weighted by transaction size.

**Signature**

  .. function:: mempool.get_fee_histogram()
  .. versionadded:: 1.2
  .. deprecated:: 1.4.2

**Result**

  The histogram is an array of [*fee*, *vsize*] pairs, where |vsize_n|
  is the cumulative virtual size of mempool transactions with a fee rate
  in the interval [|fee_n1|, |fee_n|], and |fee_n1| > |fee_n|.

  .. |vsize_n| replace:: vsize\ :sub:`n`
  .. |fee_n| replace:: fee\ :sub:`n`
  .. |fee_n1| replace:: fee\ :sub:`n-1`

  Fee intervals may have variable size.  The choice of appropriate
  intervals is currently not part of the protocol.

**Example Result**

  ::

    [[12, 128812], [4, 92524], [2, 6478638], [1, 22890421]]


server.add_peer
===============

A newly-started server uses this call to get itself into other servers'
peers lists.  It should not be used by wallet clients.

**Signature**

  .. function:: server.add_peer(features)

  .. versionadded:: 1.1

  * *features*

    The same information that a call to the sender's
    :func:`server.features` RPC call would return.

**Result**

  A boolean indicating whether the request was tentatively accepted.
  The requesting server will appear in :func:`server.peers.subscribe`
  when further sanity checks complete successfully.


server.banner
=============

Return a banner to be shown in the Electrum console.

**Signature**

  .. function:: server.banner()

**Result**

  A string.

**Example Result**

  ::

     "Welcome to Electrum!"


server.donation_address
=======================

Return a server donation address.

**Signature**

  .. function:: server.donation_address()

**Result**

  A string.

**Example Result**

  ::

     "1BWwXJH3q6PRsizBkSGm2Uw4Sz1urZ5sCj"


server.features
===============

Return a list of features and services supported by the server.

**Signature**

  .. function:: server.features()

**Result**

  A dictionary of keys and values.  Each key represents a feature or
  service of the server, and the value gives additional information.

  The following features MUST be reported by the server.  Additional
  key-value pairs may be returned.

  * *hosts*

    A dictionary, keyed by host name, that this server can be reached
    at.  Normally this will only have a single entry; other entries
    can be used in case there are other connection routes (e.g. Tor).

    The value for a host is itself a dictionary, with the following
    optional keys:

    * *ssl_port*

      An integer.  Omit or set to :const:`null` if SSL connectivity
      is not provided.

    * *tcp_port*

      An integer.  Omit or set to :const:`null` if TCP connectivity is
      not provided.

    A server should ignore information provided about any host other
    than the one it connected to.

  * *genesis_hash*

    The hash of the genesis block.  This is used to detect if a peer
    is connected to one serving a different network.

  * *hash_function*

    The hash function the server uses for :ref:`script hashing
    <script hashes>`.  The client must use this function to hash
    pay-to-scripts to produce script hashes to send to the server.
    The default is "sha256".  "sha256" is currently the only
    acceptable value.

  * *server_version*

    A string that identifies the server software.  Should be the same
    as the first element of the result to the :func:`server.version` RPC call.

  * *protocol_max*
  * *protocol_min*

    Strings that are the minimum and maximum Electrum protocol
    versions this server speaks.  Example: "1.1".

  * *protocol_bad*

    A list of protocol version strings that are not supported

  * *pruning*

    An integer, the pruning limit.  Omit or set to :const:`null` if
    there is no pruning limit.  Should be the same as what would
    suffix the letter ``p`` in the IRC real name.

**Example Result**

::

  {
      "genesis_hash": "000000000933ea01ad0ee984209779baaec3ced90fa3f408719526f8d77f4943",
      "hosts": {"14.3.140.101": {"tcp_port": 51001, "ssl_port": 51002}},
      "protocol_max": "1.0",
      "protocol_min": "1.0",
      "pruning": null,
      "server_version": "ElectrumX 1.0.17",
      "hash_function": "sha256"
  }


server.peers.subscribe
======================

Return a list of peer servers.  Despite the name this is not a
subscription and the server must send no notifications.

**Signature**

  .. function:: server.peers.subscribe()

**Result**

  An array of peer servers, each returned as a 3-element array.  For
  example::

    ["107.150.45.210",
     "e.anonyhost.org",
     ["v1.0", "p10000", "t", "s995"]]

  The first element is the IP address, the second is the host name
  (which might also be an IP address), and the third is a list of
  server features.  Each feature and starts with a letter.  'v'
  indicates the server maximum protocol version, 'p' its pruning limit
  and is omitted if it does not prune, 't' is the TCP port number, and
  's' is the SSL port number.  If a port is not given for 's' or 't'
  the default port for the coin network is implied.  If 's' or 't' is
  missing then the server does not support that transport.

server.ping
===========

Ping the server to ensure it is responding, and to keep the session
alive.  The server may disconnect clients that have sent no requests
for roughly 10 minutes.

**Signature**

  .. function:: server.ping()
  .. versionadded:: 1.2

**Result**

  Returns :const:`null`.

server.version
==============

Identify the client to the server and negotiate the protocol version.
Only the first :func:`server.version` message is accepted.

**Signature**

  .. function:: server.version(client_name="", protocol_version="1.4")

  * *client_name*

    A string identifying the connecting client software.

  * *protocol_version*

    An array ``[protocol_min, protocol_max]``, each of which is a
    string.  If ``protocol_min`` and ``protocol_max`` are the same,
    they can be passed as a single string rather than as an array of
    two strings, as for the default value.

  The server should use the highest protocol version both support::

    version = min(client.protocol_max, server.protocol_max)

  If this is below the value::

    max(client.protocol_min, server.protocol_min)

  then there is no protocol version in common and the server must
  close the connection.  Otherwise it should send a response
  appropriate for that protocol version.

**Result**

  An array of 2 strings:

     ``[server_software_version, protocol_version]``

  identifying the server and the protocol version that will be used
  for future communication.

**Example**::

  server.version("Electrum 3.0.6", ["1.1", "1.2"])

**Example Result**::

  ["ElectrumX 1.2.1", "1.2"]

