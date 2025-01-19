---
description: Position Option Token
---

# POT

POT (Position Options Token) represents the right to redeem a position upon maturity. When a user stakes and locks yield-bearing assets, in addition to minting PT and YT, a POT is also minted to encapsulate the user's position.

POT is supported by the [ERC6909](https://eips.ethereum.org/EIPS/eip-6909) standard and divides the position into shares equal to the number of minted PTs, allowing users to transfer partial redemption rights of a position.

The POT contract records immutable metadata of the position, including the **initial amount of staked yield-bearing tokens, constant principal value, number of minted PTs, and the lock-up expiry date**. Upon expiration, **a fixed amount of POT and PT can be burned to redeem a fixed amount of yield-bearing token principal**, creating different fixed interest rates at different times. Therefore, POT can also be regarded as a kind of **interest rate option token**.

By trading POT, one can obtain the right to a fixed interest rate without having to trade PT itself, which **greatly improves capital efficiency**.
