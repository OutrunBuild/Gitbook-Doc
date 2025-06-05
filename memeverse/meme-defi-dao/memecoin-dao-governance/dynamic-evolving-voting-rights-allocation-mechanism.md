# Dynamic Evolving Voting Rights Allocation Mechanism

In traditional decentralized autonomous organization (DAO) governance models, the allocation of governance voting rights is usually based solely on the number of tokens held. However, the Memeverse ecosystem has innovated this model to better adapt to its **unique economic model and governance needs**.

***

### **Governance Background of Memeverse**

Memeverse is an innovative ecosystem built on the [**FFLaunch**](../../../fflaunch/) concept. The core of FFLaunch lies in the introduction of [**Proof of Liquidity tokens**](../../../fflaunch/proof-of-liquidity-token.md) (POL), which represent users' shares in the genesis liquidity. As a result, users who participate in the genesis effectively hold Memecoin indirectly through their POL tokens, and thus should also have corresponding voting rights in the Memecoin DAO governance.

***

### **Governance Innovation of Memeverse: POL + sMemecoin Dual-Track System**

Based on the Proof-of-Liquidity (POL) mechanism of FFLaunch, a dynamic voting rights allocation system is constructed:

1. **Dual-Source Governance Weighting**
   * **sMemecoin(Staked Memecoin) Holders**: Obtain basic voting rights based on wallet balance.
   * **POL Holders**: Acquire derivative voting rights based on their shares in the genesis liquidity pool.
2. **Dynamic Balance of Voting Rights**
   * **Initial Stage**: 100% of Memecoin is locked in the genesis pool → POL holders have full governance power.
   * **Circulation Expansion Stage**:
     * Memecoin flows into the market through transactions → Basic voting rights are dispersed within the community.
     * POL voting weight automatically decays with the proportion of the liquidity pool.
   * **Mature Stage**: The dual-track voting rights ratio reflects the real-time distribution of Memecoin between the "liquidity pool" and the "circulating market."
3.  **Algorithmic Adjustment Mechanism**\
    Total Voting Rights Calculation Formula:\


    $$
    TVP = \alpha \cdot \frac{POL_i}{POL_{\text{total}}} \cdot Q_{Gen} + \beta \cdot Q_i
    $$

**Explanation of Variables:**

* $$TVP$$：Total Voting Rights of a Single Address
* $$POL_{i}$$：Number of POL Tokens Held by the Address
* $$POL_{\text {total}}$$：Total Supply of POL Tokens
* $$Q_{Gen}$$：Amount of Memecoin Held in the Genesis Liquidity
* $$Q_i$$：Amount of sMemecoin Directly Held by the Address
* $$\alpha, \beta$$：Weighting coefficient（Default $$\alpha = 2,\beta = 1$$，can be adjusted through DAO Governance）

This design ensures that governance rights are always anchored to the real value distribution within the ecosystem.

***

### **Advantages of the Dual-Track System**

#### **Anti-Manipulation**

* **Increased Cost of Manipulation**: Whales need to control both POL tokens and circulating tokens to dominate governance, significantly increasing the cost of malicious behavior.

#### **Incentivizing Early Contributions**

* **Initial Governance Rights for Genesis Contributors**: POL grants initial governance rights to those who provide genesis liquidity, especially the development teams that contribute both capital and technology, avoiding the "free-rider" problem.

#### **Lifecycle Alignment**

* **Issuance Stage**: Governance is controlled by genesis liquidity providers (early community contributors).
* **Growth Stage**: As $$Q_{Gen}$$​ decreases, governance rights automatically shift from early contributors to the broader community, preventing governance stagnation.
* **Maturity Stage**: With the increasing dispersion of token holders, the community's decentralization deepens, and governance is fully driven by community consensus.

**Governance Concentration Adjustment**

* **Optimizing Governance Concentration**: By adjusting the α/β coefficients, governance concentration can be optimized for different project stages (e.g., setting α=2 in the early stage to enhance the voice of genesis developers).

***

### **The Ultimate Form of Governance Democracy**

Through its dual-track voting rights design, Memeverse has achieved:

* **Decentralization of Power Sources**: Breaking the monopolar pattern of "tokens equal power."
* **Dynamic Adaptability of Governance**: Voting weights automatically align with the development stages of the ecosystem.
* **Precise Quantification of Contributions**: Both liquidity provision and token holding behavior jointly determine the right to speak.

This mechanism essentially establishes an **on-chain democratic model that dynamically evolves with contributions**, enabling Memecoin DAO governance to retain the spirit of decentralization while also possessing the evolutionary efficiency of a commercial system. Power naturally migrates with the flow of value, respecting the historical rights of early contributors while safeguarding the democratic foundation of ecosystem evolution. As every transaction in the Memecoin community subtly reshapes the map of governance power, the true on-chain civilization begins to unfold.
