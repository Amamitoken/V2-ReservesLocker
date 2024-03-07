
![icons8-hare-64](https://github.com/Amamitoken/V2-ReservesLocker/assets/162604718/b0c9c7dc-7561-44df-aad6-22ac59203e50)

# Lock Contract Overview

The lock contract serves as a mechanism to lock liquidity tokens acquired from Uniswap V2 for a specific period, ensuring safety and preventing premature withdrawal. Additionally, it offers the capability to lock team reserves in a similar manner. Here's how it works:

## Locking Liquidity Tokens

- **Set Uniswap V2 Pair**: The contract allows setting a Uniswap V2 pair for the token, enabling the locking of liquidity tokens associated with this pair.

- **Lock Liquidity Tokens**: Once the Uniswap V2 pair is set, liquidity tokens can be locked in the contract for a predetermined period, in our case: 180 days (6 months).

- **Non-Revocable Lock**: Once locked, liquidity tokens cannot be withdrawn by any party until the lock period expires, not even the contract owner.

## Locking Team Reserves

- **Locking Mechanism**: A portion (10%) of the total supply, allocated for the team, will also be locked using the same mechanism as liquidity tokens. This for a time period of 30 days initially. This lock feature will work in a similar locking process as its liquidity tokens variant, ensuring these reserves remain untouched for the specified duration.

## Smart Contract Structure

- `setUniswapV2Pair(address _pair)`: Sets the Uniswap V2 pair for the token.
  
- `lockLiquidityTokens(uint256 _amount)`: Locks the specified amount of liquidity tokens in the contract.
  
- `lockTeamReserves(uint256 _amount)`: Locks the specified amount of team reserves.
  
- `withdrawLiquidityTokens()`: Allows withdrawal of locked liquidity tokens after the lock period expires.
  
- `withdrawTeamReserves()`: Allows withdrawal of locked team reserves after the lock period expires.
