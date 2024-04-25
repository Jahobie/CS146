# Coin Change Problem

## Problem Statement

You are given an integer array `coins` representing coins of different denominations and an integer `amount` representing a total amount of money. Return the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.


### Approach

To solve this problem, we can use dynamic programming.

1. We create an array `dp`, where `dp[i]` represents the fewest number of coins needed to make up the amount `i`.
2. We initialize `dp` with infinity values, except for `dp[0]`, which is 0 since we need 0 coins to make up an amount of 0.
3. Then, for each coin denomination, we iterate through the `dp` array and update `dp[i]` if we can make up the amount `i` using the current coin denomination.
4. We take the minimum of the current value of `dp[i]` and `dp[i - coin] + 1`, where `coin` is the denomination of the current coin.
5. Finally, we return `dp[amount]` if it's less than infinity, otherwise, we return -1.

