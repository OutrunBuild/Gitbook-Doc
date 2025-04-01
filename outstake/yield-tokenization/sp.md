---
description: Staking Position
---

# SP

SP (Staking Position) represents **the right to redeem the principal of a locked position upon maturity**. Position owners can encapsulate the minted PT (UPT) to create transferable SP, which holders can then sell, effectively enabling an "early redemption" operation indirectly.

SP is supported by the [ERC6909](https://eips.ethereum.org/EIPS/eip-6909) standard, splitting the position into shares equal to the amount of PT minted, allowing users to transfer partial redemption rights of the position.

The SP contract records immutable metadata of the position, including **the initial amount of staked yield-bearing tokens**, **the constant principal value**, **the number of PT minted**, and **the lock-up expiration time**.

Therefore, after the position's lock-up period expires, a fixed portion of SP can be burned to redeem a fixed amount of the principal in yield-bearing tokens, resulting in different fixed yield rates based on market prices and time. **By holding SP, users can earn fixed-rate yield based on the underlying asset**.

Regarding the establishment of an SP trading market, there is a particularly intriguing characteristic, although SP is a token adhering to the ERC6909 standard, **the SP trading market does not require active or aggressive market-making**. This is due to the inherent properties of SP, which endow any SP trading market with features akin to those of an AMM . The primary goal of users trading SP is to secure a fixed yield rate. **At a fixed listed price, this fixed yield rate automatically increases as the lock-up expiration date approaches**. Consequently, **any SP trading market naturally incorporates a price discovery mechanism**. Users will purchase SP tokens at a fixed yield rate time point they deem suitable, thereby establishing the true market value of SP. Provided that the order price of SP does not exceed the value of the principal redeemable at maturity, it is certain to be sold.
