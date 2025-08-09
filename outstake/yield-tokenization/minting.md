# Minting

Users receive yield-bearing assets when they deposit funds into a yield-source. For example, BNB staked in Lista is represented as _slisBNB_. ETH staked in Lido is represented as _stETH_.

slisBNB and Stone are examples of **yield-bearing tokens**.

In OutStake, yield-bearing tokens can be broken down into three components: **Staked Position Token (SP)** and **Yield Token (YT)**.

Simultaneously, **SP** can be further divided into **Omnichain Universal Principal Token (UPT)** and **non-transferable SP**, or it can be re-synthesized back into transferable **SP**.

Here's what each token represents:

* **SP** represents the redemption right of the principal of the locked position upon maturity.
* **UPT** represents the principal portion of the underlying yield-bearing token.
* **YT** represents the right to all interest earnings of the asset.

Users can stake yield-bearing assets (e.g., stETH) on **OutStake** to mint SP, YT, and UPT. The underlying asset (e.g., ETH) will be automatically converted into an yield-bearing asset before staking.

For example: ETH → wstETH → SY-wstETH → (SP-wstETH + YT-wstETH)，SP-wstETH <=> UETH.
