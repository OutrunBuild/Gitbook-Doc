# Liquid Proof Token

**Liquidity Proof Tokens (LPT)** serve as proof of investors' participation in FFLaunch and are a special wrapping of LP tokens, representing their share in the locked liquidity pool. Investors obtain LPT by participating in FFLaunch and locking their liquidity. After the liquidity lock-up period ends, they can burn the LPT to redeem the corresponding liquidity.

During the lock-up period, the value of the locked liquidity fluctuates with the price of the project tokens, exposing investors to the risks associated with the project tokens, thereby increasing the opportunity cost of holding the position. With the introduction of LPT, investors have the option to sell their LPT on the market before the liquidity unlocks, allowing them to lock in current profits and reduce the opportunity cost of holding their position.

The quantities of the two assets in the liquidity pool are dynamic and change with other users' trades, but the share represented by the LPT always corresponds to the same proportion of the liquidity pool. Therefore, the asset amount represented by each LPT can be calculated based on the total assets in the pool and the number of LPT held, which is its **nominal value** (with the actual value being determined upon final burn).

### **LPT Trading Channels**

Unlike project tokens on FFLaunch, which have ample liquidity support, FFLaunch does not provide dedicated liquidity support for LPT. LPT is more like a tool to help investors reduce risk exposure, with its use and trading primarily driven by investor demand, although it could also be influenced by speculative behavior in certain cases. Therefore, the trading frequency of LPT is difficult to predict, but its nominal value tends to fluctuate frequently since it is closely linked to the price fluctuations of the project tokens.

If Outrun AMM were used to provide liquidity for LPT, the capital costs would be high because the total value of LPT and the total circulating value of the project tokens are relatively close. This would require a very large liquidity pool, resulting in low capital efficiency. Therefore, two main approaches are recommended for LPT trading, each with its own advantages:

* **Using the Concentrated Liquidity Engine (Outrun DLAMM):** For long-tail assets, Outrun AMM plays an important role in asset pricing. However, since LPT's value is fully correlated with the project token and has a nominal value, pricing is not necessary. Thus, the concentrated liquidity engine is well-suited for LPT market-making, offering high capital efficiency, but it also has the downside of significant impermanent loss.
* **Using the Limit Order Book Engine (Outrun Limit Order Book):** LPT, as a tool asset, sees its trading activity primarily driven by user demand, and it naturally has a large number of counterparties. Users can freely trade according to their own needs, without relying on professional market makers, while also earning transaction fees. This method avoids impermanent loss but may face the issue of low liquidity depth.

**OutSwap** will soon introduce **DLAMM** and **Limit Order Book** versions following the release of **Outrun AMM**. The presence of LPT will bring more application scenarios to these two mechanisms, greatly reducing the difficulty of accumulating liquidity TVL, while also enhancing user retention and fostering user habits.
