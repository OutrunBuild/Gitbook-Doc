# Trading POL, PT, and YT

The market features two initial trading pairs: **POL / UPT** and **PT / POL**.

After the FFLaunch Genesis phase ends, **1/3** of the genesis funds **not borrowed through the POL lending market** will form a trading pair with **1/4** of the POL tokens **not related to the POL lending market**. This mechanism provides the most direct trading pathway for POL tokens.

Since POL tokens can be split into PT and YT, trading of PT and YT occurs through the **PT / POL** liquidity pool and **flash swap**, respectively. Based on the fact that PT and YT can be minted from the underlying POL, their price relationship can be expressed as follows:

$$
P (PT ) ​+ P (YT )​=POL
$$

Given the inverse correlation between YT and PT prices, we leverage this price relationship to trade YT using the PT / POL pool.Buying YT:

1. The buyer sends POL to the Swap contract (which can be automatically routed from any major token).
2. The contract withdraws additional POL from the PT / POL pool.
3. The withdrawn POL is split into PT and YT.
4. The YT is sent to the buyer.
5. The PT is sold for POL to repay the amount borrowed in step 2.

Selling YT:

1. The seller sends YT to the Swap contract.
2. The contract borrows an equivalent amount of PT from the PT / POL pool.
3. The YT and PT are combined to redeem POL.
4. The POL is sent to the seller (or routed to other major tokens, such as ETH, USDC, etc.).
5. A portion of the POL is sold to the PT / POL pool to repay the amount borrowed in step 2.
