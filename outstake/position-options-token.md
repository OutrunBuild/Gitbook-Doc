# Position Options Token

**Position Token** represents the token of a position. When users stake and lock native yield assets, they mint not only Principal Tokens **(PT)** and YieldTokens **(YT)** but also **Position Tokens** to represent their position.

Due to the tradable nature of **Position Tokens**, they can also be viewed as a type of option. This token represents the right to redeem native yield tokens at the end of the lock-up period, and we refer to it as the **Position Options Token**.

The **Position Options Token** allows holders, at the future date **when the position lock-up period expires**, to destroy a fixed number of PTs to redeem a fixed amount of native yield assets. It provides the right to **trade for a fixed interest rate** **without having to trade the PT itself**.

**Position Options Tokens** are supported by the **ERC1155** standard, which allows a single position to be split into multiple shares, enabling users to trade partial redemption rights of the position.

Additionally, holders of **Position Options Tokens** can choose to forcefully redeem their staked native assets early. To perform a forced early redemption, a number of **YTs** related to the early redemption time must be destroyed, and a small fee will be charged.
