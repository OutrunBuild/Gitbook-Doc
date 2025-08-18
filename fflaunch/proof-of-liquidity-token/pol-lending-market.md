# POL Lending Market

To better understand the Leveraged Genesis Module, we must first clarify the definitions of POL and UPT:

* **POL** (Proof of Liquidity Token): POL serves as a certificate for investors participating in **FFLaunch** or **Memeverse**, representing **their share in the locked genesis liquidity pool**, which consists of **UPT** and **paired token** (project tokens or Memecoins). After the liquidity lock-up period ends, POL holders can burn their POL tokens to redeem the underlying genesis liquidity, receiving a corresponding amount of UPT and paired tokens, determined by the composition of the liquidity pool at the time of redemption. POL tokens can also be split into **PT** and YT, where **the UPT contributed during the genesis phase acts as the principal, and the yield is the total liquidity value redeemed at maturity minus the principal**.
* **UPT** (Universal Principal Token): UPT is an innovative **omnichain universal principal token**, backed by a variety of yield-bearing tokens supported by the same underlying assets. It also functions as an **omnichain stablecoin**.

### **How It Works**

The POL lending market is essentially **a UPT lending market that uses the principal portion (PT) of POL tokens as collateral**, supported collectively by various modules within the Outrun ecosystem. Its primary goal is to provide a **lower-cost, lower-risk, and higher-capital-leverage** method for participating in genesis liquidity pools.

When participating in a genesis event, users can opt to borrow UPT for a **fixed term** (aligned with the liquidity lock-up period of the project) by **paying only interest**. The minted POL tokens are split into PT (principal token) and YT (yield token), with the PT locked in the contract and the YT distributed to the user.

Upon liquidity unlocking and entering the liquidity protection period, the protocol conducts a **global settlement**. This process burns all locked PTs to redeem the genesis principal for debt repayment, with **any remaining tokens allocated as profits to the YT**. Even in the most extreme scenarios, users **only risk losing the paid interest**, while the potential upside remains unlimited.

For example:

A user pays **100 UUSD** in interest to borrow **1000 UUSD** to participate in the FFLaunch Genesis, receiving **1000 POL** tokens, corresponding to an initial liquidity of "**1000 UUSD + 1000 paired tokens**". These **1000 POL** tokens are split into **1000 PT** and **1000 YT**, with all PT locked and all YT sent to the user.&#x20;

One year later, when the liquidity is unlocked (or the user can sell YT before unlocking), the liquidity corresponding to the **1000 POL** tokens is now "**1250 UUSD + 800 paired tokens**". The protocol settles by repaying the **1000 UUSD** debt, leaving a profit of "**250 UUSD + 800 paired tokens**", while the user's cost is only the **100 UUSD** interest.&#x20;

In the worst-case scenario, if the project fails, the liquidity at unlocking remains "**1000 UUSD + 1000 paired tokens**". After settling and repaying the debt, **1000 paired tokens** remain. If these **1000 paired tokens** have no liquidity and cannot be sold (i.e., their value is 0), the user's loss is limited to the **100 UUSD** interest.

### **No Liquidation Risk**

In traditional leveraged trading, price fluctuations may lead to forced liquidation. However, the POL lending market eliminates this risk through the design of POL tokens. Users do not hold specific positions but directly hold YT, so no liquidation is required. Upon entering the liquidity protection period, the protocol automatically conducts a global settlement:

* All pledged PT is burned to redeem the initial UPT principal of the genesis liquidity.
* The redeemed funds are used to repay the borrowed UPT.
* The remaining funds are allocated to YT holders.

### **Lending Provider**

When users borrow through the POL lending market, the Outrun protocol **directly issues new UPT**, similar to a central bank:

* The Outrun protocol issues new UPT for lending, a mechanism akin to MakerDAO’s DAI minting but more efficient, as the collateral assets and borrowed UPT are simultaneously minted and locked. This “dual minting” model maximizes capital efficiency, enabling “**creation from nothing**” while generating direct interest income for the protocol.
* This approach also reduces reliance on external liquidity, as UPT issuance is fully controlled by the Outrun ecosystem, enhancing the system’s autonomy and stability.

### **Strategic Significance**

1.   **Maximized Capital Efficiency**:
   * The POL lending market, through its low-cost leverage mechanism, lowers the entry barrier for users participating in the genesis of the Outrun ecosystem, attracting more users to engage. This not only increases liquidity but also enhances ecosystem stickiness through network effects.
   * The UPT issuance mechanism enables Outrun to directly create capital without external dependencies, akin to a central bank’s currency creation capability, but achieved in a decentralized manner.&#x20;
2. **Increased UPT Adoption**:
   * UPT serves as the core store of value and medium of exchange within the Outrun ecosystem. The POL lending market significantly boosts UPT adoption, creating higher Total Value Locked (TVL). A high adoption rate of UPT strengthens the Outrun ecosystem’s resilience and market competitiveness. As more projects and users choose UPT as their preferred stablecoin, Outrun will form a value network centered around UPT.&#x20;
3. **Building a Moat**:
   * Through the innovative POL token design and liquidation-free lending mechanism, the POL lending market creates a unique value proposition, making Outrun stand out in the highly competitive DeFi market. This differentiated advantage attracts more projects and users, forming a strong network effect. As the use cases and demand for UPT continue to grow, Outrun will establish a self-reinforcing ecosystem that is difficult for competitors to replicate.



