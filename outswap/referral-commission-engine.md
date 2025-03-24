# Referral Commission Engine

### **The Importance of Referral Commission**

The importance of referral commission for cryptocurrency exchanges cannot be overstated, playing a crucial role in user acquisition, community building, and market promotion:

**User Growth**

* **Attracting New Users:** Referral commission incentivize existing users to invite new users to register and trade, effectively expanding the exchange's user base and transaction volume.
* **Reducing Customer Acquisition Costs:** Compared to traditional advertising and marketing methods, referral commissions are cost-effective and efficient.
* **Building Trust:** New users tend to trust recommendations from friends or acquaintances, thereby increasing their trust and loyalty.

**Increasing User Engagement**

* **Encouraging Participation:** Referral commissions motivate existing users to actively promote and invite friends, increasing the exchange's user activity and community interaction.
* **Enhancing User Stickiness:** Commission programs encourage users to stay engaged and participate in exchange activities, enhancing their stickiness and loyalty.

**Market Promotion and Brand Awareness**

* **Wide Dissemination:** Users actively promote the exchange through referral commissions, achieving widespread market dissemination and brand exposure.
* **Viral Marketing Effect:** Through user referrals, rapid expansion of brand awareness is achieved, creating a viral marketing effect.
* **Enhancing Brand Image:** User referrals can enhance the exchange's brand image and market recognition.

**Enhancing Competitiveness**

* **Differentiation Strategy:** Referral commission programs serve as a differentiation strategy, helping exchanges stand out in competitive markets.
* **Improving User Retention:** Users motivated by referral commissions have more incentives to stay on the exchange and invite others, thereby enhancing user retention rates.

Many well-known exchanges like **Binance**, **Coinbase**, and **KuCoin** have experienced rapid growth through referral commission programs. For instance, Binance's referral commission program not only attracted a large number of new users but also significantly increased platform trading volume and activity, becoming a critical factor in its rapid rise.

***

### The former promotion mechanism of decentralized exchanges

There have been two strategies in the market:

**Trade Mining**

This strategy was once very popular, but it had significant drawbacks. Strictly speaking, trade mining is not a promotional strategy but rather an unsustainable Ponzi scheme. Many early DEXs incentivized trading by **directly issuing governance tokens to traders**, effectively using project tokens to buy trading volume. This approach was not only difficult to sustain in the long term but also caused significant harm to token holders. The loss of trust in the project team led to sell-offs, and the inflation of tokens due to trade mining ultimately resulted in a sharp decline in the token’s price. The resulting price collapse reduced the returns from trade mining, leading to a death spiral.

**Points Mining**

This strategy has been more frequently used recently, but it is fundamentally no different from trade mining since points are eventually exchanged for project tokens. The only difference is that it is executed off-chain, allowing the project team to maintain better control. However, its efficiency in user growth is not even as good as that of trade mining from a few years ago, and it also suffers from issues such as lack of transparency. In comparison, liquidity staking protocols are more suitable for points mining strategies.

However, neither of these strategies promotes with real profits, and both have been phased out by both CEXs and DEXs. They focus on promoting from the trader’s perspective, resulting in a large amount of fake trading data, rather than spreading through users organically promoting to other users. Outrun AMM adopts a completely different on-chain referral rebate engine, **introducing new stakeholders**.

***

### Referral commission design for Outrun AMM

Designing a referral commission program for a decentralized exchange (DEX) requires considering its significant differences from centralized exchanges (CEX). The referral commission program for Outrun AMM focuses on the following points to fully leverage its decentralized nature and the advantages of smart contracts, while ensuring user experience and composability:

**Use of Smart Contracts**

* **Automated Distribution:** Execute referral commission through smart contracts to automatically calculate and distribute commission upon trade completion. This ensures transaction transparency and prevents any manual tampering.
* **Instant Settlement:** Smart contracts can instantly distribute referral commissions to referrers after each trade. This not only increases user trust but also boosts user engagement.

**User Experience**

* **Simple Referral Process:** Ensure that users can easily generate and share referral links. The referred users complete registration by trading through the link.
* **Clear Rewards Display:** Provide a user-friendly interface that clearly shows the accumulated and settled referral rewards. Users should be able to easily view their referral earnings.

**Composability**

* **Openness:** Allow anyone to build new referral services based on Outrun AMM without relying on a single peripheral contract. This way, third-party services can direct trades and earn referral fees.
* **Protocol Composability:** Enhance protocol composability by making referral commission features open, enabling third parties to develop new DeFi products based on the referral engine, thereby enriching the entire ecosystem.

**Enhancing Market Makers' Interests**

* **Source of Referral Fees:** Referral fees comes from a portion(**20%**) of the protocol fee, not from the market makers' due fees. This ensures that the referral commission mechanism does not harm the interests of market makers.
* **Increasing Market Makers' Earnings:** The referral engine helps increase trading activity, attracting more trading volume, and thereby increasing the earnings of market makers.

**Enhancing Liquidity Bootstrapping**

Currently, at least 50% of the trading volume on decentralized exchanges (DEXs) in the market comes from aggregator trading protocols such as 1inch, Jupiter, and ParaSwap. Their guidance on liquidity is crucial. Compared with the traditional slippage earnings of aggregator trading protocols, the referral commission engine can provide these aggregator trading protocols with more stable income. Meanwhile, these aggregator trading protocols can also bring more trading volume to OutSwap, thus achieving a win-win situation.
