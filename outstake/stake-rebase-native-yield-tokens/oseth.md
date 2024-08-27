# Principal Token (PT)

**PT** is a staking principal token minted by staking **WT**, aimed at unlocking the liquidity of staked tokens.

When users stake **WT**, they need to specify a lock-up period to mint **PT** and **YT**. The quantity of **PT** minted is not on a 1:1 basis with the staked **WT** but is related to the **staking duration or the number of YT minted**. The quantity of **Rebase native yield token** equals the amount of **native tokens convertible** (Native token amount). The specific algorithm is:

<figure><img src="../../.gitbook/assets/latex.png" alt=""><figcaption></figcaption></figure>

**YT Redeemable Value:** The native yield that can be redeemed by burning one **YT**.

Over time, the vault continuously generates native staking yields, and a corresponding amount of **WT** is minted and added to the **YieldPool**, which increases the redeemable value of **YT**. The **PT** minted from newly staked **WT** will slightly decrease, but regardless of the number of **PT** minted, users will be able to redeem their staked **WT** completely by burning the **PT** minted at the end of the lock-up period.
