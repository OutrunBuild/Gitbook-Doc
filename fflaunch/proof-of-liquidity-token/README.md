# Proof Of Liquidity Token

**The Proof of Liquidity Token (POL)** is a certificate for investors to participate in FFLaunch, representing their share in the locked Genesis liquidity pool. By participating in FFLaunch, investors can obtain POL, and after the liquidity lock-up period ends, POL holders can redeem the liquidity deposited during the Genesis phase by burning POL.

During the liquidity lock-up period, due to fluctuations in token prices, the value of the liquidity locked by investors will also fluctuate, thereby exposing them to the risk of the project token and increasing their holding opportunity cost. With the introduction of POL, investors can sell POL on the market before the liquidity is unlocked to lock in current profits and reduce holding opportunity costs.

The quantities of the two assets in the liquidity pool are dynamically changing, adjusting with the trades of other users. However, the POL shares held by investors always represent the corresponding proportion of assets in the liquidity pool. Therefore, it is possible to calculate the amount of assets each POL represents, which is the **nominal value** of POL (the actual delivery value is determined at the time of final destruction), based on the total assets of the entire pool and the number of POLs held by investors. The nominal value of POL is positively correlated with the price of its corresponding token, but there is a phenomenon of diminishing marginal rate of change. That is, as the token price rises, the nominal value of POL will also increase, but the increase will gradually decrease; conversely, as the token price falls, the nominal value of POL will also decrease, but the decrease will gradually decrease as well. Therefore, compared to its corresponding token, POL has a smaller price volatility.

### **A Different Perspective on POL Tokens**

POL tokens are essentially **specially packaged LP** tokens, with their value underpinned by the **paired tokens** and **UPT** in the liquidity pool. During the **liquidity protection period**, users can burn POL tokens to redeem at least the initial UPT deposited in the genesis liquidity pool.

This is why FFLaunch is considered a “**risk-free**” LaunchPad: **even if the project token’s price drops to zero, genesis users can still redeem their initially deposited UPT**, shielding them from the price volatility of the paired token.

Upon deeper analysis, POL tokens can be recognized as a form of **yield-bearing asset**, where **the UPT contributed during the genesis stage** serves as the principal, and the yield is the **total liquidity value redeemed at maturity minus the principal**. Consequently, POL tokens can be divided into two components: **PT** (principal token) and **YT** (yield token).&#x20;

Unlike OutStake's original model, FFLaunch's POL tokens have a **uniform expiration date**, eliminating custom lock-up period options, thus simplifying the yield model.

## Liquidity Protection Period

The Liquidity Protection Period is an essential mechanism for safeguarding token liquidity and price stability.

When the block time reaches the unlock time, some POL token holders may **rush to redeem their liquidity and immediately sell the redeemed tokens**. Without a Liquidity Protection Period, this behavior can lead to a gradual decrease in the value of subsequent redemptions, violating the principle of fairness and triggering panic redemptions and sales, which can destabilize the market.

By implementing a 48-hour liquidity protection period after the block time reaches the liquidity unlock time, during which **the genesis liquidity pool cannot perform swap operations but allows adding or removing liquidity**, users can burn POL tokens to redeem corresponding genesis liquidity. This ensures that the value of the liquidity redeemed by burning POL tokens remains consistent within this 48-hour period, providing all users with sufficient time to redeem under equal market conditions, preventing panic-induced stampedes and severe market fluctuations.
