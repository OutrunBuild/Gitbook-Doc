# Proof Of Liquidity Token

**The Proof of Liquidity Token (POL)** is a certificate for investors to participate in FFLaunch, representing their share in the locked Genesis liquidity pool. By participating in FFLaunch, investors can obtain POL, and after the liquidity lock-up period ends, POL holders can redeem the liquidity deposited during the Genesis phase by burning POL.

During the liquidity lock-up period, due to fluctuations in token prices, the value of the liquidity locked by investors will also fluctuate, thereby exposing them to the risk of the project token and increasing their holding opportunity cost. With the introduction of POL, investors can sell POL on the market before the liquidity is unlocked to lock in current profits and reduce holding opportunity costs.

The quantities of the two assets in the liquidity pool are dynamically changing, adjusting with the trades of other users. However, the POL shares held by investors always represent the corresponding proportion of assets in the liquidity pool. Therefore, it is possible to calculate the amount of assets each POL represents, which is the **nominal value** of POL (the actual delivery value is determined at the time of final destruction), based on the total assets of the entire pool and the number of POLs held by investors. The nominal value of POL is positively correlated with the price of its corresponding token, but there is a phenomenon of diminishing marginal rate of change. That is, as the token price rises, the nominal value of POL will also increase, but the increase will gradually decrease; conversely, as the token price falls, the nominal value of POL will also decrease, but the decrease will gradually decrease as well. Therefore, compared to its corresponding token, POL has a smaller price volatility.

## **Trading Proof Of Liquidity Token**

At the end of the FFLaunch Genesis phase, **1/3** of the Genesis funds will be paired with **1/4** of the POL to form a trading pair, and investors can claim the remaining **3/4** of the POL. As a result, POL has liquidity equivalent to half of the project token's liquidity, which is more than sufficient for a special token that does not have its own pricing power and whose price is linked to the project token. Investors can trade POL at their own set psychological price, or they can arbitrage using the difference between the market price and the nominal value of POL.

## Liquidity Protection Period

The Liquidity Protection Period is an essential mechanism for safeguarding token liquidity and price stability.&#x20;

When the block time reaches the unlock time, some POL token holders may **rush to redeem their liquidity and immediately sell the redeemed tokens**. Without a Liquidity Protection Period, this behavior can lead to a gradual decrease in the value of subsequent redemptions, violating the principle of fairness and triggering panic redemptions and sales, which can destabilize the market.&#x20;

By implementing a 24-hour Liquidity Protection Period immediately after the block time reaches the liquidity unlock time, only token transfers from the liquidity pool are permitted during this interval. This means that **only the purchase of tokens and the redemption of liquidity can be executed**. This ensures **consistency** in the value of liquidity redeemed by burning POL tokens within this 24-hour window and provides users who redeem liquidity with a period to consider their next steps, preventing panic-induced stampedes and severe market fluctuations.
