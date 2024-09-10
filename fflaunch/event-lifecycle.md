# Event lifecycle

In the lifecycle of the FFLaunch event, there are a total of 3 entities and 6 stages:

#### Entities

1. Investors
2. Outrun Audit Team
3. Project Team

#### Stages

**1. Apply Stage**

* The project team develops TokenGenerator, Token, and TimeLockVault contracts. The TokenGenerator contract must **implement the ITokenGenerator interface**, and the Token contract **inherits from the FFT contract (override certain methods)**. The TimeLockVault contract serves as a **treasury for leftover tokens outside LaunchPool** (can be updated before the remaining token generation stage by applying to the Outrun Audit Team).
* The project team applies to the Outrun team for FFLaunch listing, submitting detailed project and team information along with TokenGenerator, Token, and TimeLockVault contracts, and maintains ongoing communication with the Outrun Audit Team.

**2. Audit Stage**

* The Outrun Audit Team thoroughly reviews the submitted project team materials.
* The Outrun Audit Team audits the **TokenGenerator, Token, and TimeLockVault contracts** to ensure safety and compliance.
* The release conditions of the Token are checked to ensure that **no new tokens are released during the LP lock period**.
* If the audit does not pass, the Outrun Audit Team provides feedback to the project team, who then need to reapply.
* Upon successful audit, the Outrun Audit Team registers a new LaunchPool in the FFLauncher.

**3. Deposit Stage**

* When the block time is between the registered LaunchPool's startTime and endTime, investors can call the deposit method of the FFLauncher contract to deposit **native yield token** into that LaunchPool. The native yield tokens will be staked in Outstake to obtain [**UPT**](../outstake/yield-tokenization/upt.md) and [**YT**](../outstake/yield-tokenization/yield-token.md). Simultaneously, the TokenGenerator contract registered by the project team will be called to generate the corresponding number of tokens. **A portion of these tokens** will be added to liquidity on Outrun AMM along with the UPT, with the LP being locked in the FFLauncher contract, while the **remaining tokens will be sent directly to the user**. At the same time, **LiquidProof token** will be minted as proof of the liquidity added by the user, and these tokens can also be **freely traded**.
* After the block time reaches the endTime of the registered LaunchPool, it enters the **liquidity lock-up phase**, during which users can no longer stake native yield tokens to mint new tokens.

**4. Liquidity Lock Stage**

* Following the conclusion of the deposit stage, **anyone** can call the FFLauncher contract's enablePoolTokenTransfer method to enable token trading. Tokens can now be freely traded.
* During this stage, the liquidity provider (LP) earnings locked in the FFLauncher contract **accrue to the project team**, providing continuous cash flow from the funds raised.

**5. Liquidity Unlock Stage**

* After the liquidity lockup period expires, users can call the claimPoolLiquidity method of the FFLauncher contract to **burn LiquidProof tokens and withdraw the locked LP tokens**.
* The project team **no longer receives liquidity market maker fee** from this point onward.

**6. Remaining Token Generation Stage**

* This stage begins 7 days after entering the LP Unlock stage. During this phase, the project team can use the FFLauncher contract's generateRemainingTokens method to **mint remaining tokens into the TimeLockVault contract**.
* **If the token is initially fully circulating, no additional tokens can be minted**.

**These entities and stages collectively constitute the complete lifecycle of the FFLaunch event, ensuring the project's security, transparency, and compliance throughout its execution.**
