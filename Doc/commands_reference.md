# Bismuth Native API command reference

This is a documented subset of the commands the nodes currently understand.

*WIP*

# Native Commands

## statusjson
> takes no parameter, returns a dict

Returns a dict with main status info, including protocol and node version, current blockheight, current diff, thread count, uptime, consensus and peer count.  
Preferred way of getting most info over a single call.

Example output:
```
{'threads': 24, 'protocolversion': 'mainnet0016', 'consensus': 562396, 'blocks': 562396, 'connections': 21, 'uptime': 2739, 'testnet': False, 'difficulty': 109.2070139422, 'timeoffset': 0, 'walletversion': '4.2.3.0', 'consensus_percent': 100.0}
```

## diffget
> takes no parameter, returns a list

Returns diff, diff adjusted (for the next block)


## difflast
> takes no parameter, returns a list

Returns [last block_height, last diff]

Example output:
```
[562396, '109.2067509763']
```

## addvalidate
> takes an address, returns a string
*May be deprecated soon or evolve*

return either 'valid' or 'invalid'. Only does a format check.
TODO

## keygen
> takes no parameter, returns a list. May need a few seconds to complete.

Returns a list of ['privkey', 'pubkey', 'address']

Example output:
```
['-----BEGIN RSA PRIVATE KEY-----\nMIIJKAaFC6P3XvqHvISbJy3mrQ05YoSesUA\n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\n-----END RSA PRIVATE KEY-----', '-----BEGIN PUBLIC KEY-----\nMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEAx5I3kl88hpL574pSy7ia\nFC6P3XvqHvISbJy3mrQ05YoSesUAPK9VrCugtv+tGGHlDa8+vVVYkDtchDQJZoYd\nJAV6TRyE1jldeMVh2Y60IZr0GaOcewiPe9FMqZYVm2e11QmcmTIG11RNuSawV+MP\nA8aBW0SXrn73qgyrizZiJ30iqF9NO8TYwM/Vs0miy9GFVcW9WBJgkpcteP7ATTNq\nKjPsTjG8xennZ40z2aqYKLxzy/w4SPn8w9y563rvTIAXtgH0FM3HuCmsFJWh85UQ\nLauctYqIg4Ia6UKJLjt3PRSbaOwcbQz7sS/AXOiujC904/7th0r0YmTqIT4DOy3T\n6jAwy4pfkxTmrRiCbubn3WylWvsmJAqFHVHRyC3b2w8kz8sB2E4X1hNVQh6o5g1X\nDNBxel2nK/FnBirkxGYE8he96eOsq3sB4iu/DlJR2Hsq/OJbdoTQlzVEE+K4OPB/\n8SiNKLYT8AvacfeAbp5WFLdfGP+B6AR7woUqyjtfew4CtOKLlYImceV5vFCnWsjT\nApizLgaTVvRCAr1UnS9V0H704kCuEqCj9/yVOUYzIr57serHnpB4pm/1GpenJj9W\nHj5fwZn6xoFfDZc2FWQXbJ2xMNnhLwMmwo6p5GEuwbx84u1Ft+OW1sS6T4B9bWO0\n5o768MHamvaEG1Nf1BhLOjUCAwEAAQ==\n-----END PUBLIC KEY-----', 'c2cfd9a73ab23266238105d15556798d56b36d92600e64dcc41fece2']
```
*Do NOT ever use this address/keys, info is fake*

## txsend
**WARNING: Must never be used in an open network**
                        
> takes 6 parameters: timestamp, privkey, recipient, amount, operation, data

Constructs a transaction remotely. The private key is transferred to the executing node without encryption, completely unprotected. Inserts transaction into the mempool, returns signature.

## mpinsert
> takes no parameters
 
Inserts transaction or transaction list into the mempool. Transactions need to be preconstructed (signed), same as mempool exchange between nodes. Leads to `mp.MEMPOOL.merge` in **mempool.py**

## addlist
> takes one parameter: address

Returns all transactions where the given address is a sender or recipient.

## listlim
> takes one parameter: list_limit

Returns a number of blocks, starting with the most recent one. The lower bound is set by the `list_limit` parameter. For json-formatted output, use `listlimjson`.

## addlistlim
> takes two parameters: address, limit

Returns all transactions where the given address is a sender or recipient, with a given limit. 

## blockget
> takes a block height (int), returns a list of transactions.

Example output (both txs from block 558742):
```
[
[558742, 1521239985.03, '731337bb0f76463d578626a48367dfea4c6efcfa317604814f875d10', '340c195f768be515488a6efedb958e135150b2ef3e53573a7017ac7d', 6, 'K1iuKwkOac4HSuzEBDxmqb5dOmfXEK98BaWQFHltdrbDd0C5iIEbh/Fj1NLDUycMABA4vxbOFtMzlJ4nVBwcbEVl9NGk6s4yiuF9yQf7AHaloIxV7bcD75UCFg+ZIv7LFxfxz/SJIXzKkdFj+udZkh0sYv5xLNjJZl3YvlbfTnqJvr64wUVCL21Qdg0uSGO3VHM54pQqbePfHldf2+4T2iEjXVDaaIURYunKKnBZvu5VDEeiJQBCNb90RU9sI5QO/pNPVYZgV4lhHQc6kTaxW2DipaiRTdvq2kEo9DsB+4CQJ7vi172nZ+lhk3+MCCe11iJmgLG2nDoRpBlyK3otu822zDKYNkQ2bOuus7Nc1FwGsSI8jjP72xwb0zhyQ8NoelHMnWjh61YYFjbagmiHkepq5if4jfRjMr1PDFU1C6IpeK7a2ZZNSTrKx/sq9uJJygo9RJoxsmh9cqhabxjOeymUh6wpxJ2HDaTp55a517I+JBaxQeNa3GC02RzG2iuJ5SFwB4SrlCv55adKPRzMQaeiy+eukVUouiC3gDeINDZBbHAYT/V+ox+SlXS3Npy9wS/75F3ftYsulMg/acABEoeWP2kEQgQvw5w3B39Hf5IN5jfIJR2Epv0uOVUkgctcE9WBaVOUirWRn3B4FZc/spF0I6IhdV6u7Wjt/A+FaZc=', 'LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0tLS0KTUlJQ0lqQU5CZ2txaGtpRzl3MEJBUUVGQUFPQ0FnOEFNSUlDQ2dLQ0FnRUFrWkxGYTh3dkhHNVo1NVVsVjN5aQp4VEh3UUUxQXhDRHdsMDhpYWdBWDVXMEFObTNCYitQczAyVWQyZWNWbUowN3ZuOWRhY2RORnhwMXNNUTlDSEllCjZ6Tk5maFpPQlRhMGVHUFk1KzRRc0RyN0JwTW8veFo1ajFTRHFRbnM4VkdsSENaWFJnZW5JVGVIcm93cWFPNEcKQjMrSk5tY1k2aEl4ZmNBY0tiU2lnL2NMV0pDbmtwREpwWkxRTHM0SFFrbTdGcVkyNi9TcENGZ0xaenpLdDlTWgpBQlh5SE1GQWdWaDV0L0RIZmsvVW9kaGdnc1hJd0d4TVViR3UvZGwxb3UzQWpQYnFGaExSN1dTL0VSak5JUldhCnZ6NXEyT0NFditOL0tkWmxUZldseVdoWmd3Skp4dTBWNFZ0NHdMeGNJL1AxMWppUVFwWWM2MGJnU0VaQVNiMi8KNzRydU16WlZ5NFhhZHhYV0x6YXBXUVhpSEE4R0t5ZlJra0ZaZFpzdDJIOWJPTUJsMm5pRXJaSkhnRzhYaGcyQQpRNnlBTi9paFBFTC8yVjZTbFNLQWdmN1N6SFZGYXZEVmFVT0ZPdVdoc3V6S1Q2UlAvcFd5ZndtVGxmUWV3d2h0CnhaZ25BTnIwTVVyOUVXanE0S3NDWk9YbDBXaE5XVXZ4QTFlRUdpdG1Jcm00N0hOZnFFUlhBK0M2eURzUlJoaFgKV2pkR1owb3ZzUFI1NjFreGtiVWpYSlhNYmhoemlDSlE2VkgvbEVFZkJ3bWV3SUtmUlIreUxJZG5zRU1CdzkzKwo1RzZMMXo1eUpPbFl0Tm9aaGd4TzBFdlJaR01leXV0dm9meUQ3dHdscjk5d3lBRlA4U1dGSFh4blhFdDZDWlBoCmVQV0V0OUJYL2ZuLzBrUXErVU1NcDBjQ0F3RUFBUT09Ci0tLS0tRU5EIFBVQkxJQyBLRVktLS0tLQ==', '5013e53c9d77bfd9908122a22724eb9e6724ad82f4093173c3f88921', 0.01003, 0, 0, 'odd'], 
[558742, 1521240118.32, 'b54317cb538c6b3a5ae8b84f8b53c83652037038ad8ad6bef4c8b43a', 'b54317cb538c6b3a5ae8b84f8b53c83652037038ad8ad6bef4c8b43a', 0, 'kKIjf9xm8gsQRovQsW/txd0I7BIwUauXKRfasmQ/SNHCIV21+kFSKI5njiyr6Ftnz6XkiV52AqEoI5Lk09Hv7VWUBwRhvo0gHX2ihnhExgQa0Wv2y0qhNvExzvfAHlVm442Smu1FK22ShCyH1xuyEKeZaBeAnUvcnr1BWCYEvz4eUr5baawpEInNjChM6TGbXwQYWV4ui+xqJuBm+t4b8wOx3fNct1yrU9iwycxQmRv8cuQIsKFcr8ZQ55upof3/sGq8Lx6pbqT6DOSeJZR0RuR6kgpEsgQC/upcG+x2PrsVv44g5+USEtB1Md6X3XUhw9E9tk84VE1aSkEL/+0mqx+Pzw34TfzRD3E/LlevysoUIhVq/2gXWZnmswy+faA31rt7jUAWecmOeYcFrICZMthwajMeF0FGCdNlv2SHxnt+LZ6awomgNaUuhipC7UmPst/BnIN1LQCaYraeBv3RqBHZINgK/yCyttfEdlrN8q7mMSeF2XMoPzm/rlCATmdhDXpZ9Q9aWYHwpi9YLlm65+/V3mvj17fhRONYUfGOEb7u9oF0khn0Iuxd3qhy7/oloTzWqAonBxveXKoOVECpJ7DVPJDW3JUrmP92LqXVY6a7aOOJrYvjX85POym0BGd0EcSZZqZ6xfDiDsJ55NqVV1cVO18jV0DiCVCpKbZjJso=', 'LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0tLS0KTUlJQ0lqQU5CZ2txaGtpRzl3MEJBUUVGQUFPQ0FnOEFNSUlDQ2dLQ0FnRUE2VTRhM0xKZ3lOZSs3a25nVHNrbgpHRTVuQUJ2Z1Y5K29uWmY4SlhPRjMyNnJVR0xaUy9GWnVBNXBwK01lNG9NWG5XQlNJNS80STBHaG1WSlNsLzh2ClJiaW5LTUI4Wnc2MkxrWS9hYjV0dHg4bGFPd0VVNDhzQ01xTS9lTFZkazFOQkpiOTN1L1NpRzV4amhreFN1ZVoKdG9xdkJlelloVXNQcWtBNm9ZeHBraThoL1ppaWZnWTI1RDJSYlJmVUQzdjA0eXJHd2lEazFUQ20wbzE2eUIvMwpXZVFMdDdkVVpCWlAvNEtZV0d2a0FyeTN0YS9zK2JqZmlUVkQxK3RONzBNTjJ1R0ZWSlRmZVgwbDgzSDE3YndlCkVFYnQzQ1lCMHV6TkdmWHJwK0JsYXFSeFg4OTdXVzkxZHNCMUpWQlJIZE9HbXI1YkYzT0RFZXpTUVB2THhuakgKdFhOdHZRaG40WGhvbzFiSGRxVng2NXlRS1VJSk5EUnhWWTNsVmx6Tks4M1FzbXVBWFZ2VytTamR3QXVVMm55MApUY0xEVHBMOEtqZXZROVVuZDZPcU4vT0lBU0ZmYms0eVdEM2k2aVREbzFYM2RwUUR5VVJ4M09KbHRZcTRvWjB0CmJRVlVMdUVleEFFQ0RadU9kN3p5ajNXR0RqemtIL3lRR3BXdFhGaVVGZDRrQVhNb3pnMkpKWDU4WkVuWXE2UTAKd09KdjlwRFhnSXBpNnp5SEd0RFdwN0tuWXl5SStNUWxOdmFMcEZROXFDN2EyK3RZdWU5bklxbkJOb0xmSFNZTQpXK1VGZnUreEtkUTFZYXptMWxhalh1Nlp0YWUvVmNWc0tTWEIzdUVnQ0h1YllhUHR2RWhOYjR5L0xSRkJUZENqCnNickEyRFlvRVhZMURsVVhNc0NYd2k4Q0F3RUFBUT09Ci0tLS0tRU5EIFBVQkxJQyBLRVktLS0tLQ==', '5013e53c9d77bfd9908122a22724eb9e6724ad82f4093173c3f88921', 0, 14.451288, 0, '31ae736dddc5f38823fb5b949cef9f95']
]
```

# Extra API_ Commands

This commands are not used by nodes themselves, but are available to third party clients.

## api_ping 
> takes no parameter, returns a string

Does nothing except keep the socket open. API client willing a persistent connection can send an api_ping every 30 sec at most.  
The node will answer with a single string, 'api_pong'.

## api_getaddressinfo
> takes an address, returns a dict

Returns a dict with  
* known: Did that address appear on a transaction?  
* pubkey: The pubkey of the address if it signed a transaction

## api_getblocksince
> takes a block height, returns a list of list

Returns the full blocks and transactions following a given block_height
Returns at most transactions from 10 blocks (the most recent ones if it truncates)

## api_getbalance
> takes a list of addresses, the minimum number of confirmations needed and returns a float.
Even if you want the balance for a single address, you have to ask it as a list [address]

Returns total balance for a list of addresses and minconf  
BEWARE: this is NOT the bitcoind json rpc getbalance (that get balance for an account, not an address)

## api_getreceived
> takes a list of addresses, the minimum number of confirmations needed and returns a float.
Even if you want the received total for a single address, you have to ask it as a list [address]

Returns the total amount *received* for all given address with minconf

## api_listreceived
> takes a list of addresses, the minimum number of confirmations needed and returns a dict of {address: total_received}.
Even if you want the received total for a single address, you have to ask it as a list [address]

Returns the total amount *received* for each given address with minconf

## api_listbalance
> takes a list of addresses, the minimum number of needed confirmations, wether to include empty balances or not, and returns a dict of {address: total_balance}.

Returns the total balance for each given address with minconf.

Example output:
```
{'340c195f768be515488a6efedb958e135150b2ef3e53573a7017ac7d': 1279.8380546001717, '731337bb0f76463d578626a48367dfea4c6efcfa317604814f875d10': 773.8549049999674}
```

## api_gettransaction
> takes a transaction_id, the format to use (false=raw, true=json) and returns a list or dict representing the whole transaction data.

returns the transaction detail for a single transaction id. format is a boolean, returns as json format. if format is false, sends a raw list.

Example output (raw format):
```
[558742, 1521239985.03, '731337bb0f76463d578626a48367dfea4c6efcfa317604814f875d10', '340c195f768be515488a6efedb958e135150b2ef3e53573a7017ac7d', 6, 'K1iuKwkOac4HSuzEBDxmqb5dOmfXEK98BaWQFHltdrbDd0C5iIEbh/Fj1NLDUycMABA4vxbOFtMzlJ4nVBwcbEVl9NGk6s4yiuF9yQf7AHaloIxV7bcD75UCFg+ZIv7LFxfxz/SJIXzKkdFj+udZkh0sYv5xLNjJZl3YvlbfTnqJvr64wUVCL21Qdg0uSGO3VHM54pQqbePfHldf2+4T2iEjXVDaaIURYunKKnBZvu5VDEeiJQBCNb90RU9sI5QO/pNPVYZgV4lhHQc6kTaxW2DipaiRTdvq2kEo9DsB+4CQJ7vi172nZ+lhk3+MCCe11iJmgLG2nDoRpBlyK3otu822zDKYNkQ2bOuus7Nc1FwGsSI8jjP72xwb0zhyQ8NoelHMnWjh61YYFjbagmiHkepq5if4jfRjMr1PDFU1C6IpeK7a2ZZNSTrKx/sq9uJJygo9RJoxsmh9cqhabxjOeymUh6wpxJ2HDaTp55a517I+JBaxQeNa3GC02RzG2iuJ5SFwB4SrlCv55adKPRzMQaeiy+eukVUouiC3gDeINDZBbHAYT/V+ox+SlXS3Npy9wS/75F3ftYsulMg/acABEoeWP2kEQgQvw5w3B39Hf5IN5jfIJR2Epv0uOVUkgctcE9WBaVOUirWRn3B4FZc/spF0I6IhdV6u7Wjt/A+FaZc=', 'LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0tLS0KTUlJQ0lqQU5CZ2txaGtpRzl3MEJBUUVGQUFPQ0FnOEFNSUlDQ2dLQ0FnRUFrWkxGYTh3dkhHNVo1NVVsVjN5aQp4VEh3UUUxQXhDRHdsMDhpYWdBWDVXMEFObTNCYitQczAyVWQyZWNWbUowN3ZuOWRhY2RORnhwMXNNUTlDSEllCjZ6Tk5maFpPQlRhMGVHUFk1KzRRc0RyN0JwTW8veFo1ajFTRHFRbnM4VkdsSENaWFJnZW5JVGVIcm93cWFPNEcKQjMrSk5tY1k2aEl4ZmNBY0tiU2lnL2NMV0pDbmtwREpwWkxRTHM0SFFrbTdGcVkyNi9TcENGZ0xaenpLdDlTWgpBQlh5SE1GQWdWaDV0L0RIZmsvVW9kaGdnc1hJd0d4TVViR3UvZGwxb3UzQWpQYnFGaExSN1dTL0VSak5JUldhCnZ6NXEyT0NFditOL0tkWmxUZldseVdoWmd3Skp4dTBWNFZ0NHdMeGNJL1AxMWppUVFwWWM2MGJnU0VaQVNiMi8KNzRydU16WlZ5NFhhZHhYV0x6YXBXUVhpSEE4R0t5ZlJra0ZaZFpzdDJIOWJPTUJsMm5pRXJaSkhnRzhYaGcyQQpRNnlBTi9paFBFTC8yVjZTbFNLQWdmN1N6SFZGYXZEVmFVT0ZPdVdoc3V6S1Q2UlAvcFd5ZndtVGxmUWV3d2h0CnhaZ25BTnIwTVVyOUVXanE0S3NDWk9YbDBXaE5XVXZ4QTFlRUdpdG1Jcm00N0hOZnFFUlhBK0M2eURzUlJoaFgKV2pkR1owb3ZzUFI1NjFreGtiVWpYSlhNYmhoemlDSlE2VkgvbEVFZkJ3bWV3SUtmUlIreUxJZG5zRU1CdzkzKwo1RzZMMXo1eUpPbFl0Tm9aaGd4TzBFdlJaR01leXV0dm9meUQ3dHdscjk5d3lBRlA4U1dGSFh4blhFdDZDWlBoCmVQV0V0OUJYL2ZuLzBrUXErVU1NcDBjQ0F3RUFBUT09Ci0tLS0tRU5EIFBVQkxJQyBLRVktLS0tLQ==', '5013e53c9d77bfd9908122a22724eb9e6724ad82f4093173c3f88921', 0.01003, 0, 0, 'odd']
```

Example output (json format):
```
{'keep': 0, 'hash': 'K1iuKwkOac4HSuzEBDxmqb5dOmfXEK98BaWQFHltdrbDd0C5iIEbh/Fj1NLDUycMABA4vxbOFtMzlJ4nVBwcbEVl9NGk6s4yiuF9yQf7AHaloIxV7bcD75UCFg+ZIv7LFxfxz/SJIXzKkdFj+udZkh0sYv5xLNjJZl3YvlbfTnqJvr64wUVCL21Qdg0uSGO3VHM54pQqbePfHldf2+4T2iEjXVDaaIURYunKKnBZvu5VDEeiJQBCNb90RU9sI5QO/pNPVYZgV4lhHQc6kTaxW2DipaiRTdvq2kEo9DsB+4CQJ7vi172nZ+lhk3+MCCe11iJmgLG2nDoRpBlyK3otu822zDKYNkQ2bOuus7Nc1FwGsSI8jjP72xwb0zhyQ8NoelHMnWjh61YYFjbagmiHkepq5if4jfRjMr1PDFU1C6IpeK7a2ZZNSTrKx/sq9uJJygo9RJoxsmh9cqhabxjOeymUh6wpxJ2HDaTp55a517I+JBaxQeNa3GC02RzG2iuJ5SFwB4SrlCv55adKPRzMQaeiy+eukVUouiC3gDeINDZBbHAYT/V+ox+SlXS3Npy9wS/75F3ftYsulMg/acABEoeWP2kEQgQvw5w3B39Hf5IN5jfIJR2Epv0uOVUkgctcE9WBaVOUirWRn3B4FZc/spF0I6IhdV6u7Wjt/A+FaZc=', 'time': 1521239985.03, 'fee': 0.01003, 'pubkey': '-----BEGIN PUBLIC KEY-----\nMIICIjANBgkqhkiG9w0BAQEFAAOCAg8AMIICCgKCAgEAkZLFa8wvHG5Z55UlV3yi\nxTHwQE1AxCDwl08iagAX5W0ANm3Bb+Ps02Ud2ecVmJ07vn9dacdNFxp1sMQ9CHIe\n6zNNfhZOBTa0eGPY5+4QsDr7BpMo/xZ5j1SDqQns8VGlHCZXRgenITeHrowqaO4G\nB3+JNmcY6hIxfcAcKbSig/cLWJCnkpDJpZLQLs4HQkm7FqY26/SpCFgLZzzKt9SZ\nABXyHMFAgVh5t/DHfk/UodhggsXIwGxMUbGu/dl1ou3AjPbqFhLR7WS/ERjNIRWa\nvz5q2OCEv+N/KdZlTfWlyWhZgwJJxu0V4Vt4wLxcI/P11jiQQpYc60bgSEZASb2/\n74ruMzZVy4XadxXWLzapWQXiHA8GKyfRkkFZdZst2H9bOMBl2niErZJHgG8Xhg2A\nQ6yAN/ihPEL/2V6SlSKAgf7SzHVFavDVaUOFOuWhsuzKT6RP/pWyfwmTlfQewwht\nxZgnANr0MUr9EWjq4KsCZOXl0WhNWUvxA1eEGitmIrm47HNfqERXA+C6yDsRRhhX\nWjdGZ0ovsPR561kxkbUjXJXMbhhziCJQ6VH/lEEfBwmewIKfRR+yLIdnsEMBw93+\n5G6L1z5yJOlYtNoZhgxO0EvRZGMeyutvofyD7twlr99wyAFP8SWFHXxnXEt6CZPh\nePWEt9BX/fn/0kQq+UMMp0cCAwEAAQ==\n-----END PUBLIC KEY-----', 'amount': 6, 'blockminer': 'b54317cb538c6b3a5ae8b84f8b53c83652037038ad8ad6bef4c8b43a', 'blockhash': '5013e53c9d77bfd9908122a22724eb9e6724ad82f4093173c3f88921', 'address': '731337bb0f76463d578626a48367dfea4c6efcfa317604814f875d10', 'recipient': '340c195f768be515488a6efedb958e135150b2ef3e53573a7017ac7d', 'txid': 'K1iuKwkOac4HSuzEBDxmqb5dOmfXEK98BaWQFHltdrbDd0C5iIEbh/Fj', 'openfield': 'odd', 'blocktime': 1521240118.32, 'reward': 0, 'confirmations': 3654, 'blockheight': 558742}
```

## api_getpeerinfo
> takes no parameter, returns a list

Not stable
