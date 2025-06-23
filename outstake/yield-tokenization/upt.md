---
description: OmniChain Stablecoin
---

# UPT

## **As Principal Token**

**UPT** is an innovative **omnichain universal principal token** designed to solve the long-standing problem of liquidity fragmentation in the DeFi space. Unlike traditional principal tokens (PTs), where each yield-bearing token corresponds to a single PT, **UPT is backed by multiple yield-bearing tokens that share the same accounting asset**.

### Underlying Mechanism

1. **Staking:** Users stake their **SY tokens** and enable **UPT mode**.
2. **Minting:** In this mode, the quantity of **SP (Staking Position) tokens** minted differs from the standard PT mode, it's also related to the staking duration (i.e., the quantity of YT minted). The specific calculation is as follows:

<p align="center"><span class="math">\text{SP Quantity} = \text{SY Accounting Value} - (\text{YT Quantity} \times \text{YT Redeemable Value})</span></p>

3. **Splitting:** Users can split their **SP tokens** 1:1 into **UPT**. The frontend will automatically execute this operation. This action makes the original SP non-transferable but does not destroy it, allowing it to still be tracked.
4. **Synthesizing:** Users retain the right to burn their **UPT** at any time. This action will synthesize the UPT with the non-transferable SP back into the original transferable SP.

For example:

* When staking Ethereum Liquid Staking Tokens (LSTs) like **Stone**, **wstETH**, or **BETH**, users can choose to mint **UETH**.
* When staking yield-bearing stablecoins such as **sUSDe**, **sUSDS**, or **USDY**, users can opt to mint **UUSD**.

The core advantage of this mechanism is that it enables **liquidity to be shared across different yield-bearing tokens that are based on the same accounting asset**. This significantly enhances the liquidity of similar yield-bearing tokens and greatly boosts their composability and network effects.

### **Solving Liquidity Fragmentation**

Take Ethereum, for example. Its ecosystem has a ton of ETH-related Liquid Staking Tokens (LSTs), but their liquidity often gets fragmented. This leaves some LSTs with insufficient liquidity. An LST's liquidity depth is usually tied to how widely it's adopted in DeFi protocols, like the depth of LST/ETH or LST/USDT liquidity pools.

Building liquidity for each LST is a really tough and repetitive process. But **UETH** changes that by **significantly cutting down on these redundant efforts**. Let's say there's an LST with low liquidity, like xETH. With UETH, the market only needs to focus on building **UETH/ETH** or **UETH/USDT** liquidity pools. By staking xETH through OutStake and minting UETH, xETH's liquidity can then **connect to the existing UETH liquidity in the market**. As more rigorously vetted LSTs join the UPT-supported ranks, the overall liquidity will become increasingly abundant.

### **Strict Auditing Mechanism**

It's important to note that not all yield-bearing assets backed by the same underlying asset can be used to mint UPT. To ensure the robustness and security of the entire ecosystem, OutStake puts potential yield-bearing assets through a series of **strict audits**. These assessments consider crucial factors like **security, stability, and decentralization**

## **As Stablecoin**

UPT is more than just an innovative omnichain universal principal token; it also functions as the Outrun ecosystem's **omnichain stablecoin**, aiming to be a cornerstone of the DeFi landscape. Currently, UPT is available in two main versions: **UUSD** and **UETH**, both fully backed by **yield-bearing USD and ETH assets**, respectively. The plan is to expand to include stablecoins for even more asset types in the future.

UPT carries the crucial mission of driving the expansion of the Outrun ecosystem. As the ecosystem evolves, UPT will be continuously **integrated into various DeFi protocols and internal Outrun modules**, providing a stable value foundation for diverse financial activities like **lending**, **trading**, and **derivatives**.

By offering reliable value pegging, UPT significantly simplifies user participation in these activities, thereby powerfully fueling the diversified development and prosperity of the Outrun ecosystem.

## Omnichain Standard

**UPT** is built on **LayerZero**'s OFT (Omnichain Fungible Token) standard, making it an omnichain token. This allows for **seamless transfer across different blockchain networks**, significantly boosting its **utility**, **liquidity**, and **network effects**. This feature enables the Outrun ecosystem to connect more effectively with other blockchain networks, expanding its influence and application scope.
