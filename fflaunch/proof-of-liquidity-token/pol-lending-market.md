# POL Lending Market

To better understand the **POL lending market**, we first need to clarify the definitions of **POL** and **UPT**:

* **POL (Proof of Liquidity Token):** This serves as a credential for investors participating in **FFLaunch** or **Memeverse**, **representing their share in the locked genesis liquidity**. It comprises both **UPT** and **paired token** (either a project token or a Memecoin). Once the liquidity lock-up period ends, POL holders can redeem the underlying genesis liquidity by burning their POL tokens, thereby obtaining a corresponding amount of UPT and the paired token. The exact quantities are determined by the liquidity pool's composition at the time of redemption.
* **UPT (Universal Principal Token):** UPT is an innovative, **omnichain universal principal token**. It is backed by multiple interest-bearing tokens that share the same underlying assets, effectively functioning as an **omnichain stablecoin**.

### Function and Purpose of the POL Lending Market

The POL lending market is a **UPT lending market** that uses **POL tokens as collateral**. It's supported by various modules within the Outrun ecosystem. Its primary goal is to offer a **faster liquidity release mechanism** compared to simply trading POL itself. After participating in FFLaunch or Memeverse genesis, users can quickly **collateralize their POL tokens to borrow UPT**, thereby unlocking POL's liquidity while still retaining their POL rights and benefits.

### Why POL Can Be Used as Collateral？

POL tokens are suitable as collateral due to their strong value backing.

POL's value is supported by the **paired token** and **UPT** within its liquidity pool. **Every POL token functions similarly to an LP token in a constant product AMM model**. Therefore, during the **liquidity protection period**, burning POL tokens allows for the redemption of UPT equivalent to at least the initial amount of UPT in the genesis liquidity pool. This is precisely why FFLaunch is referred to as a "**risk-free**" LaunchPad.

This means that **even if the value of the project token or Memecoin drops to zero, users can still redeem their initial UPT**. This inherent value support disregards the price fluctuations of the paired token, thereby **preventing bad debt** within the POL lending market.

### Liquidation Mechanism

The POL lending market theoretically has no liquidation mechanism because, due to the unique design of POL tokens, user positions won't be force-liquidated due to token price fluctuations. However, to ensure the overall system's security, lending positions do have a time limit. The maximum duration is the POL's liquidity lock-up period, meaning users must repay their loans by no later than the liquidity unlock (i.e., before the liquidity protection period). Failure to do so will trigger liquidation:

* The collateralized **POL tokens will be burned** to redeem the genesis liquidity (i.e., initial **UPT** and paired tokens).
* The **redeemed funds are used to repay the borrowed UPT**.
* Any **remaining funds will be sent to the collateralized borrower**.
* **Liquidation bots will collect a portion of the fees** from this process.

This mechanism ensures the orderly operation of the lending market, prevents bad debt, and maintains the stability of the ecosystem.

### Loan Provider

The exact choice of loan provider is still under discussion and will be finalized before the official launch. Currently, there are two main possibilities:

* **Outrun Protocol Directly Issuing New UPT:** Similar to how MakerDAO mints DAI, Outrun could issue new UPT for lending. This approach could lead to **higher direct revenue** for the protocol.
* **Other UPT Holders Providing Loans (Preferred Option):** Existing UPT holders could supply their UPT to borrowers and earn interest. While this option might result in slightly **lower direct protocol revenue**, it's potentially better because it can build **greater user trust, stronger network effects, and enhance UPT stability**.

### Leverage Instrument

Building on the foundation of the POL lending market, we've created a specialized **option instrument**. This allows users to add **extra leverage** when participating in FFLaunch and Memeverse genesis events.

#### **How It Works**

When participating in a genesis event, users can opt to borrow **UPT** for a fixed term, which aligns with the liquidity lock-up period of the project they're involved with. They only need to pay the **interest** on this loan.

When liquidity unlocks (users can also repay early to redeem their locked POL tokens before this), users can choose to close their position. This will burn the locked POL tokens, the redeemed funds are then used to repay the borrowed UPT, with **any remaining tokens becoming profit**. Even in the most extreme scenarios, users will **only lose the interest paid**, while their potential gains are unlimited.

For example:

A user pays **100 UUSD in interest** and borrows **1,000 UUSD** to participate in an FFLaunch genesis. The **1,000 POL tokens** they receive are locked, representing an initial liquidity of "**1,000 UUSD + 1,000 paired tokens**."

One year later, the liquidity unlocks. At this point, the **1,000 POL tokens** represent "**1,250 UUSD + 800 paired tokens**." The user chooses to close their position. After repaying the **1,000 UUSD debt**, they are left with a profit of "**250 UUSD + 800 paired tokens**," while their only cost was the **100 UUSD in interest**.

Even in the most extreme scenario, if the project fails, the **1,000 POL tokens** would still represent "**1,000 UUSD + 1,000 paired tokens**" when liquidity unlocks. After closing the position and repaying the debt, the user would still have **1,000 paired tokens** remaining. If these **1,000 paired tokens** have no liquidity and cannot be sold (i.e., **their value is 0**), the user would only lose the **100 UUSD in interest**.

### Summary

The POL lending market is profoundly significant for the Outrun ecosystem. It represents a **maximal enhancement of capital efficiency**, which will bring stronger **liquidity** and **network effects** to the Outrun ecosystem. As the POL lending market matures, **UPT adoption** will increase significantly, ultimately building a robust **moat** for the Outrun ecosystem.
