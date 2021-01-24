# SRC-20 example contracts

This is an example on how Scrypta can be used to create an ERC-20 like contract.

## Contract functions

These are the functions you can call directly.

### name

Returns the name of the token:
```
scrypta-contracts test -m=src20.ssc -f=name
```

### symbol
Returns the symbol of the token:
```
scrypta-contracts test -m=src20.ssc -f=symbol
```

### owner
Returns the owner of the token, this is the account able to `mint` new tokens:
```
scrypta-contracts test -m=src20.ssc -f=owner
```

### decimals
Returns the decimals of the token:
```
scrypta-contracts test -m=src20.ssc -f=decimal
```

### consensus
Returns the status of the contract that will be checked to reach consensus:
```
scrypta-contracts test -m=src20.ssc -f=consensus
```

### balanceOf

Ask the balance of an user:
```
scrypta-contracts test -m=src20.ssc -f=balanceOf -p='{"address": "LSJq6a6AMigCiRHGrby4TuHeGirJw2PL5c"}'
```

Ask the balance of actually connected user:
```
scrypta-contracts test -m=src20.ssc -f=balanceOf
```

## This commands must be written directly into the blockchain

However you can test them running eachBlock transaction with thest function.

### mint

This will mint new tokens:
```
scrypta-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "LSJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "mint:10000"}]}}'
```

### burn

This will mint new tokens:
```
scrypta-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "LSJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "burn:10000"}]}}'
```

### transfer

This will transfer tokens between accounts:
```
scrypta-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "LSJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "transfer:Li9BgCWhQrv8LhKD3U5HS47oencDrTDAZb:19.12344"}]}}'
```