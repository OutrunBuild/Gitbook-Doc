# The difference between Outstake and Pendle

Currently, Pendle is the most popular native yield staking protocol on the market. Here’s a comparison of Outstake and Pendle, highlighting the advantages of Outstake and the problems it addresses:

1. **Token Types and Composability**

* **Pendle:** The minted Principal Tokens **(PT)** and Yield Tokens **(YT)** have an expiration date. **PT** and **YT** are not standard ERC20 tokens but are closer to NFTs (Non-fungible tokens). This limits the composability and use cases of assets on Pendle. Especially **YT**, whose value drops to zero at expiration, further restricts its usage.
* **Outstake:** The minted **PT** and **YT** are standard ERC20 tokens without an expiration date, allowing them to be traded on any decentralized exchange **(DEX)** and freely integrated into other DeFi protocols. This design enhances composability and flexibility. Additionally, Outstake’s **YT** can be seen as a stablecoin tied to the yield rate, enabling users to take long or short positions on the yield rate.

2. **Fixed Rate Yields**

* **Pendle:** The number of **PT** minted equals the amount of staked tokens, and **PT** suffer from a negative premium that decreases over time. Fixed-rate yields come from the negative premium of **PT**, i.e., **the loss incurred by stakers**. To obtain a fixed rate, users must purchase the corresponding **PT**. Due to the negative premium, early selling of **PT** results in losses, significantly reducing their practical value and making it difficult to integrate **PT** into other DeFi strategies.
* **Outstake:** The number of **PT** minted is related to the amount of **YT** minted and the redeemable value of **YT**, avoiding the negative premium of **PT**. Outstake introduces tradable **Position Options Token (POT)**, representing the redemption rights of native yield tokens at the end of the lock-up period. This allows users to obtain fixed-rate rights without trading **PT**, improving capital efficiency. The yield comes from demand exchanges, not from staking losses.

3. **Staking Duration**

* **Pendle:** The staking duration is determined by the protocol, and users cannot freely choose the staking period.
* **Outstake:** Users can freely select the staking duration, controlling the amount of **PT**  minted. The staking duration is abstracted as **POT**, making the position expiration time a tradable asset, further increasing flexibility.

4. **Yield Sources**

* **Pendle:** Pendle does not generate real external yields; its fixed-rate yields essentially come from the losses of staking users. Previously, Pendle’s high fixed-rate yields were driven by airdrop incentives from various restaking protocols, leading users to bear losses in exchange for airdrop rewards, which were short-lived.
* **Outstake:** Through the Outrun ecosystem, which supports multiple assets, Outstake creates a rich arbitrage market and multiple income sources. Users can earn native yields, fixed-rate returns from trading **POT**, and numerous arbitrage opportunities based on Outstake assets, enhancing the overall profitability and scalability of the protocol.
