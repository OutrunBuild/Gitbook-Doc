# Minting

Users receive yield-bearing assets when they deposit funds into a yield-source. For example, BNB staked in Lista is represented as _slisBNB_. ETH staked in StakeStone is represented as _Stone_.

slisBNB and Stone are examples of **yield-bearing tokens**.

In OutStake, yield-bearing tokens can be split into three components: **Principal Token (PT)**, **Yield Token (YT)**, and **Points Yield Token (PYT)**. Additionally, encapsulating PT allows users to mint **Staked Position Token (SP)**. PT represents the principal portion of the underlying yield-bearing token, YT represents the entitlement to all yields of that asset, PYT represents the external points yields of the position, and SP represents the redemption rights for the principal of the locked position upon maturity.

Users can stake yield-bearing assets (e.g., stETH) in OutStake to mint PT, YT, and PYT. The underlying asset (e.g., ETH) will be automatically converted into an yield-bearing asset before staking.

For example: ETH → stETH → SY-stETH → (SP-stETH + YT-stETH + PYT-stETH)，SP-stETH <=> PT-stETH(UETH).
