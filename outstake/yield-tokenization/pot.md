---
description: Position Option Token
---

# POT

POT (Position Options Token) represents the right to redeem a position upon maturity. When a user stakes and locks native yield assets, in addition to minting UPT and YT, a POT is also minted to encapsulate the user's position.

POT is supported by the [ERC1155](https://eips.ethereum.org/EIPS/eip-1155) standard and divides the position into shares equal to the number of minted PTs, allowing users to transfer partial redemption rights of a position.

The POT contract records immutable metadata of the position, including the initial amount of staked native yield tokens, constant principal value, number of minted PTs, and the lock-up expiry date. Upon expiration, a fixed amount of POT and UPT can be burned to redeem a fixed amount of native yield token principal, creating different fixed interest rates at different times. By trading POT, users can trade the rights to a fixed interest rate without having to trade UPT itself.
