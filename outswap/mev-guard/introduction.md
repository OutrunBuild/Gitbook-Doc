# Introduction

The dark forest always harbors tempting wealth. **MEV (Maximal Extractable Value)** extracts value from users on a first-come, first-served basis. AMM (Automated Market Maker) is the most direct link in the MEV extraction process. Due to the permissionless visibility of the mempool, DEX users are inevitably exposed to the risk of being attacked by MEV bots. At the same time, arbitrage bots play a crucial role in improving the price discovery efficiency of AMMs and the market. Before delving into the **MEV Guard** module, let's first briefly introduce the two most common types of MEV attacks on AMMs.

***

### **Initial Liquidity Front-Running Attack**

In the traditional token listing process, the project party or fundraising platform usually directly deploys the liquidity pool on a Decentralized Exchange (DEX). However, this actually creates a major market vulnerability. Some professional quantitative trading bots or malicious project parties can conduct a “**Front-Running Attack**” to sweep up a large number of tokens in the same block as the initial liquidity deployment. As a result, the majority of the token supply in the early liquidity pool is often cornered by a few individuals, resulting in a distorted holding structure.

These market imbalances trigger multiple negative effects:

* Manipulators use high-frequency trading strategies to create false liquidity on secondary markets, deceiving retail investors into buying.
* Front-runners employ programmatic selling strategies to exert continuous selling pressure, keeping token prices depressed long-term.
* Malicious market-making not only undermines a project’s valuation base but also sparks community trust crises, prompting panic selling by token holders.

LBP (Liquidity Bootstrapping Pool) is a solution historically introduced to address "front-running" issues. Its key features are as follows:

* **Flexible Liquidity Pool Composition** : The project team can create a liquidity pool with a ratio of 1:5, 1:10, or even smaller between tokens and fundraising currencies, instead of the conventional 1:1 ratio. This reduces the cost for project teams to provide initial liquidity.
* **Unique Pricing Mechanism**: LBP uses a Dutch - auction - style pricing mechanism. The issuance price starts at the highest point in the price range and decreases over time. This allows users to buy tokens when they think the price is right, without worrying about being front - run by bots.
* **Price Discovery Function**: The changing issuance price leads to price competition among buyers. Token purchases temporarily boost the token price, facilitating price discovery.

At first glance, LBP seems like an ideal solution. But this is only from the project team's perspective. For retail investors, LBP can become **the most ruthless** exploitation tool:

* **Overvalued Project**: In LBP, prices fluctuate with market forces and weightings. Retail investors, lacking professional knowledge and deep research, are prone to overestimating a project’s value due to market sentiment and the project team’s promotion.
* **Price Manipulation Risk**: Project teams can artificially slow the price decline by purchasing tokens internally during LBP. Given LBP’s time limit, token prices can be kept artificially high.
* **Rug Pull Risk**: Project teams can launch tokens with a very high FDV without preparing much initial liquidity, raise significant funds, and then disappear or abandon the project after fundraising. Meanwhile, immediately after the LBP ends, there will be no investors buying the token in the short term. Why? **Because if they were going to buy the token after the LBP ends, why wouldn’t they have bought it earlier during the LBP period?** Investors’ purchasing power is already exhausted during the LBP. Under the dual pressure of rug pull risks and the absence of subsequent buyers, the only fate awaiting investors is a token crash or even a complete wipeout (which is very common).

In fact, we can easily look up historical price data for project tokens launched through LBPs (Liquidity Bootstrapping Pools). This data shows that after the LBP ends, the vast majority of token prices quickly fall below their issuance price and continue to decline. During the 2021 bull market, there were even a large number of "air projects" that raised tens of millions, or even hundreds of millions, of dollars solely through community LBP fundraising. This doesn’t even include the selling pressure from the token shares held by project teams and VCs. After raising funds, most of these project teams essentially disappeared from public view.

LBP (Liquidity Bootstrapping Pool) does indeed address the issue of "frontrunning attacks," but in reality, it merely shifts the profits that would have gone to frontrunning bots to the project team. Worse still, if the project team itself was the original frontrunner, then LBP solves nothing at all, and retail investors gain no benefits or fairness from it. **Therefore, this is absolutely a wrong solution**.

***

### **Sandwich Attack**

A Sandwich Attack is one of the most common attack methods in MEV. It involves both front-running and back-running, where the attacker inserts their own transactions before and after a target transaction within the same block, creating a "sandwich" to profit from price fluctuations.

Attack Steps：

1. **Detecting the Target Transaction**: The attacker monitors the unconfirmed transaction pool (mempool) to identify large transactions or those likely to cause price slippage, such as a significant token swap transaction.
2. **Front-Running Transaction**: The attacker inserts a transaction before the target transaction, typically buying a large amount of the target token to drive up its price.
3. **Execution of the Target Transaction**: The target transaction is executed at the inflated price, resulting in the victim receiving fewer tokens due to price slippage.
4. **Back-Running Transaction**: The attacker inserts another transaction after the target transaction, selling the previously purchased tokens at the higher price to secure a profit.

Current Market Solutions to Sandwich Attacks：

The primary solutions available in the market to address sandwich attacks are as follows:

* **Private Transaction Submission**: Using private RPC endpoints, such as Flashbots, transactions are kept hidden from the public mempool, reducing information leakage and thereby lowering the risk of being attacked. However, **this approach requires users to manually set up private RPC nodes or use special methods to bribe validator nodes, resulting in a high barrier to entry**.
* **Batch Bundling Mechanism**: Some aggregated trading platforms employ this mechanism, where transactions are matched by solvers, bundled together, and executed collectively by the solver. However, **this method involves off-chain matching of aggregated transactions and is not an inherent feature of Automated Market Makers (AMMs), making it inapplicable to certain exchanges**.
* **Segmented Order Strategy**: For example, the Time-Weighted Average Price (TWAP) strategy breaks a large transaction order into multiple smaller orders and executes them evenly over a set time period to reduce slippage. This forces attackers to intervene over a longer timeframe and across more transaction points, increasing the complexity and cost of the attack. However, **this solution is limited in its use cases and is not suitable for everyday fast-paced trading**.

These solutions tackle sandwich attacks on various levels, maintaining market fairness and security to a certain degree. However, they all come with specific limitations and introduce numerous external systems, lacking simplicity and exhibiting high complexity. **We need an innovative, adequately concise solution at the smart contract level**.
