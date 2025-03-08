# Event lifecycle

In the lifecycle of the FFLaunch event, there are a total of 3 entities and 6 stages:

#### Entities

1. Investors
2. Outrun Audit Team
3. Project Team

#### Stages

Starting from the **genesis stage**, each stage transition of the **LaunchPool** requires manually calling the **changeStage** method of the **FFLauncher** contract.

**1. Apply Stage**

* The project team develops TokenGenerator, Token, and TimeLockVault contracts. The TokenGenerator contract must **implement the ITokenGenerator interface**, and the Token contract **inherits from the FFT contract (override certain methods)**. The TimeLockVault contract serves as a **treasury for leftover tokens outside LaunchPool** (can be updated before the remaining token generation stage by applying to the Outrun Audit Team).
* The project team applies to the Outrun team for FFLaunch listing, submitting detailed project and team information along with **Token, TokenGenerator and TimeLockVault contracts**, and maintains ongoing communication with the Outrun Audit Team.

**2. Audit Stage**

* The Outrun Audit Team thoroughly reviews the submitted project team materials.
* The Outrun Audit Team audits the **TokenGenerator, Token, and TimeLockVault contracts** to ensure safety and compliance.
* The release conditions of the Token are checked to ensure that **no new tokens are released during the LP lock period**.
* If the audit does not pass, the Outrun Audit Team provides feedback to the project team, who then need to reapply.
* Upon successful audit, the Outrun Audit Team registers a new LaunchPool in the FFLauncher.

**3. Genesis Stage**

* When the current block time is between the startTime and endTime of the LaunchPool, anyone can call the changeStage method to enter the genesis phase.
* During the genesis phase, investors can deposit [**UPT**](../outstake/yield-tokenization/pt.md) into the ongoing LaunchPool. The FFLauncher will record the **GenesisFund** deposited by each investor. **1/3** of the GenesisFund is **liquidProofFunds**, and **2/3** is **tokenFund**, which will be added to **totalTokenFunds** and **totalLiquidProofFunds** respectively.

**4. Liquidity Lock Stage**

* When the current stage is the genesis stage and the block time is between the endTime and unlockedTime of the LaunchPool, anyone can call the changeStage method to enter the liquidity lock-up stage. Meanwhile, the **token generator** registered by the project team will be called to mint the corresponding project tokens according to the totalTokenFunds. These project tokens will form a trading pair with the UPT whose quantity is equivalent to that of the **totalTokenFunds** and be deployed on the **OutrunAMM**. The liquidity pool (LP) will be locked until the **unlockedTime**. Meanwhile, [**POL**](proof-of-liquidity-token.md) tokens with the same quantity as that of the LP will be minted. **1/4** of the POL tokens will form a trading pair with the UPT whose quantity is equivalent to that of the **totalLiquidProofFunds**, and the liquidity will be locked until the unlockedTime. Users can manually claim the remaining **3/4** of the POL tokens.
* During the liquidity lock-up stage, the market-making earnings generated from the liquidity of the locked project token trading pairs belong to the project team, which is the continuous cash flow raised by the project team. And the market-making earnings generated from the liquidity of the locked POL token trading pairs belong to the protocol revenue.

**5. Liquidity Unlock Stage**

* When the current stage is the liquidity lock-up stage and the block time is greater than the unlockedTime of the LaunchPool, anyone can call the changeStage method to enter the liquidity unlock stage.
* During the liquidity unlock stage, investors can redeem the liquidity of the POL/UPT trading pair according to the proportion of the funds they deposited in the genesis stage. Meanwhile, they can also burn the POL tokens to redeem the LP tokens of the ProjectToken/UPT trading pair in the same quantity.
* A 24-hour [**Liquidity Protection Period**](proof-of-liquidity-token.md) is implemented immediately after the block time reaches the unlockTime. During this period, only token transfers from the liquidity pool are permitted, while transfers from other addresses are restricted. This means that only the purchase of tokens and the redemption of liquidity can be executed during this time.

**6. Remaining Token Generation Stage**

* After the liquidity unlock stage lasts for **14** days and enters this stage, anyone can call the changeStage method to enter the stage of generating the remaining tokens.
* During the stage of generating the remaining tokens, the project team can call the **generateRemainingTokens** method of the FFLauncher contract to mint the remaining tokens to the **TimeLockVault** contract.
* **If the token is initially fully circulating, no additional tokens can be minted**.

**These entities and stages collectively constitute the complete lifecycle of the FFLaunch event, ensuring the project's security, transparency, and compliance throughout its execution.**
