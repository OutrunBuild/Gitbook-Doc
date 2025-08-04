# Working Principle

**MEV Guard** is a **fully on-chain, standalone native module** that is highly concise and does not require the introduction of external off-chain systems, nor is it a token issuance mechanism like LBP (Liquidity Bootstrapping Pool). By providing early-stage protection to liquidity pools, effectively mitigating the impact of **initial liquidity front-running attacks.**&#x20;

### Addressing **Initial Liquidity Front-Running Attack**

The core feature of an initial liquidity front-running attack (**Sniping**) is the **one-time purchase of a large quantity of tokens within the same block as the initial liquidity deployment**, thereby monopolizing the initial token supply. To counter this key characteristic, MEV Guard’s solution **provides protection for a specific range of blocks following the deployment of the initial liquidity pool**. The details are as follows:

1. **Protection Period Configuration**: Based on the block times of different chains, an initial liquidity protection period is established, lasting for a variable number of blocks, **typically extending over hundreds of blocks**.
2. **Randomness Check**: Introduce a randomness check to **dynamically adjust** the probability based on the number of transactions attempted in the previous block. Transactions that fail the check will be interrupted rather than reverted, ensuring all transactions have an equal opportunity for execution.
3. **Transaction Count Restriction**: Within each block, the current liquidity pool can only process one **executable transaction**, with any subsequent transactions being **interrupted** to reduce the impact of Sybil attacks.
4. **Transaction Size Limitation**: The maximum token amount per transaction must not exceed one percent of the total reserves in the liquidity pool, preventing monopolization of the token supply.
5. **Protection Period Termination**: Upon the conclusion of the initial liquidity protection period, all the aforementioned restrictions are automatically removed.

{% hint style="info" %}
**Interruption Mechanism**: To track the number of attempted transactions (including failed ones) in each block, a failed transaction will not revert but will instead be interrupted, restoring the state to that of the previous swap state (in the case of multi-hop swaps).
{% endhint %}

Through the above measures, MEV front-running attacks can be effectively prevented. No one can predict in advance whether their transaction will be executable, as all transactions during the initial liquidity protection period are subject to uncertainty, and transaction sizes are restricted to prevent monopolization of the token supply.
