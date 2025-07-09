---
description: Omnichain Stablecoin
---

# UPT

## **As Principal Token**

**UPT** is an innovative **omnichain universal principal token** designed to solve the long-standing problem of liquidity fragmentation in the DeFi space. Unlike traditional principal tokens (PTs), where each yield-bearing token corresponds to a single PT, **UPT is backed by multiple yield-bearing tokens that share the same underlying asset**.

### **Underlying Mechanism**

1. **Staking:** Users stake their **SY tokens** and enable **UPT mode**.
2. **Minting:** After staking, **transferable SP tokens** will be minted 1:1 based on the value of the SY token relative to its accounting asset. For example, if 1 SY-wstETH = 1.1 ETH, staking 1 SY-wstETH will mint 1.1 SP-wstETH.
3. **Splitting:** At this point, the split quantity of UPT differs from the standard PT mode and is also related to the **staking duration (i.e., the amount of YT minted)**. This operation will render the original SP non-transferable but will not destroy it, allowing it to remain trackable. The specific calculation method is as follows:

<p align="center"><span class="math">\text{PT Quantity} = \text{SY Accounting Value} - (\text{YT Quantity} \times \text{YT Redeemable Value})</span></p>

1. **Synthesizing:** Users retain the right to burn their **UPT** at any time. This action will synthesize the UPT with the non-transferable SP back into the original transferable SP.

For example:

* When staking Ethereum Liquid Staking Tokens (LSTs) like **Stone**, **wstETH**, or **BETH**, users can choose to mint **UETH**.
* When staking yield-bearing stablecoins such as **sUSDe**, **sUSDS**, or **USDY**, users can opt to mint **UUSD**.

The core advantage of this mechanism is that it enables **liquidity to be shared across different yield-bearing tokens that are based on the same underlying asset**. This significantly enhances the liquidity of similar yield-bearing tokens and greatly boosts their composability and network effects.

### **Solving Liquidity Fragmentation**

For example, in the current Ethereum ecosystem, there are numerous Liquid Staking Tokens (LSTs) such as stETH, rETH, cbETH, etc., each with its own independent liquidity, leading to liquidity fragmentation across different liquidity pools. This not only results in insufficient liquidity for many emerging LSTs but also means that each LST must repeatedly invest significant resources to incentivize and build liquidity, a process that is both challenging and inefficient.

As UPT, UETH can fundamentally resolve this issue. It integrates the liquidity of various LSTs by creating a central liquidity hub.

**Operating Mechanism:** Suppose there is an emerging LST in the market, named xETH. The project team no longer needs to painstakingly build liquidity for xETH; instead, by integrating into the Outrun ecosystem, xETH can instantly connect to the existing liquidity in the market through UETH.

**Core Advantage:** Through this mechanism, xETH’s liquidity is seamlessly connected to the main liquidity scenarios of UETH (such as `UETH/ETH`, `UETH/UUSD`, or other UETH use cases). This means there is no need to build liquidity separately for each LST; instead, a deeper UETH liquidity pool is collectively maintained.

**Network Effect:** As more market-validated LSTs join the UETH support list, the overall liquidity of UETH will continue to strengthen, forming a powerful network effect. This not only provides instant and deep liquidity for all participating LSTs but also greatly lowers the entry barrier for new LSTs into the market, ultimately benefiting the entire DeFi ecosystem.

### **Strict Auditing Mechanism**

It's important to note that not all yield-bearing assets backed by the same underlying asset can be used to mint UPT. To ensure the robustness and security of the entire ecosystem, OutStake puts potential yield-bearing assets through a series of **strict audits**. These assessments consider crucial factors like **security, stability, and decentralization**

## **As Stablecoin**

UPT is more than just an innovative omnichain universal principal token; it also functions as the Outrun ecosystem's **omnichain stablecoin**, aiming to be a cornerstone of the DeFi landscape. Currently, UPT is available in two main versions: **UUSD** and **UETH**, both fully backed by **yield-bearing USD and ETH assets**, respectively. The plan is to expand to include stablecoins for even more asset types in the future.

Through UPT, users can unlock the liquidity of yield-bearing assets while **retaining fixed yield (holding non-transferable SP)**, without relying on third-party lending protocols or paying borrowing interest.

UPT carries the crucial mission of driving the expansion of the Outrun ecosystem. As the ecosystem evolves, UPT will be continuously **integrated into various DeFi protocols and internal Outrun modules**, providing a stable value foundation for diverse financial activities like **lending**, **trading**, and **derivatives**.

By offering reliable value pegging, UPT significantly simplifies user participation in these activities, thereby powerfully fueling the diversified development and prosperity of the Outrun ecosystem.

## Omnichain Standard

**UPT** is built on **LayerZero**'s OFT (Omnichain Fungible Token) standard, making it an omnichain token. This allows for **seamless transfer across different blockchain networks**, significantly boosting its **utility**, **liquidity**, and **network effects**. This feature enables the Outrun ecosystem to connect more effectively with other blockchain networks, expanding its influence and application scope.
