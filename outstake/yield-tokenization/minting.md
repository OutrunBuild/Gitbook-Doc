# Minting

Users receive yield-bearing assets when they deposit funds into a yield-source. For example, BNB staked in Lista is represented as _slisBNB_. ETH staked in StakeStone is represented as _Stone_.

slisBNB and Stone are examples of **yield-bearing tokens**.

In OutStake, yield-bearing tokens can be broken down into three components: **Staked Position Token (SP)**, **Yield Token (YT)**, and **Points Yield Token (PYT)**.

Simultaneously, **SP** can be further divided into **Principal Token (PT)** and **non-transferable SP**, or it can be re-synthesized back into transferable **SP**.

Here's what each token represents:

* **SP** represents the redemption right of the principal of the locked position upon maturity.
* **PT** represents the principal portion of the underlying yield-bearing token.
* **YT** represents the right to all interest earnings of the asset.
* **PYT** represents the external points earnings of the position.

Users can stake yield-bearing assets (e.g., wstETH) in OutStake to mint PT, YT, and PYT. The underlying asset (e.g., ETH) will be automatically converted into an yield-bearing asset before staking.

For example: ETH → wstETH → SY-wstETH → (SP-wstETH + YT-wstETH + PYT-wstETH)，SP-wstETH <=> PT-wstETH(UETH).
