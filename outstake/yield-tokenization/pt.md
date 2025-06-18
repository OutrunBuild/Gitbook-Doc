---
description: Principal Token
---

# PT

PT is a staked principal token minted by staking SY, designed to unlock the liquidity of staked tokens. When users stake SY, they must specify a lock-up period to mint PT, YT. The amount of PT is not minted on a 1:1 basis with the staked SY but is instead related to the staking duration (the amount of YT minted) and the **exchange rate** of the Yield-bearing Token to the Underlying Asset Token. Simply put, the amount of the Yield-bearing Token is first converted to the equivalent value of the Underlying Asset Token, and then the following algorithm is applied to calculate it:

<figure><img src="../../.gitbook/assets/latex.png" alt=""><figcaption></figcaption></figure>

**YT Redeemable Value:** The yields that can be redeemed by burning one **YT**.

Therefore, the value of PT is theoretically pegged to the value of the underlying asset token. IIts total supply will always be less than the quantity of underlying asset tokens that the staked yield-bearing tokens can be exchanged for, ensuring that the value of PT does not become decoupled from the value of the underlying asset token.

Over time, as the yield pool continuously accumulates yields, the redeemable value of YT increases. The amount of PT minted from newly staked SY will slightly decrease, but regardless of the number of PT minted, users will be able to burn the PT minted at that time to fully redeem their staked SY upon the lock-up period's expiration.

In general, Yield-bearing Tokens can be roughly classified as follows:

1. Rebase Tokens - Tokens that increase their balance over time.

_Examples: stETH, aUSDC_

2. Reward-bearing Non-Rebase Tokens - Tokens that appreciate in value over time.

_Examples: wstETH, Stone, slisBNB_

**It is important to note**: For reward-bearing non-rebase Yield-bearing Tokens, the quantity of staked Yield-bearing Tokens in the position does not change after the lock-up period expires. However, their value (relative to the Underlying Asset Token's exchange ratio) will increase with the accumulation of yields. Thus, burning PT does not redeem the same quantity of non-rebase Yield-bearing Tokens as initially staked; instead, it will be slightly less because part of the value is attributed to YT.
