---
description: Principal Token
---

# PT

**PT (Principal Token)** is a staked principal token minted by staking SY. It's a **liquid staking derivative** that represents the **initial value of SP**, designed to unlock the liquidity of staked assets.

### Underlying Mechanism

1. **Staking:** Users stake their **SY tokens** and select **non-UPT mode**.
2. **Minting:** After staking, **transferable SP tokens** will be minted 1:1 based on the value of the SY token relative to its accounting asset. For example, if 1 SY-wstETH = 1.1 ETH, staking 1 SY-wstETH will mint 1.1 SP-wstETH.
3. **Splitting:** Users can split their **SP tokens** 1:1 into **PT**. The frontend will automatically execute this operation. This action makes the original SP non-transferable but does not destroy it, allowing it to still be tracked.
4. **Synthesizing:** Users retain the right to burn their **PT** at any time. This action will synthesize the PT with the non-transferable SP back into the original transferable SP.

### Important Considerations:

**PT has no expiration date and is a generic ERC20 token. It cannot be directly redeemed for the principal portion of a staked position.** This differs from other protocols in the market. You **must first synthesize PT into a transferable SP**, and then, after the staked position matures, redeem your principal by burning that SP.

**Holding PT alone does not yield fixed interest rate returns.** The yield is associated with **transferable SP**. To obtain this yield, you have two options:

1. Your wallet already contains non-transferable SP, which allows you to synthesize it with PT to form a transferable SP by burning the PT.
2. Directly purchase transferable SP from the market.
