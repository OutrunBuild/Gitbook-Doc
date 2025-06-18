# Event lifecycle

Compared to FFLaunch events, the lifecycle of Memeverse events is simpler, involving only 2 entities and 4 stages.

#### Entities

1. Investors
2. Creator

#### Stages

Starting from the **genesis stage**, each stage transition of **Memeverse** requires manually calling the **changeStage** method of the **MemeverseLauncher** contract.

**1. Preparation Stage**

* Creators input relevant information as prompted on the **website UI** of Memeverse to set all the rules for the genesis of Memeverse, select the blockchains (either a single one or multiple ones) for the genesis. After paying the cross-chain verification fee and the gas fee for transactions on the target chain and sending the transaction, they wait for the verification nodes to confirm and complete the registration across all chains. Once the registration is completed, they can enter the genesis stage.
* It should be noted that the registered symbol will be locked before the end of the **liquidity lock-up stage** or before it is **deregistered** and cannot be registered again.

**2. Genesis Stage**

* During the genesis stage of Memeverse, users can participate in the genesis on any chain where the Memeverse is located and deploy liquidity for that chain. If the Memeverse conducts the genesis on multiple chains, there will be a maximum funding participation limit for each chain.
* Users can deposit [**UPT**](../outstake/yield-tokenization/upt.md) into the designated Memeverse. The MemeverseLauncher will record the GenesisFund deposited by each investor. **1/5** of the GenesisFund is the **liquidProofFunds**, and **3/5** is the **memecoinFunds**, which will be added to the **totalMemecoinFunds** and **totalLiquidProofFunds** respectively. The remaining 1/5 will directly enter the Memecoin DAO treasury during the liquidity locking stage.
* To prevent the **excessive occurrence** of Memeverse's genesis and to **ensure sufficient liquidity**, the amount of funds accumulated during the genesis stage on each chain must reach **minTotalFunds** before it can enter the next stage. Otherwise, it will enter the **refund stage**.

**3.1. Refund Stage**

* When the current stage is the genesis stage and the block time is greater than the endTime of Memeverse, anyone can call the changeStage method to conduct stage transition. If the genesis funds accumulated on the current chain are **less than minTotalFunds**, it will enter the refund stage. If this Memeverse enters the refund stage on all chains, the registration center will be called to cancel the registration, and its symbol will re-enter the registrable state.
* During the refund stage, users can redeem all the UPTs they deposited on the current chain during the genesis stage of this Memeverse.

**3.2. Liquidity Locking Stage**

* When the current stage is the genesis stage and the block time is greater than the endTime of Memeverse, anyone can call the changeStage method to conduct stage transition. If the genesis funds accumulated on the current chain are **greater than or equal to minTotalFunds**, it will enter the liquidity lock-up stage. At this time, the contract will mint the corresponding number of Memecoins according to the totalMemecoinFunds in the genesis stage. These Memecoins will form trading pairs with UPTs whose quantity is equal to the totalMemecoinFunds and be deployed on the **OutrunAMM**. The liquidity provider (LP) will be locked until the unlockedTime. Meanwhile, [**POL**](../fflaunch/proof-of-liquidity-token.md) **tokens** with the same quantity as the LP will be minted. **1/6** of the POL tokens will form trading pairs with UPTs whose quantity is equal to the totalLiquidProofFunds and be **locked permanently**. Users can manually claim the remaining **5/6** of the POL tokens. The final 25% of the total Memecoin supply will directly enter the Memecoin DAO treasury (it can be stipulated during registration that, upon successful genesis, the Memecoin in the treasury will immediately be paired with 20% of the genesis funds to add liquidity and mint POL tokens to the treasury).
* During the liquidity locking phase, the UPT portion of the market-making revenue generated from the locked **Memecoin / UPT** genesis liquidity will belong to the **Memecoin DAO treasury**. This provides economic support and incentives for Memecoin community operations. The Memecoin portion of the market-making revenue, on the other hand, will enter the **Memecoin Yield Vault**, offering continuous returns for **Memecoin Staking**.

**4. Liquidity Unlocking Stage**

* When the current stage is the liquidity lock-up stage and the block time is greater than the unlockTime of Memeverse, anyone can call the changeStage method to enter the liquidity unlock stage.
* During the liquidity unlock stage, users can burn POL tokens to redeem the liquidity of the **Memecoin / UPT** trading pair.
* A 24-hour [**Liquidity Protection Period**](../fflaunch/proof-of-liquidity-token.md) is implemented immediately after the block time reaches the unlockTime.&#x20;

**These stages and entities collectively define the complete lifecycle of Memeverse events, ensuring the security, transparency, and compliance of Memecoin throughout the lifecycle**.
